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
- list measurement protocol secrets
- manages data privacy compliance including gdpr deletion requests.
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- analytics administrator
- platform engineer
- audits data access and monitors configuration changes.
- list data streams for configuring event collection
- list api secrets for measurement protocol authentication
- acknowledge user data collection terms (required before creating secrets)
- querying and analyzing ga4 event data through various report types.
- analytics
- validate events
- data protection engineer
- server-side event tracking with data stream and secret management.
- manage api secrets for measurement protocol
- measures campaign performance, segments audiences, and tracks conversions.
- connecting ga4 with advertising, app, and measurement platforms.
- create a measurement protocol secret
- implements privacy-compliant data handling and deletion workflows.
- run standard, realtime, pivot, and batch reports with data access auditing.
- integrates ga4 with other platforms and manages infrastructure.
- builds automated reporting pipelines and dashboards from ga4 data.
- validate event payloads
- send events via measurement protocol
- compliance team
- segmenting and exporting user populations for analysis and activation.
- sets up and maintains ga4 accounts, properties, and configurations.
- create a new data stream for event collection
- web analytics
- validate event payloads without sending to google analytics
- reporting
- setting up and maintaining ga4 account and property structure.
- user data deletion, access auditing, and data collection acknowledgement.
- manage data streams for event collection
- bi engineer
- server side
- managing data privacy, deletion, and access auditing.
- send events
- measurement protocol
- marketing team
- implements server-side event tracking and offline data collection.
- marketing ops
- machine learning
- events
- attribution
- send events to google analytics via measurement protocol
- connects advertising platforms and implements server-side tracking.
- tracking
- create a data stream
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- metrics
- create data stream
- list data streams
- create, export, and query ga4 audience segments.
- backend engineer
- send events to google analytics
- google analytics
- data analyst
- create an api secret for measurement protocol authentication
- create measurement protocol secret
- acknowledge user data collection
- ingesting events from servers, apps, and offline sources.
- data
- privacy officer
- google
- extracts insights from ga4 data through reports and explorations.
- validate events without sending
slug: event-collection
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Analytics Event Collection\"\n  description: \"Unified workflow for server-side event tracking combining the Measurement Protocol for sending events with the Admin API for managing measurement protocol secrets and data streams. Used by backend engineers and marketing ops teams to implement server-side tracking and offline event collection.\"\n  tags:\n    - Google Analytics\n    - Measurement Protocol\n    - Events\n    - Server Side\n    - Tracking\n  created: \"2026-04-17\"\n  modified: \"2026-04-17\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_ANALYTICS_ACCESS_TOKEN: GOOGLE_ANALYTICS_ACCESS_TOKEN\n      GOOGLE_ANALYTICS_API_SECRET: GOOGLE_ANALYTICS_API_SECRET\n      GOOGLE_ANALYTICS_MEASUREMENT_ID: GOOGLE_ANALYTICS_MEASUREMENT_ID\n\ncapability:\n  consumes:\n    - import: ga-measurement-protocol\n      location: ./shared/measurement-protocol.yaml\n    - import: ga-admin-api\n      location: ./shared/admin-api.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8083\n      namespace: ga-collection-api\n      description: \"Unified REST API for Google Analytics event collection and validation.\"\n      resources:\n        - path: /v1/events\n          name: events\n          description: \"Send events to Google Analytics\"\n          operations:\n            - method: POST\n              name: send-events\n              description: \"Send events via Measurement Protocol\"\n              call: \"ga-measurement-protocol.send-events\"\n              with:\n                api_secret: \"rest.api_secret\"\n                measurement_id: \"rest.measurement_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events/validate\n          name: validate-events\n          description: \"Validate events without sending\"\n          operations:\n            - method: POST\n              name: validate-events\n              description: \"\
  Validate event payloads\"\n              call: \"ga-measurement-protocol.validate-events\"\n              with:\n                api_secret: \"rest.api_secret\"\n                measurement_id: \"rest.measurement_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data-streams\n          name: data-streams\n          description: \"Manage data streams for event collection\"\n          operations:\n            - method: GET\n              name: list-data-streams\n              description: \"List data streams\"\n              call: \"ga-admin-api.list-data-streams\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-data-stream\n              description: \"Create a data stream\"\n              call: \"ga-admin-api.create-data-stream\"\n            \
  \  with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/secrets\n          name: measurement-protocol-secrets\n          description: \"Manage API secrets for Measurement Protocol\"\n          operations:\n            - method: GET\n              name: list-measurement-protocol-secrets\n              description: \"List measurement protocol secrets\"\n              call: \"ga-admin-api.list-measurement-protocol-secrets\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-measurement-protocol-secret\n              description: \"Create a measurement protocol secret\"\n              call: \"ga-admin-api.create-measurement-protocol-secret\"\n              with:\n                parent: \"rest.parent\"\n        \
  \      outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9083\n      namespace: ga-collection-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Google Analytics event collection.\"\n      tools:\n        - name: send-events\n          description: \"Send events to Google Analytics via Measurement Protocol\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ga-measurement-protocol.send-events\"\n          with:\n            api_secret: \"tools.api_secret\"\n            measurement_id: \"tools.measurement_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: validate-events\n          description: \"Validate event payloads without sending to Google Analytics\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-measurement-protocol.validate-events\"\n\
  \          with:\n            api_secret: \"tools.api_secret\"\n            measurement_id: \"tools.measurement_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-data-streams\n          description: \"List data streams for configuring event collection\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.list-data-streams\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-data-stream\n          description: \"Create a new data stream for event collection\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ga-admin-api.create-data-stream\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-measurement-protocol-secrets\n\
  \          description: \"List API secrets for Measurement Protocol authentication\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.list-measurement-protocol-secrets\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-measurement-protocol-secret\n          description: \"Create an API secret for Measurement Protocol authentication\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ga-admin-api.create-measurement-protocol-secret\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: acknowledge-user-data-collection\n          description: \"Acknowledge user data collection terms (required before creating secrets)\"\n          hints:\n            readOnly: false\n\
  \            idempotent: true\n          call: \"ga-admin-api.acknowledge-user-data-collection\"\n          with:\n            property: \"tools.property\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-analytics/refs/heads/main/capabilities/event-collection.yaml
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
