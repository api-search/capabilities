---
consumed_apis:
- youtube-analytics
- youtube-reporting
description: Workflow combining YouTube Analytics and Reporting APIs for comprehensive channel performance monitoring, custom report generation, and bulk data export. Designed for data analysts, marketing teams, and content strategists.
layout: capability
name: YouTube Analytics And Reporting
operations:
- description: Query YouTube Analytics data
  method: GET
  name: query-analytics
  path: /v1/reports
- description: List analytics groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: Create an analytics group
  method: POST
  name: create-group
  path: /v1/groups
- description: Update an analytics group
  method: PUT
  name: update-group
  path: /v1/groups
- description: Delete an analytics group
  method: DELETE
  name: delete-group
  path: /v1/groups
- description: List items in an analytics group
  method: GET
  name: list-group-items
  path: /v1/group-items
- description: Add an item to a group
  method: POST
  name: add-group-item
  path: /v1/group-items
- description: Remove an item from a group
  method: DELETE
  name: remove-group-item
  path: /v1/group-items
- description: List reporting jobs
  method: GET
  name: list-jobs
  path: /v1/reporting-jobs
- description: Create a reporting job
  method: POST
  name: create-job
  path: /v1/reporting-jobs
- description: Delete a reporting job
  method: DELETE
  name: delete-job
  path: /v1/reporting-jobs
- description: List generated reports for a job
  method: GET
  name: list-bulk-reports
  path: /v1/bulk-reports
- description: List available report types
  method: GET
  name: list-report-types
  path: /v1/report-types
personas: []
provider_name: Youtube
provider_slug: youtube
search_terms:
- create an analytics group
- delete group
- list groups
- list jobs
- analytics
- add group item
- delete job
- list reporting jobs
- create a reporting job
- query youtube analytics data with dimensions and metrics
- delete reporting job
- list group items
- list generated bulk reports for a job
- remove group item
- list youtube analytics groups
- remove an item from an analytics group
- query youtube analytics data
- videos
- manage bulk reporting jobs
- streaming
- available report types
- list report types
- create an analytics group for organizing data
- update analytics group
- list generated reports for a job
- create reporting job
- access generated bulk reports
- query real-time analytics reports
- youtube
- create a new bulk reporting job
- video
- list analytics groups
- add an item to a group
- delete analytics group
- add an item to an analytics group
- google
- metrics
- remove an item from a group
- reporting
- list available report types
- manage analytics groups
- delete a bulk reporting job
- create job
- get metadata for a specific bulk report
- social
- query analytics
- delete a reporting job
- get bulk report
- update group
- manage items within analytics groups
- list items in an analytics group
- update an analytics group
- media
- create analytics group
- list bulk reporting jobs
- list bulk reports
- delete an analytics group
- create group
slug: analytics-and-reporting
tags:
- YouTube
- Analytics
- Reporting
- Metrics
tools:
- description: Query YouTube Analytics data with dimensions and metrics
  hints:
    idempotent: true
    readOnly: true
  name: query-analytics
- description: List YouTube Analytics groups
  hints:
    idempotent: true
    readOnly: true
  name: list-analytics-groups
- description: Create an analytics group for organizing data
  hints:
    idempotent: false
    readOnly: false
  name: create-analytics-group
- description: Update an analytics group
  hints:
    idempotent: true
    readOnly: false
  name: update-analytics-group
- description: Delete an analytics group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-analytics-group
- description: List items in an analytics group
  hints:
    idempotent: true
    readOnly: true
  name: list-group-items
- description: Add an item to an analytics group
  hints:
    idempotent: false
    readOnly: false
  name: add-group-item
- description: Remove an item from an analytics group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-group-item
- description: List bulk reporting jobs
  hints:
    idempotent: true
    readOnly: true
  name: list-reporting-jobs
- description: Create a new bulk reporting job
  hints:
    idempotent: false
    readOnly: false
  name: create-reporting-job
- description: Delete a bulk reporting job
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-reporting-job
- description: List generated bulk reports for a job
  hints:
    idempotent: true
    readOnly: true
  name: list-bulk-reports
- description: Get metadata for a specific bulk report
  hints:
    idempotent: true
    readOnly: true
  name: get-bulk-report
- description: List available report types
  hints:
    idempotent: true
    readOnly: true
  name: list-report-types
---
