---
categories: []
consumed_apis: []
description: The PandaDoc REST API provides programmatic access to PandaDoc's document automation platform, enabling developers to create, send, track, and manage documents within their own applications. The API supports the full document lifecycle including generating documents from templates with dynamic data, collecting e-signatures, managing recipients, and tracking document status. Authentication is handled via API keys or OAuth 2.0, and a free sandbox environment is available for testing integrations before moving to production. An active Enterprise plan is required to access the production API.
layout: capability
name: PandaDoc REST API
operations:
- description: List Documents
  method: GET
  name: listdocuments
  path: /documents
- description: Create Document
  method: POST
  name: createdocument
  path: /documents
- description: Get Document Details
  method: GET
  name: getdocumentdetails
  path: /documents/{id}
- description: Delete Document
  method: DELETE
  name: deletedocument
  path: /documents/{id}
- description: Get Document Status
  method: GET
  name: getdocumentstatus
  path: /documents/{id}/status
- description: Send Document
  method: POST
  name: senddocument
  path: /documents/{id}/send
- description: Download Document
  method: GET
  name: downloaddocument
  path: /documents/{id}/download
- description: Create Document Session
  method: POST
  name: createdocumentsession
  path: /documents/{id}/session
- description: List Document Recipients
  method: GET
  name: listdocumentrecipients
  path: /documents/{id}/recipients
- description: Add Document Recipient
  method: POST
  name: adddocumentrecipient
  path: /documents/{id}/recipients
- description: Update Document Recipient
  method: PATCH
  name: updatedocumentrecipient
  path: /documents/{id}/recipients/{recipient_id}
- description: Delete Document Recipient
  method: DELETE
  name: deletedocumentrecipient
  path: /documents/{id}/recipients/{recipient_id}
- description: List Document Fields
  method: GET
  name: listdocumentfields
  path: /documents/{id}/fields
- description: Update Document Fields
  method: PATCH
  name: updatedocumentfields
  path: /documents/{id}/fields
- description: List Document Attachments
  method: GET
  name: listdocumentattachments
  path: /documents/{id}/attachments
- description: Download Document Attachment
  method: GET
  name: downloaddocumentattachment
  path: /documents/{id}/attachments/{attachment_id}/download
- description: Get Document Auto-Reminders
  method: GET
  name: getdocumentautoreminders
  path: /documents/{document_id}/auto-reminders
- description: List Linked Objects
  method: GET
  name: listlinkedobjects
  path: /documents/linked-objects
- description: List Templates
  method: GET
  name: listtemplates
  path: /templates
- description: Get Template Details
  method: GET
  name: gettemplatedetails
  path: /templates/{id}/details
- description: Delete Template
  method: DELETE
  name: deletetemplate
  path: /templates/{id}
- description: List Forms
  method: GET
  name: listforms
  path: /forms
- description: List Document Folders
  method: GET
  name: listdocumentfolders
  path: /documents/folders
- description: Create Document Folder
  method: POST
  name: createdocumentfolder
  path: /documents/folders
- description: List Contacts
  method: GET
  name: listcontacts
  path: /contacts
- description: Create Contact
  method: POST
  name: createcontact
  path: /contacts
- description: Get Contact
  method: GET
  name: getcontact
  path: /contacts/{id}
- description: Update Contact
  method: PATCH
  name: updatecontact
  path: /contacts/{id}
- description: Delete Contact
  method: DELETE
  name: deletecontact
  path: /contacts/{id}
- description: List Members
  method: GET
  name: listmembers
  path: /members
- description: Get Current Member
  method: GET
  name: getcurrentmember
  path: /members/current
- description: Get Member
  method: GET
  name: getmember
  path: /members/{id}
- description: List Webhook Subscriptions
  method: GET
  name: listwebhooksubscriptions
  path: /webhook-subscriptions
- description: Create Webhook Subscription
  method: POST
  name: createwebhooksubscription
  path: /webhook-subscriptions
- description: Get Webhook Subscription
  method: GET
  name: getwebhooksubscription
  path: /webhook-subscriptions/{id}
