---
title: Aqua Design System
subtitle: Fluid, Usable, Friendly, Beautiful, Concise
category:
  - Design Systems
# author: Will Gelder
date: 2019-08-03T19:59:59.000Z
featureImage: /uploads/ads-cover.png
role: Project Lead
# market: Internal
# duration: Ongoing
# users: CBORD Designers & Developers
---
![Aqua Design System](/uploads/ads-cover.png)
# Role: Project Lead

# Context
For decades, teams at CBORD & Horizon were organized into siloes. As such, teams chose to adopt differing UI technologies, resulting in a suite of products with inconsistent UX. Interaction patterns learned by the user for one product did not translate to the next. At its best, users would have to learn new patterns for common tasks, at its worst, users would not understand them at all. In 2015, as the company began to invest more in design, and more products than ever needed to be developed, it was clear that we needed a shared design language to help standardize the UX across the company; what we dubbed the "Aqua Design System".

# Early Efforts
## Communication
Early efforts focused on gaining buy-in from groups within the company. At the time, the design team consisted of myself and one other designer. We noticed the differences between existing products and even between our own designs and so we quickly understood the need for a unifying system. We socialized the concept to Marketing, Development, Product Management, and Leadership teams. Luckily, each group agreed that the inconsistent experiences between products were a problem and that having ready-made components would speed up our delivery. With each groups blessing, we set out to establish such a system.   

## Guidelines and Tools
Some of the earliest deliverables included a documentation website and a Sketch library using Brad Frost's [Atomic Design Methodology](https://bradfrost.com/blog/post/atomic-web-design/), version-controlled in Abstract. 

![design.cbord.com](/uploads/ads-com.png)

We initially developed our own documentation website but quickly found that keeping it up to date was an inefficient process and quickly became hard to keep in sync with design changes; we needed something more automated. We decided to use the service [Zeroheight](https://zeroheight.com/) for its integration with Sketch (and later on, Figma).


![Aqua Design System Abstract project](/uploads/ads-abstract.png)

At the time, Sketch's component-based model seemed to align with our methodology. Coupled with Abstract's "git"-like versioning, our process made sense to each of us. But we quickly found out that new designers who were unfamiliar with git and Atomic design found the workflow and organization confusing. Designer's local versions would often conflict with new versions of the same file and merging conflicts were numerous.

###
![Aqua Design System Figma Project](/uploads/ads-figma.png)

Ultimately, we re-evaluated and made the call to switch from Sketch to Figma for a number of reasons.
1. Collaboration - This was by far the largest improvement to our workflow. Not only could designers occupy the same file and critique work, but our stakeholders, development teams, and marketing departments could easily view it.
2. Version Control - The ability to revert a component to an earlier state was a hard requirement for us.  
3. Component Overrides - Sketch's component model made it very difficult to create complex components that could easily be overrided. Figma's component authoring experience is continually improving with features such as variants, auto-layout, and soon-to-be-released "interactive components." This coupled with Zeroheight's ability to sync with our Figma files, made authoring the design system quite simple; we never looked back at Sketch.

## Designer Deep Dives

![Designer Deep Dives](/uploads/ads-deep-dive.png)

Along with the deliverables mentioned, even more time was spent deliberating and discussing aspects of the system: components, color, typography, and accessibility to name a few. We established recurring meetings dedicated to single aspects of the system and documented our thoughts and agreed-upon decisions.

## Development
Having a shared library of code was by no means a simple challenge. With over a dozen products, each at various product lifecycle, and created by different teams via different technologies, it would seem that the project would grind to a halt. However, through discussion with development teams, it was decided that only new applications would try to adopt the system. Whenever opportunities would arise, changes to existing products would be made. We chose to write code in the [Ionic Framework](https://ionicframework.com/) enabling us to transpile our components into Angular, React, Web Components, or output to simple Javascript and CSS. 

## Process

![ADS Jira](/uploads/ads-jira.png)


Like any project, it was important that we work on the design system in an Agile way. We set up our Jira project into 4 main phases: Design, Development, Testing, and Documentation. As the development of a component worked its way through our process, we knew that the output would be high quality and meet usage and accessibility needs. As we leveraged the components in our product designs, we were able to gather product owner feedback and work any necessary changes back into specific components.  
# Today
Fast forward to today, we now have the following:
- Documentation website (via [Zeroheight](https://zeroheight.com/0965e942f/p/052cbb-aqua-design-system))
- BitBucket Library
- Jira + Figma integration
- Figma Library
- Adoption of the system in two products

# Moving Forward
As we continue to craft the Aqua Design System, our focus will be to expand its usage throughout our suite of products. We will support product teams to meet their needs and continue to be advocates for the system's long-term value.      