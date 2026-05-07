---
categories: []
consumed_apis: []
description: Export raw event data and manage behavioral cohorts. For data analysts.
layout: capability
name: Amplitude Data Export and Cohorts
operations:
- description: Amplitude List All Cohorts
  method: GET
  name: listCohorts
  path: /v1/cohorts
- description: Amplitude Request a Cohort Export
  method: GET
  name: requestCohortExport
  path: /v1/cohorts
- description: Amplitude Get Cohort Export Status
  method: GET
  name: getCohortExportStatus
  path: /v1/cohorts
- description: Amplitude Download Cohort Export File
  method: GET
  name: downloadCohortExport
  path: /v1/cohorts
- description: Amplitude Upload a Cohort
  method: POST
  name: uploadCohort
  path: /v1/cohorts
- description: Amplitude Get Event Segmentation
  method: GET
  name: getEventSegmentation
  path: /v1/event-segmentation
- description: Amplitude Get Funnel Analysis
  method: GET
  name: getFunnelAnalysis
  path: /v1/funnel-analysis
- description: Amplitude Get Retention Analysis
  method: GET
  name: getRetentionAnalysis
  path: /v1/retention-analysis
- description: Amplitude Get User Activity
  method: GET
  name: getUserActivity
  path: /v1/user-activity
- description: Amplitude Search Users
  method: GET
  name: searchUsers
  path: /v1/user-activity
- description: Amplitude Get Revenue LTV Data
  method: GET
  name: getRevenueLTV
  path: /v1/revenue-analysis
- description: Amplitude List Event Types
  method: GET
  name: listEventTypes
  path: /v1/event-list
- description: Amplitude Export Raw Event Data
  method: GET
  name: exportEvents
  path: /v1/export
