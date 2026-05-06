---
categories: []
consumed_apis: []
description: The ClickUp Comments API provides endpoints for creating and retrieving comments on tasks, views, and lists. Comments support rich text formatting, mentions, and attachments. Developers can use this API to build integrations that synchronize discussions between ClickUp and other collaboration tools, or to programmatically add status updates and notes to tasks.
layout: capability
name: ClickUp Comments API
operations:
- description: Get task comments
  method: GET
  name: gettaskcomments
  path: /task/{task_id}/comment
- description: Create a task comment
  method: POST
  name: createtaskcomment
  path: /task/{task_id}/comment
- description: Get view comments
  method: GET
  name: getviewcomments
  path: /view/{view_id}/comment
- description: Create a view comment
  method: POST
  name: createviewcomment
  path: /view/{view_id}/comment
- description: Get list comments
  method: GET
  name: getlistcomments
  path: /list/{list_id}/comment
- description: Create a list comment
  method: POST
  name: createlistcomment
  path: /list/{list_id}/comment
- description: Update a comment
  method: PUT
  name: updatecomment
  path: /comment/{comment_id}
- description: Delete a comment
  method: DELETE
  name: deletecomment
  path: /comment/{comment_id}
personas: []
provider_name: clickup
provider_slug: clickup
search_terms:
- gettaskcomments
- get task comments
- create a list comment
- createlistcomment
- updatecomment
- api
- createviewcomment
- getlistcomments
- get list comments
- create a task comment
- clickup
- createtaskcomment
- getviewcomments
- create a view comment
- update a comment
- deletecomment
- delete a comment
- get view comments
slug: clickup-capability
source_filename: clickup-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ClickUp Comments API\n  description: The ClickUp Comments API provides endpoints for creating and retrieving comments on tasks, views, and lists.\n    Comments support rich text formatting, mentions, and attachments. Developers can use this API to build integrations that\n    synchronize discussions between ClickUp and other collaboration tools, or to programmatically add status updates and notes\n    to tasks.\n  tags:\n  - Clickup\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: clickup\n    baseUri: https://api.clickup.com/api/v2\n    description: ClickUp Comments API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CLICKUP_TOKEN}}'\n    resources:\n    - name: task-task-id-comment\n      path: /task/{task_id}/comment\n      operations:\n      - name: gettaskcomments\n        method: GET\n        description: Get task comments\n        inputParameters:\n\
  \        - name: custom_task_ids\n          in: query\n          type: boolean\n          description: If you want to reference a task by its custom task ID, this value must be true.\n        - name: team_id\n          in: query\n          type: integer\n          description: Required when custom_task_ids is set to true. The Workspace ID.\n        - name: start\n          in: query\n          type: integer\n          description: Unix timestamp in milliseconds to start from for pagination.\n        - name: start_id\n          in: query\n          type: string\n          description: Comment ID to start from for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtaskcomment\n        method: POST\n        description: Create a task comment\n        inputParameters:\n        - name: custom_task_ids\n          in: query\n          type: boolean\n          description: If you want to\
  \ reference a task by its custom task ID, this value must be true.\n        - name: team_id\n          in: query\n          type: integer\n          description: Required when custom_task_ids is set to true. The Workspace ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: view-view-id-comment\n      path: /view/{view_id}/comment\n      operations:\n      - name: getviewcomments\n        method: GET\n        description: Get view comments\n        inputParameters:\n        - name: start\n          in: query\n          type: integer\n          description: Unix timestamp in milliseconds to start from for pagination.\n        - name: start_id\n          in: query\n          type: string\n          description: Comment ID to start from for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createviewcomment\n\
  \        method: POST\n        description: Create a view comment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-list-id-comment\n      path: /list/{list_id}/comment\n      operations:\n      - name: getlistcomments\n        method: GET\n        description: Get list comments\n        inputParameters:\n        - name: start\n          in: query\n          type: integer\n          description: Unix timestamp in milliseconds to start from for pagination.\n        - name: start_id\n          in: query\n          type: string\n          description: Comment ID to start from for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlistcomment\n        method: POST\n        description: Create a list comment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: comment-comment-id\n      path: /comment/{comment_id}\n      operations:\n      - name: updatecomment\n        method: PUT\n        description: Update a comment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecomment\n        method: DELETE\n        description: Delete a comment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: clickup-rest\n    description: REST adapter for ClickUp Comments API.\n    resources:\n    - path: /task/{task_id}/comment\n      name: gettaskcomments\n      operations:\n      - method: GET\n        name: gettaskcomments\n        description: Get task comments\n        call: clickup.gettaskcomments\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /task/{task_id}/comment\n      name: createtaskcomment\n      operations:\n      - method: POST\n        name: createtaskcomment\n        description: Create a task comment\n        call: clickup.createtaskcomment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /view/{view_id}/comment\n      name: getviewcomments\n      operations:\n      - method: GET\n        name: getviewcomments\n        description: Get view comments\n        call: clickup.getviewcomments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /view/{view_id}/comment\n      name: createviewcomment\n      operations:\n      - method: POST\n        name: createviewcomment\n        description: Create a view comment\n        call: clickup.createviewcomment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /list/{list_id}/comment\n      name: getlistcomments\n      operations:\n      - method: GET\n\
  \        name: getlistcomments\n        description: Get list comments\n        call: clickup.getlistcomments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /list/{list_id}/comment\n      name: createlistcomment\n      operations:\n      - method: POST\n        name: createlistcomment\n        description: Create a list comment\n        call: clickup.createlistcomment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /comment/{comment_id}\n      name: updatecomment\n      operations:\n      - method: PUT\n        name: updatecomment\n        description: Update a comment\n        call: clickup.updatecomment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /comment/{comment_id}\n      name: deletecomment\n      operations:\n      - method: DELETE\n        name: deletecomment\n        description: Delete a comment\n        call: clickup.deletecomment\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: clickup-mcp\n    transport: http\n    description: MCP adapter for ClickUp Comments API for AI agent use.\n    tools:\n    - name: gettaskcomments\n      description: Get task comments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: clickup.gettaskcomments\n      with:\n        custom_task_ids: tools.custom_task_ids\n        team_id: tools.team_id\n        start: tools.start\n        start_id: tools.start_id\n      inputParameters:\n      - name: custom_task_ids\n        type: boolean\n        description: If you want to reference a task by its custom task ID, this value must be true.\n      - name: team_id\n        type: integer\n        description: Required when custom_task_ids is set to true. The Workspace ID.\n      - name: start\n        type: integer\n        description: Unix timestamp in milliseconds to start from for pagination.\n\
  \      - name: start_id\n        type: string\n        description: Comment ID to start from for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtaskcomment\n      description: Create a task comment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: clickup.createtaskcomment\n      with:\n        custom_task_ids: tools.custom_task_ids\n        team_id: tools.team_id\n      inputParameters:\n      - name: custom_task_ids\n        type: boolean\n        description: If you want to reference a task by its custom task ID, this value must be true.\n      - name: team_id\n        type: integer\n        description: Required when custom_task_ids is set to true. The Workspace ID.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getviewcomments\n      description: Get view comments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: clickup.getviewcomments\n      with:\n        start: tools.start\n        start_id: tools.start_id\n      inputParameters:\n      - name: start\n        type: integer\n        description: Unix timestamp in milliseconds to start from for pagination.\n      - name: start_id\n        type: string\n        description: Comment ID to start from for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createviewcomment\n      description: Create a view comment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: clickup.createviewcomment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlistcomments\n      description: Get list comments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: clickup.getlistcomments\n      with:\n        start: tools.start\n        start_id: tools.start_id\n      inputParameters:\n\
  \      - name: start\n        type: integer\n        description: Unix timestamp in milliseconds to start from for pagination.\n      - name: start_id\n        type: string\n        description: Comment ID to start from for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createlistcomment\n      description: Create a list comment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: clickup.createlistcomment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecomment\n      description: Update a comment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: clickup.updatecomment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecomment\n      description: Delete a comment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n    \
  \  call: clickup.deletecomment\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CLICKUP_TOKEN: CLICKUP_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/clickup/refs/heads/main/capabilities/clickup-capability.yaml
tags:
- Clickup
- API
tools:
- description: Get task comments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettaskcomments
- description: Create a task comment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtaskcomment
- description: Get view comments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getviewcomments
- description: Create a view comment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createviewcomment
- description: Get list comments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlistcomments
- description: Create a list comment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlistcomment
- description: Update a comment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecomment
- description: Delete a comment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecomment
---
