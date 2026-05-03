---
categories: []
consumed_apis:
- behavioral-cohorts-api
- dashboard-rest-api
- export-api
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
- amplitude get revenue ltv data
- amplitude upload a cohort
- amplitude list event types
- identity management
- amplitude get event segmentation
- getFunnelAnalysis
- export api exportEvents
- analytics
- behavioral cohorts api uploadCohort
- manage event schemas and chart annotations. for data governance teams.
- amplitude list all cohorts
- data export
- requestCohortExport
- getUserActivity
- downloadCohortExport
- amplitude get funnel analysis
- searchUsers
- dashboard rest api getEventSegmentation
- runs experiments and feature flags
- listCohorts
- behavioral cohorts api listCohorts
- a/b testing
- dashboard rest api getRevenueLTV
- export raw event data and manage behavioral cohorts. for data analysts.
- user behavior
- getCohortExportStatus
- uploadCohort
- getEventSegmentation
- amplitude export raw event data
- behavioral cohorts api getCohortExportStatus
- scim provisioning and privacy compliance. for it admins and compliance teams.
- product analytics
- manages privacy and compliance
- dashboard rest api listEventTypes
- exportEvents
- analyzes data and manages cohorts
- unified workflow for sending events and identifying users. for data engineers.
- listEventTypes
- dashboard rest api getFunnelAnalysis
- dashboard rest api getUserActivity
- behavioral cohorts api downloadCohortExport
- manage and evaluate a/b experiments and feature flags. for product managers.
- amplitude get user activity
- feature flags
- dashboard rest api searchUsers
- amplitude search users
- data governance
- getRetentionAnalysis
- ingests and exports event data
- behavioral cohorts api requestCohortExport
- experimentation
- amplitude get cohort export status
- amplitude download cohort export file
- privacy compliance
- amplitude get retention analysis
- amplitude request a cohort export
- getRevenueLTV
- amplitude
- dashboard rest api getRetentionAnalysis
slug: amplitude-data-export-and-cohorts
source_filename: amplitude-data-export-and-cohorts.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amplitude Data Export and Cohorts\n  description: Export raw event data and manage behavioral cohorts. For data analysts.\n  tags:\n  - Amplitude\n  - Analytics\n  - Data Export\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AMPLITUDE_API_KEY: AMPLITUDE_API_KEY\ncapability:\n  consumes:\n  - import: behavioral-cohorts-api\n    location: ./shared/behavioral-cohorts-api.yaml\n  - import: dashboard-rest-api\n    location: ./shared/dashboard-rest-api.yaml\n  - import: export-api\n    location: ./shared/export-api.yaml\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: amplitude-data-export-and-cohorts-api\n    description: REST API for Amplitude Data Export and Cohorts\n    resources:\n    - path: /v1/cohorts\n      name: cohorts\n      operations:\n      - method: GET\n        name: listCohorts\n        description: Amplitude List All Cohorts\n        call: behavioral-cohorts-api.listCohorts\n\
  \        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cohorts\n      name: cohorts\n      operations:\n      - method: GET\n        name: requestCohortExport\n        description: Amplitude Request a Cohort Export\n        call: behavioral-cohorts-api.requestCohortExport\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cohorts\n      name: cohorts\n      operations:\n      - method: GET\n        name: getCohortExportStatus\n        description: Amplitude Get Cohort Export Status\n        call: behavioral-cohorts-api.getCohortExportStatus\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cohorts\n      name: cohorts\n      operations:\n      - method: GET\n        name: downloadCohortExport\n        description: Amplitude Download Cohort Export File\n        call: behavioral-cohorts-api.downloadCohortExport\n      \
  \  with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cohorts\n      name: cohorts\n      operations:\n      - method: POST\n        name: uploadCohort\n        description: Amplitude Upload a Cohort\n        call: behavioral-cohorts-api.uploadCohort\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-segmentation\n      name: event-segmentation\n      operations:\n      - method: GET\n        name: getEventSegmentation\n        description: Amplitude Get Event Segmentation\n        call: dashboard-rest-api.getEventSegmentation\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/funnel-analysis\n      name: funnel-analysis\n      operations:\n      - method: GET\n        name: getFunnelAnalysis\n        description: Amplitude Get Funnel Analysis\n        call: dashboard-rest-api.getFunnelAnalysis\n        with: {}\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/retention-analysis\n      name: retention-analysis\n      operations:\n      - method: GET\n        name: getRetentionAnalysis\n        description: Amplitude Get Retention Analysis\n        call: dashboard-rest-api.getRetentionAnalysis\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-activity\n      name: user-activity\n      operations:\n      - method: GET\n        name: getUserActivity\n        description: Amplitude Get User Activity\n        call: dashboard-rest-api.getUserActivity\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-activity\n      name: user-activity\n      operations:\n      - method: GET\n        name: searchUsers\n        description: Amplitude Search Users\n        call: dashboard-rest-api.searchUsers\n        with: {}\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/revenue-analysis\n      name: revenue-analysis\n      operations:\n      - method: GET\n        name: getRevenueLTV\n        description: Amplitude Get Revenue LTV Data\n        call: dashboard-rest-api.getRevenueLTV\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-list\n      name: event-list\n      operations:\n      - method: GET\n        name: listEventTypes\n        description: Amplitude List Event Types\n        call: dashboard-rest-api.listEventTypes\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/export\n      name: export\n      operations:\n      - method: GET\n        name: exportEvents\n        description: Amplitude Export Raw Event Data\n        call: export-api.exportEvents\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n \
  \   port: 9091\n    namespace: amplitude-data-export-and-cohorts-mcp\n    transport: http\n    description: MCP for Amplitude Data Export and Cohorts\n    tools:\n    - name: behavioral-cohorts-api-listCohorts\n      description: Amplitude List All Cohorts\n      hints:\n        readOnly: true\n      call: behavioral-cohorts-api.listCohorts\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: behavioral-cohorts-api-requestCohortExport\n      description: Amplitude Request a Cohort Export\n      hints:\n        readOnly: true\n      call: behavioral-cohorts-api.requestCohortExport\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: behavioral-cohorts-api-getCohortExportStatus\n      description: Amplitude Get Cohort Export Status\n      hints:\n        readOnly: true\n      call: behavioral-cohorts-api.getCohortExportStatus\n      with: {}\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: behavioral-cohorts-api-downloadCohortExport\n      description: Amplitude Download Cohort Export File\n      hints:\n        readOnly: true\n      call: behavioral-cohorts-api.downloadCohortExport\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: behavioral-cohorts-api-uploadCohort\n      description: Amplitude Upload a Cohort\n      hints:\n        readOnly: false\n      call: behavioral-cohorts-api.uploadCohort\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dashboard-rest-api-getEventSegmentation\n      description: Amplitude Get Event Segmentation\n      hints:\n        readOnly: true\n      call: dashboard-rest-api.getEventSegmentation\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dashboard-rest-api-getFunnelAnalysis\n      description: Amplitude Get Funnel Analysis\n      hints:\n        readOnly: true\n      call: dashboard-rest-api.getFunnelAnalysis\n\
  \      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dashboard-rest-api-getRetentionAnalysis\n      description: Amplitude Get Retention Analysis\n      hints:\n        readOnly: true\n      call: dashboard-rest-api.getRetentionAnalysis\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dashboard-rest-api-getUserActivity\n      description: Amplitude Get User Activity\n      hints:\n        readOnly: true\n      call: dashboard-rest-api.getUserActivity\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dashboard-rest-api-searchUsers\n      description: Amplitude Search Users\n      hints:\n        readOnly: true\n      call: dashboard-rest-api.searchUsers\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dashboard-rest-api-getRevenueLTV\n      description: Amplitude Get Revenue LTV Data\n      hints:\n   \
  \     readOnly: true\n      call: dashboard-rest-api.getRevenueLTV\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dashboard-rest-api-listEventTypes\n      description: Amplitude List Event Types\n      hints:\n        readOnly: true\n      call: dashboard-rest-api.listEventTypes\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-api-exportEvents\n      description: Amplitude Export Raw Event Data\n      hints:\n        readOnly: true\n      call: export-api.exportEvents\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
