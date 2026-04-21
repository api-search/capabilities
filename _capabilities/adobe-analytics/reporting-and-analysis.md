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
- create a new calculated metric.
- single report suite.
- list metrics for a report suite.
- get calculated metric
- estimate the scope and cost of a data repair job.
- list saved date ranges.
- get repair job status.
- dimension discovery.
- create a repair job.
- annotation management.
- adobe
- list all tags used on analytics components.
- list date ranges
- permanently delete a segment.
- list accessible report suites.
- create annotation
- delete a calculated metric.
- get server call estimate
- list all metrics available in a report suite.
- customer intelligence
- get details for a specific report suite.
- web analytics
- run report
- list repair jobs
- list repair jobs.
- list segments
- segment management.
- delete segment
- run an adobe analytics report with metrics, dimensions, and date filters.
- update calculated metric
- single repair job.
- data governance
- list calculated metrics
- retrieve a specific segment by id.
- calculated metric management.
- list all dimensions available in a report suite.
- calculated metrics
- list report suites
- report suite management.
- list report suites.
- update segment
- metric discovery.
- get segment
- list metrics
- create repair job
- adobe analytics
- get a segment.
- create a calculated metric.
- list recent data repair jobs for a report suite.
- list segments.
- single segment operations.
- analysis
- data repair cost estimation.
- list annotations
- get report suite details.
- single calculated metric operations.
- list dimensions
- analytics
- marketing
- get report suite
- create segment
- permanently delete a calculated metric.
- digital marketing
- get status of a specific data repair job.
- retrieve a calculated metric by id.
- get repair job
- list annotations.
- create an annotation for a report suite date range.
- analytics reporting.
- estimate repair scope.
- get a calculated metric.
- reporting
- list analytics annotations.
- delete a segment.
- update an existing segment.
- create an annotation.
- business intelligence
- create calculated metric
- delete calculated metric
- run an analytics report.
- list analytics segments.
- list tags
- create a data repair job to delete or transform ingested data.
- create a new analytics segment.
- list calculated metrics.
- list dimensions for a report suite.
- data repair jobs.
- update a calculated metric.
- update a segment.
- segments
- create a segment.
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
