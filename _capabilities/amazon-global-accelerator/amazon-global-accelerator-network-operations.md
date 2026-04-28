---
categories: []
consumed_apis:
- amazon-global-accelerator
description: Workflow capability for network engineers and DevOps teams managing Amazon Global Accelerator infrastructure. Covers accelerator lifecycle, listener configuration, endpoint group management, and traffic routing optimization.
layout: capability
name: Amazon Global Accelerator Network Operations
operations:
- description: List all accelerators
  method: GET
  name: list-accelerators
  path: /v1/accelerators
- description: Create a new accelerator with static IPs
  method: POST
  name: create-accelerator
  path: /v1/accelerators
- description: Get accelerator details and status
  method: GET
  name: describe-accelerator
  path: /v1/accelerators/{acceleratorArn}
- description: Create a new listener
  method: POST
  name: create-listener
  path: /v1/listeners
- description: List all listeners
  method: GET
  name: list-listeners
  path: /v1/listeners
- description: Create an endpoint group
  method: POST
  name: create-endpoint-group
  path: /v1/endpoint-groups
- description: List endpoint groups
  method: GET
  name: list-endpoint-groups
  path: /v1/endpoint-groups
personas: []
provider_name: Amazon Global Accelerator
provider_slug: amazon-global-accelerator
search_terms:
- manages application infrastructure and availability
- describe accelerator
- update accelerator
- performance
- Network Engineer
- global
- get accelerator details and status
- create an endpoint group
- create a new global accelerator with static anycast ip addresses
- list endpoint groups
- get detailed status and configuration of a specific accelerator
- create listener
- update endpoint group
- aws
- create a new accelerator with static ips
- list accelerators
- create a listener for an accelerator specifying ports and protocol
- manage global accelerator accelerators
- load balancing
- configures and optimizes global network traffic routing
- amazon global accelerator
- list all accelerators
- delete an accelerator
- update listener
- create an endpoint group to route traffic to specific aws resources
- create a new listener
- update listener configuration including ports and protocol
- create accelerator
- manage listeners for accelerators
- cdn
- update accelerator configuration and settings
- DevOps Engineer
- manage a specific accelerator
- list all listeners configured for an accelerator
- create endpoint group
- list all global accelerator accelerators and their static ip addresses
- delete accelerator
- availability
- list listeners
- update endpoint group traffic settings and weights
- list all endpoint groups for a listener
- networking
- list all listeners
- manage endpoint groups for traffic routing
- traffic routing
slug: amazon-global-accelerator-network-operations
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon Global Accelerator Network Operations\n  description: >-\n    Workflow capability for network engineers and DevOps teams managing Amazon Global\n    Accelerator infrastructure. Covers accelerator lifecycle, listener configuration,\n    endpoint group management, and traffic routing optimization.\n  tags:\n    - Amazon Global Accelerator\n    - Networking\n    - Performance\n    - Traffic Routing\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-global-accelerator\n      location: ./shared/amazon-global-accelerator.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: global-accelerator-ops-api\n      description: Unified REST API for Amazon Global Accelerator network operations.\n\
  \      resources:\n        - path: /v1/accelerators\n          name: accelerators\n          description: Manage Global Accelerator accelerators\n          operations:\n            - method: GET\n              name: list-accelerators\n              description: List all accelerators\n              call: amazon-global-accelerator.ListAccelerators\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-accelerator\n              description: Create a new accelerator with static IPs\n              call: amazon-global-accelerator.CreateAccelerator\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accelerators/{acceleratorArn}\n          name: accelerator-detail\n          description: Manage a specific accelerator\n          operations:\n            - method: GET\n              name: describe-accelerator\n              description:\
  \ Get accelerator details and status\n              call: amazon-global-accelerator.DescribeAccelerator\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/listeners\n          name: listeners\n          description: Manage listeners for accelerators\n          operations:\n            - method: POST\n              name: create-listener\n              description: Create a new listener\n              call: amazon-global-accelerator.CreateListener\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-listeners\n              description: List all listeners\n              call: amazon-global-accelerator.ListListeners\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/endpoint-groups\n          name: endpoint-groups\n          description: Manage endpoint\
  \ groups for traffic routing\n          operations:\n            - method: POST\n              name: create-endpoint-group\n              description: Create an endpoint group\n              call: amazon-global-accelerator.CreateEndpointGroup\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-endpoint-groups\n              description: List endpoint groups\n              call: amazon-global-accelerator.ListEndpointGroups\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: global-accelerator-ops-mcp\n      transport: http\n      description: MCP server for AI-assisted Amazon Global Accelerator network management.\n      tools:\n        - name: list-accelerators\n          description: List all Global Accelerator accelerators and their static IP addresses\n          hints:\n           \
  \ readOnly: true\n            openWorld: true\n          call: amazon-global-accelerator.ListAccelerators\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-accelerator\n          description: Create a new Global Accelerator with static Anycast IP addresses\n          hints:\n            readOnly: false\n          call: amazon-global-accelerator.CreateAccelerator\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-accelerator\n          description: Get detailed status and configuration of a specific accelerator\n          hints:\n            readOnly: true\n          call: amazon-global-accelerator.DescribeAccelerator\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-accelerator\n          description: Update accelerator configuration and settings\n          hints:\n            readOnly: false\n       \
  \     idempotent: true\n          call: amazon-global-accelerator.UpdateAccelerator\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-accelerator\n          description: Delete an accelerator\n          hints:\n            readOnly: false\n            destructive: true\n          call: amazon-global-accelerator.DeleteAccelerator\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-listener\n          description: Create a listener for an accelerator specifying ports and protocol\n          hints:\n            readOnly: false\n          call: amazon-global-accelerator.CreateListener\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-listeners\n          description: List all listeners configured for an accelerator\n          hints:\n            readOnly: true\n          call: amazon-global-accelerator.ListListeners\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-listener\n          description: Update listener configuration including ports and protocol\n          hints:\n            readOnly: false\n            idempotent: true\n          call: amazon-global-accelerator.UpdateListener\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-endpoint-group\n          description: Create an endpoint group to route traffic to specific AWS resources\n          hints:\n            readOnly: false\n          call: amazon-global-accelerator.CreateEndpointGroup\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-endpoint-groups\n          description: List all endpoint groups for a listener\n          hints:\n            readOnly: true\n          call: amazon-global-accelerator.ListEndpointGroups\n          outputParameters:\n   \
  \         - type: object\n              mapping: \"$.\"\n        - name: update-endpoint-group\n          description: Update endpoint group traffic settings and weights\n          hints:\n            readOnly: false\n            idempotent: true\n          call: amazon-global-accelerator.UpdateEndpointGroup\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-global-accelerator/refs/heads/main/capabilities/amazon-global-accelerator-network-operations.yaml
