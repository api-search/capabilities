---
categories: []
consumed_apis: []
description: The Workflows API enables serverless workflow orchestration. It allows you to create, manage, and execute workflows that combine Google Cloud services and HTTP-based APIs.
layout: capability
name: Google Cloud Workflows API
operations:
- description: Google Cloud Workflows List workflows
  method: GET
  name: listworkflows
  path: /v1/projects/{project}/locations/{location}/workflows
- description: Google Cloud Workflows Create a workflow
  method: POST
  name: createworkflow
  path: /v1/projects/{project}/locations/{location}/workflows
- description: Google Cloud Workflows Get a workflow
  method: GET
  name: getworkflow
  path: /v1/projects/{project}/locations/{location}/workflows/{workflow}
- description: Google Cloud Workflows Update a workflow
  method: PATCH
  name: updateworkflow
  path: /v1/projects/{project}/locations/{location}/workflows/{workflow}
- description: Google Cloud Workflows Delete a workflow
  method: DELETE
  name: deleteworkflow
  path: /v1/projects/{project}/locations/{location}/workflows/{workflow}
- description: Google Cloud Workflows List executions
  method: GET
  name: listexecutions
  path: /v1/projects/{project}/locations/{location}/workflows/{workflow}/executions
- description: Google Cloud Workflows Create an execution
  method: POST
  name: createexecution
  path: /v1/projects/{project}/locations/{location}/workflows/{workflow}/executions
- description: Google Cloud Workflows Get an execution
  method: GET
  name: getexecution
  path: /v1/projects/{project}/locations/{location}/workflows/{workflow}/executions/{execution}
- description: Google Cloud Workflows Cancel an execution
  method: POST
  name: cancelexecution
  path: /v1/projects/{project}/locations/{location}/workflows/{workflow}/executions/{execution}:cancel
