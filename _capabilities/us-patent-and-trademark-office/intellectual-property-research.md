---
categories: []
consumed_apis: []
description: Unified capability for intellectual property research, combining patent application search, PTAB trial proceedings, and trademark status retrieval. Supports IP attorneys, researchers, portfolio managers, and compliance teams.
layout: capability
name: USPTO Intellectual Property Research
operations:
- description: Search patent applications by query and filters
  method: GET
  name: search-patents
  path: /v1/patents
- description: Get full patent application record
  method: GET
  name: get-patent
  path: /v1/patents/{applicationNumberText}
- description: List documents for a patent application
  method: GET
  name: list-patent-documents
  path: /v1/patents/{applicationNumberText}/documents
- description: Search PTAB trial proceedings
  method: GET
  name: search-ptab-proceedings
  path: /v1/ptab/proceedings
- description: Get PTAB proceeding by trial number
  method: GET
  name: get-ptab-proceeding
  path: /v1/ptab/proceedings/{trialNumber}
- description: Search PTAB trial decisions
  method: GET
  name: search-ptab-decisions
  path: /v1/ptab/decisions
- description: Get trademark case status by serial or registration number
  method: GET
  name: get-trademark-status
  path: /v1/trademarks/{caseId}/status
- description: List documents for a trademark case
  method: GET
  name: list-trademark-documents
  path: /v1/trademarks/{caseId}/documents
- description: Browse available USPTO bulk data products
  method: GET
  name: list-datasets
  path: /v1/datasets
