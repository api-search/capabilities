---
categories:
- security
consumed_apis:
- amazon-security-lake
description: Unified capability for managing a centralized security data lake including data lake configuration, log source ingestion, and subscriber access management. Used by Security Data Engineers and CISO teams.
layout: capability
name: Amazon Security Lake Security Data Lake
operations:
- description: List all security data lake configurations
  method: GET
  name: list-data-lakes
  path: /v1/data-lakes
- description: Create a new security data lake
  method: POST
  name: create-data-lake
  path: /v1/data-lakes
- description: List all configured log sources
  method: GET
  name: list-log-sources
  path: /v1/log-sources
- description: Add a native AWS log source
  method: POST
  name: add-aws-log-source
  path: /v1/log-sources
- description: List all data lake subscribers
  method: GET
  name: list-subscribers
  path: /v1/subscribers
- description: Create a new subscriber for data access
  method: POST
  name: create-subscriber
  path: /v1/subscribers
personas: []
provider_name: Amazon Security Lake
provider_slug: amazon-security-lake
search_terms:
- list log sources
- data lake
- security log source management
- list all security lake data subscribers
- add aws log source
- create a new subscriber for data access
- delete a security lake subscriber
- CISO
- create data lake
- list all security data lake configurations
- list all data lake subscribers
- delete subscriber
- security data lake lifecycle management
- data lake infrastructure management and subscriber access control
- get subscriber
- get data lake source status across accounts and regions
- engineers who configure and manage security data lakes, log sources, and subscriber access
- list all log sources configured in security lake
- aws
- enable a native aws log source in security lake
- create a subscriber for security lake data access
- add custom log source
- get data lake sources
- list all configured log sources
- security data centralization and threat analysis
- amazon security lake
- data subscriber access management
- list all amazon security lake data lake configurations
- create a new security data lake
- create a new amazon security lake data lake
- Security Data Engineer
- siem
- centralized security data lake lifecycle including data lake configuration, log source management, and subscriber access
- add a custom third-party log source to security lake
- security
- ocsf
- add a native aws log source
- list subscribers
- get details about a specific security lake subscriber
- threat detection
- security leaders who consume security data for threat intelligence and compliance reporting
- list data lakes
- create subscriber
slug: security-data-lake
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Security Lake Security Data Lake\"\n  description: \"Unified capability for managing a centralized security data lake including data lake configuration, log source ingestion, and subscriber access management. Used by Security Data Engineers and CISO teams.\"\n  tags:\n    - Amazon Security Lake\n    - Security\n    - Data Lake\n    - SIEM\n    - OCSF\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-security-lake\n      location: ./shared/amazon-security-lake.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: security-data-lake-api\n      description: \"Unified REST API for Amazon Security Lake security data lake management.\"\n      resources:\n        - path: /v1/data-lakes\n   \
  \       name: data-lakes\n          description: \"Security data lake lifecycle management\"\n          operations:\n            - method: GET\n              name: list-data-lakes\n              description: \"List all security data lake configurations\"\n              call: \"amazon-security-lake.list-data-lakes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-data-lake\n              description: \"Create a new security data lake\"\n              call: \"amazon-security-lake.create-data-lake\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/log-sources\n          name: log-sources\n          description: \"Security log source management\"\n          operations:\n            - method: GET\n              name: list-log-sources\n              description: \"List all configured log sources\"\n              call:\
  \ \"amazon-security-lake.list-log-sources\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-aws-log-source\n              description: \"Add a native AWS log source\"\n              call: \"amazon-security-lake.create-aws-log-source\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subscribers\n          name: subscribers\n          description: \"Data subscriber access management\"\n          operations:\n            - method: GET\n              name: list-subscribers\n              description: \"List all data lake subscribers\"\n              call: \"amazon-security-lake.list-subscribers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-subscriber\n              description: \"Create a new subscriber for\
  \ data access\"\n              call: \"amazon-security-lake.create-subscriber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: security-data-lake-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon Security Lake security data lake management.\"\n      tools:\n        - name: list-data-lakes\n          description: \"List all Amazon Security Lake data lake configurations\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-security-lake.list-data-lakes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-data-lake\n          description: \"Create a new Amazon Security Lake data lake\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-security-lake.create-data-lake\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-data-lake-sources\n          description: \"Get data lake source status across accounts and regions\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-security-lake.get-data-lake-sources\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-log-sources\n          description: \"List all log sources configured in Security Lake\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-security-lake.list-log-sources\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-aws-log-source\n          description: \"Enable a native AWS log source in Security Lake\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-security-lake.create-aws-log-source\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-custom-log-source\n          description: \"Add a custom third-party log source to Security Lake\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-security-lake.create-custom-log-source\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-subscribers\n          description: \"List all Security Lake data subscribers\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-security-lake.list-subscribers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-subscriber\n          description: \"Create a subscriber for Security Lake data access\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-security-lake.create-subscriber\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-subscriber\n          description: \"Get details about a specific Security Lake subscriber\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-security-lake.get-subscriber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-subscriber\n          description: \"Delete a Security Lake subscriber\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"amazon-security-lake.delete-subscriber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-security-lake/refs/heads/main/capabilities/security-data-lake.yaml
tags:
- Amazon Security Lake
- Security
- Data Lake
- SIEM
- OCSF
tools:
- description: List all Amazon Security Lake data lake configurations
  hints:
    idempotent: true
    readOnly: true
  name: list-data-lakes
- description: Create a new Amazon Security Lake data lake
  hints:
    idempotent: false
    readOnly: false
  name: create-data-lake
- description: Get data lake source status across accounts and regions
  hints:
    idempotent: true
    readOnly: true
  name: get-data-lake-sources
- description: List all log sources configured in Security Lake
  hints:
    idempotent: true
    readOnly: true
  name: list-log-sources
- description: Enable a native AWS log source in Security Lake
  hints:
    idempotent: false
    readOnly: false
  name: add-aws-log-source
- description: Add a custom third-party log source to Security Lake
  hints:
    idempotent: false
    readOnly: false
  name: add-custom-log-source
- description: List all Security Lake data subscribers
  hints:
    idempotent: true
    readOnly: true
  name: list-subscribers
- description: Create a subscriber for Security Lake data access
  hints:
    idempotent: false
    readOnly: false
  name: create-subscriber
- description: Get details about a specific Security Lake subscriber
  hints:
    idempotent: true
    readOnly: true
  name: get-subscriber
- description: Delete a Security Lake subscriber
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-subscriber
---
