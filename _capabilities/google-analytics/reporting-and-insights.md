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
- run data access audit reports
- report on who accessed ga4 reporting data
- connects advertising platforms and implements server-side tracking.
- connecting ga4 with advertising, app, and measurement platforms.
- google
- analytics
- bi engineer
- run realtime ga4 reports
- run realtime report
- check compatibility
- verify dimensions and metrics can be used together
- run up to 5 pivot reports in a single batch request
- data
- ingesting events from servers, apps, and offline sources.
- attribution
- measures campaign performance, segments audiences, and tracks conversions.
- integrates ga4 with other platforms and manages infrastructure.
- sets up and maintains ga4 accounts, properties, and configurations.
- querying and analyzing ga4 event data through various report types.
- managing data privacy, deletion, and access auditing.
- run standard ga4 reports
- run multiple reports in a single batch request
- implements privacy-compliant data handling and deletion workflows.
- reporting
- web analytics
- run up to 5 pivot reports in a batch
- run up to 5 standard reports in a single batch request
- batch run reports
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- server-side event tracking with data stream and secret management.
- marketing team
- audits data access and monitors configuration changes.
- run a customized report of ga4 event data
- run standard, realtime, pivot, and batch reports with data access auditing.
- machine learning
- create, export, and query ga4 audience segments.
- privacy officer
- report on who accessed ga4 reporting data and when
- extracts insights from ga4 data through reports and explorations.
- segmenting and exporting user populations for analysis and activation.
- marketing ops
- user data deletion, access auditing, and data collection acknowledgement.
- setting up and maintaining ga4 account and property structure.
- run a customized pivot report
- run multiple pivot reports in a single batch
- metrics
- implements server-side event tracking and offline data collection.
- manages data privacy compliance including gdpr deletion requests.
- run pivot report
- google analytics
- run report
- run access report
- run up to 5 reports in a batch
- compliance team
- data protection engineer
- builds automated reporting pipelines and dashboards from ga4 data.
- ga4
- check if dimensions and metrics are compatible for a report
- analytics administrator
- run a standard ga4 report with dimensions, metrics, and date ranges
- backend engineer
- insights
- data analyst
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- check dimension and metric compatibility
- run a realtime report showing events from the last 30 minutes
- run an advanced pivot table report for cross-tabulation analysis
- platform engineer
- run pivot reports for cross-tabulation analysis
- batch run pivot reports
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
