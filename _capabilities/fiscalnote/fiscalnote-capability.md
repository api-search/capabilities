---
categories: []
consumed_apis: []
description: The FiscalNote AppData API provides access to FiscalNote's data on legislation and regulations, both past and present, in the United States and globally. It also exposes organizational data from the FiscalNote platform including issues and labels. Developers can use the API to integrate legislative tracking, regulatory monitoring, and policy analysis capabilities into their own applications and workflows.
layout: capability
name: FiscalNote AppData API
operations:
- description: FiscalNote List bills
  method: GET
  name: listbills
  path: /appdata/v1/bills
- description: FiscalNote Get bill by ID
  method: GET
  name: getbill
  path: /appdata/v1/bills/{billId}
- description: FiscalNote List issues
  method: GET
  name: listissues
  path: /appdata/v1/issues
- description: FiscalNote Get issue by ID
  method: GET
  name: getissue
  path: /appdata/v1/issues/{issueId}
- description: FiscalNote List labels
  method: GET
  name: listlabels
  path: /appdata/v1/labels
- description: FiscalNote Get label by ID
  method: GET
  name: getlabel
  path: /appdata/v1/labels/{labelId}
- description: FiscalNote List regulatory documents
  method: GET
  name: listregulatorydocuments
  path: /appdata/v1/regulatory-documents
- description: FiscalNote Get regulatory document by ID
  method: GET
  name: getregulatorydocument
  path: /appdata/v1/regulatory-documents/{documentId}
