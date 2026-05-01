---
api_specs:
- filename: amazon-guardduty-openapi.yml
  format: yaml
  label: amazon-guardduty
  slug: amazon-guardduty
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-guardduty/refs/heads/main/openapi/amazon-guardduty-openapi.yml
categories: []
consumed_apis:
- amazon-guardduty
description: Workflow capability for security teams using Amazon GuardDuty for AWS threat detection and response. Covers finding management, detector configuration, threat intelligence integration, and automated response workflows.
layout: capability
name: Amazon GuardDuty Threat Detection
operations:
- description: List all GuardDuty detectors
  method: GET
  name: list-detectors
  path: /v1/detectors
- description: Enable GuardDuty for an account
  method: POST
  name: create-detector
  path: /v1/detectors
- description: List threat findings
  method: GET
  name: list-findings
  path: /v1/findings
- description: Archive reviewed findings
  method: POST
  name: archive-findings
  path: /v1/findings
- description: Create a finding filter
  method: POST
  name: create-filter
  path: /v1/filters
- description: List threat intelligence sets
  method: GET
  name: list-threat-intel-sets
  path: /v1/threat-intel
personas: []
provider_name: Amazon GuardDuty
provider_slug: amazon-guardduty
search_terms:
- get detailed information about specific threat findings including full context
- threat findings from guardduty analysis
- get detector status
- list member accounts monitored by this guardduty administrator account
- list threat intelligence sets used for enhanced detection
- list trusted ip address sets excluded from threat detection
- archive reviewed findings
- threat detection
- anomaly detection
- list threat findings
- get the configuration and status of a guardduty detector
- list trusted ip sets
- incident response
- finding suppression filters
- Cloud Security Engineer
- create a suppression filter to reduce noise from benign findings
- get finding statistics and severity counts for security posture overview
- monitors security alerts and manages threat response workflows
- threat intelligence feeds
- list threat intelligence sets
- get finding details
- list members
- investigates and responds to threat findings from guardduty
- list all finding suppression filters
- list findings
- archive threat findings that have been reviewed and resolved
- list active threat findings detected by guardduty with severity filters
- security operations
- machine learning
- monitoring
- list finding filters
- get findings statistics
- compliance
- guardduty detector management
- enable guardduty for an account
- create finding filter
- SOC Engineer
- list threat intel sets
- aws
- security
- list all guardduty detectors
- configures guardduty detectors and threat intelligence feeds
- create a finding filter
- list detectors
- archive findings
- amazon guardduty
- create trusted ip set
- create filter
- list all active guardduty detectors across the account
- create detector
- create a trusted ip set to exclude known safe ips from alerts
- Security Analyst
slug: amazon-guardduty-threat-detection
source_filename: amazon-guardduty-threat-detection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon GuardDuty Threat Detection\n  description: >-\n    Workflow capability for security teams using Amazon GuardDuty for AWS threat\n    detection and response. Covers finding management, detector configuration,\n    threat intelligence integration, and automated response workflows.\n  tags:\n    - Amazon GuardDuty\n    - Threat Detection\n    - Security Operations\n    - Incident Response\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-guardduty\n      location: ./shared/amazon-guardduty.yaml\n\n  exposes:\n    - type: rest\n      port: 8085\n      namespace: guardduty-threat-detection-api\n      description: Unified REST API for Amazon GuardDuty threat detection operations.\n      resources:\n\
  \        - path: /v1/detectors\n          name: detectors\n          description: GuardDuty detector management\n          operations:\n            - method: GET\n              name: list-detectors\n              description: List all GuardDuty detectors\n              call: amazon-guardduty.ListDetectors\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-detector\n              description: Enable GuardDuty for an account\n              call: amazon-guardduty.CreateDetector\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/findings\n          name: findings\n          description: Threat findings from GuardDuty analysis\n          operations:\n            - method: GET\n              name: list-findings\n              description: List threat findings\n              call: amazon-guardduty.ListFindings\n        \
  \      outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: archive-findings\n              description: Archive reviewed findings\n              call: amazon-guardduty.ArchiveFindings\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/filters\n          name: filters\n          description: Finding suppression filters\n          operations:\n            - method: POST\n              name: create-filter\n              description: Create a finding filter\n              call: amazon-guardduty.CreateFilter\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/threat-intel\n          name: threat-intel\n          description: Threat intelligence feeds\n          operations:\n            - method: GET\n              name: list-threat-intel-sets\n              description: List\
  \ threat intelligence sets\n              call: amazon-guardduty.ListThreatIntelSets\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9095\n      namespace: guardduty-threat-detection-mcp\n      transport: http\n      description: MCP server for AI-assisted Amazon GuardDuty threat detection and response.\n      tools:\n        - name: list-detectors\n          description: List all active GuardDuty detectors across the account\n          hints:\n            readOnly: true\n            openWorld: true\n          call: amazon-guardduty.ListDetectors\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-detector-status\n          description: Get the configuration and status of a GuardDuty detector\n          hints:\n            readOnly: true\n          call: amazon-guardduty.GetDetector\n          outputParameters:\n            - type: object\n      \
  \        mapping: \"$.\"\n        - name: list-threat-findings\n          description: List active threat findings detected by GuardDuty with severity filters\n          hints:\n            readOnly: true\n          call: amazon-guardduty.ListFindings\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-finding-details\n          description: Get detailed information about specific threat findings including full context\n          hints:\n            readOnly: true\n          call: amazon-guardduty.GetFindings\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: archive-findings\n          description: Archive threat findings that have been reviewed and resolved\n          hints:\n            readOnly: false\n          call: amazon-guardduty.ArchiveFindings\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-finding-filter\n\
  \          description: Create a suppression filter to reduce noise from benign findings\n          hints:\n            readOnly: false\n          call: amazon-guardduty.CreateFilter\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-finding-filters\n          description: List all finding suppression filters\n          hints:\n            readOnly: true\n          call: amazon-guardduty.ListFilters\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-trusted-ip-sets\n          description: List trusted IP address sets excluded from threat detection\n          hints:\n            readOnly: true\n          call: amazon-guardduty.ListIPSets\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-trusted-ip-set\n          description: Create a trusted IP set to exclude known safe IPs from alerts\n          hints:\n    \
  \        readOnly: false\n          call: amazon-guardduty.CreateIPSet\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-threat-intel-sets\n          description: List threat intelligence sets used for enhanced detection\n          hints:\n            readOnly: true\n          call: amazon-guardduty.ListThreatIntelSets\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-findings-statistics\n          description: Get finding statistics and severity counts for security posture overview\n          hints:\n            readOnly: true\n          call: amazon-guardduty.GetFindingsStatistics\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-members\n          description: List member accounts monitored by this GuardDuty administrator account\n          hints:\n            readOnly: true\n          call: amazon-guardduty.ListMembers\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-guardduty/refs/heads/main/capabilities/amazon-guardduty-threat-detection.yaml
