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
- get the current configuration of one or more aws resources.
- compliance summary by resource type.
- put config rule
- start remediation
- check resource compliance status.
- delete config rule
- create config rule
- remediation
- get resource compliance
- get resource history
- resource configuration history.
- compliance
- start remediation execution for noncompliant resources.
- check resource compliance
- remediation configuration and execution.
- create or update an aws config compliance rule.
- delete an aws config compliance rule.
- get compliance summary across resource types.
- create or update a config rule.
- discovered resource inventory.
- start automated remediation for noncompliant resources.
- get compliance summary
- list all aws config compliance rules in the account.
- get config history
- check compliance status of a specific aws resource against config rules.
- creates and manages config rules to enforce security policies.
- security
- audits resource compliance, reviews configuration history, and ensures governance standards.
- get configuration history for a resource.
- auditing
- get compliance status for aws resources.
- check compliance status across all resources for a specific config rule.
- Security Engineer
- list discovered aws resources of a given type.
- get current config
- configuration management
- governance
- list all aws config rules.
- list resources
- manage config compliance rules.
- get the configuration history for a specific aws resource.
- resource compliance monitoring, configuration history, and automated remediation.
- list config rules
- aws
- Compliance Officer
- check rule compliance
- list all discovered aws resources of a given type in config inventory.
- amazon
- get a summary of compliant vs noncompliant resources by resource type.
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
