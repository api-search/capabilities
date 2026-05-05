---
categories: []
consumed_apis:
- routeros
description: Unified network management capability for RouterOS-powered MikroTik devices. Combines IP address management, interface configuration, firewall policy, routing, DHCP, DNS, and wireless client monitoring into a single workflow for network administrators managing MikroTik infrastructure.
layout: capability
name: RouterOS Network Management
operations:
- description: List all IP addresses assigned to router interfaces
  method: GET
  name: list-ip-addresses
  path: /v1/ip/addresses
- description: Assign an IP address to a router interface
  method: PUT
  name: add-ip-address
  path: /v1/ip/addresses
- description: List all network interfaces with status
  method: GET
  name: list-interfaces
  path: /v1/interfaces
- description: List all firewall filter rules by chain and action
  method: GET
  name: list-firewall-filters
  path: /v1/firewall/filters
- description: Add a new firewall filter rule
  method: PUT
  name: add-firewall-filter
  path: /v1/firewall/filters
- description: List all NAT rules
  method: GET
  name: list-firewall-nat
  path: /v1/firewall/nat
- description: List all address list entries
  method: GET
  name: list-address-lists
  path: /v1/firewall/address-lists
- description: Add an IP address to a named firewall list
  method: PUT
  name: add-address-list-entry
  path: /v1/firewall/address-lists
- description: List all routes in the routing table
  method: GET
  name: list-routes
  path: /v1/routing/routes
- description: Add a static route
  method: PUT
  name: add-route
  path: /v1/routing/routes
- description: Get CPU, memory, storage, and uptime information
  method: GET
  name: get-system-resource
  path: /v1/system/resource
- description: List all DHCP leases including client hostnames and MAC addresses
  method: GET
  name: list-dhcp-leases
  path: /v1/dhcp/leases
- description: Get DNS server configuration
  method: GET
  name: get-dns-settings
  path: /v1/dns
- description: Update DNS server addresses
  method: PATCH
  name: update-dns-settings
  path: /v1/dns
- description: List all currently connected wireless clients with signal strength
  method: GET
  name: list-wireless-clients
  path: /v1/wireless/clients
