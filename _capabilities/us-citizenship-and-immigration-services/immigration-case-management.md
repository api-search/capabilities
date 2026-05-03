---
api_specs:
- filename: uscis-case-status-api-openapi.yml
  format: yaml
  label: uscis-case-status
  slug: uscis-case-status
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/us-citizenship-and-immigration-services/refs/heads/main/openapi/uscis-case-status-api-openapi.yml
- filename: uscis-foia-api-openapi.yml
  format: yaml
  label: uscis-foia
  slug: uscis-foia
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/us-citizenship-and-immigration-services/refs/heads/main/openapi/uscis-foia-api-openapi.yml
categories: []
consumed_apis:
- uscis-case-status
- uscis-foia
description: Unified capability for immigration case management workflows combining the USCIS Case Status API and FOIA Request API. Designed for immigration attorneys, accredited representatives, and case management software providers who need to monitor client case status and submit records requests on behalf of clients.
layout: capability
name: USCIS Immigration Case Management
operations:
- description: Retrieve current immigration case status and history by receipt number
  method: GET
  name: get-case-status
  path: /v1/cases/{receiptNumber}
- description: Submit a new FOIA or Privacy Act request for Alien File records
  method: POST
  name: submit-foia-request
  path: /v1/foia-requests
- description: Check the status of a submitted FOIA request
  method: GET
  name: get-foia-request-status
  path: /v1/foia-requests/{requestNumber}
personas: []
provider_name: US Citizenship and Immigration Services
provider_slug: us-citizenship-and-immigration-services
search_terms:
- get foia request status
- case management
- retrieve current immigration case status and history by receipt number
- status of a submitted foia request
- citizenship
- federal government
- legal services
- immigration
- submit a new foia or privacy act request for alien file records
- foia
- get case status
- submit a freedom of information act (foia) or privacy act request for uscis alien file records on behalf of a client. returns a request number for status tracking.
- foia and privacy act requests for alien file records
- check the processing status of a previously submitted uscis foia or privacy act request using the request number.
- case status
- retrieve the current immigration case status and complete history for a uscis receipt number. returns status in english and spanish with full historical timeline.
- uscis
- submit foia request
- immigration case status by receipt number
- check the status of a submitted foia request
slug: immigration-case-management
source_filename: immigration-case-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: USCIS Immigration Case Management\n  description: >-\n    Unified capability for immigration case management workflows combining the\n    USCIS Case Status API and FOIA Request API. Designed for immigration attorneys,\n    accredited representatives, and case management software providers who need to\n    monitor client case status and submit records requests on behalf of clients.\n  tags:\n    - Federal Government\n    - Immigration\n    - Case Management\n    - Case Status\n    - FOIA\n    - USCIS\n    - Legal Services\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      USCIS_CLIENT_ID: USCIS_CLIENT_ID\n      USCIS_CLIENT_SECRET: USCIS_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: uscis-case-status\n      location: ./shared/uscis-case-status-api.yaml\n    - import: uscis-foia\n      location: ./shared/uscis-foia-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n\
  \      namespace: uscis-immigration-case-management-api\n      description: >-\n        Unified REST API for USCIS immigration case management including case\n        status lookup and FOIA request submission.\n      resources:\n        - path: /v1/cases/{receiptNumber}\n          name: case-status\n          description: Immigration case status by receipt number\n          operations:\n            - method: GET\n              name: get-case-status\n              description: Retrieve current immigration case status and history by receipt number\n              call: \"uscis-case-status.get-case-status\"\n              with:\n                receiptNumber: \"rest.receiptNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/foia-requests\n          name: foia-requests\n          description: FOIA and Privacy Act requests for Alien File records\n          operations:\n            - method: POST\n              name:\
  \ submit-foia-request\n              description: Submit a new FOIA or Privacy Act request for Alien File records\n              call: \"uscis-foia.submit-foia-request\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/foia-requests/{requestNumber}\n          name: foia-request-status\n          description: Status of a submitted FOIA request\n          operations:\n            - method: GET\n              name: get-foia-request-status\n              description: Check the status of a submitted FOIA request\n              call: \"uscis-foia.get-foia-request-status\"\n              with:\n                requestNumber: \"rest.requestNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: uscis-immigration-case-management-mcp\n      transport: http\n      description: >-\n        MCP server for AI-assisted immigration\
  \ case management including case\n        status monitoring and FOIA request workflows.\n      tools:\n        - name: get-case-status\n          description: >-\n            Retrieve the current immigration case status and complete history\n            for a USCIS receipt number. Returns status in English and Spanish\n            with full historical timeline.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uscis-case-status.get-case-status\"\n          with:\n            receiptNumber: \"tools.receiptNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-foia-request\n          description: >-\n            Submit a Freedom of Information Act (FOIA) or Privacy Act request\n            for USCIS Alien File records on behalf of a client. Returns a\n            request number for status tracking.\n          hints:\n            readOnly: false\n            openWorld: false\n  \
  \        call: \"uscis-foia.submit-foia-request\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-foia-request-status\n          description: >-\n            Check the processing status of a previously submitted USCIS FOIA\n            or Privacy Act request using the request number.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uscis-foia.get-foia-request-status\"\n          with:\n            requestNumber: \"tools.requestNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/us-citizenship-and-immigration-services/refs/heads/main/capabilities/immigration-case-management.yaml
tags:
- Federal Government
- Immigration
- Case Management
- Case Status
- FOIA
- USCIS
- Legal Services
tools:
- description: Retrieve the current immigration case status and complete history for a USCIS receipt number. Returns status in English and Spanish with full historical timeline.
  hints:
    openWorld: false
    readOnly: true
  name: get-case-status
- description: Submit a Freedom of Information Act (FOIA) or Privacy Act request for USCIS Alien File records on behalf of a client. Returns a request number for status tracking.
  hints:
    openWorld: false
    readOnly: false
  name: submit-foia-request
- description: Check the processing status of a previously submitted USCIS FOIA or Privacy Act request using the request number.
  hints:
    openWorld: false
    readOnly: true
  name: get-foia-request-status
---
