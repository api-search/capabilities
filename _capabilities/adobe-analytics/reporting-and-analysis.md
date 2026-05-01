---
categories:
- analytics
consumed_apis:
- adobe-analytics
- adobe-data-repair
description: Unified workflow for analytics reporting, component management, and data governance combining the Analytics 2.0 API for reports, segments, calculated metrics, and the Data Repair API for data quality management. Used by digital analysts, marketing analysts, and data governance teams.
layout: capability
name: Adobe Analytics Reporting And Analysis
operations:
- description: Run an analytics report.
  method: POST
  name: run-report
  path: /v1/reports
- description: List segments.
  method: GET
  name: list-segments
  path: /v1/segments
- description: Create a segment.
  method: POST
  name: create-segment
  path: /v1/segments
- description: Get a segment.
  method: GET
  name: get-segment
  path: /v1/segments/{segmentId}
- description: Update a segment.
  method: PUT
  name: update-segment
  path: /v1/segments/{segmentId}
- description: Delete a segment.
  method: DELETE
  name: delete-segment
  path: /v1/segments/{segmentId}
- description: List calculated metrics.
  method: GET
  name: list-calculated-metrics
  path: /v1/calculated-metrics
- description: Create a calculated metric.
  method: POST
  name: create-calculated-metric
  path: /v1/calculated-metrics
- description: Get a calculated metric.
  method: GET
  name: get-calculated-metric
  path: /v1/calculated-metrics/{calculatedMetricId}
- description: Update a calculated metric.
  method: PUT
  name: update-calculated-metric
  path: /v1/calculated-metrics/{calculatedMetricId}
- description: Delete a calculated metric.
  method: DELETE
  name: delete-calculated-metric
  path: /v1/calculated-metrics/{calculatedMetricId}
- description: List metrics for a report suite.
  method: GET
  name: list-metrics
  path: /v1/metrics
- description: List dimensions for a report suite.
  method: GET
  name: list-dimensions
  path: /v1/dimensions
- description: List report suites.
  method: GET
  name: list-report-suites
  path: /v1/report-suites
- description: Get report suite details.
  method: GET
  name: get-report-suite
  path: /v1/report-suites/{rsid}
- description: List annotations.
  method: GET
  name: list-annotations
  path: /v1/annotations
- description: Create an annotation.
  method: POST
  name: create-annotation
  path: /v1/annotations
- description: Estimate repair scope.
  method: GET
  name: get-server-call-estimate
  path: /v1/report-suites/{rsid}/server-call-estimate
- description: List repair jobs.
  method: GET
  name: list-repair-jobs
  path: /v1/report-suites/{rsid}/repair-jobs
- description: Create a repair job.
  method: POST
  name: create-repair-job
  path: /v1/report-suites/{rsid}/repair-jobs
- description: Get repair job status.
  method: GET
  name: get-repair-job
  path: /v1/report-suites/{rsid}/repair-jobs/{jobId}