personas: []
provider_name: RouterOS
provider_slug: routeros
search_terms:
- add a static route with destination network and gateway
- get current dns server addresses and cache configuration
- list wireless clients
- list all ip addresses assigned to router interfaces
- list interfaces
- list all network interfaces with running status, type, and mac address
- manage ip address assignments on router interfaces
- list all routes in the routing table
- list entries in named firewall address lists
- list all ip addresses configured on router interfaces
- list all connected wireless clients with signal strength, mac address, and uptime
- update dns server addresses
- add a new firewall filter rule
- firewall nat rules for masquerading and port forwarding
- connected wireless client monitoring
- get cpu, memory, storage, and uptime information
- dhcp server lease table
- block or classify an ip by adding it to a named firewall address list
- list routing table entries; optionally filter by active routes only
- get dns settings
- get dns server configuration
- list all network interfaces with status
- list firewall filters
- list all address list entries
- device resource utilization and hardware information
- named address lists for use in firewall rules
- add ip address
- add an ip address to a named firewall list
- list firewall nat
- network interface status and configuration
- add a static route
- list all currently connected wireless clients with signal strength
- firewall packet filter rules
- list nat rules for masquerading, source nat, and destination nat
- list all nat rules
- list address lists
- static and dynamic routing table entries
- network management
- list ip addresses
- routers
- list all dhcp leases showing client hostname, mac address, and assigned ip
- dhcp
- networking
- routeros
- mikrotik
- add route
- get routeros device cpu load, memory usage, uptime, and version information
- list all dhcp leases including client hostnames and mac addresses
- list firewall filter rules; filter by chain (input/forward/output) or action
- add a packet filter rule specifying chain, action, source/destination addresses
- add firewall filter
- assign an ip address to a router interface
- add address list entry
- get system resource
- list routes
- list dhcp leases
- list all firewall filter rules by chain and action
- firewall
- dns resolver configuration
- assign a new ip address to a router interface (cidr notation required)
- dns
- update dns settings
- router
slug: network-management
source_filename: network-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: RouterOS Network Management\n  description: >-\n    Unified network management capability for RouterOS-powered MikroTik devices.\n    Combines IP address management, interface configuration, firewall policy,\n    routing, DHCP, DNS, and wireless client monitoring into a single workflow\n    for network administrators managing MikroTik infrastructure.\n  tags:\n    - RouterOS\n    - MikroTik\n    - Networking\n    - Network Management\n    - Firewall\n    - Router\n    - DHCP\n    - DNS\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      ROUTEROS_USERNAME: ROUTEROS_USERNAME\n      ROUTEROS_PASSWORD: ROUTEROS_PASSWORD\n      ROUTEROS_HOST: ROUTEROS_HOST\n\ncapability:\n  consumes:\n    - import: routeros\n      location: ./shared/routeros-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: network-management-api\n      description: \"Unified REST API for RouterOS\
  \ network device management.\"\n      resources:\n        - path: /v1/ip/addresses\n          name: ip-addresses\n          description: Manage IP address assignments on router interfaces\n          operations:\n            - method: GET\n              name: list-ip-addresses\n              description: List all IP addresses assigned to router interfaces\n              call: \"routeros.list-ip-addresses\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: PUT\n              name: add-ip-address\n              description: Assign an IP address to a router interface\n              call: \"routeros.add-ip-address\"\n              with:\n                address: \"rest.address\"\n                interface: \"rest.interface\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/interfaces\n          name: interfaces\n          description: Network interface\
  \ status and configuration\n          operations:\n            - method: GET\n              name: list-interfaces\n              description: List all network interfaces with status\n              call: \"routeros.list-interfaces\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/firewall/filters\n          name: firewall-filters\n          description: Firewall packet filter rules\n          operations:\n            - method: GET\n              name: list-firewall-filters\n              description: List all firewall filter rules by chain and action\n              call: \"routeros.list-firewall-filters\"\n              with:\n                chain: \"rest.chain\"\n                action: \"rest.action\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: PUT\n              name: add-firewall-filter\n              description: Add a new firewall\
  \ filter rule\n              call: \"routeros.add-firewall-filter\"\n              with:\n                chain: \"rest.chain\"\n                action: \"rest.action\"\n                src-address: \"rest.src_address\"\n                dst-address: \"rest.dst_address\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/firewall/nat\n          name: firewall-nat\n          description: Firewall NAT rules for masquerading and port forwarding\n          operations:\n            - method: GET\n              name: list-firewall-nat\n              description: List all NAT rules\n              call: \"routeros.list-firewall-nat\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/firewall/address-lists\n          name: address-lists\n          description: Named address lists for use in firewall rules\n          operations:\n            - method: GET\n\
  \              name: list-address-lists\n              description: List all address list entries\n              call: \"routeros.list-address-lists\"\n              with:\n                list: \"rest.list\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: PUT\n              name: add-address-list-entry\n              description: Add an IP address to a named firewall list\n              call: \"routeros.add-address-list-entry\"\n              with:\n                list: \"rest.list\"\n                address: \"rest.address\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/routing/routes\n          name: routes\n          description: Static and dynamic routing table entries\n          operations:\n            - method: GET\n              name: list-routes\n              description: List all routes in the routing table\n              call:\
  \ \"routeros.list-routes\"\n              with:\n                active: \"rest.active\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: PUT\n              name: add-route\n              description: Add a static route\n              call: \"routeros.add-route\"\n              with:\n                dst-address: \"rest.dst_address\"\n                gateway: \"rest.gateway\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/system/resource\n          name: system-resource\n          description: Device resource utilization and hardware information\n          operations:\n            - method: GET\n              name: get-system-resource\n              description: Get CPU, memory, storage, and uptime information\n              call: \"routeros.get-system-resource\"\n              outputParameters:\n                - type: object\n          \
  \        mapping: \"$.\"\n\n        - path: /v1/dhcp/leases\n          name: dhcp-leases\n          description: DHCP server lease table\n          operations:\n            - method: GET\n              name: list-dhcp-leases\n              description: List all DHCP leases including client hostnames and MAC addresses\n              call: \"routeros.list-dhcp-leases\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/dns\n          name: dns-settings\n          description: DNS resolver configuration\n          operations:\n            - method: GET\n              name: get-dns-settings\n              description: Get DNS server configuration\n              call: \"routeros.get-dns-settings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-dns-settings\n              description: Update DNS server addresses\n\
  \              call: \"routeros.update-dns-settings\"\n              with:\n                servers: \"rest.servers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/wireless/clients\n          name: wireless-clients\n          description: Connected wireless client monitoring\n          operations:\n            - method: GET\n              name: list-wireless-clients\n              description: List all currently connected wireless clients with signal strength\n              call: \"routeros.list-wireless-clients\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: network-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted RouterOS network device management.\"\n      tools:\n        - name: list-ip-addresses\n          description: List all IP addresses configured on router\
  \ interfaces\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"routeros.list-ip-addresses\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: add-ip-address\n          description: Assign a new IP address to a router interface (CIDR notation required)\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"routeros.add-ip-address\"\n          with:\n            address: \"tools.address\"\n            interface: \"tools.interface\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-interfaces\n          description: List all network interfaces with running status, type, and MAC address\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"routeros.list-interfaces\"\n          outputParameters:\n            - type: array\n              mapping: \"\
  $.\"\n\n        - name: list-firewall-filters\n          description: List firewall filter rules; filter by chain (input/forward/output) or action\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"routeros.list-firewall-filters\"\n          with:\n            chain: \"tools.chain\"\n            action: \"tools.action\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: add-firewall-filter\n          description: Add a packet filter rule specifying chain, action, source/destination addresses\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"routeros.add-firewall-filter\"\n          with:\n            chain: \"tools.chain\"\n            action: \"tools.action\"\n            src-address: \"tools.src_address\"\n            dst-address: \"tools.dst_address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \n        - name: list-firewall-nat\n          description: List NAT rules for masquerading, source NAT, and destination NAT\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"routeros.list-firewall-nat\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-address-lists\n          description: List entries in named firewall address lists\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"routeros.list-address-lists\"\n          with:\n            list: \"tools.list\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: add-address-list-entry\n          description: Block or classify an IP by adding it to a named firewall address list\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"routeros.add-address-list-entry\"\n          with:\n        \
  \    list: \"tools.list\"\n            address: \"tools.address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-routes\n          description: List routing table entries; optionally filter by active routes only\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"routeros.list-routes\"\n          with:\n            active: \"tools.active\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: add-route\n          description: Add a static route with destination network and gateway\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"routeros.add-route\"\n          with:\n            dst-address: \"tools.dst_address\"\n            gateway: \"tools.gateway\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-system-resource\n  \
  \        description: Get RouterOS device CPU load, memory usage, uptime, and version information\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"routeros.get-system-resource\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-dhcp-leases\n          description: List all DHCP leases showing client hostname, MAC address, and assigned IP\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"routeros.list-dhcp-leases\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-dns-settings\n          description: Get current DNS server addresses and cache configuration\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"routeros.get-dns-settings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name:\
  \ list-wireless-clients\n          description: List all connected wireless clients with signal strength, MAC address, and uptime\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"routeros.list-wireless-clients\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/routeros/refs/heads/main/capabilities/network-management.yaml
