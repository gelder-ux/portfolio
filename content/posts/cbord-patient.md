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
CBORD Patient offers custom-made menus for hospital patients and guests. Menus are built to respect diet orders assigned to the patient.    

## Background
A number of hospital menuing systems were already in place for our existing customers. These systems allow hospitals to manage menus, patient diet information, and meal orders. Prior to the app, patients would need to use paper menus and were left unsure of which foods they were allowed to eat. We had an opportunity to improve both the staff and patient experiences through a consumer-facing mobile app: CBORD Patient.

### Patients
![Patient empathy map](/uploads/tca-user-empathy-map.jpg)
###
At its core, this was a simple food ordering app. But since we were designing for patients, who range widely from one demographic to another, it was impossible to make assumptions about age, ethnicity, language, or literacy. We had to be sensitive to their current situation. At any time, patients could experience stress, pain, anxiety, and helplessness. Everyday choices that were once theirs to make were now being made for them by strangers. 

It was incredibly important for us to design a food ordering experience that was both simple and empowering. Allowing patients to choose for themselves again was our goal. 

### Hospitals
In addition to the patient, we needed to make sure the app served hospitals in a meaningful way. Prior, a few of our customers had hired third-party developers to create a front end for the APIs exposed by our backend systems. This had mixed results for patients in terms of ease-of-use and adoption and ultimately left many patients confused and frustrated by the technical jargon and obtuse wayfinding of these apps. Not to mention many of these apps were integrated with television systems which also exacerbated navigation frustration.

### Team
At the start of the project, the team consisted of a Business Analyst and myself as the UX Designer. Our analyst was also a healthcare dietician and so we worked closely on the user experience. 

### Security
It's important to note that from a patient confidentiality standpoint, the app does not store any personal information. It is part of a secured system within the hospital.

### Core Features
The key differentiating feature of the app is its insight into the patient's current dietary order specified by the hospital. For example, a patient that is about to undergo surgery would be assigned an NPO diet order. Meaning that they are not allowed to eat anything prior to their procedure. This information would be conveyed to the app, which would then filter out all meal options. 

Since the app takes into account the patient's diet order, it will budget and track the relevvant nutrients contained within the food options. This mechanism helps the user to not only plan their meal, but also helps them understand food nutrition a little better.  

Another challenge we had was making sure that the app could handle guest orders. Our existing hospital system supports the notion of patient guests. These guests could be spouses, family members, relatives, friends, etc. 

## Beginnings
I began by defining the information architecture and navigation system post-login. Since the core of the app was about ordering, I thought it best to nail down that experience first. I decided to keep it simple by presenting a list of meals on the home screen. Once a user selects one, "Breakfast" for example, they are presented with the menu view and begin the item selection loop, or order lifecycle. 
![User Flow](/uploads/tca-nav-system-v2.jpg)

### Onboarding
The onboarding flow posed a challenge: we needed a secure method of verifying that the user was truly the patient they claimed to be. We posited a few ideas but ultimately landed on the most secure method. The user needs to provide their date of birth, medical record number (MRN), and the hospital's facility ID (defined by our backend system). The MRN is commonly found on the patient's wristband.


![Core Flow](/uploads/tca-core-flow.jpg)
![Menu Wireframe](/uploads/tca-wireframe-1.jpg)
![Finished Login](/uploads/tca-finished-login.png)
![Who are you?](/uploads/tca-finished-who.png)
![MRN](/uploads/tca-finished-mrn.png)
![Meals](/uploads/tca-finished-meals.png)
![Menu](/uploads/tca-finished-menu-default.png)
![Menu that is over](/uploads/tca-finished-menu-over.png)
![Menu that is over](/uploads/tca-finished-switch-user.png)
![Menu that is over](/uploads/tca-finished-order-summary.png)


## Usability Testing

## Future Plans
- Guest Payment

Download
- [App Store](https://apps.apple.com/us/app/cbord-patient/id1319336992)
- [Google Play](https://play.google.com/store/apps/details?id=com.cbord.patient&hl=en_US)
