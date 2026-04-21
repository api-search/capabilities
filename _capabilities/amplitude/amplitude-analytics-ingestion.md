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
- event ingestion
- identity management
- amplitude
- manages privacy and compliance
- data governance
- amplitude send attribution data
- export raw event data and manage behavioral cohorts. for data analysts.
- experimentation
- privacy compliance
- amplitude identify a user
- feature flags
- amplitude upload events
- manage and evaluate a/b experiments and feature flags. for product managers.
- product analytics
- identify api identifyUser
- ingests and exports event data
- runs experiments and feature flags
- http v2 api uploadEvents
- sendAttribution
- analyzes data and manages cohorts
- a/b testing
- user behavior
- scim provisioning and privacy compliance. for it admins and compliance teams.
- identifyUser
- attribution api sendAttribution
- manage event schemas and chart annotations. for data governance teams.
- analytics
- unified workflow for sending events and identifying users. for data engineers.
- uploadEvents
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
