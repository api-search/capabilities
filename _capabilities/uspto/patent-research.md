---
api_specs:
- filename: uspto-patent-api-openapi.yml
  format: yaml
  label: uspto-patent-api
  slug: uspto-patent-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/uspto/refs/heads/main/openapi/uspto-patent-api-openapi.yml
categories: []
consumed_apis:
- uspto-patent-api
description: Workflow capability for patent and trademark research using USPTO Open Data Portal APIs. Supports IP attorneys, patent engineers, researchers, and business analysts conducting prior art searches, patent landscape analysis, PTAB litigation monitoring, trademark clearance, and ownership due diligence through a unified REST and MCP interface.
layout: capability
name: USPTO Patent Research
operations:
- description: Search USPTO patent applications by keyword, inventor, assignee, or CPC class
  method: GET
  name: search-patent-applications
  path: /v1/patents
- description: Get complete patent application with claims, inventors, and prosecution history
  method: GET
  name: get-patent-application
  path: /v1/patents/{applicationNumber}
- description: Get full details for a granted patent
  method: GET
  name: get-granted-patent
  path: /v1/grants/{patentNumber}
- description: Search PTAB IPR, PGR, and CBM proceedings
  method: GET
  name: search-ptab-trials
  path: /v1/ptab/trials
- description: Get complete PTAB trial information
  method: GET
  name: get-ptab-trial
  path: /v1/ptab/trials/{trialNumber}
- description: Get trademark application status and prosecution history
  method: GET
  name: get-trademark-status
  path: /v1/trademarks/{serialNumber}/status
- description: Search recorded patent assignments and ownership transfers
  method: GET
  name: search-patent-assignments
  path: /v1/assignments
