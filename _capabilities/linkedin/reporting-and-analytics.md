---
categories:
- analytics
consumed_apis:
- marketing-reporting-roi
- learning-activity-reports
description: Unified workflow for marketing analysts to access ad analytics, B2B metrics, learning activity reports, and performance data -- combining reporting/ROI and learning activity APIs.
layout: capability
name: LinkedIn Reporting And Analytics
operations:
- description: Retrieve ad analytics by various pivots.
  method: GET
  name: get-ad-analytics
  path: /v1/ad-analytics
- description: Retrieve learning activity reports.
  method: GET
  name: get-learning-activity-reports
  path: /v1/learning-activity-reports
personas: []
provider_name: LinkedIn
provider_slug: linkedin
search_terms:
- recruiting
- job posting, recruiting, and applicant tracking.
- employee development tracking and content access.
- sales intelligence, lead management, and crm integration.
- careers
- reporting
- get learning activity reports
- marketing
- business
- retrieve learning activity reports aggregated by account, group, individual, or content.
- data portability and advertiser transparency for dma.
- manages b2b ad campaigns and audience targeting on linkedin.
- message archiving and regulatory communications governance.
- learning
- uses sales navigator for lead generation and crm sync.
- retrieve ad analytics by various pivots and dimensions.
- get ad analytics
- professional networking
- tracks employee learning activity and completions.
- integrates linkedin authentication and sharing into applications.
- posts jobs and manages candidates through ats integrations.
- retrieve ad analytics by various pivots.
- analytics
- authentication, sharing, and verification for consumer apps.
- archives communications for regulatory compliance.
- b2b advertising, audience targeting, and campaign analytics.
- social media
- linkedin
- retrieve learning activity reports.
slug: reporting-and-analytics
tags:
- LinkedIn
- Reporting
- Analytics
- Learning
tools:
- description: Retrieve ad analytics by various pivots and dimensions.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-ad-analytics
- description: Retrieve learning activity reports aggregated by account, group, individual, or content.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-learning-activity-reports
---
