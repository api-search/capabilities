---
categories: []
consumed_apis:
- ga-admin-api
description: Unified workflow for managing GA4 integration links with Firebase, Google Ads, and measurement protocol secrets. Used by platform engineers and marketing ops teams to connect GA4 with advertising and app platforms.
layout: capability
name: Google Analytics Integrations and Linking
operations:
- description: List Firebase links on a property
  method: GET
  name: list-firebase-links
  path: /v1/firebase-links
- description: Create a Firebase link
  method: POST
  name: create-firebase-link
  path: /v1/firebase-links
- description: List Google Ads links on a property
  method: GET
  name: list-google-ads-links
  path: /v1/google-ads-links
- description: Create a Google Ads link
  method: POST
  name: create-google-ads-link
  path: /v1/google-ads-links
- description: Update a Google Ads link
  method: PATCH
  name: update-google-ads-link
  path: /v1/google-ads-links/{id}
- description: Delete a Google Ads link
  method: DELETE
  name: delete-google-ads-link
  path: /v1/google-ads-links/{id}
- description: List measurement protocol secrets
  method: GET
  name: list-measurement-protocol-secrets
  path: /v1/measurement-protocol-secrets
- description: Create a measurement protocol secret
  method: POST
  name: create-measurement-protocol-secret
  path: /v1/measurement-protocol-secrets
- description: Get a measurement protocol secret
  method: GET
  name: get-measurement-protocol-secret
  path: /v1/measurement-protocol-secrets/{id}
personas:
- description: Integrates GA4 with other platforms and manages infrastructure.
  id: platform-engineer
  name: Platform Engineer
- description: Connects advertising platforms and implements server-side tracking.
  id: marketing-ops
  name: Marketing Operations
