---
categories:
- monitoring
consumed_apis: []
description: Workflow capability for platform and operations teams to create and manage Grafana workspaces, dashboards, and access controls for observability on Amazon Managed Grafana.
layout: capability
name: Amazon Managed Grafana - Observability Dashboard Workflow
operations:
- description: List workspaces
  method: GET
  name: list-workspaces
  path: /v1/workspaces
- description: Create a workspace
  method: POST
  name: create-workspace
  path: /v1/workspaces
personas: []
provider_name: Amazon Managed Grafana
provider_slug: amazon-managed-grafana
search_terms:
- create workspace
- grafana workspaces
- list all grafana workspaces for observability dashboards
- visualization
- create an api key for programmatic grafana workspace access
- amazon
- update workspace
- get workspace details
- dashboards
- create workspace api key
- monitoring
- create a new grafana workspace for observability dashboards
- update grafana workspace configuration, authentication, or data sources
- create a workspace
- list grafana workspaces
- grafana
- observability
- list workspaces
- Operations Engineer
- Platform Engineer
- get configuration and authentication details of a grafana workspace
- create grafana workspace
slug: observability-dashboard-workflow
source_filename: observability-dashboard-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Managed Grafana - Observability Dashboard Workflow\n  description: Workflow capability for platform and operations teams to create and manage Grafana workspaces, dashboards,\n    and access controls for observability on Amazon Managed Grafana.\n  tags:\n  - Amazon\n  - Grafana\n  - Dashboards\n  - Monitoring\n  - Observability\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: managed-grafana\n    baseUri: https://grafana.amazonaws.com\n    description: Amazon Managed Grafana REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: AWS4-HMAC-SHA256 {{AWS_ACCESS_KEY_ID}}\n      placement: header\n    resources:\n    - name: workspaces\n      path: /workspaces\n      description: Manage Grafana\
  \ workspaces\n      operations:\n      - name: list-workspaces\n        method: GET\n        description: List all Grafana workspaces\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-workspace\n        method: POST\n        description: Create a new Grafana workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-workspace\n        method: GET\n        description: Get workspace details\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: string\n          required: true\n          description: Workspace ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-workspace\n        method: PUT\n        description: Update workspace configuration\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-workspace\n        method: DELETE\n        description: Delete a workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-keys\n      path: /workspaces/{workspaceId}/apikeys\n      description: Manage workspace API keys\n      operations:\n      - name: create-workspace-api-key\n        method: POST\n        description: Create a workspace API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-workspace-api-keys\n        method: GET\n        description: List workspace API keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: grafana-dashboard-api\n\
  \    description: Unified REST API for Grafana observability dashboard workflows.\n    resources:\n    - path: /v1/workspaces\n      name: workspaces\n      description: Grafana workspaces\n      operations:\n      - method: GET\n        name: list-workspaces\n        description: List workspaces\n        call: managed-grafana.list-workspaces\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-workspace\n        description: Create a workspace\n        call: managed-grafana.create-workspace\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: grafana-dashboard-mcp\n    transport: http\n    description: MCP server for AI-assisted Grafana observability management.\n    tools:\n    - name: list-grafana-workspaces\n      description: List all Grafana workspaces for observability dashboards\n      hints:\n        readOnly: true\n        destructive: false\n \
  \       idempotent: true\n      call: managed-grafana.list-workspaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-grafana-workspace\n      description: Create a new Grafana workspace for observability dashboards\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: managed-grafana.create-workspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-workspace-details\n      description: Get configuration and authentication details of a Grafana workspace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: managed-grafana.describe-workspace\n      with:\n        workspaceId: tools.workspaceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-workspace-api-key\n      description: Create an API key for programmatic Grafana workspace access\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: managed-grafana.create-workspace-api-key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-workspace\n      description: Update Grafana workspace configuration, authentication, or data sources\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: managed-grafana.update-workspace\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-managed-grafana/refs/heads/main/capabilities/observability-dashboard-workflow.yaml
tags:
- Amazon
- Grafana
- Dashboards
- Monitoring
- Observability
tools:
- description: List all Grafana workspaces for observability dashboards
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-grafana-workspaces
- description: Create a new Grafana workspace for observability dashboards
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-grafana-workspace
- description: Get configuration and authentication details of a Grafana workspace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-workspace-details
- description: Create an API key for programmatic Grafana workspace access
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-workspace-api-key
- description: Update Grafana workspace configuration, authentication, or data sources
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-workspace
---
