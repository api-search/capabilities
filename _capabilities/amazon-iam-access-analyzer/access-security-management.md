---
categories:
- security
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
- validate iam policies
- ensuring access controls meet security standards
- manage analyzers, findings, validate policies, and generate least-privilege policies
- manage access analyzers
- security
- create analyzer
- list archive rules for an analyzer
- validate policy
- IAM Administrator
- create access preview
- validate an iam policy document for best practices and security issues
- retrieve a policy generated from cloudtrail activity
- list findings
- creating, validating, and optimizing iam policies
- compliance
- preview access changes before deploying permission changes
- aws
- iam
- start policy generation
- managing who can access what resources
- review access analyzer findings
- start generating a policy based on cloudtrail activity
- list all iam access analyzers configured in the account
- get finding
- policy management
- get generated policy
- Cloud Security Engineer
- reviews access findings and remediates unintended access
- list findings from an analyzer
- list all access analyzers in the account
- create a new iam access analyzer for an account or organization
- list archive rules
- manages iam policies, roles, and access controls
- validate an iam policy for best practices
- access control
- generate an iam policy based on cloudtrail access activity logs
- create a new access analyzer
- list analyzers
- list security findings from an access analyzer
- Security Engineer
- get details of a specific access finding
- generate iam policies from activity logs
slug: access-security-management
source_filename: access-security-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon IAM Access Analyzer - Access Security Management\n  description: Unified capability for security teams to manage access analyzers, review findings, validate policies, and enforce least-privilege access controls across AWS accounts.\n  tags:\n    - AWS\n    - IAM\n    - Security\n    - Access Control\n    - Compliance\n    - Policy Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n\ncapability:\n  consumes:\n    - import: iam-access-analyzer\n      location: ./shared/iam-access-analyzer.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: access-security-api\n      description: Unified REST API for access security management.\n      resources:\n        - path: /v1/analyzers\n          name: analyzers\n          description: Manage access analyzers\n   \
  \       operations:\n            - method: GET\n              name: list-analyzers\n              description: List all access analyzers in the account\n              call: \"iam-access-analyzer.listanalyzers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-analyzer\n              description: Create a new access analyzer\n              call: \"iam-access-analyzer.createanalyzer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/findings\n          name: findings\n          description: Review access analyzer findings\n          operations:\n            - method: GET\n              name: list-findings\n              description: List findings from an analyzer\n              call: \"iam-access-analyzer.listfindings\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/policies/validate\n          name: policy-validation\n          description: Validate IAM policies\n          operations:\n            - method: POST\n              name: validate-policy\n              description: Validate an IAM policy for best practices\n              call: \"iam-access-analyzer.validatepolicy\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/policies/generate\n          name: policy-generation\n          description: Generate IAM policies from activity logs\n          operations:\n            - method: POST\n              name: start-policy-generation\n              description: Start generating a policy based on CloudTrail activity\n              call: \"iam-access-analyzer.startpolicygeneration\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: access-security-mcp\n\
  \      transport: http\n      description: MCP server for AI-assisted access security management.\n      tools:\n        - name: list-analyzers\n          description: List all IAM Access Analyzers configured in the account\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iam-access-analyzer.listanalyzers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-analyzer\n          description: Create a new IAM Access Analyzer for an account or organization\n          hints:\n            readOnly: false\n          call: \"iam-access-analyzer.createanalyzer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-findings\n          description: List security findings from an access analyzer\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iam-access-analyzer.listfindings\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-finding\n          description: Get details of a specific access finding\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iam-access-analyzer.getfinding\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: validate-policy\n          description: Validate an IAM policy document for best practices and security issues\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"iam-access-analyzer.validatepolicy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-policy-generation\n          description: Generate an IAM policy based on CloudTrail access activity logs\n          hints:\n            readOnly: false\n          call: \"iam-access-analyzer.startpolicygeneration\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: get-generated-policy\n          description: Retrieve a policy generated from CloudTrail activity\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"iam-access-analyzer.getgeneratedpolicy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-access-preview\n          description: Preview access changes before deploying permission changes\n          hints:\n            readOnly: false\n          call: \"iam-access-analyzer.createaccesspreview\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-archive-rules\n          description: List archive rules for an analyzer\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iam-access-analyzer.listarchiveruless\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-iam-access-analyzer/refs/heads/main/capabilities/access-security-management.yaml
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