provider_name: Google Analytics
provider_slug: google-analytics
search_terms:
- segmenting and exporting user populations for analysis and activation.
- backend engineer
- google
- privacy officer
- attribution
- create firebase link
- create a measurement protocol secret for server-side tracking
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- manages data privacy compliance including gdpr deletion requests.
- manage measurement protocol secrets
- google analytics
- list firebase links on a property
- list google ads links on a ga4 property
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- marketing ops
- integrations
- list firebase links on a ga4 property
- update a google ads link
- user data deletion, access auditing, and data collection acknowledgement.
- sets up and maintains ga4 accounts, properties, and configurations.
- google ads
- reporting
- machine learning
- run standard, realtime, pivot, and batch reports with data access auditing.
- delete google ads link
- data analyst
- create google ads link
- querying and analyzing ga4 event data through various report types.
- linking
- implements privacy-compliant data handling and deletion workflows.
- setting up and maintaining ga4 account and property structure.
- list google ads links on a property
- create a measurement protocol secret
- list measurement protocol secrets for a data stream
- manage google ads integration links
- data protection engineer
- connects advertising platforms and implements server-side tracking.
- implements server-side event tracking and offline data collection.
- create a firebase link
- ingesting events from servers, apps, and offline sources.
- managing data privacy, deletion, and access auditing.
- list google ads links
- create a firebase integration link on a ga4 property
- analytics
- analytics administrator
- create, export, and query ga4 audience segments.
- extracts insights from ga4 data through reports and explorations.
- builds automated reporting pipelines and dashboards from ga4 data.
- update google ads link
- manage firebase integration links
- connecting ga4 with advertising, app, and measurement platforms.
- create a google ads link
- create measurement protocol secret
- bi engineer
- compliance team
- marketing team
- get a specific measurement protocol secret
- update a google ads link configuration
- data
- measures campaign performance, segments audiences, and tracks conversions.
- delete a google ads link
- get a measurement protocol secret
- audits data access and monitors configuration changes.
- metrics
- get details of a specific measurement protocol secret
- server-side event tracking with data stream and secret management.
- web analytics
- integrates ga4 with other platforms and manages infrastructure.
- list measurement protocol secrets
- list firebase links
- firebase
- delete a google ads integration link
- platform engineer
- create a google ads integration link on a ga4 property
- get measurement protocol secret
- manage a specific google ads link
slug: integrations-and-linking
source_filename: integrations-and-linking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Analytics Integrations and Linking\"\n  description: \"Unified workflow for managing GA4 integration links with Firebase, Google Ads, and measurement protocol secrets. Used by platform engineers and marketing ops teams to connect GA4 with advertising and app platforms.\"\n  tags:\n    - Google Analytics\n    - Integrations\n    - Firebase\n    - Google Ads\n    - Linking\n  created: \"2026-04-17\"\n  modified: \"2026-04-17\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_ANALYTICS_ACCESS_TOKEN: GOOGLE_ANALYTICS_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: ga-admin-api\n      location: ./shared/admin-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: ga-integrations-api\n      description: \"Unified REST API for Google Analytics integration management.\"\n      resources:\n        - path: /v1/firebase-links\n          name: firebase-links\n          description: \"Manage Firebase\
  \ integration links\"\n          operations:\n            - method: GET\n              name: list-firebase-links\n              description: \"List Firebase links on a property\"\n              call: \"ga-admin-api.list-firebase-links\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-firebase-link\n              description: \"Create a Firebase link\"\n              call: \"ga-admin-api.create-firebase-link\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/google-ads-links\n          name: google-ads-links\n          description: \"Manage Google Ads integration links\"\n          operations:\n            - method: GET\n              name: list-google-ads-links\n              description:\
  \ \"List Google Ads links on a property\"\n              call: \"ga-admin-api.list-google-ads-links\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-google-ads-link\n              description: \"Create a Google Ads link\"\n              call: \"ga-admin-api.create-google-ads-link\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/google-ads-links/{id}\n          name: google-ads-link\n          description: \"Manage a specific Google Ads link\"\n          operations:\n            - method: PATCH\n              name: update-google-ads-link\n              description: \"Update a Google Ads link\"\n              call: \"ga-admin-api.update-google-ads-link\"\n              with:\n         \
  \       name: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-google-ads-link\n              description: \"Delete a Google Ads link\"\n              call: \"ga-admin-api.delete-google-ads-link\"\n              with:\n                name: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/measurement-protocol-secrets\n          name: measurement-protocol-secrets\n          description: \"Manage measurement protocol secrets\"\n          operations:\n            - method: GET\n              name: list-measurement-protocol-secrets\n              description: \"List measurement protocol secrets\"\n              call: \"ga-admin-api.list-measurement-protocol-secrets\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n            - method: POST\n              name: create-measurement-protocol-secret\n              description: \"Create a measurement protocol secret\"\n              call: \"ga-admin-api.create-measurement-protocol-secret\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/measurement-protocol-secrets/{id}\n          name: measurement-protocol-secret\n          description: \"Get a specific measurement protocol secret\"\n          operations:\n            - method: GET\n              name: get-measurement-protocol-secret\n              description: \"Get a measurement protocol secret\"\n              call: \"ga-admin-api.get-measurement-protocol-secret\"\n              with:\n                name: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type:\
  \ mcp\n      port: 9082\n      namespace: ga-integrations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Google Analytics integration management.\"\n      tools:\n        - name: list-firebase-links\n          description: \"List Firebase links on a GA4 property\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.list-firebase-links\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-firebase-link\n          description: \"Create a Firebase integration link on a GA4 property\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ga-admin-api.create-firebase-link\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-google-ads-links\n\
  \          description: \"List Google Ads links on a GA4 property\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.list-google-ads-links\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-google-ads-link\n          description: \"Create a Google Ads integration link on a GA4 property\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ga-admin-api.create-google-ads-link\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-google-ads-link\n          description: \"Update a Google Ads link configuration\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"ga-admin-api.update-google-ads-link\"\n          with:\n\
  \            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-google-ads-link\n          description: \"Delete a Google Ads integration link\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"ga-admin-api.delete-google-ads-link\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-measurement-protocol-secrets\n          description: \"List measurement protocol secrets for a data stream\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.list-measurement-protocol-secrets\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-measurement-protocol-secret\n\
  \          description: \"Create a measurement protocol secret for server-side tracking\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ga-admin-api.create-measurement-protocol-secret\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-measurement-protocol-secret\n          description: \"Get details of a specific measurement protocol secret\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.get-measurement-protocol-secret\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-analytics/refs/heads/main/capabilities/integrations-and-linking.yaml
tags:
- Google Analytics
- Integrations
- Firebase
- Google Ads
- Linking
tools:
- description: List Firebase links on a GA4 property
  hints:
    idempotent: true
    readOnly: true
  name: list-firebase-links
- description: Create a Firebase integration link on a GA4 property
  hints:
    idempotent: false
    readOnly: false
  name: create-firebase-link
- description: List Google Ads links on a GA4 property
  hints:
    idempotent: true
    readOnly: true
  name: list-google-ads-links
- description: Create a Google Ads integration link on a GA4 property
  hints:
    idempotent: false
    readOnly: false
  name: create-google-ads-link
- description: Update a Google Ads link configuration
  hints:
    idempotent: true
    readOnly: false
  name: update-google-ads-link
- description: Delete a Google Ads integration link
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-google-ads-link
- description: List measurement protocol secrets for a data stream
  hints:
    idempotent: true
    readOnly: true
  name: list-measurement-protocol-secrets
- description: Create a measurement protocol secret for server-side tracking
  hints:
    idempotent: false
    readOnly: false
  name: create-measurement-protocol-secret
- description: Get details of a specific measurement protocol secret
  hints:
    idempotent: true
    readOnly: true
  name: get-measurement-protocol-secret
---
