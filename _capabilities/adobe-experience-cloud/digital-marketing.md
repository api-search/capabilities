---
categories:
- analytics
consumed_apis: []
description: Unified workflow capability combining Adobe Analytics, Adobe Target, and Adobe Journey Optimizer for data-driven marketing campaigns, A/B testing, and personalized journey orchestration. Designed for digital marketers and marketing technologists.
layout: capability
name: Adobe Experience Cloud Digital Marketing
operations:
- description: Run an Adobe Analytics report.
  method: POST
  name: run-report
  path: /v1/reports
- description: List analytics segments.
  method: GET
  name: list-segments
  path: /v1/segments
- description: List Target activities.
  method: GET
  name: list-activities
  path: /v1/activities
- description: List Target audiences.
  method: GET
  name: list-audiences
  path: /v1/audiences
- description: List Journey Optimizer journeys.
  method: GET
  name: list-journeys
  path: /v1/journeys
- description: List Journey Optimizer offers.
  method: GET
  name: list-offers
  path: /v1/offers
personas: []
provider_name: Adobe Experience Cloud
provider_slug: adobe-experience-cloud
search_terms:
- list offers
- CDP Administrator
- target list activities
- ajo create offer
- digital marketing
- list customer journeys in adobe journey optimizer.
- engineer managing data pipelines, schemas, and datasets in experience platform.
- analytics
- list analytics segments.
- run an adobe analytics report.
- list available metrics for an adobe analytics report suite.
- adobe experience cloud
- personalized offers.
- list segments
- target list audiences
- list personalized offers in adobe journey optimizer.
- analytics, a/b testing, and journey orchestration for digital marketers.
- run an adobe analytics report with dimensions, metrics, and segments.
- Data Engineer
- administrator managing customer profiles, segments, and identity resolution.
- run report
- profile management, audience segmentation, and data ingestion.
- target audiences.
- list journey optimizer offers.
- ajo list offers
- list a/b test and personalization activities in adobe target.
- ajo list journeys
- list audiences
- ajo list messages
- list journey optimizer journeys.
- list content offers in adobe target.
- analytics list segments
- marketing professional using analytics, personalization, and journey tools.
- a/b testing and content personalization.
- unified customer profiles and data management.
- list target audiences.
- Digital Marketer
- technical marketer integrating experience cloud apis into marketing stack.
- list journeys
- customer journeys.
- list targeting audiences in adobe target.
- a/b test and personalization activities.
- analytics list metrics
- list campaign messages in adobe journey optimizer.
- Marketing Technologist
- run analytics report
- list audience segments in adobe analytics.
- journey orchestration
- analytics report execution.
- list activities
- audience segment management.
- create a new personalized offer in adobe journey optimizer.
- digital analytics reporting and audience insights.
- campaign management
- customer experience
- multi-channel customer journey management.
- list target activities.
- personalization
- target list offers
slug: digital-marketing
source_filename: digital-marketing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Experience Cloud Digital Marketing\n  description: Unified workflow capability combining Adobe Analytics, Adobe Target, and Adobe Journey Optimizer for data-driven\n    marketing campaigns, A/B testing, and personalized journey orchestration. Designed for digital marketers and marketing\n    technologists.\n  tags:\n  - Adobe Experience Cloud\n  - Digital Marketing\n  - Analytics\n  - Personalization\n  - Journey Orchestration\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ADOBE_ANALYTICS_ACCESS_TOKEN: ADOBE_ANALYTICS_ACCESS_TOKEN\n    ADOBE_TARGET_ACCESS_TOKEN: ADOBE_TARGET_ACCESS_TOKEN\n    ADOBE_AJO_ACCESS_TOKEN: ADOBE_AJO_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: analytics-api\n    baseUri: https://analytics.adobe.io/api/{companyId}\n    description: Adobe Analytics 2.0 REST API for reports and management.\n    authentication:\n      type: bearer\n     \
  \ token: '{{ADOBE_ANALYTICS_ACCESS_TOKEN}}'\n    resources:\n    - name: reports\n      path: /reports\n      description: Run and retrieve analytics reports.\n      operations:\n      - name: run-report\n        method: POST\n        description: Run an analytics report with dimensions, metrics, and date ranges.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rsid: '{{tools.rsid}}'\n            globalFilters: []\n            metricContainer: {}\n    - name: segments\n      path: /segments\n      description: Manage audience segments.\n      operations:\n      - name: list-segments\n        method: GET\n        description: List all segments in the account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-segment\n        method: POST\n       \
  \ description: Create a new segment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            rsid: '{{tools.rsid}}'\n    - name: metrics\n      path: /metrics\n      description: Retrieve available metrics for a report suite.\n      operations:\n      - name: list-metrics\n        method: GET\n        description: List all metrics for a report suite.\n        inputParameters:\n        - name: rsid\n          in: query\n          type: string\n          required: true\n          description: Report Suite ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dimensions\n      path: /dimensions\n      description: Retrieve available dimensions for a report suite.\n      operations:\n      - name: list-dimensions\n        method:\
  \ GET\n        description: List all dimensions for a report suite.\n        inputParameters:\n        - name: rsid\n          in: query\n          type: string\n          required: true\n          description: Report Suite ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: target-api\n    baseUri: https://mc.adobe.io/{tenant}/target\n    description: Adobe Target REST API for personalization and testing.\n    authentication:\n      type: bearer\n      token: '{{ADOBE_TARGET_ACCESS_TOKEN}}'\n    resources:\n    - name: activities\n      path: /activities\n      description: Manage A/B tests and personalization activities.\n      operations:\n      - name: list-activities\n        method: GET\n        description: List all activities.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-ab-activity\n\
  \        method: POST\n        description: Create a new A/B test activity.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: ab\n    - name: audiences\n      path: /audiences\n      description: Manage target audiences.\n      operations:\n      - name: list-audiences\n        method: GET\n        description: List all audiences.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: offers\n      path: /offers/content\n      description: Manage content offers.\n      operations:\n      - name: list-offers\n        method: GET\n        description: List all content offers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n   \
  \ namespace: journey-optimizer\n    baseUri: https://platform.adobe.io\n    description: Adobe Journey Optimizer API for journey and campaign management.\n    authentication:\n      type: bearer\n      token: '{{ADOBE_AJO_ACCESS_TOKEN}}'\n    resources:\n    - name: journeys\n      path: /journey/journeyVersions\n      description: Manage customer journeys.\n      operations:\n      - name: list-journeys\n        method: GET\n        description: List all journey versions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages\n      path: /ajo/message\n      description: Manage campaign messages.\n      operations:\n      - name: list-messages\n        method: GET\n        description: List all messages.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: offers\n      path: /offer_library/offers\n      description:\
  \ Manage personalized offers.\n      operations:\n      - name: list-offers\n        method: GET\n        description: List all offers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-offer\n        method: POST\n        description: Create a personalized offer.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            status: draft\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: digital-marketing-api\n    description: Unified REST API for Adobe Experience Cloud digital marketing — analytics, personalization, journeys, and\n      offers.\n    resources:\n    - path: /v1/reports\n      name: reports\n      description: Analytics report execution.\n      operations:\n      - method: POST\n        name: run-report\n\
  \        description: Run an Adobe Analytics report.\n        call: analytics-api.run-report\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/segments\n      name: segments\n      description: Audience segment management.\n      operations:\n      - method: GET\n        name: list-segments\n        description: List analytics segments.\n        call: analytics-api.list-segments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/activities\n      name: activities\n      description: A/B test and personalization activities.\n      operations:\n      - method: GET\n        name: list-activities\n        description: List Target activities.\n        call: target-api.list-activities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audiences\n      name: audiences\n      description: Target audiences.\n      operations:\n      - method: GET\n        name: list-audiences\n\
  \        description: List Target audiences.\n        call: target-api.list-audiences\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/journeys\n      name: journeys\n      description: Customer journeys.\n      operations:\n      - method: GET\n        name: list-journeys\n        description: List Journey Optimizer journeys.\n        call: journey-optimizer.list-journeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/offers\n      name: offers\n      description: Personalized offers.\n      operations:\n      - method: GET\n        name: list-offers\n        description: List Journey Optimizer offers.\n        call: journey-optimizer.list-offers\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: digital-marketing-mcp\n    transport: http\n    description: MCP server for AI-assisted digital marketing — analyze campaigns, test personalization,\
  \ orchestrate journeys,\n      and manage offers.\n    tools:\n    - name: run-analytics-report\n      description: Run an Adobe Analytics report with dimensions, metrics, and segments.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: analytics-api.run-report\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: analytics-list-segments\n      description: List audience segments in Adobe Analytics.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: analytics-api.list-segments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: analytics-list-metrics\n      description: List available metrics for an Adobe Analytics report suite.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: analytics-api.list-metrics\n      with:\n        rsid: tools.rsid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: target-list-activities\n      description:\
  \ List A/B test and personalization activities in Adobe Target.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: target-api.list-activities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: target-list-audiences\n      description: List targeting audiences in Adobe Target.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: target-api.list-audiences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: target-list-offers\n      description: List content offers in Adobe Target.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: target-api.list-offers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ajo-list-journeys\n      description: List customer journeys in Adobe Journey Optimizer.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: journey-optimizer.list-journeys\n      outputParameters:\n     \
  \ - type: object\n        mapping: $.\n    - name: ajo-list-offers\n      description: List personalized offers in Adobe Journey Optimizer.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: journey-optimizer.list-offers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ajo-create-offer\n      description: Create a new personalized offer in Adobe Journey Optimizer.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: journey-optimizer.create-offer\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ajo-list-messages\n      description: List campaign messages in Adobe Journey Optimizer.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: journey-optimizer.list-messages\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-experience-cloud/refs/heads/main/capabilities/digital-marketing.yaml
