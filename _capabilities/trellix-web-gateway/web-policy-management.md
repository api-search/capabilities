---
categories: []
consumed_apis: []
description: Unified capability for network security admins to configure and manage web security policies on Trellix Web Gateway. Combines policy rule sets, URL filtering, anti-malware settings, SSL inspection, DLP configuration, and appliance management for network security engineers and IT administrators.
layout: capability
name: Trellix Web Gateway Policy Management
operations:
- description: List all rule sets
  method: GET
  name: list-rule-sets
  path: /v1/rule-sets
- description: Create a new rule set
  method: POST
  name: create-rule-set
  path: /v1/rule-sets
- description: Get URL filter settings
  method: GET
  name: get-url-filter-settings
  path: /v1/url-filter/settings
- description: Look up URL categorization
  method: GET
  name: lookup-url
  path: /v1/url-filter/lookup
- description: Get anti-malware settings
  method: GET
  name: get-anti-malware-settings
  path: /v1/anti-malware/settings
- description: Get SSL scanning settings
  method: GET
  name: get-ssl-settings
  path: /v1/ssl/settings
- description: Get DLP settings
  method: GET
  name: get-dlp-settings
  path: /v1/dlp/settings
- description: List custom lists
  method: GET
  name: list-custom-lists
  path: /v1/lists
- description: Get current configuration
  method: GET
  name: get-configuration
  path: /v1/configuration
