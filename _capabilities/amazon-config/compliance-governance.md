---
categories:
- compliance
consumed_apis:
- config
description: Workflow capability for AWS resource configuration tracking, compliance evaluation, configuration history auditing, and automated remediation using Amazon Config. Used by security engineers and compliance officers to enforce governance policies and audit configuration changes across AWS infrastructure.
layout: capability
name: Amazon Config Compliance and Governance
operations:
- description: List all AWS Config rules.
  method: GET
  name: list-config-rules
  path: /v1/config-rules
- description: Create or update a Config rule.
  method: PUT
  name: put-config-rule
  path: /v1/config-rules
- description: Get compliance status for AWS resources.
  method: GET
  name: get-resource-compliance
  path: /v1/compliance/resources
- description: Get compliance summary across resource types.
  method: GET
  name: get-compliance-summary
  path: /v1/compliance/summary
- description: List discovered AWS resources of a given type.
  method: GET
  name: list-resources
  path: /v1/resources
- description: Get configuration history for a resource.
  method: GET
  name: get-config-history
  path: /v1/resources/{resource_type}/{resource_id}/history
- description: Start remediation execution for noncompliant resources.
  method: POST
  name: start-remediation
  path: /v1/remediation
personas: []
provider_name: Amazon Config
provider_slug: amazon-config
search_terms:
- manage config compliance rules.
- resource compliance monitoring, configuration history, and automated remediation.
- start automated remediation for noncompliant resources.
- list discovered aws resources of a given type.
- get compliance status for aws resources.
- resource configuration history.
- list all discovered aws resources of a given type in config inventory.
- delete an aws config compliance rule.
- check resource compliance
- compliance
- check resource compliance status.
- get resource history
- create or update an aws config compliance rule.
- get resource compliance
- check rule compliance
- create config rule
- get the configuration history for a specific aws resource.
- Compliance Officer
- discovered resource inventory.
- remediation
- list all aws config rules.
- get a summary of compliant vs noncompliant resources by resource type.
- check compliance status of a specific aws resource against config rules.
- auditing
- aws
- get compliance summary across resource types.
- get configuration history for a resource.
- get config history
- Security Engineer
- amazon
- start remediation
- get compliance summary
- get current config
- security
- create or update a config rule.
- compliance summary by resource type.
- governance
- delete config rule
- configuration management
- get the current configuration of one or more aws resources.
- list resources
- remediation configuration and execution.
- list all aws config compliance rules in the account.
- list config rules
- put config rule
- start remediation execution for noncompliant resources.
- creates and manages config rules to enforce security policies.
- audits resource compliance, reviews configuration history, and ensures governance standards.
- check compliance status across all resources for a specific config rule.
slug: compliance-governance
source_filename: compliance-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Config Compliance and Governance\"\n  description: \"Workflow capability for AWS resource configuration tracking, compliance evaluation, configuration history auditing, and automated remediation using Amazon Config. Used by security engineers and compliance officers to enforce governance policies and audit configuration changes across AWS infrastructure.\"\n  tags:\n    - Amazon\n    - AWS\n    - Compliance\n    - Configuration Management\n    - Governance\n    - Security\n    - Auditing\n    - Remediation\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: config\n      location: ./shared/config.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: compliance-governance-api\n      description:\
  \ \"Unified REST API for Amazon Config compliance monitoring and governance.\"\n      resources:\n        - path: /v1/config-rules\n          name: config-rules\n          description: \"Manage Config compliance rules.\"\n          operations:\n            - method: GET\n              name: list-config-rules\n              description: \"List all AWS Config rules.\"\n              call: \"config.describe-config-rules\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: PUT\n              name: put-config-rule\n              description: \"Create or update a Config rule.\"\n              call: \"config.put-config-rule\"\n              with:\n                config_rule: \"rest.config_rule\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/compliance/resources\n          name: resource-compliance\n          description: \"Check resource compliance\
  \ status.\"\n          operations:\n            - method: GET\n              name: get-resource-compliance\n              description: \"Get compliance status for AWS resources.\"\n              call: \"config.describe-compliance-by-resource\"\n              with:\n                resource_type: \"rest.resource_type\"\n                resource_id: \"rest.resource_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/compliance/summary\n          name: compliance-summary\n          description: \"Compliance summary by resource type.\"\n          operations:\n            - method: GET\n              name: get-compliance-summary\n              description: \"Get compliance summary across resource types.\"\n              call: \"config.get-compliance-summary-by-resource-type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/resources\n       \
  \   name: resources\n          description: \"Discovered resource inventory.\"\n          operations:\n            - method: GET\n              name: list-resources\n              description: \"List discovered AWS resources of a given type.\"\n              call: \"config.list-discovered-resources\"\n              with:\n                resource_type: \"rest.resource_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/resources/{resource_type}/{resource_id}/history\n          name: resource-history\n          description: \"Resource configuration history.\"\n          operations:\n            - method: GET\n              name: get-config-history\n              description: \"Get configuration history for a resource.\"\n              call: \"config.get-resource-config-history\"\n              with:\n                resource_type: \"rest.resource_type\"\n                resource_id: \"rest.resource_id\"\n    \
  \          outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/remediation\n          name: remediation\n          description: \"Remediation configuration and execution.\"\n          operations:\n            - method: POST\n              name: start-remediation\n              description: \"Start remediation execution for noncompliant resources.\"\n              call: \"config.start-remediation-execution\"\n              with:\n                rule_name: \"rest.rule_name\"\n                resource_keys: \"rest.resource_keys\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: compliance-governance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon Config compliance monitoring and governance.\"\n      tools:\n        - name: list-config-rules\n          description: \"List all AWS Config compliance\
  \ rules in the account.\"\n          hints:\n            readOnly: true\n          call: \"config.describe-config-rules\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-resource-compliance\n          description: \"Check compliance status of a specific AWS resource against Config rules.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"config.describe-compliance-by-resource\"\n          with:\n            resource_type: \"tools.resource_type\"\n            resource_id: \"tools.resource_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-rule-compliance\n          description: \"Check compliance status across all resources for a specific Config rule.\"\n          hints:\n            readOnly: true\n          call: \"config.describe-compliance-by-config-rule\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: get-compliance-summary\n          description: \"Get a summary of compliant vs noncompliant resources by resource type.\"\n          hints:\n            readOnly: true\n          call: \"config.get-compliance-summary-by-resource-type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-resources\n          description: \"List all discovered AWS resources of a given type in Config inventory.\"\n          hints:\n            readOnly: true\n          call: \"config.list-discovered-resources\"\n          with:\n            resource_type: \"tools.resource_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-resource-history\n          description: \"Get the configuration history for a specific AWS resource.\"\n          hints:\n            readOnly: true\n          call: \"config.get-resource-config-history\"\n     \
  \     with:\n            resource_type: \"tools.resource_type\"\n            resource_id: \"tools.resource_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-current-config\n          description: \"Get the current configuration of one or more AWS resources.\"\n          hints:\n            readOnly: true\n          call: \"config.batch-get-resource-config\"\n          with:\n            resource_keys: \"tools.resource_keys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-config-rule\n          description: \"Create or update an AWS Config compliance rule.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"config.put-config-rule\"\n          with:\n            config_rule: \"tools.config_rule\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-config-rule\n\
  \          description: \"Delete an AWS Config compliance rule.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"config.delete-config-rule\"\n          with:\n            rule_name: \"tools.rule_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-remediation\n          description: \"Start automated remediation for noncompliant resources.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"config.start-remediation-execution\"\n          with:\n            rule_name: \"tools.rule_name\"\n            resource_keys: \"tools.resource_keys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-config/refs/heads/main/capabilities/compliance-governance.yaml
