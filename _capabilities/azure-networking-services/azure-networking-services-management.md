---
categories: []
consumed_apis: []
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
- networking
- list loadbalancer resources
- azure
- management
- list all resources
- list virtual networks
- cloud
- list subnets
- list networkinterface resources
- azure resource management
- list load balancers
- list network interfaces
- list subnet resources
- list
- infrastructure
- resource management
- microsoft
- list virtualnetwork resources
slug: azure-networking-services-management
source_filename: azure-networking-services-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Networking Services Management\n  description: Workflow capability for managing Azure Networking Services resources. Used by cloud engineers and DevOps teams.\n  tags:\n  - Azure\n  - Cloud\n  - Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n    AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: azure-networking-services\n    baseUri: https://management.azure.com\n    description: Azure Networking Services REST API\n    authentication:\n      type: bearer\n      token: '{{AZURE_ACCESS_TOKEN}}'\n    resources:\n    - name: virtual-network\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.VirtualNetwork/VirtualNetworks\n      description: Manage VirtualNetwork resources\n      operations:\n      - name: list-virtual-networks\n        method: GET\n        description: List\
  \ all VirtualNetwork resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subnet\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Subnet/Subnets\n      description: Manage Subnet resources\n      operations:\n      - name: list-subnets\n        method: GET\n        description: List all Subnet resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: load-balancer\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.LoadBalancer/LoadBalancers\n\
  \      description: Manage LoadBalancer resources\n      operations:\n      - name: list-load-balancers\n        method: GET\n        description: List all LoadBalancer resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: network-interface\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.NetworkInterface/NetworkInterfaces\n      description: Manage NetworkInterface resources\n      operations:\n      - name: list-network-interfaces\n        method: GET\n        description: List all NetworkInterface resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8088\n    namespace: azure-networking-services-management-api\n    description: Unified REST API for Azure Networking Services management.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Resource management\n      operations:\n      - method: GET\n        name: list\n        description: List all resources\n        call: azure-networking-services.list-virtual-networks\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9098\n    namespace: azure-networking-services-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure Networking Services management.\n    tools:\n    - name: list-virtual-networks\n      description: List VirtualNetwork resources\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: azure-networking-services.list-virtual-networks\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-subnets\n      description: List Subnet resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-networking-services.list-subnets\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-load-balancers\n      description: List LoadBalancer resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-networking-services.list-load-balancers\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-network-interfaces\n      description: List NetworkInterface resources\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: azure-networking-services.list-network-interfaces\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
