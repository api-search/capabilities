---
categories: []
consumed_apis: []
description: The Harness Platform API provides access to core platform resources including projects, organizations, connectors, secrets, users, roles, pipelines, triggers, and pipeline execution.
layout: capability
name: Harness Platform API
operations:
- description: Harness List Organizations
  method: GET
  name: listorganizations
  path: /ng/api/organizations
- description: Harness List Projects
  method: GET
  name: listprojects
  path: /ng/api/projects
- description: Harness List Pipelines
  method: GET
  name: listpipelines
  path: /pipeline/api/pipelines
- description: Harness Execute Pipeline
  method: POST
  name: executepipeline
  path: /pipeline/api/pipelines/execute/{pipelineIdentifier}
personas: []
provider_name: Harness
provider_slug: harness
search_terms:
- gitops
- software delivery
- api
- harness list pipelines
- devops
- harness execute pipeline
- listprojects
- executepipeline
- harness list projects
- lifecycle
- harness list organizations
- internal developer portal
- listorganizations
- harness
- listpipelines
slug: harness-capability
source_filename: harness-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Harness Platform API\n  description: The Harness Platform API provides access to core platform resources including projects, organizations, connectors,\n    secrets, users, roles, pipelines, triggers, and pipeline execution.\n  tags:\n  - Harness\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: harness\n    baseUri: https://app.harness.io/gateway\n    description: Harness Platform API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{HARNESS_TOKEN}}'\n    resources:\n    - name: ng-api-organizations\n      path: /ng/api/organizations\n      operations:\n      - name: listorganizations\n        method: GET\n        description: Harness List Organizations\n        inputParameters:\n        - name: accountIdentifier\n          in: query\n          type: string\n          required: true\n          description: Account\
  \ identifier.\n        - name: pageIndex\n          in: query\n          type: integer\n          description: Page number (0-based).\n        - name: pageSize\n          in: query\n          type: integer\n          description: Number of items per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ng-api-projects\n      path: /ng/api/projects\n      operations:\n      - name: listprojects\n        method: GET\n        description: Harness List Projects\n        inputParameters:\n        - name: accountIdentifier\n          in: query\n          type: string\n          required: true\n          description: Account identifier.\n        - name: orgIdentifier\n          in: query\n          type: string\n          description: Organization identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipeline-api-pipelines\n\
  \      path: /pipeline/api/pipelines\n      operations:\n      - name: listpipelines\n        method: GET\n        description: Harness List Pipelines\n        inputParameters:\n        - name: accountIdentifier\n          in: query\n          type: string\n          required: true\n        - name: orgIdentifier\n          in: query\n          type: string\n          required: true\n        - name: projectIdentifier\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipeline-api-pipelines-execute-pipelineidentifie\n      path: /pipeline/api/pipelines/execute/{pipelineIdentifier}\n      operations:\n      - name: executepipeline\n        method: POST\n        description: Harness Execute Pipeline\n        inputParameters:\n        - name: pipelineIdentifier\n          in: path\n          type: string\n          required: true\n \
  \         description: Pipeline identifier.\n        - name: accountIdentifier\n          in: query\n          type: string\n          required: true\n        - name: orgIdentifier\n          in: query\n          type: string\n          required: true\n        - name: projectIdentifier\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: harness-rest\n    description: REST adapter for Harness Platform API.\n    resources:\n    - path: /ng/api/organizations\n      name: listorganizations\n      operations:\n      - method: GET\n        name: listorganizations\n        description: Harness List Organizations\n        call: harness.listorganizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ng/api/projects\n      name: listprojects\n      operations:\n\
  \      - method: GET\n        name: listprojects\n        description: Harness List Projects\n        call: harness.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipeline/api/pipelines\n      name: listpipelines\n      operations:\n      - method: GET\n        name: listpipelines\n        description: Harness List Pipelines\n        call: harness.listpipelines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipeline/api/pipelines/execute/{pipelineIdentifier}\n      name: executepipeline\n      operations:\n      - method: POST\n        name: executepipeline\n        description: Harness Execute Pipeline\n        call: harness.executepipeline\n        with:\n          pipelineIdentifier: rest.pipelineIdentifier\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: harness-mcp\n    transport: http\n    description: MCP adapter for\
  \ Harness Platform API for AI agent use.\n    tools:\n    - name: listorganizations\n      description: Harness List Organizations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harness.listorganizations\n      with:\n        accountIdentifier: tools.accountIdentifier\n        pageIndex: tools.pageIndex\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: accountIdentifier\n        type: string\n        description: Account identifier.\n        required: true\n      - name: pageIndex\n        type: integer\n        description: Page number (0-based).\n      - name: pageSize\n        type: integer\n        description: Number of items per page.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprojects\n      description: Harness List Projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harness.listprojects\n      with:\n\
  \        accountIdentifier: tools.accountIdentifier\n        orgIdentifier: tools.orgIdentifier\n      inputParameters:\n      - name: accountIdentifier\n        type: string\n        description: Account identifier.\n        required: true\n      - name: orgIdentifier\n        type: string\n        description: Organization identifier.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpipelines\n      description: Harness List Pipelines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harness.listpipelines\n      with:\n        accountIdentifier: tools.accountIdentifier\n        orgIdentifier: tools.orgIdentifier\n        projectIdentifier: tools.projectIdentifier\n      inputParameters:\n      - name: accountIdentifier\n        type: string\n        description: accountIdentifier\n        required: true\n      - name: orgIdentifier\n        type: string\n        description: orgIdentifier\n   \
  \     required: true\n      - name: projectIdentifier\n        type: string\n        description: projectIdentifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: executepipeline\n      description: Harness Execute Pipeline\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: harness.executepipeline\n      with:\n        pipelineIdentifier: tools.pipelineIdentifier\n        accountIdentifier: tools.accountIdentifier\n        orgIdentifier: tools.orgIdentifier\n        projectIdentifier: tools.projectIdentifier\n      inputParameters:\n      - name: pipelineIdentifier\n        type: string\n        description: Pipeline identifier.\n        required: true\n      - name: accountIdentifier\n        type: string\n        description: accountIdentifier\n        required: true\n      - name: orgIdentifier\n        type: string\n        description: orgIdentifier\n        required:\
  \ true\n      - name: projectIdentifier\n        type: string\n        description: projectIdentifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HARNESS_TOKEN: HARNESS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/harness/refs/heads/main/capabilities/harness-capability.yaml
tags:
- Harness
- API
tools:
- description: Harness List Organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizations
- description: Harness List Projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Harness List Pipelines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpipelines
- description: Harness Execute Pipeline
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executepipeline
---
