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
- run an advanced pivot table report for cross-tabulation analysis
- web analytics
- run up to 5 pivot reports in a single batch request
- metrics
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- google analytics
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- insights
- querying and analyzing ga4 event data through various report types.
- run pivot report
- setting up and maintaining ga4 account and property structure.
- check dimension and metric compatibility
- data analyst
- run access report
- managing data privacy, deletion, and access auditing.
- extracts insights from ga4 data through reports and explorations.
- builds automated reporting pipelines and dashboards from ga4 data.
- run realtime report
- ga4
- segmenting and exporting user populations for analysis and activation.
- analytics
- report on who accessed ga4 reporting data and when
- run up to 5 pivot reports in a batch
- analytics administrator
- platform engineer
- run multiple reports in a single batch request
- run up to 5 reports in a batch
- run data access audit reports
- run up to 5 standard reports in a single batch request
- implements privacy-compliant data handling and deletion workflows.
- manages data privacy compliance including gdpr deletion requests.
- server-side event tracking with data stream and secret management.
- bi engineer
- privacy officer
- integrates ga4 with other platforms and manages infrastructure.
- batch run reports
- measures campaign performance, segments audiences, and tracks conversions.
- connecting ga4 with advertising, app, and measurement platforms.
- check if dimensions and metrics are compatible for a report
- verify dimensions and metrics can be used together
- marketing ops
- machine learning
- run multiple pivot reports in a single batch
- implements server-side event tracking and offline data collection.
- attribution
- user data deletion, access auditing, and data collection acknowledgement.
- audits data access and monitors configuration changes.
- batch run pivot reports
- run a customized report of ga4 event data
- marketing team
- sets up and maintains ga4 accounts, properties, and configurations.
- run a realtime report showing events from the last 30 minutes
- connects advertising platforms and implements server-side tracking.
- run a standard ga4 report with dimensions, metrics, and date ranges
- run standard, realtime, pivot, and batch reports with data access auditing.
- compliance team
- ingesting events from servers, apps, and offline sources.
- google
- run realtime ga4 reports
- run standard ga4 reports
- run a customized pivot report
- report on who accessed ga4 reporting data
- data protection engineer
- run pivot reports for cross-tabulation analysis
- backend engineer
- create, export, and query ga4 audience segments.
- run report
- data
- check compatibility
- reporting
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
