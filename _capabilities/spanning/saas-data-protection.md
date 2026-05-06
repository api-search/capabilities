---
categories: []
consumed_apis: []
description: Workflow capability for managing SaaS data protection across Microsoft 365, Google Workspace, and Salesforce via Spanning Backup. Enables IT admins and MSPs to manage backup license assignments, monitor backup status, and initiate data exports for recovery or compliance.
layout: capability
name: Spanning SaaS Data Protection
operations:
- description: List all users and their Spanning Backup license and status
  method: GET
  name: list-users
  path: /v1/users
- description: Assign a Spanning Backup license to a user
  method: POST
  name: assign-user
  path: /v1/users
- description: Get backup status for a specific user
  method: GET
  name: get-user
  path: /v1/users/{userKey}
- description: List all shared drives being backed up by Spanning
  method: GET
  name: list-shared-drives
  path: /v1/shared-drives
- description: List all export jobs with current status
  method: GET
  name: list-exports
  path: /v1/exports
- description: Initiate a data export for a user account
  method: POST
  name: initiate-export
  path: /v1/exports
- description: Get status and download URL for an export job
  method: GET
  name: get-export
  path: /v1/exports/{exportId}
personas: []
provider_name: Spanning
provider_slug: spanning
search_terms:
- get backup status and license details for a specific user by email or user key
- list all google workspace shared drives being backed up by spanning
- list all data export jobs with their current status (pending, in_progress, completed, failed)
- microsoft 365
- google workspace
- cloud backup
- data export jobs for recovery or compliance
- get the status and download url for a specific spanning export job
- saas backup
- get status and download url for an export job
- data protection
- google workspace shared drives under backup protection
- initiate export
- compliance
- backup-licensed users across protected saas platforms
- assign a spanning backup license to a user
- list all shared drives being backed up by spanning
- list all export jobs with current status
- individual user backup status
- get backup status for a specific user
- list all users and their spanning backup license and status
- list shared drives
- individual export job details
- get export
- list exports
- initiate a data export for a user account to enable recovery or compliance download
- get user
- remove a spanning backup license from a user
- list all users in spanning backup with their license assignment status and last backup time
- unassign user
- list users
- assign user
- assign a spanning backup license to a user to enable their data protection
- initiate a data export for a user account
- salesforce
slug: saas-data-protection
source_filename: saas-data-protection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spanning SaaS Data Protection\n  description: Workflow capability for managing SaaS data protection across Microsoft 365, Google Workspace, and Salesforce\n    via Spanning Backup. Enables IT admins and MSPs to manage backup license assignments, monitor backup status, and initiate\n    data exports for recovery or compliance.\n  tags:\n  - Data Protection\n  - SaaS Backup\n  - Cloud Backup\n  - Google Workspace\n  - Microsoft 365\n  - Compliance\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPANNING_API_TOKEN: SPANNING_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: spanning-gws\n    baseUri: https://api.spanningbackup.com\n    description: Spanning Backup for Google Workspace API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{SPANNING_API_TOKEN}}'\n      placement: header\n    resources:\n    - name: users\n      path: /users\n      description:\
  \ User backup license management\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users and their backup license status\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of users per page\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-user\n        method: GET\n        description: Get a single user's backup status\n        inputParameters:\n        - name: userKey\n          in: path\n          type: string\n          required: true\n          description: User email or unique ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: assign-user\n        method: POST\n        description: Assign a Spanning Backup license to a user\n        inputParameters:\n        - name: userKey\n          in: path\n          type: string\n          required: true\n          description: User email or unique ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unassign-user\n        method: POST\n        description: Remove a Spanning Backup license from a user\n        inputParameters:\n        - name: userKey\n          in: path\n          type: string\n          required: true\n          description: User email or unique ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shared-drives\n      path: /shared-drives\n      description: Google Workspace shared drive backup management\n      operations:\n      - name: list-shared-drives\n\
  \        method: GET\n        description: List all shared drives being backed up\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: export-shared-drive\n        method: POST\n        description: Initiate export of a shared drive's backed-up data\n        inputParameters:\n        - name: driveId\n          in: path\n          type: string\n          required: true\n          description: Shared drive unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: exports\n      path: /exports\n      description: Data export job management\n      operations:\n      - name: list-exports\n        method: GET\n        description: List all export jobs and their status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ initiate-export\n        method: POST\n        description: Initiate a data export for a user account\n        body:\n          type: json\n          data:\n            userKey: '{{tools.userKey}}'\n            includeGmail: '{{tools.includeGmail}}'\n            includeDrive: '{{tools.includeDrive}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-export\n        method: GET\n        description: Get the status and download URL for an export job\n        inputParameters:\n        - name: exportId\n          in: path\n          type: string\n          required: true\n          description: Export job unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: spanning-protection-api\n    description: Unified REST API for SaaS data protection management\
  \ via Spanning Backup.\n    resources:\n    - path: /v1/users\n      name: users\n      description: Backup-licensed users across protected SaaS platforms\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users and their Spanning Backup license and status\n        call: spanning-gws.list-users\n        with:\n          pageSize: rest.pageSize\n          pageToken: rest.pageToken\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: assign-user\n        description: Assign a Spanning Backup license to a user\n        call: spanning-gws.assign-user\n        with:\n          userKey: rest.userKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{userKey}\n      name: user\n      description: Individual user backup status\n      operations:\n      - method: GET\n        name: get-user\n        description: Get backup status for a specific user\n\
  \        call: spanning-gws.get-user\n        with:\n          userKey: rest.userKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/shared-drives\n      name: shared-drives\n      description: Google Workspace shared drives under backup protection\n      operations:\n      - method: GET\n        name: list-shared-drives\n        description: List all shared drives being backed up by Spanning\n        call: spanning-gws.list-shared-drives\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/exports\n      name: exports\n      description: Data export jobs for recovery or compliance\n      operations:\n      - method: GET\n        name: list-exports\n        description: List all export jobs with current status\n        call: spanning-gws.list-exports\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: initiate-export\n        description: Initiate\
  \ a data export for a user account\n        call: spanning-gws.initiate-export\n        with:\n          userKey: rest.body.userKey\n          includeGmail: rest.body.includeGmail\n          includeDrive: rest.body.includeDrive\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/exports/{exportId}\n      name: export\n      description: Individual export job details\n      operations:\n      - method: GET\n        name: get-export\n        description: Get status and download URL for an export job\n        call: spanning-gws.get-export\n        with:\n          exportId: rest.exportId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: spanning-protection-mcp\n    transport: http\n    description: MCP server for AI-assisted SaaS backup management and data recovery via Spanning.\n    tools:\n    - name: list-users\n      description: List all users in Spanning Backup with their license\
  \ assignment status and last backup time\n      hints:\n        readOnly: true\n      call: spanning-gws.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get backup status and license details for a specific user by email or user key\n      hints:\n        readOnly: true\n      call: spanning-gws.get-user\n      with:\n        userKey: tools.userKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: assign-user\n      description: Assign a Spanning Backup license to a user to enable their data protection\n      hints:\n        readOnly: false\n      call: spanning-gws.assign-user\n      with:\n        userKey: tools.userKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unassign-user\n      description: Remove a Spanning Backup license from a user\n      hints:\n        readOnly: false\n        destructive: false\n      call: spanning-gws.unassign-user\n\
  \      with:\n        userKey: tools.userKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-shared-drives\n      description: List all Google Workspace shared drives being backed up by Spanning\n      hints:\n        readOnly: true\n      call: spanning-gws.list-shared-drives\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-exports\n      description: List all data export jobs with their current status (PENDING, IN_PROGRESS, COMPLETED, FAILED)\n      hints:\n        readOnly: true\n      call: spanning-gws.list-exports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: initiate-export\n      description: Initiate a data export for a user account to enable recovery or compliance download\n      hints:\n        readOnly: false\n      call: spanning-gws.initiate-export\n      with:\n        userKey: tools.userKey\n        includeGmail: tools.includeGmail\n        includeDrive: tools.includeDrive\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-export\n      description: Get the status and download URL for a specific Spanning export job\n      hints:\n        readOnly: true\n      call: spanning-gws.get-export\n      with:\n        exportId: tools.exportId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spanning/refs/heads/main/capabilities/saas-data-protection.yaml
tags:
- Data Protection
- SaaS Backup
- Cloud Backup
- Google Workspace
- Microsoft 365
- Compliance
tools:
- description: List all users in Spanning Backup with their license assignment status and last backup time
  hints:
    readOnly: true
  name: list-users
- description: Get backup status and license details for a specific user by email or user key
  hints:
    readOnly: true
  name: get-user
- description: Assign a Spanning Backup license to a user to enable their data protection
  hints:
    readOnly: false
  name: assign-user
- description: Remove a Spanning Backup license from a user
  hints:
    destructive: false
    readOnly: false
  name: unassign-user
- description: List all Google Workspace shared drives being backed up by Spanning
  hints:
    readOnly: true
  name: list-shared-drives
- description: List all data export jobs with their current status (PENDING, IN_PROGRESS, COMPLETED, FAILED)
  hints:
    readOnly: true
  name: list-exports
- description: Initiate a data export for a user account to enable recovery or compliance download
  hints:
    readOnly: false
  name: initiate-export
- description: Get the status and download URL for a specific Spanning export job
  hints:
    readOnly: true
  name: get-export
---
