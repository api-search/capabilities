---
categories: []
consumed_apis:
- ga-data-api
- ga-admin-api
description: Unified workflow for creating, exporting, and analyzing GA4 audiences. Combines the Data API audience export capabilities with Admin API property configuration. Used by marketing teams and data analysts for audience segmentation, export, and activation.
layout: capability
name: Google Analytics Audience Management
operations:
- description: Create an audience export
  method: POST
  name: create-audience-export
  path: /v1/audience-exports
- description: List audience exports
  method: GET
  name: list-audience-exports
  path: /v1/audience-exports
- description: Get audience export details
  method: GET
  name: get-audience-export
  path: /v1/audience-exports/{id}
- description: Query users from an audience export
  method: POST
  name: query-audience-export
  path: /v1/audience-exports/{id}/users
- description: List GA4 properties
  method: GET
  name: list-properties
  path: /v1/properties
personas:
- description: Measures campaign performance, segments audiences, and tracks conversions.
  id: marketing-team
  name: Marketing Team
- description: Extracts insights from GA4 data through reports and explorations.
  id: data-analyst
  name: Data Analyst
provider_name: Google Analytics
provider_slug: google-analytics
search_terms:
- get audience export details
- create an audience export for a ga4 property
- bi engineer
- implements server-side event tracking and offline data collection.
- list ga4 properties to identify available audiences
- list all audience exports for a property
- get a specific audience export
- setting up and maintaining ga4 account and property structure.
- integrates ga4 with other platforms and manages infrastructure.
- web analytics
- attribution
- marketing
- get metadata about a specific audience export
- list properties for audience context
- retrieve users from an audience export
- export
- create, export, and query ga4 audience segments.
- audits data access and monitors configuration changes.
- ingesting events from servers, apps, and offline sources.
- analytics
- data
- retrieve users from a completed audience export
- list audience exports
- google
- get audience export
- query audience export
- list ga4 properties
- querying and analyzing ga4 event data through various report types.
- server-side event tracking with data stream and secret management.
- backend engineer
- builds automated reporting pipelines and dashboards from ga4 data.
- implements privacy-compliant data handling and deletion workflows.
- create an audience export
- connecting ga4 with advertising, app, and measurement platforms.
- reporting
- data analyst
- data protection engineer
- managing data privacy, deletion, and access auditing.
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- run standard, realtime, pivot, and batch reports with data access auditing.
- platform engineer
- measures campaign performance, segments audiences, and tracks conversions.
- query users from an audience export
- compliance team
- connects advertising platforms and implements server-side tracking.
- machine learning
- marketing ops
- analytics administrator
- google analytics
- create audience export
- extracts insights from ga4 data through reports and explorations.
- metrics
- segmentation
- user data deletion, access auditing, and data collection acknowledgement.
- manages data privacy compliance including gdpr deletion requests.
- audiences
- sets up and maintains ga4 accounts, properties, and configurations.
- list properties
- segmenting and exporting user populations for analysis and activation.
- marketing team
- privacy officer
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- create and list audience exports
slug: audience-management
source_filename: audience-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Analytics Audience Management\"\n  description: \"Unified workflow for creating, exporting, and analyzing GA4 audiences. Combines the Data API audience export capabilities with Admin API property configuration. Used by marketing teams and data analysts for audience segmentation, export, and activation.\"\n  tags:\n    - Google Analytics\n    - Audiences\n    - Segmentation\n    - Export\n    - Marketing\n  created: \"2026-04-17\"\n  modified: \"2026-04-17\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_ANALYTICS_ACCESS_TOKEN: GOOGLE_ANALYTICS_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: ga-data-api\n      location: ./shared/data-api.yaml\n    - import: ga-admin-api\n      location: ./shared/admin-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: ga-audience-api\n      description: \"Unified REST API for Google Analytics audience management.\"\n      resources:\n        - path:\
  \ /v1/audience-exports\n          name: audience-exports\n          description: \"Create and list audience exports\"\n          operations:\n            - method: POST\n              name: create-audience-export\n              description: \"Create an audience export\"\n              call: \"ga-data-api.create-audience-export\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-audience-exports\n              description: \"List audience exports\"\n              call: \"ga-data-api.list-audience-exports\"\n              with:\n                parent: \"rest.parent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/audience-exports/{id}\n          name: audience-export\n          description: \"Get a specific audience export\"\n          operations:\n  \
  \          - method: GET\n              name: get-audience-export\n              description: \"Get audience export details\"\n              call: \"ga-data-api.get-audience-export\"\n              with:\n                name: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/audience-exports/{id}/users\n          name: audience-export-users\n          description: \"Retrieve users from an audience export\"\n          operations:\n            - method: POST\n              name: query-audience-export\n              description: \"Query users from an audience export\"\n              call: \"ga-data-api.query-audience-export\"\n              with:\n                name: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/properties\n          name: properties\n          description: \"List properties for audience context\"\n  \
  \        operations:\n            - method: GET\n              name: list-properties\n              description: \"List GA4 properties\"\n              call: \"ga-admin-api.list-properties\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9084\n      namespace: ga-audience-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Google Analytics audience management.\"\n      tools:\n        - name: create-audience-export\n          description: \"Create an audience export for a GA4 property\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ga-data-api.create-audience-export\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-audience-export\n          description: \"Get metadata about a specific audience export\"\n         \
  \ hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-data-api.get-audience-export\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-audience-exports\n          description: \"List all audience exports for a property\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-data-api.list-audience-exports\"\n          with:\n            parent: \"tools.parent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-audience-export\n          description: \"Retrieve users from a completed audience export\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-data-api.query-audience-export\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n   \
  \           mapping: \"$.\"\n        - name: list-properties\n          description: \"List GA4 properties to identify available audiences\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.list-properties\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-analytics/refs/heads/main/capabilities/audience-management.yaml
tags:
- Google Analytics
- Audiences
- Segmentation
- Export
- Marketing
tools:
- description: Create an audience export for a GA4 property
  hints:
    idempotent: false
    readOnly: false
  name: create-audience-export
- description: Get metadata about a specific audience export
  hints:
    idempotent: true
    readOnly: true
  name: get-audience-export
- description: List all audience exports for a property
  hints:
    idempotent: true
    readOnly: true
  name: list-audience-exports
- description: Retrieve users from a completed audience export
  hints:
    idempotent: true
    readOnly: true
  name: query-audience-export
- description: List GA4 properties to identify available audiences
  hints:
    idempotent: true
    readOnly: true
  name: list-properties
---
