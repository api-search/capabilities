---
categories: []
consumed_apis: []
description: Cflow's business automation workflow offers REST APIs for applications, services, and programming components. The API provides a way to connect with external applications and update their data in Cflow's process automation engine. You can list workflows, initiate or approve requests, and manage users, roles, and permissions using the external REST API. All business objects and integration object structures are stored as REST API resources and are available in JSON or XML format.
layout: capability
name: Cflow API
operations:
- description: Cflow List Workflows
  method: GET
  name: getworkflows
  path: /integromat/api/cflow/getworkflows
- description: Cflow Get Workflow
  method: GET
  name: getworkflow
  path: /integromat/api/cflow/workflows/{workflowId}
- description: Cflow List Requests
  method: GET
  name: listrequests
  path: /integromat/api/cflow/workflows/{workflowId}/requests
- description: Cflow Create Request
  method: POST
  name: createrequest
  path: /integromat/api/cflow/workflows/{workflowId}/requests
- description: Cflow Get Request
  method: GET
  name: getrequest
  path: /integromat/api/cflow/workflows/{workflowId}/requests/{requestId}
- description: Cflow Update Request
  method: PUT
  name: updaterequest
  path: /integromat/api/cflow/workflows/{workflowId}/requests/{requestId}
- description: Cflow Delete Request
  method: DELETE
  name: deleterequest
  path: /integromat/api/cflow/workflows/{workflowId}/requests/{requestId}
- description: Cflow Approve Request
  method: POST
  name: approverequest
  path: /integromat/api/cflow/workflows/{workflowId}/requests/{requestId}/approve
- description: Cflow Reject Request
  method: POST
  name: rejectrequest
  path: /integromat/api/cflow/workflows/{workflowId}/requests/{requestId}/reject
- description: Cflow Create Draft Request
  method: POST
  name: createdraftrequest
  path: /integromat/api/cflow/workflows/{workflowId}/drafts
- description: Cflow List Users
  method: GET
  name: listusers
  path: /integromat/api/cflow/users
- description: Cflow List Roles
  method: GET
  name: listroles
  path: /integromat/api/cflow/roles