personas: []
provider_name: Google Cloud Workflows
provider_slug: google-cloud-workflows
search_terms:
- deleteworkflow
- google cloud workflows delete a workflow
- integration
- google cloud workflows get an execution
- google cloud workflows update a workflow
- serverless
- google cloud workflows list executions
- cloud
- google cloud workflows create an execution
- google
- google cloud workflows list workflows
- listworkflows
- createexecution
- getexecution
- google cloud workflows get a workflow
- orchestration
- api
- createworkflow
- workflows
- getworkflow
- google cloud workflows cancel an execution
- google cloud workflows create a workflow
- cancelexecution
- updateworkflow
- listexecutions
- google cloud
- automation
slug: google-cloud-workflows-capability
source_filename: google-cloud-workflows-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Workflows API\n  description: The Workflows API enables serverless workflow orchestration. It allows you to create, manage, and execute workflows\n    that combine Google Cloud services and HTTP-based APIs.\n  tags:\n  - Google\n  - Cloud\n  - Workflows\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-workflows\n    baseUri: https://workflows.googleapis.com\n    description: Google Cloud Workflows API HTTP API.\n    resources:\n    - name: v1-projects-project-locations-location-workflows\n      path: /v1/projects/{project}/locations/{location}/workflows\n      operations:\n      - name: listworkflows\n        method: GET\n        description: Google Cloud Workflows List workflows\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n\
  \          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createworkflow\n        method: POST\n        description: Google Cloud Workflows Create a workflow\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: workflowId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-location-workflows\n      path: /v1/projects/{project}/locations/{location}/workflows/{workflow}\n      operations:\n      - name: getworkflow\n        method: GET\n        description: Google Cloud Workflows Get a workflow\n        inputParameters:\n\
  \        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: workflow\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateworkflow\n        method: PATCH\n        description: Google Cloud Workflows Update a workflow\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: workflow\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteworkflow\n\
  \        method: DELETE\n        description: Google Cloud Workflows Delete a workflow\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: workflow\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-location-workflows\n      path: /v1/projects/{project}/locations/{location}/workflows/{workflow}/executions\n      operations:\n      - name: listexecutions\n        method: GET\n        description: Google Cloud Workflows List executions\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n\
  \          required: true\n        - name: workflow\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createexecution\n        method: POST\n        description: Google Cloud Workflows Create an execution\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: workflow\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-location-workflows\n      path: /v1/projects/{project}/locations/{location}/workflows/{workflow}/executions/{execution}\n      operations:\n      - name:\
  \ getexecution\n        method: GET\n        description: Google Cloud Workflows Get an execution\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: workflow\n          in: path\n          type: string\n          required: true\n        - name: execution\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-location-workflows\n      path: /v1/projects/{project}/locations/{location}/workflows/{workflow}/executions/{execution}:cancel\n      operations:\n      - name: cancelexecution\n        method: POST\n        description: Google Cloud Workflows Cancel an execution\n        inputParameters:\n        - name: project\n     \
  \     in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: workflow\n          in: path\n          type: string\n          required: true\n        - name: execution\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-workflows-rest\n    description: REST adapter for Google Cloud Workflows API.\n    resources:\n    - path: /v1/projects/{project}/locations/{location}/workflows\n      name: listworkflows\n      operations:\n      - method: GET\n        name: listworkflows\n        description: Google Cloud Workflows List workflows\n        call: google-cloud-workflows.listworkflows\n        with:\n          project: rest.project\n          location: rest.location\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/workflows\n      name: createworkflow\n      operations:\n      - method: POST\n        name: createworkflow\n        description: Google Cloud Workflows Create a workflow\n        call: google-cloud-workflows.createworkflow\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/workflows/{workflow}\n      name: getworkflow\n      operations:\n      - method: GET\n        name: getworkflow\n        description: Google Cloud Workflows Get a workflow\n        call: google-cloud-workflows.getworkflow\n        with:\n          project: rest.project\n          location: rest.location\n          workflow: rest.workflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/workflows/{workflow}\n\
  \      name: updateworkflow\n      operations:\n      - method: PATCH\n        name: updateworkflow\n        description: Google Cloud Workflows Update a workflow\n        call: google-cloud-workflows.updateworkflow\n        with:\n          project: rest.project\n          location: rest.location\n          workflow: rest.workflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/workflows/{workflow}\n      name: deleteworkflow\n      operations:\n      - method: DELETE\n        name: deleteworkflow\n        description: Google Cloud Workflows Delete a workflow\n        call: google-cloud-workflows.deleteworkflow\n        with:\n          project: rest.project\n          location: rest.location\n          workflow: rest.workflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/workflows/{workflow}/executions\n      name: listexecutions\n\
  \      operations:\n      - method: GET\n        name: listexecutions\n        description: Google Cloud Workflows List executions\n        call: google-cloud-workflows.listexecutions\n        with:\n          project: rest.project\n          location: rest.location\n          workflow: rest.workflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/workflows/{workflow}/executions\n      name: createexecution\n      operations:\n      - method: POST\n        name: createexecution\n        description: Google Cloud Workflows Create an execution\n        call: google-cloud-workflows.createexecution\n        with:\n          project: rest.project\n          location: rest.location\n          workflow: rest.workflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/workflows/{workflow}/executions/{execution}\n      name: getexecution\n\
  \      operations:\n      - method: GET\n        name: getexecution\n        description: Google Cloud Workflows Get an execution\n        call: google-cloud-workflows.getexecution\n        with:\n          project: rest.project\n          location: rest.location\n          workflow: rest.workflow\n          execution: rest.execution\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/workflows/{workflow}/executions/{execution}:cancel\n      name: cancelexecution\n      operations:\n      - method: POST\n        name: cancelexecution\n        description: Google Cloud Workflows Cancel an execution\n        call: google-cloud-workflows.cancelexecution\n        with:\n          project: rest.project\n          location: rest.location\n          workflow: rest.workflow\n          execution: rest.execution\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n\
  \    namespace: google-cloud-workflows-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Workflows API for AI agent use.\n    tools:\n    - name: listworkflows\n      description: Google Cloud Workflows List workflows\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-workflows.listworkflows\n      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createworkflow\n      description: Google Cloud Workflows Create a workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-workflows.createworkflow\n      with:\n\
  \        project: tools.project\n        location: tools.location\n        workflowId: tools.workflowId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: workflowId\n        type: string\n        description: workflowId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkflow\n      description: Google Cloud Workflows Get a workflow\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-workflows.getworkflow\n      with:\n        project: tools.project\n        location: tools.location\n        workflow: tools.workflow\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description:\
  \ location\n        required: true\n      - name: workflow\n        type: string\n        description: workflow\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateworkflow\n      description: Google Cloud Workflows Update a workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-workflows.updateworkflow\n      with:\n        project: tools.project\n        location: tools.location\n        workflow: tools.workflow\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: workflow\n        type: string\n        description: workflow\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteworkflow\n      description: Google Cloud\
  \ Workflows Delete a workflow\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-workflows.deleteworkflow\n      with:\n        project: tools.project\n        location: tools.location\n        workflow: tools.workflow\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: workflow\n        type: string\n        description: workflow\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listexecutions\n      description: Google Cloud Workflows List executions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-workflows.listexecutions\n      with:\n        project: tools.project\n        location: tools.location\n        workflow:\
  \ tools.workflow\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: workflow\n        type: string\n        description: workflow\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createexecution\n      description: Google Cloud Workflows Create an execution\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-workflows.createexecution\n      with:\n        project: tools.project\n        location: tools.location\n        workflow: tools.workflow\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name:\
  \ workflow\n        type: string\n        description: workflow\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getexecution\n      description: Google Cloud Workflows Get an execution\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-workflows.getexecution\n      with:\n        project: tools.project\n        location: tools.location\n        workflow: tools.workflow\n        execution: tools.execution\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: workflow\n        type: string\n        description: workflow\n        required: true\n      - name: execution\n        type: string\n        description: execution\n        required: true\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: cancelexecution\n      description: Google Cloud Workflows Cancel an execution\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-workflows.cancelexecution\n      with:\n        project: tools.project\n        location: tools.location\n        workflow: tools.workflow\n        execution: tools.execution\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: workflow\n        type: string\n        description: workflow\n        required: true\n      - name: execution\n        type: string\n        description: execution\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-workflows/refs/heads/main/capabilities/google-cloud-workflows-capability.yaml
tags:
- Google
- Cloud
- Workflows
- API
tools:
- description: Google Cloud Workflows List workflows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkflows
- description: Google Cloud Workflows Create a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkflow
- description: Google Cloud Workflows Get a workflow
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflow
- description: Google Cloud Workflows Update a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateworkflow
- description: Google Cloud Workflows Delete a workflow
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteworkflow
- description: Google Cloud Workflows List executions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listexecutions
- description: Google Cloud Workflows Create an execution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createexecution
- description: Google Cloud Workflows Get an execution
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexecution
- description: Google Cloud Workflows Cancel an execution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelexecution
---
