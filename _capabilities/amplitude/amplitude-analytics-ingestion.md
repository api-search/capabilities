---
consumed_apis:
- attribution-api
- http-v2-api
- identify-api
description: Unified workflow for sending events and identifying users. For data engineers.
layout: capability
name: Amplitude Analytics Ingestion
operations:
- description: Amplitude Send Attribution Data
  method: POST
  name: sendAttribution
  path: /v1/attribution
- description: Amplitude Upload Events
  method: POST
  name: uploadEvents
  path: /v1/events
- description: Amplitude Identify a User
  method: POST
  name: identifyUser
  path: /v1/identify
personas: []
provider_name: Amplitude
provider_slug: amplitude
search_terms:
- runs experiments and feature flags
- uploadEvents
- privacy compliance
- amplitude identify a user
- experimentation
- analytics
- manage event schemas and chart annotations. for data governance teams.
- identify api identifyUser
- data governance
- export raw event data and manage behavioral cohorts. for data analysts.
- feature flags
- manages privacy and compliance
- user behavior
- identity management
- sendAttribution
- http v2 api uploadEvents
- product analytics
- amplitude upload events
- identifyUser
- amplitude
- unified workflow for sending events and identifying users. for data engineers.
- ingests and exports event data
- event ingestion
- attribution api sendAttribution
- scim provisioning and privacy compliance. for it admins and compliance teams.
- a/b testing
- manage and evaluate a/b experiments and feature flags. for product managers.
- analyzes data and manages cohorts
- amplitude send attribution data
slug: amplitude-analytics-ingestion
tags:
- Amplitude
- Analytics
- Event Ingestion
tools:
- description: Amplitude Send Attribution Data
  hints:
    readOnly: false
  name: attribution-api-sendAttribution
- description: Amplitude Upload Events
  hints:
    readOnly: false
  name: http-v2-api-uploadEvents
- description: Amplitude Identify a User
  hints:
    readOnly: false
  name: identify-api-identifyUser
---
