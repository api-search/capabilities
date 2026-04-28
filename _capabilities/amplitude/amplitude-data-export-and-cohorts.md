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
- behavioral cohorts api uploadCohort
- dashboard rest api getUserActivity
- getUserActivity
- downloadCohortExport
- behavioral cohorts api downloadCohortExport
- amplitude get revenue ltv data
- amplitude get user activity
- export api exportEvents
- amplitude export raw event data
- getRevenueLTV
- product analytics
- data export
- listCohorts
- export raw event data and manage behavioral cohorts. for data analysts.
- amplitude get retention analysis
- a/b testing
- dashboard rest api searchUsers
- dashboard rest api getRevenueLTV
- amplitude download cohort export file
- feature flags
- user behavior
- getFunnelAnalysis
- getEventSegmentation
- exportEvents
- searchUsers
- amplitude list all cohorts
- listEventTypes
- amplitude request a cohort export
- dashboard rest api getRetentionAnalysis
- getCohortExportStatus
- unified workflow for sending events and identifying users. for data engineers.
- scim provisioning and privacy compliance. for it admins and compliance teams.
- amplitude
- manages privacy and compliance
- uploadCohort
- manage event schemas and chart annotations. for data governance teams.
- amplitude get cohort export status
- behavioral cohorts api listCohorts
- ingests and exports event data
- experimentation
- amplitude search users
- dashboard rest api listEventTypes
- requestCohortExport
- amplitude get funnel analysis
- dashboard rest api getEventSegmentation
- privacy compliance
- analytics
- data governance
- behavioral cohorts api getCohortExportStatus
- analyzes data and manages cohorts
- dashboard rest api getFunnelAnalysis
- manage and evaluate a/b experiments and feature flags. for product managers.
- getRetentionAnalysis
- amplitude upload a cohort
- runs experiments and feature flags
- behavioral cohorts api requestCohortExport
- amplitude get event segmentation
- identity management
- amplitude list event types
slug: amplitude-data-export-and-cohorts
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
