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
- uploadEvents
- http v2 api uploadEvents
- manage event schemas and chart annotations. for data governance teams.
- a/b testing
- amplitude send attribution data
- identifyUser
- privacy compliance
- manage and evaluate a/b experiments and feature flags. for product managers.
- feature flags
- export raw event data and manage behavioral cohorts. for data analysts.
- unified workflow for sending events and identifying users. for data engineers.
- user behavior
- ingests and exports event data
- amplitude upload events
- identify api identifyUser
- analyzes data and manages cohorts
- data governance
- product analytics
- amplitude
- experimentation
- runs experiments and feature flags
- analytics
- identity management
- event ingestion
- amplitude identify a user
- attribution api sendAttribution
- sendAttribution
- scim provisioning and privacy compliance. for it admins and compliance teams.
- manages privacy and compliance
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