personas: []
provider_name: Trellix Web Gateway
provider_slug: trellix-web-gateway
search_terms:
- configuration management
- url filtering
- appliance configuration management
- get ssl settings
- get current configuration
- malware protection
- custom url, ip, and string lists
- look up url categorization
- lookup url
- policy management
- rollback configuration
- policy rule sets
- create rule set
- dlp
- rollback uncommitted configuration changes to the last committed state.
- list all rule sets
- url categorization lookup
- network security
- get dlp settings
- get ssl/tls inspection configuration to verify encrypted traffic scanning.
- get anti malware settings
- list custom lists
- threat protection
- list all policy rule sets on the web gateway for review and audit.
- list custom url, ip, and string lists used in security policies.
- url filtering configuration
- get the current appliance configuration for backup or review.
- data loss prevention
- create a new policy rule set on the web gateway.
- look up how a specific url is categorized by the web gateway to troubleshoot filtering decisions.
- dlp policy settings
- commit configuration
- commit pending configuration changes to activate them on the web gateway.
- get url filter settings
- get anti-malware settings
- get ssl scanning settings
- get data loss prevention settings to verify data exfiltration protection.
- get url filtering configuration including blocked and allowed categories.
- list rule sets
- ssl/tls inspection settings
- cybersecurity
- create a new rule set
- ssl inspection
- web gateway
- get configuration
- enterprise security
- anti-malware settings
- get anti-malware scanning configuration to verify threat protection settings.
slug: web-policy-management
source_filename: web-policy-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Trellix Web Gateway Policy Management\n  description: Unified capability for network security admins to configure and manage web security policies on Trellix Web\n    Gateway. Combines policy rule sets, URL filtering, anti-malware settings, SSL inspection, DLP configuration, and appliance\n    management for network security engineers and IT administrators.\n  tags:\n  - Configuration Management\n  - DLP\n  - Enterprise Security\n  - Network Security\n  - Policy Management\n  - URL Filtering\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TWG_SESSION_COOKIE: TWG_SESSION_COOKIE\ncapability:\n  consumes:\n  - type: http\n    namespace: twg-rest\n    baseUri: https://mwg.example.com:4712/Konfigurator/REST\n    description: Trellix Web Gateway appliance management REST API\n    authentication:\n      type: apikey\n      key: Cookie\n      value: JSESSIONID={{TWG_SESSION_COOKIE}}\n      placement:\
  \ header\n    resources:\n    - name: system\n      path: /system\n      description: System information and appliance status\n      operations:\n      - name: get-system-info\n        method: GET\n        description: Get system information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: appliances\n      path: /system/appliances\n      description: Managed appliances in the cluster\n      operations:\n      - name: list-appliances\n        method: GET\n        description: List managed appliances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: appliance-detail\n      path: /system/appliances/{applianceId}\n      description: Single appliance details\n      operations:\n      - name: get-appliance\n        method: GET\n        description: Get appliance details\n        inputParameters:\n        - name:\
  \ applianceId\n          in: path\n          type: string\n          required: true\n          description: Appliance identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration\n      path: /configuration\n      description: Appliance configuration\n      operations:\n      - name: get-configuration\n        method: GET\n        description: Get current configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration-commit\n      path: /configuration/commit\n      description: Commit configuration changes\n      operations:\n      - name: commit-configuration\n        method: POST\n        description: Commit configuration changes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration-rollback\n\
  \      path: /configuration/rollback\n      description: Rollback configuration changes\n      operations:\n      - name: rollback-configuration\n        method: POST\n        description: Rollback configuration changes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lists\n      path: /lists\n      description: Custom URL and IP lists\n      operations:\n      - name: list-custom-lists\n        method: GET\n        description: List custom lists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-detail\n      path: /lists/{listId}\n      description: Single custom list\n      operations:\n      - name: get-custom-list\n        method: GET\n        description: Get a custom list\n        inputParameters:\n        - name: listId\n          in: path\n          type: string\n          required: true\n    \
  \      description: List identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-custom-list\n        method: PUT\n        description: Update a custom list\n        inputParameters:\n        - name: listId\n          in: path\n          type: string\n          required: true\n          description: List identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            entries: '{{tools.entries}}'\n    - name: logs\n      path: /troubleshooting/logs\n      description: System and audit logs\n      operations:\n      - name: get-logs\n        method: GET\n        description: Retrieve system logs\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Log type (system,\
  \ audit, access, debug)\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start timestamp\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End timestamp\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max log entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: twg-policy\n    baseUri: https://mwg.example.com:4712/Konfigurator/REST/policy\n    description: Trellix Web Gateway Policy management API\n    authentication:\n      type: apikey\n      key: Cookie\n      value: JSESSIONID={{TWG_SESSION_COOKIE}}\n      placement: header\n    resources:\n    - name: rule-sets\n      path: /rulesets\n      description: Web Gateway policy rule sets\n      operations:\n      - name:\
  \ list-rule-sets\n        method: GET\n        description: List all rule sets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-rule-set\n        method: POST\n        description: Create a new rule set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n    - name: rule-set-detail\n      path: /rulesets/{ruleSetId}\n      description: Single rule set\n      operations:\n      - name: get-rule-set\n        method: GET\n        description: Get a rule set\n        inputParameters:\n        - name: ruleSetId\n          in: path\n          type: string\n          required: true\n          description: Rule set identifier\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: update-rule-set\n        method: PUT\n        description: Update a rule set\n        inputParameters:\n        - name: ruleSetId\n          in: path\n          type: string\n          required: true\n          description: Rule set identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-rule-set\n        method: DELETE\n        description: Delete a rule set\n        inputParameters:\n        - name: ruleSetId\n          in: path\n          type: string\n          required: true\n          description: Rule set identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: url-filtering\n      path: /urlfilter/settings\n    \
  \  description: URL filtering configuration\n      operations:\n      - name: get-url-filter-settings\n        method: GET\n        description: Get URL filter settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-url-filter-settings\n        method: PUT\n        description: Update URL filter settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            blockCategories: '{{tools.blockCategories}}'\n    - name: url-lookup\n      path: /urlfilter/lookup\n      description: URL categorization lookup\n      operations:\n      - name: lookup-url\n        method: GET\n        description: Look up URL categorization\n        inputParameters:\n        - name: url\n          in: query\n          type: string\n          required: true\n          description:\
  \ URL to categorize\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: anti-malware\n      path: /antimalware/settings\n      description: Anti-malware settings\n      operations:\n      - name: get-anti-malware-settings\n        method: GET\n        description: Get anti-malware settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-anti-malware-settings\n        method: PUT\n        description: Update anti-malware settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            enableGatewayAntiMalware: '{{tools.enableGatewayAntiMalware}}'\n    - name: ssl-settings\n      path: /ssl/settings\n      description: SSL/TLS inspection settings\n      operations:\n\
  \      - name: get-ssl-settings\n        method: GET\n        description: Get SSL scanning settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-ssl-settings\n        method: PUT\n        description: Update SSL scanning settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            enableSslScanning: '{{tools.enableSslScanning}}'\n    - name: dlp-settings\n      path: /dlp/settings\n      description: Data Loss Prevention settings\n      operations:\n      - name: get-dlp-settings\n        method: GET\n        description: Get DLP settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-dlp-settings\n        method: PUT\n        description: Update\
  \ DLP settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            enableDlp: '{{tools.enableDlp}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: twg-policy-mgmt-api\n    description: Unified REST API for Web Gateway policy configuration and management.\n    resources:\n    - path: /v1/rule-sets\n      name: rule-sets\n      description: Policy rule sets\n      operations:\n      - method: GET\n        name: list-rule-sets\n        description: List all rule sets\n        call: twg-policy.list-rule-sets\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-rule-set\n        description: Create a new rule set\n        call: twg-policy.create-rule-set\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/url-filter/settings\n      name:\
  \ url-filter-settings\n      description: URL filtering configuration\n      operations:\n      - method: GET\n        name: get-url-filter-settings\n        description: Get URL filter settings\n        call: twg-policy.get-url-filter-settings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/url-filter/lookup\n      name: url-lookup\n      description: URL categorization lookup\n      operations:\n      - method: GET\n        name: lookup-url\n        description: Look up URL categorization\n        call: twg-policy.lookup-url\n        with:\n          url: rest.url\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/anti-malware/settings\n      name: anti-malware-settings\n      description: Anti-malware settings\n      operations:\n      - method: GET\n        name: get-anti-malware-settings\n        description: Get anti-malware settings\n        call: twg-policy.get-anti-malware-settings\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/ssl/settings\n      name: ssl-settings\n      description: SSL/TLS inspection settings\n      operations:\n      - method: GET\n        name: get-ssl-settings\n        description: Get SSL scanning settings\n        call: twg-policy.get-ssl-settings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dlp/settings\n      name: dlp-settings\n      description: DLP policy settings\n      operations:\n      - method: GET\n        name: get-dlp-settings\n        description: Get DLP settings\n        call: twg-policy.get-dlp-settings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lists\n      name: custom-lists\n      description: Custom URL, IP, and string lists\n      operations:\n      - method: GET\n        name: list-custom-lists\n        description: List custom lists\n        call: twg-rest.list-custom-lists\n        outputParameters:\n  \
  \      - type: object\n          mapping: $.\n    - path: /v1/configuration\n      name: configuration\n      description: Appliance configuration management\n      operations:\n      - method: GET\n        name: get-configuration\n        description: Get current configuration\n        call: twg-rest.get-configuration\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: twg-policy-mgmt-mcp\n    transport: http\n    description: MCP server for AI-assisted Web Gateway policy configuration and optimization.\n    tools:\n    - name: list-rule-sets\n      description: List all policy rule sets on the Web Gateway for review and audit.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twg-policy.list-rule-sets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-rule-set\n      description: Create a new policy rule set on the Web Gateway.\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: twg-policy.create-rule-set\n      with:\n        name: tools.name\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-url-filter-settings\n      description: Get URL filtering configuration including blocked and allowed categories.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: twg-policy.get-url-filter-settings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-url\n      description: Look up how a specific URL is categorized by the Web Gateway to troubleshoot filtering decisions.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: twg-policy.lookup-url\n      with:\n        url: tools.url\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-anti-malware-settings\n      description: Get anti-malware scanning configuration\
  \ to verify threat protection settings.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: twg-policy.get-anti-malware-settings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ssl-settings\n      description: Get SSL/TLS inspection configuration to verify encrypted traffic scanning.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: twg-policy.get-ssl-settings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dlp-settings\n      description: Get Data Loss Prevention settings to verify data exfiltration protection.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: twg-policy.get-dlp-settings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-custom-lists\n      description: List custom URL, IP, and string lists used in security policies.\n      hints:\n        readOnly: true\n        openWorld: true\n  \
  \    call: twg-rest.list-custom-lists\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-configuration\n      description: Get the current appliance configuration for backup or review.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: twg-rest.get-configuration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: commit-configuration\n      description: Commit pending configuration changes to activate them on the Web Gateway.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: twg-rest.commit-configuration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: rollback-configuration\n      description: Rollback uncommitted configuration changes to the last committed state.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: twg-rest.rollback-configuration\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trellix-web-gateway/refs/heads/main/capabilities/web-policy-management.yaml