tags:
- Adobe Experience Cloud
- Digital Marketing
- Analytics
- Personalization
- Journey Orchestration
tools:
- description: Run an Adobe Analytics report with dimensions, metrics, and segments.
  hints:
    openWorld: true
    readOnly: true
  name: run-analytics-report
- description: List audience segments in Adobe Analytics.
  hints:
    openWorld: true
    readOnly: true
  name: analytics-list-segments
- description: List available metrics for an Adobe Analytics report suite.
  hints:
    openWorld: true
    readOnly: true
  name: analytics-list-metrics
- description: List A/B test and personalization activities in Adobe Target.
  hints:
    openWorld: true
    readOnly: true
  name: target-list-activities
- description: List targeting audiences in Adobe Target.
  hints:
    openWorld: true
    readOnly: true
  name: target-list-audiences
- description: List content offers in Adobe Target.
  hints:
    openWorld: true
    readOnly: true
  name: target-list-offers
- description: List customer journeys in Adobe Journey Optimizer.
  hints:
    openWorld: true
    readOnly: true
  name: ajo-list-journeys
- description: List personalized offers in Adobe Journey Optimizer.
  hints:
    openWorld: true
    readOnly: true
  name: ajo-list-offers
- description: Create a new personalized offer in Adobe Journey Optimizer.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: ajo-create-offer
- description: List campaign messages in Adobe Journey Optimizer.
  hints:
    openWorld: true
    readOnly: true
  name: ajo-list-messages
---
