---
categories: []
consumed_apis: []
description: The Google AppSheet API enables programmatic access to AppSheet applications, allowing developers to add, update, delete, and find records in AppSheet tables, as well as invoke predefined AppSheet actions via a REST interface.
layout: capability
name: Google AppSheet API
operations:
- description: Google AppSheet Invoke Table Action
  method: POST
  name: invokeaction
  path: /apps/{appId}/tables/{tableName}/Action
personas: []
provider_name: Google AppSheet
provider_slug: google-appsheet
search_terms:
- no-code
- data
- low-code
- tables
- google
- api
- appsheet
- applications
- google appsheet invoke table action
- invokeaction
slug: google-appsheet-capability
source_filename: google-appsheet-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google AppSheet API\n  description: The Google AppSheet API enables programmatic access to AppSheet applications, allowing developers to add, update,\n    delete, and find records in AppSheet tables, as well as invoke predefined AppSheet actions via a REST interface.\n  tags:\n  - Google\n  - Appsheet\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-appsheet\n    baseUri: https://api.appsheet.com/api/v2\n    description: Google AppSheet API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: ApplicationAccessKey\n      value: '{{GOOGLE_APPSHEET_TOKEN}}'\n    resources:\n    - name: apps-appid-tables-tablename-action\n      path: /apps/{appId}/tables/{tableName}/Action\n      operations:\n      - name: invokeaction\n        method: POST\n        description: Google AppSheet Invoke Table Action\n        inputParameters:\n        - name:\
  \ appId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the AppSheet application.\n        - name: tableName\n          in: path\n          type: string\n          required: true\n          description: The name of the table to perform the action on.\n        - name: applicationAccessKey\n          in: query\n          type: string\n          description: The application access key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-appsheet-rest\n    description: REST adapter for Google AppSheet API.\n    resources:\n    - path: /apps/{appId}/tables/{tableName}/Action\n      name: invokeaction\n      operations:\n      - method: POST\n        name: invokeaction\n        description: Google AppSheet Invoke Table Action\n        call: google-appsheet.invokeaction\n\
  \        with:\n          appId: rest.appId\n          tableName: rest.tableName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-appsheet-mcp\n    transport: http\n    description: MCP adapter for Google AppSheet API for AI agent use.\n    tools:\n    - name: invokeaction\n      description: Google AppSheet Invoke Table Action\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-appsheet.invokeaction\n      with:\n        appId: tools.appId\n        tableName: tools.tableName\n        applicationAccessKey: tools.applicationAccessKey\n      inputParameters:\n      - name: appId\n        type: string\n        description: The unique identifier of the AppSheet application.\n        required: true\n      - name: tableName\n        type: string\n        description: The name of the table to perform the action on.\n        required: true\n      - name:\
  \ applicationAccessKey\n        type: string\n        description: The application access key for authentication.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_APPSHEET_TOKEN: GOOGLE_APPSHEET_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-appsheet/refs/heads/main/capabilities/google-appsheet-capability.yaml
tags:
- Google
- Appsheet
- API
tools:
- description: Google AppSheet Invoke Table Action
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invokeaction
---
