---
title: Known issues in Customer Insights - Journeys
description: Learn about known issues in Customer Insights - Journeys and how to work around them.
ms.date: 10/27/2023
ms.topic: article
author: alfergus
ms.author: alfergus
search.audienceType: 
  - admin
  - customizer
  - enduser
---

# Known issues in Customer Insights - Journeys

[!INCLUDE [consolidated-sku-rtm-only](./includes/consolidated-sku-rtm-only.md)]

As we continue to work on Customer Insights - Journeys and refine the experience, we've become aware of some outstanding issues for you to bear in mind. These issues are summarized in this article.

## Analytics

- In the aggregate cross-journey analytics dashboard, an extra step is needed to load the Power BI report in the Android and iPad native apps. To load the report, go to **Analytics**, then select a row, select the **Show as from** sub menu, then select **CC_Analytics_ReportingControl**.
- Data retention is 12 months for Contact and Lead insights, goal analytics, channel analytics (including delivery and interaction details such as contacts impacted by delivery and interaction issues), and AI optimization analytics.
- Some strings in the Power BI aggregate analytics dashboard aren’t localized.
- In the event of an email remote bounce, the contact/lead timeline might display two "email delivered" interactions for the same message with the same time stamp despite no message being delivered to the contact/lead email address. This is because the second interaction is intended to "erase" the first one. However, this isn't currently being handled in the timeline.
- When two contacts or leads are merged, only interactions of the primary contact or lead will be visible in contact/lead insights.
- There might be cases where unique values (for example, unique opens and clicks) in aggregated analytics dashboards have a slight deviation when compared to operational analytics. KPIs in aggregated analytics are calculated once per day to ensure the highest possible accuracy. Operational analytics, designed for near real-time analysis, operate on demand utilizing faster calculation methods for unique values, which may be slightly less precise.

## Consent

- Only one email address can be checked for consent for contacts.
- Only one physical address field is available for commercial emails.

## Customer journeys and orchestration

- The journey goal only counts unique profiles. Unique profiles are the number of unduplicated (counted only once) people that enter the journey. This means that in cases where the journey is a repeating journey, the total inflow won’t match the number of unique profiles with which the goal attainment is calculated.
- The journey goal met in analytics currently counts the number of unique profiles that met the goal divided by the total inflow. This will be fixed soon to count unique profiles that met the goal divided by total unique profiles.
- After a Customer Insights - Journeys journey is migrated, restored, or copied, its state is changed from **Live** to **Stopped**. To restart a migrated, restored, or copied journey, you need to first duplicate the journey, and then execute it.
- Customer journeys have a limitation of eight nested conditions.
- When a segment-based journey is stopped (by stopping it manually or when it reaches its end date), it stops the instances of the segments that it's using. When this takes longer than expected, the **Status Reason** will temporarily change to "Error" and only when the stopping has completed, it will go to status "Stopped" (normally within one or two hours after stopping).

## Dynamics 365 Customer Insights - Data

-	Segments and profiles in Customer Insights - Data aren’t evaluated in real time. Segments and profiles can be set to refresh on a schedule defined by the Customer Insights - Data admin. When a customer journey uses profiles from Customer Insights - Data, the earliest you can engage with a new customer is when their profile is created on the next scheduled refresh. Similarly, when you use segments from Customer Insights - Data, new customers will only enter the journey on the next scheduled refresh.
-	Once you start using Customer Insights - Data profiles in customer journeys, you can’t remove the profile attributes being used from the data unification process (Map-Match-Merge). Doing so might break customer journeys and personalization tokens that reference those attributes.
- Customer Insights - Data segments used in customer journeys can’t currently exceed 10 million profiles. A larger sized segment may get truncated to the first 10 million profiles only.

## Email editor

- Emails created in outbound marketing need to be recreated in the Customer Insights - Journeys email designer to be used in Customer Insights - Journeys.
- Content blocks may not be editable immediately after inserting into an email. When a content block is added to an email, its content may not be editable (can't be selected). To work around this issue, refresh the page.

## General

- The Customer Insights - Journeys app may still appear to be named "Marketing" in the app switcher screen and in the top menu bar, even if your installation is up to date. This will be updated in future revisions.

## Natural language

-	Natural language for journey conditions isn’t compatible with events or behavioral attributes.
    - "Customers that opened an email" isn’t a phrase we currently support.
-	The entity type of the journey follows the entity type the journey is bound to.
    - If the journey is contact-bound, the natural language will also require the term "contact."
    - If the journey is customer profile-bound, the natural language will also require the term "customer."

## Personalization

- Changing the data binding of existing dynamic text creates new dynamic text.
- Even if you delete all usage of a piece of dynamic text from the current message, it's still shown and considered in use.

## Triggers

- You can’t instrument C# apps in Customer Insights - Journeys. If you choose to use an alternate language like Python, you’ll have to manage an infra to run Python.
- Published triggers can’t be migrated when moving data between environments. Any published triggers in the old environment need to be re-created in the new environment. Draft triggers, however, can be migrated as described in [Move custom triggers between environments](move-triggers-between-environments.md).
- 
[!INCLUDE [footer-include](./includes/footer-banner.md)]
