---
categories: []
consumed_apis: []
description: Unified workflow for managing embedded integrations within SaaS products - browsing connectors, building workflows, monitoring usage analytics, and managing user connections.
layout: capability
name: Apifuse Embedded Integration Management
operations:
- description: List all integrations.
  method: GET
  name: list-integrations
  path: /v1/integrations
- description: List all connectors.
  method: GET
  name: list-connectors
  path: /v1/connectors
- description: List workflows.
  method: GET
  name: list-workflows
  path: /v1/workflows
- description: Create a workflow.
  method: POST
  name: create-workflow
  path: /v1/workflows
- description: Get analytics data.
  method: GET
  name: get-analytics
  path: /v1/analytics
personas: []
provider_name: Apifuse
provider_slug: apifuse
search_terms:
- integrations
- list integrations
- list all pre-built connectors available for embedding into your saas product.
- list all integration workflows configured in the embedded marketplace.
- list workflows
- workflow automation
- get analytics
- list all integrations.
- embedded integrations
- browse all available embedded integrations, optionally filtered by category.
- saas
- SaaS Product Manager
- apifuse
- list workflows.
- create a workflow.
- retrieve integration usage analytics including total tasks, active integrations, and active users.
- integration platform
- create workflow
- browse pre-built connectors.
- integration analytics.
- product manager building native integrations into a saas product.
- marketplace
- list connectors
- get analytics data.
- ipaas
- Integration Developer
- developer implementing and automating embedded integration workflows.
- list all connectors.
- create a new automation workflow connecting two or more integrated platforms.
- managing native integrations within saas products.
- browse and manage integrations.
- manage workflows.
slug: embedded-integration-management
source_filename: embedded-integration-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apifuse Embedded Integration Management\n  description: Unified workflow for managing embedded integrations within SaaS products - browsing connectors, building workflows,\n    monitoring usage analytics, and managing user connections.\n  tags:\n  - Apifuse\n  - Embedded Integrations\n  - Workflow Automation\n  - SaaS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APIFUSE_API_KEY: APIFUSE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: apifuse\n    baseUri: https://api.apifuse.io\n    description: Apifuse REST API for managing embedded integrations and workflows.\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{APIFUSE_API_KEY}}'\n      placement: header\n    resources:\n    - name: integrations\n      path: /integrations\n      description: Manage embedded integrations.\n      operations:\n      - name: list-integrations\n        method: GET\n\
  \        description: List all available integrations.\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter by category.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-integration\n        method: GET\n        description: Get details for a specific integration.\n        inputParameters:\n        - name: integrationId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the integration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connectors\n      path: /connectors\n      description: Browse pre-built connectors.\n      operations:\n      - name: list-connectors\n        method: GET\n        description: List all pre-built connectors.\n\
  \        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter by category.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows\n      path: /workflows\n      description: Manage integration workflows.\n      operations:\n      - name: list-workflows\n        method: GET\n        description: List all integration workflows.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-workflow\n        method: POST\n        description: Create a new integration workflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            triggerType: '{{tools.triggerType}}'\n\
  \    - name: users\n      path: /users\n      description: Manage integration users.\n      operations:\n      - name: list-users\n        method: GET\n        description: List users with connected integrations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics\n      path: /analytics\n      description: Integration usage analytics.\n      operations:\n      - name: get-analytics\n        method: GET\n        description: Get integration usage analytics.\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date (ISO 8601).\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date (ISO 8601).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \  exposes:\n  - type: rest\n    port: 8080\n    namespace: apifuse-integration-api\n    description: Unified REST API for managing Apifuse embedded integrations.\n    resources:\n    - path: /v1/integrations\n      name: integrations\n      description: Browse and manage integrations.\n      operations:\n      - method: GET\n        name: list-integrations\n        description: List all integrations.\n        call: apifuse.list-integrations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connectors\n      name: connectors\n      description: Browse pre-built connectors.\n      operations:\n      - method: GET\n        name: list-connectors\n        description: List all connectors.\n        call: apifuse.list-connectors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows\n      name: workflows\n      description: Manage workflows.\n      operations:\n      - method: GET\n        name: list-workflows\n\
  \        description: List workflows.\n        call: apifuse.list-workflows\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-workflow\n        description: Create a workflow.\n        call: apifuse.create-workflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics\n      name: analytics\n      description: Integration analytics.\n      operations:\n      - method: GET\n        name: get-analytics\n        description: Get analytics data.\n        call: apifuse.get-analytics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: apifuse-integration-mcp\n    transport: http\n    description: MCP server for AI-assisted embedded integration management.\n    tools:\n    - name: list-integrations\n      description: Browse all available embedded integrations, optionally filtered by category.\n      hints:\n  \
  \      readOnly: true\n        destructive: false\n        idempotent: true\n      call: apifuse.list-integrations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-connectors\n      description: List all pre-built connectors available for embedding into your SaaS product.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apifuse.list-connectors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workflows\n      description: List all integration workflows configured in the embedded marketplace.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apifuse.list-workflows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-workflow\n      description: Create a new automation workflow connecting two or more integrated platforms.\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: apifuse.create-workflow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-analytics\n      description: Retrieve integration usage analytics including total tasks, active integrations, and active users.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apifuse.get-analytics\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apifuse/refs/heads/main/capabilities/embedded-integration-management.yaml
tags:
- Apifuse
- Embedded Integrations
- Workflow Automation
- SaaS
tools:
- description: Browse all available embedded integrations, optionally filtered by category.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-integrations
- description: List all pre-built connectors available for embedding into your SaaS product.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-connectors
- description: List all integration workflows configured in the embedded marketplace.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-workflows
- description: Create a new automation workflow connecting two or more integrated platforms.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-workflow
- description: Retrieve integration usage analytics including total tasks, active integrations, and active users.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-analytics
---
