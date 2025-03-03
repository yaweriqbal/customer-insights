---
title: Email policies and suspension standards
description: Learn about Dynamics 365 Customer Insights - Journeys email policies and what to do if your account is suspended.
ms.date: 09/08/2023
ms.topic: article
author: alfergus
ms.author: alfergus
search.audienceType: 
  - admin
  - customizer
  - enduser
---

# Email policies and suspension standards

[!INCLUDE [consolidated-sku-rtm-only](./includes/consolidated-sku-rtm-only.md)]

To preserve your reputation as a sender, Dynamics 365 Customer Insights - Journeys has developed a deliverability protection system that detects excessive hard bounces, spam reports, block listing, or abuse complaints. This system protects our entire customer base. If email criteria are violated, accounts can be placed under review or terminated. 

## Stages of review

- *Warned*

    In the first stage of review, the Customer Insights - Journeys application sends a warning notification to the admin email address associated with your account. The account maintains full sending functionality during the warning period. However, if the application doesn't receive a response or the protection system records successive alerts, your account may be suspended to prevent further risk to your sending reputation.

- *Suspended*

    Email sending is suspended when the deliverability protection system detects that one or multiple email limits were breached on your email recipients, or fraudulent account activity was detected.

    When email sending is suspended, you see a warning banner in your email tool about a problem detected by the deliverability protection system. The banner contains details about the problem and recommendations to improve future email messages.

    If your email sending is suspended, create a ticket with our [Email Deliverability team](mailto:dynmktdeliverability@microsoft.com). When we believe that you have taken sufficient steps to address the cause of suspension, we will reinstate your account.

## What are the email limits for Dynamics 365 Customer Insights - Journeys?

- *Hard bounces*: The hard bounce limit is for Customer Insights - Journeys 8%. The preferred bounce rate is less than 2%.

- *Spam reports*: The spam complaint rate limit for Customer Insights - Journeys is 0.3% (1 in 1,000 messages sent).

- *Direct complaints*: Direct complaints are sent to the Dynamics 365 abuse desk and are reviewed on a case by case basis.

## Other reasons that can cause account suspensions

- A violation of our messaging policy.
- A violation of our terms of use.
- Content that is abusive or harmful.

[!INCLUDE [footer-include](./includes/footer-banner.md)]
