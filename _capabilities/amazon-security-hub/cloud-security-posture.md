---
api_specs:
- filename: amazon-security-hub-openapi.yml
  format: yaml
  label: amazon-security-hub
  slug: amazon-security-hub
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-security-hub/refs/heads/main/openapi/amazon-security-hub-openapi.yml
categories:
- security
consumed_apis:
- amazon-security-hub
description: Unified capability for cloud security posture management including findings aggregation, compliance standards monitoring, and security insights. Used by Cloud Security Engineers and SOC Analysts.
layout: capability
name: Amazon Security Hub Cloud Security Posture
operations:
- description: List and filter security findings
  method: GET
  name: list-findings
  path: /v1/findings
- description: Import findings from custom security tools
  method: POST
  name: import-findings
  path: /v1/findings
- description: List enabled compliance standards
  method: GET
  name: list-standards
  path: /v1/standards
- description: List security controls and their compliance status
  method: GET
  name: list-controls
  path: /v1/controls
- description: List security insights and trends
  method: GET
  name: list-insights
  path: /v1/insights
personas: []
provider_name: Amazon Security Hub
provider_slug: amazon-security-hub
search_terms:
- update security findings notes and status
- security
- amazon security hub
- SOC Analyst
- monitoring
- import findings
- security controls status and configuration
- compliance security standards monitoring
- cspm
- import security findings
- cloud security posture and finding management across aws accounts
- import custom security findings into amazon security hub
- get aggregated security insights and trend analysis
- aggregated security insights across your environment
- aws
- list controls
- import findings from custom security tools
- list security controls and their compliance status
- list enabled compliance standards like cis, pci dss, soc 2
- list security insights and trends
- update findings
- list compliance standards
- compliance
- Cloud Security Engineer
- list enabled compliance standards
- analysts who investigate security findings and track remediation workflows
- list and filter security findings
- centralized cloud security posture management including findings, compliance standards, controls, and insights
- list security controls and check their compliance status
- security standards compliance monitoring and control management
- get security insights
- list findings
- list standards
- engineers who configure security standards, manage controls, and remediate findings
- get security findings
- security findings from across your aws environment
- get and filter security findings from amazon security hub
- list security controls
- list insights
slug: cloud-security-posture
source_filename: cloud-security-posture.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Security Hub Cloud Security Posture\"\n  description: \"Unified capability for cloud security posture management including findings aggregation, compliance standards monitoring, and security insights. Used by Cloud Security Engineers and SOC Analysts.\"\n  tags:\n    - Amazon Security Hub\n    - Security\n    - Compliance\n    - CSPM\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-security-hub\n      location: ./shared/amazon-security-hub.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cloud-security-posture-api\n      description: \"Unified REST API for Amazon Security Hub cloud security posture management.\"\n      resources:\n        - path: /v1/findings\n      \
  \    name: findings\n          description: \"Security findings from across your AWS environment\"\n          operations:\n            - method: GET\n              name: list-findings\n              description: \"List and filter security findings\"\n              call: \"amazon-security-hub.get-findings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: import-findings\n              description: \"Import findings from custom security tools\"\n              call: \"amazon-security-hub.batch-import-findings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/standards\n          name: standards\n          description: \"Compliance security standards monitoring\"\n          operations:\n            - method: GET\n              name: list-standards\n              description: \"List enabled compliance standards\"\n    \
  \          call: \"amazon-security-hub.get-enabled-standards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/controls\n          name: controls\n          description: \"Security controls status and configuration\"\n          operations:\n            - method: GET\n              name: list-controls\n              description: \"List security controls and their compliance status\"\n              call: \"amazon-security-hub.describe-standards-controls\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/insights\n          name: insights\n          description: \"Aggregated security insights across your environment\"\n          operations:\n            - method: GET\n              name: list-insights\n              description: \"List security insights and trends\"\n              call: \"amazon-security-hub.get-insights\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: cloud-security-posture-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon Security Hub cloud security posture management.\"\n      tools:\n        - name: get-security-findings\n          description: \"Get and filter security findings from Amazon Security Hub\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-security-hub.get-findings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: import-security-findings\n          description: \"Import custom security findings into Amazon Security Hub\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-security-hub.batch-import-findings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n       \
  \ - name: update-findings\n          description: \"Update security findings notes and status\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-security-hub.batch-update-findings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-compliance-standards\n          description: \"List enabled compliance standards like CIS, PCI DSS, SOC 2\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-security-hub.get-enabled-standards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-security-controls\n          description: \"List security controls and check their compliance status\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-security-hub.describe-standards-controls\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: get-security-insights\n          description: \"Get aggregated security insights and trend analysis\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-security-hub.get-insights\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-security-hub/refs/heads/main/capabilities/cloud-security-posture.yaml
tags:
- Amazon Security Hub
- Security
- Compliance
- CSPM
tools:
- description: Get and filter security findings from Amazon Security Hub
  hints:
    idempotent: true
    readOnly: true
  name: get-security-findings
- description: Import custom security findings into Amazon Security Hub
  hints:
    idempotent: false
    readOnly: false
  name: import-security-findings
- description: Update security findings notes and status
  hints:
    idempotent: false
    readOnly: false
  name: update-findings
- description: List enabled compliance standards like CIS, PCI DSS, SOC 2
  hints:
    idempotent: true
    readOnly: true
  name: list-compliance-standards
- description: List security controls and check their compliance status
  hints:
    idempotent: true
    readOnly: true
  name: list-security-controls
- description: Get aggregated security insights and trend analysis
  hints:
    idempotent: true
    readOnly: true
  name: get-security-insights
---