personas: []
provider_name: Amplitude
provider_slug: amplitude
search_terms:
- getUserActivity
- analytics
- amplitude list event types
- feature flags
- amplitude request a cohort export
- amplitude get retention analysis
- data export
- getFunnelAnalysis
- unified workflow for sending events and identifying users. for data engineers.
- manage event schemas and chart annotations. for data governance teams.
- experimentation
- runs experiments and feature flags
- manages privacy and compliance
- ingests and exports event data
- identity management
- product analytics
- dashboard rest api getUserActivity
- amplitude search users
- analyzes data and manages cohorts
- privacy compliance
- listCohorts
- dashboard rest api getFunnelAnalysis
- behavioral cohorts api requestCohortExport
- amplitude export raw event data
- amplitude
- exportEvents
- amplitude download cohort export file
- dashboard rest api getRetentionAnalysis
- amplitude get revenue ltv data
- searchUsers
- getRetentionAnalysis
- amplitude get user activity
- amplitude upload a cohort
- behavioral cohorts api uploadCohort
- dashboard rest api searchUsers
- dashboard rest api listEventTypes
- manage and evaluate a/b experiments and feature flags. for product managers.
- downloadCohortExport
- scim provisioning and privacy compliance. for it admins and compliance teams.
- amplitude list all cohorts
- uploadCohort
- listEventTypes
- getEventSegmentation
- export api exportEvents
- dashboard rest api getRevenueLTV
- requestCohortExport
- amplitude get funnel analysis
- a/b testing
- getCohortExportStatus
- behavioral cohorts api downloadCohortExport
- export raw event data and manage behavioral cohorts. for data analysts.
- data governance
- behavioral cohorts api getCohortExportStatus
- user behavior
- getRevenueLTV
- amplitude get event segmentation
- behavioral cohorts api listCohorts
- amplitude get cohort export status
- dashboard rest api getEventSegmentation
slug: amplitude-data-export-and-cohorts
source_filename: amplitude-data-export-and-cohorts.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amplitude Data Export and Cohorts\n  description: Export raw event data and manage behavioral cohorts. For data analysts.\n  tags:\n  - Amplitude\n  - Analytics\n  - Data Export\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AMPLITUDE_API_KEY: AMPLITUDE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: behavioral-cohorts-api\n    baseUri: https://amplitude.com\n    description: The Amplitude Behavioral Cohorts API allows developers to list, export, and upload cohorts in Amplitude.\n      Cohorts are groups of users defined by shared behavioral patterns or properties. This API supports downloading cohort\n      membership lists, creating new cohorts from external data, and retrieving cohort metadata. It is commonly used for syncing\n      audience segments with marketing platforms, CRMs, and other downstream tools.\n    resources:\n    - name: cohorts\n      path: /cohorts\n  \
  \    description: Cohorts operations\n      operations:\n      - name: listCohorts\n        method: GET\n        description: Amplitude List All Cohorts\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: requestCohortExport\n        method: GET\n        description: Amplitude Request a Cohort Export\n        inputParameters:\n        - name: cohort_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the cohort to export.\n        - name: props\n          in: query\n          type: integer\n          required: false\n          description: Set to 1 to include user properties in the export.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getCohortExportStatus\n        method: GET\n        description: Amplitude Get Cohort Export\
  \ Status\n        inputParameters:\n        - name: cohort_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the cohort whose export status to check.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: downloadCohortExport\n        method: GET\n        description: Amplitude Download Cohort Export File\n        inputParameters:\n        - name: cohort_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the cohort to download.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploadCohort\n        method: POST\n        description: Amplitude Upload a Cohort\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n    authentication:\n      type: basic\n      username: '{{AMPLITUDE_API_KEY}}'\n      password: '{{AMPLITUDE_SECRET_KEY}}'\n  - type: http\n    namespace: dashboard-rest-api\n    baseUri: https://amplitude.com\n    description: The Amplitude Dashboard REST API provides programmatic access to the same data displayed in Amplitude's dashboard\n      charts and graphs. It returns results in JSON format and supports queries filtered by event types, user segments, cohorts,\n      and date ranges. Developers can use this API to build custom reporting tools, export chart data, or integrate Amplitude\n      analytics into external dashboards and business intelligence systems.\n    resources:\n    - name: event-segmentation\n      path: /event-segmentation\n      description: Event Segmentation operations\n      operations:\n      - name: getEventSegmentation\n        method: GET\n        description: Amplitude Get Event Segmentation\n        inputParameters:\n        - name: param\n\
  \          in: query\n          type: string\n          required: false\n          description: ''\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: m\n          in: query\n          type: string\n          required: false\n          description: The metric to compute. Options include uniques, totals, pct_dau, average, histogram, sums, value_avg,\n            or formula.\n        - name: i\n          in: query\n          type: integer\n          required: false\n          description: Time interval granularity. Use -300000 for real-time, 1 for daily, 7 for weekly, or 30 for monthly.\n        - name: s\n          in: query\n          type: string\n          required: false\n          description: Segment definitions as a JSON-encoded array of segment objects for filtering results.\n\
  \        - name: g\n          in: query\n          type: string\n          required: false\n          description: The property to group results by, such as a user property or event property name.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: The number of group-by values to return. Default is 100, max is 1000.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: funnel-analysis\n      path: /funnel-analysis\n      description: Funnel Analysis operations\n      operations:\n      - name: getFunnelAnalysis\n        method: GET\n        description: Amplitude Get Funnel Analysis\n        inputParameters:\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: param\n          in: query\n          type: string\n          required: false\n          description:\
  \ ''\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: n\n          in: query\n          type: integer\n          required: false\n          description: The conversion window in days. Default varies by project settings.\n        - name: s\n          in: query\n          type: string\n          required: false\n          description: Segment definitions as a JSON-encoded array.\n        - name: g\n          in: query\n          type: string\n          required: false\n          description: The property to group results by.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: retention-analysis\n      path: /retention-analysis\n      description: Retention Analysis operations\n      operations:\n      - name: getRetentionAnalysis\n        method: GET\n        description: Amplitude Get Retention Analysis\n      \
  \  inputParameters:\n        - name: se\n          in: query\n          type: string\n          required: true\n          description: The starting event as a JSON-encoded object with event_type field.\n        - name: re\n          in: query\n          type: string\n          required: true\n          description: The returning event as a JSON-encoded object with event_type field.\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: rm\n          in: query\n          type: string\n          required: false\n          description: Retention mode. Use bracket for N-day retention or rolling for unbounded retention.\n        - name: s\n          in: query\n          type: string\n          required: false\n          description: Segment definitions as a JSON-encoded array.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-activity\n      path: /user-activity\n      description: User Activity operations\n      operations:\n      - name: getUserActivity\n        method: GET\n        description: Amplitude Get User Activity\n        inputParameters:\n        - name: user\n          in: query\n          type: string\n          required: true\n          description: The user_id to look up activity for.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: The offset for pagination. Default is 0.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: The number of events to return. Default is 1000.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchUsers\n        method:\
  \ GET\n        description: Amplitude Search Users\n        inputParameters:\n        - name: user\n          in: query\n          type: string\n          required: true\n          description: The user_id, device_id, or Amplitude ID to search for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: revenue-analysis\n      path: /revenue-analysis\n      description: Revenue Analysis operations\n      operations:\n      - name: getRevenueLTV\n        method: GET\n        description: Amplitude Get Revenue LTV Data\n        inputParameters:\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: m\n          in: query\n          type: string\n          required: false\n          description: The revenue\
  \ metric to compute.\n        - name: s\n          in: query\n          type: string\n          required: false\n          description: Segment definitions as a JSON-encoded array.\n        - name: g\n          in: query\n          type: string\n          required: false\n          description: The property to group results by.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-list\n      path: /event-list\n      description: Event List operations\n      operations:\n      - name: listEventTypes\n        method: GET\n        description: Amplitude List Event Types\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    authentication:\n      type: basic\n      username: '{{AMPLITUDE_API_KEY}}'\n      password: '{{AMPLITUDE_SECRET_KEY}}'\n  - type: http\n    namespace: export-api\n    baseUri:\
  \ https://amplitude.com\n    description: The Amplitude Export API enables bulk export of raw event data for a given project within a specified date\n      range. Results are returned as zipped archives of JSON files containing complete event records with timestamps, user\n      properties, device information, and attribution data. This API is commonly used for data warehousing, offline analysis,\n      and feeding event data into external processing pipelines.\n    resources:\n    - name: export\n      path: /export\n      description: Export operations\n      operations:\n      - name: exportEvents\n        method: GET\n        description: Amplitude Export Raw Event Data\n        inputParameters:\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: The start date and hour in YYYYMMDDTHH format, for example 20220101T00. For multi-day exports, the\n            format YYYYMMDD is also accepted.\n        - name: end\n    \
  \      in: query\n          type: string\n          required: true\n          description: The end date and hour in YYYYMMDDTHH format, for example 20220101T23. For multi-day exports, the format\n            YYYYMMDD is also accepted.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    authentication:\n      type: basic\n      username: '{{AMPLITUDE_API_KEY}}'\n      password: '{{AMPLITUDE_SECRET_KEY}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: amplitude-data-export-and-cohorts-api\n    description: REST API for Amplitude Data Export and Cohorts\n    resources:\n    - path: /v1/cohorts\n      name: cohorts\n      operations:\n      - method: GET\n        name: listCohorts\n        description: Amplitude List All Cohorts\n        call: behavioral-cohorts-api.listCohorts\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cohorts\n   \
  \   name: cohorts\n      operations:\n      - method: GET\n        name: requestCohortExport\n        description: Amplitude Request a Cohort Export\n        call: behavioral-cohorts-api.requestCohortExport\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cohorts\n      name: cohorts\n      operations:\n      - method: GET\n        name: getCohortExportStatus\n        description: Amplitude Get Cohort Export Status\n        call: behavioral-cohorts-api.getCohortExportStatus\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cohorts\n      name: cohorts\n      operations:\n      - method: GET\n        name: downloadCohortExport\n        description: Amplitude Download Cohort Export File\n        call: behavioral-cohorts-api.downloadCohortExport\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cohorts\n      name:\
  \ cohorts\n      operations:\n      - method: POST\n        name: uploadCohort\n        description: Amplitude Upload a Cohort\n        call: behavioral-cohorts-api.uploadCohort\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-segmentation\n      name: event-segmentation\n      operations:\n      - method: GET\n        name: getEventSegmentation\n        description: Amplitude Get Event Segmentation\n        call: dashboard-rest-api.getEventSegmentation\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/funnel-analysis\n      name: funnel-analysis\n      operations:\n      - method: GET\n        name: getFunnelAnalysis\n        description: Amplitude Get Funnel Analysis\n        call: dashboard-rest-api.getFunnelAnalysis\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/retention-analysis\n      name: retention-analysis\n\
  \      operations:\n      - method: GET\n        name: getRetentionAnalysis\n        description: Amplitude Get Retention Analysis\n        call: dashboard-rest-api.getRetentionAnalysis\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-activity\n      name: user-activity\n      operations:\n      - method: GET\n        name: getUserActivity\n        description: Amplitude Get User Activity\n        call: dashboard-rest-api.getUserActivity\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-activity\n      name: user-activity\n      operations:\n      - method: GET\n        name: searchUsers\n        description: Amplitude Search Users\n        call: dashboard-rest-api.searchUsers\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/revenue-analysis\n      name: revenue-analysis\n      operations:\n      - method:\
  \ GET\n        name: getRevenueLTV\n        description: Amplitude Get Revenue LTV Data\n        call: dashboard-rest-api.getRevenueLTV\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-list\n      name: event-list\n      operations:\n      - method: GET\n        name: listEventTypes\n        description: Amplitude List Event Types\n        call: dashboard-rest-api.listEventTypes\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/export\n      name: export\n      operations:\n      - method: GET\n        name: exportEvents\n        description: Amplitude Export Raw Event Data\n        call: export-api.exportEvents\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: amplitude-data-export-and-cohorts-mcp\n    transport: http\n    description: MCP for Amplitude Data Export and Cohorts\n\
  \    tools:\n    - name: behavioral-cohorts-api-listCohorts\n      description: Amplitude List All Cohorts\n      hints:\n        readOnly: true\n      call: behavioral-cohorts-api.listCohorts\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: behavioral-cohorts-api-requestCohortExport\n      description: Amplitude Request a Cohort Export\n      hints:\n        readOnly: true\n      call: behavioral-cohorts-api.requestCohortExport\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: behavioral-cohorts-api-getCohortExportStatus\n      description: Amplitude Get Cohort Export Status\n      hints:\n        readOnly: true\n      call: behavioral-cohorts-api.getCohortExportStatus\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: behavioral-cohorts-api-downloadCohortExport\n      description: Amplitude Download Cohort Export File\n      hints:\n        readOnly:\
  \ true\n      call: behavioral-cohorts-api.downloadCohortExport\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: behavioral-cohorts-api-uploadCohort\n      description: Amplitude Upload a Cohort\n      hints:\n        readOnly: false\n      call: behavioral-cohorts-api.uploadCohort\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dashboard-rest-api-getEventSegmentation\n      description: Amplitude Get Event Segmentation\n      hints:\n        readOnly: true\n      call: dashboard-rest-api.getEventSegmentation\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dashboard-rest-api-getFunnelAnalysis\n      description: Amplitude Get Funnel Analysis\n      hints:\n        readOnly: true\n      call: dashboard-rest-api.getFunnelAnalysis\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dashboard-rest-api-getRetentionAnalysis\n\
  \      description: Amplitude Get Retention Analysis\n      hints:\n        readOnly: true\n      call: dashboard-rest-api.getRetentionAnalysis\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dashboard-rest-api-getUserActivity\n      description: Amplitude Get User Activity\n      hints:\n        readOnly: true\n      call: dashboard-rest-api.getUserActivity\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dashboard-rest-api-searchUsers\n      description: Amplitude Search Users\n      hints:\n        readOnly: true\n      call: dashboard-rest-api.searchUsers\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dashboard-rest-api-getRevenueLTV\n      description: Amplitude Get Revenue LTV Data\n      hints:\n        readOnly: true\n      call: dashboard-rest-api.getRevenueLTV\n      with: {}\n      outputParameters:\n      - type: object\n       \
  \ mapping: $.\n    - name: dashboard-rest-api-listEventTypes\n      description: Amplitude List Event Types\n      hints:\n        readOnly: true\n      call: dashboard-rest-api.listEventTypes\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-api-exportEvents\n      description: Amplitude Export Raw Event Data\n      hints:\n        readOnly: true\n      call: export-api.exportEvents\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amplitude/refs/heads/main/capabilities/amplitude-data-export-and-cohorts.yaml