personas: []
provider_name: Adobe Analytics
provider_slug: adobe-analytics
search_terms:
- get repair job
- get report suite details.
- get server call estimate
- data repair cost estimation.
- marketing
- create a new calculated metric.
- list report suites
- update segment
- update calculated metric
- update an existing segment.
- digital marketing
- adobe
- delete a calculated metric.
- get repair job status.
- update a calculated metric.
- delete calculated metric
- analytics
- estimate repair scope.
- get a calculated metric.
- list annotations.
- list metrics
- list analytics segments.
- data repair jobs.
- list repair jobs.
- get status of a specific data repair job.
- create an annotation.
- create segment
- report suite management.
- data governance
- list accessible report suites.
- permanently delete a segment.
- create a repair job.
- run report
- list calculated metrics.
- list recent data repair jobs for a report suite.
- list report suites.
- single report suite.
- list date ranges
- create a segment.
- create a calculated metric.
- permanently delete a calculated metric.
- delete segment
- adobe analytics
- retrieve a calculated metric by id.
- estimate the scope and cost of a data repair job.
- web analytics
- create a new analytics segment.
- run an analytics report.
- metric discovery.
- create annotation
- create an annotation for a report suite date range.
- customer intelligence
- segments
- list all metrics available in a report suite.
- business intelligence
- list tags
- get details for a specific report suite.
- single segment operations.
- list segments.
- annotation management.
- list analytics annotations.
- dimension discovery.
- calculated metric management.
- single calculated metric operations.
- list metrics for a report suite.
- list segments
- list saved date ranges.
- get calculated metric
- calculated metrics
- get report suite
- delete a segment.
- list dimensions for a report suite.
- list all tags used on analytics components.
- create calculated metric
- get segment
- single repair job.
- list all dimensions available in a report suite.
- get a segment.
- reporting
- retrieve a specific segment by id.
- list dimensions
- update a segment.
- segment management.
- run an adobe analytics report with metrics, dimensions, and date filters.
- analysis
- create repair job
- create a data repair job to delete or transform ingested data.
- list calculated metrics
- list annotations
- list repair jobs
- analytics reporting.
slug: reporting-and-analysis
source_filename: reporting-and-analysis.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Adobe Analytics Reporting And Analysis\"\n  description: \"Unified workflow for analytics reporting, component management, and data governance combining the Analytics 2.0 API for reports, segments, calculated metrics, and the Data Repair API for data quality management. Used by digital analysts, marketing analysts, and data governance teams.\"\n  tags:\n    - Adobe Analytics\n    - Reporting\n    - Analysis\n    - Segments\n    - Calculated Metrics\n    - Data Governance\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ADOBE_ANALYTICS_BEARER_TOKEN: ADOBE_ANALYTICS_BEARER_TOKEN\n      ADOBE_ANALYTICS_API_KEY: ADOBE_ANALYTICS_API_KEY\n      ADOBE_ANALYTICS_GLOBAL_COMPANY_ID: ADOBE_ANALYTICS_GLOBAL_COMPANY_ID\n\ncapability:\n  consumes:\n    - import: adobe-analytics\n      location: ./shared/analytics-api.yaml\n    - import: adobe-data-repair\n      location: ./shared/data-repair.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: adobe-reporting-analysis-api\n      description: \"Unified REST API for Adobe Analytics reporting, component management, and data governance.\"\n      resources:\n        - path: /v1/reports\n          name: reports\n          description: \"Analytics reporting.\"\n          operations:\n            - method: POST\n              name: run-report\n              description: \"Run an analytics report.\"\n              call: \"adobe-analytics.run-report\"\n              with:\n                rsid: \"rest.rsid\"\n                globalFilters: \"rest.globalFilters\"\n                metricContainer: \"rest.metricContainer\"\n                dimension: \"rest.dimension\"\n                settings: \"rest.settings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/segments\n          name: segments\n          description: \"Segment management.\"\n      \
  \    operations:\n            - method: GET\n              name: list-segments\n              description: \"List segments.\"\n              call: \"adobe-analytics.list-segments\"\n              with:\n                limit: \"rest.limit\"\n                page: \"rest.page\"\n                includeType: \"rest.includeType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-segment\n              description: \"Create a segment.\"\n              call: \"adobe-analytics.create-segment\"\n              with:\n                name: \"rest.name\"\n                rsid: \"rest.rsid\"\n                definition: \"rest.definition\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/segments/{segmentId}\n          name: segment-detail\n          description: \"Single segment operations.\"\n          operations:\n   \
  \         - method: GET\n              name: get-segment\n              description: \"Get a segment.\"\n              call: \"adobe-analytics.get-segment\"\n              with:\n                segmentId: \"rest.segmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-segment\n              description: \"Update a segment.\"\n              call: \"adobe-analytics.update-segment\"\n              with:\n                segmentId: \"rest.segmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-segment\n              description: \"Delete a segment.\"\n              call: \"adobe-analytics.delete-segment\"\n              with:\n                segmentId: \"rest.segmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n        - path: /v1/calculated-metrics\n          name: calculated-metrics\n          description: \"Calculated metric management.\"\n          operations:\n            - method: GET\n              name: list-calculated-metrics\n              description: \"List calculated metrics.\"\n              call: \"adobe-analytics.list-calculated-metrics\"\n              with:\n                limit: \"rest.limit\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-calculated-metric\n              description: \"Create a calculated metric.\"\n              call: \"adobe-analytics.create-calculated-metric\"\n              with:\n                name: \"rest.name\"\n                rsid: \"rest.rsid\"\n                definition: \"rest.definition\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n   \
  \               mapping: \"$.\"\n        - path: /v1/calculated-metrics/{calculatedMetricId}\n          name: calculated-metric-detail\n          description: \"Single calculated metric operations.\"\n          operations:\n            - method: GET\n              name: get-calculated-metric\n              description: \"Get a calculated metric.\"\n              call: \"adobe-analytics.get-calculated-metric\"\n              with:\n                calculatedMetricId: \"rest.calculatedMetricId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-calculated-metric\n              description: \"Update a calculated metric.\"\n              call: \"adobe-analytics.update-calculated-metric\"\n              with:\n                calculatedMetricId: \"rest.calculatedMetricId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method:\
  \ DELETE\n              name: delete-calculated-metric\n              description: \"Delete a calculated metric.\"\n              call: \"adobe-analytics.delete-calculated-metric\"\n              with:\n                calculatedMetricId: \"rest.calculatedMetricId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics\n          name: metrics\n          description: \"Metric discovery.\"\n          operations:\n            - method: GET\n              name: list-metrics\n              description: \"List metrics for a report suite.\"\n              call: \"adobe-analytics.list-metrics\"\n              with:\n                rsid: \"rest.rsid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/dimensions\n          name: dimensions\n          description: \"Dimension discovery.\"\n          operations:\n            - method: GET\n           \
  \   name: list-dimensions\n              description: \"List dimensions for a report suite.\"\n              call: \"adobe-analytics.list-dimensions\"\n              with:\n                rsid: \"rest.rsid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/report-suites\n          name: report-suites\n          description: \"Report suite management.\"\n          operations:\n            - method: GET\n              name: list-report-suites\n              description: \"List report suites.\"\n              call: \"adobe-analytics.list-report-suites\"\n              with:\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/report-suites/{rsid}\n          name: report-suite-detail\n          description: \"Single report suite.\"\n          operations:\n            - method: GET\n              name: get-report-suite\n\
  \              description: \"Get report suite details.\"\n              call: \"adobe-analytics.get-report-suite\"\n              with:\n                rsid: \"rest.rsid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/annotations\n          name: annotations\n          description: \"Annotation management.\"\n          operations:\n            - method: GET\n              name: list-annotations\n              description: \"List annotations.\"\n              call: \"adobe-analytics.list-annotations\"\n              with:\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-annotation\n              description: \"Create an annotation.\"\n              call: \"adobe-analytics.create-annotation\"\n              with:\n                name: \"rest.name\"\n                dateRange:\
  \ \"rest.dateRange\"\n                rsids: \"rest.rsids\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/report-suites/{rsid}/server-call-estimate\n          name: server-call-estimate\n          description: \"Data repair cost estimation.\"\n          operations:\n            - method: GET\n              name: get-server-call-estimate\n              description: \"Estimate repair scope.\"\n              call: \"adobe-data-repair.get-server-call-estimate\"\n              with:\n                rsid: \"rest.rsid\"\n                dateRangeStart: \"rest.dateRangeStart\"\n                dateRangeEnd: \"rest.dateRangeEnd\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/report-suites/{rsid}/repair-jobs\n          name: repair-jobs\n          description: \"Data repair jobs.\"\n          operations:\n            - method: GET\n              name:\
  \ list-repair-jobs\n              description: \"List repair jobs.\"\n              call: \"adobe-data-repair.list-repair-jobs\"\n              with:\n                rsid: \"rest.rsid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-repair-job\n              description: \"Create a repair job.\"\n              call: \"adobe-data-repair.create-repair-job\"\n              with:\n                rsid: \"rest.rsid\"\n                validationToken: \"rest.validationToken\"\n                variables: \"rest.variables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/report-suites/{rsid}/repair-jobs/{jobId}\n          name: repair-job-detail\n          description: \"Single repair job.\"\n          operations:\n            - method: GET\n              name: get-repair-job\n              description: \"Get repair\
  \ job status.\"\n              call: \"adobe-data-repair.get-repair-job\"\n              with:\n                rsid: \"rest.rsid\"\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: adobe-reporting-analysis-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Adobe Analytics reporting, analysis, and data governance.\"\n      tools:\n        - name: run-report\n          description: \"Run an Adobe Analytics report with metrics, dimensions, and date filters.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"adobe-analytics.run-report\"\n          with:\n            rsid: \"tools.rsid\"\n            globalFilters: \"tools.globalFilters\"\n            metricContainer: \"tools.metricContainer\"\n            dimension: \"tools.dimension\"\n           \
  \ settings: \"tools.settings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-segments\n          description: \"List analytics segments.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"adobe-analytics.list-segments\"\n          with:\n            limit: \"tools.limit\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-segment\n          description: \"Create a new analytics segment.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"adobe-analytics.create-segment\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n            rsid: \"tools.rsid\"\n            definition: \"tools.definition\"\n          outputParameters:\n            - type: object\n      \
  \        mapping: \"$.\"\n        - name: get-segment\n          description: \"Retrieve a specific segment by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"adobe-analytics.get-segment\"\n          with:\n            segmentId: \"tools.segmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-segment\n          description: \"Update an existing segment.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"adobe-analytics.update-segment\"\n          with:\n            segmentId: \"tools.segmentId\"\n            name: \"tools.name\"\n            definition: \"tools.definition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-segment\n          description: \"Permanently delete a segment.\"\n          hints:\n            destructive: true\n            idempotent:\
  \ true\n          call: \"adobe-analytics.delete-segment\"\n          with:\n            segmentId: \"tools.segmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-calculated-metrics\n          description: \"List calculated metrics.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"adobe-analytics.list-calculated-metrics\"\n          with:\n            limit: \"tools.limit\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-calculated-metric\n          description: \"Create a new calculated metric.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"adobe-analytics.create-calculated-metric\"\n          with:\n            name: \"tools.name\"\n            rsid: \"tools.rsid\"\n            definition: \"tools.definition\"\
  \n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-calculated-metric\n          description: \"Retrieve a calculated metric by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"adobe-analytics.get-calculated-metric\"\n          with:\n            calculatedMetricId: \"tools.calculatedMetricId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-calculated-metric\n          description: \"Update a calculated metric.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"adobe-analytics.update-calculated-metric\"\n          with:\n            calculatedMetricId: \"tools.calculatedMetricId\"\n            name: \"tools.name\"\n            definition: \"tools.definition\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: delete-calculated-metric\n          description: \"Permanently delete a calculated metric.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"adobe-analytics.delete-calculated-metric\"\n          with:\n            calculatedMetricId: \"tools.calculatedMetricId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-metrics\n          description: \"List all metrics available in a report suite.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"adobe-analytics.list-metrics\"\n          with:\n            rsid: \"tools.rsid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-dimensions\n          description: \"List all dimensions available in a report suite.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"\
  adobe-analytics.list-dimensions\"\n          with:\n            rsid: \"tools.rsid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-report-suites\n          description: \"List accessible report suites.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"adobe-analytics.list-report-suites\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-report-suite\n          description: \"Get details for a specific report suite.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"adobe-analytics.get-report-suite\"\n          with:\n            rsid: \"tools.rsid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-annotations\n          description:\
  \ \"List analytics annotations.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"adobe-analytics.list-annotations\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-annotation\n          description: \"Create an annotation for a report suite date range.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"adobe-analytics.create-annotation\"\n          with:\n            name: \"tools.name\"\n            dateRange: \"tools.dateRange\"\n            rsids: \"tools.rsids\"\n            color: \"tools.color\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-date-ranges\n          description: \"List saved date ranges.\"\n          hints:\n            readOnly: true\n            idempotent: true\n\
  \            openWorld: true\n          call: \"adobe-analytics.list-date-ranges\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tags\n          description: \"List all tags used on analytics components.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"adobe-analytics.list-tags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-server-call-estimate\n          description: \"Estimate the scope and cost of a data repair job.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"adobe-data-repair.get-server-call-estimate\"\n          with:\n            rsid: \"tools.rsid\"\n            dateRangeStart: \"tools.dateRangeStart\"\n            dateRangeEnd: \"tools.dateRangeEnd\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-repair-jobs\n          description: \"List recent data repair jobs for a report suite.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"adobe-data-repair.list-repair-jobs\"\n          with:\n            rsid: \"tools.rsid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-repair-job\n          description: \"Create a data repair job to delete or transform ingested data.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"adobe-data-repair.create-repair-job\"\n          with:\n            rsid: \"tools.rsid\"\n            validationToken: \"tools.validationToken\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-repair-job\n\
  \          description: \"Get status of a specific data repair job.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"adobe-data-repair.get-repair-job\"\n          with:\n            rsid: \"tools.rsid\"\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-analytics/refs/heads/main/capabilities/reporting-and-analysis.yaml
