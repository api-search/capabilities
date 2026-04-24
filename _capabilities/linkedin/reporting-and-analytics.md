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
- get learning activity reports
- b2b advertising, audience targeting, and campaign analytics.
- tracks employee learning activity and completions.
- marketing
- retrieve ad analytics by various pivots.
- uses sales navigator for lead generation and crm sync.
- archives communications for regulatory compliance.
- retrieve learning activity reports aggregated by account, group, individual, or content.
- authentication, sharing, and verification for consumer apps.
- message archiving and regulatory communications governance.
- analytics
- professional networking
- recruiting
- learning
- careers
- business
- get ad analytics
- retrieve learning activity reports.
- job posting, recruiting, and applicant tracking.
- data portability and advertiser transparency for dma.
- sales intelligence, lead management, and crm integration.
- employee development tracking and content access.
- linkedin
- posts jobs and manages candidates through ats integrations.
- integrates linkedin authentication and sharing into applications.
- social media
- manages b2b ad campaigns and audience targeting on linkedin.
- reporting
- retrieve ad analytics by various pivots and dimensions.
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
