---
categories: []
consumed_apis: []
description: The Gong Auditing API enables retrieval of audit log data by type and time range, providing visibility into user actions and system events for compliance and security monitoring.
layout: capability
name: Gong Auditing API
operations:
- description: Gong Retrieve audit logs by type and time range
  method: GET
  name: retrieveauditlogs
  path: /logs
personas: []
provider_name: Gong
provider_slug: gong
search_terms:
- gong retrieve audit logs by type and time range
- retrieveauditlogs
- gong
- api
slug: gong-capability
source_filename: gong-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Gong Auditing API\n  description: The Gong Auditing API enables retrieval of audit log data by type and time range, providing visibility into\n    user actions and system events for compliance and security monitoring.\n  tags:\n  - Gong\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: gong\n    baseUri: https://api.gong.io/v2\n    description: Gong Auditing API HTTP API.\n    authentication:\n      type: basic\n      username: '{{GONG_USERNAME}}'\n      password: '{{GONG_PASSWORD}}'\n    resources:\n    - name: logs\n      path: /logs\n      operations:\n      - name: retrieveauditlogs\n        method: GET\n        description: Gong Retrieve audit logs by type and time range\n        inputParameters:\n        - name: logType\n          in: query\n          type: string\n          required: true\n          description: The type of audit log to retrieve (e.g., UserAction,\
  \ SystemEvent, ConfigChange).\n        - name: fromDateTime\n          in: query\n          type: string\n          required: true\n          description: The start date and time for the log filter in ISO-8601 format.\n        - name: toDateTime\n          in: query\n          type: string\n          required: true\n          description: The end date and time for the log filter in ISO-8601 format.\n        - name: cursor\n          in: query\n          type: string\n          description: A cursor for pagination. Pass the cursor from the previous response to retrieve the next page of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: gong-rest\n    description: REST adapter for Gong Auditing API.\n    resources:\n    - path: /logs\n      name: retrieveauditlogs\n      operations:\n      - method: GET\n        name: retrieveauditlogs\n       \
  \ description: Gong Retrieve audit logs by type and time range\n        call: gong.retrieveauditlogs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: gong-mcp\n    transport: http\n    description: MCP adapter for Gong Auditing API for AI agent use.\n    tools:\n    - name: retrieveauditlogs\n      description: Gong Retrieve audit logs by type and time range\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: gong.retrieveauditlogs\n      with:\n        logType: tools.logType\n        fromDateTime: tools.fromDateTime\n        toDateTime: tools.toDateTime\n        cursor: tools.cursor\n      inputParameters:\n      - name: logType\n        type: string\n        description: The type of audit log to retrieve (e.g., UserAction, SystemEvent, ConfigChange).\n        required: true\n      - name: fromDateTime\n        type: string\n        description: The start date and\
  \ time for the log filter in ISO-8601 format.\n        required: true\n      - name: toDateTime\n        type: string\n        description: The end date and time for the log filter in ISO-8601 format.\n        required: true\n      - name: cursor\n        type: string\n        description: A cursor for pagination. Pass the cursor from the previous response to retrieve the next page of results.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GONG_USERNAME: GONG_USERNAME\n    GONG_PASSWORD: GONG_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/gong/refs/heads/main/capabilities/gong-capability.yaml
tags:
- Gong
- API
tools:
- description: Gong Retrieve audit logs by type and time range
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrieveauditlogs
---
