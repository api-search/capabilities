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
- scim provisioning and privacy compliance. for it admins and compliance teams.
- attribution api sendAttribution
- sendAttribution
- manage event schemas and chart annotations. for data governance teams.
- data governance
- experimentation
- analytics
- export raw event data and manage behavioral cohorts. for data analysts.
- ingests and exports event data
- amplitude send attribution data
- unified workflow for sending events and identifying users. for data engineers.
- analyzes data and manages cohorts
- user behavior
- uploadEvents
- amplitude upload events
- identity management
- privacy compliance
- a/b testing
- manages privacy and compliance
- runs experiments and feature flags
- amplitude
- amplitude identify a user
- http v2 api uploadEvents
- identifyUser
- event ingestion
- product analytics
- identify api identifyUser
- feature flags
- manage and evaluate a/b experiments and feature flags. for product managers.
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
