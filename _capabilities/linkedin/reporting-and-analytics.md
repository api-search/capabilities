---
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
- sales intelligence, lead management, and crm integration.
- data portability and advertiser transparency for dma.
- learning
- archives communications for regulatory compliance.
- get learning activity reports
- retrieve learning activity reports.
- retrieve ad analytics by various pivots and dimensions.
- authentication, sharing, and verification for consumer apps.
- job posting, recruiting, and applicant tracking.
- reporting
- retrieve learning activity reports aggregated by account, group, individual, or content.
- b2b advertising, audience targeting, and campaign analytics.
- get ad analytics
- integrates linkedin authentication and sharing into applications.
- marketing
- business
- linkedin
- uses sales navigator for lead generation and crm sync.
- careers
- employee development tracking and content access.
- professional networking
- tracks employee learning activity and completions.
- retrieve ad analytics by various pivots.
- analytics
- message archiving and regulatory communications governance.
- posts jobs and manages candidates through ats integrations.
- recruiting
- social media
- manages b2b ad campaigns and audience targeting on linkedin.
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
