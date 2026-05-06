---
categories: []
consumed_apis: []
description: Unified capability for lobbying disclosure research and transparency, combining access to LDA filings, registrant profiles, client information, and lobbyist records. Supports investigative journalists, researchers, compliance teams, and transparency advocates.
layout: capability
name: US Senate Lobbying Transparency
operations:
- description: Search lobbying disclosure filings
  method: GET
  name: search-filings
  path: /v1/filings
- description: Get a specific filing by UUID
  method: GET
  name: get-filing
  path: /v1/filings/{filing_uuid}
- description: Search lobbying registrants
  method: GET
  name: search-registrants
  path: /v1/registrants
- description: Search lobbying clients
  method: GET
  name: search-clients
  path: /v1/clients
- description: Search individual lobbyists
  method: GET
  name: search-lobbyists
  path: /v1/lobbyists
- description: Get all lobbying activity issue codes
  method: GET
  name: list-issue-codes
  path: /v1/reference/issues
- description: Get all government entity codes
  method: GET
  name: list-government-entities
  path: /v1/reference/government-entities
personas: []
provider_name: US Senate
provider_slug: us-senate
search_terms:
- search clients
- lobbying issue codes
- individual filing detail
- search individual lobbyists
- search lobbying disclosure filings
- get complete details of a specific lobbying disclosure filing including activities and lobbyists
- individual lobbyists
- get all government entity codes
- list lobbying issue codes
- get all issue area codes used to categorize lobbying activities (e.g., tax, hcr, def)
- get lobbying filing
- lobbying registrants
- search lobbyists
- search senate lobbying disclosure filings (ld-1 registrations, ld-2 quarterly reports). filter by year, period, registrant name, client name, or issue code.
- search individual registered lobbyists by name
- lobbying disclosure filings
- campaign finance
- get filing
- search filings
- search lobbying registrants
- search organizations and entities that have hired lobbyists
- list government entities
- lobbying clients
- get all lobbying activity issue codes
- search registered lobbying firms and individual lobbyists by name
- list issue codes
- federal government
- lobbied government entities
- search lobbying clients
- lobbying
- get all government bodies and agencies that appear as lobbying targets
- get a specific filing by uuid
- search registrants
- government transparency
- open data
- search lobbying filings
slug: lobbying-transparency
source_filename: lobbying-transparency.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: US Senate Lobbying Transparency\n  description: Unified capability for lobbying disclosure research and transparency, combining access to LDA filings, registrant\n    profiles, client information, and lobbyist records. Supports investigative journalists, researchers, compliance teams,\n    and transparency advocates.\n  tags:\n  - Lobbying\n  - Government Transparency\n  - Federal Government\n  - Open Data\n  - Campaign Finance\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    LDA_API_KEY: LDA_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: senate-lda\n    baseUri: https://lda.senate.gov/api/v1\n    description: Senate LDA REST API for lobbying disclosure data.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Token {{LDA_API_KEY}}\n      placement: header\n    resources:\n    - name: filings\n      path: /filings/\n      description: Lobbying disclosure\
  \ filings\n      operations:\n      - name: list-filings\n        method: GET\n        description: List lobbying disclosure filings with filtering\n        inputParameters:\n        - name: filing_type\n          in: query\n          type: string\n          required: false\n          description: Filing type code\n        - name: filing_year\n          in: query\n          type: integer\n          required: false\n          description: Year of filing\n        - name: registrant_name\n          in: query\n          type: string\n          required: false\n          description: Registrant name filter\n        - name: client_name\n          in: query\n          type: string\n          required: false\n          description: Client name filter\n        - name: issue_code\n          in: query\n          type: string\n          required: false\n          description: Lobbying issue code\n        - name: page\n          in: query\n          type: integer\n          required: false\n      \
  \    description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filing-detail\n      path: /filings/{filing_uuid}/\n      description: Individual filing record\n      operations:\n      - name: get-filing\n        method: GET\n        description: Get a specific filing by UUID\n        inputParameters:\n        - name: filing_uuid\n          in: path\n          type: string\n          required: true\n          description: Filing UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: registrants\n      path: /registrants/\n      description: Lobbying registrants\n      operations:\n      - name: list-registrants\n        method: GET\n        description: List lobbying registrants\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: false\n\
  \          description: Name filter\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-registrant\n        method: GET\n        description: Get a specific registrant by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Registrant ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clients\n      path: /clients/\n      description: Lobbying clients\n      operations:\n      - name: list-clients\n        method: GET\n        description: List lobbying clients\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: false\n    \
  \      description: Name filter\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lobbyists\n      path: /lobbyists/\n      description: Individual lobbyists\n      operations:\n      - name: list-lobbyists\n        method: GET\n        description: List lobbyists\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Name filter\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: constants-issues\n      path: /constants/filing/lobbyingactivityissues/\n      description:\
  \ Lobbying issue codes\n      operations:\n      - name: list-lobbying-issues\n        method: GET\n        description: Get all lobbying activity issue codes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: constants-government\n      path: /constants/filing/governmententities/\n      description: Government entity codes\n      operations:\n      - name: list-government-entities\n        method: GET\n        description: Get all lobbied government entity codes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lobbying-transparency-api\n    description: Unified REST API for Senate lobbying disclosure research.\n    resources:\n    - path: /v1/filings\n      name: filings\n      description: Lobbying disclosure filings\n      operations:\n      - method: GET\n    \
  \    name: search-filings\n        description: Search lobbying disclosure filings\n        call: senate-lda.list-filings\n        with:\n          filing_year: rest.filing_year\n          filing_type: rest.filing_type\n          issue_code: rest.issue_code\n          registrant_name: rest.registrant_name\n          client_name: rest.client_name\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/filings/{filing_uuid}\n      name: filing\n      description: Individual filing detail\n      operations:\n      - method: GET\n        name: get-filing\n        description: Get a specific filing by UUID\n        call: senate-lda.get-filing\n        with:\n          filing_uuid: rest.filing_uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/registrants\n      name: registrants\n      description: Lobbying registrants\n      operations:\n      - method: GET\n        name: search-registrants\n\
  \        description: Search lobbying registrants\n        call: senate-lda.list-registrants\n        with:\n          name: rest.name\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clients\n      name: clients\n      description: Lobbying clients\n      operations:\n      - method: GET\n        name: search-clients\n        description: Search lobbying clients\n        call: senate-lda.list-clients\n        with:\n          name: rest.name\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lobbyists\n      name: lobbyists\n      description: Individual lobbyists\n      operations:\n      - method: GET\n        name: search-lobbyists\n        description: Search individual lobbyists\n        call: senate-lda.list-lobbyists\n        with:\n          name: rest.name\n          page: rest.page\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n    - path: /v1/reference/issues\n      name: issue-codes\n      description: Lobbying issue codes\n      operations:\n      - method: GET\n        name: list-issue-codes\n        description: Get all lobbying activity issue codes\n        call: senate-lda.list-lobbying-issues\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/reference/government-entities\n      name: government-entities\n      description: Lobbied government entities\n      operations:\n      - method: GET\n        name: list-government-entities\n        description: Get all government entity codes\n        call: senate-lda.list-government-entities\n        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: lobbying-transparency-mcp\n    transport: http\n    description: MCP server for AI-assisted lobbying disclosure research.\n    tools:\n    - name: search-lobbying-filings\n      description: Search Senate\
  \ lobbying disclosure filings (LD-1 registrations, LD-2 quarterly reports). Filter by year,\n        period, registrant name, client name, or issue code.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: senate-lda.list-filings\n      with:\n        filing_year: tools.filing_year\n        filing_type: tools.filing_type\n        issue_code: tools.issue_code\n        registrant_name: tools.registrant_name\n        client_name: tools.client_name\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-lobbying-filing\n      description: Get complete details of a specific lobbying disclosure filing including activities and lobbyists\n      hints:\n        readOnly: true\n        openWorld: false\n      call: senate-lda.get-filing\n      with:\n        filing_uuid: tools.filing_uuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-lobbying-registrants\n      description: Search\
  \ registered lobbying firms and individual lobbyists by name\n      hints:\n        readOnly: true\n        openWorld: true\n      call: senate-lda.list-registrants\n      with:\n        name: tools.name\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-lobbying-clients\n      description: Search organizations and entities that have hired lobbyists\n      hints:\n        readOnly: true\n        openWorld: true\n      call: senate-lda.list-clients\n      with:\n        name: tools.name\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-lobbyists\n      description: Search individual registered lobbyists by name\n      hints:\n        readOnly: true\n        openWorld: true\n      call: senate-lda.list-lobbyists\n      with:\n        name: tools.name\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-lobbying-issue-codes\n\
  \      description: Get all issue area codes used to categorize lobbying activities (e.g., TAX, HCR, DEF)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: senate-lda.list-lobbying-issues\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-government-entities\n      description: Get all government bodies and agencies that appear as lobbying targets\n      hints:\n        readOnly: true\n        openWorld: false\n      call: senate-lda.list-government-entities\n      outputParameters:\n      - type: array\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/us-senate/refs/heads/main/capabilities/lobbying-transparency.yaml
tags:
- Lobbying
- Government Transparency
- Federal Government
- Open Data
- Campaign Finance
tools:
- description: Search Senate lobbying disclosure filings (LD-1 registrations, LD-2 quarterly reports). Filter by year, period, registrant name, client name, or issue code.
  hints:
    openWorld: true
    readOnly: true
  name: search-lobbying-filings
- description: Get complete details of a specific lobbying disclosure filing including activities and lobbyists
  hints:
    openWorld: false
    readOnly: true
  name: get-lobbying-filing
- description: Search registered lobbying firms and individual lobbyists by name
  hints:
    openWorld: true
    readOnly: true
  name: search-lobbying-registrants
- description: Search organizations and entities that have hired lobbyists
  hints:
    openWorld: true
    readOnly: true
  name: search-lobbying-clients
- description: Search individual registered lobbyists by name
  hints:
    openWorld: true
    readOnly: true
  name: search-lobbyists
- description: Get all issue area codes used to categorize lobbying activities (e.g., TAX, HCR, DEF)
  hints:
    openWorld: false
    readOnly: true
  name: list-lobbying-issue-codes
- description: Get all government bodies and agencies that appear as lobbying targets
  hints:
    openWorld: false
    readOnly: true
  name: list-government-entities
---
