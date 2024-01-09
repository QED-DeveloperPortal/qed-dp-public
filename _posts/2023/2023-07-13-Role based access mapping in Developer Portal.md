---
title: Role based access mapping in Developer Portal
author: jeny-qed
categories: [public]
tags: [getting-started,about]
date: 2023-07-13 01:14:37 
updatedBy: Joyclyn
updated: 2023-11-29 02:51:24 
likes: 0
---

## Introduction
The following table provides an overview of how access is controlled via custom roles using AAD B2C in Developer Portal application. 


| | |User Roles| | | | |
|:----|:----|:----|:----|:----|:----|:----|
| | |none|authenticated|internal|moderator_general|administrator|
| | | | | | | |
|Home| |Y|Y|Y|Y|Y|
|Navigation|Home|Y|Y|Y|Y|Y||
| |Categories|Y|Y|Y|Y|Y|
| |Tags|Y|Y|Y|Y|Y|
| |APIs|Y|Y|Y|Y|Y|
| |Help|Y|Y|Y|Y|Y|
| |Contact us|Y|Y|Y|Y|Y|
| |Toggle Theme|Y|Y|Y|Y|Y|
| |Admin|N|N|N|N|Y|
|Categories|View posts under public|Y|Y|Y|Y|Y|
| |View posts under internal|N|N|Y|Y|Y|
||Add  post for category|N|N|Y|Y|Y|
| |Update  post for category|N|N|Y|Y|Y|
| |Edit  post for category|N|N |Y|Y|Y|
| |Like post|N|Y|Y|Y|Y|
| |Submit feedback on post|N|Y|Y|Y|Y|
|Tags|View all tags|Y|Y|Y|Y|Y|
| |Subscribe/unsubscribe to tags|N|N|Y|Y|Y|
|Help|FAQ|Y|Y|Y|Y|Y|
|Contact us|Send feedback|N|Y|Y|Y|Y|
|Admin|View posts pending approval|N|N|N|N|Y|