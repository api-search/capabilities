---
categories:
- analytics
consumed_apis: []
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
- get details for a report suite to verify collection configuration.
- get report suite details.
- validate a batch events file without ingesting.
- server side
- digital marketing
- customer intelligence
- analytics
- list metrics to validate event data mapping.
- list available dimensions to validate event data mapping.
- upload events
- bulk data insertion
- marketing
- list report suites to identify data collection targets.
- data collection
- batch event upload.
- list report suites
- list available metrics to validate event data mapping.
- events
- web analytics
- list dimensions to validate event data mapping.
- list report suites to identify collection targets.
- upload a gzip-compressed csv file of batched analytics event data.
- report suite details.
- validate events
- list metrics
- list dimensions
- business intelligence
- adobe
- validate event files.
- validate a batch events file without ingesting data.
- dimension discovery for event mapping.
- report suite discovery for data collection targeting.
- metric discovery for event mapping.
- get report suite
- adobe analytics
slug: data-collection
source_filename: data-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Analytics Data Collection\n  description: Unified workflow for server-side data collection and ingestion combining Bulk Data Insertion for high-volume\n    event uploads with the Analytics API for report suite discovery and validation. Used by data engineers and implementation\n    teams.\n  tags:\n  - Adobe Analytics\n  - Data Collection\n  - Bulk Data Insertion\n  - Events\n  - Server Side\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ADOBE_ANALYTICS_BEARER_TOKEN: ADOBE_ANALYTICS_BEARER_TOKEN\n    ADOBE_ANALYTICS_API_KEY: ADOBE_ANALYTICS_API_KEY\n    ADOBE_ANALYTICS_GLOBAL_COMPANY_ID: ADOBE_ANALYTICS_GLOBAL_COMPANY_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: adobe-bulk-data-insertion\n    baseUri: https://analytics-collection.adobe.io/aa/collect/v1\n    description: Adobe Analytics Bulk Data Insertion API for high-volume server-side data collection.\n    authentication:\n\
  \      type: bearer\n      token: '{{ADOBE_ANALYTICS_BEARER_TOKEN}}'\n    resources:\n    - name: events\n      path: /events\n      description: Batch event upload and validation.\n      operations:\n      - name: upload-events\n        method: POST\n        description: Upload a gzip-compressed CSV file containing batched Analytics event data.\n        inputParameters:\n        - name: x-adobe-vgid\n          in: header\n          type: string\n          required: true\n          description: Visitor group ID for correct visitor stitching.\n        - name: x-adobe-idempotency-key\n          in: header\n          type: string\n          required: false\n          description: Unique identifier for deduplication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: validate-events\n        method: POST\n        path: /validate\n        description: Validate a gzip-compressed CSV events file without\
  \ ingesting data.\n        inputParameters:\n        - name: x-adobe-vgid\n          in: header\n          type: string\n          required: true\n          description: Visitor group ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: adobe-analytics\n    baseUri: https://analytics.adobe.io/api/{{ADOBE_ANALYTICS_GLOBAL_COMPANY_ID}}\n    description: Adobe Analytics 2.0 API for reporting, segmentation, and component management.\n    authentication:\n      type: bearer\n      token: '{{ADOBE_ANALYTICS_BEARER_TOKEN}}'\n    resources:\n    - name: reports\n      path: /reports\n      description: Analytics reporting operations.\n      operations:\n      - name: run-report\n        method: POST\n        description: Run an analytics report with specified metrics, dimensions, and filters.\n        body:\n          type: json\n          data:\n            rsid: '{{tools.rsid}}'\n  \
  \          globalFilters: '{{tools.globalFilters}}'\n            metricContainer: '{{tools.metricContainer}}'\n            dimension: '{{tools.dimension}}'\n            settings: '{{tools.settings}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: segments\n      path: /segments\n      description: Segment management operations.\n      operations:\n      - name: list-segments\n        method: GET\n        description: List analytics segments with filtering and pagination.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results per page (max 1000).\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number (zero-indexed).\n        - name: expansion\n          in: query\n          type: string\n          required: false\n\
  \          description: Additional fields to include.\n        - name: includeType\n          in: query\n          type: string\n          required: false\n          description: Controls which segments are returned (all, shared, templates).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-segment\n        method: POST\n        description: Create a new analytics segment.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            rsid: '{{tools.rsid}}'\n            definition: '{{tools.definition}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-segment\n        method: GET\n        path: /{segmentId}\n        description: Retrieve a specific segment.\n        inputParameters:\n        - name: segmentId\n\
  \          in: path\n          type: string\n          required: true\n          description: The segment ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-segment\n        method: PUT\n        path: /{segmentId}\n        description: Update an existing segment.\n        inputParameters:\n        - name: segmentId\n          in: path\n          type: string\n          required: true\n          description: The segment ID.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            rsid: '{{tools.rsid}}'\n            definition: '{{tools.definition}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-segment\n        method: DELETE\n        path: /{segmentId}\n        description: Permanently delete\
  \ a segment.\n        inputParameters:\n        - name: segmentId\n          in: path\n          type: string\n          required: true\n          description: The segment ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: calculated-metrics\n      path: /calculatedmetrics\n      description: Calculated metric management.\n      operations:\n      - name: list-calculated-metrics\n        method: GET\n        description: List calculated metrics.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results per page.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: expansion\n          in: query\n          type: string\n          required: false\n          description: Additional fields to include.\n\
  \        - name: includeType\n          in: query\n          type: string\n          required: false\n          description: Filter type (all, shared, templates).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-calculated-metric\n        method: POST\n        description: Create a new calculated metric.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            rsid: '{{tools.rsid}}'\n            definition: '{{tools.definition}}'\n            type: '{{tools.type}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-calculated-metric\n        method: GET\n        path: /{calculatedMetricId}\n        description: Retrieve a specific calculated metric.\n        inputParameters:\n        - name: calculatedMetricId\n\
  \          in: path\n          type: string\n          required: true\n          description: The calculated metric ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-calculated-metric\n        method: PUT\n        path: /{calculatedMetricId}\n        description: Update an existing calculated metric.\n        inputParameters:\n        - name: calculatedMetricId\n          in: path\n          type: string\n          required: true\n          description: The calculated metric ID.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            rsid: '{{tools.rsid}}'\n            definition: '{{tools.definition}}'\n            type: '{{tools.type}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-calculated-metric\n\
  \        method: DELETE\n        path: /{calculatedMetricId}\n        description: Permanently delete a calculated metric.\n        inputParameters:\n        - name: calculatedMetricId\n          in: path\n          type: string\n          required: true\n          description: The calculated metric ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /metrics\n      description: Metric discovery.\n      operations:\n      - name: list-metrics\n        method: GET\n        description: List all available metrics in a report suite.\n        inputParameters:\n        - name: rsid\n          in: query\n          type: string\n          required: true\n          description: The report suite ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dimensions\n      path: /dimensions\n      description:\
  \ Dimension discovery.\n      operations:\n      - name: list-dimensions\n        method: GET\n        description: List all available dimensions in a report suite.\n        inputParameters:\n        - name: rsid\n          in: query\n          type: string\n          required: true\n          description: The report suite ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: report-suites\n      path: /reportsuites/collections/suites\n      description: Report suite operations.\n      operations:\n      - name: list-report-suites\n        method: GET\n        description: List accessible report suites.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results per page.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-report-suite\n        method: GET\n        path: /{rsid}\n        description: Get a specific report suite.\n        inputParameters:\n        - name: rsid\n          in: path\n          type: string\n          required: true\n          description: The report suite ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: annotations\n      path: /annotations\n      description: Annotation management.\n      operations:\n      - name: list-annotations\n        method: GET\n        description: List all annotations.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: create-annotation\n        method: POST\n        description: Create a new annotation.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            dateRange: '{{tools.dateRange}}'\n            rsids: '{{tools.rsids}}'\n            color: '{{tools.color}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: date-ranges\n      path: /dateranges\n      description: Saved date range operations.\n      operations:\n      - name: list-date-ranges\n        method: GET\n        description: List saved date ranges.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return.\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /componentmetadata/tags\n      description: Component tag operations.\n      operations:\n      - name: list-tags\n        method: GET\n        description: List all tags used on analytics components.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: adobe-data-collection-api\n    description: Unified REST API for Adobe Analytics server-side data collection and ingestion.\n    resources:\n    - path: /v1/events\n      name: events\n      description: Batch event upload.\n      operations:\n      - method: POST\n        name: upload-events\n        description: Upload a batch events file.\n        call: adobe-bulk-data-insertion.upload-events\n        with:\n          x-adobe-vgid: rest.x-adobe-vgid\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n    - path: /v1/events/validate\n      name: event-validation\n      description: Validate event files.\n      operations:\n      - method: POST\n        name: validate-events\n        description: Validate a batch events file without ingesting.\n        call: adobe-bulk-data-insertion.validate-events\n        with:\n          x-adobe-vgid: rest.x-adobe-vgid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/report-suites\n      name: report-suites\n      description: Report suite discovery for data collection targeting.\n      operations:\n      - method: GET\n        name: list-report-suites\n        description: List report suites to identify collection targets.\n        call: adobe-analytics.list-report-suites\n        with:\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/report-suites/{rsid}\n      name: report-suite-detail\n      description: Report suite\
  \ details.\n      operations:\n      - method: GET\n        name: get-report-suite\n        description: Get report suite details.\n        call: adobe-analytics.get-report-suite\n        with:\n          rsid: rest.rsid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics\n      name: metrics\n      description: Metric discovery for event mapping.\n      operations:\n      - method: GET\n        name: list-metrics\n        description: List metrics to validate event data mapping.\n        call: adobe-analytics.list-metrics\n        with:\n          rsid: rest.rsid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dimensions\n      name: dimensions\n      description: Dimension discovery for event mapping.\n      operations:\n      - method: GET\n        name: list-dimensions\n        description: List dimensions to validate event data mapping.\n        call: adobe-analytics.list-dimensions\n       \
  \ with:\n          rsid: rest.rsid\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: adobe-data-collection-mcp\n    transport: http\n    description: MCP server for AI-assisted Adobe Analytics data collection and ingestion workflows.\n    tools:\n    - name: upload-events\n      description: Upload a gzip-compressed CSV file of batched Analytics event data.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: adobe-bulk-data-insertion.upload-events\n      with:\n        x-adobe-vgid: tools.visitor_group_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validate-events\n      description: Validate a batch events file without ingesting data.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: adobe-bulk-data-insertion.validate-events\n      with:\n        x-adobe-vgid: tools.visitor_group_id\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-report-suites\n      description: List report suites to identify data collection targets.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: adobe-analytics.list-report-suites\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-report-suite\n      description: Get details for a report suite to verify collection configuration.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: adobe-analytics.get-report-suite\n      with:\n        rsid: tools.rsid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-metrics\n      description: List available metrics to validate event data mapping.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: adobe-analytics.list-metrics\n      with:\n        rsid: tools.rsid\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-dimensions\n      description: List available dimensions to validate event data mapping.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: adobe-analytics.list-dimensions\n      with:\n        rsid: tools.rsid\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
