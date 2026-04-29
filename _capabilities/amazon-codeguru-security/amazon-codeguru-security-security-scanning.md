---
categories:
- security
consumed_apis:
- codegurusecurity
description: Unified workflow for security and DevOps teams to create security scans, retrieve findings, track vulnerabilities by severity, and manage remediation using Amazon CodeGuru Security.
layout: capability
name: Amazon CodeGuru Security Application Security Scanning
operations: []
personas: []
provider_name: Amazon CodeGuru Security
provider_slug: amazon-codeguru-security
search_terms:
- unified workflow for security and devops teams to create security scans, retrieve findings, track vulnerabilities by severity, and manage remediation
- list findings across all scans in the account
- list findings by account
- get security metrics summary
- sast
- list security scans
- list scans
- devsecops engineer persona.
- amazon
- developer persona.
- Security Engineer
- get security findings from a scan
- get scan
- create a new security scan
- DevSecOps Engineer
- get metrics summary
- get details about a security scan
- security engineer persona.
- create scan
- get details about multiple findings
- developer tools
- unified workflow for security and devops teams to create security scans, retrieve findings, track vu
- get findings
- security
- aws
- batch get findings
- Developer
- devsecops
- code analysis
slug: amazon-codeguru-security-security-scanning
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon CodeGuru Security Application Security Scanning\n  description: Unified workflow for security and DevOps teams to create security scans, retrieve findings, track vulnerabilities by severity, and manage remediation using Amazon CodeGuru Security.\n  tags:\n  - Amazon\n  - AWS\n  - Security\n  - SAST\n  - Code Analysis\n  - DevSecOps\n  - Developer Tools\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: codegurusecurity\n    location: ./shared/codegurusecurity.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: codegurusecurity-security-scanning-api\n    description: Unified REST API for Application Security Scanning.\n    resources:\n    - path: /v1/createScan\n      name: create-scan\n      description: Create a new security\
  \ scan\n    - path: /v1/getScan\n      name: get-scan\n      description: Get details about a security scan\n    - path: /v1/listScans\n      name: list-scans\n      description: List security scans\n    - path: /v1/getFindings\n      name: get-findings\n      description: Get security findings from a scan\n  - type: mcp\n    port: 9090\n    namespace: codegurusecurity-security-scanning-mcp\n    transport: http\n    description: MCP server for AI-assisted Application Security Scanning.\n    tools:\n    - name: create-scan\n      description: Create a new security scan\n      hints:\n        readOnly: false\n        openWorld: true\n      call: codegurusecurity.createScan\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-scan\n      description: Get details about a security scan\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codegurusecurity.getScan\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: list-scans\n      description: List security scans\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codegurusecurity.listScans\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-findings\n      description: Get security findings from a scan\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codegurusecurity.getFindings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-get-findings\n      description: Get details about multiple findings\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codegurusecurity.batchGetFindings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-metrics-summary\n      description: Get security metrics summary\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codegurusecurity.getMetricsSummary\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: list-findings-by-account\n      description: List findings across all scans in the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codegurusecurity.listFindingsByAccount\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-codeguru-security/refs/heads/main/capabilities/amazon-codeguru-security-security-scanning.yaml
tags:
- Amazon
- AWS
- Security
- SAST
- Code Analysis
- DevSecOps
- Developer Tools
tools:
- description: Create a new security scan
  hints:
    openWorld: true
    readOnly: false
  name: create-scan
- description: Get details about a security scan
  hints:
    openWorld: true
    readOnly: true
  name: get-scan
- description: List security scans
  hints:
    openWorld: true
    readOnly: true
  name: list-scans
- description: Get security findings from a scan
  hints:
    openWorld: true
    readOnly: true
  name: get-findings
- description: Get details about multiple findings
  hints:
    openWorld: true
    readOnly: true
  name: batch-get-findings
- description: Get security metrics summary
  hints:
    openWorld: true
    readOnly: true
  name: get-metrics-summary
- description: List findings across all scans in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-findings-by-account
---
