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
- message archiving and regulatory communications governance.
- analytics
- social media
- b2b advertising, audience targeting, and campaign analytics.
- learning
- professional networking
- manages b2b ad campaigns and audience targeting on linkedin.
- authentication, sharing, and verification for consumer apps.
- integrates linkedin authentication and sharing into applications.
- retrieve learning activity reports aggregated by account, group, individual, or content.
- retrieve ad analytics by various pivots.
- business
- careers
- job posting, recruiting, and applicant tracking.
- posts jobs and manages candidates through ats integrations.
- reporting
- uses sales navigator for lead generation and crm sync.
- data portability and advertiser transparency for dma.
- marketing
- archives communications for regulatory compliance.
- tracks employee learning activity and completions.
- get learning activity reports
- sales intelligence, lead management, and crm integration.
- get ad analytics
- linkedin
- retrieve learning activity reports.
- retrieve ad analytics by various pivots and dimensions.
- employee development tracking and content access.
- recruiting
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
