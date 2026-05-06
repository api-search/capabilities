---
categories:
- analytics
consumed_apis: []
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
- retrieve ad analytics by various pivots and dimensions.
- get ad analytics
- tracks employee learning activity and completions.
- recruiting
- reporting
- analytics
- authentication, sharing, and verification for consumer apps.
- careers
- linkedin
- marketing
- professional networking
- retrieve learning activity reports aggregated by account, group, individual, or content.
- data portability and advertiser transparency for dma.
- business
- employee development tracking and content access.
- sales intelligence, lead management, and crm integration.
- message archiving and regulatory communications governance.
- retrieve learning activity reports.
- b2b advertising, audience targeting, and campaign analytics.
- manages b2b ad campaigns and audience targeting on linkedin.
- get learning activity reports
- posts jobs and manages candidates through ats integrations.
- retrieve ad analytics by various pivots.
- job posting, recruiting, and applicant tracking.
- social media
- uses sales navigator for lead generation and crm sync.
- integrates linkedin authentication and sharing into applications.
- learning
- archives communications for regulatory compliance.
slug: reporting-and-analytics
source_filename: reporting-and-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: LinkedIn Reporting And Analytics\n  description: Unified workflow for marketing analysts to access ad analytics, B2B metrics, learning activity reports, and\n    performance data -- combining reporting/ROI and learning activity APIs.\n  tags:\n  - LinkedIn\n  - Reporting\n  - Analytics\n  - Learning\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    LINKEDIN_OAUTH_TOKEN: LINKEDIN_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: marketing-reporting-roi\n    baseUri: https://api.linkedin.com\n    description: LinkedIn Reporting and ROI API.\n    authentication:\n      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n    resources:\n    - name: ad-analytics\n      path: /adAnalytics\n      description: Ad analytics and performance reporting.\n      operations:\n      - name: get-ad-analytics\n        method: GET\n        description: Retrieve ad analytics by various pivots\
  \ and dimensions.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query type (analytics or statistics)\n        - name: pivot\n          in: query\n          type: string\n          required: false\n          description: Pivot dimension\n        - name: dateRange\n          in: query\n          type: string\n          required: false\n          description: Date range\n        - name: timeGranularity\n          in: query\n          type: string\n          required: false\n          description: Time granularity\n        - name: accounts\n          in: query\n          type: string\n          required: false\n          description: Account URNs\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n  - type: http\n    namespace: learning-activity-reports\n    baseUri: https://api.linkedin.com\n    description: LinkedIn Learning Activity Reports API.\n    authentication:\n      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n    resources:\n    - name: learning-activity-reports\n      path: /v2/learningActivityReports\n      description: Learning activity reports including completions, views, and logins.\n      operations:\n      - name: get-learning-activity-reports\n        method: GET\n        description: Retrieve learning activity reports aggregated by account, group, individual, or content.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: startedAt\n          in: query\n          type: integer\n          required: true\n          description: Start timestamp in milliseconds since epoch\n        - name: timeOffset.unit\n          in: query\n\
  \          type: string\n          required: true\n          description: Time offset unit (DAY, WEEK, MONTH)\n        - name: timeOffset.duration\n          in: query\n          type: integer\n          required: true\n          description: Time offset duration\n        - name: aggregationCriteria.primary\n          in: query\n          type: string\n          required: true\n          description: Primary aggregation criteria (ACCOUNT, GROUP, INDIVIDUAL, CONTENT)\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return\n        - name: start\n          in: query\n          type: integer\n          required: false\n          description: Starting index for pagination\n        - name: contentSource\n          in: query\n          type: string\n          required: false\n          description: Source of learning content\n        - name: referer\n          in: header\n          type: string\n    \
  \      required: false\n          description: Referrer URN for the request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: reporting-analytics-api\n    description: Unified REST API for LinkedIn reporting and analytics.\n    resources:\n    - path: /v1/ad-analytics\n      name: ad-analytics\n      operations:\n      - method: GET\n        name: get-ad-analytics\n        description: Retrieve ad analytics by various pivots.\n        call: marketing-reporting-roi.get-ad-analytics\n    - path: /v1/learning-activity-reports\n      name: learning-activity-reports\n      operations:\n      - method: GET\n        name: get-learning-activity-reports\n        description: Retrieve learning activity reports.\n        call: learning-activity-reports.get-learning-activity-reports\n  - type: mcp\n    port: 9093\n    namespace: reporting-analytics-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted LinkedIn reporting and analytics.\n    tools:\n    - name: get-ad-analytics\n      description: Retrieve ad analytics by various pivots and dimensions.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-reporting-roi.get-ad-analytics\n    - name: get-learning-activity-reports\n      description: Retrieve learning activity reports aggregated by account, group, individual, or content.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: learning-activity-reports.get-learning-activity-reports\n"
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
