---
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
- list repair jobs
- calculated metrics
- create a new calculated metric.
- metric discovery.
- reporting
- get repair job
- single segment operations.
- create an annotation.
- update calculated metric
- dimension discovery.
- update a segment.
- list report suites
- retrieve a specific segment by id.
- permanently delete a calculated metric.
- delete calculated metric
- get status of a specific data repair job.
- run report
- list analytics annotations.
- get a segment.
- create calculated metric
- get a calculated metric.
- list dimensions
- customer intelligence
- list metrics for a report suite.
- adobe analytics
- permanently delete a segment.
- data repair cost estimation.
- get calculated metric
- update a calculated metric.
- delete segment
- list dimensions for a report suite.
- list tags
- single calculated metric operations.
- get repair job status.
- list all dimensions available in a report suite.
- create a data repair job to delete or transform ingested data.
- list accessible report suites.
- create a calculated metric.
- update an existing segment.
- get details for a specific report suite.
- create a segment.
- list annotations
- list annotations.
- business intelligence
- list segments
- list date ranges
- list recent data repair jobs for a report suite.
- create annotation
- create an annotation for a report suite date range.
- list saved date ranges.
- delete a calculated metric.
- report suite management.
- retrieve a calculated metric by id.
- list all tags used on analytics components.
- list calculated metrics
- estimate repair scope.
- run an adobe analytics report with metrics, dimensions, and date filters.
- calculated metric management.
- list repair jobs.
- get report suite
- create repair job
- delete a segment.
- marketing
- list report suites.
- list segments.
- data governance
- get server call estimate
- digital marketing
- get report suite details.
- single repair job.
- analysis
- update segment
- get segment
- adobe
- analytics
- create segment
- single report suite.
- create a repair job.
- create a new analytics segment.
- list metrics
- analytics reporting.
- run an analytics report.
- data repair jobs.
- list calculated metrics.
- segments
- list all metrics available in a report suite.
- web analytics
- annotation management.
- list analytics segments.
- segment management.
- estimate the scope and cost of a data repair job.
slug: reporting-and-analysis
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
