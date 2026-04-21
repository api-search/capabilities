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
- list security findings from an access analyzer
- create access preview
- validate an iam policy document for best practices and security issues
- generate an iam policy based on cloudtrail access activity logs
- manages iam policies, roles, and access controls
- create a new access analyzer
- validate an iam policy for best practices
- start generating a policy based on cloudtrail activity
- validate policy
- list all iam access analyzers configured in the account
- list findings from an analyzer
- generate iam policies from activity logs
- policy management
- start policy generation
- list archive rules
- Cloud Security Engineer
- manage analyzers, findings, validate policies, and generate least-privilege policies
- get generated policy
- access control
- compliance
- list archive rules for an analyzer
- iam
- security
- IAM Administrator
- Security Engineer
- preview access changes before deploying permission changes
- manage access analyzers
- list all access analyzers in the account
- retrieve a policy generated from cloudtrail activity
- managing who can access what resources
- creating, validating, and optimizing iam policies
- validate iam policies
- aws
- review access analyzer findings
- list findings
- get finding
- list analyzers
- ensuring access controls meet security standards
- get details of a specific access finding
- create a new iam access analyzer for an account or organization
- reviews access findings and remediates unintended access
- create analyzer
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
