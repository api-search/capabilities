---
categories: []
consumed_apis: []
description: Unified workflow for API security operations using the Wallarm platform. Enables security teams to monitor attacks, investigate vulnerabilities, manage IP blocklists, configure security rules, and coordinate incident response workflows across API infrastructure.
layout: capability
name: Wallarm API Security Operations
operations:
- description: List security attacks detected by Wallarm
  method: GET
  name: list-attacks
  path: /v1/attacks
- description: List vulnerabilities detected across APIs
  method: GET
  name: list-vulnerabilities
  path: /v1/vulnerabilities
- description: List configured security rules and virtual patches
  method: GET
  name: list-rules
  path: /v1/rules
- description: Create a new security rule or virtual patch
  method: POST
  name: create-rule
  path: /v1/rules
- description: Delete a security rule by ID
  method: DELETE
  name: delete-rule
  path: /v1/rules
- description: List IP rules from all IP lists
  method: GET
  name: list-ip-rules
  path: /v1/ip-rules
- description: Add an IP or subnet to a blocklist or allowlist
  method: POST
  name: add-ip-rule
  path: /v1/ip-rules
- description: Remove an IP rule from a list
  method: DELETE
  name: delete-ip-rule
  path: /v1/ip-rules
- description: List all deployed Wallarm filter nodes
  method: GET
  name: list-nodes
  path: /v1/nodes
- description: List configured SIEM and notification integrations
  method: GET
  name: list-integrations
  path: /v1/integrations
- description: List configured automated security triggers
  method: GET
  name: list-triggers
  path: /v1/triggers