tags:
- RouterOS
- MikroTik
- Networking
- Network Management
- Firewall
- Router
- DHCP
- DNS
tools:
- description: List all IP addresses configured on router interfaces
  hints:
    idempotent: true
    readOnly: true
  name: list-ip-addresses
- description: Assign a new IP address to a router interface (CIDR notation required)
  hints:
    idempotent: false
    readOnly: false
  name: add-ip-address
- description: List all network interfaces with running status, type, and MAC address
  hints:
    idempotent: true
    readOnly: true
  name: list-interfaces
- description: List firewall filter rules; filter by chain (input/forward/output) or action
  hints:
    idempotent: true
    readOnly: true
  name: list-firewall-filters
- description: Add a packet filter rule specifying chain, action, source/destination addresses
  hints:
    idempotent: false
    readOnly: false
  name: add-firewall-filter
- description: List NAT rules for masquerading, source NAT, and destination NAT
  hints:
    idempotent: true
    readOnly: true
  name: list-firewall-nat
- description: List entries in named firewall address lists
  hints:
    idempotent: true
    readOnly: true
  name: list-address-lists
- description: Block or classify an IP by adding it to a named firewall address list
  hints:
    idempotent: false
    readOnly: false
  name: add-address-list-entry
- description: List routing table entries; optionally filter by active routes only
  hints:
    idempotent: true
    readOnly: true
  name: list-routes
- description: Add a static route with destination network and gateway
  hints:
    idempotent: false
    readOnly: false
  name: add-route
- description: Get RouterOS device CPU load, memory usage, uptime, and version information
  hints:
    idempotent: true
    readOnly: true
  name: get-system-resource
- description: List all DHCP leases showing client hostname, MAC address, and assigned IP
  hints:
    idempotent: true
    readOnly: true
  name: list-dhcp-leases
- description: Get current DNS server addresses and cache configuration
  hints:
    idempotent: true
    readOnly: true
  name: get-dns-settings
- description: List all connected wireless clients with signal strength, MAC address, and uptime
  hints:
    idempotent: true
    readOnly: true
  name: list-wireless-clients
---
