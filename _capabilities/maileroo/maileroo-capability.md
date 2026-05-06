---
categories: []
consumed_apis: []
description: The Maileroo REST API allows sending transactional and marketing emails via JSON requests with high deliverability. Supports HTML and plain text emails, attachments, tracking, templates, scheduled delivery, and bulk sending. All requests are authenticated via an API sending key passed in the X-Api-Key header or as a Bearer token in the Authorization header.
layout: capability
name: Maileroo Email API
operations:
- description: Send a basic email
  method: POST
  name: sendbasicemail
  path: /emails
- description: Send a templated email
  method: POST
  name: sendtemplatedemail
  path: /emails/template
- description: Send bulk emails
  method: POST
  name: sendbulkemails
  path: /emails/bulk
- description: List scheduled emails
  method: GET
  name: listscheduledemails
  path: /emails/scheduled
- description: Delete a scheduled email
  method: DELETE
  name: deletescheduledemail
  path: /emails/scheduled/{reference_id}
personas: []
provider_name: Maileroo
provider_slug: maileroo
search_terms:
- send a templated email
- sendbulkemails
- email
- transactional email
- sendbasicemail
- smtp
- maileroo
- send bulk emails
- api
- delete a scheduled email
- listscheduledemails
- sendtemplatedemail
- deletescheduledemail
- email delivery
- list scheduled emails
- send a basic email
- marketing email
slug: maileroo-capability
source_filename: maileroo-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Maileroo Email API\n  description: The Maileroo REST API allows sending transactional and marketing emails via JSON requests with high deliverability.\n    Supports HTML and plain text emails, attachments, tracking, templates, scheduled delivery, and bulk sending. All requests\n    are authenticated via an API sending key passed in the X-Api-Key header or as a Bearer token in the Authorization header.\n  tags:\n  - Maileroo\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: maileroo\n    baseUri: https://smtp.maileroo.com/api/v2\n    description: Maileroo Email API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Api-Key\n      value: '{{MAILEROO_TOKEN}}'\n    resources:\n    - name: emails\n      path: /emails\n      operations:\n      - name: sendbasicemail\n        method: POST\n        description: Send a basic email\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: emails-template\n      path: /emails/template\n      operations:\n      - name: sendtemplatedemail\n        method: POST\n        description: Send a templated email\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: emails-bulk\n      path: /emails/bulk\n      operations:\n      - name: sendbulkemails\n        method: POST\n        description: Send bulk emails\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: emails-scheduled\n      path: /emails/scheduled\n      operations:\n      - name: listscheduledemails\n        method: GET\n        description: List scheduled emails\n        inputParameters:\n        - name: domain\n          in: query\n          type: string\n          description: Sender\
  \ domain (required for app-scoped API keys)\n        - name: page\n          in: query\n          type: integer\n        - name: per_page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: emails-scheduled-reference-id\n      path: /emails/scheduled/{reference_id}\n      operations:\n      - name: deletescheduledemail\n        method: DELETE\n        description: Delete a scheduled email\n        inputParameters:\n        - name: reference_id\n          in: path\n          type: string\n          required: true\n          description: The 24-character hex reference ID of the scheduled email\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: maileroo-rest\n    description: REST adapter for Maileroo Email API.\n    resources:\n\
  \    - path: /emails\n      name: sendbasicemail\n      operations:\n      - method: POST\n        name: sendbasicemail\n        description: Send a basic email\n        call: maileroo.sendbasicemail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /emails/template\n      name: sendtemplatedemail\n      operations:\n      - method: POST\n        name: sendtemplatedemail\n        description: Send a templated email\n        call: maileroo.sendtemplatedemail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /emails/bulk\n      name: sendbulkemails\n      operations:\n      - method: POST\n        name: sendbulkemails\n        description: Send bulk emails\n        call: maileroo.sendbulkemails\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /emails/scheduled\n      name: listscheduledemails\n      operations:\n      - method: GET\n        name: listscheduledemails\n        description:\
  \ List scheduled emails\n        call: maileroo.listscheduledemails\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /emails/scheduled/{reference_id}\n      name: deletescheduledemail\n      operations:\n      - method: DELETE\n        name: deletescheduledemail\n        description: Delete a scheduled email\n        call: maileroo.deletescheduledemail\n        with:\n          reference_id: rest.reference_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: maileroo-mcp\n    transport: http\n    description: MCP adapter for Maileroo Email API for AI agent use.\n    tools:\n    - name: sendbasicemail\n      description: Send a basic email\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: maileroo.sendbasicemail\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendtemplatedemail\n      description:\
  \ Send a templated email\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: maileroo.sendtemplatedemail\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendbulkemails\n      description: Send bulk emails\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: maileroo.sendbulkemails\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listscheduledemails\n      description: List scheduled emails\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: maileroo.listscheduledemails\n      with:\n        domain: tools.domain\n        page: tools.page\n        per_page: tools.per_page\n      inputParameters:\n      - name: domain\n        type: string\n        description: Sender domain (required for app-scoped API keys)\n      - name: page\n        type: integer\n        description:\
  \ page\n      - name: per_page\n        type: integer\n        description: per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletescheduledemail\n      description: Delete a scheduled email\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: maileroo.deletescheduledemail\n      with:\n        reference_id: tools.reference_id\n      inputParameters:\n      - name: reference_id\n        type: string\n        description: The 24-character hex reference ID of the scheduled email\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MAILEROO_TOKEN: MAILEROO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/maileroo/refs/heads/main/capabilities/maileroo-capability.yaml
tags:
- Maileroo
- API
tools:
- description: Send a basic email
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendbasicemail
- description: Send a templated email
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendtemplatedemail
- description: Send bulk emails
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendbulkemails
- description: List scheduled emails
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listscheduledemails
- description: Delete a scheduled email
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletescheduledemail
---