personas: []
provider_name: US Patent and Trademark Office
provider_slug: us-patent-and-trademark-office
search_terms:
- search ptab trial proceedings
- search uspto patent applications by keyword, inventor, assignee, or classification
- list all office actions, responses, and other documents filed in a patent application
- list all documents filed in a trademark case including office actions and responses
- get patent documents
- get the full list of uspto patent application status codes and their meanings
- ptab inter partes review and post-grant review proceedings
- get ptab proceeding
- search patents
- search ptab inter partes review (ipr), post-grant review (pgr), and covered business method (cbm) proceedings
- get trademark case status by serial or registration number
- ptab proceeding detail
- get full patent application record
- list datasets
- patents
- trademark case documents
- list documents for a trademark case
- search ptab final written decisions and institution decisions
- list trademark documents
- bulk data products
- browse available uspto bulk data products
- get complete details for a specific patent application including inventors, assignees, and status
- list patent documents
- search ptab trial decisions
- get trademark status
- ptab trial final written decisions
- search patent applications by query and filters
- list patent status codes
- trademark case status
- patent application search and retrieval
- intellectual property
- search patent applications
- get patent
- get ptab proceeding by trial number
- browse available uspto bulk data products for economic research and analysis
- get the current prosecution status and owner information for a trademark application or registration
- patent application documents
- legal research
- federal government
- get patent application
- search ptab proceedings
- browse bulk datasets
- get full details of a ptab trial including petitioner, respondent, and claim dispositions
- search ptab decisions
- patent application detail
- trademarks
- list documents for a patent application
- open data
slug: intellectual-property-research
source_filename: intellectual-property-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: USPTO Intellectual Property Research\n  description: Unified capability for intellectual property research, combining patent application search, PTAB trial proceedings,\n    and trademark status retrieval. Supports IP attorneys, researchers, portfolio managers, and compliance teams.\n  tags:\n  - Patents\n  - Trademarks\n  - Intellectual Property\n  - Federal Government\n  - Open Data\n  - Legal Research\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    USPTO_ODP_API_KEY: USPTO_ODP_API_KEY\n    USPTO_TSDR_API_KEY: USPTO_TSDR_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: uspto-odp\n    baseUri: https://api.uspto.gov\n    description: USPTO Open Data Portal REST API for patent and PTAB data.\n    authentication:\n      type: apikey\n      key: X-API-KEY\n      value: '{{USPTO_ODP_API_KEY}}'\n      placement: header\n    resources:\n    - name: patent-applications\n      path: /api/v1/patent/applications\n\
  \      description: Search and retrieve patent application data\n      operations:\n      - name: search-patent-applications\n        method: POST\n        description: Search patent applications by JSON payload\n        body:\n          type: json\n          data:\n            q: '{{tools.query}}'\n            start: '{{tools.start}}'\n            rows: '{{tools.rows}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-patent-applications\n        method: GET\n        description: Search patent applications by query parameters\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query string\n        - name: start\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: rows\n          in: query\n          type: integer\n\
  \          required: false\n          description: Number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patent-application-detail\n      path: /api/v1/patent/applications/{applicationNumberText}\n      description: Retrieve specific patent application details\n      operations:\n      - name: get-patent-application\n        method: GET\n        description: Get full patent application record\n        inputParameters:\n        - name: applicationNumberText\n          in: path\n          type: string\n          required: true\n          description: Patent application number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-patent-application-documents\n        method: GET\n        description: Get documents for a patent application\n        inputParameters:\n        - name: applicationNumberText\n\
  \          in: path\n          type: string\n          required: true\n          description: Patent application number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patent-status-codes\n      path: /api/v1/patent/status-codes\n      description: Patent application status codes\n      operations:\n      - name: list-patent-status-codes\n        method: GET\n        description: Get all patent application status codes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: ptab-proceedings\n      path: /api/v1/patent/trials/proceedings\n      description: PTAB trial proceedings\n      operations:\n      - name: search-ptab-proceedings\n        method: GET\n        description: Search PTAB trial proceedings\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required:\
  \ false\n          description: Search query\n        - name: start\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: rows\n          in: query\n          type: integer\n          required: false\n          description: Number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-ptab-proceeding\n        method: GET\n        description: Get PTAB trial proceeding by trial number\n        inputParameters:\n        - name: trialNumber\n          in: path\n          type: string\n          required: true\n          description: PTAB trial number (e.g., IPR2023-00001)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ptab-decisions\n      path: /api/v1/patent/trials/decisions\n      description: PTAB trial decisions\n \
  \     operations:\n      - name: search-ptab-decisions\n        method: GET\n        description: Search PTAB trial decisions\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query\n        - name: start\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: rows\n          in: query\n          type: integer\n          required: false\n          description: Number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bulk-datasets\n      path: /api/v1/datasets/products\n      description: Bulk dataset products\n      operations:\n      - name: search-dataset-products\n        method: GET\n        description: Search available bulk datasets\n        inputParameters:\n        - name: q\n          in: query\n          type:\
  \ string\n          required: false\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: uspto-tsdr\n    baseUri: https://tsdrapi.uspto.gov\n    description: USPTO TSDR REST API for trademark case status and documents.\n    authentication:\n      type: apikey\n      key: USPTO-API-KEY\n      value: '{{USPTO_TSDR_API_KEY}}'\n      placement: header\n    resources:\n    - name: case-status\n      path: /ts/cd/caseMultiStatus/{type}\n      description: Retrieve status for multiple trademark cases\n      operations:\n      - name: get-trademark-case-status\n        method: GET\n        description: Get status for one or more trademark cases by serial or registration number\n        inputParameters:\n        - name: type\n          in: path\n          type: string\n          required: true\n          description: Response format (json or xml)\n     \
  \   - name: sn\n          in: query\n          type: string\n          required: false\n          description: Serial numbers (comma-separated)\n        - name: rn\n          in: query\n          type: string\n          required: false\n          description: Registration numbers (comma-separated)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: case-documents\n      path: /ts/cd/casedocs/{caseid}\n      description: Trademark case document access\n      operations:\n      - name: get-case-document-list\n        method: GET\n        description: Get list of documents for a trademark case\n        inputParameters:\n        - name: caseid\n          in: path\n          type: string\n          required: true\n          description: Trademark serial or registration number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \ exposes:\n  - type: rest\n    port: 8080\n    namespace: ip-research-api\n    description: Unified REST API for USPTO intellectual property research.\n    resources:\n    - path: /v1/patents\n      name: patents\n      description: Patent application search and retrieval\n      operations:\n      - method: GET\n        name: search-patents\n        description: Search patent applications by query and filters\n        call: uspto-odp.list-patent-applications\n        with:\n          q: rest.q\n          start: rest.start\n          rows: rest.rows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/patents/{applicationNumberText}\n      name: patent-detail\n      description: Patent application detail\n      operations:\n      - method: GET\n        name: get-patent\n        description: Get full patent application record\n        call: uspto-odp.get-patent-application\n        with:\n          applicationNumberText: rest.applicationNumberText\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/patents/{applicationNumberText}/documents\n      name: patent-documents\n      description: Patent application documents\n      operations:\n      - method: GET\n        name: list-patent-documents\n        description: List documents for a patent application\n        call: uspto-odp.get-patent-application-documents\n        with:\n          applicationNumberText: rest.applicationNumberText\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ptab/proceedings\n      name: ptab-proceedings\n      description: PTAB inter partes review and post-grant review proceedings\n      operations:\n      - method: GET\n        name: search-ptab-proceedings\n        description: Search PTAB trial proceedings\n        call: uspto-odp.search-ptab-proceedings\n        with:\n          q: rest.q\n          start: rest.start\n          rows: rest.rows\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/ptab/proceedings/{trialNumber}\n      name: ptab-proceeding\n      description: PTAB proceeding detail\n      operations:\n      - method: GET\n        name: get-ptab-proceeding\n        description: Get PTAB proceeding by trial number\n        call: uspto-odp.get-ptab-proceeding\n        with:\n          trialNumber: rest.trialNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ptab/decisions\n      name: ptab-decisions\n      description: PTAB trial final written decisions\n      operations:\n      - method: GET\n        name: search-ptab-decisions\n        description: Search PTAB trial decisions\n        call: uspto-odp.search-ptab-decisions\n        with:\n          q: rest.q\n          start: rest.start\n          rows: rest.rows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trademarks/{caseId}/status\n      name: trademark-status\n\
  \      description: Trademark case status\n      operations:\n      - method: GET\n        name: get-trademark-status\n        description: Get trademark case status by serial or registration number\n        call: uspto-tsdr.get-trademark-case-status\n        with:\n          type: json\n          sn: rest.caseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trademarks/{caseId}/documents\n      name: trademark-documents\n      description: Trademark case documents\n      operations:\n      - method: GET\n        name: list-trademark-documents\n        description: List documents for a trademark case\n        call: uspto-tsdr.get-case-document-list\n        with:\n          caseid: rest.caseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/datasets\n      name: datasets\n      description: Bulk data products\n      operations:\n      - method: GET\n        name: list-datasets\n        description: Browse\
  \ available USPTO bulk data products\n        call: uspto-odp.search-dataset-products\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ip-research-mcp\n    transport: http\n    description: MCP server for AI-assisted USPTO intellectual property research.\n    tools:\n    - name: search-patent-applications\n      description: Search USPTO patent applications by keyword, inventor, assignee, or classification\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uspto-odp.list-patent-applications\n      with:\n        q: tools.q\n        start: tools.start\n        rows: tools.rows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-patent-application\n      description: Get complete details for a specific patent application including inventors, assignees, and status\n      hints:\n        readOnly: true\n        openWorld: false\n\
  \      call: uspto-odp.get-patent-application\n      with:\n        applicationNumberText: tools.applicationNumberText\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-patent-documents\n      description: List all office actions, responses, and other documents filed in a patent application\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uspto-odp.get-patent-application-documents\n      with:\n        applicationNumberText: tools.applicationNumberText\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-ptab-proceedings\n      description: Search PTAB inter partes review (IPR), post-grant review (PGR), and covered business method (CBM) proceedings\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uspto-odp.search-ptab-proceedings\n      with:\n        q: tools.q\n        start: tools.start\n        rows: tools.rows\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: get-ptab-proceeding\n      description: Get full details of a PTAB trial including petitioner, respondent, and claim dispositions\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uspto-odp.get-ptab-proceeding\n      with:\n        trialNumber: tools.trialNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-ptab-decisions\n      description: Search PTAB final written decisions and institution decisions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uspto-odp.search-ptab-decisions\n      with:\n        q: tools.q\n        start: tools.start\n        rows: tools.rows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-trademark-status\n      description: Get the current prosecution status and owner information for a trademark application or registration\n      hints:\n        readOnly: true\n        openWorld: false\n      call:\
  \ uspto-tsdr.get-trademark-case-status\n      with:\n        type: json\n        sn: tools.serialNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-trademark-documents\n      description: List all documents filed in a trademark case including office actions and responses\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uspto-tsdr.get-case-document-list\n      with:\n        caseid: tools.caseId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-patent-status-codes\n      description: Get the full list of USPTO patent application status codes and their meanings\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uspto-odp.list-patent-status-codes\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: browse-bulk-datasets\n      description: Browse available USPTO bulk data products for economic research and analysis\n      hints:\n  \
  \      readOnly: true\n        openWorld: true\n      call: uspto-odp.search-dataset-products\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/us-patent-and-trademark-office/refs/heads/main/capabilities/intellectual-property-research.yaml
