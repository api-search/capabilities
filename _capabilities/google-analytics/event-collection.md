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
- connects advertising platforms and implements server-side tracking.
- connecting ga4 with advertising, app, and measurement platforms.
- google
- analytics
- measurement protocol
- manage api secrets for measurement protocol
- bi engineer
- validate events
- data
- list data streams for configuring event collection
- attribution
- ingesting events from servers, apps, and offline sources.
- measures campaign performance, segments audiences, and tracks conversions.
- send events
- list api secrets for measurement protocol authentication
- integrates ga4 with other platforms and manages infrastructure.
- sets up and maintains ga4 accounts, properties, and configurations.
- querying and analyzing ga4 event data through various report types.
- managing data privacy, deletion, and access auditing.
- create an api secret for measurement protocol authentication
- events
- implements privacy-compliant data handling and deletion workflows.
- send events to google analytics via measurement protocol
- platform engineer
- reporting
- web analytics
- send events via measurement protocol
- validate events without sending
- send events to google analytics
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- server-side event tracking with data stream and secret management.
- manage data streams for event collection
- audits data access and monitors configuration changes.
- run standard, realtime, pivot, and batch reports with data access auditing.
- create measurement protocol secret
- create, export, and query ga4 audience segments.
- machine learning
- validate event payloads
- acknowledge user data collection
- privacy officer
- extracts insights from ga4 data through reports and explorations.
- segmenting and exporting user populations for analysis and activation.
- marketing ops
- user data deletion, access auditing, and data collection acknowledgement.
- setting up and maintaining ga4 account and property structure.
- metrics
- validate event payloads without sending to google analytics
- implements server-side event tracking and offline data collection.
- manages data privacy compliance including gdpr deletion requests.
- google analytics
- create a measurement protocol secret
- data protection engineer
- compliance team
- builds automated reporting pipelines and dashboards from ga4 data.
- create a new data stream for event collection
- list data streams
- acknowledge user data collection terms (required before creating secrets)
- analytics administrator
- backend engineer
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- create a data stream
- tracking
- server side
- list measurement protocol secrets
- marketing team
- create data stream
- data analyst
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
