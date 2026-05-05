---
api_specs:
- filename: smartproxy-openapi.yml
  format: yaml
  label: smartproxy
  slug: smartproxy
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/smartproxy/refs/heads/main/openapi/smartproxy-openapi.yml
categories: []
consumed_apis:
- smartproxy
description: Unified workflow capability for managing Smartproxy proxy accounts at scale. Enables DevOps teams, data engineers, and web scraping operations to programmatically manage proxy sub-users, monitor traffic consumption, configure IP whitelisting, and discover available proxy endpoints across residential, datacenter, mobile, and ISP proxy networks.
layout: capability
name: Smartproxy Proxy Account Management
operations:
- description: List all proxy sub-user accounts
  method: GET
  name: get-sub-users
  path: /v1/sub-users
- description: Create a new proxy sub-user
  method: POST
  name: create-sub-user
  path: /v1/sub-users
- description: Delete a proxy sub-user account
  method: DELETE
  name: delete-sub-user
  path: /v1/sub-users/{subUserId}
- description: Get traffic usage for a specific sub-user
  method: GET
  name: get-sub-user-traffic
  path: /v1/sub-users/{username}/traffic
- description: Get total traffic allocation across all sub-users
  method: GET
  name: get-allocated-traffic
  path: /v1/traffic
- description: List all whitelisted IP addresses
  method: GET
  name: get-whitelisted-ips
  path: /v1/whitelisted-ips
- description: Add IP addresses to the whitelist
  method: POST
  name: add-whitelisted-ips
  path: /v1/whitelisted-ips
- description: Get active subscription plans and usage limits
  method: GET
  name: get-subscriptions
  path: /v1/subscriptions
- description: List all available proxy endpoints
  method: GET
  name: get-endpoints
  path: /v1/endpoints
- description: Get proxy endpoints filtered by type
  method: GET
  name: get-endpoints-by-type
  path: /v1/endpoints/{type}
