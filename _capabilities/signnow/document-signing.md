---
categories: []
consumed_apis: []
description: Workflow capability for end-to-end electronic document signing using SignNow. Covers document preparation, template-based workflows, signature invitation, bulk signing, and envelope management for legal and business agreement workflows.
layout: capability
name: SignNow Document Signing
operations:
- description: List all documents with their signing status.
  method: GET
  name: list-documents
  path: /v1/documents
- description: Upload a PDF document to begin the signing workflow.
  method: POST
  name: upload-document
  path: /v1/documents
- description: Retrieve document details, fields, and current signing status.
  method: GET
  name: get-document
  path: /v1/documents/{id}
- description: Delete a document from the system.
  method: DELETE
  name: delete-document
  path: /v1/documents/{id}
- description: Download a document as a signed PDF.
  method: GET
  name: download-document
  path: /v1/documents/{id}/download
- description: Send signature invitations to one or more recipients.
  method: POST
  name: send-signature-invite
  path: /v1/documents/{id}/invite
- description: Cancel all pending signature invitations for a document.
  method: POST
  name: cancel-signature-invite
  path: /v1/documents/{id}/cancel-invite
- description: List all reusable document templates.
  method: GET
  name: list-templates
  path: /v1/templates
- description: Create a reusable template from an existing document.
  method: POST
  name: create-template
  path: /v1/templates
- description: Retrieve a specific template with its fields and roles.
  method: GET
  name: get-template
  path: /v1/templates/{id}
- description: Delete a document template.
  method: DELETE
  name: delete-template
  path: /v1/templates/{id}
- description: Send signature invitations to multiple recipients via CSV.
  method: POST
  name: send-bulk-invite
  path: /v1/templates/{id}/bulk-invite
- description: List all document group envelopes.
  method: GET
  name: list-envelopes
  path: /v1/envelopes
- description: Create a document group envelope for coordinated multi-document signing.
  method: POST
  name: create-envelope
  path: /v1/envelopes
- description: List all active webhook subscriptions.
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: Register a webhook to receive signing event notifications.
  method: POST
  name: create-webhook
  path: /v1/webhooks
- description: Retrieve the current user's profile and subscription information.
  method: GET
  name: get-current-user
  path: /v1/users/me
