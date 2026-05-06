---
categories:
- compliance
consumed_apis: []
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
- monitored s3 buckets
- create identifier
- sensitive data
- sensitive data findings
- get security details and sensitive data statistics for monitored s3 buckets
- list jobs
- data discovery jobs
- workflow for discovering sensitive data, investigating findings, and managing data security posture
- create job
- amazon
- create a data discovery job
- list discovery jobs
- automated discovery and classification of sensitive data in s3
- Compliance Officer
- compliance
- get detailed information about specific sensitive data findings
- describe buckets
- create a job to discover sensitive data in s3 buckets
- reviews sensitive data findings to ensure data governance and regulatory compliance
- create discovery job
- machine learning
- list all custom sensitive data identifiers
- list identifiers
- list all sensitive data discovery jobs
- list custom identifiers
- list all discovery jobs
- data security
- get bucket security posture
- Security Engineer
- manages macie configuration, discovery jobs, and investigates sensitive data findings
- list sensitive data findings
- create custom data identifier
- list findings
- get bucket security details
- list all sensitive data findings detected by macie
- custom patterns for identifying organization-specific sensitive data
- s3
- get findings
- custom data identifiers
- privacy
- managing and investigating sensitive data findings
- create a custom pattern to detect organization-specific sensitive data types
slug: data-security-operations
source_filename: data-security-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Macie - Data Security Operations\n  description: Workflow capability for security and compliance teams to discover sensitive data, investigate findings, and\n    manage data security posture in Amazon S3 using Amazon Macie.\n  tags:\n  - Amazon\n  - Data Security\n  - Sensitive Data\n  - Privacy\n  - Compliance\n  - S3\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: macie\n    baseUri: https://macie2.amazonaws.com\n    description: Amazon Macie 2 REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: AWS4-HMAC-SHA256 {{AWS_ACCESS_KEY_ID}}\n      placement: header\n    resources:\n    - name: findings\n      path: /findings\n      description: Manage sensitive data findings\n      operations:\n\
  \      - name: list-findings\n        method: GET\n        description: List findings for the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-findings\n        method: POST\n        description: Get details for specific findings\n        inputParameters:\n        - name: findingIds\n          in: body\n          type: array\n          required: true\n          description: List of finding IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: classification-jobs\n      path: /jobs\n      description: Manage sensitive data discovery jobs\n      operations:\n      - name: create-classification-job\n        method: POST\n        description: Create a sensitive data discovery job\n        inputParameters:\n        - name: body\n          in: body\n          type: object\n          required: true\n\
  \          description: Job configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-classification-jobs\n        method: GET\n        description: List classification jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-classification-job\n        method: GET\n        description: Get details of a classification job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: Job ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: buckets\n      path: /datasources/s3\n      description: Manage monitored S3 buckets\n      operations:\n      - name: describe-buckets\n        method: POST\n        description: Get\
  \ details of monitored S3 buckets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: custom-data-identifiers\n      path: /custom-data-identifiers\n      description: Manage custom sensitive data identifiers\n      operations:\n      - name: create-custom-data-identifier\n        method: POST\n        description: Create a custom data identifier\n        inputParameters:\n        - name: body\n          in: body\n          type: object\n          required: true\n          description: Custom identifier configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-custom-data-identifiers\n        method: GET\n        description: List custom data identifiers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type:\
  \ rest\n    port: 8080\n    namespace: data-security-api\n    description: Unified REST API for Amazon Macie data security operations.\n    resources:\n    - path: /v1/findings\n      name: findings\n      description: Sensitive data findings\n      operations:\n      - method: GET\n        name: list-findings\n        description: List sensitive data findings\n        call: macie.list-findings\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: get-findings\n        description: Get finding details\n        call: macie.get-findings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description: Data discovery jobs\n      operations:\n      - method: POST\n        name: create-job\n        description: Create a data discovery job\n        call: macie.create-classification-job\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method:\
  \ GET\n        name: list-jobs\n        description: List all discovery jobs\n        call: macie.list-classification-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets\n      name: buckets\n      description: Monitored S3 buckets\n      operations:\n      - method: GET\n        name: describe-buckets\n        description: Get bucket security details\n        call: macie.describe-buckets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/identifiers\n      name: identifiers\n      description: Custom data identifiers\n      operations:\n      - method: POST\n        name: create-identifier\n        description: Create custom data identifier\n        call: macie.create-custom-data-identifier\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-identifiers\n        description: List custom identifiers\n        call: macie.list-custom-data-identifiers\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: data-security-mcp\n    transport: http\n    description: MCP server for AI-assisted data security operations with Amazon Macie.\n    tools:\n    - name: list-sensitive-data-findings\n      description: List all sensitive data findings detected by Macie\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macie.list-findings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-finding-details\n      description: Get detailed information about specific sensitive data findings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macie.get-findings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-discovery-job\n      description: Create a job to discover sensitive data in S3 buckets\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: macie.create-classification-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-discovery-jobs\n      description: List all sensitive data discovery jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macie.list-classification-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bucket-security-posture\n      description: Get security details and sensitive data statistics for monitored S3 buckets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macie.describe-buckets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-custom-data-identifier\n      description: Create a custom pattern to detect organization-specific sensitive data types\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: macie.create-custom-data-identifier\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-custom-identifiers\n      description: List all custom sensitive data identifiers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macie.list-custom-data-identifiers\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
