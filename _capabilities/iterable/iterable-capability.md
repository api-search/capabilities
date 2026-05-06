---
categories: []
consumed_apis: []
description: The Iterable Export API enables developers to extract data from Iterable projects for analytics, reporting, and data warehousing purposes. It provides export endpoints that allow retrieval of user data, event data, campaign metrics, and message engagement information in CSV and JSON formats. The export endpoints support filtering by date ranges and event types, making it possible to build custom reporting pipelines and synchronize Iterable data with external business intelligence tools.
layout: capability
name: Iterable Export API
operations:
- description: Export data as JSON
  method: GET
  name: exportdatajson
  path: /export/data.json
- description: Export data as CSV
  method: GET
  name: exportdatacsv
  path: /export/data.csv
- description: Export events for a specific user
  method: GET
  name: exportuserevents
  path: /export/userEvents
- description: Export experiment metrics as CSV
  method: GET
  name: exportexperimentmetrics
  path: /experiments/metrics
personas: []
provider_name: Iterable
provider_slug: iterable
search_terms:
- email
- marketing automation
- exportexperimentmetrics
- exportuserevents
- export data as json
- export experiment metrics as csv
- exportdatajson
- customer engagement
- api
- export events for a specific user
- push notifications
- exportdatacsv
- cross-channel messaging
- sms
- export data as csv
- iterable
slug: iterable-capability
source_filename: iterable-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Iterable Export API\n  description: The Iterable Export API enables developers to extract data from Iterable projects for analytics, reporting,\n    and data warehousing purposes. It provides export endpoints that allow retrieval of user data, event data, campaign metrics,\n    and message engagement information in CSV and JSON formats. The export endpoints support filtering by date ranges and\n    event types, making it possible to build custom reporting pipelines and synchronize Iterable data with external business\n    intelligence tools.\n  tags:\n  - Iterable\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: iterable\n    baseUri: https://api.iterable.com/api\n    description: Iterable Export API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Api-Key\n      value: '{{ITERABLE_TOKEN}}'\n    resources:\n    - name: export-data-json\n\
  \      path: /export/data.json\n      operations:\n      - name: exportdatajson\n        method: GET\n        description: Export data as JSON\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: export-data-csv\n      path: /export/data.csv\n      operations:\n      - name: exportdatacsv\n        method: GET\n        description: Export data as CSV\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: export-userevents\n      path: /export/userEvents\n      operations:\n      - name: exportuserevents\n        method: GET\n        description: Export events for a specific user\n        inputParameters:\n        - name: email\n          in: query\n          type: string\n          required: true\n          description: Email address of the user whose events to export\n        - name: includeCustomEvents\n          in:\
  \ query\n          type: boolean\n          description: Whether to include custom events in the export\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: experiments-metrics\n      path: /experiments/metrics\n      operations:\n      - name: exportexperimentmetrics\n        method: GET\n        description: Export experiment metrics as CSV\n        inputParameters:\n        - name: experimentId\n          in: query\n          type: array\n          description: One or more experiment IDs to export metrics for\n        - name: campaignId\n          in: query\n          type: array\n          description: One or more campaign IDs to export metrics for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: iterable-rest\n    description: REST adapter for Iterable Export\
  \ API.\n    resources:\n    - path: /export/data.json\n      name: exportdatajson\n      operations:\n      - method: GET\n        name: exportdatajson\n        description: Export data as JSON\n        call: iterable.exportdatajson\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /export/data.csv\n      name: exportdatacsv\n      operations:\n      - method: GET\n        name: exportdatacsv\n        description: Export data as CSV\n        call: iterable.exportdatacsv\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /export/userEvents\n      name: exportuserevents\n      operations:\n      - method: GET\n        name: exportuserevents\n        description: Export events for a specific user\n        call: iterable.exportuserevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /experiments/metrics\n      name: exportexperimentmetrics\n      operations:\n      - method: GET\n\
  \        name: exportexperimentmetrics\n        description: Export experiment metrics as CSV\n        call: iterable.exportexperimentmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: iterable-mcp\n    transport: http\n    description: MCP adapter for Iterable Export API for AI agent use.\n    tools:\n    - name: exportdatajson\n      description: Export data as JSON\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: iterable.exportdatajson\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: exportdatacsv\n      description: Export data as CSV\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: iterable.exportdatacsv\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: exportuserevents\n      description: Export events for a specific user\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: iterable.exportuserevents\n      with:\n        email: tools.email\n        includeCustomEvents: tools.includeCustomEvents\n      inputParameters:\n      - name: email\n        type: string\n        description: Email address of the user whose events to export\n        required: true\n      - name: includeCustomEvents\n        type: boolean\n        description: Whether to include custom events in the export\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: exportexperimentmetrics\n      description: Export experiment metrics as CSV\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: iterable.exportexperimentmetrics\n      with:\n        experimentId: tools.experimentId\n        campaignId: tools.campaignId\n      inputParameters:\n      - name: experimentId\n        type: array\n        description: One or more experiment\
  \ IDs to export metrics for\n      - name: campaignId\n        type: array\n        description: One or more campaign IDs to export metrics for\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ITERABLE_TOKEN: ITERABLE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/iterable/refs/heads/main/capabilities/iterable-capability.yaml
tags:
- Iterable
- API
tools:
- description: Export data as JSON
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: exportdatajson
- description: Export data as CSV
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: exportdatacsv
- description: Export events for a specific user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: exportuserevents
- description: Export experiment metrics as CSV
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: exportexperimentmetrics
---