personas: []
provider_name: SignNow
provider_slug: signnow
search_terms:
- delete a document from the system.
- cancel pending signature invites.
- retrieve a specific template with its fields and roles.
- contract management
- document template management.
- retrieve a specific document template with its signing fields and roles.
- cancel all pending signature invitations for a document.
- list all available document templates for e-signature workflows.
- document management
- workflow automation
- permanently delete a document from signnow.
- delete a document template.
- list templates
- create a document group envelope for coordinated multi-document signing.
- current user profile.
- create a reusable e-signature template from an existing document.
- create a document group envelope to coordinate signing across multiple documents.
- download a document as a signed pdf.
- list all active webhook event subscriptions.
- delete a document template from signnow.
- list all document group envelopes for coordinated multi-document signing.
- send e-signature invitations to one or more recipients for a document.
- list all documents with their signing status.
- download a completed signed document as a pdf.
- create webhook
- get document
- create template
- document lifecycle management.
- retrieve full details of a specific document including its fields and signing status.
- upload document
- retrieve document details, fields, and current signing status.
- document download.
- send signature invite
- list envelopes
- list all reusable document templates.
- bulk signature invitation.
- register a webhook to receive signing event notifications.
- signature invitation management.
- get envelope
- create a reusable template from an existing document.
- document group envelope management.
- delete template
- single template operations.
- list webhooks
- send signature invitations to multiple recipients via csv.
- register a webhook to receive notifications when document signing events occur.
- document signing
- send bulk invite
- retrieve details of a specific document group envelope.
- list all document group envelopes.
- webhook event subscription management.
- download document
- upload a pdf document to begin the signing workflow.
- get current user
- list documents
- create envelope
- list all e-signature documents and their current signing status.
- send e-signature invitations to multiple recipients using a csv file and template.
- e-signature
- legal
- retrieve the current user's profile and subscription information.
- electronic signature
- delete document
- get template
- list all active webhook subscriptions.
- single document operations.
- cancel signature invite
- retrieve current user profile, subscription details, and usage information.
- upload a pdf document to begin an e-signature workflow.
- send signature invitations to one or more recipients.
slug: document-signing
source_filename: document-signing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SignNow Document Signing\n  description: Workflow capability for end-to-end electronic document signing using SignNow. Covers document preparation,\n    template-based workflows, signature invitation, bulk signing, and envelope management for legal and business agreement\n    workflows.\n  tags:\n  - E-Signature\n  - Document Signing\n  - Contract Management\n  - Workflow Automation\n  - Legal\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SIGNNOW_ACCESS_TOKEN: SIGNNOW_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: signnow\n    baseUri: https://api.signnow.com\n    description: SignNow REST API for e-signature workflows and document management.\n    authentication:\n      type: bearer\n      token: '{{SIGNNOW_ACCESS_TOKEN}}'\n    resources:\n    - name: documents\n      path: /document\n      description: Document upload and management operations.\n      operations:\n\
  \      - name: list-documents\n        method: GET\n        description: List all documents for the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: upload-document\n        method: POST\n        description: Upload a PDF document for e-signature processing.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: document\n      path: /document/{document_id}\n      description: Single document operations.\n      operations:\n      - name: get-document\n        method: GET\n        description: Retrieve document details including fields, signers, and status.\n        inputParameters:\n        - name: document_id\n          in: path\n          type: string\n          required: true\n          description: Unique document identifier.\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n      - name: delete-document\n        method: DELETE\n        description: Permanently delete a document.\n        inputParameters:\n        - name: document_id\n          in: path\n          type: string\n          required: true\n          description: Unique document identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: document-download\n      path: /document/{document_id}/download\n      description: Document download operations.\n      operations:\n      - name: download-document\n        method: GET\n        description: Download a signed document as PDF.\n        inputParameters:\n        - name: document_id\n          in: path\n          type: string\n          required: true\n          description: Unique document identifier.\n        - name: type\n          in: query\n          type: string\n          required:\
  \ false\n          description: 'Download type: collapsed or with_history.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: signature-invite\n      path: /document/{document_id}/invite\n      description: Signature invitation operations.\n      operations:\n      - name: send-signature-invite\n        method: POST\n        description: Send a signature invitation to one or more recipients.\n        inputParameters:\n        - name: document_id\n          in: path\n          type: string\n          required: true\n          description: Unique document identifier.\n        body:\n          type: json\n          data:\n            from: '{{tools.from_email}}'\n            to: '{{tools.recipients}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cancel-invite\n      path: /document/{document_id}/fieldinvitecancel\n\
  \      description: Cancel signature invite operations.\n      operations:\n      - name: cancel-signature-invite\n        method: PUT\n        description: Cancel all pending signature invitations for a document.\n        inputParameters:\n        - name: document_id\n          in: path\n          type: string\n          required: true\n          description: Unique document identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates\n      path: /template\n      description: Template management operations.\n      operations:\n      - name: list-templates\n        method: GET\n        description: List all document templates.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-template\n        method: POST\n        description: Create a new reusable document template.\n        body:\n    \
  \      type: json\n          data:\n            document_id: '{{tools.document_id}}'\n            document_name: '{{tools.document_name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: template\n      path: /template/{template_id}\n      description: Single template operations.\n      operations:\n      - name: get-template\n        method: GET\n        description: Retrieve details of a specific document template.\n        inputParameters:\n        - name: template_id\n          in: path\n          type: string\n          required: true\n          description: Unique template identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-template\n        method: DELETE\n        description: Delete a document template.\n        inputParameters:\n        - name: template_id\n          in: path\n \
  \         type: string\n          required: true\n          description: Unique template identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bulk-invite\n      path: /template/{template_id}/bulkinvite\n      description: Bulk invitation operations.\n      operations:\n      - name: send-bulk-invite\n        method: POST\n        description: Send signature invitations to multiple recipients using CSV.\n        inputParameters:\n        - name: template_id\n          in: path\n          type: string\n          required: true\n          description: Unique template identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /user\n      description: User management operations.\n      operations:\n      - name: create-user\n        method: POST\n        description: Create a new SignNow\
  \ user account.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            password: '{{tools.password}}'\n            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: current-user\n      path: /user/me\n      description: Current user profile operations.\n      operations:\n      - name: get-current-user\n        method: GET\n        description: Retrieve the profile of the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /api/events\n      description: Webhook subscription management.\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List all registered webhook subscriptions.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Register a new webhook event subscription.\n        body:\n          type: json\n          data:\n            event: '{{tools.event}}'\n            action: '{{tools.callback_url}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: envelopes\n      path: /documentgroup\n      description: Document group envelope operations.\n      operations:\n      - name: list-envelopes\n        method: GET\n        description: List all document group envelopes.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-envelope\n        method: POST\n        description: Create a new document group envelope.\n        body:\n          type: json\n    \
  \      data:\n            document_ids: '{{tools.document_ids}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: document-signing-api\n    description: Unified REST API for end-to-end electronic document signing workflows.\n    resources:\n    - path: /v1/documents\n      name: documents\n      description: Document lifecycle management.\n      operations:\n      - method: GET\n        name: list-documents\n        description: List all documents with their signing status.\n        call: signnow.list-documents\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: upload-document\n        description: Upload a PDF document to begin the signing workflow.\n        call: signnow.upload-document\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents/{id}\n\
  \      name: document\n      description: Single document operations.\n      operations:\n      - method: GET\n        name: get-document\n        description: Retrieve document details, fields, and current signing status.\n        call: signnow.get-document\n        with:\n          document_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-document\n        description: Delete a document from the system.\n        call: signnow.delete-document\n        with:\n          document_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents/{id}/download\n      name: document-download\n      description: Document download.\n      operations:\n      - method: GET\n        name: download-document\n        description: Download a document as a signed PDF.\n        call: signnow.download-document\n        with:\n          document_id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/documents/{id}/invite\n      name: signature-invite\n      description: Signature invitation management.\n      operations:\n      - method: POST\n        name: send-signature-invite\n        description: Send signature invitations to one or more recipients.\n        call: signnow.send-signature-invite\n        with:\n          document_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents/{id}/cancel-invite\n      name: cancel-invite\n      description: Cancel pending signature invites.\n      operations:\n      - method: POST\n        name: cancel-signature-invite\n        description: Cancel all pending signature invitations for a document.\n        call: signnow.cancel-signature-invite\n        with:\n          document_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/templates\n      name: templates\n     \
  \ description: Document template management.\n      operations:\n      - method: GET\n        name: list-templates\n        description: List all reusable document templates.\n        call: signnow.list-templates\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-template\n        description: Create a reusable template from an existing document.\n        call: signnow.create-template\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/templates/{id}\n      name: template\n      description: Single template operations.\n      operations:\n      - method: GET\n        name: get-template\n        description: Retrieve a specific template with its fields and roles.\n        call: signnow.get-template\n        with:\n          template_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-template\n        description:\
  \ Delete a document template.\n        call: signnow.delete-template\n        with:\n          template_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/templates/{id}/bulk-invite\n      name: bulk-invite\n      description: Bulk signature invitation.\n      operations:\n      - method: POST\n        name: send-bulk-invite\n        description: Send signature invitations to multiple recipients via CSV.\n        call: signnow.send-bulk-invite\n        with:\n          template_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/envelopes\n      name: envelopes\n      description: Document group envelope management.\n      operations:\n      - method: GET\n        name: list-envelopes\n        description: List all document group envelopes.\n        call: signnow.list-envelopes\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name:\
  \ create-envelope\n        description: Create a document group envelope for coordinated multi-document signing.\n        call: signnow.create-envelope\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhooks\n      name: webhooks\n      description: Webhook event subscription management.\n      operations:\n      - method: GET\n        name: list-webhooks\n        description: List all active webhook subscriptions.\n        call: signnow.list-webhooks\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-webhook\n        description: Register a webhook to receive signing event notifications.\n        call: signnow.create-webhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/me\n      name: current-user\n      description: Current user profile.\n      operations:\n      - method: GET\n        name: get-current-user\n        description:\
  \ Retrieve the current user's profile and subscription information.\n        call: signnow.get-current-user\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: document-signing-mcp\n    transport: http\n    description: MCP server for AI-assisted electronic document signing and workflow management.\n    tools:\n    - name: list-documents\n      description: List all e-signature documents and their current signing status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: signnow.list-documents\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: upload-document\n      description: Upload a PDF document to begin an e-signature workflow.\n      hints:\n        readOnly: false\n      call: signnow.upload-document\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-document\n      description: Retrieve full details of a specific document\
  \ including its fields and signing status.\n      hints:\n        readOnly: true\n      call: signnow.get-document\n      with:\n        document_id: tools.document_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-document\n      description: Permanently delete a document from SignNow.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: signnow.delete-document\n      with:\n        document_id: tools.document_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: download-document\n      description: Download a completed signed document as a PDF.\n      hints:\n        readOnly: true\n      call: signnow.download-document\n      with:\n        document_id: tools.document_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-signature-invite\n      description: Send e-signature invitations to one or more recipients for a document.\n\
  \      hints:\n        readOnly: false\n      call: signnow.send-signature-invite\n      with:\n        document_id: tools.document_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-signature-invite\n      description: Cancel all pending signature invitations for a document.\n      hints:\n        readOnly: false\n        destructive: false\n      call: signnow.cancel-signature-invite\n      with:\n        document_id: tools.document_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-templates\n      description: List all available document templates for e-signature workflows.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: signnow.list-templates\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-template\n      description: Retrieve a specific document template with its signing fields and roles.\n      hints:\n        readOnly: true\n      call: signnow.get-template\n\
  \      with:\n        template_id: tools.template_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-template\n      description: Create a reusable e-signature template from an existing document.\n      hints:\n        readOnly: false\n      call: signnow.create-template\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-template\n      description: Delete a document template from SignNow.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: signnow.delete-template\n      with:\n        template_id: tools.template_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-bulk-invite\n      description: Send e-signature invitations to multiple recipients using a CSV file and template.\n      hints:\n        readOnly: false\n      call: signnow.send-bulk-invite\n      with:\n        template_id: tools.template_id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-envelopes\n      description: List all document group envelopes for coordinated multi-document signing.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: signnow.list-envelopes\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-envelope\n      description: Create a document group envelope to coordinate signing across multiple documents.\n      hints:\n        readOnly: false\n      call: signnow.create-envelope\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-envelope\n      description: Retrieve details of a specific document group envelope.\n      hints:\n        readOnly: true\n      call: signnow.get-envelope\n      with:\n        group_id: tools.group_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-webhooks\n      description: List all active webhook event subscriptions.\n      hints:\n\
  \        readOnly: true\n      call: signnow.list-webhooks\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-webhook\n      description: Register a webhook to receive notifications when document signing events occur.\n      hints:\n        readOnly: false\n      call: signnow.create-webhook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-current-user\n      description: Retrieve current user profile, subscription details, and usage information.\n      hints:\n        readOnly: true\n      call: signnow.get-current-user\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/signnow/refs/heads/main/capabilities/document-signing.yaml
tags:
- E-Signature
- Document Signing
- Contract Management
- Workflow Automation
- Legal
tools:
- description: List all e-signature documents and their current signing status.
  hints:
    openWorld: true
    readOnly: true
  name: list-documents
- description: Upload a PDF document to begin an e-signature workflow.
  hints:
    readOnly: false
  name: upload-document
- description: Retrieve full details of a specific document including its fields and signing status.
  hints:
    readOnly: true
  name: get-document
- description: Permanently delete a document from SignNow.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-document
- description: Download a completed signed document as a PDF.
  hints:
    readOnly: true
  name: download-document
- description: Send e-signature invitations to one or more recipients for a document.
  hints:
    readOnly: false
  name: send-signature-invite
- description: Cancel all pending signature invitations for a document.
  hints:
    destructive: false
    readOnly: false
  name: cancel-signature-invite
- description: List all available document templates for e-signature workflows.
  hints:
    openWorld: true
    readOnly: true
  name: list-templates
- description: Retrieve a specific document template with its signing fields and roles.
  hints:
    readOnly: true
  name: get-template
- description: Create a reusable e-signature template from an existing document.
  hints:
    readOnly: false
  name: create-template
- description: Delete a document template from SignNow.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-template
- description: Send e-signature invitations to multiple recipients using a CSV file and template.
  hints:
    readOnly: false
  name: send-bulk-invite
- description: List all document group envelopes for coordinated multi-document signing.
  hints:
    openWorld: true
    readOnly: true
  name: list-envelopes
- description: Create a document group envelope to coordinate signing across multiple documents.
  hints:
    readOnly: false
  name: create-envelope
- description: Retrieve details of a specific document group envelope.
  hints:
    readOnly: true
  name: get-envelope
- description: List all active webhook event subscriptions.
  hints:
    readOnly: true
  name: list-webhooks
- description: Register a webhook to receive notifications when document signing events occur.
  hints:
    readOnly: false
  name: create-webhook
- description: Retrieve current user profile, subscription details, and usage information.
  hints:
    readOnly: true
  name: get-current-user
---
