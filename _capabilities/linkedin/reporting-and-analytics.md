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
- analytics
- sales intelligence, lead management, and crm integration.
- archives communications for regulatory compliance.
- marketing
- business
- social media
- recruiting
- careers
- employee development tracking and content access.
- posts jobs and manages candidates through ats integrations.
- tracks employee learning activity and completions.
- data portability and advertiser transparency for dma.
- linkedin
- uses sales navigator for lead generation and crm sync.
- message archiving and regulatory communications governance.
- manages b2b ad campaigns and audience targeting on linkedin.
- authentication, sharing, and verification for consumer apps.
- retrieve learning activity reports.
- reporting
- learning
- integrates linkedin authentication and sharing into applications.
- b2b advertising, audience targeting, and campaign analytics.
- get ad analytics
- retrieve ad analytics by various pivots.
- get learning activity reports
- job posting, recruiting, and applicant tracking.
- professional networking
- retrieve ad analytics by various pivots and dimensions.
- retrieve learning activity reports aggregated by account, group, individual, or content.
slug: reporting-and-analytics
source_filename: reporting-and-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"LinkedIn Reporting And Analytics\"\n  description: \"Unified workflow for marketing analysts to access ad analytics, B2B metrics, learning activity reports, and performance data -- combining reporting/ROI and learning activity APIs.\"\n  tags:\n    - LinkedIn\n    - Reporting\n    - Analytics\n    - Learning\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      LINKEDIN_OAUTH_TOKEN: LINKEDIN_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: marketing-reporting-roi\n      location: ./shared/marketing-reporting-roi.yaml\n    - import: learning-activity-reports\n      location: ./shared/learning-activity-reports.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: reporting-analytics-api\n      description: \"Unified REST API for LinkedIn reporting and analytics.\"\n      resources:\n        - path: /v1/ad-analytics\n          name: ad-analytics\n          operations:\n\
  \            - method: GET\n              name: get-ad-analytics\n              description: \"Retrieve ad analytics by various pivots.\"\n              call: \"marketing-reporting-roi.get-ad-analytics\"\n        - path: /v1/learning-activity-reports\n          name: learning-activity-reports\n          operations:\n            - method: GET\n              name: get-learning-activity-reports\n              description: \"Retrieve learning activity reports.\"\n              call: \"learning-activity-reports.get-learning-activity-reports\"\n\n    - type: mcp\n      port: 9093\n      namespace: reporting-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted LinkedIn reporting and analytics.\"\n      tools:\n        - name: get-ad-analytics\n          description: \"Retrieve ad analytics by various pivots and dimensions.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-reporting-roi.get-ad-analytics\"\n\
  \        - name: get-learning-activity-reports\n          description: \"Retrieve learning activity reports aggregated by account, group, individual, or content.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"learning-activity-reports.get-learning-activity-reports\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/linkedin/refs/heads/main/capabilities/reporting-and-analytics.yaml
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
