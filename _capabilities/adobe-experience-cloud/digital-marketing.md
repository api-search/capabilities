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
- list analytics segments.
- analytics list metrics
- list targeting audiences in adobe target.
- campaign management
- run analytics report
- target audiences.
- list available metrics for an adobe analytics report suite.
- analytics, a/b testing, and journey orchestration for digital marketers.
- audience segment management.
- adobe experience cloud
- analytics list segments
- list customer journeys in adobe journey optimizer.
- ajo create offer
- a/b testing and content personalization.
- create a new personalized offer in adobe journey optimizer.
- unified customer profiles and data management.
- multi-channel customer journey management.
- ajo list journeys
- list target activities.
- Data Engineer
- run an adobe analytics report with dimensions, metrics, and segments.
- ajo list offers
- list audiences
- list campaign messages in adobe journey optimizer.
- list segments
- target list audiences
- digital analytics reporting and audience insights.
- technical marketer integrating experience cloud apis into marketing stack.
- marketing professional using analytics, personalization, and journey tools.
- run report
- list journey optimizer offers.
- list target audiences.
- digital marketing
- CDP Administrator
- personalized offers.
- target list offers
- target list activities
- customer experience
- list personalized offers in adobe journey optimizer.
- ajo list messages
- profile management, audience segmentation, and data ingestion.
- analytics report execution.
- list journeys
- list journey optimizer journeys.
- analytics
- a/b test and personalization activities.
- list activities
- Digital Marketer
- Marketing Technologist
- administrator managing customer profiles, segments, and identity resolution.
- list offers
- run an adobe analytics report.
- list a/b test and personalization activities in adobe target.
- engineer managing data pipelines, schemas, and datasets in experience platform.
- list content offers in adobe target.
- journey orchestration
- personalization
- customer journeys.
- list audience segments in adobe analytics.
slug: digital-marketing
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
