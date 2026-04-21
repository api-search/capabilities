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
- videos
- create analytics group
- query real-time analytics reports
- update an analytics group
- delete a bulk reporting job
- video
- remove group item
- create an analytics group for organizing data
- delete reporting job
- delete a reporting job
- get bulk report
- update group
- add an item to a group
- list reporting jobs
- list groups
- query youtube analytics data with dimensions and metrics
- query youtube analytics data
- remove an item from an analytics group
- list jobs
- list analytics groups
- create a new bulk reporting job
- create group
- list bulk reports
- delete analytics group
- get metadata for a specific bulk report
- list group items
- create a reporting job
- social
- create an analytics group
- add an item to an analytics group
- list available report types
- create reporting job
- list youtube analytics groups
- list items in an analytics group
- add group item
- streaming
- analytics
- delete job
- delete an analytics group
- youtube
- list generated reports for a job
- manage bulk reporting jobs
- google
- available report types
- metrics
- list generated bulk reports for a job
- delete group
- media
- reporting
- query analytics
- manage analytics groups
- access generated bulk reports
- update analytics group
- list bulk reporting jobs
- remove an item from a group
- manage items within analytics groups
- list report types
- create job
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
