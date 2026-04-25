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
- create calculated metric
- get segment
- create a data repair job to delete or transform ingested data.
- dimension discovery.
- single calculated metric operations.
- create a new calculated metric.
- web analytics
- reporting
- update calculated metric
- list report suites.
- get details for a specific report suite.
- customer intelligence
- create annotation
- report suite management.
- get server call estimate
- calculated metric management.
- business intelligence
- list metrics for a report suite.
- get report suite details.
- create a segment.
- delete calculated metric
- permanently delete a segment.
- list repair jobs.
- analytics
- create repair job
- list segments
- marketing
- analytics reporting.
- list all tags used on analytics components.
- get repair job status.
- calculated metrics
- update a segment.
- metric discovery.
- list calculated metrics
- analysis
- retrieve a specific segment by id.
- run an analytics report.
- get repair job
- data repair jobs.
- create a repair job.
- estimate repair scope.
- list tags
- estimate the scope and cost of a data repair job.
- permanently delete a calculated metric.
- list all metrics available in a report suite.
- list repair jobs
- list analytics segments.
- single report suite.
- update segment
- list segments.
- get a calculated metric.
- single segment operations.
- run an adobe analytics report with metrics, dimensions, and date filters.
- create an annotation for a report suite date range.
- list analytics annotations.
- annotation management.
- retrieve a calculated metric by id.
- create segment
- digital marketing
- list calculated metrics.
- get calculated metric
- list recent data repair jobs for a report suite.
- list annotations.
- create a calculated metric.
- list accessible report suites.
- delete a calculated metric.
- list all dimensions available in a report suite.
- data governance
- data repair cost estimation.
- get a segment.
- list date ranges
- segments
- list dimensions
- create a new analytics segment.
- list report suites
- adobe
- single repair job.
- get status of a specific data repair job.
- create an annotation.
- run report
- segment management.
- update an existing segment.
- list saved date ranges.
- adobe analytics
- get report suite
- list dimensions for a report suite.
- delete segment
- update a calculated metric.
- list annotations
- list metrics
- delete a segment.
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
