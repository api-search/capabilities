---
categories: []
consumed_apis: []
description: REST API for Check Point CloudGuard Native cloud security posture management. Manages cloud accounts, assets, security policies, and risk findings across AWS, Azure, and GCP environments.
layout: capability
name: Check Point CloudGuard API
operations:
- description: List onboarded cloud accounts
  method: GET
  name: listcloudaccounts
  path: /CloudAccounts
- description: Onboard a cloud account
  method: POST
  name: createcloudaccount
  path: /CloudAccounts
- description: List compliance findings
  method: GET
  name: listfindings
  path: /Compliance/Finding
- description: List rulesets used for posture management
  method: GET
  name: listrulesets
  path: /Ruleset/view
- description: List historical compliance assessments
  method: GET
  name: listassessments
  path: /AssessmentHistoryV2
personas: []
provider_name: Check Point
provider_slug: checkpoint
search_terms:
- createcloudaccount
- listcloudaccounts
- listfindings
- api
- identity awareness
- list rulesets used for posture management
- waf
- checkpoint
- onboard a cloud account
- endpoint security
- cloud security
- network security
- mobile security
- firewall
- list historical compliance assessments
- listrulesets
- cybersecurity
- listassessments
- list onboarded cloud accounts
- threat prevention
- security
- list compliance findings
slug: checkpoint-capability
source_filename: checkpoint-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Check Point CloudGuard API\n  description: REST API for Check Point CloudGuard Native cloud security posture management. Manages cloud accounts, assets,\n    security policies, and risk findings across AWS, Azure, and GCP environments.\n  tags:\n  - Checkpoint\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: checkpoint\n    baseUri: https://api.dome9.com/v2\n    description: Check Point CloudGuard API HTTP API.\n    authentication:\n      type: basic\n      username: '{{CHECKPOINT_USERNAME}}'\n      password: '{{CHECKPOINT_PASSWORD}}'\n    resources:\n    - name: cloudaccounts\n      path: /CloudAccounts\n      operations:\n      - name: listcloudaccounts\n        method: GET\n        description: List onboarded cloud accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcloudaccount\n\
  \        method: POST\n        description: Onboard a cloud account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliance-finding\n      path: /Compliance/Finding\n      operations:\n      - name: listfindings\n        method: GET\n        description: List compliance findings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ruleset-view\n      path: /Ruleset/view\n      operations:\n      - name: listrulesets\n        method: GET\n        description: List rulesets used for posture management\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assessmenthistoryv2\n      path: /AssessmentHistoryV2\n      operations:\n      - name: listassessments\n        method: GET\n        description: List historical compliance\
  \ assessments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: checkpoint-rest\n    description: REST adapter for Check Point CloudGuard API.\n    resources:\n    - path: /CloudAccounts\n      name: listcloudaccounts\n      operations:\n      - method: GET\n        name: listcloudaccounts\n        description: List onboarded cloud accounts\n        call: checkpoint.listcloudaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /CloudAccounts\n      name: createcloudaccount\n      operations:\n      - method: POST\n        name: createcloudaccount\n        description: Onboard a cloud account\n        call: checkpoint.createcloudaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Compliance/Finding\n      name: listfindings\n      operations:\n      - method: GET\n \
  \       name: listfindings\n        description: List compliance findings\n        call: checkpoint.listfindings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Ruleset/view\n      name: listrulesets\n      operations:\n      - method: GET\n        name: listrulesets\n        description: List rulesets used for posture management\n        call: checkpoint.listrulesets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /AssessmentHistoryV2\n      name: listassessments\n      operations:\n      - method: GET\n        name: listassessments\n        description: List historical compliance assessments\n        call: checkpoint.listassessments\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: checkpoint-mcp\n    transport: http\n    description: MCP adapter for Check Point CloudGuard API for AI agent use.\n    tools:\n    - name: listcloudaccounts\n\
  \      description: List onboarded cloud accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: checkpoint.listcloudaccounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcloudaccount\n      description: Onboard a cloud account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: checkpoint.createcloudaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfindings\n      description: List compliance findings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: checkpoint.listfindings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrulesets\n      description: List rulesets used for posture management\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: checkpoint.listrulesets\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listassessments\n      description: List historical compliance assessments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: checkpoint.listassessments\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CHECKPOINT_USERNAME: CHECKPOINT_USERNAME\n    CHECKPOINT_PASSWORD: CHECKPOINT_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/checkpoint/refs/heads/main/capabilities/checkpoint-capability.yaml
tags:
- Checkpoint
- API
tools:
- description: List onboarded cloud accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcloudaccounts
- description: Onboard a cloud account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcloudaccount
- description: List compliance findings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfindings
- description: List rulesets used for posture management
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrulesets
- description: List historical compliance assessments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listassessments
---
