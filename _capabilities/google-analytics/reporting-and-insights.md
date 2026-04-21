---
consumed_apis:
- ga-data-api
- ga-admin-api
description: Unified reporting workflow combining the Data API for running standard, realtime, and pivot reports with the Admin API for accessing data access audit reports. Used by data analysts, marketing teams, and BI engineers to extract insights from GA4 properties.
layout: capability
name: Google Analytics Reporting and Insights
operations:
- description: Run a customized report of GA4 event data
  method: POST
  name: run-report
  path: /v1/reports
- description: Run a realtime report showing events from the last 30 minutes
  method: POST
  name: run-realtime-report
  path: /v1/reports/realtime
- description: Run a customized pivot report
  method: POST
  name: run-pivot-report
  path: /v1/reports/pivot
- description: Run up to 5 reports in a batch
  method: POST
  name: batch-run-reports
  path: /v1/reports/batch
- description: Run up to 5 pivot reports in a batch
  method: POST
  name: batch-run-pivot-reports
  path: /v1/reports/pivot/batch
- description: Verify dimensions and metrics can be used together
  method: POST
  name: check-compatibility
  path: /v1/compatibility
- description: Report on who accessed GA4 reporting data
  method: POST
  name: run-access-report
  path: /v1/access-reports
personas:
- description: Extracts insights from GA4 data through reports and explorations.
  id: data-analyst
  name: Data Analyst
- description: Measures campaign performance, segments audiences, and tracks conversions.
  id: marketing-team
  name: Marketing Team
- description: Builds automated reporting pipelines and dashboards from GA4 data.
  id: bi-engineer
  name: BI Engineer
provider_name: Google Analytics
provider_slug: google-analytics
search_terms:
- marketing team
- data protection engineer
- extracts insights from ga4 data through reports and explorations.
- privacy officer
- implements server-side event tracking and offline data collection.
- run access report
- machine learning
- report on who accessed ga4 reporting data and when
- batch run reports
- integrates ga4 with other platforms and manages infrastructure.
- connecting ga4 with advertising, app, and measurement platforms.
- verify dimensions and metrics can be used together
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- web analytics
- run up to 5 standard reports in a single batch request
- check dimension and metric compatibility
- run realtime ga4 reports
- bi engineer
- builds automated reporting pipelines and dashboards from ga4 data.
- run pivot reports for cross-tabulation analysis
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- run up to 5 reports in a batch
- create, export, and query ga4 audience segments.
- audits data access and monitors configuration changes.
- check compatibility
- run standard, realtime, pivot, and batch reports with data access auditing.
- compliance team
- run data access audit reports
- implements privacy-compliant data handling and deletion workflows.
- marketing ops
- data analyst
- querying and analyzing ga4 event data through various report types.
- analytics administrator
- run a customized report of ga4 event data
- run report
- platform engineer
- user data deletion, access auditing, and data collection acknowledgement.
- run pivot report
- run multiple pivot reports in a single batch
- measures campaign performance, segments audiences, and tracks conversions.
- run an advanced pivot table report for cross-tabulation analysis
- report on who accessed ga4 reporting data
- data
- run standard ga4 reports
- analytics
- attribution
- manages data privacy compliance including gdpr deletion requests.
- run a customized pivot report
- run realtime report
- server-side event tracking with data stream and secret management.
- sets up and maintains ga4 accounts, properties, and configurations.
- run multiple reports in a single batch request
- run up to 5 pivot reports in a single batch request
- backend engineer
- run a realtime report showing events from the last 30 minutes
- connects advertising platforms and implements server-side tracking.
- google
- managing data privacy, deletion, and access auditing.
- run a standard ga4 report with dimensions, metrics, and date ranges
- google analytics
- segmenting and exporting user populations for analysis and activation.
- metrics
- insights
- check if dimensions and metrics are compatible for a report
- reporting
- setting up and maintaining ga4 account and property structure.
- ga4
- run up to 5 pivot reports in a batch
- batch run pivot reports
- ingesting events from servers, apps, and offline sources.
slug: reporting-and-insights
tags:
- Google Analytics
- Reporting
- Analytics
- Insights
- GA4
tools:
- description: Run a standard GA4 report with dimensions, metrics, and date ranges
  hints:
    idempotent: true
    readOnly: true
  name: run-report
- description: Run a realtime report showing events from the last 30 minutes
  hints:
    idempotent: true
    readOnly: true
  name: run-realtime-report
- description: Run an advanced pivot table report for cross-tabulation analysis
  hints:
    idempotent: true
    readOnly: true
  name: run-pivot-report
- description: Run up to 5 standard reports in a single batch request
  hints:
    idempotent: true
    readOnly: true
  name: batch-run-reports
- description: Run up to 5 pivot reports in a single batch request
  hints:
    idempotent: true
    readOnly: true
  name: batch-run-pivot-reports
- description: Check if dimensions and metrics are compatible for a report
  hints:
    idempotent: true
    readOnly: true
  name: check-compatibility
- description: Report on who accessed GA4 reporting data and when
  hints:
    idempotent: true
    readOnly: true
  name: run-access-report
---
