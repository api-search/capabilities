---
categories: []
consumed_apis: []
description: Unified workflow capability for Amazon Lightsail combining resource management and operations.
layout: capability
name: Amazon Lightsail Workflow
operations: []
personas: []
provider_name: Amazon Lightsail
provider_slug: amazon-lightsail
search_terms:
- integrates api into applications
- instances create instances
- aws
- workflow
- instances get instance
- Administrator
- creates one or more amazon lightsail instances.
- unified workflow for amazon lightsail resource management
- amazon lightsail
- manages resources and configurations
- returns information about all amazon lightsail virtual private servers.
- instances get instances
- returns information about a specific amazon lightsail instance.
- Developer
slug: amazon-lightsail-workflow
source_filename: amazon-lightsail-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Lightsail Workflow\n  description: Unified workflow capability for Amazon Lightsail combining resource management and operations.\n  tags:\n  - Amazon Lightsail\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: lightsail\n    baseUri: https://lightsail.us-east-1.amazonaws.com\n    description: Amazon Lightsail service.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: instances\n      path: /instances\n      description: Lightsail virtual server instance management\n      operations:\n      - name: createinstances\n        method: POST\n        description: Creates one or more Amazon Lightsail instances.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getinstances\n        method: GET\n        description: Returns information about all Amazon Lightsail virtual private servers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getinstance\n        method: GET\n        description: Returns information about a specific Amazon Lightsail instance.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lightsail-api\n    description: REST API for Amazon Lightsail workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: lightsail-mcp\n    transport: http\n    description: MCP server for Amazon Lightsail.\n    tools:\n    - name: instances-create-instances\n      description: Creates one\
  \ or more Amazon Lightsail instances.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: lightsail.createinstances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: instances-get-instances\n      description: Returns information about all Amazon Lightsail virtual private servers.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lightsail.getinstances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: instances-get-instance\n      description: Returns information about a specific Amazon Lightsail instance.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lightsail.getinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-lightsail/refs/heads/main/capabilities/amazon-lightsail-workflow.yaml
tags:
- Amazon Lightsail
- Workflow
tools:
- description: Creates one or more Amazon Lightsail instances.
  hints:
    idempotent: false
    readOnly: false
  name: instances-create-instances
- description: Returns information about all Amazon Lightsail virtual private servers.
  hints:
    idempotent: true
    readOnly: true
  name: instances-get-instances
- description: Returns information about a specific Amazon Lightsail instance.
  hints:
    idempotent: true
    readOnly: true
  name: instances-get-instance
---