tags:
- Amazon GuardDuty
- Threat Detection
- Security Operations
- Incident Response
tools:
- description: List all active GuardDuty detectors across the account
  hints:
    openWorld: true
    readOnly: true
  name: list-detectors
- description: Get the configuration and status of a GuardDuty detector
  hints:
    readOnly: true
  name: get-detector-status
- description: List active threat findings detected by GuardDuty with severity filters
  hints:
    readOnly: true
  name: list-threat-findings
- description: Get detailed information about specific threat findings including full context
  hints:
    readOnly: true
  name: get-finding-details
- description: Archive threat findings that have been reviewed and resolved
  hints:
    readOnly: false
  name: archive-findings
- description: Create a suppression filter to reduce noise from benign findings
  hints:
    readOnly: false
  name: create-finding-filter
- description: List all finding suppression filters
  hints:
    readOnly: true
  name: list-finding-filters
- description: List trusted IP address sets excluded from threat detection
  hints:
    readOnly: true
  name: list-trusted-ip-sets
- description: Create a trusted IP set to exclude known safe IPs from alerts
  hints:
    readOnly: false
  name: create-trusted-ip-set
- description: List threat intelligence sets used for enhanced detection
  hints:
    readOnly: true
  name: list-threat-intel-sets
- description: Get finding statistics and severity counts for security posture overview
  hints:
    readOnly: true
  name: get-findings-statistics
- description: List member accounts monitored by this GuardDuty administrator account
  hints:
    readOnly: true
  name: list-members
---