tags:
- Amazon Global Accelerator
- Networking
- Performance
- Traffic Routing
- AWS
tools:
- description: List all Global Accelerator accelerators and their static IP addresses
  hints:
    openWorld: true
    readOnly: true
  name: list-accelerators
- description: Create a new Global Accelerator with static Anycast IP addresses
  hints:
    readOnly: false
  name: create-accelerator
- description: Get detailed status and configuration of a specific accelerator
  hints:
    readOnly: true
  name: describe-accelerator
- description: Update accelerator configuration and settings
  hints:
    idempotent: true
    readOnly: false
  name: update-accelerator
- description: Delete an accelerator
  hints:
    destructive: true
    readOnly: false
  name: delete-accelerator
- description: Create a listener for an accelerator specifying ports and protocol
  hints:
    readOnly: false
  name: create-listener
- description: List all listeners configured for an accelerator
  hints:
    readOnly: true
  name: list-listeners
- description: Update listener configuration including ports and protocol
  hints:
    idempotent: true
    readOnly: false
  name: update-listener
- description: Create an endpoint group to route traffic to specific AWS resources
  hints:
    readOnly: false
  name: create-endpoint-group
- description: List all endpoint groups for a listener
  hints:
    readOnly: true
  name: list-endpoint-groups
- description: Update endpoint group traffic settings and weights
  hints:
    idempotent: true
    readOnly: false
  name: update-endpoint-group
---
