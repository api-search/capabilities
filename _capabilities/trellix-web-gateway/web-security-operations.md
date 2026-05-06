---
categories: []
consumed_apis: []
description: Unified capability for security operations teams to monitor, investigate, and respond to web security threats using Trellix Web Gateway. Combines traffic log analysis, security event investigation, threat statistics, and appliance health monitoring for SOC analysts and network security engineers.
layout: capability
name: Trellix Web Gateway Security Operations
operations:
- description: Retrieve security events for investigation
  method: GET
  name: get-security-events
  path: /v1/security-events
- description: Retrieve traffic logs
  method: GET
  name: get-traffic-logs
  path: /v1/traffic-logs
- description: Get threat statistics
  method: GET
  name: get-threat-statistics
  path: /v1/statistics/threats
- description: Get traffic statistics
  method: GET
  name: get-traffic-statistics
  path: /v1/statistics/traffic
- description: Get top URLs
  method: GET
  name: get-top-urls
  path: /v1/top-urls
- description: List appliances and health status
  method: GET
  name: list-appliances
  path: /v1/appliances
- description: Get system logs
  method: GET
  name: get-logs
  path: /v1/logs
personas: []
provider_name: Trellix Web Gateway
provider_slug: trellix-web-gateway
search_terms:
- get top categories
- top accessed urls
- list appliances and health status
- get traffic logs
- url filtering
- get traffic statistics
- retrieve security events from web gateway including malware detections and policy violations. use for incident investigation and threat hunting.
- retrieve web gateway system and audit logs for compliance and change tracking.
- malware protection
- traffic statistics for capacity and monitoring
- list appliances
- list web gateway appliances and check their operational health status.
- get threat statistics to understand attack patterns, malware trends, and security posture over time.
- get top accessed urls to identify potential policy violations or unusual browsing patterns.
- web security
- get logs
- get threat statistics
- get top urls
- network security
- threat protection
- retrieve web traffic logs for forensic analysis, compliance auditing, and user behavior investigation.
- get system logs
- data loss prevention
- security events and threat detections
- security operations
- web gateway appliance health
- threat detection
- web traffic logs for forensic analysis
- get top url categories to understand web browsing patterns and policy effectiveness.
- system and audit logs
- retrieve traffic logs
- cybersecurity
- ssl inspection
- threat statistics for security reporting
- web gateway
- get web traffic statistics for capacity planning and anomaly detection.
- get security events
- enterprise security
- retrieve security events for investigation
slug: web-security-operations
source_filename: web-security-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Trellix Web Gateway Security Operations\n  description: Unified capability for security operations teams to monitor, investigate, and respond to web security threats\n    using Trellix Web Gateway. Combines traffic log analysis, security event investigation, threat statistics, and appliance\n    health monitoring for SOC analysts and network security engineers.\n  tags:\n  - Enterprise Security\n  - Network Security\n  - Security Operations\n  - Threat Detection\n  - Web Security\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TWG_SESSION_COOKIE: TWG_SESSION_COOKIE\ncapability:\n  consumes:\n  - type: http\n    namespace: twg-rest\n    baseUri: https://mwg.example.com:4712/Konfigurator/REST\n    description: Trellix Web Gateway appliance management REST API\n    authentication:\n      type: apikey\n      key: Cookie\n      value: JSESSIONID={{TWG_SESSION_COOKIE}}\n      placement: header\n   \
  \ resources:\n    - name: system\n      path: /system\n      description: System information and appliance status\n      operations:\n      - name: get-system-info\n        method: GET\n        description: Get system information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: appliances\n      path: /system/appliances\n      description: Managed appliances in the cluster\n      operations:\n      - name: list-appliances\n        method: GET\n        description: List managed appliances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: appliance-detail\n      path: /system/appliances/{applianceId}\n      description: Single appliance details\n      operations:\n      - name: get-appliance\n        method: GET\n        description: Get appliance details\n        inputParameters:\n        - name: applianceId\n\
  \          in: path\n          type: string\n          required: true\n          description: Appliance identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration\n      path: /configuration\n      description: Appliance configuration\n      operations:\n      - name: get-configuration\n        method: GET\n        description: Get current configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration-commit\n      path: /configuration/commit\n      description: Commit configuration changes\n      operations:\n      - name: commit-configuration\n        method: POST\n        description: Commit configuration changes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration-rollback\n\
  \      path: /configuration/rollback\n      description: Rollback configuration changes\n      operations:\n      - name: rollback-configuration\n        method: POST\n        description: Rollback configuration changes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lists\n      path: /lists\n      description: Custom URL and IP lists\n      operations:\n      - name: list-custom-lists\n        method: GET\n        description: List custom lists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-detail\n      path: /lists/{listId}\n      description: Single custom list\n      operations:\n      - name: get-custom-list\n        method: GET\n        description: Get a custom list\n        inputParameters:\n        - name: listId\n          in: path\n          type: string\n          required: true\n    \
  \      description: List identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-custom-list\n        method: PUT\n        description: Update a custom list\n        inputParameters:\n        - name: listId\n          in: path\n          type: string\n          required: true\n          description: List identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            entries: '{{tools.entries}}'\n    - name: logs\n      path: /troubleshooting/logs\n      description: System and audit logs\n      operations:\n      - name: get-logs\n        method: GET\n        description: Retrieve system logs\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Log type (system,\
  \ audit, access, debug)\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start timestamp\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End timestamp\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max log entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: twg-reporting\n    baseUri: https://mwg.example.com:4712/reporter/api\n    description: Trellix Web Gateway reporting and analytics API\n    authentication:\n      type: apikey\n      key: Cookie\n      value: JSESSIONID={{TWG_SESSION_COOKIE}}\n      placement: header\n    resources:\n    - name: traffic-logs\n      path: /v1/traffic/logs\n      description: Web traffic logs\n      operations:\n      - name: get-traffic-logs\n\
  \        method: GET\n        description: Retrieve web traffic logs\n        inputParameters:\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start timestamp\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End timestamp\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: security-events\n      path: /v1/events/security\n      description: Security events\n      operations:\n      - name: get-security-events\n        method: GET\n        description: Retrieve security events\n        inputParameters:\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start timestamp\n\
  \        - name: to\n          in: query\n          type: string\n          required: false\n          description: End timestamp\n        - name: severity\n          in: query\n          type: string\n          required: false\n          description: Event severity filter\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /v1/reports\n      description: Generated reports\n      operations:\n      - name: list-reports\n        method: GET\n        description: List available reports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: generate-report\n        method: POST\n        description: Generate a new report\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            from: '{{tools.from}}'\n            to: '{{tools.to}}'\n    - name: traffic-statistics\n      path: /v1/statistics/traffic\n      description: Traffic statistics\n      operations:\n      - name: get-traffic-statistics\n        method: GET\n        description: Get traffic statistics\n        inputParameters:\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Statistics period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: threat-statistics\n      path: /v1/statistics/threats\n      description: Threat statistics\n      operations:\n      - name: get-threat-statistics\n        method: GET\n        description: Get threat statistics\n        inputParameters:\n\
  \        - name: period\n          in: query\n          type: string\n          required: false\n          description: Statistics period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: top-urls\n      path: /v1/top/urls\n      description: Top accessed URLs\n      operations:\n      - name: get-top-urls\n        method: GET\n        description: Get top accessed URLs\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of top URLs\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: top-categories\n      path: /v1/top/categories\n      description: Top URL categories\n      operations:\n\
  \      - name: get-top-categories\n        method: GET\n        description: Get top URL categories\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of categories\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: twg-security-ops-api\n    description: Unified REST API for Web Gateway security operations and monitoring.\n    resources:\n    - path: /v1/security-events\n      name: security-events\n      description: Security events and threat detections\n      operations:\n      - method: GET\n        name: get-security-events\n        description: Retrieve security events for investigation\n        call: twg-reporting.get-security-events\n\
  \        with:\n          from: rest.from\n          to: rest.to\n          severity: rest.severity\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/traffic-logs\n      name: traffic-logs\n      description: Web traffic logs for forensic analysis\n      operations:\n      - method: GET\n        name: get-traffic-logs\n        description: Retrieve traffic logs\n        call: twg-reporting.get-traffic-logs\n        with:\n          from: rest.from\n          to: rest.to\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/statistics/threats\n      name: threat-statistics\n      description: Threat statistics for security reporting\n      operations:\n      - method: GET\n        name: get-threat-statistics\n        description: Get threat statistics\n        call: twg-reporting.get-threat-statistics\n        with:\n          period: rest.period\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/statistics/traffic\n      name: traffic-statistics\n      description: Traffic statistics for capacity and monitoring\n      operations:\n      - method: GET\n        name: get-traffic-statistics\n        description: Get traffic statistics\n        call: twg-reporting.get-traffic-statistics\n        with:\n          period: rest.period\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/top-urls\n      name: top-urls\n      description: Top accessed URLs\n      operations:\n      - method: GET\n        name: get-top-urls\n        description: Get top URLs\n        call: twg-reporting.get-top-urls\n        with:\n          limit: rest.limit\n          period: rest.period\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/appliances\n      name: appliances\n      description: Web Gateway appliance health\n      operations:\n\
  \      - method: GET\n        name: list-appliances\n        description: List appliances and health status\n        call: twg-rest.list-appliances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/logs\n      name: system-logs\n      description: System and audit logs\n      operations:\n      - method: GET\n        name: get-logs\n        description: Get system logs\n        call: twg-rest.get-logs\n        with:\n          type: rest.type\n          from: rest.from\n          to: rest.to\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: twg-security-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted Web Gateway security operations and threat investigation.\n    tools:\n    - name: get-security-events\n      description: Retrieve security events from Web Gateway including malware detections and policy violations. Use for\
  \ incident\n        investigation and threat hunting.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twg-reporting.get-security-events\n      with:\n        from: tools.from\n        to: tools.to\n        severity: tools.severity\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-traffic-logs\n      description: Retrieve web traffic logs for forensic analysis, compliance auditing, and user behavior investigation.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twg-reporting.get-traffic-logs\n      with:\n        from: tools.from\n        to: tools.to\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-threat-statistics\n      description: Get threat statistics to understand attack patterns, malware trends, and security posture over time.\n      hints:\n        readOnly: true\n        openWorld: true\n      call:\
  \ twg-reporting.get-threat-statistics\n      with:\n        period: tools.period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-traffic-statistics\n      description: Get web traffic statistics for capacity planning and anomaly detection.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twg-reporting.get-traffic-statistics\n      with:\n        period: tools.period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-top-urls\n      description: Get top accessed URLs to identify potential policy violations or unusual browsing patterns.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twg-reporting.get-top-urls\n      with:\n        limit: tools.limit\n        period: tools.period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-top-categories\n      description: Get top URL categories to understand web browsing patterns and policy\
  \ effectiveness.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twg-reporting.get-top-categories\n      with:\n        limit: tools.limit\n        period: tools.period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-system-logs\n      description: Retrieve Web Gateway system and audit logs for compliance and change tracking.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twg-rest.get-logs\n      with:\n        type: tools.type\n        from: tools.from\n        to: tools.to\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-appliances\n      description: List Web Gateway appliances and check their operational health status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twg-rest.list-appliances\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trellix-web-gateway/refs/heads/main/capabilities/web-security-operations.yaml
