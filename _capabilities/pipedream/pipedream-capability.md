---
categories: []
consumed_apis: []
description: The Pipedream REST API allows developers to programmatically create and manage workflows, event sources, subscriptions, and user resources. Authentication uses Bearer tokens (OAuth access tokens or user API keys). List endpoints support cursor-based pagination via limit, after, and before parameters.
layout: capability
name: Pipedream REST API
operations:
- description: Get the authenticated user
  method: GET
  name: getme
  path: /users/me
- description: List event sources for the authenticated user
  method: GET
  name: listsources
  path: /users/me/sources
- description: Create an event source
  method: POST
  name: createsource
  path: /users/me/sources
- description: Get an event source
  method: GET
  name: getsource
  path: /sources/{id}
- description: Delete an event source
  method: DELETE
  name: deletesource
  path: /sources/{id}
- description: List subscriptions
  method: GET
  name: listsubscriptions
  path: /subscriptions
- description: Create a subscription
  method: POST
  name: createsubscription
  path: /subscriptions
- description: Delete a subscription
  method: DELETE
  name: deletesubscription
  path: /subscriptions/{id}
- description: Get a workflow
  method: GET
  name: getworkflow
  path: /workflows/{id}
- description: Create a Connect token
  method: POST
  name: createconnecttoken
  path: /connect/{project_id}/tokens
- description: List connected accounts for a project
  method: GET
  name: listconnectaccounts
  path: /connect/{project_id}/accounts