tags:
- Patents
- Trademarks
- Intellectual Property
- Federal Government
- Open Data
- Legal Research
tools:
- description: Search USPTO patent applications by keyword, inventor, assignee, or classification
  hints:
    openWorld: true
    readOnly: true
  name: search-patent-applications
- description: Get complete details for a specific patent application including inventors, assignees, and status
  hints:
    openWorld: false
    readOnly: true
  name: get-patent-application
- description: List all office actions, responses, and other documents filed in a patent application
  hints:
    openWorld: false
    readOnly: true
  name: get-patent-documents
- description: Search PTAB inter partes review (IPR), post-grant review (PGR), and covered business method (CBM) proceedings
  hints:
    openWorld: true
    readOnly: true
  name: search-ptab-proceedings
- description: Get full details of a PTAB trial including petitioner, respondent, and claim dispositions
  hints:
    openWorld: false
    readOnly: true
  name: get-ptab-proceeding
- description: Search PTAB final written decisions and institution decisions
  hints:
    openWorld: true
    readOnly: true
  name: search-ptab-decisions
- description: Get the current prosecution status and owner information for a trademark application or registration
  hints:
    openWorld: false
    readOnly: true
  name: get-trademark-status
- description: List all documents filed in a trademark case including office actions and responses
  hints:
    openWorld: false
    readOnly: true
  name: list-trademark-documents
- description: Get the full list of USPTO patent application status codes and their meanings
  hints:
    openWorld: false
    readOnly: true
  name: list-patent-status-codes
- description: Browse available USPTO bulk data products for economic research and analysis
  hints:
    openWorld: true
    readOnly: true
  name: browse-bulk-datasets
---
