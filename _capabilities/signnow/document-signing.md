---
api_specs:
- filename: signnow-openapi.yml
  format: yaml
  label: signnow
  slug: signnow
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/signnow/refs/heads/main/openapi/signnow-openapi.yml
categories: []
consumed_apis:
- signnow
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
- retrieve full details of a specific document including its fields and signing status.
- document template management.
- e-signature
- list all active webhook subscriptions.
- list all available document templates for e-signature workflows.
- single document operations.
- retrieve a specific document template with its signing fields and roles.
- send signature invitations to multiple recipients via csv.
- delete a document template from signnow.
- list documents
- create template
- bulk signature invitation.
- list all document group envelopes.
- delete a document from the system.
- delete document
- cancel signature invite
- create webhook
- list all reusable document templates.
- retrieve document details, fields, and current signing status.
- create a document group envelope for coordinated multi-document signing.
- webhook event subscription management.
- delete a document template.
- send e-signature invitations to one or more recipients for a document.
- permanently delete a document from signnow.
- download document
- create a document group envelope to coordinate signing across multiple documents.
- document lifecycle management.
- create envelope
- signature invitation management.
- document download.
- list all active webhook event subscriptions.
- current user profile.
- get current user
- send e-signature invitations to multiple recipients using a csv file and template.
- send signature invite
- cancel pending signature invites.
- get document
- create a reusable template from an existing document.
- electronic signature
- list webhooks
- list all document group envelopes for coordinated multi-document signing.
- retrieve current user profile, subscription details, and usage information.
- upload document
- upload a pdf document to begin an e-signature workflow.
- get template
- list templates
- download a document as a signed pdf.
- legal
- upload a pdf document to begin the signing workflow.
- retrieve the current user's profile and subscription information.
- send signature invitations to one or more recipients.
- cancel all pending signature invitations for a document.
- document group envelope management.
- list all e-signature documents and their current signing status.
- get envelope
- register a webhook to receive notifications when document signing events occur.
- retrieve a specific template with its fields and roles.
- register a webhook to receive signing event notifications.
- create a reusable e-signature template from an existing document.
- document signing
- list all documents with their signing status.
- contract management
- download a completed signed document as a pdf.
- workflow automation
- retrieve details of a specific document group envelope.
- document management
- single template operations.
- send bulk invite
- delete template
- list envelopes
slug: document-signing
source_filename: document-signing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SignNow Document Signing\"\n  description: \"Workflow capability for end-to-end electronic document signing using SignNow. Covers document preparation, template-based workflows, signature invitation, bulk signing, and envelope management for legal and business agreement workflows.\"\n  tags:\n  - E-Signature\n  - Document Signing\n  - Contract Management\n  - Workflow Automation\n  - Legal\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SIGNNOW_ACCESS_TOKEN: SIGNNOW_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: signnow\n      location: ./shared/signnow.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: document-signing-api\n      description: \"Unified REST API for end-to-end electronic document signing workflows.\"\n      resources:\n        - path: /v1/documents\n          name: documents\n          description: \"Document lifecycle management.\"\
  \n          operations:\n            - method: GET\n              name: list-documents\n              description: \"List all documents with their signing status.\"\n              call: \"signnow.list-documents\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: upload-document\n              description: \"Upload a PDF document to begin the signing workflow.\"\n              call: \"signnow.upload-document\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{id}\n          name: document\n          description: \"Single document operations.\"\n          operations:\n            - method: GET\n              name: get-document\n              description: \"Retrieve document details, fields, and current signing status.\"\n              call: \"signnow.get-document\"\n              with:\n                document_id:\
  \ \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-document\n              description: \"Delete a document from the system.\"\n              call: \"signnow.delete-document\"\n              with:\n                document_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{id}/download\n          name: document-download\n          description: \"Document download.\"\n          operations:\n            - method: GET\n              name: download-document\n              description: \"Download a document as a signed PDF.\"\n              call: \"signnow.download-document\"\n              with:\n                document_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{id}/invite\n\
  \          name: signature-invite\n          description: \"Signature invitation management.\"\n          operations:\n            - method: POST\n              name: send-signature-invite\n              description: \"Send signature invitations to one or more recipients.\"\n              call: \"signnow.send-signature-invite\"\n              with:\n                document_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{id}/cancel-invite\n          name: cancel-invite\n          description: \"Cancel pending signature invites.\"\n          operations:\n            - method: POST\n              name: cancel-signature-invite\n              description: \"Cancel all pending signature invitations for a document.\"\n              call: \"signnow.cancel-signature-invite\"\n              with:\n                document_id: \"rest.id\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/templates\n          name: templates\n          description: \"Document template management.\"\n          operations:\n            - method: GET\n              name: list-templates\n              description: \"List all reusable document templates.\"\n              call: \"signnow.list-templates\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-template\n              description: \"Create a reusable template from an existing document.\"\n              call: \"signnow.create-template\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/templates/{id}\n          name: template\n          description: \"Single template operations.\"\n          operations:\n            - method: GET\n              name: get-template\n              description: \"Retrieve a specific\
  \ template with its fields and roles.\"\n              call: \"signnow.get-template\"\n              with:\n                template_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-template\n              description: \"Delete a document template.\"\n              call: \"signnow.delete-template\"\n              with:\n                template_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/templates/{id}/bulk-invite\n          name: bulk-invite\n          description: \"Bulk signature invitation.\"\n          operations:\n            - method: POST\n              name: send-bulk-invite\n              description: \"Send signature invitations to multiple recipients via CSV.\"\n              call: \"signnow.send-bulk-invite\"\n              with:\n                template_id:\
  \ \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/envelopes\n          name: envelopes\n          description: \"Document group envelope management.\"\n          operations:\n            - method: GET\n              name: list-envelopes\n              description: \"List all document group envelopes.\"\n              call: \"signnow.list-envelopes\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-envelope\n              description: \"Create a document group envelope for coordinated multi-document signing.\"\n              call: \"signnow.create-envelope\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/webhooks\n          name: webhooks\n          description: \"Webhook event subscription management.\"\n          operations:\n\
  \            - method: GET\n              name: list-webhooks\n              description: \"List all active webhook subscriptions.\"\n              call: \"signnow.list-webhooks\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-webhook\n              description: \"Register a webhook to receive signing event notifications.\"\n              call: \"signnow.create-webhook\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/me\n          name: current-user\n          description: \"Current user profile.\"\n          operations:\n            - method: GET\n              name: get-current-user\n              description: \"Retrieve the current user's profile and subscription information.\"\n              call: \"signnow.get-current-user\"\n              outputParameters:\n                - type: object\n     \
  \             mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: document-signing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted electronic document signing and workflow management.\"\n      tools:\n        - name: list-documents\n          description: \"List all e-signature documents and their current signing status.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"signnow.list-documents\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: upload-document\n          description: \"Upload a PDF document to begin an e-signature workflow.\"\n          hints:\n            readOnly: false\n          call: \"signnow.upload-document\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-document\n          description: \"Retrieve full details of a specific document including its fields and\
  \ signing status.\"\n          hints:\n            readOnly: true\n          call: \"signnow.get-document\"\n          with:\n            document_id: \"tools.document_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-document\n          description: \"Permanently delete a document from SignNow.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"signnow.delete-document\"\n          with:\n            document_id: \"tools.document_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: download-document\n          description: \"Download a completed signed document as a PDF.\"\n          hints:\n            readOnly: true\n          call: \"signnow.download-document\"\n          with:\n            document_id: \"tools.document_id\"\n          outputParameters:\n            - type: object\n \
  \             mapping: \"$.\"\n        - name: send-signature-invite\n          description: \"Send e-signature invitations to one or more recipients for a document.\"\n          hints:\n            readOnly: false\n          call: \"signnow.send-signature-invite\"\n          with:\n            document_id: \"tools.document_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-signature-invite\n          description: \"Cancel all pending signature invitations for a document.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"signnow.cancel-signature-invite\"\n          with:\n            document_id: \"tools.document_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-templates\n          description: \"List all available document templates for e-signature workflows.\"\n          hints:\n            readOnly: true\n\
  \            openWorld: true\n          call: \"signnow.list-templates\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-template\n          description: \"Retrieve a specific document template with its signing fields and roles.\"\n          hints:\n            readOnly: true\n          call: \"signnow.get-template\"\n          with:\n            template_id: \"tools.template_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-template\n          description: \"Create a reusable e-signature template from an existing document.\"\n          hints:\n            readOnly: false\n          call: \"signnow.create-template\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-template\n          description: \"Delete a document template from SignNow.\"\n          hints:\n            readOnly: false\n          \
  \  destructive: true\n            idempotent: true\n          call: \"signnow.delete-template\"\n          with:\n            template_id: \"tools.template_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-bulk-invite\n          description: \"Send e-signature invitations to multiple recipients using a CSV file and template.\"\n          hints:\n            readOnly: false\n          call: \"signnow.send-bulk-invite\"\n          with:\n            template_id: \"tools.template_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-envelopes\n          description: \"List all document group envelopes for coordinated multi-document signing.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"signnow.list-envelopes\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: create-envelope\n\
  \          description: \"Create a document group envelope to coordinate signing across multiple documents.\"\n          hints:\n            readOnly: false\n          call: \"signnow.create-envelope\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-envelope\n          description: \"Retrieve details of a specific document group envelope.\"\n          hints:\n            readOnly: true\n          call: \"signnow.get-envelope\"\n          with:\n            group_id: \"tools.group_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-webhooks\n          description: \"List all active webhook event subscriptions.\"\n          hints:\n            readOnly: true\n          call: \"signnow.list-webhooks\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: create-webhook\n          description: \"Register a webhook to receive\
  \ notifications when document signing events occur.\"\n          hints:\n            readOnly: false\n          call: \"signnow.create-webhook\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-current-user\n          description: \"Retrieve current user profile, subscription details, and usage information.\"\n          hints:\n            readOnly: true\n          call: \"signnow.get-current-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
