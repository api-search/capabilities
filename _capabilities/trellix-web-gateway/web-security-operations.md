---
categories: []
consumed_apis:
- twg-rest
- twg-reporting
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
- threat statistics for security reporting
- web security
- retrieve web traffic logs for forensic analysis, compliance auditing, and user behavior investigation.
- get security events
- system and audit logs
- get threat statistics
- malware protection
- list appliances and health status
- get system logs
- get web traffic statistics for capacity planning and anomaly detection.
- top accessed urls
- get top accessed urls to identify potential policy violations or unusual browsing patterns.
- cybersecurity
- enterprise security
- retrieve security events for investigation
- retrieve web gateway system and audit logs for compliance and change tracking.
- get threat statistics to understand attack patterns, malware trends, and security posture over time.
- threat detection
- web gateway
- get top categories
- retrieve traffic logs
- retrieve security events from web gateway including malware detections and policy violations. use for incident investigation and threat hunting.
- threat protection
- security events and threat detections
- get traffic statistics
- get top urls
- web gateway appliance health
- get top url categories to understand web browsing patterns and policy effectiveness.
- security operations
- ssl inspection
- network security
- list appliances
- web traffic logs for forensic analysis
- url filtering
- get traffic logs
- traffic statistics for capacity and monitoring
- list web gateway appliances and check their operational health status.
- get logs
- data loss prevention
slug: web-security-operations
source_filename: web-security-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Trellix Web Gateway Security Operations\"\n  description: >-\n    Unified capability for security operations teams to monitor, investigate,\n    and respond to web security threats using Trellix Web Gateway. Combines\n    traffic log analysis, security event investigation, threat statistics,\n    and appliance health monitoring for SOC analysts and network security engineers.\n  tags:\n    - Enterprise Security\n    - Network Security\n    - Security Operations\n    - Threat Detection\n    - Web Security\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TWG_SESSION_COOKIE: TWG_SESSION_COOKIE\n\ncapability:\n  consumes:\n    - import: twg-rest\n      location: ./shared/web-gateway-rest-api.yaml\n    - import: twg-reporting\n      location: ./shared/web-gateway-reporting-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: twg-security-ops-api\n      description:\
  \ \"Unified REST API for Web Gateway security operations and monitoring.\"\n      resources:\n        - path: /v1/security-events\n          name: security-events\n          description: \"Security events and threat detections\"\n          operations:\n            - method: GET\n              name: get-security-events\n              description: \"Retrieve security events for investigation\"\n              call: \"twg-reporting.get-security-events\"\n              with:\n                from: \"rest.from\"\n                to: \"rest.to\"\n                severity: \"rest.severity\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/traffic-logs\n          name: traffic-logs\n          description: \"Web traffic logs for forensic analysis\"\n          operations:\n            - method: GET\n              name: get-traffic-logs\n              description: \"Retrieve traffic logs\"\
  \n              call: \"twg-reporting.get-traffic-logs\"\n              with:\n                from: \"rest.from\"\n                to: \"rest.to\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/statistics/threats\n          name: threat-statistics\n          description: \"Threat statistics for security reporting\"\n          operations:\n            - method: GET\n              name: get-threat-statistics\n              description: \"Get threat statistics\"\n              call: \"twg-reporting.get-threat-statistics\"\n              with:\n                period: \"rest.period\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/statistics/traffic\n          name: traffic-statistics\n          description: \"Traffic statistics for capacity and monitoring\"\n          operations:\n            - method: GET\n\
  \              name: get-traffic-statistics\n              description: \"Get traffic statistics\"\n              call: \"twg-reporting.get-traffic-statistics\"\n              with:\n                period: \"rest.period\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/top-urls\n          name: top-urls\n          description: \"Top accessed URLs\"\n          operations:\n            - method: GET\n              name: get-top-urls\n              description: \"Get top URLs\"\n              call: \"twg-reporting.get-top-urls\"\n              with:\n                limit: \"rest.limit\"\n                period: \"rest.period\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/appliances\n          name: appliances\n          description: \"Web Gateway appliance health\"\n          operations:\n            - method: GET\n              name: list-appliances\n\
  \              description: \"List appliances and health status\"\n              call: \"twg-rest.list-appliances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/logs\n          name: system-logs\n          description: \"System and audit logs\"\n          operations:\n            - method: GET\n              name: get-logs\n              description: \"Get system logs\"\n              call: \"twg-rest.get-logs\"\n              with:\n                type: \"rest.type\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: twg-security-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Web Gateway security operations and threat investigation.\"\n      tools:\n        - name: get-security-events\n\
  \          description: \"Retrieve security events from Web Gateway including malware detections and policy violations. Use for incident investigation and threat hunting.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twg-reporting.get-security-events\"\n          with:\n            from: \"tools.from\"\n            to: \"tools.to\"\n            severity: \"tools.severity\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-traffic-logs\n          description: \"Retrieve web traffic logs for forensic analysis, compliance auditing, and user behavior investigation.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twg-reporting.get-traffic-logs\"\n          with:\n            from: \"tools.from\"\n            to: \"tools.to\"\n            limit: \"tools.limit\"\n          outputParameters:\n          \
  \  - type: object\n              mapping: \"$.\"\n        - name: get-threat-statistics\n          description: \"Get threat statistics to understand attack patterns, malware trends, and security posture over time.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twg-reporting.get-threat-statistics\"\n          with:\n            period: \"tools.period\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-traffic-statistics\n          description: \"Get web traffic statistics for capacity planning and anomaly detection.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twg-reporting.get-traffic-statistics\"\n          with:\n            period: \"tools.period\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-top-urls\n          description: \"Get top accessed URLs to identify potential\
  \ policy violations or unusual browsing patterns.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twg-reporting.get-top-urls\"\n          with:\n            limit: \"tools.limit\"\n            period: \"tools.period\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-top-categories\n          description: \"Get top URL categories to understand web browsing patterns and policy effectiveness.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twg-reporting.get-top-categories\"\n          with:\n            limit: \"tools.limit\"\n            period: \"tools.period\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-system-logs\n          description: \"Retrieve Web Gateway system and audit logs for compliance and change tracking.\"\n          hints:\n            readOnly: true\n \
  \           openWorld: true\n          call: \"twg-rest.get-logs\"\n          with:\n            type: \"tools.type\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-appliances\n          description: \"List Web Gateway appliances and check their operational health status.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twg-rest.list-appliances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