tags:
- Configuration Management
- DLP
- Enterprise Security
- Network Security
- Policy Management
- URL Filtering
tools:
- description: List all policy rule sets on the Web Gateway for review and audit.
  hints:
    openWorld: true
    readOnly: true
  name: list-rule-sets
- description: Create a new policy rule set on the Web Gateway.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-rule-set
- description: Get URL filtering configuration including blocked and allowed categories.
  hints:
    openWorld: false
    readOnly: true
  name: get-url-filter-settings
- description: Look up how a specific URL is categorized by the Web Gateway to troubleshoot filtering decisions.
  hints:
    openWorld: false
    readOnly: true
  name: lookup-url
- description: Get anti-malware scanning configuration to verify threat protection settings.
  hints:
    openWorld: false
    readOnly: true
  name: get-anti-malware-settings
- description: Get SSL/TLS inspection configuration to verify encrypted traffic scanning.
  hints:
    openWorld: false
    readOnly: true
  name: get-ssl-settings
- description: Get Data Loss Prevention settings to verify data exfiltration protection.
  hints:
    openWorld: false
    readOnly: true
  name: get-dlp-settings
- description: List custom URL, IP, and string lists used in security policies.
  hints:
    openWorld: true
    readOnly: true
  name: list-custom-lists
- description: Get the current appliance configuration for backup or review.
  hints:
    openWorld: false
    readOnly: true
  name: get-configuration
- description: Commit pending configuration changes to activate them on the Web Gateway.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: commit-configuration
- description: Rollback uncommitted configuration changes to the last committed state.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: rollback-configuration
---
