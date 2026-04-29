---
categories:
- compliance
consumed_apis:
- macie
description: Workflow capability for security and compliance teams to discover sensitive data, investigate findings, and manage data security posture in Amazon S3 using Amazon Macie.
layout: capability
name: Amazon Macie - Data Security Operations
operations:
- description: List sensitive data findings
  method: GET
  name: list-findings
  path: /v1/findings
- description: Get finding details
  method: POST
  name: get-findings
  path: /v1/findings
- description: Create a data discovery job
  method: POST
  name: create-job
  path: /v1/jobs
- description: List all discovery jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Get bucket security details
  method: GET
  name: describe-buckets
  path: /v1/buckets
- description: Create custom data identifier
  method: POST
  name: create-identifier
  path: /v1/identifiers
- description: List custom identifiers
  method: GET
  name: list-identifiers
  path: /v1/identifiers
personas: []
provider_name: Amazon Macie
provider_slug: amazon-macie
search_terms:
- get finding details
- manages macie configuration, discovery jobs, and investigates sensitive data findings
- describe buckets
- data discovery jobs
- automated discovery and classification of sensitive data in s3
- list all discovery jobs
- data security
- list jobs
- workflow for discovering sensitive data, investigating findings, and managing data security posture
- list identifiers
- create a job to discover sensitive data in s3 buckets
- sensitive data
- compliance
- create a custom pattern to detect organization-specific sensitive data types
- aws
- get bucket security posture
- get findings
- create a data discovery job
- Security Engineer
- machine learning
- amazon
- list all sensitive data findings detected by macie
- sensitive data findings
- s3
- get detailed information about specific sensitive data findings
- reviews sensitive data findings to ensure data governance and regulatory compliance
- list all custom sensitive data identifiers
- create discovery job
- list sensitive data findings
- create job
- privacy
- monitored s3 buckets
- list all sensitive data discovery jobs
- list discovery jobs
- get security details and sensitive data statistics for monitored s3 buckets
- get bucket security details
- list findings
- managing and investigating sensitive data findings
- custom patterns for identifying organization-specific sensitive data
- custom data identifiers
- create identifier
- list custom identifiers
- create custom data identifier
- Compliance Officer
slug: data-security-operations
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Macie - Data Security Operations\"\n  description: \"Workflow capability for security and compliance teams to discover sensitive data, investigate findings, and manage data security posture in Amazon S3 using Amazon Macie.\"\n  tags:\n    - Amazon\n    - Data Security\n    - Sensitive Data\n    - Privacy\n    - Compliance\n    - S3\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: macie\n      location: ./shared/macie.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: data-security-api\n      description: \"Unified REST API for Amazon Macie data security operations.\"\n      resources:\n        - path: /v1/findings\n          name: findings\n          description: \"Sensitive data findings\"\
  \n          operations:\n            - method: GET\n              name: list-findings\n              description: \"List sensitive data findings\"\n              call: \"macie.list-findings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: get-findings\n              description: \"Get finding details\"\n              call: \"macie.get-findings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs\n          name: jobs\n          description: \"Data discovery jobs\"\n          operations:\n            - method: POST\n              name: create-job\n              description: \"Create a data discovery job\"\n              call: \"macie.create-classification-job\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-jobs\n\
  \              description: \"List all discovery jobs\"\n              call: \"macie.list-classification-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/buckets\n          name: buckets\n          description: \"Monitored S3 buckets\"\n          operations:\n            - method: GET\n              name: describe-buckets\n              description: \"Get bucket security details\"\n              call: \"macie.describe-buckets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/identifiers\n          name: identifiers\n          description: \"Custom data identifiers\"\n          operations:\n            - method: POST\n              name: create-identifier\n              description: \"Create custom data identifier\"\n              call: \"macie.create-custom-data-identifier\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n            - method: GET\n              name: list-identifiers\n              description: \"List custom identifiers\"\n              call: \"macie.list-custom-data-identifiers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: data-security-mcp\n      transport: http\n      description: \"MCP server for AI-assisted data security operations with Amazon Macie.\"\n      tools:\n        - name: list-sensitive-data-findings\n          description: \"List all sensitive data findings detected by Macie\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"macie.list-findings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-finding-details\n          description: \"Get detailed information about specific sensitive data\
  \ findings\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"macie.get-findings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-discovery-job\n          description: \"Create a job to discover sensitive data in S3 buckets\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"macie.create-classification-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-discovery-jobs\n          description: \"List all sensitive data discovery jobs\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"macie.list-classification-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-bucket-security-posture\n\
  \          description: \"Get security details and sensitive data statistics for monitored S3 buckets\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"macie.describe-buckets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-custom-data-identifier\n          description: \"Create a custom pattern to detect organization-specific sensitive data types\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"macie.create-custom-data-identifier\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-custom-identifiers\n          description: \"List all custom sensitive data identifiers\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"macie.list-custom-data-identifiers\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-macie/refs/heads/main/capabilities/data-security-operations.yaml
tags:
- Amazon
- Data Security
- Sensitive Data
- Privacy
- Compliance
- S3
tools:
- description: List all sensitive data findings detected by Macie
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-sensitive-data-findings
- description: Get detailed information about specific sensitive data findings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-finding-details
- description: Create a job to discover sensitive data in S3 buckets
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-discovery-job
- description: List all sensitive data discovery jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-discovery-jobs
- description: Get security details and sensitive data statistics for monitored S3 buckets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-bucket-security-posture
- description: Create a custom pattern to detect organization-specific sensitive data types
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-custom-data-identifier
- description: List all custom sensitive data identifiers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-custom-identifiers
---
