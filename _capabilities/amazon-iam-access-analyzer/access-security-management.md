---
consumed_apis:
- iam-access-analyzer
description: Unified capability for security teams to manage access analyzers, review findings, validate policies, and enforce least-privilege access controls across AWS accounts.
layout: capability
name: Amazon IAM Access Analyzer - Access Security Management
operations:
- description: List all access analyzers in the account
  method: GET
  name: list-analyzers
  path: /v1/analyzers
- description: Create a new access analyzer
  method: POST
  name: create-analyzer
  path: /v1/analyzers
- description: List findings from an analyzer
  method: GET
  name: list-findings
  path: /v1/findings
- description: Validate an IAM policy for best practices
  method: POST
  name: validate-policy
  path: /v1/policies/validate
- description: Start generating a policy based on CloudTrail activity
  method: POST
  name: start-policy-generation
  path: /v1/policies/generate
personas: []
provider_name: Amazon IAM Access Analyzer
provider_slug: amazon-iam-access-analyzer
search_terms:
- ensuring access controls meet security standards
- list findings from an analyzer
- list analyzers
- list findings
- review access analyzer findings
- Security Engineer
- creating, validating, and optimizing iam policies
- security
- retrieve a policy generated from cloudtrail activity
- list all access analyzers in the account
- Cloud Security Engineer
- validate an iam policy document for best practices and security issues
- get finding
- manages iam policies, roles, and access controls
- generate an iam policy based on cloudtrail access activity logs
- create analyzer
- aws
- start generating a policy based on cloudtrail activity
- compliance
- reviews access findings and remediates unintended access
- create a new iam access analyzer for an account or organization
- start policy generation
- validate an iam policy for best practices
- manage access analyzers
- list security findings from an access analyzer
- validate policy
- IAM Administrator
- access control
- list archive rules
- generate iam policies from activity logs
- create access preview
- preview access changes before deploying permission changes
- validate iam policies
- list archive rules for an analyzer
- managing who can access what resources
- policy management
- get generated policy
- get details of a specific access finding
- iam
- create a new access analyzer
- list all iam access analyzers configured in the account
- manage analyzers, findings, validate policies, and generate least-privilege policies
slug: access-security-management
tags:
- AWS
- IAM
- Security
- Access Control
- Compliance
- Policy Management
tools:
- description: List all IAM Access Analyzers configured in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-analyzers
- description: Create a new IAM Access Analyzer for an account or organization
  hints:
    readOnly: false
  name: create-analyzer
- description: List security findings from an access analyzer
  hints:
    openWorld: true
    readOnly: true
  name: list-findings
- description: Get details of a specific access finding
  hints:
    openWorld: true
    readOnly: true
  name: get-finding
- description: Validate an IAM policy document for best practices and security issues
  hints:
    openWorld: false
    readOnly: true
  name: validate-policy
- description: Generate an IAM policy based on CloudTrail access activity logs
  hints:
    readOnly: false
  name: start-policy-generation
- description: Retrieve a policy generated from CloudTrail activity
  hints:
    openWorld: false
    readOnly: true
  name: get-generated-policy
- description: Preview access changes before deploying permission changes
  hints:
    readOnly: false
  name: create-access-preview
- description: List archive rules for an analyzer
  hints:
    openWorld: true
    readOnly: true
  name: list-archive-rules
---
