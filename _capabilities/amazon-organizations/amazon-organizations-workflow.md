---
categories: []
consumed_apis: []
description: Workflow capability composing Amazon Organizations APIs for developers and operators.
layout: capability
name: Amazon Organizations API Workflow
operations:
- description: List Amazon Organizations resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon Organizations
provider_slug: amazon-organizations
search_terms:
- list resources
- list and manage openapi.yml resources
- aws
- core api workflow
- account management
- Developer
- primary amazon organizations resources
- multi-account
- amazon organizations
- developer using amazon organizations apis
- governance
- policies
- list openapi.yml
- consolidated billing
- list amazon organizations resources
- organizations
slug: amazon-organizations-workflow
source_filename: amazon-organizations-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Organizations API Workflow\n  description: Workflow capability composing Amazon Organizations APIs for developers and operators.\n  tags:\n  - Amazon Organizations\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\ncapability:\n  consumes:\n  - type: http\n    namespace: openapi.yml\n    baseUri: https://organizations.{region}.amazonaws.com\n    description: The AWS Organizations API enables programmatic management of your organization. You can create accou\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_SIGV4_AUTH}}'\n      placement: header\n    resources:\n    - name: organizations\n      path: /organizations\n      description: Organizations operations for Amazon Organizations AWS Organizations API\n      operations:\n      - name: CreateOrganization\n        method: POST\n        description: Amazon Organizations\
  \ Create an Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-organizations-api\n    description: Unified REST API for Amazon Organizations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Primary Amazon Organizations resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Organizations resources\n        call: openapi.yml.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-organizations-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Organizations operations.\n    tools:\n    - name: list-openapi.yml\n      description: List and manage openapi.yml resources\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: openapi.yml.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-organizations/refs/heads/main/capabilities/amazon-organizations-workflow.yaml
tags:
- Amazon Organizations
tools:
- description: List and manage openapi.yml resources
  hints:
    openWorld: true
    readOnly: true
  name: list-openapi.yml
---
