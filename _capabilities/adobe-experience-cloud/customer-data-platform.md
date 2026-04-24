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
- Marketing Technologist
- customer experience
- data management
- digital marketing
- analytics, a/b testing, and journey orchestration for digital marketers.
- audience segments.
- list audience segment definitions in adobe experience platform.
- adobe experience platform
- data sets.
- list audience segments.
- create segment
- list all datasets ingested into adobe experience platform.
- marketing professional using analytics, personalization, and journey tools.
- unified customer profiles and data management.
- digital analytics reporting and audience insights.
- analytics
- real-time profiles
- audience segmentation
- technical marketer integrating experience cloud apis into marketing stack.
- create a new audience segment using pql expression in adobe experience platform.
- retrieve a unified real-time customer profile from adobe experience platform by identity.
- list audience segments
- administrator managing customer profiles, segments, and identity resolution.
- create audience segment
- Digital Marketer
- engineer managing data pipelines, schemas, and datasets in experience platform.
- get customer profile
- list all datasets.
- CDP Administrator
- Data Engineer
- list segments
- customer data platform
- journey orchestration
- get a unified customer profile.
- campaign management
- unified customer profiles.
- a/b testing and content personalization.
- profile management, audience segmentation, and data ingestion.
- multi-channel customer journey management.
- create a new audience segment.
- list datasets
- get profile
- personalization
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
