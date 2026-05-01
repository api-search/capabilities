---
categories:
- iot
consumed_apis:
- iot-device-defender
description: Unified capability for Security Engineer, IoT Developer to manage security service for iot fleet auditing and anomaly detection operations.
layout: capability
name: Amazon IoT Device Defender - Iot Security Monitoring
operations:
- description: List Security Profiles
  method: GET
  name: list-security-profiles
  path: /v1/resources
personas: []
provider_name: Amazon IoT Device Defender
provider_slug: amazon-iot-device-defender
search_terms:
- amazon iot device defender start audit
- vulnerability management
- list audit tasks
- list detect mitigations
- amazon iot device defender list detect mitigations
- amazon iot device defender describe security profile
- list audit findings
- iot
- amazon iot device defender list audit findings
- amazon iot device defender list audit tasks
- Security Engineer
- start audit
- amazon iot device defender resources
- device management
- amazon iot device defender list violations
- IoT Developer
- amazon iot device defender list security profiles
- amazon iot device defender create security profile
- describe security profile
- security service for iot fleet auditing and anomaly detection.
- list security profiles
- compliance
- create security profile
- aws
- security
- manages amazon iot device defender resources and operations
- list violations
slug: iot-security-monitoring
source_filename: iot-security-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: Amazon IoT Device Defender - Iot Security Monitoring\n  description: Unified capability for Security Engineer, IoT Developer to manage security service for iot fleet auditing and anomaly detection operations.\n  tags:\n    - IoT\n    - AWS\n    - Security\n    - Device Management\n    - Compliance\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n    - import: iot-device-defender\n      location: ./shared/iot-device-defender.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: iot-security-monitoring-api\n      description: Unified REST API for iot security monitoring.\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: Amazon IoT Device Defender resources\n          operations:\n            - method: GET\n\
  \              name: list-security-profiles\n              description: List Security Profiles\n              call: \"iot-device-defender.list-security-profiles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: iot-security-monitoring-mcp\n      transport: http\n      description: MCP server for AI-assisted iot security monitoring.\n      tools:\n        - name: list-security-profiles\n          description: Amazon IoT Device Defender List Security Profiles\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-device-defender.list-security-profiles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-security-profile\n          description: Amazon IoT Device Defender Create Security Profile\n          hints:\n            readOnly: false\n            \n          call: \"iot-device-defender.create-security-profile\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-audit-tasks\n          description: Amazon IoT Device Defender List Audit Tasks\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-device-defender.list-audit-tasks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-audit\n          description: Amazon IoT Device Defender Start Audit\n          hints:\n            readOnly: false\n            \n          call: \"iot-device-defender.start-audit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-violations\n          description: Amazon IoT Device Defender List Violations\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-device-defender.list-violations\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: list-detect-mitigations\n          description: Amazon IoT Device Defender List Detect Mitigations\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-device-defender.list-detect-mitigations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-security-profile\n          description: Amazon IoT Device Defender Describe Security Profile\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-device-defender.describe-security-profile\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-audit-findings\n          description: Amazon IoT Device Defender List Audit Findings\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iot-device-defender.list-audit-findings\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-iot-device-defender/refs/heads/main/capabilities/iot-security-monitoring.yaml
tags:
- IoT
- Security
- Device Management
- Compliance
tools:
- description: Amazon IoT Device Defender List Security Profiles
  hints:
    openWorld: true
    readOnly: true
  name: list-security-profiles
- description: Amazon IoT Device Defender Create Security Profile
  hints:
    readOnly: false
  name: create-security-profile
- description: Amazon IoT Device Defender List Audit Tasks
  hints:
    openWorld: true
    readOnly: true
  name: list-audit-tasks
- description: Amazon IoT Device Defender Start Audit
  hints:
    readOnly: false
  name: start-audit
- description: Amazon IoT Device Defender List Violations
  hints:
    openWorld: true
    readOnly: true
  name: list-violations
- description: Amazon IoT Device Defender List Detect Mitigations
  hints:
    openWorld: true
    readOnly: true
  name: list-detect-mitigations
- description: Amazon IoT Device Defender Describe Security Profile
  hints:
    openWorld: true
    readOnly: true
  name: describe-security-profile
- description: Amazon IoT Device Defender List Audit Findings
  hints:
    openWorld: true
    readOnly: true
  name: list-audit-findings
---
