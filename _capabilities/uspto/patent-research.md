---
categories: []
consumed_apis: []
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
- search recorded patent assignments and ownership transfers
- regulatory
- get full details for a granted patent
- retrieve full patent application details
- ptab trial proceedings search
- search patent applications and granted patents
- get complete patent application with claims, inventors, and prosecution history
- get ptab trial details
- patent research
- search patent applications
- search patent assignments
- retrieve complete details for a patent application including claims, inventors, assignees, cpc classifications, and prosecution history.
- retrieve a granted patent
- get trademark status
- get complete ptab trial information
- search ptab inter partes review (ipr), post-grant review (pgr), and covered business method (cbm) trials. useful for patent validity research and litigation monitoring.
- get complete ptab trial information including contested claims, grounds of challenge, prior art references, and filed documents.
- patents
- retrieve full details for a granted uspto patent including claims, grant date, expiration date, and complete bibliographic data.
- search recorded patent assignments to trace ownership history and current ownership of patents. useful for m&a due diligence and freedom-to-operate analysis.
- patent assignment search
- due diligence
- get granted patent
- get patent application details
- uspto
- search the uspto patent database by keyword, inventor name, assignee, cpc classification code, filing date range, or patent type. use for prior art searches and patent landscape analysis.
- government
- trademark status lookup
- get ptab trial
- search ptab trials
- look up the current status and prosecution history for a uspto trademark application by serial number. use for trademark clearance research.
- intellectual property
- search patents
- ptab
- search ptab ipr, pgr, and cbm proceedings
- trademarks
- open data
- search uspto patent applications by keyword, inventor, assignee, or cpc class
- prior art
- get patent application
- get trademark application status and prosecution history
slug: patent-research
source_filename: patent-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: USPTO Patent Research\n  description: Workflow capability for patent and trademark research using USPTO Open Data Portal APIs. Supports IP attorneys,\n    patent engineers, researchers, and business analysts conducting prior art searches, patent landscape analysis, PTAB litigation\n    monitoring, trademark clearance, and ownership due diligence through a unified REST and MCP interface.\n  tags:\n  - Due Diligence\n  - Government\n  - Intellectual Property\n  - Open Data\n  - Patent Research\n  - Patents\n  - Prior Art\n  - PTAB\n  - Regulatory\n  - Trademarks\n  - USPTO\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    USPTO_API_KEY: USPTO_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: uspto-patent-api\n    baseUri: https://data.uspto.gov/api/v1\n    description: USPTO Open Data Portal REST API\n    authentication:\n      type: apikey\n      key: X-API-KEY\n      value: '{{USPTO_API_KEY}}'\n\
  \      placement: header\n    resources:\n    - name: patent-applications\n      path: /patent/applications\n      description: Patent application search and retrieval\n      operations:\n      - name: search-patent-applications\n        method: GET\n        description: Search USPTO patent applications by keyword, inventor, assignee, and other criteria\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Keyword search query\n        - name: inventor\n          in: query\n          type: string\n          required: false\n          description: Inventor name\n        - name: assignee\n          in: query\n          type: string\n          required: false\n          description: Assignee company name\n        - name: filingDateStart\n          in: query\n          type: string\n          required: false\n          description: Filing date range start (YYYY-MM-DD)\n        - name: filingDateEnd\n\
  \          in: query\n          type: string\n          required: false\n          description: Filing date range end (YYYY-MM-DD)\n        - name: cpcClassification\n          in: query\n          type: string\n          required: false\n          description: CPC classification code\n        - name: patentType\n          in: query\n          type: string\n          required: false\n          description: Patent type (UTILITY, DESIGN, PLANT, REISSUE)\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Application status\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Results per page (max 100)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: get-patent-application\n        method: GET\n        description: Get full details for a specific patent application\n        inputParameters:\n        - name: applicationNumber\n          in: path\n          type: string\n          required: true\n          description: USPTO application number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patent-grants\n      path: /patent/grants\n      description: Granted patent retrieval\n      operations:\n      - name: get-granted-patent\n        method: GET\n        description: Get full details for a granted USPTO patent by patent number\n        inputParameters:\n        - name: patentNumber\n          in: path\n          type: string\n          required: true\n          description: USPTO patent number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: ptab-trials\n      path: /ptab/trials\n      description: PTAB trial proceeding search and retrieval\n      operations:\n      - name: search-ptab-trials\n        method: GET\n        description: Search PTAB IPR, PGR, and CBM trial proceedings\n        inputParameters:\n        - name: patentNumber\n          in: query\n          type: string\n          required: false\n          description: Challenged patent number\n        - name: petitionerName\n          in: query\n          type: string\n          required: false\n          description: Petitioner company name\n        - name: patentOwnerName\n          in: query\n          type: string\n          required: false\n          description: Patent owner name\n        - name: proceedingType\n          in: query\n          type: string\n          required: false\n          description: Proceeding type (IPR, PGR, CBM)\n        - name: status\n          in: query\n          type: string\n          required: false\n        \
  \  description: Trial status\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-ptab-trial\n        method: GET\n        description: Get full details for a specific PTAB trial proceeding\n        inputParameters:\n        - name: trialNumber\n          in: path\n          type: string\n          required: true\n          description: PTAB trial number (e.g., IPR2023-00001)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ptab-decisions\n      path: /ptab/decisions\n      description: PTAB decision search\n      operations:\n      - name: search-ptab-decisions\n        method: GET\n        description: Search PTAB decisions by trial number, date, or keyword\n        inputParameters:\n\
  \        - name: searchText\n          in: query\n          type: string\n          required: false\n          description: Full-text search in decision documents\n        - name: proceedingType\n          in: query\n          type: string\n          required: false\n          description: Proceeding type\n        - name: decisionType\n          in: query\n          type: string\n          required: false\n          description: Decision type\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trademark-status\n      path: /trademark/status\n      description: Trademark status lookup\n      operations:\n      - name: get-trademark-status\n        method: GET\n        description: Get current status and prosecution history for a trademark by serial number\n        inputParameters:\n\
  \        - name: serialNumber\n          in: path\n          type: string\n          required: true\n          description: Trademark serial number (8 digits)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patent-assignments\n      path: /patent/assignments\n      description: Patent assignment search\n      operations:\n      - name: search-patent-assignments\n        method: GET\n        description: Search recorded patent assignments and ownership transfers\n        inputParameters:\n        - name: patentNumber\n          in: query\n          type: string\n          required: false\n          description: Patent number\n        - name: assignorName\n          in: query\n          type: string\n          required: false\n          description: Assignor name\n        - name: assigneeName\n          in: query\n          type: string\n          required: false\n          description: Assignee name\n\
  \        - name: conveyanceType\n          in: query\n          type: string\n          required: false\n          description: Assignment type\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: patent-research-api\n    description: Unified REST API for USPTO patent and trademark research workflows.\n    resources:\n    - path: /v1/patents\n      name: patent-search\n      description: Search patent applications and granted patents\n      operations:\n      - method: GET\n        name: search-patent-applications\n        description: Search USPTO patent applications by keyword, inventor, assignee, or CPC class\n        call: uspto-patent-api.search-patent-applications\n        with:\n          query: rest.query\n    \
  \      inventor: rest.inventor\n          assignee: rest.assignee\n          cpcClassification: rest.cpcClassification\n          patentType: rest.patentType\n          status: rest.status\n          filingDateStart: rest.filingDateStart\n          filingDateEnd: rest.filingDateEnd\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/patents/{applicationNumber}\n      name: patent-application-detail\n      description: Retrieve full patent application details\n      operations:\n      - method: GET\n        name: get-patent-application\n        description: Get complete patent application with claims, inventors, and prosecution history\n        call: uspto-patent-api.get-patent-application\n        with:\n          applicationNumber: rest.applicationNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/grants/{patentNumber}\n      name: granted-patent\n\
  \      description: Retrieve a granted patent\n      operations:\n      - method: GET\n        name: get-granted-patent\n        description: Get full details for a granted patent\n        call: uspto-patent-api.get-granted-patent\n        with:\n          patentNumber: rest.patentNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ptab/trials\n      name: ptab-trials\n      description: PTAB trial proceedings search\n      operations:\n      - method: GET\n        name: search-ptab-trials\n        description: Search PTAB IPR, PGR, and CBM proceedings\n        call: uspto-patent-api.search-ptab-trials\n        with:\n          patentNumber: rest.patentNumber\n          petitionerName: rest.petitionerName\n          proceedingType: rest.proceedingType\n          status: rest.status\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ptab/trials/{trialNumber}\n      name: ptab-trial-detail\n\
  \      description: Get PTAB trial details\n      operations:\n      - method: GET\n        name: get-ptab-trial\n        description: Get complete PTAB trial information\n        call: uspto-patent-api.get-ptab-trial\n        with:\n          trialNumber: rest.trialNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trademarks/{serialNumber}/status\n      name: trademark-status\n      description: Trademark status lookup\n      operations:\n      - method: GET\n        name: get-trademark-status\n        description: Get trademark application status and prosecution history\n        call: uspto-patent-api.get-trademark-status\n        with:\n          serialNumber: rest.serialNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assignments\n      name: patent-assignments\n      description: Patent assignment search\n      operations:\n      - method: GET\n        name: search-patent-assignments\n\
  \        description: Search recorded patent assignments and ownership transfers\n        call: uspto-patent-api.search-patent-assignments\n        with:\n          patentNumber: rest.patentNumber\n          assigneeName: rest.assigneeName\n          conveyanceType: rest.conveyanceType\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: patent-research-mcp\n    transport: http\n    description: MCP server for AI-assisted patent and trademark research.\n    tools:\n    - name: search-patents\n      description: Search the USPTO patent database by keyword, inventor name, assignee, CPC classification code, filing date\n        range, or patent type. Use for prior art searches and patent landscape analysis.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uspto-patent-api.search-patent-applications\n      with:\n        query: tools.query\n        inventor: tools.inventor\n\
  \        assignee: tools.assignee\n        cpcClassification: tools.cpcClassification\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-patent-application-details\n      description: Retrieve complete details for a patent application including claims, inventors, assignees, CPC classifications,\n        and prosecution history.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: uspto-patent-api.get-patent-application\n      with:\n        applicationNumber: tools.applicationNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-granted-patent\n      description: Retrieve full details for a granted USPTO patent including claims, grant date, expiration date, and complete\n        bibliographic data.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: uspto-patent-api.get-granted-patent\n      with:\n        patentNumber: tools.patentNumber\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-ptab-trials\n      description: Search PTAB inter partes review (IPR), post-grant review (PGR), and covered business method (CBM) trials.\n        Useful for patent validity research and litigation monitoring.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uspto-patent-api.search-ptab-trials\n      with:\n        patentNumber: tools.patentNumber\n        petitionerName: tools.petitionerName\n        proceedingType: tools.proceedingType\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ptab-trial-details\n      description: Get complete PTAB trial information including contested claims, grounds of challenge, prior art references,\n        and filed documents.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: uspto-patent-api.get-ptab-trial\n      with:\n        trialNumber: tools.trialNumber\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-trademark-status\n      description: Look up the current status and prosecution history for a USPTO trademark application by serial number.\n        Use for trademark clearance research.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: uspto-patent-api.get-trademark-status\n      with:\n        serialNumber: tools.serialNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-patent-assignments\n      description: Search recorded patent assignments to trace ownership history and current ownership of patents. Useful\n        for M&A due diligence and freedom-to-operate analysis.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uspto-patent-api.search-patent-assignments\n      with:\n        patentNumber: tools.patentNumber\n        assigneeName: tools.assigneeName\n        conveyanceType: tools.conveyanceType\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
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
