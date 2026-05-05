---
categories: []
consumed_apis:
- wallarm
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
- incident response
- list rules
- list all configured security rules and virtual patches
- create rule
- list ip rules from all ip lists
- delete a security rule by id
- add ip rule
- detected vulnerability data
- security testing
- list attacks
- delete rule
- automated alert triggers
- security rule management
- detected attack data
- list configured security rules and virtual patches
- list security attacks detected by wallarm across api infrastructure
- create a virtual patch or custom security rule to block an attack vector
- block ip address
- cybersecurity
- attack detection
- add an ip or subnet to a blocklist or allowlist
- add an ip address or subnet to the denylist
- remove an ip rule from a list
- waf
- create a new security rule or virtual patch
- list configured automated security triggers
- list vulnerabilities detected across monitored apis
- create security rule
- list all wallarm filter nodes deployed in the environment
- list ip rules
- list configured siem and notification integrations
- list vulnerabilities detected across apis
- delete ip rule
- ip list management (allowlist, denylist, graylist)
- remove ip block
- list vulnerabilities
- list integrations
- vulnerability management
- list all entries in wallarm ip allowlists, denylists, and graylists
- list security attacks detected by wallarm
- list nodes
- api security
- list all deployed wallarm filter nodes
- list triggers
- wallarm filter node inventory
- remove an ip address or subnet from a blocklist
- third-party security integrations
- list automated security alert triggers
slug: api-security-operations
source_filename: api-security-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Wallarm API Security Operations\"\n  description: >-\n    Unified workflow for API security operations using the Wallarm platform.\n    Enables security teams to monitor attacks, investigate vulnerabilities,\n    manage IP blocklists, configure security rules, and coordinate incident\n    response workflows across API infrastructure.\n  tags:\n    - API Security\n    - Attack Detection\n    - Vulnerability Management\n    - Incident Response\n    - WAF\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WALLARM_API_TOKEN: WALLARM_API_TOKEN\n\ncapability:\n  consumes:\n    - import: wallarm\n      location: ./shared/wallarm-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: wallarm-security-api\n      description: \"Unified REST API for Wallarm API security operations.\"\n      resources:\n        - path: /v1/attacks\n          name: attacks\n         \
  \ description: Detected attack data\n          operations:\n            - method: GET\n              name: list-attacks\n              description: List security attacks detected by Wallarm\n              call: \"wallarm.list-attacks\"\n              with:\n                clientid: \"rest.clientid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/vulnerabilities\n          name: vulnerabilities\n          description: Detected vulnerability data\n          operations:\n            - method: GET\n              name: list-vulnerabilities\n              description: List vulnerabilities detected across APIs\n              call: \"wallarm.list-vulnerabilities\"\n              with:\n                clientid: \"rest.clientid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/rules\n          name: rules\n          description: Security rule management\n\
  \          operations:\n            - method: GET\n              name: list-rules\n              description: List configured security rules and virtual patches\n              call: \"wallarm.list-rules\"\n              with:\n                clientid: \"rest.clientid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-rule\n              description: Create a new security rule or virtual patch\n              call: \"wallarm.create-rule\"\n              with:\n                clientid: \"rest.clientid\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-rule\n              description: Delete a security rule by ID\n              call: \"wallarm.delete-rule\"\n              with:\n                id: \"rest.id\"\n                clientid: \"\
  rest.clientid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ip-rules\n          name: ip-rules\n          description: IP list management (allowlist, denylist, graylist)\n          operations:\n            - method: GET\n              name: list-ip-rules\n              description: List IP rules from all IP lists\n              call: \"wallarm.list-ip-rules\"\n              with:\n                clientid: \"rest.clientid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-ip-rule\n              description: Add an IP or subnet to a blocklist or allowlist\n              call: \"wallarm.add-ip-rule\"\n              with:\n                clientid: \"rest.clientid\"\n                rule_type: \"rest.rule_type\"\n                pools: \"rest.pools\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-ip-rule\n              description: Remove an IP rule from a list\n              call: \"wallarm.delete-ip-rule\"\n              with:\n                id: \"rest.id\"\n                clientid: \"rest.clientid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/nodes\n          name: nodes\n          description: Wallarm filter node inventory\n          operations:\n            - method: GET\n              name: list-nodes\n              description: List all deployed Wallarm filter nodes\n              call: \"wallarm.list-nodes\"\n              with:\n                clientid: \"rest.clientid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/integrations\n          name: integrations\n          description: Third-party security integrations\n   \
  \       operations:\n            - method: GET\n              name: list-integrations\n              description: List configured SIEM and notification integrations\n              call: \"wallarm.list-integrations\"\n              with:\n                clientid: \"rest.clientid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/triggers\n          name: triggers\n          description: Automated alert triggers\n          operations:\n            - method: GET\n              name: list-triggers\n              description: List configured automated security triggers\n              call: \"wallarm.list-triggers\"\n              with:\n                clientid: \"rest.clientid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: wallarm-security-mcp\n      transport: http\n      description: \"MCP server for AI-assisted\
  \ API security monitoring and response.\"\n      tools:\n        - name: list-attacks\n          description: List security attacks detected by Wallarm across API infrastructure\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wallarm.list-attacks\"\n          with:\n            clientid: \"tools.clientid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-vulnerabilities\n          description: List vulnerabilities detected across monitored APIs\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wallarm.list-vulnerabilities\"\n          with:\n            clientid: \"tools.clientid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-rules\n          description: List all configured security rules and virtual patches\n          hints:\n            readOnly: true\n            openWorld:\
  \ false\n          call: \"wallarm.list-rules\"\n          with:\n            clientid: \"tools.clientid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-security-rule\n          description: Create a virtual patch or custom security rule to block an attack vector\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"wallarm.create-rule\"\n          with:\n            clientid: \"tools.clientid\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-ip-rules\n          description: List all entries in Wallarm IP allowlists, denylists, and graylists\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wallarm.list-ip-rules\"\n          with:\n            clientid: \"tools.clientid\"\n          outputParameters:\n      \
  \      - type: object\n              mapping: \"$.\"\n        - name: block-ip-address\n          description: Add an IP address or subnet to the denylist\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"wallarm.add-ip-rule\"\n          with:\n            clientid: \"tools.clientid\"\n            rule_type: \"tools.rule_type\"\n            pools: \"tools.pools\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: remove-ip-block\n          description: Remove an IP address or subnet from a blocklist\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"wallarm.delete-ip-rule\"\n          with:\n            id: \"tools.id\"\n            clientid: \"tools.clientid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-nodes\n   \
  \       description: List all Wallarm filter nodes deployed in the environment\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wallarm.list-nodes\"\n          with:\n            clientid: \"tools.clientid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-integrations\n          description: List configured SIEM and notification integrations\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wallarm.list-integrations\"\n          with:\n            clientid: \"tools.clientid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-triggers\n          description: List automated security alert triggers\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wallarm.list-triggers\"\n          with:\n            clientid: \"tools.clientid\"\n    \
  \      outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