personas: []
provider_name: Cflow
provider_slug: cflow
search_terms:
- cflow list users
- no-code
- updaterequest
- cflow get workflow
- cflow update request
- createdraftrequest
- cflow create draft request
- automations
- cflow create request
- cflow list requests
- deleterequest
- cflow list roles
- integrations
- listroles
- cflow reject request
- cflow get request
- api
- workflows
- business process automation
- rejectrequest
- getrequest
- getworkflows
- cflow
- rules
- getworkflow
- approverequest
- cflow delete request
- listrequests
- cflow approve request
- platform
- cflow list workflows
- listusers
- createrequest
- protocols
slug: cflow-capability
source_filename: cflow-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Cflow API\n  description: Cflow's business automation workflow offers REST APIs for applications, services, and programming components.\n    The API provides a way to connect with external applications and update their data in Cflow's process automation engine.\n    You can list workflows, initiate or approve requests, and manage users, roles, and permissions using the external REST\n    API. All business objects and integration object structures are stored as REST API resources and are available in JSON\n    or XML format.\n  tags:\n  - Cflow\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: cflow\n    baseUri: https://us.cflowapps.com\n    description: Cflow API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: apikey\n      value: '{{CFLOW_TOKEN}}'\n    resources:\n    - name: integromat-api-cflow-getworkflows\n      path: /integromat/api/cflow/getworkflows\n\
  \      operations:\n      - name: getworkflows\n        method: GET\n        description: Cflow List Workflows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integromat-api-cflow-workflows-workflowid\n      path: /integromat/api/cflow/workflows/{workflowId}\n      operations:\n      - name: getworkflow\n        method: GET\n        description: Cflow Get Workflow\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integromat-api-cflow-workflows-workflowid-reques\n      path: /integromat/api/cflow/workflows/{workflowId}/requests\n      operations:\n      - name: listrequests\n        method: GET\n        description: Cflow List\
  \ Requests\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrequest\n        method: POST\n        description: Cflow Create Request\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integromat-api-cflow-workflows-workflowid-reques\n      path: /integromat/api/cflow/workflows/{workflowId}/requests/{requestId}\n      operations:\n      - name: getrequest\n        method: GET\n        description: Cflow Get Request\n        inputParameters:\n\
  \        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workflow.\n        - name: requestId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterequest\n        method: PUT\n        description: Cflow Update Request\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workflow.\n        - name: requestId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n      - name: deleterequest\n        method: DELETE\n        description: Cflow Delete Request\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workflow.\n        - name: requestId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integromat-api-cflow-workflows-workflowid-reques\n      path: /integromat/api/cflow/workflows/{workflowId}/requests/{requestId}/approve\n      operations:\n      - name: approverequest\n        method: POST\n        description: Cflow Approve Request\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: The\
  \ unique identifier of the workflow.\n        - name: requestId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integromat-api-cflow-workflows-workflowid-reques\n      path: /integromat/api/cflow/workflows/{workflowId}/requests/{requestId}/reject\n      operations:\n      - name: rejectrequest\n        method: POST\n        description: Cflow Reject Request\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workflow.\n        - name: requestId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the request.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: integromat-api-cflow-workflows-workflowid-drafts\n      path: /integromat/api/cflow/workflows/{workflowId}/drafts\n      operations:\n      - name: createdraftrequest\n        method: POST\n        description: Cflow Create Draft Request\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integromat-api-cflow-users\n      path: /integromat/api/cflow/users\n      operations:\n      - name: listusers\n        method: GET\n        description: Cflow List Users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integromat-api-cflow-roles\n      path: /integromat/api/cflow/roles\n\
  \      operations:\n      - name: listroles\n        method: GET\n        description: Cflow List Roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cflow-rest\n    description: REST adapter for Cflow API.\n    resources:\n    - path: /integromat/api/cflow/getworkflows\n      name: getworkflows\n      operations:\n      - method: GET\n        name: getworkflows\n        description: Cflow List Workflows\n        call: cflow.getworkflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integromat/api/cflow/workflows/{workflowId}\n      name: getworkflow\n      operations:\n      - method: GET\n        name: getworkflow\n        description: Cflow Get Workflow\n        call: cflow.getworkflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /integromat/api/cflow/workflows/{workflowId}/requests\n      name: listrequests\n      operations:\n      - method: GET\n        name: listrequests\n        description: Cflow List Requests\n        call: cflow.listrequests\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integromat/api/cflow/workflows/{workflowId}/requests\n      name: createrequest\n      operations:\n      - method: POST\n        name: createrequest\n        description: Cflow Create Request\n        call: cflow.createrequest\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integromat/api/cflow/workflows/{workflowId}/requests/{requestId}\n      name: getrequest\n      operations:\n      - method: GET\n        name: getrequest\n        description: Cflow Get Request\n        call: cflow.getrequest\n        with:\n  \
  \        workflowId: rest.workflowId\n          requestId: rest.requestId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integromat/api/cflow/workflows/{workflowId}/requests/{requestId}\n      name: updaterequest\n      operations:\n      - method: PUT\n        name: updaterequest\n        description: Cflow Update Request\n        call: cflow.updaterequest\n        with:\n          workflowId: rest.workflowId\n          requestId: rest.requestId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integromat/api/cflow/workflows/{workflowId}/requests/{requestId}\n      name: deleterequest\n      operations:\n      - method: DELETE\n        name: deleterequest\n        description: Cflow Delete Request\n        call: cflow.deleterequest\n        with:\n          workflowId: rest.workflowId\n          requestId: rest.requestId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /integromat/api/cflow/workflows/{workflowId}/requests/{requestId}/approve\n      name: approverequest\n      operations:\n      - method: POST\n        name: approverequest\n        description: Cflow Approve Request\n        call: cflow.approverequest\n        with:\n          workflowId: rest.workflowId\n          requestId: rest.requestId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integromat/api/cflow/workflows/{workflowId}/requests/{requestId}/reject\n      name: rejectrequest\n      operations:\n      - method: POST\n        name: rejectrequest\n        description: Cflow Reject Request\n        call: cflow.rejectrequest\n        with:\n          workflowId: rest.workflowId\n          requestId: rest.requestId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integromat/api/cflow/workflows/{workflowId}/drafts\n      name: createdraftrequest\n      operations:\n      - method: POST\n        name: createdraftrequest\n\
  \        description: Cflow Create Draft Request\n        call: cflow.createdraftrequest\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integromat/api/cflow/users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: Cflow List Users\n        call: cflow.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integromat/api/cflow/roles\n      name: listroles\n      operations:\n      - method: GET\n        name: listroles\n        description: Cflow List Roles\n        call: cflow.listroles\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cflow-mcp\n    transport: http\n    description: MCP adapter for Cflow API for AI agent use.\n    tools:\n    - name: getworkflows\n      description: Cflow List Workflows\n      hints:\n  \
  \      readOnly: true\n        destructive: false\n        idempotent: true\n      call: cflow.getworkflows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkflow\n      description: Cflow Get Workflow\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cflow.getworkflow\n      with:\n        workflowId: tools.workflowId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: The unique identifier of the workflow.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrequests\n      description: Cflow List Requests\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cflow.listrequests\n      with:\n        workflowId: tools.workflowId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: The unique identifier of the\
  \ workflow.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrequest\n      description: Cflow Create Request\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cflow.createrequest\n      with:\n        workflowId: tools.workflowId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: The unique identifier of the workflow.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrequest\n      description: Cflow Get Request\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cflow.getrequest\n      with:\n        workflowId: tools.workflowId\n        requestId: tools.requestId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: The unique identifier of the workflow.\n        required: true\n\
  \      - name: requestId\n        type: string\n        description: The unique identifier of the request.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updaterequest\n      description: Cflow Update Request\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: cflow.updaterequest\n      with:\n        workflowId: tools.workflowId\n        requestId: tools.requestId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: The unique identifier of the workflow.\n        required: true\n      - name: requestId\n        type: string\n        description: The unique identifier of the request.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterequest\n      description: Cflow Delete Request\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n  \
  \    call: cflow.deleterequest\n      with:\n        workflowId: tools.workflowId\n        requestId: tools.requestId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: The unique identifier of the workflow.\n        required: true\n      - name: requestId\n        type: string\n        description: The unique identifier of the request.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: approverequest\n      description: Cflow Approve Request\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cflow.approverequest\n      with:\n        workflowId: tools.workflowId\n        requestId: tools.requestId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: The unique identifier of the workflow.\n        required: true\n      - name: requestId\n        type: string\n        description: The unique identifier\
  \ of the request.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: rejectrequest\n      description: Cflow Reject Request\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cflow.rejectrequest\n      with:\n        workflowId: tools.workflowId\n        requestId: tools.requestId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: The unique identifier of the workflow.\n        required: true\n      - name: requestId\n        type: string\n        description: The unique identifier of the request.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdraftrequest\n      description: Cflow Create Draft Request\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cflow.createdraftrequest\n      with:\n        workflowId: tools.workflowId\n\
  \      inputParameters:\n      - name: workflowId\n        type: string\n        description: The unique identifier of the workflow.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: Cflow List Users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cflow.listusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listroles\n      description: Cflow List Roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cflow.listroles\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CFLOW_TOKEN: CFLOW_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cflow/refs/heads/main/capabilities/cflow-capability.yaml
tags:
- Cflow
- API
tools:
- description: Cflow List Workflows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflows
- description: Cflow Get Workflow
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflow
- description: Cflow List Requests
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrequests
- description: Cflow Create Request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrequest
- description: Cflow Get Request
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrequest
- description: Cflow Update Request
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updaterequest
- description: Cflow Delete Request
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterequest
- description: Cflow Approve Request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: approverequest
- description: Cflow Reject Request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rejectrequest
- description: Cflow Create Draft Request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdraftrequest
- description: Cflow List Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Cflow List Roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroles
---