personas: []
provider_name: USPTO
provider_slug: uspto
search_terms:
- patent research
- regulatory
- open data
- ptab trial proceedings search
- search ptab trials
- search uspto patent applications by keyword, inventor, assignee, or cpc class
- search recorded patent assignments and ownership transfers
- government
- get ptab trial
- search patents
- get full details for a granted patent
- trademark status lookup
- due diligence
- get trademark application status and prosecution history
- search ptab inter partes review (ipr), post-grant review (pgr), and covered business method (cbm) trials. useful for patent validity research and litigation monitoring.
- retrieve a granted patent
- trademarks
- search patent assignments
- look up the current status and prosecution history for a uspto trademark application by serial number. use for trademark clearance research.
- retrieve complete details for a patent application including claims, inventors, assignees, cpc classifications, and prosecution history.
- intellectual property
- get patent application
- get complete patent application with claims, inventors, and prosecution history
- search the uspto patent database by keyword, inventor name, assignee, cpc classification code, filing date range, or patent type. use for prior art searches and patent landscape analysis.
- get trademark status
- get complete ptab trial information including contested claims, grounds of challenge, prior art references, and filed documents.
- get complete ptab trial information
- search ptab ipr, pgr, and cbm proceedings
- prior art
- search recorded patent assignments to trace ownership history and current ownership of patents. useful for m&a due diligence and freedom-to-operate analysis.
- ptab
- get granted patent
- retrieve full patent application details
- uspto
- patent assignment search
- get patent application details
- search patent applications
- patents
- search patent applications and granted patents
- get ptab trial details
- retrieve full details for a granted uspto patent including claims, grant date, expiration date, and complete bibliographic data.
slug: patent-research
source_filename: patent-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: USPTO Patent Research\n  description: >-\n    Workflow capability for patent and trademark research using USPTO Open Data\n    Portal APIs. Supports IP attorneys, patent engineers, researchers, and\n    business analysts conducting prior art searches, patent landscape analysis,\n    PTAB litigation monitoring, trademark clearance, and ownership due diligence\n    through a unified REST and MCP interface.\n  tags:\n    - Due Diligence\n    - Government\n    - Intellectual Property\n    - Open Data\n    - Patent Research\n    - Patents\n    - Prior Art\n    - PTAB\n    - Regulatory\n    - Trademarks\n    - USPTO\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      USPTO_API_KEY: USPTO_API_KEY\n\ncapability:\n  consumes:\n    - import: uspto-patent-api\n      location: ./shared/uspto-patent-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: patent-research-api\n\
  \      description: \"Unified REST API for USPTO patent and trademark research workflows.\"\n      resources:\n        - path: /v1/patents\n          name: patent-search\n          description: Search patent applications and granted patents\n          operations:\n            - method: GET\n              name: search-patent-applications\n              description: Search USPTO patent applications by keyword, inventor, assignee, or CPC class\n              call: \"uspto-patent-api.search-patent-applications\"\n              with:\n                query: \"rest.query\"\n                inventor: \"rest.inventor\"\n                assignee: \"rest.assignee\"\n                cpcClassification: \"rest.cpcClassification\"\n                patentType: \"rest.patentType\"\n                status: \"rest.status\"\n                filingDateStart: \"rest.filingDateStart\"\n                filingDateEnd: \"rest.filingDateEnd\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/patents/{applicationNumber}\n          name: patent-application-detail\n          description: Retrieve full patent application details\n          operations:\n            - method: GET\n              name: get-patent-application\n              description: Get complete patent application with claims, inventors, and prosecution history\n              call: \"uspto-patent-api.get-patent-application\"\n              with:\n                applicationNumber: \"rest.applicationNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/grants/{patentNumber}\n          name: granted-patent\n          description: Retrieve a granted patent\n          operations:\n            - method: GET\n              name: get-granted-patent\n              description: Get full details for a granted patent\n    \
  \          call: \"uspto-patent-api.get-granted-patent\"\n              with:\n                patentNumber: \"rest.patentNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ptab/trials\n          name: ptab-trials\n          description: PTAB trial proceedings search\n          operations:\n            - method: GET\n              name: search-ptab-trials\n              description: Search PTAB IPR, PGR, and CBM proceedings\n              call: \"uspto-patent-api.search-ptab-trials\"\n              with:\n                patentNumber: \"rest.patentNumber\"\n                petitionerName: \"rest.petitionerName\"\n                proceedingType: \"rest.proceedingType\"\n                status: \"rest.status\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ptab/trials/{trialNumber}\n          name:\
  \ ptab-trial-detail\n          description: Get PTAB trial details\n          operations:\n            - method: GET\n              name: get-ptab-trial\n              description: Get complete PTAB trial information\n              call: \"uspto-patent-api.get-ptab-trial\"\n              with:\n                trialNumber: \"rest.trialNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/trademarks/{serialNumber}/status\n          name: trademark-status\n          description: Trademark status lookup\n          operations:\n            - method: GET\n              name: get-trademark-status\n              description: Get trademark application status and prosecution history\n              call: \"uspto-patent-api.get-trademark-status\"\n              with:\n                serialNumber: \"rest.serialNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n\
  \        - path: /v1/assignments\n          name: patent-assignments\n          description: Patent assignment search\n          operations:\n            - method: GET\n              name: search-patent-assignments\n              description: Search recorded patent assignments and ownership transfers\n              call: \"uspto-patent-api.search-patent-assignments\"\n              with:\n                patentNumber: \"rest.patentNumber\"\n                assigneeName: \"rest.assigneeName\"\n                conveyanceType: \"rest.conveyanceType\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: patent-research-mcp\n      transport: http\n      description: \"MCP server for AI-assisted patent and trademark research.\"\n      tools:\n        - name: search-patents\n          description: >-\n            Search the USPTO patent database by keyword,\
  \ inventor name, assignee,\n            CPC classification code, filing date range, or patent type. Use for\n            prior art searches and patent landscape analysis.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uspto-patent-api.search-patent-applications\"\n          with:\n            query: \"tools.query\"\n            inventor: \"tools.inventor\"\n            assignee: \"tools.assignee\"\n            cpcClassification: \"tools.cpcClassification\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-patent-application-details\n          description: >-\n            Retrieve complete details for a patent application including claims,\n            inventors, assignees, CPC classifications, and prosecution history.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"uspto-patent-api.get-patent-application\"\
  \n          with:\n            applicationNumber: \"tools.applicationNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-granted-patent\n          description: >-\n            Retrieve full details for a granted USPTO patent including claims,\n            grant date, expiration date, and complete bibliographic data.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"uspto-patent-api.get-granted-patent\"\n          with:\n            patentNumber: \"tools.patentNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-ptab-trials\n          description: >-\n            Search PTAB inter partes review (IPR), post-grant review (PGR),\n            and covered business method (CBM) trials. Useful for patent validity\n            research and litigation monitoring.\n          hints:\n            readOnly: true\n     \
  \       openWorld: true\n          call: \"uspto-patent-api.search-ptab-trials\"\n          with:\n            patentNumber: \"tools.patentNumber\"\n            petitionerName: \"tools.petitionerName\"\n            proceedingType: \"tools.proceedingType\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-ptab-trial-details\n          description: >-\n            Get complete PTAB trial information including contested claims,\n            grounds of challenge, prior art references, and filed documents.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"uspto-patent-api.get-ptab-trial\"\n          with:\n            trialNumber: \"tools.trialNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-trademark-status\n          description: >-\n            Look up the current status and prosecution\
  \ history for a USPTO trademark\n            application by serial number. Use for trademark clearance research.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"uspto-patent-api.get-trademark-status\"\n          with:\n            serialNumber: \"tools.serialNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-patent-assignments\n          description: >-\n            Search recorded patent assignments to trace ownership history and\n            current ownership of patents. Useful for M&A due diligence and\n            freedom-to-operate analysis.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uspto-patent-api.search-patent-assignments\"\n          with:\n            patentNumber: \"tools.patentNumber\"\n            assigneeName: \"tools.assigneeName\"\n            conveyanceType: \"tools.conveyanceType\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/uspto/refs/heads/main/capabilities/patent-research.yaml
tags:
- Due Diligence
- Government
- Intellectual Property
- Open Data
- Patent Research
- Patents
- Prior Art
- PTAB
- Regulatory
- Trademarks
- USPTO
tools:
- description: Search the USPTO patent database by keyword, inventor name, assignee, CPC classification code, filing date range, or patent type. Use for prior art searches and patent landscape analysis.
  hints:
    openWorld: true
    readOnly: true
  name: search-patents
- description: Retrieve complete details for a patent application including claims, inventors, assignees, CPC classifications, and prosecution history.
  hints:
    idempotent: true
    readOnly: true
  name: get-patent-application-details
- description: Retrieve full details for a granted USPTO patent including claims, grant date, expiration date, and complete bibliographic data.
  hints:
    idempotent: true
    readOnly: true
  name: get-granted-patent
- description: Search PTAB inter partes review (IPR), post-grant review (PGR), and covered business method (CBM) trials. Useful for patent validity research and litigation monitoring.
  hints:
    openWorld: true
    readOnly: true
  name: search-ptab-trials
- description: Get complete PTAB trial information including contested claims, grounds of challenge, prior art references, and filed documents.
  hints:
    idempotent: true
    readOnly: true
  name: get-ptab-trial-details
- description: Look up the current status and prosecution history for a USPTO trademark application by serial number. Use for trademark clearance research.
  hints:
    idempotent: true
    readOnly: true
  name: get-trademark-status
- description: Search recorded patent assignments to trace ownership history and current ownership of patents. Useful for M&A due diligence and freedom-to-operate analysis.
  hints:
    openWorld: true
    readOnly: true
  name: search-patent-assignments
---
