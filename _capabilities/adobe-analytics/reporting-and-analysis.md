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
- list calculated metrics.
- list accessible report suites.
- segment management.
- delete segment
- retrieve a specific segment by id.
- list segments.
- marketing
- estimate repair scope.
- list date ranges
- list report suites.
- delete a calculated metric.
- single report suite.
- update a segment.
- list annotations
- list analytics annotations.
- create repair job
- permanently delete a segment.
- adobe
- create a new calculated metric.
- create a data repair job to delete or transform ingested data.
- update a calculated metric.
- web analytics
- create a repair job.
- run an adobe analytics report with metrics, dimensions, and date filters.
- list metrics for a report suite.
- list repair jobs
- analytics reporting.
- list saved date ranges.
- retrieve a calculated metric by id.
- data governance
- run report
- digital marketing
- get report suite details.
- get a segment.
- update calculated metric
- get segment
- data repair jobs.
- create annotation
- list all dimensions available in a report suite.
- list all metrics available in a report suite.
- list recent data repair jobs for a report suite.
- analytics
- list calculated metrics
- get calculated metric
- create a calculated metric.
- get details for a specific report suite.
- list metrics
- calculated metric management.
- customer intelligence
- create calculated metric
- run an analytics report.
- get report suite
- delete a segment.
- data repair cost estimation.
- list report suites
- list annotations.
- report suite management.
- annotation management.
- get a calculated metric.
- get repair job status.
- list all tags used on analytics components.
- create an annotation for a report suite date range.
- update an existing segment.
- create a new analytics segment.
- single repair job.
- get server call estimate
- list tags
- adobe analytics
- analysis
- list analytics segments.
- create segment
- estimate the scope and cost of a data repair job.
- reporting
- single calculated metric operations.
- single segment operations.
- business intelligence
- segments
- dimension discovery.
- permanently delete a calculated metric.
- list dimensions for a report suite.
- delete calculated metric
- list repair jobs.
- list segments
- get status of a specific data repair job.
- update segment
- list dimensions
- metric discovery.
- get repair job
- calculated metrics
- create an annotation.
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
