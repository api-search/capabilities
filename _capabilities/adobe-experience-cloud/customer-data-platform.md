---
consumed_apis:
- experience-platform
description: Unified workflow for managing real-time customer profiles, audience segmentation, and data ingestion using Adobe Experience Platform. Designed for data engineers and customer data platform administrators.
layout: capability
name: Adobe Experience Cloud Customer Data Platform
operations:
- description: Get a unified customer profile.
  method: GET
  name: get-profile
  path: /v1/profiles
- description: List all datasets.
  method: GET
  name: list-datasets
  path: /v1/datasets
- description: List audience segments.
  method: GET
  name: list-segments
  path: /v1/segments
- description: Create a new audience segment.
  method: POST
  name: create-segment
  path: /v1/segments
personas: []
provider_name: Adobe Experience Cloud
provider_slug: adobe-experience-cloud
search_terms:
- CDP Administrator
- retrieve a unified real-time customer profile from adobe experience platform by identity.
- get profile
- create audience segment
- create a new audience segment.
- analytics
- Data Engineer
- list segments
- data management
- list all datasets.
- create a new audience segment using pql expression in adobe experience platform.
- personalization
- audience segmentation
- Marketing Technologist
- journey orchestration
- unified customer profiles and data management.
- Digital Marketer
- audience segments.
- analytics, a/b testing, and journey orchestration for digital marketers.
- customer data platform
- marketing professional using analytics, personalization, and journey tools.
- engineer managing data pipelines, schemas, and datasets in experience platform.
- data sets.
- real-time profiles
- unified customer profiles.
- list datasets
- create segment
- list all datasets ingested into adobe experience platform.
- technical marketer integrating experience cloud apis into marketing stack.
- a/b testing and content personalization.
- customer experience
- list audience segments.
- digital marketing
- campaign management
- get customer profile
- digital analytics reporting and audience insights.
- get a unified customer profile.
- adobe experience platform
- list audience segment definitions in adobe experience platform.
- administrator managing customer profiles, segments, and identity resolution.
- multi-channel customer journey management.
- profile management, audience segmentation, and data ingestion.
- list audience segments
slug: customer-data-platform
tags:
- Adobe Experience Platform
- Customer Data Platform
- Real-Time Profiles
- Data Management
- Audience Segmentation
tools:
- description: Retrieve a unified real-time customer profile from Adobe Experience Platform by identity.
  hints:
    openWorld: false
    readOnly: true
  name: get-customer-profile
- description: List all datasets ingested into Adobe Experience Platform.
  hints:
    openWorld: true
    readOnly: true
  name: list-datasets
- description: List audience segment definitions in Adobe Experience Platform.
  hints:
    openWorld: true
    readOnly: true
  name: list-audience-segments
- description: Create a new audience segment using PQL expression in Adobe Experience Platform.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-audience-segment
---