personas: []
provider_name: Smartproxy
provider_slug: smartproxy
search_terms:
- account management
- get subscriptions
- get active subscription plans and usage limits
- filtered endpoint discovery
- list proxy sub users
- manage specific sub-user
- subscription management
- proxies
- list all ip addresses whitelisted for credential-free proxy authentication
- smartproxy
- permanently delete a proxy sub-user account
- get proxy endpoints filtered by connection type (random, sticky, datacenter, mobile)
- list proxy endpoints by type
- create proxy sub user
- datacenter proxies
- create sub user
- list all proxy sub-user accounts with their service types and traffic status
- update a proxy sub-user's password or traffic limit
- web scraping
- get allocated traffic
- delete proxy sub user
- update proxy sub user
- list all available proxy endpoints
- get sub users
- add whitelisted ips
- list all available proxy endpoints with hostnames, ports, and protocols
- data collection
- network infrastructure
- get sub user traffic
- remove an ip address from the proxy authentication whitelist
- proxy endpoint discovery
- list all whitelisted ip addresses
- get proxy endpoints filtered by type
- create a new proxy sub-user with specified service type and optional traffic limit
- traffic management
- create a new proxy sub-user
- get total traffic gb allocated and consumed across all sub-users
- get total traffic allocation
- list whitelisted ips
- get active subscription plans, traffic limits, and validity dates
- list proxy endpoints
- get whitelisted ips
- ip whitelist management
- mobile proxies
- delete a proxy sub-user account
- residential proxies
- remove whitelisted ip
- list all proxy sub-user accounts
- manage proxy sub-user accounts
- add one or more ip addresses to the proxy authentication whitelist
- get endpoints
- add ip addresses to the whitelist
- get traffic consumption metrics for a specific proxy sub-user
- get traffic usage for a specific sub-user
- get endpoints by type
- overall traffic allocation
- get total traffic allocation across all sub-users
- delete sub user
- traffic usage monitoring
slug: proxy-account-management
source_filename: proxy-account-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Smartproxy Proxy Account Management\n  description: >-\n    Unified workflow capability for managing Smartproxy proxy accounts at scale.\n    Enables DevOps teams, data engineers, and web scraping operations to\n    programmatically manage proxy sub-users, monitor traffic consumption,\n    configure IP whitelisting, and discover available proxy endpoints across\n    residential, datacenter, mobile, and ISP proxy networks.\n  tags:\n    - Smartproxy\n    - Proxies\n    - Web Scraping\n    - Data Collection\n    - Account Management\n    - Traffic Management\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SMARTPROXY_API_KEY: SMARTPROXY_API_KEY\n      SMARTPROXY_USER_ID: SMARTPROXY_USER_ID\n\ncapability:\n  consumes:\n    - import: smartproxy\n      location: ./shared/smartproxy.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: smartproxy-account-api\n   \
  \   description: Unified REST API for proxy account and traffic management.\n      resources:\n        - path: /v1/sub-users\n          name: sub-users\n          description: Manage proxy sub-user accounts\n          operations:\n            - method: GET\n              name: get-sub-users\n              description: List all proxy sub-user accounts\n              call: \"smartproxy.get-sub-users\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-sub-user\n              description: Create a new proxy sub-user\n              call: \"smartproxy.create-sub-user\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sub-users/{subUserId}\n          name: sub-user\n          description: Manage specific\
  \ sub-user\n          operations:\n            - method: DELETE\n              name: delete-sub-user\n              description: Delete a proxy sub-user account\n              call: \"smartproxy.delete-sub-user\"\n              with:\n                userId: \"rest.userId\"\n                subUserId: \"rest.subUserId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sub-users/{username}/traffic\n          name: sub-user-traffic\n          description: Traffic usage monitoring\n          operations:\n            - method: GET\n              name: get-sub-user-traffic\n              description: Get traffic usage for a specific sub-user\n              call: \"smartproxy.get-sub-user-traffic\"\n              with:\n                userId: \"rest.userId\"\n                username: \"rest.username\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/traffic\n\
  \          name: traffic\n          description: Overall traffic allocation\n          operations:\n            - method: GET\n              name: get-allocated-traffic\n              description: Get total traffic allocation across all sub-users\n              call: \"smartproxy.get-allocated-traffic\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/whitelisted-ips\n          name: whitelisted-ips\n          description: IP whitelist management\n          operations:\n            - method: GET\n              name: get-whitelisted-ips\n              description: List all whitelisted IP addresses\n              call: \"smartproxy.get-whitelisted-ips\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name:\
  \ add-whitelisted-ips\n              description: Add IP addresses to the whitelist\n              call: \"smartproxy.add-whitelisted-ips\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: Subscription management\n          operations:\n            - method: GET\n              name: get-subscriptions\n              description: Get active subscription plans and usage limits\n              call: \"smartproxy.get-subscriptions\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/endpoints\n          name: endpoints\n          description: Proxy endpoint discovery\n          operations:\n            - method: GET\n              name: get-endpoints\n           \
  \   description: List all available proxy endpoints\n              call: \"smartproxy.get-endpoints\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/endpoints/{type}\n          name: endpoints-by-type\n          description: Filtered endpoint discovery\n          operations:\n            - method: GET\n              name: get-endpoints-by-type\n              description: Get proxy endpoints filtered by type\n              call: \"smartproxy.get-endpoints-by-type\"\n              with:\n                type: \"rest.type\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: smartproxy-account-mcp\n      transport: http\n      description: MCP server for AI-assisted proxy account and traffic management.\n      tools:\n        - name: list-proxy-sub-users\n          description: List all proxy sub-user accounts with their\
  \ service types and traffic status\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartproxy.get-sub-users\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: create-proxy-sub-user\n          description: Create a new proxy sub-user with specified service type and optional traffic limit\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"smartproxy.create-sub-user\"\n          with:\n            userId: \"tools.userId\"\n            username: \"tools.username\"\n            password: \"tools.password\"\n            service_type: \"tools.service_type\"\n            traffic_limit: \"tools.traffic_limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-proxy-sub-user\n          description: Update a proxy sub-user's password or\
  \ traffic limit\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"smartproxy.update-sub-user\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-proxy-sub-user\n          description: Permanently delete a proxy sub-user account\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"smartproxy.delete-sub-user\"\n          with:\n            userId: \"tools.userId\"\n            subUserId: \"tools.subUserId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-sub-user-traffic\n          description: Get traffic consumption metrics for a specific proxy sub-user\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartproxy.get-sub-user-traffic\"\n          with:\n\
  \            userId: \"tools.userId\"\n            username: \"tools.username\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-total-traffic-allocation\n          description: Get total traffic GB allocated and consumed across all sub-users\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartproxy.get-allocated-traffic\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-whitelisted-ips\n          description: List all IP addresses whitelisted for credential-free proxy authentication\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartproxy.get-whitelisted-ips\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name:\
  \ add-whitelisted-ips\n          description: Add one or more IP addresses to the proxy authentication whitelist\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"smartproxy.add-whitelisted-ips\"\n          with:\n            userId: \"tools.userId\"\n            ip_addresses: \"tools.ip_addresses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: remove-whitelisted-ip\n          description: Remove an IP address from the proxy authentication whitelist\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"smartproxy.delete-whitelisted-ip\"\n          with:\n            userId: \"tools.userId\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-subscriptions\n          description: Get active subscription plans, traffic limits,\
  \ and validity dates\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartproxy.get-subscriptions\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: list-proxy-endpoints\n          description: List all available proxy endpoints with hostnames, ports, and protocols\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smartproxy.get-endpoints\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: list-proxy-endpoints-by-type\n          description: Get proxy endpoints filtered by connection type (random, sticky, datacenter, mobile)\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smartproxy.get-endpoints-by-type\"\n          with:\n            type: \"tools.type\"\n          outputParameters:\n   \
  \         - type: array\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/smartproxy/refs/heads/main/capabilities/proxy-account-management.yaml
