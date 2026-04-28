---
categories:
- analytics
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
- list report types
- remove an item from an analytics group
- create a new bulk reporting job
- list reporting jobs
- list group items
- add group item
- list youtube analytics groups
- delete reporting job
- streaming
- query analytics
- delete job
- manage bulk reporting jobs
- query real-time analytics reports
- get bulk report
- delete analytics group
- list generated reports for a job
- create reporting job
- update group
- list jobs
- update analytics group
- video
- manage analytics groups
- analytics
- delete group
- manage items within analytics groups
- list items in an analytics group
- get metadata for a specific bulk report
- social
- list bulk reports
- create a reporting job
- reporting
- delete a bulk reporting job
- create an analytics group
- list groups
- videos
- query youtube analytics data with dimensions and metrics
- delete a reporting job
- add an item to a group
- query youtube analytics data
- create analytics group
- list analytics groups
- access generated bulk reports
- list bulk reporting jobs
- add an item to an analytics group
- youtube
- google
- media
- list generated bulk reports for a job
- metrics
- create group
- list available report types
- remove an item from a group
- remove group item
- update an analytics group
- available report types
- create job
- create an analytics group for organizing data
- delete an analytics group
slug: analytics-and-reporting
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"YouTube Analytics And Reporting\"\n  description: \"Workflow combining YouTube Analytics and Reporting APIs for comprehensive channel performance monitoring, custom report generation, and bulk data export. Designed for data analysts, marketing teams, and content strategists.\"\n  tags:\n    - YouTube\n    - Analytics\n    - Reporting\n    - Metrics\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      YOUTUBE_OAUTH_TOKEN: YOUTUBE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: youtube-analytics\n      location: ./shared/analytics.yaml\n    - import: youtube-reporting\n      location: ./shared/reporting.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: analytics-reporting-api\n      description: \"Unified REST API for YouTube analytics and reporting workflows.\"\n      resources:\n        - path: /v1/reports\n          name: analytics-reports\n      \
  \    description: \"Query real-time analytics reports\"\n          operations:\n            - method: GET\n              name: query-analytics\n              description: \"Query YouTube Analytics data\"\n              call: \"youtube-analytics.query-reports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups\n          name: analytics-groups\n          description: \"Manage analytics groups\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List analytics groups\"\n              call: \"youtube-analytics.list-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-group\n              description: \"Create an analytics group\"\n              call: \"youtube-analytics.insert-group\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-group\n              description: \"Update an analytics group\"\n              call: \"youtube-analytics.update-group\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-group\n              description: \"Delete an analytics group\"\n              call: \"youtube-analytics.delete-group\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/group-items\n          name: group-items\n          description: \"Manage items within analytics groups\"\n          operations:\n            - method: GET\n              name: list-group-items\n              description: \"List items in an analytics group\"\n              call: \"youtube-analytics.list-group-items\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n            - method: POST\n              name: add-group-item\n              description: \"Add an item to a group\"\n              call: \"youtube-analytics.insert-group-item\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: remove-group-item\n              description: \"Remove an item from a group\"\n              call: \"youtube-analytics.delete-group-item\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reporting-jobs\n          name: reporting-jobs\n          description: \"Manage bulk reporting jobs\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List reporting jobs\"\n              call: \"youtube-reporting.list-jobs\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n            - method: POST\n              name: create-job\n              description: \"Create a reporting job\"\n              call: \"youtube-reporting.create-job\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-job\n              description: \"Delete a reporting job\"\n              call: \"youtube-reporting.delete-job\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bulk-reports\n          name: bulk-reports\n          description: \"Access generated bulk reports\"\n          operations:\n            - method: GET\n              name: list-bulk-reports\n              description: \"List generated reports for a job\"\n              call: \"youtube-reporting.list-reports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/report-types\n\
  \          name: report-types\n          description: \"Available report types\"\n          operations:\n            - method: GET\n              name: list-report-types\n              description: \"List available report types\"\n              call: \"youtube-reporting.list-report-types\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: analytics-reporting-mcp\n      transport: http\n      description: \"MCP server for AI-assisted YouTube analytics and reporting.\"\n      tools:\n        - name: query-analytics\n          description: \"Query YouTube Analytics data with dimensions and metrics\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-analytics.query-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-analytics-groups\n          description: \"List YouTube\
  \ Analytics groups\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-analytics.list-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-analytics-group\n          description: \"Create an analytics group for organizing data\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"youtube-analytics.insert-group\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-analytics-group\n          description: \"Update an analytics group\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"youtube-analytics.update-group\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-analytics-group\n          description: \"Delete an analytics group\"\n          hints:\n       \
  \     readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"youtube-analytics.delete-group\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-group-items\n          description: \"List items in an analytics group\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-analytics.list-group-items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-group-item\n          description: \"Add an item to an analytics group\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"youtube-analytics.insert-group-item\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: remove-group-item\n          description: \"Remove an item from an analytics group\"\n          hints:\n            readOnly: false\n\
  \            destructive: true\n            idempotent: true\n          call: \"youtube-analytics.delete-group-item\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-reporting-jobs\n          description: \"List bulk reporting jobs\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-reporting.list-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-reporting-job\n          description: \"Create a new bulk reporting job\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"youtube-reporting.create-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-reporting-job\n          description: \"Delete a bulk reporting job\"\n          hints:\n            readOnly: false\n            destructive: true\n   \
  \         idempotent: true\n          call: \"youtube-reporting.delete-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-bulk-reports\n          description: \"List generated bulk reports for a job\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-reporting.list-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-bulk-report\n          description: \"Get metadata for a specific bulk report\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-reporting.get-report\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-report-types\n          description: \"List available report types\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"youtube-reporting.list-report-types\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/youtube/refs/heads/main/capabilities/analytics-and-reporting.yaml
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