personas: []
provider_name: FiscalNote
provider_slug: fiscalnote
search_terms:
- listregulatorydocuments
- regulation
- listlabels
- fiscalnote list regulatory documents
- getbill
- fiscalnote list bills
- government
- fiscalnote get label by id
- getlabel
- getissue
- listbills
- fiscalnote get regulatory document by id
- fiscalnote list issues
- political intelligence
- fiscalnote get bill by id
- api
- fiscalnote get issue by id
- legislation
- fiscalnote
- fiscalnote list labels
- policy
- listissues
- getregulatorydocument
slug: fiscalnote-capability
source_filename: fiscalnote-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FiscalNote AppData API\n  description: The FiscalNote AppData API provides access to FiscalNote's data on legislation and regulations, both past and\n    present, in the United States and globally. It also exposes organizational data from the FiscalNote platform including\n    issues and labels. Developers can use the API to integrate legislative tracking, regulatory monitoring, and policy analysis\n    capabilities into their own applications and workflows.\n  tags:\n  - Fiscalnote\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fiscalnote\n    baseUri: https://api.fiscalnote.com\n    description: FiscalNote AppData API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{FISCALNOTE_TOKEN}}'\n    resources:\n    - name: appdata-v1-bills\n      path: /appdata/v1/bills\n      operations:\n      - name: listbills\n\
  \        method: GET\n        description: FiscalNote List bills\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: appdata-v1-bills-billid\n      path: /appdata/v1/bills/{billId}\n      operations:\n      - name: getbill\n        method: GET\n        description: FiscalNote Get bill by ID\n        inputParameters:\n        - name: billId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the bill.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: appdata-v1-issues\n      path: /appdata/v1/issues\n      operations:\n      - name: listissues\n        method: GET\n        description: FiscalNote List issues\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ appdata-v1-issues-issueid\n      path: /appdata/v1/issues/{issueId}\n      operations:\n      - name: getissue\n        method: GET\n        description: FiscalNote Get issue by ID\n        inputParameters:\n        - name: issueId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the issue.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: appdata-v1-labels\n      path: /appdata/v1/labels\n      operations:\n      - name: listlabels\n        method: GET\n        description: FiscalNote List labels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: appdata-v1-labels-labelid\n      path: /appdata/v1/labels/{labelId}\n      operations:\n      - name: getlabel\n        method: GET\n        description: FiscalNote Get label by ID\n        inputParameters:\n\
  \        - name: labelId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the label.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: appdata-v1-regulatory-documents\n      path: /appdata/v1/regulatory-documents\n      operations:\n      - name: listregulatorydocuments\n        method: GET\n        description: FiscalNote List regulatory documents\n        inputParameters:\n        - name: agency\n          in: query\n          type: string\n          description: Filter by issuing agency name or identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: appdata-v1-regulatory-documents-documentid\n      path: /appdata/v1/regulatory-documents/{documentId}\n      operations:\n      - name: getregulatorydocument\n        method: GET\n    \
  \    description: FiscalNote Get regulatory document by ID\n        inputParameters:\n        - name: documentId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the regulatory document.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fiscalnote-rest\n    description: REST adapter for FiscalNote AppData API.\n    resources:\n    - path: /appdata/v1/bills\n      name: listbills\n      operations:\n      - method: GET\n        name: listbills\n        description: FiscalNote List bills\n        call: fiscalnote.listbills\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /appdata/v1/bills/{billId}\n      name: getbill\n      operations:\n      - method: GET\n        name: getbill\n        description: FiscalNote Get bill by ID\n        call: fiscalnote.getbill\n\
  \        with:\n          billId: rest.billId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /appdata/v1/issues\n      name: listissues\n      operations:\n      - method: GET\n        name: listissues\n        description: FiscalNote List issues\n        call: fiscalnote.listissues\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /appdata/v1/issues/{issueId}\n      name: getissue\n      operations:\n      - method: GET\n        name: getissue\n        description: FiscalNote Get issue by ID\n        call: fiscalnote.getissue\n        with:\n          issueId: rest.issueId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /appdata/v1/labels\n      name: listlabels\n      operations:\n      - method: GET\n        name: listlabels\n        description: FiscalNote List labels\n        call: fiscalnote.listlabels\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /appdata/v1/labels/{labelId}\n      name: getlabel\n      operations:\n      - method: GET\n        name: getlabel\n        description: FiscalNote Get label by ID\n        call: fiscalnote.getlabel\n        with:\n          labelId: rest.labelId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /appdata/v1/regulatory-documents\n      name: listregulatorydocuments\n      operations:\n      - method: GET\n        name: listregulatorydocuments\n        description: FiscalNote List regulatory documents\n        call: fiscalnote.listregulatorydocuments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /appdata/v1/regulatory-documents/{documentId}\n      name: getregulatorydocument\n      operations:\n      - method: GET\n        name: getregulatorydocument\n        description: FiscalNote Get regulatory document by ID\n        call: fiscalnote.getregulatorydocument\n        with:\n          documentId:\
  \ rest.documentId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fiscalnote-mcp\n    transport: http\n    description: MCP adapter for FiscalNote AppData API for AI agent use.\n    tools:\n    - name: listbills\n      description: FiscalNote List bills\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiscalnote.listbills\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbill\n      description: FiscalNote Get bill by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiscalnote.getbill\n      with:\n        billId: tools.billId\n      inputParameters:\n      - name: billId\n        type: string\n        description: The unique identifier of the bill.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listissues\n  \
  \    description: FiscalNote List issues\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiscalnote.listissues\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getissue\n      description: FiscalNote Get issue by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiscalnote.getissue\n      with:\n        issueId: tools.issueId\n      inputParameters:\n      - name: issueId\n        type: string\n        description: The unique identifier of the issue.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlabels\n      description: FiscalNote List labels\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiscalnote.listlabels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlabel\n      description: FiscalNote\
  \ Get label by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiscalnote.getlabel\n      with:\n        labelId: tools.labelId\n      inputParameters:\n      - name: labelId\n        type: string\n        description: The unique identifier of the label.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listregulatorydocuments\n      description: FiscalNote List regulatory documents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiscalnote.listregulatorydocuments\n      with:\n        agency: tools.agency\n      inputParameters:\n      - name: agency\n        type: string\n        description: Filter by issuing agency name or identifier.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getregulatorydocument\n      description: FiscalNote Get regulatory document by ID\n      hints:\n \
  \       readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiscalnote.getregulatorydocument\n      with:\n        documentId: tools.documentId\n      inputParameters:\n      - name: documentId\n        type: string\n        description: The unique identifier of the regulatory document.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FISCALNOTE_TOKEN: FISCALNOTE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fiscalnote/refs/heads/main/capabilities/fiscalnote-capability.yaml
tags:
- Fiscalnote
- API
tools:
- description: FiscalNote List bills
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbills
- description: FiscalNote Get bill by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbill
- description: FiscalNote List issues
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listissues
- description: FiscalNote Get issue by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getissue
- description: FiscalNote List labels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlabels
- description: FiscalNote Get label by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlabel
- description: FiscalNote List regulatory documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listregulatorydocuments
- description: FiscalNote Get regulatory document by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getregulatorydocument
---