tags:
- Amplitude
- Analytics
- Data Export
tools:
- description: Amplitude List All Cohorts
  hints:
    readOnly: true
  name: behavioral-cohorts-api-listCohorts
- description: Amplitude Request a Cohort Export
  hints:
    readOnly: true
  name: behavioral-cohorts-api-requestCohortExport
- description: Amplitude Get Cohort Export Status
  hints:
    readOnly: true
  name: behavioral-cohorts-api-getCohortExportStatus
- description: Amplitude Download Cohort Export File
  hints:
    readOnly: true
  name: behavioral-cohorts-api-downloadCohortExport
- description: Amplitude Upload a Cohort
  hints:
    readOnly: false
  name: behavioral-cohorts-api-uploadCohort
- description: Amplitude Get Event Segmentation
  hints:
    readOnly: true
  name: dashboard-rest-api-getEventSegmentation
- description: Amplitude Get Funnel Analysis
  hints:
    readOnly: true
  name: dashboard-rest-api-getFunnelAnalysis
- description: Amplitude Get Retention Analysis
  hints:
    readOnly: true
  name: dashboard-rest-api-getRetentionAnalysis
- description: Amplitude Get User Activity
  hints:
    readOnly: true
  name: dashboard-rest-api-getUserActivity
- description: Amplitude Search Users
  hints:
    readOnly: true
  name: dashboard-rest-api-searchUsers
- description: Amplitude Get Revenue LTV Data
  hints:
    readOnly: true
  name: dashboard-rest-api-getRevenueLTV
- description: Amplitude List Event Types
  hints:
    readOnly: true
  name: dashboard-rest-api-listEventTypes
- description: Amplitude Export Raw Event Data
  hints:
    readOnly: true
  name: export-api-exportEvents
---
