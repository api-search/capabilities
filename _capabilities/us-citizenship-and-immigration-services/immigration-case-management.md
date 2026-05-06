---
categories: []
consumed_apis: []
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
- get case status
- immigration
- case management
- get foia request status
- foia
- retrieve current immigration case status and history by receipt number
- case status
- uscis
- immigration case status by receipt number
- check the status of a submitted foia request
- foia and privacy act requests for alien file records
- submit a new foia or privacy act request for alien file records
- submit a freedom of information act (foia) or privacy act request for uscis alien file records on behalf of a client. returns a request number for status tracking.
- submit foia request
- retrieve the current immigration case status and complete history for a uscis receipt number. returns status in english and spanish with full historical timeline.
- federal government
- citizenship
- legal services
- check the processing status of a previously submitted uscis foia or privacy act request using the request number.
- status of a submitted foia request
slug: immigration-case-management
source_filename: immigration-case-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: USCIS Immigration Case Management\n  description: Unified capability for immigration case management workflows combining the USCIS Case Status API and FOIA Request\n    API. Designed for immigration attorneys, accredited representatives, and case management software providers who need to\n    monitor client case status and submit records requests on behalf of clients.\n  tags:\n  - Federal Government\n  - Immigration\n  - Case Management\n  - Case Status\n  - FOIA\n  - USCIS\n  - Legal Services\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    USCIS_CLIENT_ID: USCIS_CLIENT_ID\n    USCIS_CLIENT_SECRET: USCIS_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: uscis-case-status\n    baseUri: https://api-int.uscis.gov/case-status\n    description: USCIS Case Status API for immigration case status lookup\n    authentication:\n      type: bearer\n      token: '{{USCIS_ACCESS_TOKEN}}'\n\
  \    resources:\n    - name: case-status\n      path: /\n      description: Immigration case status by receipt number\n      operations:\n      - name: get-case-status\n        method: GET\n        description: Retrieve case status for a specific USCIS receipt number\n        inputParameters:\n        - name: receiptNumber\n          in: path\n          type: string\n          required: true\n          description: 13-character USCIS receipt number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: uscis-foia\n    baseUri: https://api-int.uscis.gov/foia\n    description: USCIS FOIA request submission and status tracking API\n    authentication:\n      type: bearer\n      token: '{{USCIS_ACCESS_TOKEN}}'\n    resources:\n    - name: foia-requests\n      path: /requests\n      description: FOIA and Privacy Act request management\n      operations:\n      - name: submit-foia-request\n\
  \        method: POST\n        description: Submit a new FOIA or Privacy Act request for Alien File records\n        inputParameters:\n        - name: requestType\n          in: body\n          type: string\n          required: true\n          description: Request type (FOIA or PrivacyAct)\n        - name: subjectFirstName\n          in: body\n          type: string\n          required: true\n          description: First name of the subject\n        - name: subjectLastName\n          in: body\n          type: string\n          required: true\n          description: Last name of the subject\n        - name: subjectDateOfBirth\n          in: body\n          type: string\n          required: false\n          description: Date of birth of the subject\n        - name: subjectAlienNumber\n          in: body\n          type: string\n          required: false\n          description: USCIS A-Number if known\n        - name: requesterName\n          in: body\n          type: string\n          required:\
  \ true\n          description: Name of the requester\n        - name: requesterEmail\n          in: body\n          type: string\n          required: true\n          description: Email for response delivery\n        - name: requesterType\n          in: body\n          type: string\n          required: true\n          description: Relationship to subject (self, attorney, etc.)\n        - name: descriptionOfRecords\n          in: body\n          type: string\n          required: true\n          description: Description of records requested\n        - name: deliveryMethod\n          in: body\n          type: string\n          required: false\n          description: Delivery method (email, usps, portal)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-foia-request-status\n        method: GET\n        description: Check status of a submitted FOIA request by request number\n        inputParameters:\n\
  \        - name: requestNumber\n          in: path\n          type: string\n          required: true\n          description: FOIA request number returned upon submission\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: uscis-immigration-case-management-api\n    description: Unified REST API for USCIS immigration case management including case status lookup and FOIA request submission.\n    resources:\n    - path: /v1/cases/{receiptNumber}\n      name: case-status\n      description: Immigration case status by receipt number\n      operations:\n      - method: GET\n        name: get-case-status\n        description: Retrieve current immigration case status and history by receipt number\n        call: uscis-case-status.get-case-status\n        with:\n          receiptNumber: rest.receiptNumber\n        outputParameters:\n        - type: object\n      \
  \    mapping: $.\n    - path: /v1/foia-requests\n      name: foia-requests\n      description: FOIA and Privacy Act requests for Alien File records\n      operations:\n      - method: POST\n        name: submit-foia-request\n        description: Submit a new FOIA or Privacy Act request for Alien File records\n        call: uscis-foia.submit-foia-request\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/foia-requests/{requestNumber}\n      name: foia-request-status\n      description: Status of a submitted FOIA request\n      operations:\n      - method: GET\n        name: get-foia-request-status\n        description: Check the status of a submitted FOIA request\n        call: uscis-foia.get-foia-request-status\n        with:\n          requestNumber: rest.requestNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: uscis-immigration-case-management-mcp\n    transport: http\n\
  \    description: MCP server for AI-assisted immigration case management including case status monitoring and FOIA request\n      workflows.\n    tools:\n    - name: get-case-status\n      description: Retrieve the current immigration case status and complete history for a USCIS receipt number. Returns status\n        in English and Spanish with full historical timeline.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uscis-case-status.get-case-status\n      with:\n        receiptNumber: tools.receiptNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-foia-request\n      description: Submit a Freedom of Information Act (FOIA) or Privacy Act request for USCIS Alien File records on behalf\n        of a client. Returns a request number for status tracking.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: uscis-foia.submit-foia-request\n      outputParameters:\n      - type: object\n      \
  \  mapping: $.\n    - name: get-foia-request-status\n      description: Check the processing status of a previously submitted USCIS FOIA or Privacy Act request using the request\n        number.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uscis-foia.get-foia-request-status\n      with:\n        requestNumber: tools.requestNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