tags:
- Enterprise Security
- Network Security
- Security Operations
- Threat Detection
- Web Security
tools:
- description: Retrieve security events from Web Gateway including malware detections and policy violations. Use for incident investigation and threat hunting.
  hints:
    openWorld: true
    readOnly: true
  name: get-security-events
- description: Retrieve web traffic logs for forensic analysis, compliance auditing, and user behavior investigation.
  hints:
    openWorld: true
    readOnly: true
  name: get-traffic-logs
- description: Get threat statistics to understand attack patterns, malware trends, and security posture over time.
  hints:
    openWorld: true
    readOnly: true
  name: get-threat-statistics
- description: Get web traffic statistics for capacity planning and anomaly detection.
  hints:
    openWorld: true
    readOnly: true
  name: get-traffic-statistics
- description: Get top accessed URLs to identify potential policy violations or unusual browsing patterns.
  hints:
    openWorld: true
    readOnly: true
  name: get-top-urls
- description: Get top URL categories to understand web browsing patterns and policy effectiveness.
  hints:
    openWorld: true
    readOnly: true
  name: get-top-categories
- description: Retrieve Web Gateway system and audit logs for compliance and change tracking.
  hints:
    openWorld: true
    readOnly: true
  name: get-system-logs
- description: List Web Gateway appliances and check their operational health status.
  hints:
    openWorld: true
    readOnly: true
  name: list-appliances
---
