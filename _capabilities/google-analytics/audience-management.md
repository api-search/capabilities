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
- create and list audience exports
- data
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- get a specific audience export
- create an audience export
- analytics
- get audience export details
- metrics
- attribution
- query audience export
- machine learning
- manages data privacy compliance including gdpr deletion requests.
- bi engineer
- create audience export
- marketing
- list ga4 properties to identify available audiences
- backend engineer
- list all audience exports for a property
- server-side event tracking with data stream and secret management.
- get audience export
- setting up and maintaining ga4 account and property structure.
- marketing ops
- google analytics
- marketing team
- compliance team
- google
- reporting
- managing data privacy, deletion, and access auditing.
- implements privacy-compliant data handling and deletion workflows.
- querying and analyzing ga4 event data through various report types.
- extracts insights from ga4 data through reports and explorations.
- audiences
- platform engineer
- privacy officer
- list audience exports
- data analyst
- query users from an audience export
- builds automated reporting pipelines and dashboards from ga4 data.
- integrates ga4 with other platforms and manages infrastructure.
- create, export, and query ga4 audience segments.
- data protection engineer
- sets up and maintains ga4 accounts, properties, and configurations.
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- retrieve users from an audience export
- measures campaign performance, segments audiences, and tracks conversions.
- run standard, realtime, pivot, and batch reports with data access auditing.
- list properties
- user data deletion, access auditing, and data collection acknowledgement.
- implements server-side event tracking and offline data collection.
- segmenting and exporting user populations for analysis and activation.
- list ga4 properties
- connecting ga4 with advertising, app, and measurement platforms.
- segmentation
- get metadata about a specific audience export
- retrieve users from a completed audience export
- audits data access and monitors configuration changes.
- connects advertising platforms and implements server-side tracking.
- list properties for audience context
- web analytics
- ingesting events from servers, apps, and offline sources.
- export
- analytics administrator
- create an audience export for a ga4 property
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
