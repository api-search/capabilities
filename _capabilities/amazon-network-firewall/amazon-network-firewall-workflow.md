---
categories: []
consumed_apis:
- network_firewall
description: Workflow capability composing Amazon Network Firewall APIs for developers and operators.
layout: capability
name: Amazon Network Firewall API Workflow
operations:
- description: List Amazon Network Firewall resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon Network Firewall
provider_slug: amazon-network-firewall
search_terms:
- list and manage openapi.yml resources
- firewall
- aws
- list resources
- vpc
- amazon network firewall
- intrusion detection
- core api workflow
- developer using amazon network firewall apis
- Developer
- list openapi.yml
- network security
- list amazon network firewall resources
- primary amazon network firewall resources
slug: amazon-network-firewall-workflow
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Network Firewall API Workflow\n  description: Workflow capability composing Amazon Network Firewall APIs for developers and operators.\n  tags:\n  - Amazon Network Firewall\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\ncapability:\n  consumes:\n  - import: network_firewall\n    location: ./shared/network-firewall.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-network-firewall-api\n    description: Unified REST API for Amazon Network Firewall.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Primary Amazon Network Firewall resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Network Firewall resources\n        call: openapi.yml.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n  \
  \  port: 9090\n    namespace: amazon-network-firewall-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Network Firewall operations.\n    tools:\n    - name: list-openapi.yml\n      description: List and manage openapi.yml resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openapi.yml.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-network-firewall/refs/heads/main/capabilities/amazon-network-firewall-workflow.yaml
tags:
- Amazon Network Firewall
- AWS
tools:
- description: List and manage openapi.yml resources
  hints:
    openWorld: true
    readOnly: true
  name: list-openapi.yml
---
