---
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
- get bucket security details
- list sensitive data findings
- create a custom pattern to detect organization-specific sensitive data types
- data security
- list all discovery jobs
- managing and investigating sensitive data findings
- get bucket security posture
- machine learning
- compliance
- get finding details
- get security details and sensitive data statistics for monitored s3 buckets
- Compliance Officer
- get detailed information about specific sensitive data findings
- list all sensitive data findings detected by macie
- Security Engineer
- create a data discovery job
- s3
- list jobs
- sensitive data findings
- custom data identifiers
- create job
- sensitive data
- list custom identifiers
- monitored s3 buckets
- manages macie configuration, discovery jobs, and investigates sensitive data findings
- create discovery job
- list discovery jobs
- privacy
- list findings
- create identifier
- amazon
- data discovery jobs
- list identifiers
- list all sensitive data discovery jobs
- get findings
- list all custom sensitive data identifiers
- aws
- create a job to discover sensitive data in s3 buckets
- workflow for discovering sensitive data, investigating findings, and managing data security posture
- automated discovery and classification of sensitive data in s3
- custom patterns for identifying organization-specific sensitive data
- create custom data identifier
- reviews sensitive data findings to ensure data governance and regulatory compliance
- describe buckets
slug: data-security-operations
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
