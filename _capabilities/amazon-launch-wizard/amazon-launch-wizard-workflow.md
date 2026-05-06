---
categories: []
consumed_apis: []
description: Unified workflow capability for Amazon Launch Wizard combining resource management and operations.
layout: capability
name: Amazon Launch Wizard Workflow
operations: []
personas: []
provider_name: Amazon Launch Wizard
provider_slug: amazon-launch-wizard
search_terms:
- amazon launch wizard
- manages resources and configurations
- deployments create deployment
- Administrator
- integrates api into applications
- aws
- returns information about the deployment.
- deployments get deployment
- deployment
- sap
- sql server
- workflow
- deployments list deployments
- unified workflow for amazon launch wizard resource management
- Developer
- lists the deployments that have been created.
- creates a deployment for the given workload.
- enterprise applications
slug: amazon-launch-wizard-workflow
source_filename: amazon-launch-wizard-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Launch Wizard Workflow\n  description: Unified workflow capability for Amazon Launch Wizard combining resource management and operations.\n  tags:\n  - Amazon Launch Wizard\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: launch-wizard\n    baseUri: https://launchwizard.us-east-1.amazonaws.com\n    description: Amazon Launch Wizard service.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: deployments\n      path: /deployments\n      description: Launch Wizard deployment management\n      operations:\n      - name: createdeployment\n        method: POST\n        description: Creates a deployment for the given workload.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listdeployments\n        method: GET\n        description: Lists the deployments that have been created.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getdeployment\n        method: GET\n        description: Returns information about the deployment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: launch-wizard-api\n    description: REST API for Amazon Launch Wizard workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: launch-wizard-mcp\n    transport: http\n    description: MCP server for Amazon Launch Wizard.\n    tools:\n    - name: deployments-create-deployment\n      description: Creates a\
  \ deployment for the given workload.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: launch-wizard.createdeployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployments-list-deployments\n      description: Lists the deployments that have been created.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: launch-wizard.listdeployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployments-get-deployment\n      description: Returns information about the deployment.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: launch-wizard.getdeployment\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-launch-wizard/refs/heads/main/capabilities/amazon-launch-wizard-workflow.yaml
tags:
- Amazon Launch Wizard
- Workflow
tools:
- description: Creates a deployment for the given workload.
  hints:
    idempotent: false
    readOnly: false
  name: deployments-create-deployment
- description: Lists the deployments that have been created.
  hints:
    idempotent: true
    readOnly: true
  name: deployments-list-deployments
- description: Returns information about the deployment.
  hints:
    idempotent: true
    readOnly: true
  name: deployments-get-deployment
---
