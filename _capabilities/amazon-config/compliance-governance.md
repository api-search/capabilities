---
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
- list all aws config rules.
- governance
- audits resource compliance, reviews configuration history, and ensures governance standards.
- get compliance status for aws resources.
- configuration management
- Security Engineer
- put config rule
- security
- auditing
- get configuration history for a resource.
- check compliance status across all resources for a specific config rule.
- create or update an aws config compliance rule.
- start remediation
- list all discovered aws resources of a given type in config inventory.
- get the current configuration of one or more aws resources.
- start remediation execution for noncompliant resources.
- start automated remediation for noncompliant resources.
- discovered resource inventory.
- Compliance Officer
- list resources
- list discovered aws resources of a given type.
- aws
- resource configuration history.
- compliance
- create or update a config rule.
- get config history
- compliance summary by resource type.
- get compliance summary
- amazon
- get the configuration history for a specific aws resource.
- remediation
- create config rule
- check compliance status of a specific aws resource against config rules.
- delete config rule
- get a summary of compliant vs noncompliant resources by resource type.
- check resource compliance
- delete an aws config compliance rule.
- manage config compliance rules.
- get current config
- resource compliance monitoring, configuration history, and automated remediation.
- list all aws config compliance rules in the account.
- check rule compliance
- get resource history
- get compliance summary across resource types.
- creates and manages config rules to enforce security policies.
- list config rules
- check resource compliance status.
- remediation configuration and execution.
- get resource compliance
slug: compliance-governance
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