tags:
- Amazon
- AWS
- Compliance
- Configuration Management
- Governance
- Security
- Auditing
- Remediation
tools:
- description: List all AWS Config compliance rules in the account.
  hints:
    readOnly: true
  name: list-config-rules
- description: Check compliance status of a specific AWS resource against Config rules.
  hints:
    openWorld: false
    readOnly: true
  name: check-resource-compliance
- description: Check compliance status across all resources for a specific Config rule.
  hints:
    readOnly: true
  name: check-rule-compliance
- description: Get a summary of compliant vs noncompliant resources by resource type.
  hints:
    readOnly: true
  name: get-compliance-summary
- description: List all discovered AWS resources of a given type in Config inventory.
  hints:
    readOnly: true
  name: list-resources
- description: Get the configuration history for a specific AWS resource.
  hints:
    readOnly: true
  name: get-resource-history
- description: Get the current configuration of one or more AWS resources.
  hints:
    readOnly: true
  name: get-current-config
- description: Create or update an AWS Config compliance rule.
  hints:
    destructive: false
    readOnly: false
  name: create-config-rule
- description: Delete an AWS Config compliance rule.
  hints:
    destructive: true
    readOnly: false
  name: delete-config-rule
- description: Start automated remediation for noncompliant resources.
  hints:
    destructive: false
    readOnly: false
  name: start-remediation
---
