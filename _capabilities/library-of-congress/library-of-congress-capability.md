---
categories: []
consumed_apis: []
description: The Chronicling America API exposes historic American newspapers digitized through the National Digital Newspaper Program, providing search and metadata access to newspaper pages, issues, and titles.
layout: capability
name: Library of Congress Chronicling America API
operations:
- description: Search Pages
  method: GET
  name: searchpages
  path: /search/pages/results/
- description: Search Titles
  method: GET
  name: searchtitles
  path: /search/titles/results/
- description: Get Title
  method: GET
  name: gettitle
  path: /lccn/{lccn}.json
- description: Get Issue
  method: GET
  name: getissue
  path: /lccn/{lccn}/{date}/ed-{edition}.json
- description: List Newspapers
  method: GET
  name: listnewspapers
  path: /newspapers.json
personas: []
provider_name: Library of Congress
provider_slug: library-of-congress
search_terms:
- get title
- getissue
- legislative
- api
- listnewspapers
- newspapers
- searchtitles
- congress
- get issue
- gettitle
- library
- of
- search pages
- cultural heritage
- search titles
- list newspapers
- search
- federal government
- searchpages
slug: library-of-congress-capability
source_filename: library-of-congress-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Library of Congress Chronicling America API\n  description: The Chronicling America API exposes historic American newspapers digitized through the National Digital Newspaper\n    Program, providing search and metadata access to newspaper pages, issues, and titles.\n  tags:\n  - Library\n  - Of\n  - Congress\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: library-of-congress\n    baseUri: https://chroniclingamerica.loc.gov\n    description: Library of Congress Chronicling America API HTTP API.\n    resources:\n    - name: search-pages-results\n      path: /search/pages/results/\n      operations:\n      - name: searchpages\n        method: GET\n        description: Search Pages\n        inputParameters:\n        - name: andtext\n          in: query\n          type: string\n          description: Phrase to search within page text.\n        - name: state\n          in:\
  \ query\n          type: string\n          description: U.S. state filter.\n        - name: dateFilterType\n          in: query\n          type: string\n        - name: date1\n          in: query\n          type: string\n        - name: date2\n          in: query\n          type: string\n        - name: format\n          in: query\n          type: string\n        - name: rows\n          in: query\n          type: integer\n        - name: page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-titles-results\n      path: /search/titles/results/\n      operations:\n      - name: searchtitles\n        method: GET\n        description: Search Titles\n        inputParameters:\n        - name: terms\n          in: query\n          type: string\n        - name: state\n          in: query\n          type: string\n        - name: format\n          in: query\n\
  \          type: string\n        - name: rows\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lccn-lccn-json\n      path: /lccn/{lccn}.json\n      operations:\n      - name: gettitle\n        method: GET\n        description: Get Title\n        inputParameters:\n        - name: lccn\n          in: path\n          type: string\n          required: true\n          description: Library of Congress Control Number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lccn-lccn-date-ed-edition-json\n      path: /lccn/{lccn}/{date}/ed-{edition}.json\n      operations:\n      - name: getissue\n        method: GET\n        description: Get Issue\n        inputParameters:\n        - name: lccn\n          in: path\n          type: string\n          required: true\n        - name:\
  \ date\n          in: path\n          type: string\n          required: true\n          description: Issue date in YYYY-MM-DD format.\n        - name: edition\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: newspapers-json\n      path: /newspapers.json\n      operations:\n      - name: listnewspapers\n        method: GET\n        description: List Newspapers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: library-of-congress-rest\n    description: REST adapter for Library of Congress Chronicling America API.\n    resources:\n    - path: /search/pages/results/\n      name: searchpages\n      operations:\n      - method: GET\n        name: searchpages\n        description: Search Pages\n   \
  \     call: library-of-congress.searchpages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search/titles/results/\n      name: searchtitles\n      operations:\n      - method: GET\n        name: searchtitles\n        description: Search Titles\n        call: library-of-congress.searchtitles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lccn/{lccn}.json\n      name: gettitle\n      operations:\n      - method: GET\n        name: gettitle\n        description: Get Title\n        call: library-of-congress.gettitle\n        with:\n          lccn: rest.lccn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lccn/{lccn}/{date}/ed-{edition}.json\n      name: getissue\n      operations:\n      - method: GET\n        name: getissue\n        description: Get Issue\n        call: library-of-congress.getissue\n        with:\n          lccn: rest.lccn\n          date: rest.date\n\
  \          edition: rest.edition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /newspapers.json\n      name: listnewspapers\n      operations:\n      - method: GET\n        name: listnewspapers\n        description: List Newspapers\n        call: library-of-congress.listnewspapers\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: library-of-congress-mcp\n    transport: http\n    description: MCP adapter for Library of Congress Chronicling America API for AI agent use.\n    tools:\n    - name: searchpages\n      description: Search Pages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: library-of-congress.searchpages\n      with:\n        andtext: tools.andtext\n        state: tools.state\n        dateFilterType: tools.dateFilterType\n        date1: tools.date1\n        date2: tools.date2\n        format: tools.format\n \
  \       rows: tools.rows\n        page: tools.page\n      inputParameters:\n      - name: andtext\n        type: string\n        description: Phrase to search within page text.\n      - name: state\n        type: string\n        description: U.S. state filter.\n      - name: dateFilterType\n        type: string\n        description: dateFilterType\n      - name: date1\n        type: string\n        description: date1\n      - name: date2\n        type: string\n        description: date2\n      - name: format\n        type: string\n        description: format\n      - name: rows\n        type: integer\n        description: rows\n      - name: page\n        type: integer\n        description: page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchtitles\n      description: Search Titles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: library-of-congress.searchtitles\n      with:\n        terms:\
  \ tools.terms\n        state: tools.state\n        format: tools.format\n        rows: tools.rows\n      inputParameters:\n      - name: terms\n        type: string\n        description: terms\n      - name: state\n        type: string\n        description: state\n      - name: format\n        type: string\n        description: format\n      - name: rows\n        type: integer\n        description: rows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettitle\n      description: Get Title\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: library-of-congress.gettitle\n      with:\n        lccn: tools.lccn\n      inputParameters:\n      - name: lccn\n        type: string\n        description: Library of Congress Control Number.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getissue\n      description: Get Issue\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: library-of-congress.getissue\n      with:\n        lccn: tools.lccn\n        date: tools.date\n        edition: tools.edition\n      inputParameters:\n      - name: lccn\n        type: string\n        description: lccn\n        required: true\n      - name: date\n        type: string\n        description: Issue date in YYYY-MM-DD format.\n        required: true\n      - name: edition\n        type: integer\n        description: edition\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnewspapers\n      description: List Newspapers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: library-of-congress.listnewspapers\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/library-of-congress/refs/heads/main/capabilities/library-of-congress-capability.yaml
tags:
- Library
- Of
- Congress
- API
tools:
- description: Search Pages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchpages
- description: Search Titles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchtitles
- description: Get Title
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettitle
- description: Get Issue
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getissue
- description: List Newspapers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnewspapers
---
