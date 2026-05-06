---
categories: []
consumed_apis: []
description: Workflow capability for Amazon Ses. Enables automation of Amazon Ses resources for cloud operations teams.
layout: capability
name: Amazon Ses Operations
operations:
- description: List Amazon Ses resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon SES
provider_slug: amazon-ses
search_terms:
- list resources
- email
- aws
- email deliverability
- smtp
- notifications
- engineer managing amazon ses resources
- aws cloud resource management
- cloud operations
- automation workflow for amazon ses
- transactional email
- email service
- amazon ses
- amazon ses resources
- marketing email
- list amazon ses resources
slug: amazon-ses
source_filename: amazon-ses.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Ses Operations\n  description: Workflow capability for Amazon Ses. Enables automation of Amazon Ses resources for cloud operations teams.\n  tags:\n  - Amazon Ses\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-ses\n    baseUri: https://email.amazonaws.com\n    description: Amazon SES Amazon Simple Email Service (SES)\n    authentication:\n      type: bearer\n      token: '{{AWS_ACCESS_KEY}}'\n    resources:\n    - name: v2\n      path: /v2/email/outbound-emails\n      description: v2 operations\n      operations:\n      - name: SendEmail\n        method: POST\n        description: Amazon SES Send Email\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: ListEmailIdentities\n        method: GET\n        description: Amazon SES List Email Identities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreateEmailIdentity\n        method: POST\n        description: Amazon SES Create Email Identity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: GetEmailIdentity\n        method: GET\n        description: Amazon SES Get Email Identity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreateContactList\n        method: POST\n        description: Amazon SES Create Contact List\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreateEmailTemplate\n        method: POST\n\
  \        description: Amazon SES Create Email Template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-ses-api\n    description: Unified REST API for Amazon Ses operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon Ses resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Ses resources\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-ses-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Ses operations.\n    tools:\n    - name: list-amazon-ses-resources\n      description: List Amazon Ses resources\n      hints:\n        readOnly: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-ses/refs/heads/main/capabilities/amazon-ses.yaml
tags:
- Amazon Ses
- Cloud Operations
tools:
- description: List Amazon Ses resources
  hints:
    readOnly: true
  name: list-amazon-ses-resources
---