- description: Update Webhook Subscription
  method: PATCH
  name: updatewebhooksubscription
  path: /webhook-subscriptions/{id}
- description: Delete Webhook Subscription
  method: DELETE
  name: deletewebhooksubscription
  path: /webhook-subscriptions/{id}
- description: Regenerate Webhook Shared Key
  method: PATCH
  name: updatewebhooksubscriptionsharedkey
  path: /webhook-subscriptions/{id}/shared-key
- description: List Webhook Events
  method: GET
  name: listwebhookevents
  path: /webhook-events
- description: Get Webhook Event Details
  method: GET
  name: getwebhookevent
  path: /webhook-events/{id}
- description: List API Logs
  method: GET
  name: listapilogs
  path: /logs
- description: List Workspaces
  method: GET
  name: listworkspaces
  path: /workspaces
- description: Create Workspace
  method: POST
  name: createworkspace
  path: /workspaces
personas: []
provider_name: PandaDoc
provider_slug: pandadoc
search_terms:
- create workspace
- deletedocumentrecipient
- list document folders
- createdocument
- create webhook subscription
- create contact
- getcurrentmember
- list linked objects
- getdocumentautoreminders
- createdocumentfolder
- updatecontact
- senddocument
- list document fields
- list webhook events
- get member
- get document details
- api
- deletedocument
- listdocumentfolders
- update document recipient
- get template details
- listwebhookevents
- updatedocumentfields
- updatedocumentrecipient
- update contact
- list forms
- listapilogs
- delete document
- create document folder
- adddocumentrecipient
- createdocumentsession
- listlinkedobjects
- get webhook subscription
- updatewebhooksubscription
- listwebhooksubscriptions
- update document fields
- listforms
- delete template
- pandadoc
- getdocumentstatus
- listdocumentfields
- create document
- deletetemplate
- getmember
- deletewebhooksubscription
- listworkspaces
- webhooks
- get contact
- listtemplates
- list documents
- list templates
- send document
- create document session
- add document recipient
- getwebhookevent
- download document attachment
- list api logs
- e-signature
- getcontact
- list webhook subscriptions
- downloaddocument
- getdocumentdetails
- createcontact
- createwebhooksubscription
- downloaddocumentattachment
- document management
- list workspaces
- getwebhooksubscription
- listdocumentattachments
- list contacts
- delete document recipient
- get document status
- regenerate webhook shared key
- listcontacts
- delete webhook subscription
- createworkspace
- listmembers
- get webhook event details
- listdocuments
- gettemplatedetails
- updatewebhooksubscriptionsharedkey
- get current member
- list document recipients
- document automation
- list document attachments
- update webhook subscription
- document generation
- download document
- delete contact
- listdocumentrecipients
- get document auto-reminders
- list members
- deletecontact
slug: pandadoc-capability
source_filename: pandadoc-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PandaDoc REST API\n  description: The PandaDoc REST API provides programmatic access to PandaDoc's document automation platform, enabling developers\n    to create, send, track, and manage documents within their own applications. The API supports the full document lifecycle\n    including generating documents from templates with dynamic data, collecting e-signatures, managing recipients, and tracking\n    document status. Authentication is handled via API keys or OAuth 2.0, and a free sandbox environment is available for\n    testing integrations before moving to production. An active Enterprise plan is required to access the production API.\n  tags:\n  - Pandadoc\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pandadoc\n    baseUri: https://api.pandadoc.com/public/v1\n    description: PandaDoc REST API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n\
  \      name: Authorization\n      value: '{{PANDADOC_TOKEN}}'\n    resources:\n    - name: documents\n      path: /documents\n      operations:\n      - name: listdocuments\n        method: GET\n        description: List Documents\n        inputParameters:\n        - name: template_id\n          in: query\n          type: string\n          description: Filter by the parent template identifier.\n        - name: form_id\n          in: query\n          type: string\n          description: Filter by the parent form identifier.\n        - name: folder_uuid\n          in: query\n          type: string\n          description: Filter by the folder where documents are stored.\n        - name: contact_id\n          in: query\n          type: string\n          description: Filter by recipient or approver contact identifier.\n        - name: status\n          in: query\n          type: string\n          description: Filter by document status.\n        - name: tag\n          in: query\n          type:\
  \ string\n          description: Filter by document tag (exact match).\n        - name: q\n          in: query\n          type: string\n          description: Search by document name substring.\n        - name: id\n          in: query\n          type: string\n          description: Filter by a specific document identifier.\n        - name: owner_id\n          in: query\n          type: string\n          description: Filter by the document owner member identifier.\n        - name: order_by\n          in: query\n          type: string\n          description: Sort field for results.\n        - name: asc\n          in: query\n          type: boolean\n          description: Set to true for ascending order, false for descending.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdocument\n        method: POST\n        description: Create Document\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: documents-id\n      path: /documents/{id}\n      operations:\n      - name: getdocumentdetails\n        method: GET\n        description: Get Document Details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedocument\n        method: DELETE\n        description: Delete Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-id-status\n      path: /documents/{id}/status\n      operations:\n      - name: getdocumentstatus\n        method: GET\n        description: Get Document Status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-id-send\n      path: /documents/{id}/send\n      operations:\n      - name: senddocument\n\
  \        method: POST\n        description: Send Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-id-download\n      path: /documents/{id}/download\n      operations:\n      - name: downloaddocument\n        method: GET\n        description: Download Document\n        inputParameters:\n        - name: watermark_color\n          in: query\n          type: string\n          description: Hex color code for watermark text applied to the downloaded PDF.\n        - name: watermark_font_size\n          in: query\n          type: integer\n          description: Font size for watermark text in points.\n        - name: watermark_opacity\n          in: query\n          type: number\n          description: Opacity of the watermark from 0.0 to 1.0.\n        - name: watermark_text\n          in: query\n          type: string\n          description: Text to render as a watermark on every page\
  \ of the PDF.\n        - name: separate_files\n          in: query\n          type: boolean\n          description: If true, returns a ZIP archive containing each document section as a separate PDF file.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-id-session\n      path: /documents/{id}/session\n      operations:\n      - name: createdocumentsession\n        method: POST\n        description: Create Document Session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-id-recipients\n      path: /documents/{id}/recipients\n      operations:\n      - name: listdocumentrecipients\n        method: GET\n        description: List Document Recipients\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: adddocumentrecipient\n\
  \        method: POST\n        description: Add Document Recipient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-id-recipients-recipient-id\n      path: /documents/{id}/recipients/{recipient_id}\n      operations:\n      - name: updatedocumentrecipient\n        method: PATCH\n        description: Update Document Recipient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedocumentrecipient\n        method: DELETE\n        description: Delete Document Recipient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-id-fields\n      path: /documents/{id}/fields\n      operations:\n      - name: listdocumentfields\n        method: GET\n        description: List Document Fields\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedocumentfields\n        method: PATCH\n        description: Update Document Fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-id-attachments\n      path: /documents/{id}/attachments\n      operations:\n      - name: listdocumentattachments\n        method: GET\n        description: List Document Attachments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-id-attachments-attachment-id-download\n      path: /documents/{id}/attachments/{attachment_id}/download\n      operations:\n      - name: downloaddocumentattachment\n        method: GET\n        description: Download Document Attachment\n        inputParameters:\n        - name: attachment_id\n          in: path\n\
  \          type: string\n          required: true\n          description: Unique identifier of the document attachment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-document-id-auto-reminders\n      path: /documents/{document_id}/auto-reminders\n      operations:\n      - name: getdocumentautoreminders\n        method: GET\n        description: Get Document Auto-Reminders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-linked-objects\n      path: /documents/linked-objects\n      operations:\n      - name: listlinkedobjects\n        method: GET\n        description: List Linked Objects\n        inputParameters:\n        - name: provider\n          in: query\n          type: string\n          required: true\n          description: CRM provider name (e.g., salesforce, hubspot).\n     \
  \   - name: entity_type\n          in: query\n          type: string\n          required: true\n          description: CRM entity type (e.g., contact, deal, account).\n        - name: entity_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier of the CRM entity.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates\n      path: /templates\n      operations:\n      - name: listtemplates\n        method: GET\n        description: List Templates\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description: Search by template name substring.\n        - name: tag\n          in: query\n          type: string\n          description: Filter by template tag (exact match).\n        - name: folder_uuid\n          in: query\n          type: string\n          description: Filter by folder identifier.\n\
  \        - name: deleted\n          in: query\n          type: boolean\n          description: If true, include deleted templates in the results.\n        - name: id\n          in: query\n          type: string\n          description: Filter by specific template identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates-id-details\n      path: /templates/{id}/details\n      operations:\n      - name: gettemplatedetails\n        method: GET\n        description: Get Template Details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates-id\n      path: /templates/{id}\n      operations:\n      - name: deletetemplate\n        method: DELETE\n        description: Delete Template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n    - name: forms\n      path: /forms\n      operations:\n      - name: listforms\n        method: GET\n        description: List Forms\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter forms by name substring.\n        - name: status\n          in: query\n          type: string\n          description: Filter forms by status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-folders\n      path: /documents/folders\n      operations:\n      - name: listdocumentfolders\n        method: GET\n        description: List Document Folders\n        inputParameters:\n        - name: parent_uuid\n          in: query\n          type: string\n          description: Filter by parent folder UUID to retrieve sub-folders. Omit to retrieve root-level folders.\n        - name: name\n          in: query\n          type: string\n\
  \          description: Filter folders by name substring.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdocumentfolder\n        method: POST\n        description: Create Document Folder\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts\n      path: /contacts\n      operations:\n      - name: listcontacts\n        method: GET\n        description: List Contacts\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description: Search contacts by name, email, or company substring.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcontact\n        method: POST\n        description: Create Contact\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: contacts-id\n      path: /contacts/{id}\n      operations:\n      - name: getcontact\n        method: GET\n        description: Get Contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecontact\n        method: PATCH\n        description: Update Contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontact\n        method: DELETE\n        description: Delete Contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: members\n      path: /members\n      operations:\n      - name: listmembers\n        method: GET\n        description: List Members\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: members-current\n      path: /members/current\n      operations:\n      - name: getcurrentmember\n        method: GET\n        description: Get Current Member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: members-id\n      path: /members/{id}\n      operations:\n      - name: getmember\n        method: GET\n        description: Get Member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhook-subscriptions\n      path: /webhook-subscriptions\n      operations:\n      - name: listwebhooksubscriptions\n        method: GET\n        description: List Webhook Subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createwebhooksubscription\n \
  \       method: POST\n        description: Create Webhook Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhook-subscriptions-id\n      path: /webhook-subscriptions/{id}\n      operations:\n      - name: getwebhooksubscription\n        method: GET\n        description: Get Webhook Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatewebhooksubscription\n        method: PATCH\n        description: Update Webhook Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletewebhooksubscription\n        method: DELETE\n        description: Delete Webhook Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: webhook-subscriptions-id-shared-key\n      path: /webhook-subscriptions/{id}/shared-key\n      operations:\n      - name: updatewebhooksubscriptionsharedkey\n        method: PATCH\n        description: Regenerate Webhook Shared Key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhook-events\n      path: /webhook-events\n      operations:\n      - name: listwebhookevents\n        method: GET\n        description: List Webhook Events\n        inputParameters:\n        - name: count\n          in: query\n          type: integer\n          required: true\n          description: Number of results to return per page.\n        - name: page\n          in: query\n          type: integer\n          required: true\n          description: Page number to retrieve.\n        - name: since\n          in: query\n          type: string\n          description: Return events created on\
  \ or after this timestamp.\n        - name: to\n          in: query\n          type: string\n          description: Return events created before this timestamp.\n        - name: type\n          in: query\n          type: array\n          description: Filter by event trigger type.\n        - name: http_status_code\n          in: query\n          type: array\n          description: Filter by HTTP response status code group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhook-events-id\n      path: /webhook-events/{id}\n      operations:\n      - name: getwebhookevent\n        method: GET\n        description: Get Webhook Event Details\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the webhook event.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: logs\n      path: /logs\n      operations:\n      - name: listapilogs\n        method: GET\n        description: List API Logs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces\n      path: /workspaces\n      operations:\n      - name: listworkspaces\n        method: GET\n        description: List Workspaces\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createworkspace\n        method: POST\n        description: Create Workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pandadoc-rest\n    description: REST adapter for PandaDoc REST API.\n    resources:\n    - path: /documents\n      name: listdocuments\n\
  \      operations:\n      - method: GET\n        name: listdocuments\n        description: List Documents\n        call: pandadoc.listdocuments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents\n      name: createdocument\n      operations:\n      - method: POST\n        name: createdocument\n        description: Create Document\n        call: pandadoc.createdocument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{id}\n      name: getdocumentdetails\n      operations:\n      - method: GET\n        name: getdocumentdetails\n        description: Get Document Details\n        call: pandadoc.getdocumentdetails\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{id}\n      name: deletedocument\n      operations:\n      - method: DELETE\n        name: deletedocument\n        description: Delete Document\n        call: pandadoc.deletedocument\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{id}/status\n      name: getdocumentstatus\n      operations:\n      - method: GET\n        name: getdocumentstatus\n        description: Get Document Status\n        call: pandadoc.getdocumentstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{id}/send\n      name: senddocument\n      operations:\n      - method: POST\n        name: senddocument\n        description: Send Document\n        call: pandadoc.senddocument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{id}/download\n      name: downloaddocument\n      operations:\n      - method: GET\n        name: downloaddocument\n        description: Download Document\n        call: pandadoc.downloaddocument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{id}/session\n      name: createdocumentsession\n\
  \      operations:\n      - method: POST\n        name: createdocumentsession\n        description: Create Document Session\n        call: pandadoc.createdocumentsession\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{id}/recipients\n      name: listdocumentrecipients\n      operations:\n      - method: GET\n        name: listdocumentrecipients\n        description: List Document Recipients\n        call: pandadoc.listdocumentrecipients\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{id}/recipients\n      name: adddocumentrecipient\n      operations:\n      - method: POST\n        name: adddocumentrecipient\n        description: Add Document Recipient\n        call: pandadoc.adddocumentrecipient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{id}/recipients/{recipient_id}\n      name: updatedocumentrecipient\n      operations:\n      -\
  \ method: PATCH\n        name: updatedocumentrecipient\n        description: Update Document Recipient\n        call: pandadoc.updatedocumentrecipient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{id}/recipients/{recipient_id}\n      name: deletedocumentrecipient\n      operations:\n      - method: DELETE\n        name: deletedocumentrecipient\n        description: Delete Document Recipient\n        call: pandadoc.deletedocumentrecipient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{id}/fields\n      name: listdocumentfields\n      operations:\n      - method: GET\n        name: listdocumentfields\n        description: List Document Fields\n        call: pandadoc.listdocumentfields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{id}/fields\n      name: updatedocumentfields\n      operations:\n      - method: PATCH\n        name: updatedocumentfields\n\
  \        description: Update Document Fields\n        call: pandadoc.updatedocumentfields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{id}/attachments\n      name: listdocumentattachments\n      operations:\n      - method: GET\n        name: listdocumentattachments\n        description: List Document Attachments\n        call: pandadoc.listdocumentattachments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{id}/attachments/{attachment_id}/download\n      name: downloaddocumentattachment\n      operations:\n      - method: GET\n        name: downloaddocumentattachment\n        description: Download Document Attachment\n        call: pandadoc.downloaddocumentattachment\n        with:\n          attachment_id: rest.attachment_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{document_id}/auto-reminders\n      name: getdocumentautoreminders\n\
  \      operations:\n      - method: GET\n        name: getdocumentautoreminders\n        description: Get Document Auto-Reminders\n        call: pandadoc.getdocumentautoreminders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/linked-objects\n      name: listlinkedobjects\n      operations:\n      - method: GET\n        name: listlinkedobjects\n        description: List Linked Objects\n        call: pandadoc.listlinkedobjects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /templates\n      name: listtemplates\n      operations:\n      - method: GET\n        name: listtemplates\n        description: List Templates\n        call: pandadoc.listtemplates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /templates/{id}/details\n      name: gettemplatedetails\n      operations:\n      - method: GET\n        name: gettemplatedetails\n        description: Get Template\
  \ Details\n        call: pandadoc.gettemplatedetails\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /templates/{id}\n      name: deletetemplate\n      operations:\n      - method: DELETE\n        name: deletetemplate\n        description: Delete Template\n        call: pandadoc.deletetemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /forms\n      name: listforms\n      operations:\n      - method: GET\n        name: listforms\n        description: List Forms\n        call: pandadoc.listforms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/folders\n      name: listdocumentfolders\n      operations:\n      - method: GET\n        name: listdocumentfolders\n        description: List Document Folders\n        call: pandadoc.listdocumentfolders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/folders\n      name:\
  \ createdocumentfolder\n      operations:\n      - method: POST\n        name: createdocumentfolder\n        description: Create Document Folder\n        call: pandadoc.createdocumentfolder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name: listcontacts\n      operations:\n      - method: GET\n        name: listcontacts\n        description: List Contacts\n        call: pandadoc.listcontacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name: createcontact\n      operations:\n      - method: POST\n        name: createcontact\n        description: Create Contact\n        call: pandadoc.createcontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/{id}\n      name: getcontact\n      operations:\n      - method: GET\n        name: getcontact\n        description: Get Contact\n        call: pandadoc.getcontact\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /contacts/{id}\n      name: updatecontact\n      operations:\n      - method: PATCH\n        name: updatecontact\n        description: Update Contact\n        call: pandadoc.updatecontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/{id}\n      name: deletecontact\n      operations:\n      - method: DELETE\n        name: deletecontact\n        description: Delete Contact\n        call: pandadoc.deletecontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /members\n      name: listmembers\n      operations:\n      - method: GET\n        name: listmembers\n        description: List Members\n        call: pandadoc.listmembers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /members/current\n      name: getcurrentmember\n      operations:\n      - method: GET\n        name: getcurrentmember\n        description:\
  \ Get Current Member\n        call: pandadoc.getcurrentmember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /members/{id}\n      name: getmember\n      operations:\n      - method: GET\n        name: getmember\n        description: Get Member\n        call: pandadoc.getmember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhook-subscriptions\n      name: listwebhooksubscriptions\n      operations:\n      - method: GET\n        name: listwebhooksubscriptions\n        description: List Webhook Subscriptions\n        call: pandadoc.listwebhooksubscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhook-subscriptions\n      name: createwebhooksubscription\n      operations:\n      - method: POST\n        name: createwebhooksubscription\n        description: Create Webhook Subscription\n        call: pandadoc.createwebhooksubscription\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /webhook-subscriptions/{id}\n      name: getwebhooksubscription\n      operations:\n      - method: GET\n        name: getwebhooksubscription\n        description: Get Webhook Subscription\n        call: pandadoc.getwebhooksubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhook-subscriptions/{id}\n      name: updatewebhooksubscription\n      operations:\n      - method: PATCH\n        name: updatewebhooksubscription\n        description: Update Webhook Subscription\n        call: pandadoc.updatewebhooksubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhook-subscriptions/{id}\n      name: deletewebhooksubscription\n      operations:\n      - method: DELETE\n        name: deletewebhooksubscription\n        description: Delete Webhook Subscription\n        call: pandadoc.deletewebhooksubscription\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /webhook-subscriptions/{id}/shared-key\n      name: updatewebhooksubscriptionsharedkey\n      operations:\n      - method: PATCH\n        name: updatewebhooksubscriptionsharedkey\n        description: Regenerate Webhook Shared Key\n        call: pandadoc.updatewebhooksubscriptionsharedkey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhook-events\n      name: listwebhookevents\n      operations:\n      - method: GET\n        name: listwebhookevents\n        description: List Webhook Events\n        call: pandadoc.listwebhookevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhook-events/{id}\n      name: getwebhookevent\n      operations:\n      - method: GET\n        name: getwebhookevent\n        description: Get Webhook Event Details\n        call: pandadoc.getwebhookevent\n        with:\n          id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /logs\n      name: listapilogs\n      operations:\n      - method: GET\n        name: listapilogs\n        description: List API Logs\n        call: pandadoc.listapilogs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces\n      name: listworkspaces\n      operations:\n      - method: GET\n        name: listworkspaces\n        description: List Workspaces\n        call: pandadoc.listworkspaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces\n      name: createworkspace\n      operations:\n      - method: POST\n        name: createworkspace\n        description: Create Workspace\n        call: pandadoc.createworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pandadoc-mcp\n    transport: http\n    description: MCP adapter for PandaDoc REST API for AI agent\
  \ use.\n    tools:\n    - name: listdocuments\n      description: List Documents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pandadoc.listdocuments\n      with:\n        template_id: tools.template_id\n        form_id: tools.form_id\n        folder_uuid: tools.folder_uuid\n        contact_id: tools.contact_id\n        status: tools.status\n        tag: tools.tag\n        q: tools.q\n        id: tools.id\n        owner_id: tools.owner_id\n        order_by: tools.order_by\n        asc: tools.asc\n      inputParameters:\n      - name: template_id\n        type: string\n        description: Filter by the parent template identifier.\n      - name: form_id\n        type: string\n        description: Filter by the parent form identifier.\n      - name: folder_uuid\n        type: string\n        description: Filter by the folder where documents are stored.\n      - name: contact_id\n        type: string\n        description: Filter by\
  \ recipient or approver contact identifier.\n      - name: status\n        type: string\n        description: Filter by document status.\n      - name: tag\n        type: string\n        description: Filter by document tag (exact match).\n      - name: q\n        type: string\n        description: Search by document name substring.\n      - name: id\n        type: string\n        description: Filter by a specific document identifier.\n      - name: owner_id\n        type: string\n        description: Filter by the document owner member identifier.\n      - name: order_by\n        type: string\n        description: Sort field for results.\n      - name: asc\n        type: boolean\n        description: Set to true for ascending order, false for descending.\n      outp\n\n# --- truncated at 32 KB (47 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/pandadoc/refs/heads/main/capabilities/pandadoc-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pandadoc/refs/heads/main/capabilities/pandadoc-capability.yaml
