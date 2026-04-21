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
- analyzes data and manages cohorts
- manage and evaluate a/b experiments and feature flags. for product managers.
- uploadEvents
- unified workflow for sending events and identifying users. for data engineers.
- amplitude send attribution data
- http v2 api uploadEvents
- product analytics
- sendAttribution
- identify api identifyUser
- runs experiments and feature flags
- identity management
- analytics
- identifyUser
- event ingestion
- amplitude
- manages privacy and compliance
- scim provisioning and privacy compliance. for it admins and compliance teams.
- export raw event data and manage behavioral cohorts. for data analysts.
- privacy compliance
- feature flags
- data governance
- a/b testing
- attribution api sendAttribution
- ingests and exports event data
- experimentation
- manage event schemas and chart annotations. for data governance teams.
- amplitude upload events
- user behavior
- amplitude identify a user
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
