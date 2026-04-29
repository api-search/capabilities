---
categories: []
consumed_apis:
- azure-networking-services
description: Workflow capability for managing Azure Networking Services resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure Networking Services Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure Networking Services
provider_slug: azure-networking-services
search_terms:
- list network interfaces
- resource management
- cloud
- azure
- list subnet resources
- microsoft
- list virtual networks
- infrastructure
- list networkinterface resources
- list loadbalancer resources
- list load balancers
- list subnets
- list virtualnetwork resources
- list all resources
- azure resource management
- management
- networking
- list
slug: azure-networking-services-management
source_filename: azure-networking-services-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure Networking Services Management\"\n  description: \"Workflow capability for managing Azure Networking Services resources. Used by cloud engineers and DevOps teams.\"\n  tags:\n    - Azure\n    - Cloud\n    - Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n      AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: azure-networking-services\n      location: ./shared/azure-networking-services.yaml\n\n  exposes:\n    - type: rest\n      port: 8088\n      namespace: azure-networking-services-management-api\n      description: \"Unified REST API for Azure Networking Services management.\"\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: \"Resource management\"\n          operations:\n            - method: GET\n              name: list\n   \
  \           description: \"List all resources\"\n              call: \"azure-networking-services.list-virtual-networks\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9098\n      namespace: azure-networking-services-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure Networking Services management.\"\n      tools:\n        - name: list-virtual-networks\n          description: \"List VirtualNetwork resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-networking-services.list-virtual-networks\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-subnets\n          description: \"List Subnet resources\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-networking-services.list-subnets\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-load-balancers\n          description: \"List LoadBalancer resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-networking-services.list-load-balancers\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-network-interfaces\n          description: \"List NetworkInterface resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-networking-services.list-network-interfaces\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-networking-services/refs/heads/main/capabilities/azure-networking-services-management.yaml
tags:
- Azure
- Cloud
- Management
tools:
- description: List VirtualNetwork resources
  hints:
    openWorld: true
    readOnly: true
  name: list-virtual-networks
- description: List Subnet resources
  hints:
    openWorld: true
    readOnly: true
  name: list-subnets
- description: List LoadBalancer resources
  hints:
    openWorld: true
    readOnly: true
  name: list-load-balancers
- description: List NetworkInterface resources
  hints:
    openWorld: true
    readOnly: true
  name: list-network-interfaces
---