tags:
- Pandadoc
- API
tools:
- description: List Documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdocuments
- description: Create Document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdocument
- description: Get Document Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocumentdetails
- description: Delete Document
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedocument
- description: Get Document Status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocumentstatus
- description: Send Document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: senddocument
- description: Download Document
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloaddocument
- description: Create Document Session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdocumentsession
- description: List Document Recipients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdocumentrecipients
- description: Add Document Recipient
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: adddocumentrecipient
- description: Update Document Recipient
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedocumentrecipient
- description: Delete Document Recipient
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedocumentrecipient
- description: List Document Fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdocumentfields
- description: Update Document Fields
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedocumentfields
- description: List Document Attachments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdocumentattachments
- description: Download Document Attachment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloaddocumentattachment
- description: Get Document Auto-Reminders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocumentautoreminders
- description: List Linked Objects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlinkedobjects
- description: List Templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtemplates
- description: Get Template Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettemplatedetails
- description: Delete Template
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetemplate
- description: List Forms
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listforms
- description: List Document Folders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdocumentfolders
- description: Create Document Folder
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdocumentfolder
- description: List Contacts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontacts
- description: Create Contact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontact
- description: Get Contact
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontact
- description: Update Contact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecontact
- description: Delete Contact
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontact
- description: List Members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmembers
- description: Get Current Member
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentmember
- description: Get Member
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmember
- description: List Webhook Subscriptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwebhooksubscriptions
- description: Create Webhook Subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwebhooksubscription
- description: Get Webhook Subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwebhooksubscription
- description: Update Webhook Subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatewebhooksubscription
- description: Delete Webhook Subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletewebhooksubscription
- description: Regenerate Webhook Shared Key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatewebhooksubscriptionsharedkey
- description: List Webhook Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwebhookevents
- description: Get Webhook Event Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwebhookevent
- description: List API Logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapilogs
- description: List Workspaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkspaces
- description: Create Workspace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkspace
---
