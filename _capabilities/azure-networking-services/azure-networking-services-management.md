---
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
- infrastructure
- cloud
- list subnet resources
- resource management
- list load balancers
- list loadbalancer resources
- list subnets
- list network interfaces
- management
- list virtualnetwork resources
- list networkinterface resources
- azure resource management
- microsoft
- list virtual networks
- networking
- list
- azure
- list all resources
slug: azure-networking-services-management
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
