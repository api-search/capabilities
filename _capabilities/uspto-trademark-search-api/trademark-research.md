---
categories: []
consumed_apis:
- uspto-trademark-search
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
- check trademark availability
- check whether a trademark keyword appears to be available for registration. returns availability status and any conflicting marks found in the uspto database.
- trademark
- retrieve complete trademark details by serial number
- data
- get database status
- brand
- verify database is current before conducting research
- uspto trademark database status
- business
- list all trademarks owned by an individual or organization
- legal research
- get trademark by serial number
- check when the uspto trademark database was last updated and verify it is operating normally before running trademark research queries.
- check if a trademark keyword is available for registration
- brand protection
- research trademark portfolio of a specific owner
- due diligence
- search uspto trademark database by keyword
- find all trademarks owned by a specific company or individual. useful for competitive intelligence and m&a due diligence.
- search
- get full trademark filing details, prosecution history, and owner info
- government data
- search active or all trademarks matching a keyword
- intellectual property
- search trademarks by owner
- retrieve complete trademark details for a known serial number, including prosecution history, owner details, and goods/services classification.
- research owner trademark portfolio
- search trademarks
- returns availability status and list of conflicting marks
- legal
- search the uspto trademark database for marks matching a keyword. use this to find existing trademarks before registering a new brand name.
- uspto
slug: trademark-research
source_filename: trademark-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: USPTO Trademark Research\n  description: >-\n    Workflow capability for trademark research and brand protection using the\n    USPTO Trademark Search API. Supports legal professionals, brand managers,\n    startup founders, and IP attorneys conducting trademark availability checks,\n    competitive brand portfolio research, and ownership due diligence through\n    a unified REST and MCP interface.\n  tags:\n    - Brand Protection\n    - Due Diligence\n    - Intellectual Property\n    - Legal Research\n    - Trademark\n    - USPTO\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      RAPIDAPI_KEY: RAPIDAPI_KEY\n\ncapability:\n  consumes:\n    - import: uspto-trademark-search\n      location: ./shared/uspto-trademark-search.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: trademark-research-api\n      description: \"Unified REST API for trademark research and\
  \ brand protection workflows.\"\n      resources:\n        - path: /v1/trademarks\n          name: trademark-search\n          description: Search USPTO trademark database by keyword\n          operations:\n            - method: GET\n              name: search-trademarks\n              description: Search active or all trademarks matching a keyword\n              call: \"uspto-trademark-search.search-trademarks\"\n              with:\n                keyword: \"rest.keyword\"\n                searchType: \"rest.searchType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/trademarks/availability/{keyword}\n          name: trademark-availability\n          description: Check if a trademark keyword is available for registration\n          operations:\n            - method: GET\n              name: check-trademark-availability\n              description: Returns availability status and list of conflicting marks\n  \
  \            call: \"uspto-trademark-search.check-trademark-availability\"\n              with:\n                keyword: \"rest.keyword\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/trademarks/{serialNumber}\n          name: trademark-detail\n          description: Retrieve complete trademark details by serial number\n          operations:\n            - method: GET\n              name: get-trademark-by-serial-number\n              description: Get full trademark filing details, prosecution history, and owner info\n              call: \"uspto-trademark-search.get-trademark-by-serial-number\"\n              with:\n                serialNumber: \"rest.serialNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/owners/{owner}/trademarks\n          name: owner-portfolio\n          description: Research trademark portfolio of a specific\
  \ owner\n          operations:\n            - method: GET\n              name: search-trademarks-by-owner\n              description: List all trademarks owned by an individual or organization\n              call: \"uspto-trademark-search.search-trademarks-by-owner\"\n              with:\n                owner: \"rest.owner\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/database/status\n          name: database-status\n          description: USPTO trademark database status\n          operations:\n            - method: GET\n              name: get-database-status\n              description: Verify database is current before conducting research\n              call: \"uspto-trademark-search.get-database-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: trademark-research-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted trademark research and brand protection.\"\n      tools:\n        - name: search-trademarks\n          description: >-\n            Search the USPTO trademark database for marks matching a keyword.\n            Use this to find existing trademarks before registering a new brand name.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uspto-trademark-search.search-trademarks\"\n          with:\n            keyword: \"tools.keyword\"\n            searchType: \"tools.searchType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-trademark-availability\n          description: >-\n            Check whether a trademark keyword appears to be available for registration.\n            Returns availability status and any conflicting marks found in the USPTO database.\n          hints:\n            readOnly: true\n       \
  \     openWorld: true\n          call: \"uspto-trademark-search.check-trademark-availability\"\n          with:\n            keyword: \"tools.keyword\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-trademark-by-serial-number\n          description: >-\n            Retrieve complete trademark details for a known serial number,\n            including prosecution history, owner details, and goods/services classification.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"uspto-trademark-search.get-trademark-by-serial-number\"\n          with:\n            serialNumber: \"tools.serialNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: research-owner-trademark-portfolio\n          description: >-\n            Find all trademarks owned by a specific company or individual.\n            Useful for competitive intelligence and\
  \ M&A due diligence.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uspto-trademark-search.search-trademarks-by-owner\"\n          with:\n            owner: \"tools.owner\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-database-status\n          description: >-\n            Check when the USPTO trademark database was last updated and verify\n            it is operating normally before running trademark research queries.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"uspto-trademark-search.get-database-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
