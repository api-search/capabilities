---
categories:
- analytics
consumed_apis:
- analytics-api
- target-api
- journey-optimizer
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
- analytics
- run an adobe analytics report with dimensions, metrics, and segments.
- digital marketing
- list personalized offers in adobe journey optimizer.
- target audiences.
- adobe experience cloud
- list journey optimizer journeys.
- analytics list metrics
- list journeys
- campaign management
- list targeting audiences in adobe target.
- ajo list journeys
- run analytics report
- administrator managing customer profiles, segments, and identity resolution.
- list target activities.
- audience segment management.
- digital analytics reporting and audience insights.
- analytics report execution.
- run report
- list target audiences.
- list activities
- list audience segments in adobe analytics.
- target list offers
- a/b testing and content personalization.
- target list activities
- list offers
- list available metrics for an adobe analytics report suite.
- list content offers in adobe target.
- technical marketer integrating experience cloud apis into marketing stack.
- engineer managing data pipelines, schemas, and datasets in experience platform.
- multi-channel customer journey management.
- customer experience
- analytics, a/b testing, and journey orchestration for digital marketers.
- run an adobe analytics report.
- CDP Administrator
- personalization
- list segments
- ajo create offer
- Marketing Technologist
- profile management, audience segmentation, and data ingestion.
- marketing professional using analytics, personalization, and journey tools.
- Digital Marketer
- list campaign messages in adobe journey optimizer.
- list journey optimizer offers.
- list customer journeys in adobe journey optimizer.
- a/b test and personalization activities.
- customer journeys.
- ajo list offers
- Data Engineer
- ajo list messages
- analytics list segments
- unified customer profiles and data management.
- journey orchestration
- list audiences
- target list audiences
- create a new personalized offer in adobe journey optimizer.
- personalized offers.
- list a/b test and personalization activities in adobe target.
- list analytics segments.
slug: digital-marketing
source_filename: digital-marketing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Adobe Experience Cloud Digital Marketing\"\n  description: \"Unified workflow capability combining Adobe Analytics, Adobe Target, and Adobe Journey Optimizer for data-driven marketing campaigns, A/B testing, and personalized journey orchestration. Designed for digital marketers and marketing technologists.\"\n  tags:\n    - Adobe Experience Cloud\n    - Digital Marketing\n    - Analytics\n    - Personalization\n    - Journey Orchestration\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ADOBE_ANALYTICS_ACCESS_TOKEN: ADOBE_ANALYTICS_ACCESS_TOKEN\n      ADOBE_TARGET_ACCESS_TOKEN: ADOBE_TARGET_ACCESS_TOKEN\n      ADOBE_AJO_ACCESS_TOKEN: ADOBE_AJO_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: analytics-api\n      location: ./shared/analytics-api.yaml\n    - import: target-api\n      location: ./shared/target-api.yaml\n    - import: journey-optimizer\n      location: ./shared/journey-optimizer-api.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: digital-marketing-api\n      description: \"Unified REST API for Adobe Experience Cloud digital marketing — analytics, personalization, journeys, and offers.\"\n      resources:\n        - path: /v1/reports\n          name: reports\n          description: \"Analytics report execution.\"\n          operations:\n            - method: POST\n              name: run-report\n              description: \"Run an Adobe Analytics report.\"\n              call: \"analytics-api.run-report\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/segments\n          name: segments\n          description: \"Audience segment management.\"\n          operations:\n            - method: GET\n              name: list-segments\n              description: \"List analytics segments.\"\n              call: \"analytics-api.list-segments\"\n              outputParameters:\n      \
  \          - type: object\n                  mapping: \"$.\"\n        - path: /v1/activities\n          name: activities\n          description: \"A/B test and personalization activities.\"\n          operations:\n            - method: GET\n              name: list-activities\n              description: \"List Target activities.\"\n              call: \"target-api.list-activities\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/audiences\n          name: audiences\n          description: \"Target audiences.\"\n          operations:\n            - method: GET\n              name: list-audiences\n              description: \"List Target audiences.\"\n              call: \"target-api.list-audiences\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/journeys\n          name: journeys\n          description: \"Customer journeys.\"\n          operations:\n\
  \            - method: GET\n              name: list-journeys\n              description: \"List Journey Optimizer journeys.\"\n              call: \"journey-optimizer.list-journeys\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/offers\n          name: offers\n          description: \"Personalized offers.\"\n          operations:\n            - method: GET\n              name: list-offers\n              description: \"List Journey Optimizer offers.\"\n              call: \"journey-optimizer.list-offers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: digital-marketing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted digital marketing — analyze campaigns, test personalization, orchestrate journeys, and manage offers.\"\n      tools:\n        - name: run-analytics-report\n       \
  \   description: \"Run an Adobe Analytics report with dimensions, metrics, and segments.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"analytics-api.run-report\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: analytics-list-segments\n          description: \"List audience segments in Adobe Analytics.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"analytics-api.list-segments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: analytics-list-metrics\n          description: \"List available metrics for an Adobe Analytics report suite.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"analytics-api.list-metrics\"\n          with:\n            rsid: \"tools.rsid\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: target-list-activities\n          description: \"List A/B test and personalization activities in Adobe Target.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"target-api.list-activities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: target-list-audiences\n          description: \"List targeting audiences in Adobe Target.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"target-api.list-audiences\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: target-list-offers\n          description: \"List content offers in Adobe Target.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"target-api.list-offers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ajo-list-journeys\n\
  \          description: \"List customer journeys in Adobe Journey Optimizer.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"journey-optimizer.list-journeys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ajo-list-offers\n          description: \"List personalized offers in Adobe Journey Optimizer.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"journey-optimizer.list-offers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ajo-create-offer\n          description: \"Create a new personalized offer in Adobe Journey Optimizer.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"journey-optimizer.create-offer\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n           \
  \ - type: object\n              mapping: \"$.\"\n        - name: ajo-list-messages\n          description: \"List campaign messages in Adobe Journey Optimizer.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"journey-optimizer.list-messages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
