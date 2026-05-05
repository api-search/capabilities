---
categories: []
consumed_apis:
- weave-net
description: Unified container networking workflow for managing Weave Net's IPAM, peer connections, DNS, and network status. Used by DevOps engineers and platform operators to automate container network management.
layout: capability
name: Weave Net Container Networking
operations:
- description: Get Weave Net daemon status
  method: GET
  name: get-status
  path: /v1/status
- description: Connect to a remote peer
  method: POST
  name: connect-peer
  path: /v1/peers
- description: Allocate IP for a container
  method: POST
  name: allocate-ip
  path: /v1/ipam/allocations
- description: Look up container IP
  method: GET
  name: lookup-ip
  path: /v1/ipam/allocations/{containerId}
- description: Release container IPs
  method: DELETE
  name: release-ips
  path: /v1/ipam/allocations/{containerId}
- description: Get default IPAM subnet
  method: GET
  name: get-default-subnet
  path: /v1/ipam/subnet
- description: Get WeaveDNS domain
  method: GET
  name: get-dns-domain
  path: /v1/dns/domain
- description: Register container DNS name
  method: PUT
  name: register-dns
  path: /v1/dns/registrations/{containerId}/{ip}
- description: Deregister container DNS name
  method: DELETE
  name: deregister-dns
  path: /v1/dns/registrations/{containerId}/{ip}
