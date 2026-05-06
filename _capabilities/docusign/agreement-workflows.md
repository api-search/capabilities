---
categories: []
consumed_apis: []
description: Unified workflow for managing the full agreement lifecycle using DocuSign eSignature APIs, combining envelope management, document handling, templates, and signing workflows for business users and developers.
layout: capability
name: DocuSign Agreement Workflows
operations:
- description: List envelopes
  method: GET
  name: list-envelopes
  path: /v1/envelopes
- description: Create and send an envelope
  method: POST
  name: create-envelope
  path: /v1/envelopes
- description: Retrieve envelope details
  method: GET
  name: get-envelope
  path: /v1/envelopes/{envelopeId}
- description: List templates
  method: GET
  name: list-templates
  path: /v1/templates
personas: []
provider_name: Docusign
provider_slug: docusign
search_terms:
- individual envelope operations
- digital transaction management
- agreements
- list templates
- create and send an envelope
- get envelope
- create envelope
- retrieve envelope details
- docusign
- list available agreement templates
- retrieve details of a specific envelope
- list envelopes
- workflows
- create and optionally send an agreement envelope
- esignature
- envelope lifecycle management
- documents
- list envelopes in the docusign account
- electronic signatures
- template management
- contracts
slug: agreement-workflows
source_filename: agreement-workflows.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: DocuSign Agreement Workflows\n  description: Unified workflow for managing the full agreement lifecycle using DocuSign eSignature APIs, combining envelope\n    management, document handling, templates, and signing workflows for business users and developers.\n  tags:\n  - DocuSign\n  - Agreements\n  - eSignature\n  - Workflows\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    DOCUSIGN_ACCESS_TOKEN: DOCUSIGN_ACCESS_TOKEN\n    DOCUSIGN_ACCOUNT_ID: DOCUSIGN_ACCOUNT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: esignature\n    baseUri: https://demo.docusign.net/restapi/v2.1\n    description: DocuSign eSignature REST API\n    authentication:\n      type: bearer\n      token: '{{DOCUSIGN_ACCESS_TOKEN}}'\n    resources:\n    - name: envelopes\n      path: /accounts/{accountId}/envelopes\n      description: Envelope management\n      operations:\n      - name: list-envelopes\n        method:\
  \ GET\n        description: List envelopes\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account ID\n        - name: from_date\n          in: query\n          type: string\n          required: false\n          description: Start date for envelope search\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-envelope\n        method: POST\n        description: Create and send an envelope\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            emailSubject: '{{tools.emailSubject}}'\n            status: '{{tools.status}}'\n\
  \    - name: envelope\n      path: /accounts/{accountId}/envelopes/{envelopeId}\n      description: Individual envelope operations\n      operations:\n      - name: get-envelope\n        method: GET\n        description: Retrieve an envelope\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account ID\n        - name: envelopeId\n          in: path\n          type: string\n          required: true\n          description: Envelope ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates\n      path: /accounts/{accountId}/templates\n      description: Template management\n      operations:\n      - name: list-templates\n        method: GET\n        description: List templates\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n\
  \          description: Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: agreement-workflows-api\n    description: Unified REST API for DocuSign agreement workflows.\n    resources:\n    - path: /v1/envelopes\n      name: envelopes\n      description: Envelope lifecycle management\n      operations:\n      - method: GET\n        name: list-envelopes\n        description: List envelopes\n        call: esignature.list-envelopes\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-envelope\n        description: Create and send an envelope\n        call: esignature.create-envelope\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/envelopes/{envelopeId}\n\
  \      name: envelope\n      description: Individual envelope operations\n      operations:\n      - method: GET\n        name: get-envelope\n        description: Retrieve envelope details\n        call: esignature.get-envelope\n        with:\n          accountId: rest.accountId\n          envelopeId: rest.envelopeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/templates\n      name: templates\n      description: Template management\n      operations:\n      - method: GET\n        name: list-templates\n        description: List templates\n        call: esignature.list-templates\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: agreement-workflows-mcp\n    transport: http\n    description: MCP server for AI-assisted DocuSign agreement management.\n    tools:\n    - name: list-envelopes\n      description: List envelopes\
  \ in the DocuSign account\n      hints:\n        readOnly: true\n        idempotent: true\n      call: esignature.list-envelopes\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-envelope\n      description: Retrieve details of a specific envelope\n      hints:\n        readOnly: true\n        idempotent: true\n      call: esignature.get-envelope\n      with:\n        accountId: tools.accountId\n        envelopeId: tools.envelopeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-envelope\n      description: Create and optionally send an agreement envelope\n      hints:\n        readOnly: false\n      call: esignature.create-envelope\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-templates\n      description: List available agreement templates\n      hints:\n        readOnly: true\n\
  \        idempotent: true\n      call: esignature.list-templates\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/docusign/refs/heads/main/capabilities/agreement-workflows.yaml
tags:
- DocuSign
- Agreements
- eSignature
- Workflows
tools:
- description: List envelopes in the DocuSign account
  hints:
    idempotent: true
    readOnly: true
  name: list-envelopes
- description: Retrieve details of a specific envelope
  hints:
    idempotent: true
    readOnly: true
  name: get-envelope
- description: Create and optionally send an agreement envelope
  hints:
    readOnly: false
  name: create-envelope
- description: List available agreement templates
  hints:
    idempotent: true
    readOnly: true
  name: list-templates
---