personas: []
provider_name: Wallarm
provider_slug: wallarm
search_terms:
- list configured security rules and virtual patches
- create rule
- vulnerability management
- list security attacks detected by wallarm across api infrastructure
- remove an ip address or subnet from a blocklist
- list vulnerabilities detected across monitored apis
- list security attacks detected by wallarm
- add ip rule
- attack detection
- list vulnerabilities
- list vulnerabilities detected across apis
- list nodes
- list all deployed wallarm filter nodes
- list automated security alert triggers
- delete rule
- list triggers
- list all entries in wallarm ip allowlists, denylists, and graylists
- third-party security integrations
- remove an ip rule from a list
- add an ip address or subnet to the denylist
- list ip rules from all ip lists
- list attacks
- list integrations
- create security rule
- wallarm filter node inventory
- waf
- create a virtual patch or custom security rule to block an attack vector
- ip list management (allowlist, denylist, graylist)
- list all configured security rules and virtual patches
- list all wallarm filter nodes deployed in the environment
- automated alert triggers
- delete ip rule
- list configured siem and notification integrations
- detected vulnerability data
- list rules
- create a new security rule or virtual patch
- block ip address
- api security
- list ip rules
- delete a security rule by id
- incident response
- add an ip or subnet to a blocklist or allowlist
- list configured automated security triggers
- detected attack data
- cybersecurity
- remove ip block
- security rule management
- security testing
slug: api-security-operations
source_filename: api-security-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Wallarm API Security Operations\n  description: Unified workflow for API security operations using the Wallarm platform. Enables security teams to monitor\n    attacks, investigate vulnerabilities, manage IP blocklists, configure security rules, and coordinate incident response\n    workflows across API infrastructure.\n  tags:\n  - API Security\n  - Attack Detection\n  - Vulnerability Management\n  - Incident Response\n  - WAF\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WALLARM_API_TOKEN: WALLARM_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: wallarm\n    baseUri: https://us1.api.wallarm.com\n    description: Wallarm API Security Platform REST API\n    authentication:\n      type: apikey\n      key: X-WallarmApi-Token\n      value: '{{WALLARM_API_TOKEN}}'\n      placement: header\n    resources:\n    - name: user\n      path: /v1/user\n      description: User account\
  \ management\n      operations:\n      - name: get-user\n        method: POST\n        description: Get user details and client ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: attacks\n      path: /v1/objects/attack\n      description: Attack data retrieval\n      operations:\n      - name: list-attacks\n        method: POST\n        description: List detected attacks with filtering\n        inputParameters:\n        - name: clientid\n          in: body\n          type: integer\n          required: true\n          description: Client ID\n        - name: limit\n          in: body\n          type: integer\n          required: false\n          description: Maximum results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: attacks-paginated\n      path: /v2/objects/attack\n      description: Paginated\
  \ attack data retrieval\n      operations:\n      - name: list-attacks-paginated\n        method: POST\n        description: List attacks with cursor-based pagination\n        inputParameters:\n        - name: clientid\n          in: body\n          type: integer\n          required: true\n          description: Client ID\n        - name: cursor\n          in: body\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vulnerabilities\n      path: /v1/objects/vuln\n      description: Vulnerability management\n      operations:\n      - name: list-vulnerabilities\n        method: POST\n        description: List detected vulnerabilities\n        inputParameters:\n        - name: clientid\n          in: body\n          type: integer\n          required: true\n          description: Client ID\n        - name: status\n\
  \          in: body\n          type: string\n          required: false\n          description: Filter by status (active, fixed, false_positive)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rules\n      path: /v1/objects/hint\n      description: Security rules management\n      operations:\n      - name: list-rules\n        method: POST\n        description: List all security rules\n        inputParameters:\n        - name: clientid\n          in: body\n          type: integer\n          required: true\n          description: Client ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: create-rule\n      path: /v1/objects/hint/create\n      description: Create security rule\n      operations:\n      - name: create-rule\n        method: POST\n        description: Create a new security rule or virtual patch\n\
  \        inputParameters:\n        - name: clientid\n          in: body\n          type: integer\n          required: true\n          description: Client ID\n        - name: type\n          in: body\n          type: string\n          required: true\n          description: Rule type (vpatch, regex, etc.)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            clientid: '{{tools.clientid}}'\n            type: '{{tools.type}}'\n    - name: delete-rule\n      path: /v1/objects/hint/delete\n      description: Delete security rule\n      operations:\n      - name: delete-rule\n        method: POST\n        description: Delete a security rule by ID\n        inputParameters:\n        - name: id\n          in: body\n          type: integer\n          required: true\n          description: Rule ID to delete\n        - name: clientid\n          in: body\n     \
  \     type: integer\n          required: true\n          description: Client ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            id: '{{tools.id}}'\n            clientid: '{{tools.clientid}}'\n    - name: ip-rules\n      path: /v4/ip_rules\n      description: IP list management\n      operations:\n      - name: list-ip-rules\n        method: GET\n        description: List IP rules from allowlist, denylist, or graylist\n        inputParameters:\n        - name: clientid\n          in: query\n          type: integer\n          required: true\n          description: Client ID\n        - name: list\n          in: query\n          type: string\n          required: false\n          description: Filter by list type (allowlist, denylist, graylist)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n       \
  \   description: Number of items to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-ip-rule\n        method: POST\n        description: Add an IP, subnet, country, or proxy to an IP list\n        inputParameters:\n        - name: clientid\n          in: body\n          type: integer\n          required: true\n          description: Client ID\n        - name: rule_type\n          in: body\n          type: string\n          required: true\n          description: Rule type (ip_range, country, proxy_type)\n        - name: pools\n          in: body\n          type: array\n          required: true\n          description: Target IP lists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n        body:\n          type: json\n          data:\n            clientid: '{{tools.clientid}}'\n            rule_type: '{{tools.rule_type}}'\n            pools: '{{tools.pools}}'\n      - name: delete-ip-rule\n        method: DELETE\n        description: Remove an IP rule from an IP list\n        inputParameters:\n        - name: id\n          in: body\n          type: integer\n          required: true\n          description: IP rule ID to delete\n        - name: clientid\n          in: body\n          type: integer\n          required: true\n          description: Client ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            id: '{{tools.id}}'\n            clientid: '{{tools.clientid}}'\n    - name: nodes\n      path: /v1/objects/node\n      description: Filter node management\n      operations:\n      - name: list-nodes\n       \
  \ method: POST\n        description: List all Wallarm filter nodes\n        inputParameters:\n        - name: clientid\n          in: body\n          type: integer\n          required: true\n          description: Client ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrations\n      path: /v1/objects/integration\n      description: Third-party integration management\n      operations:\n      - name: list-integrations\n        method: POST\n        description: List configured third-party integrations\n        inputParameters:\n        - name: clientid\n          in: body\n          type: integer\n          required: true\n          description: Client ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: triggers\n      path: /v1/objects/trigger\n      description: Automated trigger management\n    \
  \  operations:\n      - name: list-triggers\n        method: POST\n        description: List configured automated triggers\n        inputParameters:\n        - name: clientid\n          in: body\n          type: integer\n          required: true\n          description: Client ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /v1/objects/application\n      description: Application scope management\n      operations:\n      - name: list-applications\n        method: POST\n        description: List configured applications and scopes\n        inputParameters:\n        - name: clientid\n          in: body\n          type: integer\n          required: true\n          description: Client ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: wallarm-security-api\n\
  \    description: Unified REST API for Wallarm API security operations.\n    resources:\n    - path: /v1/attacks\n      name: attacks\n      description: Detected attack data\n      operations:\n      - method: GET\n        name: list-attacks\n        description: List security attacks detected by Wallarm\n        call: wallarm.list-attacks\n        with:\n          clientid: rest.clientid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vulnerabilities\n      name: vulnerabilities\n      description: Detected vulnerability data\n      operations:\n      - method: GET\n        name: list-vulnerabilities\n        description: List vulnerabilities detected across APIs\n        call: wallarm.list-vulnerabilities\n        with:\n          clientid: rest.clientid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rules\n      name: rules\n      description: Security rule management\n      operations:\n      -\
  \ method: GET\n        name: list-rules\n        description: List configured security rules and virtual patches\n        call: wallarm.list-rules\n        with:\n          clientid: rest.clientid\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-rule\n        description: Create a new security rule or virtual patch\n        call: wallarm.create-rule\n        with:\n          clientid: rest.clientid\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-rule\n        description: Delete a security rule by ID\n        call: wallarm.delete-rule\n        with:\n          id: rest.id\n          clientid: rest.clientid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ip-rules\n      name: ip-rules\n      description: IP list management (allowlist, denylist, graylist)\n      operations:\n    \
  \  - method: GET\n        name: list-ip-rules\n        description: List IP rules from all IP lists\n        call: wallarm.list-ip-rules\n        with:\n          clientid: rest.clientid\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-ip-rule\n        description: Add an IP or subnet to a blocklist or allowlist\n        call: wallarm.add-ip-rule\n        with:\n          clientid: rest.clientid\n          rule_type: rest.rule_type\n          pools: rest.pools\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-ip-rule\n        description: Remove an IP rule from a list\n        call: wallarm.delete-ip-rule\n        with:\n          id: rest.id\n          clientid: rest.clientid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nodes\n      name: nodes\n      description: Wallarm filter node inventory\n      operations:\n\
  \      - method: GET\n        name: list-nodes\n        description: List all deployed Wallarm filter nodes\n        call: wallarm.list-nodes\n        with:\n          clientid: rest.clientid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/integrations\n      name: integrations\n      description: Third-party security integrations\n      operations:\n      - method: GET\n        name: list-integrations\n        description: List configured SIEM and notification integrations\n        call: wallarm.list-integrations\n        with:\n          clientid: rest.clientid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/triggers\n      name: triggers\n      description: Automated alert triggers\n      operations:\n      - method: GET\n        name: list-triggers\n        description: List configured automated security triggers\n        call: wallarm.list-triggers\n        with:\n          clientid: rest.clientid\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: wallarm-security-mcp\n    transport: http\n    description: MCP server for AI-assisted API security monitoring and response.\n    tools:\n    - name: list-attacks\n      description: List security attacks detected by Wallarm across API infrastructure\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wallarm.list-attacks\n      with:\n        clientid: tools.clientid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vulnerabilities\n      description: List vulnerabilities detected across monitored APIs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wallarm.list-vulnerabilities\n      with:\n        clientid: tools.clientid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-rules\n      description: List all configured security rules and virtual\
  \ patches\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wallarm.list-rules\n      with:\n        clientid: tools.clientid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-security-rule\n      description: Create a virtual patch or custom security rule to block an attack vector\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: wallarm.create-rule\n      with:\n        clientid: tools.clientid\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ip-rules\n      description: List all entries in Wallarm IP allowlists, denylists, and graylists\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wallarm.list-ip-rules\n      with:\n        clientid: tools.clientid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: block-ip-address\n      description: Add an\
  \ IP address or subnet to the denylist\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: wallarm.add-ip-rule\n      with:\n        clientid: tools.clientid\n        rule_type: tools.rule_type\n        pools: tools.pools\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-ip-block\n      description: Remove an IP address or subnet from a blocklist\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: wallarm.delete-ip-rule\n      with:\n        id: tools.id\n        clientid: tools.clientid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-nodes\n      description: List all Wallarm filter nodes deployed in the environment\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wallarm.list-nodes\n      with:\n        clientid: tools.clientid\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-integrations\n      description: List configured SIEM and notification integrations\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wallarm.list-integrations\n      with:\n        clientid: tools.clientid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-triggers\n      description: List automated security alert triggers\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wallarm.list-triggers\n      with:\n        clientid: tools.clientid\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/wallarm/refs/heads/main/capabilities/api-security-operations.yaml
tags:
- API Security
- Attack Detection
- Vulnerability Management
- Incident Response
- WAF
tools:
- description: List security attacks detected by Wallarm across API infrastructure
  hints:
    openWorld: true
    readOnly: true
  name: list-attacks
- description: List vulnerabilities detected across monitored APIs
  hints:
    openWorld: true
    readOnly: true
  name: list-vulnerabilities
- description: List all configured security rules and virtual patches
  hints:
    openWorld: false
    readOnly: true
  name: list-rules
- description: Create a virtual patch or custom security rule to block an attack vector
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-security-rule
- description: List all entries in Wallarm IP allowlists, denylists, and graylists
  hints:
    openWorld: false
    readOnly: true
  name: list-ip-rules
- description: Add an IP address or subnet to the denylist
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: block-ip-address
- description: Remove an IP address or subnet from a blocklist
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-ip-block
- description: List all Wallarm filter nodes deployed in the environment
  hints:
    openWorld: false
    readOnly: true
  name: list-nodes
- description: List configured SIEM and notification integrations
  hints:
    openWorld: false
    readOnly: true
  name: list-integrations
- description: List automated security alert triggers
  hints:
    openWorld: false
    readOnly: true
  name: list-triggers
---