personas: []
provider_name: Weave Net
provider_slug: weave-net
search_terms:
- containers
- deregister dns
- ip address allocations
- get dns domain
- allocate ip for a container
- dns name registrations
- get default subnet
- docker
- lookup container ip
- open source
- connect peer
- connect to a remote peer
- get weavedns domain
- ipam
- get the weavedns domain suffix for name resolution
- get daemon status
- release ips
- lookup ip
- register dns
- allocate ip
- deregister container dns name
- allocate container ip
- get default ipam subnet
- daemon status
- get weave net daemon status
- default subnet information
- get the current status of the weave net daemon including peers and ipam state
- deregister a container's dns name from weavedns
- release container ips
- devops
- allocate an ip address for a container on the weave network
- look up container ip
- get status
- deregister container dns
- networking
- container ip allocation
- dns domain
- peer connection management
- register a dns name for a container in weavedns
- connect to peer
- get the default subnet used for ipam allocation
- cncf
- register container dns name
- connect weave net to a remote peer node
- dns
- kubernetes
- register container dns
- look up the ip address allocated to a container
- release all ip addresses allocated to a container
slug: container-networking
source_filename: container-networking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Weave Net Container Networking\"\n  description: \"Unified container networking workflow for managing Weave Net's IPAM, peer connections, DNS, and network status. Used by DevOps engineers and platform operators to automate container network management.\"\n  tags:\n    - Containers\n    - Networking\n    - Kubernetes\n    - IPAM\n    - DNS\n    - DevOps\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WEAVE_NET_HOST: WEAVE_NET_HOST\n\ncapability:\n  consumes:\n    - import: weave-net\n      location: ./shared/weave-net-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: container-networking-api\n      description: \"Unified REST API for Weave Net container networking management.\"\n      resources:\n        - path: /v1/status\n          name: status\n          description: \"Daemon status\"\n          operations:\n            - method: GET\n         \
  \     name: get-status\n              description: \"Get Weave Net daemon status\"\n              call: \"weave-net.get-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/peers\n          name: peers\n          description: \"Peer connection management\"\n          operations:\n            - method: POST\n              name: connect-peer\n              description: \"Connect to a remote peer\"\n              call: \"weave-net.connect-peer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ipam/allocations\n          name: ipam-allocations\n          description: \"IP address allocations\"\n          operations:\n            - method: POST\n              name: allocate-ip\n              description: \"Allocate IP for a container\"\n              call: \"weave-net.allocate-ip\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/ipam/allocations/{containerId}\n          name: ipam-allocation\n          description: \"Container IP allocation\"\n          operations:\n            - method: GET\n              name: lookup-ip\n              description: \"Look up container IP\"\n              call: \"weave-net.lookup-ip\"\n              with:\n                containerId: \"rest.containerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: release-ips\n              description: \"Release container IPs\"\n              call: \"weave-net.release-ips\"\n              with:\n                containerId: \"rest.containerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ipam/subnet\n          name: default-subnet\n          description: \"Default subnet information\"\n          operations:\n\
  \            - method: GET\n              name: get-default-subnet\n              description: \"Get default IPAM subnet\"\n              call: \"weave-net.get-default-subnet\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/dns/domain\n          name: dns-domain\n          description: \"DNS domain\"\n          operations:\n            - method: GET\n              name: get-dns-domain\n              description: \"Get WeaveDNS domain\"\n              call: \"weave-net.get-dns-domain\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/dns/registrations/{containerId}/{ip}\n          name: dns-registration\n          description: \"DNS name registrations\"\n          operations:\n            - method: PUT\n              name: register-dns\n              description: \"Register container DNS name\"\n              call: \"weave-net.register-dns\"\n\
  \              with:\n                containerId: \"rest.containerId\"\n                ip: \"rest.ip\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: deregister-dns\n              description: \"Deregister container DNS name\"\n              call: \"weave-net.deregister-dns\"\n              with:\n                containerId: \"rest.containerId\"\n                ip: \"rest.ip\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: container-networking-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Weave Net container networking management.\"\n      tools:\n        - name: get-daemon-status\n          description: \"Get the current status of the Weave Net daemon including peers and IPAM state\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ false\n          call: \"weave-net.get-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: connect-to-peer\n          description: \"Connect Weave Net to a remote peer node\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"weave-net.connect-peer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: allocate-container-ip\n          description: \"Allocate an IP address for a container on the Weave network\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"weave-net.allocate-ip\"\n          with:\n            containerId: \"tools.containerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-container-ip\n          description: \"Look up the IP address allocated to a container\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: false\n          call: \"weave-net.lookup-ip\"\n          with:\n            containerId: \"tools.containerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: release-container-ips\n          description: \"Release all IP addresses allocated to a container\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"weave-net.release-ips\"\n          with:\n            containerId: \"tools.containerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-default-subnet\n          description: \"Get the default subnet used for IPAM allocation\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"weave-net.get-default-subnet\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dns-domain\n          description:\
  \ \"Get the WeaveDNS domain suffix for name resolution\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"weave-net.get-dns-domain\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: register-container-dns\n          description: \"Register a DNS name for a container in WeaveDNS\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"weave-net.register-dns\"\n          with:\n            containerId: \"tools.containerId\"\n            ip: \"tools.ip\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deregister-container-dns\n          description: \"Deregister a container's DNS name from WeaveDNS\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"weave-net.deregister-dns\"\n          with:\n            containerId: \"tools.containerId\"\n    \
  \        ip: \"tools.ip\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/weave-net/refs/heads/main/capabilities/container-networking.yaml
tags:
- Containers
- Networking
- Kubernetes
- IPAM
- DNS
- DevOps
tools:
- description: Get the current status of the Weave Net daemon including peers and IPAM state
  hints:
    openWorld: false
    readOnly: true
  name: get-daemon-status
- description: Connect Weave Net to a remote peer node
  hints:
    idempotent: true
    readOnly: false
  name: connect-to-peer
- description: Allocate an IP address for a container on the Weave network
  hints:
    idempotent: false
    readOnly: false
  name: allocate-container-ip
- description: Look up the IP address allocated to a container
  hints:
    openWorld: false
    readOnly: true
  name: lookup-container-ip
- description: Release all IP addresses allocated to a container
  hints:
    destructive: true
    readOnly: false
  name: release-container-ips
- description: Get the default subnet used for IPAM allocation
  hints:
    openWorld: false
    readOnly: true
  name: get-default-subnet
- description: Get the WeaveDNS domain suffix for name resolution
  hints:
    openWorld: false
    readOnly: true
  name: get-dns-domain
- description: Register a DNS name for a container in WeaveDNS
  hints:
    idempotent: true
    readOnly: false
  name: register-container-dns
- description: Deregister a container's DNS name from WeaveDNS
  hints:
    destructive: true
    readOnly: false
  name: deregister-container-dns
---
