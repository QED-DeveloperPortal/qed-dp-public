---
title: Offline first - a look at how the R4Q app manages data between device and cloud
author: matt
categories: [public]
tags: [cloud,architecture]
date: 2023-05-16 03:29:31
updatedBy: jayarvee
updated: 2023-05-16 03:30:20
likes: 0
---

The recent R4Q Application Uplift project saw the creation of a new Xamarin 5.0 mobile app and Angular 14 web site, with both supported by a .NET Core 3.1 Web Api service layer hosted in Microsoft Azure.

The application was designed to be used in offline scenarios, utilising a true "offline first" capability - where media and notes can be added to a case study in an offline state and synced with the cloud at some later point in time.

Central to this capability was a data broker between online and offline states - the Data Integrity Service (or DIS).

What follows are some thoughts about how the DIS works, it's original design goals and how it has evolved, it's current state and thoughts about how to refactor the service to bring it closer to some of those original design goals that it has moved away from over time.

## Purpose
The purpose of the DIS is to support one of the important goals of the R4Q mobile application to offer true "offline first" capability. Users of the mobile application will oftentimes be offsite and visiting daycare centres, sometimes with little or no internet connectivity.

Evidence collected and edited on the device in such locations remains on the device only, until such time as internet connectivity is achieved. Only at this time will evidence be pushed to the cloud.

In this way, the service truly acts as the sole broker between the offline and online states of the R4Q product.

## Original design goals
Here are some of the original design goals of the DIS.

### Run often (implicitly or explicitly)
The service was designed to run regularly, either explcitly by the user, or implicitly due to some change of environmental state (device moves from having no internet connectivity to having internet connectivity, or the app resumes after being in a 'sleep' state). Whenever the service runs it should determine if any work is do be performed in the most efficient way possible.

### Only do as much work as required, no more
The service should not run infrequently and be expected to consume a lot of resources (time, bandwidth, device battery) and move a lot of data between the device and cloud. Rather, it should run frequently, perform an appropriate amount of work and then stop work gracefully.

### Semi automated to ensure message queue is never too big
Further to the point above, the service is configured so that:

* It may only run again after n minutes has elapsed since it's last successful implicit run;
* After uploading n bytes of data in a single implicit run it will gracefully conclude the run;
* After downloading n bytes of data in a single implicit run it will gracefully conclude the run;
* After the running time of the current implicit run exceeds n minutes it will gracefully conclude the run;

Note that these constraints are not enforced if the user explcitly initiates the service run.

## Current state
The DIS originally employed a simple message queue to record the state and order of work that needed to be performed when it ran. Data was created/updated/deleted on the mobile device and then the required changes were pushed to cloud when the service would run. Initially this meant that changes were pushed to the cloud only - a one way sync. This pattern initially worked very well.

As the service evolved there became a requirement for a two way synchronisation between mobile device and cloud. Concurrency rules were determined but the time taken on each run started to increase as the service determined what work (if any) should be performed.

This was exacerbated as new requirements were introduced to support secondary officers - now data was to be synced between device and cloud and also between multiple users/devices.

This has resulted in the original design pattern no longer being appropriate and the service becoming convoluted and bloated.

The most recent refactor sought to address the time taken to determine whether any syncronisation work needed to be performed.

Artefacts such as evidence notes, evidence photos, tags, memos etc were all associated with a GUID (globally unique identifier), both on the device and in the cloud (where they were stored in SQL Azure). Whenever such a record was added or changed, the GUID was also updated. Artefacts were grouped together and a checksum was calculated for each group. Whenever the DIS runs the local and cloud based manifest is compared - if there is a mismatch in any of the high level groupings the service then drills down to see what needs to be pushed or pulled.

This change only partially addressed the issues being experienced. The current DIS implementation still remains difficult to understand and is not particularly efficient.

## Potential/suggested changes
Two ideas that have been postulated:

### Don't dynamically calculate the artefact manifests on every run of the DIS.
Rather than dynamically calculating the manifest comparison, calculate and store in table on every save, both locally and in the cloud.
Then no need to constantly calculate - just lookup and compare local and azure values at DIS run time.

### Implement a cloud based message queue to match the local queue on the device
Would have to determine concurrency rules but effectively just process both queues.

* Would eliminate the need for a manifest comparison between the device and the cloud.
* Ensure any message items on the local queue have enough information to indicate if other target users should be affected (secondary officers)
* Ensure any message items on the cloud based queue have enough information to indicate if other target users should be affected (secondary officers)