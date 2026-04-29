---
categories:
- analytics
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
- run standard ga4 reports
- run up to 5 pivot reports in a batch
- run multiple pivot reports in a single batch
- analytics administrator
- data
- verify dimensions and metrics can be used together
- querying and analyzing ga4 event data through various report types.
- server-side event tracking with data stream and secret management.
- run up to 5 standard reports in a single batch request
- analytics
- machine learning
- attribution
- check compatibility
- marketing team
- measures campaign performance, segments audiences, and tracks conversions.
- builds automated reporting pipelines and dashboards from ga4 data.
- manage accounts, properties, data streams, custom dimensions/metrics, and conversion events.
- compliance team
- run pivot report
- report on who accessed ga4 reporting data and when
- web analytics
- check dimension and metric compatibility
- run realtime report
- privacy officer
- run a realtime report showing events from the last 30 minutes
- manages data privacy compliance including gdpr deletion requests.
- check if dimensions and metrics are compatible for a report
- managing data privacy, deletion, and access auditing.
- google analytics
- connects advertising platforms and implements server-side tracking.
- run multiple reports in a single batch request
- google
- run realtime ga4 reports
- run data access audit reports
- run pivot reports for cross-tabulation analysis
- bi engineer
- connect ga4 with firebase, google ads, and manage measurement protocol secrets.
- run up to 5 pivot reports in a single batch request
- report on who accessed ga4 reporting data
- audits data access and monitors configuration changes.
- sets up and maintains ga4 accounts, properties, and configurations.
- implements privacy-compliant data handling and deletion workflows.
- run access report
- metrics
- connecting ga4 with advertising, app, and measurement platforms.
- run standard, realtime, pivot, and batch reports with data access auditing.
- batch run reports
- user data deletion, access auditing, and data collection acknowledgement.
- run a customized report of ga4 event data
- implements server-side event tracking and offline data collection.
- run up to 5 reports in a batch
- run a customized pivot report
- setting up and maintaining ga4 account and property structure.
- platform engineer
- create, export, and query ga4 audience segments.
- run report
- ga4
- insights
- run a standard ga4 report with dimensions, metrics, and date ranges
- run an advanced pivot table report for cross-tabulation analysis
- reporting
- marketing ops
- backend engineer
- extracts insights from ga4 data through reports and explorations.
- ingesting events from servers, apps, and offline sources.
- segmenting and exporting user populations for analysis and activation.
- data protection engineer
- integrates ga4 with other platforms and manages infrastructure.
- batch run pivot reports
- data analyst
slug: reporting-and-insights
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Analytics Reporting and Insights\"\n  description: \"Unified reporting workflow combining the Data API for running standard, realtime, and pivot reports with the Admin API for accessing data access audit reports. Used by data analysts, marketing teams, and BI engineers to extract insights from GA4 properties.\"\n  tags:\n    - Google Analytics\n    - Reporting\n    - Analytics\n    - Insights\n    - GA4\n  created: \"2026-04-17\"\n  modified: \"2026-04-17\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_ANALYTICS_ACCESS_TOKEN: GOOGLE_ANALYTICS_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: ga-data-api\n      location: ./shared/data-api.yaml\n    - import: ga-admin-api\n      location: ./shared/admin-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ga-reporting-api\n      description: \"Unified REST API for Google Analytics reporting and insights.\"\n      resources:\n        -\
  \ path: /v1/reports\n          name: standard-reports\n          description: \"Run standard GA4 reports\"\n          operations:\n            - method: POST\n              name: run-report\n              description: \"Run a customized report of GA4 event data\"\n              call: \"ga-data-api.run-report\"\n              with:\n                property: \"rest.property\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/realtime\n          name: realtime-reports\n          description: \"Run realtime GA4 reports\"\n          operations:\n            - method: POST\n              name: run-realtime-report\n              description: \"Run a realtime report showing events from the last 30 minutes\"\n              call: \"ga-data-api.run-realtime-report\"\n              with:\n                property: \"rest.property\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/reports/pivot\n          name: pivot-reports\n          description: \"Run pivot reports for cross-tabulation analysis\"\n          operations:\n            - method: POST\n              name: run-pivot-report\n              description: \"Run a customized pivot report\"\n              call: \"ga-data-api.run-pivot-report\"\n              with:\n                property: \"rest.property\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/batch\n          name: batch-reports\n          description: \"Run multiple reports in a single batch request\"\n          operations:\n            - method: POST\n              name: batch-run-reports\n              description: \"Run up to 5 reports in a batch\"\n              call: \"ga-data-api.batch-run-reports\"\n              with:\n                property: \"rest.property\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/reports/pivot/batch\n          name: batch-pivot-reports\n          description: \"Run multiple pivot reports in a single batch\"\n          operations:\n            - method: POST\n              name: batch-run-pivot-reports\n              description: \"Run up to 5 pivot reports in a batch\"\n              call: \"ga-data-api.batch-run-pivot-reports\"\n              with:\n                property: \"rest.property\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compatibility\n          name: compatibility\n          description: \"Check dimension and metric compatibility\"\n          operations:\n            - method: POST\n              name: check-compatibility\n              description: \"Verify dimensions and metrics can be used together\"\n              call: \"ga-data-api.check-compatibility\"\n              with:\n                property: \"rest.property\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/access-reports\n          name: access-reports\n          description: \"Run data access audit reports\"\n          operations:\n            - method: POST\n              name: run-access-report\n              description: \"Report on who accessed GA4 reporting data\"\n              call: \"ga-admin-api.run-access-report\"\n              with:\n                entity: \"rest.entity\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: ga-reporting-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Google Analytics reporting and insights.\"\n      tools:\n        - name: run-report\n          description: \"Run a standard GA4 report with dimensions, metrics, and date ranges\"\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n          call: \"ga-data-api.run-report\"\n          with:\n            property: \"tools.property\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-realtime-report\n          description: \"Run a realtime report showing events from the last 30 minutes\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-data-api.run-realtime-report\"\n          with:\n            property: \"tools.property\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-pivot-report\n          description: \"Run an advanced pivot table report for cross-tabulation analysis\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-data-api.run-pivot-report\"\n          with:\n            property: \"tools.property\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n        - name: batch-run-reports\n          description: \"Run up to 5 standard reports in a single batch request\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-data-api.batch-run-reports\"\n          with:\n            property: \"tools.property\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: batch-run-pivot-reports\n          description: \"Run up to 5 pivot reports in a single batch request\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-data-api.batch-run-pivot-reports\"\n          with:\n            property: \"tools.property\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-compatibility\n          description: \"Check if dimensions and metrics are compatible for a report\"\n          hints:\n            readOnly: true\n            idempotent: true\n   \
  \       call: \"ga-data-api.check-compatibility\"\n          with:\n            property: \"tools.property\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-access-report\n          description: \"Report on who accessed GA4 reporting data and when\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ga-admin-api.run-access-report\"\n          with:\n            entity: \"tools.entity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-analytics/refs/heads/main/capabilities/reporting-and-insights.yaml
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
