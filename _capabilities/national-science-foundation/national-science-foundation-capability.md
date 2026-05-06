---
categories: []
consumed_apis: []
description: The NSF Research Spending and Results Web API provides programmatic access to the award search functionality available through Research.gov. The API exposes how federal research dollars are being spent, what research is being performed, and project outcomes that result from NSF-funded work.
layout: capability
name: National Science Foundation Awards API
operations:
- description: Search awards
  method: GET
  name: get-awards-format
  path: /awards.{format}
- description: Retrieve a single award
  method: GET
  name: get-awards-id-format
  path: /awards/{id}.{format}
- description: Retrieve project outcomes for an award
  method: GET
  name: get-awards-id-projectoutcomes-format
  path: /awards/{id}/projectoutcomes.{format}
personas: []
provider_name: National Science Foundation
provider_slug: national-science-foundation
search_terms:
- retrieve project outcomes for an award
- get awards id format
- federal government
- search awards
- national
- research
- api
- foundation
- retrieve a single award
- science
- get awards format
- get awards id projectoutcomes format
slug: national-science-foundation-capability
source_filename: national-science-foundation-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: National Science Foundation Awards API\n  description: The NSF Research Spending and Results Web API provides programmatic access to the award search functionality\n    available through Research.gov. The API exposes how federal research dollars are being spent, what research is being performed,\n    and project outcomes that result from NSF-funded work.\n  tags:\n  - National\n  - Science\n  - Foundation\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: national-science-foundation\n    baseUri: https://api.nsf.gov/services/v1\n    description: National Science Foundation Awards API HTTP API.\n    resources:\n    - name: awards-format\n      path: /awards.{format}\n      operations:\n      - name: get-awards-format\n        method: GET\n        description: Search awards\n        inputParameters:\n        - name: format\n          in: path\n          type: string\n   \
  \       required: true\n        - name: keyword\n          in: query\n          type: string\n          description: Free-text search supporting Boolean AND, OR, NOT.\n        - name: rpp\n          in: query\n          type: integer\n          description: Results per page.\n        - name: offset\n          in: query\n          type: integer\n          description: Starting record offset for pagination.\n        - name: sortKey\n          in: query\n          type: string\n        - name: sortDirection\n          in: query\n          type: string\n        - name: dateStart\n          in: query\n          type: string\n          description: Award date start (mm/dd/yyyy).\n        - name: dateEnd\n          in: query\n          type: string\n        - name: startDateStart\n          in: query\n          type: string\n        - name: startDateEnd\n          in: query\n          type: string\n        - name: expDateStart\n          in: query\n          type: string\n        - name: expDateEnd\n\
  \          in: query\n          type: string\n        - name: estimatedTotalAmtFrom\n          in: query\n          type: number\n        - name: estimatedTotalAmtTo\n          in: query\n          type: number\n        - name: fundsObligatedAmtFrom\n          in: query\n          type: number\n        - name: fundsObligatedAmtTo\n          in: query\n          type: number\n        - name: awardeeName\n          in: query\n          type: string\n        - name: awardeeCity\n          in: query\n          type: string\n        - name: awardeeStateCode\n          in: query\n          type: string\n        - name: awardeeZipCode\n          in: query\n          type: string\n        - name: perfCity\n          in: query\n          type: string\n        - name: perfStateCode\n          in: query\n          type: string\n        - name: perfLocation\n          in: query\n          type: string\n        - name: pdPIName\n          in: query\n          type: string\n        - name: coPDPI\n\
  \          in: query\n          type: string\n        - name: poName\n          in: query\n          type: string\n        - name: org_code_dir\n          in: query\n          type: string\n        - name: org_code_div\n          in: query\n          type: string\n        - name: progEleCode\n          in: query\n          type: string\n        - name: ActiveAwards\n          in: query\n          type: boolean\n        - name: ExpiredAwards\n          in: query\n          type: boolean\n        - name: histAwd\n          in: query\n          type: boolean\n        - name: transType\n          in: query\n          type: string\n        - name: callback\n          in: query\n          type: string\n          description: JSONP callback name (when format is json).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: awards-id-format\n      path: /awards/{id}.{format}\n      operations:\n      - name: get-awards-id-format\n\
  \        method: GET\n        description: Retrieve a single award\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: NSF award number.\n        - name: format\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: awards-id-projectoutcomes-format\n      path: /awards/{id}/projectoutcomes.{format}\n      operations:\n      - name: get-awards-id-projectoutcomes-format\n        method: GET\n        description: Retrieve project outcomes for an award\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: format\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: national-science-foundation-rest\n    description: REST adapter for National Science Foundation Awards API.\n    resources:\n    - path: /awards.{format}\n      name: get-awards-format\n      operations:\n      - method: GET\n        name: get-awards-format\n        description: Search awards\n        call: national-science-foundation.get-awards-format\n        with:\n          format: rest.format\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /awards/{id}.{format}\n      name: get-awards-id-format\n      operations:\n      - method: GET\n        name: get-awards-id-format\n        description: Retrieve a single award\n        call: national-science-foundation.get-awards-id-format\n        with:\n          id: rest.id\n          format: rest.format\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /awards/{id}/projectoutcomes.{format}\n\
  \      name: get-awards-id-projectoutcomes-format\n      operations:\n      - method: GET\n        name: get-awards-id-projectoutcomes-format\n        description: Retrieve project outcomes for an award\n        call: national-science-foundation.get-awards-id-projectoutcomes-format\n        with:\n          id: rest.id\n          format: rest.format\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: national-science-foundation-mcp\n    transport: http\n    description: MCP adapter for National Science Foundation Awards API for AI agent use.\n    tools:\n    - name: get-awards-format\n      description: Search awards\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-science-foundation.get-awards-format\n      with:\n        format: tools.format\n        keyword: tools.keyword\n        rpp: tools.rpp\n        offset: tools.offset\n        sortKey: tools.sortKey\n\
  \        sortDirection: tools.sortDirection\n        dateStart: tools.dateStart\n        dateEnd: tools.dateEnd\n        startDateStart: tools.startDateStart\n        startDateEnd: tools.startDateEnd\n        expDateStart: tools.expDateStart\n        expDateEnd: tools.expDateEnd\n        estimatedTotalAmtFrom: tools.estimatedTotalAmtFrom\n        estimatedTotalAmtTo: tools.estimatedTotalAmtTo\n        fundsObligatedAmtFrom: tools.fundsObligatedAmtFrom\n        fundsObligatedAmtTo: tools.fundsObligatedAmtTo\n        awardeeName: tools.awardeeName\n        awardeeCity: tools.awardeeCity\n        awardeeStateCode: tools.awardeeStateCode\n        awardeeZipCode: tools.awardeeZipCode\n        perfCity: tools.perfCity\n        perfStateCode: tools.perfStateCode\n        perfLocation: tools.perfLocation\n        pdPIName: tools.pdPIName\n        coPDPI: tools.coPDPI\n        poName: tools.poName\n        org_code_dir: tools.org_code_dir\n        org_code_div: tools.org_code_div\n        progEleCode:\
  \ tools.progEleCode\n        ActiveAwards: tools.ActiveAwards\n        ExpiredAwards: tools.ExpiredAwards\n        histAwd: tools.histAwd\n        transType: tools.transType\n        callback: tools.callback\n      inputParameters:\n      - name: format\n        type: string\n        description: format\n        required: true\n      - name: keyword\n        type: string\n        description: Free-text search supporting Boolean AND, OR, NOT.\n      - name: rpp\n        type: integer\n        description: Results per page.\n      - name: offset\n        type: integer\n        description: Starting record offset for pagination.\n      - name: sortKey\n        type: string\n        description: sortKey\n      - name: sortDirection\n        type: string\n        description: sortDirection\n      - name: dateStart\n        type: string\n        description: Award date start (mm/dd/yyyy).\n      - name: dateEnd\n        type: string\n        description: dateEnd\n      - name: startDateStart\n\
  \        type: string\n        description: startDateStart\n      - name: startDateEnd\n        type: string\n        description: startDateEnd\n      - name: expDateStart\n        type: string\n        description: expDateStart\n      - name: expDateEnd\n        type: string\n        description: expDateEnd\n      - name: estimatedTotalAmtFrom\n        type: number\n        description: estimatedTotalAmtFrom\n      - name: estimatedTotalAmtTo\n        type: number\n        description: estimatedTotalAmtTo\n      - name: fundsObligatedAmtFrom\n        type: number\n        description: fundsObligatedAmtFrom\n      - name: fundsObligatedAmtTo\n        type: number\n        description: fundsObligatedAmtTo\n      - name: awardeeName\n        type: string\n        description: awardeeName\n      - name: awardeeCity\n        type: string\n        description: awardeeCity\n      - name: awardeeStateCode\n        type: string\n        description: awardeeStateCode\n      - name: awardeeZipCode\n\
  \        type: string\n        description: awardeeZipCode\n      - name: perfCity\n        type: string\n        description: perfCity\n      - name: perfStateCode\n        type: string\n        description: perfStateCode\n      - name: perfLocation\n        type: string\n        description: perfLocation\n      - name: pdPIName\n        type: string\n        description: pdPIName\n      - name: coPDPI\n        type: string\n        description: coPDPI\n      - name: poName\n        type: string\n        description: poName\n      - name: org_code_dir\n        type: string\n        description: org_code_dir\n      - name: org_code_div\n        type: string\n        description: org_code_div\n      - name: progEleCode\n        type: string\n        description: progEleCode\n      - name: ActiveAwards\n        type: boolean\n        description: ActiveAwards\n      - name: ExpiredAwards\n        type: boolean\n        description: ExpiredAwards\n      - name: histAwd\n        type: boolean\n\
  \        description: histAwd\n      - name: transType\n        type: string\n        description: transType\n      - name: callback\n        type: string\n        description: JSONP callback name (when format is json).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-awards-id-format\n      description: Retrieve a single award\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-science-foundation.get-awards-id-format\n      with:\n        id: tools.id\n        format: tools.format\n      inputParameters:\n      - name: id\n        type: string\n        description: NSF award number.\n        required: true\n      - name: format\n        type: string\n        description: format\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-awards-id-projectoutcomes-format\n      description: Retrieve project outcomes for an award\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-science-foundation.get-awards-id-projectoutcomes-format\n      with:\n        id: tools.id\n        format: tools.format\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      - name: format\n        type: string\n        description: format\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/national-science-foundation/refs/heads/main/capabilities/national-science-foundation-capability.yaml
tags:
- National
- Science
- Foundation
- API
tools:
- description: Search awards
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-awards-format
- description: Retrieve a single award
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-awards-id-format
- description: Retrieve project outcomes for an award
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-awards-id-projectoutcomes-format
---
