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
- experimentation
- analytics
- analyzes data and manages cohorts
- data governance
- amplitude identify a user
- identity management
- product analytics
- http v2 api uploadEvents
- ingests and exports event data
- feature flags
- unified workflow for sending events and identifying users. for data engineers.
- runs experiments and feature flags
- user behavior
- manages privacy and compliance
- manage event schemas and chart annotations. for data governance teams.
- manage and evaluate a/b experiments and feature flags. for product managers.
- privacy compliance
- sendAttribution
- identify api identifyUser
- attribution api sendAttribution
- identifyUser
- event ingestion
- amplitude
- uploadEvents
- scim provisioning and privacy compliance. for it admins and compliance teams.
- amplitude upload events
- amplitude send attribution data
- export raw event data and manage behavioral cohorts. for data analysts.
- a/b testing
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
