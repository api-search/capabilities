---
categories:
- analytics
consumed_apis:
- adobe-bulk-data-insertion
- adobe-analytics
description: Unified workflow for server-side data collection and ingestion combining Bulk Data Insertion for high-volume event uploads with the Analytics API for report suite discovery and validation. Used by data engineers and implementation teams.
layout: capability
name: Adobe Analytics Data Collection
operations:
- description: Upload a batch events file.
  method: POST
  name: upload-events
  path: /v1/events
- description: Validate a batch events file without ingesting.
  method: POST
  name: validate-events
  path: /v1/events/validate
- description: List report suites to identify collection targets.
  method: GET
  name: list-report-suites
  path: /v1/report-suites
- description: Get report suite details.
  method: GET
  name: get-report-suite
  path: /v1/report-suites/{rsid}
- description: List metrics to validate event data mapping.
  method: GET
  name: list-metrics
  path: /v1/metrics
- description: List dimensions to validate event data mapping.
  method: GET
  name: list-dimensions
  path: /v1/dimensions
personas: []
provider_name: Adobe Analytics
provider_slug: adobe-analytics
search_terms:
- upload a batch events file.
- adobe
- validate a batch events file without ingesting data.
- list available metrics to validate event data mapping.
- web analytics
- list metrics to validate event data mapping.
- list available dimensions to validate event data mapping.
- marketing
- adobe analytics
- business intelligence
- get report suite
- analytics
- validate event files.
- list report suites to identify data collection targets.
- upload events
- upload a gzip-compressed csv file of batched analytics event data.
- server side
- report suite details.
- list report suites
- get details for a report suite to verify collection configuration.
- data collection
- validate a batch events file without ingesting.
- validate events
- digital marketing
- list metrics
- report suite discovery for data collection targeting.
- dimension discovery for event mapping.
- bulk data insertion
- batch event upload.
- events
- list dimensions
- get report suite details.
- list dimensions to validate event data mapping.
- list report suites to identify collection targets.
- metric discovery for event mapping.
- customer intelligence
slug: data-collection
source_filename: data-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Adobe Analytics Data Collection\"\n  description: \"Unified workflow for server-side data collection and ingestion combining Bulk Data Insertion for high-volume event uploads with the Analytics API for report suite discovery and validation. Used by data engineers and implementation teams.\"\n  tags:\n    - Adobe Analytics\n    - Data Collection\n    - Bulk Data Insertion\n    - Events\n    - Server Side\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ADOBE_ANALYTICS_BEARER_TOKEN: ADOBE_ANALYTICS_BEARER_TOKEN\n      ADOBE_ANALYTICS_API_KEY: ADOBE_ANALYTICS_API_KEY\n      ADOBE_ANALYTICS_GLOBAL_COMPANY_ID: ADOBE_ANALYTICS_GLOBAL_COMPANY_ID\n\ncapability:\n  consumes:\n    - import: adobe-bulk-data-insertion\n      location: ./shared/bulk-data-insertion.yaml\n    - import: adobe-analytics\n      location: ./shared/analytics-api.yaml\n\n  exposes:\n    - type: rest\n      port:\
  \ 8081\n      namespace: adobe-data-collection-api\n      description: \"Unified REST API for Adobe Analytics server-side data collection and ingestion.\"\n      resources:\n        - path: /v1/events\n          name: events\n          description: \"Batch event upload.\"\n          operations:\n            - method: POST\n              name: upload-events\n              description: \"Upload a batch events file.\"\n              call: \"adobe-bulk-data-insertion.upload-events\"\n              with:\n                x-adobe-vgid: \"rest.x-adobe-vgid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events/validate\n          name: event-validation\n          description: \"Validate event files.\"\n          operations:\n            - method: POST\n              name: validate-events\n              description: \"Validate a batch events file without ingesting.\"\n              call: \"adobe-bulk-data-insertion.validate-events\"\
  \n              with:\n                x-adobe-vgid: \"rest.x-adobe-vgid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/report-suites\n          name: report-suites\n          description: \"Report suite discovery for data collection targeting.\"\n          operations:\n            - method: GET\n              name: list-report-suites\n              description: \"List report suites to identify collection targets.\"\n              call: \"adobe-analytics.list-report-suites\"\n              with:\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/report-suites/{rsid}\n          name: report-suite-detail\n          description: \"Report suite details.\"\n          operations:\n            - method: GET\n              name: get-report-suite\n              description: \"Get report suite details.\"\n       \
  \       call: \"adobe-analytics.get-report-suite\"\n              with:\n                rsid: \"rest.rsid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics\n          name: metrics\n          description: \"Metric discovery for event mapping.\"\n          operations:\n            - method: GET\n              name: list-metrics\n              description: \"List metrics to validate event data mapping.\"\n              call: \"adobe-analytics.list-metrics\"\n              with:\n                rsid: \"rest.rsid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/dimensions\n          name: dimensions\n          description: \"Dimension discovery for event mapping.\"\n          operations:\n            - method: GET\n              name: list-dimensions\n              description: \"List dimensions to validate event data mapping.\"\n    \
  \          call: \"adobe-analytics.list-dimensions\"\n              with:\n                rsid: \"rest.rsid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: adobe-data-collection-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Adobe Analytics data collection and ingestion workflows.\"\n      tools:\n        - name: upload-events\n          description: \"Upload a gzip-compressed CSV file of batched Analytics event data.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"adobe-bulk-data-insertion.upload-events\"\n          with:\n            x-adobe-vgid: \"tools.visitor_group_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: validate-events\n          description: \"Validate a batch events file without ingesting data.\"\n          hints:\n     \
  \       readOnly: true\n            idempotent: true\n          call: \"adobe-bulk-data-insertion.validate-events\"\n          with:\n            x-adobe-vgid: \"tools.visitor_group_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-report-suites\n          description: \"List report suites to identify data collection targets.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"adobe-analytics.list-report-suites\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-report-suite\n          description: \"Get details for a report suite to verify collection configuration.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"adobe-analytics.get-report-suite\"\n          with:\n            rsid: \"tools.rsid\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-metrics\n          description: \"List available metrics to validate event data mapping.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"adobe-analytics.list-metrics\"\n          with:\n            rsid: \"tools.rsid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-dimensions\n          description: \"List available dimensions to validate event data mapping.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"adobe-analytics.list-dimensions\"\n          with:\n            rsid: \"tools.rsid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-analytics/refs/heads/main/capabilities/data-collection.yaml
tags:
- Adobe Analytics
- Data Collection
- Bulk Data Insertion
- Events
- Server Side
tools:
- description: Upload a gzip-compressed CSV file of batched Analytics event data.
  hints:
    idempotent: false
    readOnly: false
  name: upload-events
- description: Validate a batch events file without ingesting data.
  hints:
    idempotent: true
    readOnly: true
  name: validate-events
- description: List report suites to identify data collection targets.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-report-suites
- description: Get details for a report suite to verify collection configuration.
  hints:
    idempotent: true
    readOnly: true
  name: get-report-suite
- description: List available metrics to validate event data mapping.
  hints:
    idempotent: true
    readOnly: true
  name: list-metrics
- description: List available dimensions to validate event data mapping.
  hints:
    idempotent: true
    readOnly: true
  name: list-dimensions
---
