---
categories: []
consumed_apis: []
description: Workflow capability for trademark research and brand protection using the USPTO Trademark Search API. Supports legal professionals, brand managers, startup founders, and IP attorneys conducting trademark availability checks, competitive brand portfolio research, and ownership due diligence through a unified REST and MCP interface.
layout: capability
name: USPTO Trademark Research
operations:
- description: Search active or all trademarks matching a keyword
  method: GET
  name: search-trademarks
  path: /v1/trademarks
- description: Returns availability status and list of conflicting marks
  method: GET
  name: check-trademark-availability
  path: /v1/trademarks/availability/{keyword}
- description: Get full trademark filing details, prosecution history, and owner info
  method: GET
  name: get-trademark-by-serial-number
  path: /v1/trademarks/{serialNumber}
- description: List all trademarks owned by an individual or organization
  method: GET
  name: search-trademarks-by-owner
  path: /v1/owners/{owner}/trademarks
- description: Verify database is current before conducting research
  method: GET
  name: get-database-status
  path: /v1/database/status
personas: []
provider_name: USPTO Trademark Search API
provider_slug: uspto-trademark-search-api
search_terms:
- due diligence
- get full trademark filing details, prosecution history, and owner info
- verify database is current before conducting research
- list all trademarks owned by an individual or organization
- uspto
- legal
- research owner trademark portfolio
- check if a trademark keyword is available for registration
- get database status
- business
- search trademarks
- intellectual property
- government data
- check when the uspto trademark database was last updated and verify it is operating normally before running trademark research queries.
- returns availability status and list of conflicting marks
- search the uspto trademark database for marks matching a keyword. use this to find existing trademarks before registering a new brand name.
- trademark
- retrieve complete trademark details by serial number
- search active or all trademarks matching a keyword
- search
- get trademark by serial number
- find all trademarks owned by a specific company or individual. useful for competitive intelligence and m&a due diligence.
- search trademarks by owner
- search uspto trademark database by keyword
- research trademark portfolio of a specific owner
- check trademark availability
- legal research
- check whether a trademark keyword appears to be available for registration. returns availability status and any conflicting marks found in the uspto database.
- data
- brand protection
- uspto trademark database status
- brand
- retrieve complete trademark details for a known serial number, including prosecution history, owner details, and goods/services classification.
slug: trademark-research
source_filename: trademark-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: USPTO Trademark Research\n  description: Workflow capability for trademark research and brand protection using the USPTO Trademark Search API. Supports\n    legal professionals, brand managers, startup founders, and IP attorneys conducting trademark availability checks, competitive\n    brand portfolio research, and ownership due diligence through a unified REST and MCP interface.\n  tags:\n  - Brand Protection\n  - Due Diligence\n  - Intellectual Property\n  - Legal Research\n  - Trademark\n  - USPTO\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RAPIDAPI_KEY: RAPIDAPI_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: uspto-trademark-search\n    baseUri: https://uspto-trademark.p.rapidapi.com\n    description: USPTO Trademark Search API via RapidAPI\n    authentication:\n      type: apikey\n      key: X-RapidAPI-Key\n      value: '{{RAPIDAPI_KEY}}'\n      placement: header\n    resources:\n\
  \    - name: trademark-search\n      path: /v1/trademarkSearch\n      description: Search trademarks by keyword\n      operations:\n      - name: search-trademarks\n        method: GET\n        description: Search active or all trademarks by keyword\n        inputParameters:\n        - name: keyword\n          in: path\n          type: string\n          required: true\n          description: Trademark keyword to search for\n        - name: searchType\n          in: path\n          type: string\n          required: true\n          description: Search type (active or all)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trademark-availability\n      path: /v1/trademarkAvailable\n      description: Check trademark availability\n      operations:\n      - name: check-trademark-availability\n        method: GET\n        description: Check if a trademark keyword is available for registration\n        inputParameters:\n\
  \        - name: keyword\n          in: path\n          type: string\n          required: true\n          description: Trademark keyword to check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trademark-lookup\n      path: /v1/trademarkBySerial\n      description: Look up trademark by serial number\n      operations:\n      - name: get-trademark-by-serial-number\n        method: GET\n        description: Retrieve full trademark details by USPTO serial number\n        inputParameters:\n        - name: serialNumber\n          in: path\n          type: string\n          required: true\n          description: USPTO trademark serial number (8 digits)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trademark-owner-search\n      path: /v1/trademarkOwner\n      description: Search trademarks by owner name\n    \
  \  operations:\n      - name: search-trademarks-by-owner\n        method: GET\n        description: Find all trademarks owned by a specific individual or organization\n        inputParameters:\n        - name: owner\n          in: path\n          type: string\n          required: true\n          description: Owner name to search for\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: database-status\n      path: /v1/databaseStatus\n      description: Database freshness and health\n      operations:\n      - name: get-database-status\n        method: GET\n        description: Get current database update status and record count\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n\
  \  - type: rest\n    port: 8080\n    namespace: trademark-research-api\n    description: Unified REST API for trademark research and brand protection workflows.\n    resources:\n    - path: /v1/trademarks\n      name: trademark-search\n      description: Search USPTO trademark database by keyword\n      operations:\n      - method: GET\n        name: search-trademarks\n        description: Search active or all trademarks matching a keyword\n        call: uspto-trademark-search.search-trademarks\n        with:\n          keyword: rest.keyword\n          searchType: rest.searchType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trademarks/availability/{keyword}\n      name: trademark-availability\n      description: Check if a trademark keyword is available for registration\n      operations:\n      - method: GET\n        name: check-trademark-availability\n        description: Returns availability status and list of conflicting marks\n       \
  \ call: uspto-trademark-search.check-trademark-availability\n        with:\n          keyword: rest.keyword\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trademarks/{serialNumber}\n      name: trademark-detail\n      description: Retrieve complete trademark details by serial number\n      operations:\n      - method: GET\n        name: get-trademark-by-serial-number\n        description: Get full trademark filing details, prosecution history, and owner info\n        call: uspto-trademark-search.get-trademark-by-serial-number\n        with:\n          serialNumber: rest.serialNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/owners/{owner}/trademarks\n      name: owner-portfolio\n      description: Research trademark portfolio of a specific owner\n      operations:\n      - method: GET\n        name: search-trademarks-by-owner\n        description: List all trademarks owned by an individual or organization\n\
  \        call: uspto-trademark-search.search-trademarks-by-owner\n        with:\n          owner: rest.owner\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/database/status\n      name: database-status\n      description: USPTO trademark database status\n      operations:\n      - method: GET\n        name: get-database-status\n        description: Verify database is current before conducting research\n        call: uspto-trademark-search.get-database-status\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: trademark-research-mcp\n    transport: http\n    description: MCP server for AI-assisted trademark research and brand protection.\n    tools:\n    - name: search-trademarks\n      description: Search the USPTO trademark database for marks matching a keyword. Use this to find existing trademarks\n        before registering a new brand name.\n  \
  \    hints:\n        readOnly: true\n        openWorld: true\n      call: uspto-trademark-search.search-trademarks\n      with:\n        keyword: tools.keyword\n        searchType: tools.searchType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-trademark-availability\n      description: Check whether a trademark keyword appears to be available for registration. Returns availability status\n        and any conflicting marks found in the USPTO database.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uspto-trademark-search.check-trademark-availability\n      with:\n        keyword: tools.keyword\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-trademark-by-serial-number\n      description: Retrieve complete trademark details for a known serial number, including prosecution history, owner details,\n        and goods/services classification.\n      hints:\n        readOnly: true\n      \
  \  idempotent: true\n      call: uspto-trademark-search.get-trademark-by-serial-number\n      with:\n        serialNumber: tools.serialNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: research-owner-trademark-portfolio\n      description: Find all trademarks owned by a specific company or individual. Useful for competitive intelligence and\n        M&A due diligence.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uspto-trademark-search.search-trademarks-by-owner\n      with:\n        owner: tools.owner\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-database-status\n      description: Check when the USPTO trademark database was last updated and verify it is operating normally before running\n        trademark research queries.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: uspto-trademark-search.get-database-status\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/uspto-trademark-search-api/refs/heads/main/capabilities/trademark-research.yaml
tags:
- Brand Protection
- Due Diligence
- Intellectual Property
- Legal Research
- Trademark
- USPTO
tools:
- description: Search the USPTO trademark database for marks matching a keyword. Use this to find existing trademarks before registering a new brand name.
  hints:
    openWorld: true
    readOnly: true
  name: search-trademarks
- description: Check whether a trademark keyword appears to be available for registration. Returns availability status and any conflicting marks found in the USPTO database.
  hints:
    openWorld: true
    readOnly: true
  name: check-trademark-availability
- description: Retrieve complete trademark details for a known serial number, including prosecution history, owner details, and goods/services classification.
  hints:
    idempotent: true
    readOnly: true
  name: get-trademark-by-serial-number
- description: Find all trademarks owned by a specific company or individual. Useful for competitive intelligence and M&A due diligence.
  hints:
    openWorld: true
    readOnly: true
  name: research-owner-trademark-portfolio
- description: Check when the USPTO trademark database was last updated and verify it is operating normally before running trademark research queries.
  hints:
    idempotent: true
    readOnly: true
  name: get-database-status
---
