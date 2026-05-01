---
categories: []
consumed_apis:
- payment_cryptography
description: Workflow capability composing Amazon Payment Cryptography APIs for developers and operators.
layout: capability
name: Amazon Payment Cryptography API Workflow
operations:
- description: List Amazon Payment Cryptography resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon Payment Cryptography
provider_slug: amazon-payment-cryptography
search_terms:
- pci
- list openapi.yml
- core api workflow
- list resources
- primary amazon payment cryptography resources
- Developer
- financial services
- payment processing
- aws
- amazon payment cryptography
- list and manage openapi.yml resources
- list amazon payment cryptography resources
- developer using amazon payment cryptography apis
- cryptography
slug: amazon-payment-cryptography-workflow
source_filename: amazon-payment-cryptography-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Payment Cryptography API Workflow\n  description: Workflow capability composing Amazon Payment Cryptography APIs for developers and operators.\n  tags:\n  - Amazon Payment Cryptography\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\ncapability:\n  consumes:\n  - import: payment_cryptography\n    location: ./shared/payment-cryptography.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-payment-cryptography-api\n    description: Unified REST API for Amazon Payment Cryptography.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Primary Amazon Payment Cryptography resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Payment Cryptography resources\n        call: openapi.yml.list\n        outputParameters:\n        - type: object\n    \
  \      mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-payment-cryptography-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Payment Cryptography operations.\n    tools:\n    - name: list-openapi.yml\n      description: List and manage openapi.yml resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openapi.yml.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-payment-cryptography/refs/heads/main/capabilities/amazon-payment-cryptography-workflow.yaml
tags:
- Amazon Payment Cryptography
- AWS
tools:
- description: List and manage openapi.yml resources
  hints:
    openWorld: true
    readOnly: true
  name: list-openapi.yml
---
