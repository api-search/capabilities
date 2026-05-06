---
categories: []
consumed_apis: []
description: Distribute traffic across multiple virtual machines and services with Azure Load Balancer. This API provides operations for creating, configuring, and managing load balancers including frontend IP configurations, backend address pools, health probes, load balancing rules, inbound NAT rules, and outbound rules.
layout: capability
name: Azure Networking Azure Load Balancer API
operations:
- description: Azure Networking List load balancers
  method: GET
  name: loadbalancers-list
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers
- description: Azure Networking Get load balancer
  method: GET
  name: loadbalancers-get
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}
- description: Azure Networking Create or update load balancer
  method: PUT
  name: loadbalancers-createorupdate
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}
- description: Azure Networking Delete load balancer
  method: DELETE
  name: loadbalancers-delete
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}
- description: Azure Networking List all load balancers
  method: GET
  name: loadbalancers-listall
  path: /subscriptions/{subscriptionId}/providers/Microsoft.Network/loadBalancers
- description: Azure Networking List backend address pools
  method: GET
  name: loadbalancerbackendaddresspools-list
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}/backendAddressPools
- description: Azure Networking List health probes
  method: GET
  name: loadbalancerprobes-list
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}/probes
- description: Azure Networking List load balancing rules
  method: GET
  name: loadbalancerloadbalancingrules-list
  path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}/loadBalancingRules
