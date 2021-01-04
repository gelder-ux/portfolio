---
title: Patient Food Ordering App
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
# Role
UX Designer

# Overview
As the name implies, this is a meal ordering app for hospital patients. With safety as the prime concern, the app guarantees that menu offerings abide by the dietary requirements of each patient by integrating with the hospital's EHR system.

# Problem
A number of our proprietary hospital menuing systems were already in place for our existing customers. These systems allowed hospitals to manage menus, patient diet information, and meal orders. However, prior to the app, patients would need to use paper menus and were left feeling unsure of which foods they were allowed to eat. We had an opportunity to improve both the staff and patient experiences through a consumer-facing mobile app.

# Hypothesis
By reducing meal ordering inefficiencies, we hoped to remove one of the many bottlenecks within the healthcare system. Patients are empowered to order for themselves via their smartphones and hospital staff are allowed to focus on their priority-one responsibilities. 

## Patients
![Patient empathy map](/uploads/tca-user-empathy-map.jpg)
##
Since we were designing for patients, it was impossible to make consistent assumptions about age, language, and familiarity with technology. Patients often experience stress, pain, anxiety, and helplessness when admitted to a hospital. Everyday choices that were once theirs to make were being made for them by strangers. With this loss of control, it was important for us to design an experience that was both simple, yet empowering. 

## Hospitals
We needed to make sure that the app served hospitals in a meaningful way as well. In the past, some customers had hired third-party developers to create user interfaces leveraging the APIs that we had made available from our backend systems. This had mixed results for patients in terms of ease-of-use and adoption, and ultimately left many patients confused and frustrated by the technical jargon and obtuse navigation of their "solutions."

## Team
At the start of the project, the team consisted of a Business Analyst and myself as the UX Designer. Our analyst came from a healthcare dietician background which gave us a head start in terms of context and requirements. For example, there are various types of "dietary orders" used by hospitals that limit the amount of specific nutrients found within meal items. Having an RDN on the team provided key insights during the design phase. Eventually, as the project gained traction, our team expanded to include multiple developers, QA testers, and one other designer.

## Security
One note of importance was that from a patient confidentiality standpoint, it was required that the app NOT store any personal information. In other words, it was required that the app comply with privacy laws, both within the United States and Australia.

## Core Features
The key differentiating feature of the app is its insight into the patient's current dietary order specified by the hospital. For example, a patient that is about to undergo surgery would be assigned an NPO, "Nothing by mouth", diet order. Meaning that the patient is not allowed to eat anything prior to a procedure. This information sent to the app, which would then filter out all food items that do not meet the order criteria; in this case, all foods. 

Since the app takes into account the patient's diet order, it will budget and track the relevant nutrientsn meal options. This mechanism helps the user to not only plan their meal, but also shows them the effects that their meal choices will have on their overall nutrition.   

Another challenge we had was making sure that the app could handle guest orders. Our existing hospital system supports the notion of patient guests. These guests could be spouses, family members, relatives, friends, etcetera. 

# Beginnings
I began by defining the information architecture of the app and its navigation system. Since the core of the app was about ordering, I thought it best to nail down that experience first. I decided to keep it simple by presenting a list of meals on the home screen. Once a user selects one, "Breakfast" for example, they are presented with the menu view and begin the order lifecycle. 
#
![User Flow](/uploads/tca-nav-system-v2.jpg)
#
As shown in the diagram, the user advances the state of the order by making food selections, looking at the order summary, and ultimately placing the order; the core loop.
# Onboarding
We also needed a secure method of verifying the identity of the user in order to associate them with the enrolled patient. The user needs to provide their date of birth, medical record number (MRN), and the hospital's facility ID (defined by our backend system). This combination of information guarantees the validity of the user as the patient or a guest of the patient.
# Guest Ordering
Our existing backend systems support the notion of patient guests. This gives hospitals the ability to process patient and guest meals together so that they can be served at the same time. These are represented by "roles". Examples include: Father, Mother, Friend, and any other types defined by the hospital. For this reason we decided that the app would also need to support both patient and guest ordering.
#
![Core Flow](/uploads/tca-core-flow.png)
We revised the core ordering flow to accommodate this more complex requirement. The user is able to switch roles at any time during the ordering process via our "patron picker" mechanism. 
# The Menu
![Early Wireframes](/uploads/tca-early-wireframes.png)
#
By far, the menu view underwent the most iteration throughout the project. Our initial designs displayed a 2 column tile grid of foods. However, upon usability testing, we found that users wanted to see more options at a time. Scannability and scroll fatigue contributed to this feeling. Also, if items did not have photos (which the hospitals often would not upload), the usability of the grid declined; items would appear as solid blocks of color and would often distract users. Subsequent designs leveraged a more subtle list view that could handle missing food images more elegantly. 
#
![Elegant menu](/uploads/tca-menu-missing-thumbnail.png)
#
A key feature to note is the nutrient gauge. Depending on the patient's diet order, nutrient gauges are displayed which track nutrient(s) according to the diet order. As the patient adds foods to their order, the gauges update to reflect the amount of the tracked nutrients found within those foods. These act as a sort of "budget" for the patient. If the patient selects an item that pushes a particular nutrient over its budget, the order cannot be placed until he returns his nutrient level under acceptable level by selecting different foods. This has a compound positive effect: for the hospital, this system ensures that diet orders are being respected, and for patients, it allows the flexibility of choice in their food (within medical reason).      
# Development
Like many projects, we were under an aggressive timeline. As such, we did not have proper usability testing processes established before development was scheduled to start. Much of the design of the app occured in tandem with the development team; complete with redesigns, rough code, technical debt, miscommunications, and BUGS. Though we were able to mature the product over time in the end, I believe its important to acknowledge such realities and learn from them so as to not repeat the same process mistakes. Since then, the design and the app itself have stablized.
#
![Finished Onboarding](/uploads/tca-early-finished-1.png)
#
The onboarding experience underwent many iterations as well. Upon prelimenary usability testing, we found that the process for creating an account to be tedious for the user. Some struggled with creating a password and verifying their account. Some struggled with the date picking control that we used for specifying date-of-birth. In subsequent iterations, we simplified the password creation process and used a simpler date picking pattern. Upon retest, those issues went away. 
# Usability Testing
![Usability Testing](/uploads/tca-usability-testing-raw.png)
#
As the app got closer to a formal release, we were able to conduct more robust testing with the general public at one of our user group conferences. Attendees had the chance to sign up for a testing session and were asked to complete a number of tasks relating to signing up, selecting menu options, and placing orders. Our findings echoed many of the trouble spots we had identified such as the date picker issues, layout of the menu, and general occasional bugs. We were able to take this data back to the development team and make recommendations for improvements.
# Future
As the app continues to gain feedback from customers and patients alike, so too will efforts be made to enhance the user experience for the better. Below are a few screenshots of the app as it is today.  
#
![Finished Meals](/uploads/tca-finished-2.png)
#
![Finished Menu](/uploads/tca-finished-3.png)
#
![Finished Placed Order](/uploads/tca-finished-4.png)