personas: []
provider_name: Pipedream
provider_slug: pipedream
search_terms:
- create a connect token
- list event sources for the authenticated user
- create a subscription
- api
- get the authenticated user
- createsubscription
- listsubscriptions
- create an event source
- listconnectaccounts
- getsource
- listsources
- createconnecttoken
- delete an event source
- getme
- deletesubscription
- pipedream
- getworkflow
- procode_api_composition
- list subscriptions
- get an event source
- get a workflow
- deletesource
- list connected accounts for a project
- delete a subscription
- workflows
- createsource
slug: pipedream-capability
source_filename: pipedream-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Pipedream REST API\n  description: The Pipedream REST API allows developers to programmatically create and manage workflows, event sources, subscriptions,\n    and user resources. Authentication uses Bearer tokens (OAuth access tokens or user API keys). List endpoints support cursor-based\n    pagination via limit, after, and before parameters.\n  tags:\n  - Pipedream\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pipedream\n    baseUri: https://api.pipedream.com/v1\n    description: Pipedream REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PIPEDREAM_TOKEN}}'\n    resources:\n    - name: users-me\n      path: /users/me\n      operations:\n      - name: getme\n        method: GET\n        description: Get the authenticated user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n    - name: users-me-sources\n      path: /users/me/sources\n      operations:\n      - name: listsources\n        method: GET\n        description: List event sources for the authenticated user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsource\n        method: POST\n        description: Create an event source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sources-id\n      path: /sources/{id}\n      operations:\n      - name: getsource\n        method: GET\n        description: Get an event source\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesource\n       \
  \ method: DELETE\n        description: Delete an event source\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions\n      path: /subscriptions\n      operations:\n      - name: listsubscriptions\n        method: GET\n        description: List subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsubscription\n        method: POST\n        description: Create a subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-id\n      path: /subscriptions/{id}\n      operations:\n      - name: deletesubscription\n        method: DELETE\n        description: Delete a subscription\n\
  \        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows-id\n      path: /workflows/{id}\n      operations:\n      - name: getworkflow\n        method: GET\n        description: Get a workflow\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connect-project-id-tokens\n      path: /connect/{project_id}/tokens\n      operations:\n      - name: createconnecttoken\n        method: POST\n        description: Create a Connect token\n        inputParameters:\n        - name: project_id\n          in: path\n          type: string\n          required: true\n        - name: X-PD-Environment\n\
  \          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connect-project-id-accounts\n      path: /connect/{project_id}/accounts\n      operations:\n      - name: listconnectaccounts\n        method: GET\n        description: List connected accounts for a project\n        inputParameters:\n        - name: project_id\n          in: path\n          type: string\n          required: true\n        - name: X-PD-Environment\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pipedream-rest\n    description: REST adapter for Pipedream REST API.\n    resources:\n    - path: /users/me\n      name: getme\n      operations:\n      - method:\
  \ GET\n        name: getme\n        description: Get the authenticated user\n        call: pipedream.getme\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/me/sources\n      name: listsources\n      operations:\n      - method: GET\n        name: listsources\n        description: List event sources for the authenticated user\n        call: pipedream.listsources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/me/sources\n      name: createsource\n      operations:\n      - method: POST\n        name: createsource\n        description: Create an event source\n        call: pipedream.createsource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sources/{id}\n      name: getsource\n      operations:\n      - method: GET\n        name: getsource\n        description: Get an event source\n        call: pipedream.getsource\n        with:\n          id: rest.id\n  \
  \      outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sources/{id}\n      name: deletesource\n      operations:\n      - method: DELETE\n        name: deletesource\n        description: Delete an event source\n        call: pipedream.deletesource\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions\n      name: listsubscriptions\n      operations:\n      - method: GET\n        name: listsubscriptions\n        description: List subscriptions\n        call: pipedream.listsubscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions\n      name: createsubscription\n      operations:\n      - method: POST\n        name: createsubscription\n        description: Create a subscription\n        call: pipedream.createsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{id}\n\
  \      name: deletesubscription\n      operations:\n      - method: DELETE\n        name: deletesubscription\n        description: Delete a subscription\n        call: pipedream.deletesubscription\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/{id}\n      name: getworkflow\n      operations:\n      - method: GET\n        name: getworkflow\n        description: Get a workflow\n        call: pipedream.getworkflow\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /connect/{project_id}/tokens\n      name: createconnecttoken\n      operations:\n      - method: POST\n        name: createconnecttoken\n        description: Create a Connect token\n        call: pipedream.createconnecttoken\n        with:\n          project_id: rest.project_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /connect/{project_id}/accounts\n\
  \      name: listconnectaccounts\n      operations:\n      - method: GET\n        name: listconnectaccounts\n        description: List connected accounts for a project\n        call: pipedream.listconnectaccounts\n        with:\n          project_id: rest.project_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pipedream-mcp\n    transport: http\n    description: MCP adapter for Pipedream REST API for AI agent use.\n    tools:\n    - name: getme\n      description: Get the authenticated user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pipedream.getme\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsources\n      description: List event sources for the authenticated user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pipedream.listsources\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createsource\n      description: Create an event source\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pipedream.createsource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsource\n      description: Get an event source\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pipedream.getsource\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesource\n      description: Delete an event source\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: pipedream.deletesource\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type:\
  \ string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsubscriptions\n      description: List subscriptions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pipedream.listsubscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsubscription\n      description: Create a subscription\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pipedream.createsubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesubscription\n      description: Delete a subscription\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: pipedream.deletesubscription\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description:\
  \ id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkflow\n      description: Get a workflow\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pipedream.getworkflow\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createconnecttoken\n      description: Create a Connect token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pipedream.createconnecttoken\n      with:\n        project_id: tools.project_id\n      inputParameters:\n      - name: project_id\n        type: string\n        description: project_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listconnectaccounts\n      description:\
  \ List connected accounts for a project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pipedream.listconnectaccounts\n      with:\n        project_id: tools.project_id\n      inputParameters:\n      - name: project_id\n        type: string\n        description: project_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PIPEDREAM_TOKEN: PIPEDREAM_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pipedream/refs/heads/main/capabilities/pipedream-capability.yaml
tags:
- Pipedream
- API
tools:
- description: Get the authenticated user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getme
- description: List event sources for the authenticated user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsources
- description: Create an event source
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsource
- description: Get an event source
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsource
- description: Delete an event source
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesource
- description: List subscriptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsubscriptions
- description: Create a subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsubscription
- description: Delete a subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesubscription
- description: Get a workflow
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflow
- description: Create a Connect token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconnecttoken
- description: List connected accounts for a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconnectaccounts
---