personas: []
provider_name: Azure Networking
provider_slug: microsoft-azure-networking
search_terms:
- networking
- loadbalancerbackendaddresspools list
- azure networking list health probes
- loadbalancerloadbalancingrules list
- infrastructure
- azure
- loadbalancers delete
- cloud
- azure networking get load balancer
- azure networking create or update load balancer
- loadbalancers listall
- loadbalancers get
- api
- azure networking list backend address pools
- azure networking list load balancers
- loadbalancerprobes list
- azure networking delete load balancer
- loadbalancers createorupdate
- azure networking list all load balancers
- azure networking list load balancing rules
- loadbalancers list
- microsoft
slug: microsoft-azure-networking-capability
source_filename: microsoft-azure-networking-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Networking Azure Load Balancer API\n  description: Distribute traffic across multiple virtual machines and services with Azure Load Balancer. This API provides\n    operations for creating, configuring, and managing load balancers including frontend IP configurations, backend address\n    pools, health probes, load balancing rules, inbound NAT rules, and outbound rules.\n  tags:\n  - Microsoft\n  - Azure\n  - Networking\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-azure-networking\n    baseUri: https://management.azure.com\n    description: Azure Networking Azure Load Balancer API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_AZURE_NETWORKING_TOKEN}}'\n    resources:\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers\n\
  \      operations:\n      - name: loadbalancers-list\n        method: GET\n        description: Azure Networking List load balancers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}\n      operations:\n      - name: loadbalancers-get\n        method: GET\n        description: Azure Networking Get load balancer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: loadbalancers-createorupdate\n        method: PUT\n        description: Azure Networking Create or update load balancer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: loadbalancers-delete\n\
  \        method: DELETE\n        description: Azure Networking Delete load balancer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-providers-microsoft\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Network/loadBalancers\n      operations:\n      - name: loadbalancers-listall\n        method: GET\n        description: Azure Networking List all load balancers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}/backendAddressPools\n      operations:\n      - name: loadbalancerbackendaddresspools-list\n        method: GET\n        description: Azure Networking List backend address\
  \ pools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}/probes\n      operations:\n      - name: loadbalancerprobes-list\n        method: GET\n        description: Azure Networking List health probes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}/loadBalancingRules\n      operations:\n      - name: loadbalancerloadbalancingrules-list\n        method: GET\n        description: Azure Networking List load balancing rules\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-azure-networking-rest\n    description: REST adapter for Azure Networking Azure Load Balancer API.\n    resources:\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers\n      name: loadbalancers-list\n      operations:\n      - method: GET\n        name: loadbalancers-list\n        description: Azure Networking List load balancers\n        call: microsoft-azure-networking.loadbalancers-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}\n      name: loadbalancers-get\n      operations:\n      - method: GET\n        name: loadbalancers-get\n        description: Azure Networking Get load\
  \ balancer\n        call: microsoft-azure-networking.loadbalancers-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}\n      name: loadbalancers-createorupdate\n      operations:\n      - method: PUT\n        name: loadbalancers-createorupdate\n        description: Azure Networking Create or update load balancer\n        call: microsoft-azure-networking.loadbalancers-createorupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}\n      name: loadbalancers-delete\n      operations:\n      - method: DELETE\n        name: loadbalancers-delete\n        description: Azure Networking Delete load balancer\n        call: microsoft-azure-networking.loadbalancers-delete\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/providers/Microsoft.Network/loadBalancers\n      name: loadbalancers-listall\n      operations:\n      - method: GET\n        name: loadbalancers-listall\n        description: Azure Networking List all load balancers\n        call: microsoft-azure-networking.loadbalancers-listall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}/backendAddressPools\n      name: loadbalancerbackendaddresspools-list\n      operations:\n      - method: GET\n        name: loadbalancerbackendaddresspools-list\n        description: Azure Networking List backend address pools\n        call: microsoft-azure-networking.loadbalancerbackendaddresspools-list\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}/probes\n      name: loadbalancerprobes-list\n      operations:\n      - method: GET\n        name: loadbalancerprobes-list\n        description: Azure Networking List health probes\n        call: microsoft-azure-networking.loadbalancerprobes-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/loadBalancers/{loadBalancerName}/loadBalancingRules\n      name: loadbalancerloadbalancingrules-list\n      operations:\n      - method: GET\n        name: loadbalancerloadbalancingrules-list\n        description: Azure Networking List load balancing rules\n        call: microsoft-azure-networking.loadbalancerloadbalancingrules-list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port:\
  \ 9090\n    namespace: microsoft-azure-networking-mcp\n    transport: http\n    description: MCP adapter for Azure Networking Azure Load Balancer API for AI agent use.\n    tools:\n    - name: loadbalancers-list\n      description: Azure Networking List load balancers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-networking.loadbalancers-list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loadbalancers-get\n      description: Azure Networking Get load balancer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-networking.loadbalancers-get\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loadbalancers-createorupdate\n      description: Azure Networking Create or update load balancer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n   \
  \   call: microsoft-azure-networking.loadbalancers-createorupdate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loadbalancers-delete\n      description: Azure Networking Delete load balancer\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-azure-networking.loadbalancers-delete\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loadbalancers-listall\n      description: Azure Networking List all load balancers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-networking.loadbalancers-listall\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loadbalancerbackendaddresspools-list\n      description: Azure Networking List backend address pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-networking.loadbalancerbackendaddresspools-list\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loadbalancerprobes-list\n      description: Azure Networking List health probes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-networking.loadbalancerprobes-list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loadbalancerloadbalancingrules-list\n      description: Azure Networking List load balancing rules\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-networking.loadbalancerloadbalancingrules-list\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_AZURE_NETWORKING_TOKEN: MICROSOFT_AZURE_NETWORKING_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure-networking/refs/heads/main/capabilities/microsoft-azure-networking-capability.yaml
tags:
- Microsoft
- Azure
- Networking
- API
tools:
- description: Azure Networking List load balancers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: loadbalancers-list
- description: Azure Networking Get load balancer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: loadbalancers-get
- description: Azure Networking Create or update load balancer
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: loadbalancers-createorupdate
- description: Azure Networking Delete load balancer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: loadbalancers-delete
- description: Azure Networking List all load balancers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: loadbalancers-listall
- description: Azure Networking List backend address pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: loadbalancerbackendaddresspools-list
- description: Azure Networking List health probes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: loadbalancerprobes-list
- description: Azure Networking List load balancing rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: loadbalancerloadbalancingrules-list
---