tags:
- Adobe Analytics
- Reporting
- Analysis
- Segments
- Calculated Metrics
- Data Governance
tools:
- description: Run an Adobe Analytics report with metrics, dimensions, and date filters.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: run-report
- description: List analytics segments.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-segments
- description: Create a new analytics segment.
  hints:
    idempotent: false
    readOnly: false
  name: create-segment
- description: Retrieve a specific segment by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-segment
- description: Update an existing segment.
  hints:
    idempotent: true
    readOnly: false
  name: update-segment
- description: Permanently delete a segment.
  hints:
    destructive: true
    idempotent: true
  name: delete-segment
- description: List calculated metrics.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-calculated-metrics
- description: Create a new calculated metric.
  hints:
    idempotent: false
    readOnly: false
  name: create-calculated-metric
- description: Retrieve a calculated metric by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-calculated-metric
- description: Update a calculated metric.
  hints:
    idempotent: true
    readOnly: false
  name: update-calculated-metric
- description: Permanently delete a calculated metric.
  hints:
    destructive: true
    idempotent: true
  name: delete-calculated-metric
- description: List all metrics available in a report suite.
  hints:
    idempotent: true
    readOnly: true
  name: list-metrics
- description: List all dimensions available in a report suite.
  hints:
    idempotent: true
    readOnly: true
  name: list-dimensions
- description: List accessible report suites.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-report-suites
- description: Get details for a specific report suite.
  hints:
    idempotent: true
    readOnly: true
  name: get-report-suite
- description: List analytics annotations.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-annotations
- description: Create an annotation for a report suite date range.
  hints:
    idempotent: false
    readOnly: false
  name: create-annotation
- description: List saved date ranges.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-date-ranges
- description: List all tags used on analytics components.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-tags
- description: Estimate the scope and cost of a data repair job.
  hints:
    idempotent: true
    readOnly: true
  name: get-server-call-estimate
- description: List recent data repair jobs for a report suite.
  hints:
    idempotent: true
    readOnly: true
  name: list-repair-jobs
- description: Create a data repair job to delete or transform ingested data.
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: create-repair-job
- description: Get status of a specific data repair job.
  hints:
    idempotent: true
    readOnly: true
  name: get-repair-job
---
