---
categories:
- analytics
consumed_apis: []
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
- analytics
- delete reporting job
- create group
- remove group item
- add an item to a group
- create job
- list bulk reports
- update analytics group
- streaming
- video
- list groups
- create analytics group
- query youtube analytics data with dimensions and metrics
- add an item to an analytics group
- get metadata for a specific bulk report
- youtube
- query youtube analytics data
- remove an item from a group
- manage bulk reporting jobs
- update an analytics group
- list available report types
- list youtube analytics groups
- list reporting jobs
- list bulk reporting jobs
- list analytics groups
- list group items
- get bulk report
- create an analytics group
- create an analytics group for organizing data
- delete analytics group
- available report types
- remove an item from an analytics group
- google
- create a reporting job
- delete an analytics group
- create a new bulk reporting job
- query analytics
- manage analytics groups
- add group item
- access generated bulk reports
- list report types
- create reporting job
- list jobs
- manage items within analytics groups
- media
- videos
- metrics
- list generated reports for a job
- reporting
- list items in an analytics group
- list generated bulk reports for a job
- social
- query real-time analytics reports
- delete group
- delete job
- delete a reporting job
- delete a bulk reporting job
- update group
slug: analytics-and-reporting
source_filename: analytics-and-reporting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: YouTube Analytics And Reporting\n  description: Workflow combining YouTube Analytics and Reporting APIs for comprehensive channel performance monitoring, custom\n    report generation, and bulk data export. Designed for data analysts, marketing teams, and content strategists.\n  tags:\n  - YouTube\n  - Analytics\n  - Reporting\n  - Metrics\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    YOUTUBE_OAUTH_TOKEN: YOUTUBE_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: youtube-analytics\n    baseUri: https://youtubeanalytics.googleapis.com/v2\n    description: YouTube Analytics API v2 for generating custom analytics reports and managing groups.\n    authentication:\n      type: bearer\n      token: '{{YOUTUBE_OAUTH_TOKEN}}'\n    resources:\n    - name: reports\n      path: /reports\n      description: Operations for querying YouTube Analytics report data\n      operations:\n   \
  \   - name: query-reports\n        method: GET\n        description: Retrieves YouTube Analytics data for a channel or content owner\n        inputParameters:\n        - name: ids\n          in: query\n          type: string\n          required: true\n          description: Identifies the YouTube channel or content owner for which the report is being retrieved.\n        - name: startDate\n          in: query\n          type: string\n          required: true\n          description: The start date for fetching YouTube Analytics data in YYYY-MM-DD format.\n        - name: endDate\n          in: query\n          type: string\n          required: true\n          description: The end date for fetching YouTube Analytics data in YYYY-MM-DD format.\n        - name: metrics\n          in: query\n          type: string\n          required: true\n          description: A comma-separated list of YouTube Analytics metrics, such as views or likes, dislikes.\n        - name: dimensions\n          in:\
  \ query\n          type: string\n          required: false\n          description: A comma-separated list of YouTube Analytics dimensions, such as video or country.\n        - name: filters\n          in: query\n          type: string\n          required: false\n          description: A list of filters that should be applied when retrieving YouTube Analytics data.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of rows to include in the response.\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: A comma-separated list of dimensions or metrics that determine the sort order.\n        - name: startIndex\n          in: query\n          type: integer\n          required: false\n          description: An index of the first entity to retrieve.\n        - name: currency\n          in: query\n          type: string\n          required:\
  \ false\n          description: The currency to which financial metrics should be converted.\n        - name: alt\n          in: query\n          type: string\n          required: false\n          description: Data format for the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      description: Operations for managing YouTube Analytics groups\n      operations:\n      - name: list-groups\n        method: GET\n        description: Returns a collection of groups that match the API request parameters\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of YouTube group IDs for the resources being retrieved.\n        - name: mine\n          in: query\n          type: boolean\n          required: false\n          description: Set to true to retrieve all\
  \ groups owned by the authenticated user.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set that should be returned.\n        - name: onBehalfOfContentOwner\n          in: query\n          type: string\n          required: false\n          description: Indicates that the request's authorization credentials identify a YouTube CMS user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-group\n        method: POST\n        description: Creates an Analytics group\n        inputParameters:\n        - name: onBehalfOfContentOwner\n          in: query\n          type: string\n          required: false\n          description: Indicates that the request's authorization credentials identify a YouTube CMS user.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: update-group\n        method: PUT\n        description: Modifies a group\n        inputParameters:\n        - name: onBehalfOfContentOwner\n          in: query\n          type: string\n          required: false\n          description: Indicates that the request's authorization credentials identify a YouTube CMS user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-group\n        method: DELETE\n        description: Deletes a group\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The id parameter specifies the YouTube group ID for the group being deleted.\n        - name: onBehalfOfContentOwner\n          in: query\n          type: string\n          required: false\n          description: Indicates that the request's authorization\
  \ credentials identify a YouTube CMS user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: group-items\n      path: /groupItems\n      description: Operations for managing items within YouTube Analytics groups\n      operations:\n      - name: list-group-items\n        method: GET\n        description: Returns a collection of group items that match the API request parameters\n        inputParameters:\n        - name: groupId\n          in: query\n          type: string\n          required: true\n          description: The id parameter specifies the unique ID of the group for which you want to retrieve group items.\n        - name: onBehalfOfContentOwner\n          in: query\n          type: string\n          required: false\n          description: Indicates that the request's authorization credentials identify a YouTube CMS user.\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n      - name: insert-group-item\n        method: POST\n        description: Creates a group item, adding a resource to an Analytics group\n        inputParameters:\n        - name: onBehalfOfContentOwner\n          in: query\n          type: string\n          required: false\n          description: Indicates that the request's authorization credentials identify a YouTube CMS user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-group-item\n        method: DELETE\n        description: Removes an item from a group\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The id parameter specifies the YouTube group item ID for the group item being deleted.\n        - name: onBehalfOfContentOwner\n          in: query\n          type: string\n  \
  \        required: false\n          description: Indicates that the request's authorization credentials identify a YouTube CMS user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: youtube-reporting\n    baseUri: https://youtubereporting.googleapis.com/v1\n    description: YouTube Reporting API v1 for scheduling reporting jobs and downloading bulk analytics data.\n    authentication:\n      type: bearer\n      token: '{{YOUTUBE_OAUTH_TOKEN}}'\n    resources:\n    - name: jobs\n      path: /jobs\n      description: Operations for managing YouTube reporting jobs\n      operations:\n      - name: create-job\n        method: POST\n        description: Creates a reporting job\n        inputParameters:\n        - name: onBehalfOfContentOwner\n          in: query\n          type: string\n          required: false\n          description: The content owner's external ID on which behalf\
  \ the user is acting on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-jobs\n        method: GET\n        description: Lists all reporting jobs that have been scheduled for the channel or content owner\n        inputParameters:\n        - name: onBehalfOfContentOwner\n          in: query\n          type: string\n          required: false\n          description: The content owner's external ID on which behalf the user is acting on.\n        - name: includeSystemManaged\n          in: query\n          type: boolean\n          required: false\n          description: If set to true, also returns system-managed reporting jobs.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: A token identifying a page of results to return.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n\
  \          description: The maximum number of items to return in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-details\n      path: /jobs/{jobId}\n      description: Operations for retrieving and deleting specific reporting jobs\n      operations:\n      - name: get-job\n        method: GET\n        description: Gets the metadata for a specific reporting job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The ID of the job to retrieve.\n        - name: onBehalfOfContentOwner\n          in: query\n          type: string\n          required: false\n          description: The content owner's external ID on which behalf the user is acting on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-job\n\
  \        method: DELETE\n        description: Deletes a reporting job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The ID of the job to delete.\n        - name: onBehalfOfContentOwner\n          in: query\n          type: string\n          required: false\n          description: The content owner's external ID on which behalf the user is acting on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /jobs/{jobId}/reports\n      description: Operations for retrieving generated reports\n      operations:\n      - name: list-reports\n        method: GET\n        description: Lists reports created by a specific reporting job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The ID of the job whose\
  \ reports are being listed.\n        - name: onBehalfOfContentOwner\n          in: query\n          type: string\n          required: false\n          description: The content owner's external ID on which behalf the user is acting on.\n        - name: createdAfter\n          in: query\n          type: string\n          required: false\n          description: If specified, only reports created after the specified date/time are returned.\n        - name: startTimeAtOrAfter\n          in: query\n          type: string\n          required: false\n          description: If specified, only reports covering data on or after this date are returned.\n        - name: startTimeBefore\n          in: query\n          type: string\n          required: false\n          description: If specified, only reports covering data before this date are returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: A token identifying a page\
  \ of results to return.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items to return in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: report-details\n      path: /jobs/{jobId}/reports/{reportId}\n      description: Operations for retrieving specific report metadata\n      operations:\n      - name: get-report\n        method: GET\n        description: Gets the metadata for a specific report including its download URL\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The ID of the job that created the report.\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: The ID of the report to retrieve.\n        - name: onBehalfOfContentOwner\n\
  \          in: query\n          type: string\n          required: false\n          description: The content owner's external ID on which behalf the user is acting on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: report-types\n      path: /reportTypes\n      description: Operations for listing available report types\n      operations:\n      - name: list-report-types\n        method: GET\n        description: Lists report types that the channel or content owner can retrieve\n        inputParameters:\n        - name: onBehalfOfContentOwner\n          in: query\n          type: string\n          required: false\n          description: The content owner's external ID on which behalf the user is acting on.\n        - name: includeSystemManaged\n          in: query\n          type: boolean\n          required: false\n          description: If set to true, also returns system-managed report types.\n\
  \        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: A token identifying a page of results to return.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items to return in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: analytics-reporting-api\n    description: Unified REST API for YouTube analytics and reporting workflows.\n    resources:\n    - path: /v1/reports\n      name: analytics-reports\n      description: Query real-time analytics reports\n      operations:\n      - method: GET\n        name: query-analytics\n        description: Query YouTube Analytics data\n        call: youtube-analytics.query-reports\n        outputParameters:\n        - type: object\n         \
  \ mapping: $.\n    - path: /v1/groups\n      name: analytics-groups\n      description: Manage analytics groups\n      operations:\n      - method: GET\n        name: list-groups\n        description: List analytics groups\n        call: youtube-analytics.list-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-group\n        description: Create an analytics group\n        call: youtube-analytics.insert-group\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-group\n        description: Update an analytics group\n        call: youtube-analytics.update-group\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-group\n        description: Delete an analytics group\n        call: youtube-analytics.delete-group\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /v1/group-items\n      name: group-items\n      description: Manage items within analytics groups\n      operations:\n      - method: GET\n        name: list-group-items\n        description: List items in an analytics group\n        call: youtube-analytics.list-group-items\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-group-item\n        description: Add an item to a group\n        call: youtube-analytics.insert-group-item\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: remove-group-item\n        description: Remove an item from a group\n        call: youtube-analytics.delete-group-item\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reporting-jobs\n      name: reporting-jobs\n      description: Manage bulk reporting jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description:\
  \ List reporting jobs\n        call: youtube-reporting.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-job\n        description: Create a reporting job\n        call: youtube-reporting.create-job\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-job\n        description: Delete a reporting job\n        call: youtube-reporting.delete-job\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bulk-reports\n      name: bulk-reports\n      description: Access generated bulk reports\n      operations:\n      - method: GET\n        name: list-bulk-reports\n        description: List generated reports for a job\n        call: youtube-reporting.list-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/report-types\n      name: report-types\n      description: Available\
  \ report types\n      operations:\n      - method: GET\n        name: list-report-types\n        description: List available report types\n        call: youtube-reporting.list-report-types\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: analytics-reporting-mcp\n    transport: http\n    description: MCP server for AI-assisted YouTube analytics and reporting.\n    tools:\n    - name: query-analytics\n      description: Query YouTube Analytics data with dimensions and metrics\n      hints:\n        readOnly: true\n        idempotent: true\n      call: youtube-analytics.query-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-analytics-groups\n      description: List YouTube Analytics groups\n      hints:\n        readOnly: true\n        idempotent: true\n      call: youtube-analytics.list-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ create-analytics-group\n      description: Create an analytics group for organizing data\n      hints:\n        readOnly: false\n        idempotent: false\n      call: youtube-analytics.insert-group\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-analytics-group\n      description: Update an analytics group\n      hints:\n        readOnly: false\n        idempotent: true\n      call: youtube-analytics.update-group\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-analytics-group\n      description: Delete an analytics group\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: youtube-analytics.delete-group\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-group-items\n      description: List items in an analytics group\n      hints:\n        readOnly: true\n        idempotent: true\n      call: youtube-analytics.list-group-items\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-group-item\n      description: Add an item to an analytics group\n      hints:\n        readOnly: false\n        idempotent: false\n      call: youtube-analytics.insert-group-item\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-group-item\n      description: Remove an item from an analytics group\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: youtube-analytics.delete-group-item\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reporting-jobs\n      description: List bulk reporting jobs\n      hints:\n        readOnly: true\n        idempotent: true\n      call: youtube-reporting.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-reporting-job\n      description: Create a new bulk reporting job\n      hints:\n        readOnly:\
  \ false\n        idempotent: false\n      call: youtube-reporting.create-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-reporting-job\n      description: Delete a bulk reporting job\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: youtube-reporting.delete-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bulk-reports\n      description: List generated bulk reports for a job\n      hints:\n        readOnly: true\n        idempotent: true\n      call: youtube-reporting.list-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bulk-report\n      description: Get metadata for a specific bulk report\n      hints:\n        readOnly: true\n        idempotent: true\n      call: youtube-reporting.get-report\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-report-types\n      description:\
  \ List available report types\n      hints:\n        readOnly: true\n        idempotent: true\n      call: youtube-reporting.list-report-types\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
