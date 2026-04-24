---
consumed_apis:
- esignature
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
- create and optionally send an agreement envelope
- electronic signatures
- envelope lifecycle management
- retrieve details of a specific envelope
- digital transaction management
- documents
- template management
- list envelopes
- list envelopes in the docusign account
- create envelope
- list available agreement templates
- retrieve envelope details
- individual envelope operations
- agreements
- docusign
- contracts
- list templates
- create and send an envelope
- workflows
- get envelope
- esignature
slug: agreement-workflows
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
