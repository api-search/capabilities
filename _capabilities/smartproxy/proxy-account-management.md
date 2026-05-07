---
categories: []
consumed_apis: []
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
- get proxy endpoints filtered by type
- create sub user
- list proxy endpoints
- subscription management
- list all available proxy endpoints
- permanently delete a proxy sub-user account
- list proxy endpoints by type
- traffic usage monitoring
- manage specific sub-user
- list whitelisted ips
- network infrastructure
- get total traffic allocation across all sub-users
- account management
- get endpoints
- get endpoints by type
- list all ip addresses whitelisted for credential-free proxy authentication
- remove an ip address from the proxy authentication whitelist
- list all proxy sub-user accounts with their service types and traffic status
- get traffic consumption metrics for a specific proxy sub-user
- data collection
- remove whitelisted ip
- delete proxy sub user
- create a new proxy sub-user
- ip whitelist management
- add ip addresses to the whitelist
- list all available proxy endpoints with hostnames, ports, and protocols
- list proxy sub users
- get whitelisted ips
- datacenter proxies
- add whitelisted ips
- delete a proxy sub-user account
- get sub user traffic
- smartproxy
- get total traffic allocation
- proxy endpoint discovery
- filtered endpoint discovery
- mobile proxies
- get sub users
- get proxy endpoints filtered by connection type (random, sticky, datacenter, mobile)
- traffic management
- residential proxies
- overall traffic allocation
- get traffic usage for a specific sub-user
- delete sub user
- get active subscription plans and usage limits
- update a proxy sub-user's password or traffic limit
- get active subscription plans, traffic limits, and validity dates
- list all proxy sub-user accounts
- get subscriptions
- manage proxy sub-user accounts
- create proxy sub user
- update proxy sub user
- get total traffic gb allocated and consumed across all sub-users
- add one or more ip addresses to the proxy authentication whitelist
- proxies
- get allocated traffic
- web scraping
- create a new proxy sub-user with specified service type and optional traffic limit
- list all whitelisted ip addresses
slug: proxy-account-management
source_filename: proxy-account-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Smartproxy Proxy Account Management\n  description: Unified workflow capability for managing Smartproxy proxy accounts at scale. Enables DevOps teams, data engineers,\n    and web scraping operations to programmatically manage proxy sub-users, monitor traffic consumption, configure IP whitelisting,\n    and discover available proxy endpoints across residential, datacenter, mobile, and ISP proxy networks.\n  tags:\n  - Smartproxy\n  - Proxies\n  - Web Scraping\n  - Data Collection\n  - Account Management\n  - Traffic Management\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SMARTPROXY_API_KEY: SMARTPROXY_API_KEY\n    SMARTPROXY_USER_ID: SMARTPROXY_USER_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: smartproxy\n    baseUri: https://api.decodo.com/v1\n    description: Smartproxy/Decodo account management API\n    authentication:\n      type: apikey\n      key: Authorization\n     \
  \ value: '{{SMARTPROXY_API_KEY}}'\n      placement: header\n    resources:\n    - name: sub-users\n      path: /users/{userId}/sub-users\n      description: Manage proxy sub-user accounts\n      operations:\n      - name: get-sub-users\n        method: GET\n        description: List all proxy sub-users\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: Primary account user ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-sub-user\n        method: POST\n        description: Create a new proxy sub-user account\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            password: '{{tools.password}}'\n            service_type: '{{tools.service_type}}'\n\
  \            traffic_limit: '{{tools.traffic_limit}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-sub-user\n        method: PUT\n        description: Update a sub-user's traffic limit or password\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            password: '{{tools.password}}'\n            traffic_limit: '{{tools.traffic_limit}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sub-user\n      path: /users/{userId}/sub-users/{subUserId}\n      description: Manage specific sub-user\n      operations:\n      - name: delete-sub-user\n        method: DELETE\n        description: Permanently delete a proxy sub-user\n        inputParameters:\n        - name: userId\n\
  \          in: path\n          type: string\n          required: true\n        - name: subUserId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sub-user-traffic\n      path: /users/{userId}/sub-users/{username}/traffic\n      description: Monitor sub-user traffic usage\n      operations:\n      - name: get-sub-user-traffic\n        method: GET\n        description: Get traffic usage for a specific sub-user\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: username\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allocated-traffic\n      path: /users/{userId}/allocated-traffic\n    \
  \  description: Monitor overall traffic allocation\n      operations:\n      - name: get-allocated-traffic\n        method: GET\n        description: Get total allocated traffic across all sub-users\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: whitelisted-ips\n      path: /users/{userId}/whitelisted-ips\n      description: Manage IP whitelist for proxy authentication\n      operations:\n      - name: get-whitelisted-ips\n        method: GET\n        description: List all whitelisted IP addresses\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: add-whitelisted-ips\n \
  \       method: POST\n        description: Add IP addresses to the authentication whitelist\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            IPAddressList: '{{tools.ip_addresses}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: whitelisted-ip\n      path: /users/{userId}/whitelisted-ips/{id}\n      description: Manage specific whitelisted IP\n      operations:\n      - name: delete-whitelisted-ip\n        method: DELETE\n        description: Remove an IP from the whitelist\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: subscriptions\n      path: /users/{userId}/subscriptions\n      description: View subscription details\n      operations:\n      - name: get-subscriptions\n        method: GET\n        description: Get active subscription plans and limits\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: endpoints\n      path: /endpoints\n      description: Discover proxy endpoints\n      operations:\n      - name: get-endpoints\n        method: GET\n        description: List all available proxy endpoints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: endpoints-by-type\n      path: /endpoints/{type}\n      description: Get endpoints filtered by type\n\
  \      operations:\n      - name: get-endpoints-by-type\n        method: GET\n        description: Get proxy endpoints by connection type\n        inputParameters:\n        - name: type\n          in: path\n          type: string\n          required: true\n          description: Endpoint type (random, sticky, datacenter, mobile)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: smartproxy-account-api\n    description: Unified REST API for proxy account and traffic management.\n    resources:\n    - path: /v1/sub-users\n      name: sub-users\n      description: Manage proxy sub-user accounts\n      operations:\n      - method: GET\n        name: get-sub-users\n        description: List all proxy sub-user accounts\n        call: smartproxy.get-sub-users\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: array\n    \
  \      mapping: $.\n      - method: POST\n        name: create-sub-user\n        description: Create a new proxy sub-user\n        call: smartproxy.create-sub-user\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sub-users/{subUserId}\n      name: sub-user\n      description: Manage specific sub-user\n      operations:\n      - method: DELETE\n        name: delete-sub-user\n        description: Delete a proxy sub-user account\n        call: smartproxy.delete-sub-user\n        with:\n          userId: rest.userId\n          subUserId: rest.subUserId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sub-users/{username}/traffic\n      name: sub-user-traffic\n      description: Traffic usage monitoring\n      operations:\n      - method: GET\n        name: get-sub-user-traffic\n        description: Get traffic usage for a specific sub-user\n        call: smartproxy.get-sub-user-traffic\n\
  \        with:\n          userId: rest.userId\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/traffic\n      name: traffic\n      description: Overall traffic allocation\n      operations:\n      - method: GET\n        name: get-allocated-traffic\n        description: Get total traffic allocation across all sub-users\n        call: smartproxy.get-allocated-traffic\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/whitelisted-ips\n      name: whitelisted-ips\n      description: IP whitelist management\n      operations:\n      - method: GET\n        name: get-whitelisted-ips\n        description: List all whitelisted IP addresses\n        call: smartproxy.get-whitelisted-ips\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name:\
  \ add-whitelisted-ips\n        description: Add IP addresses to the whitelist\n        call: smartproxy.add-whitelisted-ips\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscriptions\n      name: subscriptions\n      description: Subscription management\n      operations:\n      - method: GET\n        name: get-subscriptions\n        description: Get active subscription plans and usage limits\n        call: smartproxy.get-subscriptions\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/endpoints\n      name: endpoints\n      description: Proxy endpoint discovery\n      operations:\n      - method: GET\n        name: get-endpoints\n        description: List all available proxy endpoints\n        call: smartproxy.get-endpoints\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/endpoints/{type}\n\
  \      name: endpoints-by-type\n      description: Filtered endpoint discovery\n      operations:\n      - method: GET\n        name: get-endpoints-by-type\n        description: Get proxy endpoints filtered by type\n        call: smartproxy.get-endpoints-by-type\n        with:\n          type: rest.type\n        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: smartproxy-account-mcp\n    transport: http\n    description: MCP server for AI-assisted proxy account and traffic management.\n    tools:\n    - name: list-proxy-sub-users\n      description: List all proxy sub-user accounts with their service types and traffic status\n      hints:\n        readOnly: true\n        openWorld: false\n      call: smartproxy.get-sub-users\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-proxy-sub-user\n      description: Create a new proxy sub-user with specified\
  \ service type and optional traffic limit\n      hints:\n        readOnly: false\n        idempotent: false\n      call: smartproxy.create-sub-user\n      with:\n        userId: tools.userId\n        username: tools.username\n        password: tools.password\n        service_type: tools.service_type\n        traffic_limit: tools.traffic_limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-proxy-sub-user\n      description: Update a proxy sub-user's password or traffic limit\n      hints:\n        readOnly: false\n        idempotent: true\n      call: smartproxy.update-sub-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-proxy-sub-user\n      description: Permanently delete a proxy sub-user account\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: smartproxy.delete-sub-user\n      with:\n        userId: tools.userId\n\
  \        subUserId: tools.subUserId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sub-user-traffic\n      description: Get traffic consumption metrics for a specific proxy sub-user\n      hints:\n        readOnly: true\n        openWorld: false\n      call: smartproxy.get-sub-user-traffic\n      with:\n        userId: tools.userId\n        username: tools.username\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-total-traffic-allocation\n      description: Get total traffic GB allocated and consumed across all sub-users\n      hints:\n        readOnly: true\n        openWorld: false\n      call: smartproxy.get-allocated-traffic\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-whitelisted-ips\n      description: List all IP addresses whitelisted for credential-free proxy authentication\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: smartproxy.get-whitelisted-ips\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: add-whitelisted-ips\n      description: Add one or more IP addresses to the proxy authentication whitelist\n      hints:\n        readOnly: false\n        idempotent: true\n      call: smartproxy.add-whitelisted-ips\n      with:\n        userId: tools.userId\n        ip_addresses: tools.ip_addresses\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-whitelisted-ip\n      description: Remove an IP address from the proxy authentication whitelist\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: smartproxy.delete-whitelisted-ip\n      with:\n        userId: tools.userId\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-subscriptions\n      description: Get active subscription\
  \ plans, traffic limits, and validity dates\n      hints:\n        readOnly: true\n        openWorld: false\n      call: smartproxy.get-subscriptions\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-proxy-endpoints\n      description: List all available proxy endpoints with hostnames, ports, and protocols\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smartproxy.get-endpoints\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-proxy-endpoints-by-type\n      description: Get proxy endpoints filtered by connection type (random, sticky, datacenter, mobile)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smartproxy.get-endpoints-by-type\n      with:\n        type: tools.type\n      outputParameters:\n      - type: array\n        mapping: $.\n"
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
