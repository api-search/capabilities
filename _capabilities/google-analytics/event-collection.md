---
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
- marketing team
- data protection engineer
- extracts insights from ga4 data through reports and explorations.
- privacy officer
- implements server-side event tracking and offline data collection.
- machine learning
- connecting ga4 with advertising, app, and measurement platforms.
- tracking
- integrates ga4 with other platforms and manages infrastructure.
- validate event payloads
- create a data stream
- send events to google analytics via measurement protocol
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- web analytics
- builds automated reporting pipelines and dashboards from ga4 data.
- bi engineer
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- create, export, and query ga4 audience segments.
- list data streams for configuring event collection
- create measurement protocol secret
- audits data access and monitors configuration changes.
- create data stream
- events
- send events to google analytics
- run standard, realtime, pivot, and batch reports with data access auditing.
- compliance team
- list data streams
- implements privacy-compliant data handling and deletion workflows.
- server side
- marketing ops
- data analyst
- manage api secrets for measurement protocol
- measurement protocol
- analytics administrator
- querying and analyzing ga4 event data through various report types.
- create an api secret for measurement protocol authentication
- platform engineer
- user data deletion, access auditing, and data collection acknowledgement.
- send events
- measures campaign performance, segments audiences, and tracks conversions.
- validate event payloads without sending to google analytics
- list api secrets for measurement protocol authentication
- data
- analytics
- acknowledge user data collection
- attribution
- manages data privacy compliance including gdpr deletion requests.
- validate events
- manage data streams for event collection
- server-side event tracking with data stream and secret management.
- sets up and maintains ga4 accounts, properties, and configurations.
- ingesting events from servers, apps, and offline sources.
- backend engineer
- connects advertising platforms and implements server-side tracking.
- google
- metrics
- managing data privacy, deletion, and access auditing.
- google analytics
- create a measurement protocol secret
- segmenting and exporting user populations for analysis and activation.
- send events via measurement protocol
- reporting
- setting up and maintaining ga4 account and property structure.
- list measurement protocol secrets
- acknowledge user data collection terms (required before creating secrets)
- create a new data stream for event collection
- validate events without sending
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
