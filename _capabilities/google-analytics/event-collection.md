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
- send events to google analytics via measurement protocol
- querying and analyzing ga4 event data through various report types.
- tracking
- data
- send events to google analytics
- metrics
- sets up and maintains ga4 accounts, properties, and configurations.
- extracts insights from ga4 data through reports and explorations.
- marketing ops
- segmenting and exporting user populations for analysis and activation.
- data protection engineer
- create a new data stream for event collection
- list api secrets for measurement protocol authentication
- integrates ga4 with other platforms and manages infrastructure.
- analytics
- privacy officer
- web analytics
- validate events without sending
- measures campaign performance, segments audiences, and tracks conversions.
- validate event payloads
- create an api secret for measurement protocol authentication
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- machine learning
- validate events
- server side
- create measurement protocol secret
- acknowledge user data collection terms (required before creating secrets)
- events
- bi engineer
- server-side event tracking with data stream and secret management.
- managing data privacy, deletion, and access auditing.
- implements server-side event tracking and offline data collection.
- google analytics
- create, export, and query ga4 audience segments.
- create a measurement protocol secret
- list data streams for configuring event collection
- backend engineer
- setting up and maintaining ga4 account and property structure.
- marketing team
- audits data access and monitors configuration changes.
- list measurement protocol secrets
- run standard, realtime, pivot, and batch reports with data access auditing.
- manages data privacy compliance including gdpr deletion requests.
- connecting ga4 with advertising, app, and measurement platforms.
- google
- implements privacy-compliant data handling and deletion workflows.
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- analytics administrator
- compliance team
- validate event payloads without sending to google analytics
- acknowledge user data collection
- attribution
- connects advertising platforms and implements server-side tracking.
- manage api secrets for measurement protocol
- send events via measurement protocol
- platform engineer
- user data deletion, access auditing, and data collection acknowledgement.
- data analyst
- builds automated reporting pipelines and dashboards from ga4 data.
- create a data stream
- create data stream
- ingesting events from servers, apps, and offline sources.
- send events
- measurement protocol
- list data streams
- reporting
- manage data streams for event collection
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
