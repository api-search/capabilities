---
categories: []
consumed_apis:
- uspto-odp
- uspto-tsdr
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
- open data
- legal research
- patent application search and retrieval
- get patent
- trademark case status
- federal government
- get full details of a ptab trial including petitioner, respondent, and claim dispositions
- patent application detail
- bulk data products
- list patent status codes
- get full patent application record
- get the full list of uspto patent application status codes and their meanings
- search ptab decisions
- list datasets
- intellectual property
- search uspto patent applications by keyword, inventor, assignee, or classification
- patent application documents
- get trademark case status by serial or registration number
- ptab trial final written decisions
- list all documents filed in a trademark case including office actions and responses
- search ptab trial decisions
- list all office actions, responses, and other documents filed in a patent application
- get patent documents
- get complete details for a specific patent application including inventors, assignees, and status
- trademark case documents
- search patent applications
- ptab inter partes review and post-grant review proceedings
- get ptab proceeding
- search ptab final written decisions and institution decisions
- ptab proceeding detail
- get the current prosecution status and owner information for a trademark application or registration
- get ptab proceeding by trial number
- patents
- search ptab inter partes review (ipr), post-grant review (pgr), and covered business method (cbm) proceedings
- get trademark status
- browse available uspto bulk data products
- search patents
- list documents for a trademark case
- search patent applications by query and filters
- list patent documents
- search ptab trial proceedings
- browse bulk datasets
- browse available uspto bulk data products for economic research and analysis
- list documents for a patent application
- list trademark documents
- trademarks
- search ptab proceedings
- get patent application
slug: intellectual-property-research
source_filename: intellectual-property-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"USPTO Intellectual Property Research\"\n  description: >-\n    Unified capability for intellectual property research, combining patent\n    application search, PTAB trial proceedings, and trademark status retrieval.\n    Supports IP attorneys, researchers, portfolio managers, and compliance teams.\n  tags:\n    - Patents\n    - Trademarks\n    - Intellectual Property\n    - Federal Government\n    - Open Data\n    - Legal Research\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      USPTO_ODP_API_KEY: USPTO_ODP_API_KEY\n      USPTO_TSDR_API_KEY: USPTO_TSDR_API_KEY\n\ncapability:\n  consumes:\n    - import: uspto-odp\n      location: ./shared/open-data-portal.yaml\n    - import: uspto-tsdr\n      location: ./shared/tsdr.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ip-research-api\n      description: \"Unified REST API for USPTO intellectual property research.\"\
  \n      resources:\n        - path: /v1/patents\n          name: patents\n          description: \"Patent application search and retrieval\"\n          operations:\n            - method: GET\n              name: search-patents\n              description: \"Search patent applications by query and filters\"\n              call: \"uspto-odp.list-patent-applications\"\n              with:\n                q: \"rest.q\"\n                start: \"rest.start\"\n                rows: \"rest.rows\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/patents/{applicationNumberText}\n          name: patent-detail\n          description: \"Patent application detail\"\n          operations:\n            - method: GET\n              name: get-patent\n              description: \"Get full patent application record\"\n              call: \"uspto-odp.get-patent-application\"\n              with:\n                applicationNumberText:\
  \ \"rest.applicationNumberText\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/patents/{applicationNumberText}/documents\n          name: patent-documents\n          description: \"Patent application documents\"\n          operations:\n            - method: GET\n              name: list-patent-documents\n              description: \"List documents for a patent application\"\n              call: \"uspto-odp.get-patent-application-documents\"\n              with:\n                applicationNumberText: \"rest.applicationNumberText\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ptab/proceedings\n          name: ptab-proceedings\n          description: \"PTAB inter partes review and post-grant review proceedings\"\n          operations:\n            - method: GET\n              name: search-ptab-proceedings\n              description: \"Search\
  \ PTAB trial proceedings\"\n              call: \"uspto-odp.search-ptab-proceedings\"\n              with:\n                q: \"rest.q\"\n                start: \"rest.start\"\n                rows: \"rest.rows\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ptab/proceedings/{trialNumber}\n          name: ptab-proceeding\n          description: \"PTAB proceeding detail\"\n          operations:\n            - method: GET\n              name: get-ptab-proceeding\n              description: \"Get PTAB proceeding by trial number\"\n              call: \"uspto-odp.get-ptab-proceeding\"\n              with:\n                trialNumber: \"rest.trialNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ptab/decisions\n          name: ptab-decisions\n          description: \"PTAB trial final written decisions\"\n          operations:\n        \
  \    - method: GET\n              name: search-ptab-decisions\n              description: \"Search PTAB trial decisions\"\n              call: \"uspto-odp.search-ptab-decisions\"\n              with:\n                q: \"rest.q\"\n                start: \"rest.start\"\n                rows: \"rest.rows\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/trademarks/{caseId}/status\n          name: trademark-status\n          description: \"Trademark case status\"\n          operations:\n            - method: GET\n              name: get-trademark-status\n              description: \"Get trademark case status by serial or registration number\"\n              call: \"uspto-tsdr.get-trademark-case-status\"\n              with:\n                type: \"json\"\n                sn: \"rest.caseId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/trademarks/{caseId}/documents\n\
  \          name: trademark-documents\n          description: \"Trademark case documents\"\n          operations:\n            - method: GET\n              name: list-trademark-documents\n              description: \"List documents for a trademark case\"\n              call: \"uspto-tsdr.get-case-document-list\"\n              with:\n                caseid: \"rest.caseId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/datasets\n          name: datasets\n          description: \"Bulk data products\"\n          operations:\n            - method: GET\n              name: list-datasets\n              description: \"Browse available USPTO bulk data products\"\n              call: \"uspto-odp.search-dataset-products\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace:\
  \ ip-research-mcp\n      transport: http\n      description: \"MCP server for AI-assisted USPTO intellectual property research.\"\n      tools:\n        - name: search-patent-applications\n          description: \"Search USPTO patent applications by keyword, inventor, assignee, or classification\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uspto-odp.list-patent-applications\"\n          with:\n            q: \"tools.q\"\n            start: \"tools.start\"\n            rows: \"tools.rows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-patent-application\n          description: \"Get complete details for a specific patent application including inventors, assignees, and status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uspto-odp.get-patent-application\"\n          with:\n            applicationNumberText: \"tools.applicationNumberText\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-patent-documents\n          description: \"List all office actions, responses, and other documents filed in a patent application\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uspto-odp.get-patent-application-documents\"\n          with:\n            applicationNumberText: \"tools.applicationNumberText\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-ptab-proceedings\n          description: \"Search PTAB inter partes review (IPR), post-grant review (PGR), and covered business method (CBM) proceedings\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uspto-odp.search-ptab-proceedings\"\n          with:\n            q: \"tools.q\"\n            start: \"tools.start\"\n            rows: \"tools.rows\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-ptab-proceeding\n          description: \"Get full details of a PTAB trial including petitioner, respondent, and claim dispositions\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uspto-odp.get-ptab-proceeding\"\n          with:\n            trialNumber: \"tools.trialNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-ptab-decisions\n          description: \"Search PTAB final written decisions and institution decisions\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uspto-odp.search-ptab-decisions\"\n          with:\n            q: \"tools.q\"\n            start: \"tools.start\"\n            rows: \"tools.rows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-trademark-status\n      \
  \    description: \"Get the current prosecution status and owner information for a trademark application or registration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uspto-tsdr.get-trademark-case-status\"\n          with:\n            type: \"json\"\n            sn: \"tools.serialNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-trademark-documents\n          description: \"List all documents filed in a trademark case including office actions and responses\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uspto-tsdr.get-case-document-list\"\n          with:\n            caseid: \"tools.caseId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-patent-status-codes\n          description: \"Get the full list of USPTO patent application status codes and their meanings\"\
  \n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uspto-odp.list-patent-status-codes\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: browse-bulk-datasets\n          description: \"Browse available USPTO bulk data products for economic research and analysis\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uspto-odp.search-dataset-products\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
