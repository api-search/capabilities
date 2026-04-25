---
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
- update endpoint group
- get accelerator details and status
- list all endpoint groups for a listener
- delete an accelerator
- update accelerator
- DevOps Engineer
- traffic routing
- delete accelerator
- describe accelerator
- list listeners
- create endpoint group
- manage a specific accelerator
- create an endpoint group to route traffic to specific aws resources
- create a new accelerator with static ips
- update listener configuration including ports and protocol
- create a new listener
- manage endpoint groups for traffic routing
- availability
- performance
- update listener
- aws
- create a listener for an accelerator specifying ports and protocol
- list accelerators
- manage listeners for accelerators
- amazon global accelerator
- create a new global accelerator with static anycast ip addresses
- update accelerator configuration and settings
- Network Engineer
- list all listeners
- list endpoint groups
- configures and optimizes global network traffic routing
- networking
- load balancing
- create listener
- get detailed status and configuration of a specific accelerator
- list all listeners configured for an accelerator
- global
- update endpoint group traffic settings and weights
- create accelerator
- list all global accelerator accelerators and their static ip addresses
- create an endpoint group
- manages application infrastructure and availability
- list all accelerators
- manage global accelerator accelerators
- cdn
slug: amazon-global-accelerator-network-operations
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
