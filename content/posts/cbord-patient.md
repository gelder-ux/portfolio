---
title: CBORD Patient
subtitle: Designing a Better Patient Experience
category:
  - Food
author: Will Gelder
date: 2020-04-07T17:30:16.858Z
featureImage: /uploads/cp.png
role: UX Designer
market: Healthcare
# duration: 1 year
users: Patients
description: A
---
![CBORD Patient](/uploads/cp.png)
## Overview
CBORD Patient is a meal ordering app for patients. With safety as the prime concern, CBORD Patient guarantees that menu offerings are custom-tailored to meet the needs of each and every patient.    

## Problem
A number of our proprietary hospital menuing systems were already in place for our existing customers. These systems allowed hospitals to manage menus, patient diet information, and meal orders. However, prior to the app, patients would need to use paper menus and were left feeling unsure of which foods they were allowed to eat. We had an opportunity to improve both the staff and patient experiences through a consumer-facing mobile app: CBORD Patient.

## Solution
By reducing meal ordering inefficiencies, CBORD Patient hopes to remove one of the many bottlenecks within the healthcare system. Patients are empowered to order for themselves via their smartphones and hospital staff can be freed up to focus on their high priority responsibilities. 

### Patients
![Patient empathy map](/uploads/tca-user-empathy-map.jpg)
###
Since we were designing for patients, it was impossible to make consistent assumptions about age, language, and familiarity with technology. Patients often experience stress, pain, anxiety, and helplessness. Everyday choices that were once theirs to make were being made for them by strangers. With this loss of control, it was important for us to design an experience that was both simple, yet empowering. 

### Hospitals
We needed to make sure that the app served hospitals in a meaningful way as well. In the past, some customers had hired third-party developers to create user interfaces leveraging the APIs that we had exposed from the backend systems. This had mixed results for patients in terms of ease-of-use and adoption, and ultimately left many patients confused and frustrated by the technical jargon and obtuse navigation. Not to mention many of these apps were integrated into hospital television systems which also exacerbated patients.

### Team
At the start of the project, the team consisted of a Business Analyst and myself as the UX Designer. Our analyst was a healthcare dietician (RDN) which gave us a head start in terms of assumptions we needed to make about patient nutrition. For example, there are various types of "dietary orders" used by hospitals that limit the amount of specific nutrients found in food. Having an RDN on the team provided key insights during the design phase. Eventually, as the project gained traction, our team expanded to include multiple developers, QA testers, and designers.

### Security
It's important to note that from a patient confidentiality standpoint, the app does not store any personal information. It is part of a secured system within the hospital.

### Core Features
The key differentiating feature of the app is its insight into the patient's current dietary order specified by the hospital. For example, a patient that is about to undergo surgery would be assigned an NPO diet order. Meaning that they are not allowed to eat anything prior to their procedure. This information would be conveyed to the app, which would then filter out all meal options. 

Since the app takes into account the patient's diet order, it will budget and track the relevvant nutrients contained within the food options. This mechanism helps the user to not only plan their meal, but also helps them understand food nutrition a little better.  

Another challenge we had was making sure that the app could handle guest orders. Our existing hospital system supports the notion of patient guests. These guests could be spouses, family members, relatives, friends, etc. 

## Beginnings
I began by defining the information architecture and navigation system, post-login. Since the core of the app was about ordering, I thought it best to nail down that experience first. I decided to keep it simple by presenting a list of meals on the home screen. Once a user selects one, "Breakfast" for example, they are presented with the menu view and begin the order lifecycle. 
###
![User Flow](/uploads/tca-nav-system-v2.jpg)

As shown in the diagram, the user advances the state of the order by making food selections, looking at the order summary, and ultimately placing the order; the core loop.

## Onboarding
We also needed a secure method of verifying the identity of the user in order to associate them with the enrolled patient. The user needs to provide their date of birth, medical record number (MRN), and the hospital's facility ID (defined by our backend system). This combination of information guarantees the validity of the user as the patient.

## Guest Ordering
Our existing backend systems support the notion of patient guests. This gives hospitals the ability to process patient and guest meals. These are represented by "roles". Examples include: Father, Mother, Friend, and any other types defined by the hospital. For this reason we decided that the app would also need to support both patient and guest ordering. 
##
![Core Flow](/uploads/tca-core-flow.png)
We revised the core ordering flow to accommodate this more complex requirement. The user is able to switch roles at any time during the ordering process via our "patron picker" mechanism. 

## The Menu
![Early Wireframes](/uploads/tca-early-wireframes.png)

By far, the menu view underwent the most iteration throughout the project. Our initial designs displayed a 2 column tile grid of foods. However, upon usability testing, we found that users wanted to see more options at a time. Scannability and scroll fatigue contributed to this feeling. Also, if items did not have photos, the usability of the grid declined; items would appear as solid blocks of color and often distracted users. Subsequent designs leveraged a more subtle list view that could handle missing food images more elegantly. 

A key feature to note are the nutrient gauges (found at the bottom of the menu in earlier designs). These gauges are displayed according to the patient's diet order assigned to them. Each gauge tracks a nutrient controlled by the diet order. As the patient adds foods to their order, the gauges update to reflect the amount of nutrients found in those foods. These act as a sort of "budget" for the patient. If the patient is over their budget, they cannot place the order and have to balance out their meal in order to stay under their limits.     

## Development
Due to the aggressive nature of the project timeline, we did not have the luxury of creating and testing all of our assumptions before development was scheduled to start. Much of the design of the app occured in tandem with the development team.  



![Finished Onboarding](/uploads/tca-early-finished-1.png)
The onboarding experience underwent a lot of iteration as well. Upon prelimenary usability testing, we found that the process for creating an account to be tedious for the user. Some struggled with creating a password and verifying it. Some struggled with the date picking control we used when specifying their date of birth. In further iterations, we simplified the password creation process and using the native device date picker control. Upon retest, those issues went away. 


![Finished Meals](/uploads/tca-finished-2.png)

![Finished Menu](/uploads/tca-finished-3.png)

![Finished Placed Order](/uploads/tca-finished-4.png)



## Usability Testing
![Usability Testing](/uploads/tca-usability-testing-raw.png)
Testing was made difficult by the dual nature of the project; design and development happened in parallel leading to broken builds, design updates, and communication issues with the backend. However, we did bring a test build to our user group conference and conducted usability tests with attendees with Healthcare expertise.  

## Future Plans
- Enhancements to the onboarding experience
- Guest Payment

## Retrospective


Download
- [App Store](https://apps.apple.com/us/app/cbord-patient/id1319336992)
- [Google Play](https://play.google.com/store/apps/details?id=com.cbord.patient&hl=en_US)
