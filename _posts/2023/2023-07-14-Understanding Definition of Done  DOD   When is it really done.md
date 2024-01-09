---
title: Understanding Definition of Done (DOD)  When is it really done
author: jeny-qed
categories: [public]
tags: [scrum,agile]
date: 2023-07-14 01:40:28 
updatedBy: jeny-qed
updated: 2023-07-25 22:09:20 
likes: 8
---

## Introduction

To understanding the '**Definition of Done**', it is imperative to understand what counts as being "done". As per Scrum Guide, every sprint is meant to add value to the product by producing usable, shippable deliverables i.e. **increments**.

> As per Scrum Guide, an increment is a concrete stepping stone towards the Product Goal and each increment is additive to all prior increments, thoroughly verified, ensuring that all increments work together.

A Product Backlog item becomes an increment once it meets the Definition of Done.

> Definition of Done is a formal description of the state of the increment when it meets the quality measures required for the product.

It is a shared understanding within Scrum team on what it takes to make a PBI releasable. It may vary significantly for every Scrum team. and is used to access when work is complete on the product Increment.

## Components of Definition of Done

* Business or Functional Requirements
* Quality
* Non-Functional Requirements

**Business or Functional Requirements**

* This component is owned by the Product owner and written in the form of the User Stories and acceptance criteria.

**Quality**

* This component is owned by Development team and largely aligned with the coding/technical tools used to build the Product. Examples include
    * Coding standards
    * Unit test coverage
    * Technical Debt
    * No Known Defects

**Non-Functional Requirements**

* These are standard characteristics for the Product that may not add direct business value.
    * Performance
    * Security
    * Scalability
    * Compliance/Regulatory etc.
* They are usually included in Acceptance Criteria or PBI.

| Business Requirements | Quality | Non-Functional Requirements |
| --------------------- | ------- | --------------------------- |
| All acceptance criteria met | No build failures | Relevant documentation updated|
| No dependence unattended | Functional testing passed | Compliance Documents updated |
|  | Integration testing passed | Code checked in / merged with branch |
|  | No known defects |  |
|  | Compatible with DoE brand |  |
|  | No accessibility errors |  |
|  | Compatible with mobile devices | |

### References:

* [Scrum Guide](https://scrumguides.org/scrum-guide.html)