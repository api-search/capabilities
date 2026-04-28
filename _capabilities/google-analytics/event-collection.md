---
categories: []
consumed_apis:
- ga-measurement-protocol
- ga-admin-api
description: Unified workflow for server-side event tracking combining the Measurement Protocol for sending events with the Admin API for managing measurement protocol secrets and data streams. Used by backend engineers and marketing ops teams to implement server-side tracking and offline event collection.
layout: capability
name: Google Analytics Event Collection
operations:
- description: Send events via Measurement Protocol
  method: POST
  name: send-events
  path: /v1/events
- description: Validate event payloads
  method: POST
  name: validate-events
  path: /v1/events/validate
- description: List data streams
  method: GET
  name: list-data-streams
  path: /v1/data-streams
- description: Create a data stream
  method: POST
  name: create-data-stream
  path: /v1/data-streams
- description: List measurement protocol secrets
  method: GET
  name: list-measurement-protocol-secrets
  path: /v1/secrets
- description: Create a measurement protocol secret
  method: POST
  name: create-measurement-protocol-secret
  path: /v1/secrets
personas:
- description: Implements server-side event tracking and offline data collection.
  id: backend-engineer
  name: Backend Engineer
- description: Connects advertising platforms and implements server-side tracking.
  id: marketing-ops
  name: Marketing Operations
provider_name: Google Analytics
provider_slug: google-analytics
search_terms:
- marketing ops
- implements server-side event tracking and offline data collection.
- create an api secret for measurement protocol authentication
- list measurement protocol secrets
- create a measurement protocol secret
- data protection engineer
- marketing team
- sets up and maintains ga4 accounts, properties, and configurations.
- builds automated reporting pipelines and dashboards from ga4 data.
- server-side event tracking with data stream and secret management.
- measures campaign performance, segments audiences, and tracks conversions.
- create a data stream
- create, export, and query ga4 audience segments.
- segmenting and exporting user populations for analysis and activation.
- reporting
- analytics administrator
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- acknowledge user data collection terms (required before creating secrets)
- manage api secrets for measurement protocol
- send events via measurement protocol
- create measurement protocol secret
- compliance team
- extracts insights from ga4 data through reports and explorations.
- audits data access and monitors configuration changes.
- analytics
- google analytics
- measurement protocol
- backend engineer
- querying and analyzing ga4 event data through various report types.
- validate events without sending
- list data streams
- google
- acknowledge user data collection
- privacy officer
- metrics
- create data stream
- implements privacy-compliant data handling and deletion workflows.
- events
- manage data streams for event collection
- list api secrets for measurement protocol authentication
- data
- bi engineer
- send events to google analytics
- data analyst
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- connecting ga4 with advertising, app, and measurement platforms.
- ingesting events from servers, apps, and offline sources.
- user data deletion, access auditing, and data collection acknowledgement.
- validate event payloads without sending to google analytics
- web analytics
- list data streams for configuring event collection
- machine learning
- tracking
- create a new data stream for event collection
- validate events
- run standard, realtime, pivot, and batch reports with data access auditing.
- managing data privacy, deletion, and access auditing.
- platform engineer
- server side
- validate event payloads
- attribution
- manages data privacy compliance including gdpr deletion requests.
- integrates ga4 with other platforms and manages infrastructure.
- setting up and maintaining ga4 account and property structure.
- connects advertising platforms and implements server-side tracking.
- send events
- send events to google analytics via measurement protocol
slug: event-collection
tags:
- Google Analytics
- Measurement Protocol
- Events
- Server Side
- Tracking
tools:
- description: Send events to Google Analytics via Measurement Protocol
  hints:
    idempotent: false
    readOnly: false
  name: send-events
- description: Validate event payloads without sending to Google Analytics
  hints:
    idempotent: true
    readOnly: true
  name: validate-events
- description: List data streams for configuring event collection
  hints:
    idempotent: true
    readOnly: true
  name: list-data-streams
- description: Create a new data stream for event collection
  hints:
    idempotent: false
    readOnly: false
  name: create-data-stream
- description: List API secrets for Measurement Protocol authentication
  hints:
    idempotent: true
    readOnly: true
  name: list-measurement-protocol-secrets
- description: Create an API secret for Measurement Protocol authentication
  hints:
    idempotent: false
    readOnly: false
  name: create-measurement-protocol-secret
- description: Acknowledge user data collection terms (required before creating secrets)
  hints:
    idempotent: true
    readOnly: false
  name: acknowledge-user-data-collection
---
