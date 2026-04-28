---
categories:
- analytics
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
- sendAttribution
- scim provisioning and privacy compliance. for it admins and compliance teams.
- uploadEvents
- identifyUser
- runs experiments and feature flags
- manages privacy and compliance
- event ingestion
- amplitude send attribution data
- ingests and exports event data
- export raw event data and manage behavioral cohorts. for data analysts.
- amplitude identify a user
- data governance
- amplitude
- amplitude upload events
- identify api identifyUser
- manage event schemas and chart annotations. for data governance teams.
- feature flags
- analyzes data and manages cohorts
- identity management
- privacy compliance
- product analytics
- analytics
- experimentation
- unified workflow for sending events and identifying users. for data engineers.
- http v2 api uploadEvents
- a/b testing
- attribution api sendAttribution
- manage and evaluate a/b experiments and feature flags. for product managers.
- user behavior
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
