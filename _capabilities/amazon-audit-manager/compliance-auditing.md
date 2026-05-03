---
categories:
- compliance
consumed_apis: []
description: Workflow capability for conducting continuous compliance auditing with Amazon Audit Manager including assessment creation, evidence collection, and report generation.
layout: capability
name: Compliance Auditing Workflow
operations:
- description: List all assessments
  method: GET
  name: list-assessments
  path: /v1/assessments
- description: Create a new assessment
  method: POST
  name: create-assessment
  path: /v1/assessments
- description: List available frameworks
  method: GET
  name: list-frameworks
  path: /v1/frameworks
personas: []
provider_name: Amazon Audit Manager
provider_slug: amazon-audit-manager
search_terms:
- compliance assessment management
- audit
- list controls
- get settings
- amazon audit manager
- generate a compliance assessment report from collected evidence.
- compliance
- update audit manager settings including sns notifications and default report destination.
- create a custom compliance control for use in frameworks and assessments.
- create a new compliance assessment using a regulatory framework.
- list all compliance assessments to understand current audit coverage.
- risk management
- list available frameworks
- aws
- list assessments
- list generated assessment reports for compliance documentation.
- compliance framework management
- list frameworks
- get complete details of a compliance assessment including control status.
- list compliance controls available for building assessments.
- create assessment report
- list assessment reports
- list available compliance frameworks such as soc 2, pci dss, and hipaa.
- get assessment
- create a new assessment
- create control
- update settings
- list all assessments
- get audit manager account settings including default destinations and process owners.
- create assessment
slug: compliance-auditing
source_filename: compliance-auditing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Compliance Auditing Workflow\n  description: Workflow capability for conducting continuous compliance auditing with Amazon Audit Manager including assessment creation, evidence collection, and report generation.\n  tags:\n    - Amazon Audit Manager\n    - Compliance\n    - Audit\n    - Risk Management\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nimports:\n  - namespace: auditmanager\n    from: shared/audit-manager-api.yaml\n\ncapability:\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: compliance-auditing-rest\n      resources:\n        - path: /v1/assessments\n          name: assessments\n          description: Compliance assessment management\n          operations:\n            - method: GET\n              name: list-assessments\n              description: List all assessments\n              call: \"auditmanager.list-assessments\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-assessment\n              description: Create a new assessment\n              call: \"auditmanager.create-assessment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/frameworks\n          name: frameworks\n          description: Compliance framework management\n          operations:\n            - method: GET\n              name: list-frameworks\n              description: List available frameworks\n              call: \"auditmanager.list-frameworks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: compliance-auditing-mcp\n      transport: http\n      tools:\n        - name: list-assessments\n          description: List all compliance assessments to understand current audit coverage.\n          hints:\n    \
  \        readOnly: true\n            openWorld: true\n          call: \"auditmanager.list-assessments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-assessment\n          description: Create a new compliance assessment using a regulatory framework.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"auditmanager.create-assessment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-assessment\n          description: Get complete details of a compliance assessment including control status.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"auditmanager.get-assessment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-frameworks\n          description: List available compliance frameworks such as SOC 2, PCI DSS, and\
  \ HIPAA.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"auditmanager.list-frameworks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-controls\n          description: List compliance controls available for building assessments.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"auditmanager.list-controls\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-control\n          description: Create a custom compliance control for use in frameworks and assessments.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"auditmanager.create-control\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-assessment-reports\n          description: List generated assessment reports for\
  \ compliance documentation.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"auditmanager.list-assessment-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-assessment-report\n          description: Generate a compliance assessment report from collected evidence.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"auditmanager.create-assessment-report\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-settings\n          description: Get Audit Manager account settings including default destinations and process owners.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"auditmanager.get-settings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-settings\n     \
  \     description: Update Audit Manager settings including SNS notifications and default report destination.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"auditmanager.update-settings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\npersonas:\n  - name: Compliance Officer\n    description: Manages compliance assessments, reviews evidence, and generates audit reports.\n    tools:\n      - list-assessments\n      - create-assessment\n      - get-assessment\n      - list-frameworks\n      - list-assessment-reports\n      - create-assessment-report\n      - get-settings\n\n  - name: Security Engineer\n    description: Builds and maintains compliance frameworks and controls for the organization.\n    tools:\n      - list-frameworks\n      - list-controls\n      - create-control\n      - list-assessments\n      - get-assessment\n      - update-settings\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-audit-manager/refs/heads/main/capabilities/compliance-auditing.yaml
tags:
- Amazon Audit Manager
- Compliance
- Audit
- Risk Management
tools:
- description: List all compliance assessments to understand current audit coverage.
  hints:
    openWorld: true
    readOnly: true
  name: list-assessments
- description: Create a new compliance assessment using a regulatory framework.
  hints:
    openWorld: false
    readOnly: false
  name: create-assessment
- description: Get complete details of a compliance assessment including control status.
  hints:
    openWorld: true
    readOnly: true
  name: get-assessment
- description: List available compliance frameworks such as SOC 2, PCI DSS, and HIPAA.
  hints:
    openWorld: true
    readOnly: true
  name: list-frameworks
- description: List compliance controls available for building assessments.
  hints:
    openWorld: true
    readOnly: true
  name: list-controls
- description: Create a custom compliance control for use in frameworks and assessments.
  hints:
    openWorld: false
    readOnly: false
  name: create-control
- description: List generated assessment reports for compliance documentation.
  hints:
    openWorld: true
    readOnly: true
  name: list-assessment-reports
- description: Generate a compliance assessment report from collected evidence.
  hints:
    openWorld: false
    readOnly: false
  name: create-assessment-report
- description: Get Audit Manager account settings including default destinations and process owners.
  hints:
    openWorld: true
    readOnly: true
  name: get-settings
- description: Update Audit Manager settings including SNS notifications and default report destination.
  hints:
    openWorld: false
    readOnly: false
  name: update-settings
---