tags:
- Smartproxy
- Proxies
- Web Scraping
- Data Collection
- Account Management
- Traffic Management
tools:
- description: List all proxy sub-user accounts with their service types and traffic status
  hints:
    openWorld: false
    readOnly: true
  name: list-proxy-sub-users
- description: Create a new proxy sub-user with specified service type and optional traffic limit
  hints:
    idempotent: false
    readOnly: false
  name: create-proxy-sub-user
- description: Update a proxy sub-user's password or traffic limit
  hints:
    idempotent: true
    readOnly: false
  name: update-proxy-sub-user
- description: Permanently delete a proxy sub-user account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-proxy-sub-user
- description: Get traffic consumption metrics for a specific proxy sub-user
  hints:
    openWorld: false
    readOnly: true
  name: get-sub-user-traffic
- description: Get total traffic GB allocated and consumed across all sub-users
  hints:
    openWorld: false
    readOnly: true
  name: get-total-traffic-allocation
- description: List all IP addresses whitelisted for credential-free proxy authentication
  hints:
    openWorld: false
    readOnly: true
  name: list-whitelisted-ips
- description: Add one or more IP addresses to the proxy authentication whitelist
  hints:
    idempotent: true
    readOnly: false
  name: add-whitelisted-ips
- description: Remove an IP address from the proxy authentication whitelist
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-whitelisted-ip
- description: Get active subscription plans, traffic limits, and validity dates
  hints:
    openWorld: false
    readOnly: true
  name: get-subscriptions
- description: List all available proxy endpoints with hostnames, ports, and protocols
  hints:
    openWorld: true
    readOnly: true
  name: list-proxy-endpoints
- description: Get proxy endpoints filtered by connection type (random, sticky, datacenter, mobile)
  hints:
    openWorld: true
    readOnly: true
  name: list-proxy-endpoints-by-type
---
