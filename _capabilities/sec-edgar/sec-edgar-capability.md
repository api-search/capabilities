---
categories: []
consumed_apis: []
description: The SEC EDGAR data APIs provide free, authenticated-free access to company filing metadata, XBRL financial data, and full-text search across all SEC submissions. APIs are hosted at data.sec.gov and efts.sec.gov and require a descriptive User-Agent header per SEC fair-access policy.
layout: capability
name: SEC EDGAR Submissions & XBRL API
operations:
- description: Get company filing submission history
  method: GET
  name: getcompanysubmissions
  path: /submissions/CIK{cik}.json
- description: Get all XBRL facts for a company
  method: GET
  name: getcompanyfacts
  path: /api/xbrl/companyfacts/CIK{cik}.json
- description: Get a single XBRL concept for a company
  method: GET
  name: getcompanyconcept
  path: /api/xbrl/companyconcept/CIK{cik}/{taxonomy}/{concept}.json
- description: Get all company values for a concept in a period
  method: GET
  name: getxbrlframes
  path: /api/xbrl/frames/{taxonomy}/{concept}/{unit}/{period}.json
- description: Full-text search across EDGAR filings
  method: GET
  name: fulltextsearch
  path: /LATEST/search-index
personas: []
provider_name: sec-edgar
provider_slug: sec-edgar
search_terms:
- getcompanyfacts
- fulltextsearch
- getcompanysubmissions
- getcompanyconcept
- api
- edgar
- get company filing submission history
- sec
- get all xbrl facts for a company
- get all company values for a concept in a period
- full-text search across edgar filings
- getxbrlframes
- get a single xbrl concept for a company
slug: sec-edgar-capability
source_filename: sec-edgar-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SEC EDGAR Submissions & XBRL API\n  description: The SEC EDGAR data APIs provide free, authenticated-free access to company filing metadata, XBRL financial\n    data, and full-text search across all SEC submissions. APIs are hosted at data.sec.gov and efts.sec.gov and require a\n    descriptive User-Agent header per SEC fair-access policy.\n  tags:\n  - Sec\n  - Edgar\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: sec-edgar\n    baseUri: https://data.sec.gov\n    description: SEC EDGAR Submissions & XBRL API HTTP API.\n    resources:\n    - name: submissions-cik-cik-json\n      path: /submissions/CIK{cik}.json\n      operations:\n      - name: getcompanysubmissions\n        method: GET\n        description: Get company filing submission history\n        inputParameters:\n        - name: cik\n          in: path\n          type: string\n          required: true\n    \
  \      description: '10-digit Central Index Key (CIK) with leading zeros. Example: 0000320193 for Apple Inc.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-xbrl-companyfacts-cik-cik-json\n      path: /api/xbrl/companyfacts/CIK{cik}.json\n      operations:\n      - name: getcompanyfacts\n        method: GET\n        description: Get all XBRL facts for a company\n        inputParameters:\n        - name: cik\n          in: path\n          type: string\n          required: true\n          description: 10-digit CIK with leading zeros\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-xbrl-companyconcept-cik-cik-taxonomy-concept\n      path: /api/xbrl/companyconcept/CIK{cik}/{taxonomy}/{concept}.json\n      operations:\n      - name: getcompanyconcept\n        method: GET\n        description: Get a single\
  \ XBRL concept for a company\n        inputParameters:\n        - name: cik\n          in: path\n          type: string\n          required: true\n        - name: taxonomy\n          in: path\n          type: string\n          required: true\n          description: XBRL taxonomy namespace\n        - name: concept\n          in: path\n          type: string\n          required: true\n          description: XBRL concept name (camelCase)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-xbrl-frames-taxonomy-concept-unit-period-jso\n      path: /api/xbrl/frames/{taxonomy}/{concept}/{unit}/{period}.json\n      operations:\n      - name: getxbrlframes\n        method: GET\n        description: Get all company values for a concept in a period\n        inputParameters:\n        - name: taxonomy\n          in: path\n          type: string\n          required: true\n        - name: concept\n          in:\
  \ path\n          type: string\n          required: true\n        - name: unit\n          in: path\n          type: string\n          required: true\n          description: Unit of measure (USD, shares, pure)\n        - name: period\n          in: path\n          type: string\n          required: true\n          description: 'Period identifier. For annual instant: CY{year}Q{quarter}I. For annual duration: CY{year}.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: latest-search-index\n      path: /LATEST/search-index\n      operations:\n      - name: fulltextsearch\n        method: GET\n        description: Full-text search across EDGAR filings\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description: Full-text search query (Elasticsearch query string syntax)\n        - name: dateRange\n          in: query\n          type: string\n         \
  \ description: Date range filter\n        - name: startdt\n          in: query\n          type: string\n        - name: enddt\n          in: query\n          type: string\n        - name: forms\n          in: query\n          type: string\n          description: Comma-separated list of form types to filter\n        - name: entity\n          in: query\n          type: string\n          description: Company name search filter\n        - name: _source\n          in: query\n          type: string\n          description: Response fields to include\n        - name: from\n          in: query\n          type: integer\n          description: Pagination offset\n        - name: hits.hits.total.value\n          in: query\n          type: integer\n          description: Maximum results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sec-edgar-rest\n  \
  \  description: REST adapter for SEC EDGAR Submissions & XBRL API.\n    resources:\n    - path: /submissions/CIK{cik}.json\n      name: getcompanysubmissions\n      operations:\n      - method: GET\n        name: getcompanysubmissions\n        description: Get company filing submission history\n        call: sec-edgar.getcompanysubmissions\n        with:\n          cik: rest.cik\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/xbrl/companyfacts/CIK{cik}.json\n      name: getcompanyfacts\n      operations:\n      - method: GET\n        name: getcompanyfacts\n        description: Get all XBRL facts for a company\n        call: sec-edgar.getcompanyfacts\n        with:\n          cik: rest.cik\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/xbrl/companyconcept/CIK{cik}/{taxonomy}/{concept}.json\n      name: getcompanyconcept\n      operations:\n      - method: GET\n        name: getcompanyconcept\n     \
  \   description: Get a single XBRL concept for a company\n        call: sec-edgar.getcompanyconcept\n        with:\n          cik: rest.cik\n          taxonomy: rest.taxonomy\n          concept: rest.concept\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/xbrl/frames/{taxonomy}/{concept}/{unit}/{period}.json\n      name: getxbrlframes\n      operations:\n      - method: GET\n        name: getxbrlframes\n        description: Get all company values for a concept in a period\n        call: sec-edgar.getxbrlframes\n        with:\n          taxonomy: rest.taxonomy\n          concept: rest.concept\n          unit: rest.unit\n          period: rest.period\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /LATEST/search-index\n      name: fulltextsearch\n      operations:\n      - method: GET\n        name: fulltextsearch\n        description: Full-text search across EDGAR filings\n        call: sec-edgar.fulltextsearch\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sec-edgar-mcp\n    transport: http\n    description: MCP adapter for SEC EDGAR Submissions & XBRL API for AI agent use.\n    tools:\n    - name: getcompanysubmissions\n      description: Get company filing submission history\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sec-edgar.getcompanysubmissions\n      with:\n        cik: tools.cik\n      inputParameters:\n      - name: cik\n        type: string\n        description: '10-digit Central Index Key (CIK) with leading zeros. Example: 0000320193 for Apple Inc.'\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcompanyfacts\n      description: Get all XBRL facts for a company\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sec-edgar.getcompanyfacts\n\
  \      with:\n        cik: tools.cik\n      inputParameters:\n      - name: cik\n        type: string\n        description: 10-digit CIK with leading zeros\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcompanyconcept\n      description: Get a single XBRL concept for a company\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sec-edgar.getcompanyconcept\n      with:\n        cik: tools.cik\n        taxonomy: tools.taxonomy\n        concept: tools.concept\n      inputParameters:\n      - name: cik\n        type: string\n        description: cik\n        required: true\n      - name: taxonomy\n        type: string\n        description: XBRL taxonomy namespace\n        required: true\n      - name: concept\n        type: string\n        description: XBRL concept name (camelCase)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: getxbrlframes\n      description: Get all company values for a concept in a period\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sec-edgar.getxbrlframes\n      with:\n        taxonomy: tools.taxonomy\n        concept: tools.concept\n        unit: tools.unit\n        period: tools.period\n      inputParameters:\n      - name: taxonomy\n        type: string\n        description: taxonomy\n        required: true\n      - name: concept\n        type: string\n        description: concept\n        required: true\n      - name: unit\n        type: string\n        description: Unit of measure (USD, shares, pure)\n        required: true\n      - name: period\n        type: string\n        description: 'Period identifier. For annual instant: CY{year}Q{quarter}I. For annual duration: CY{year}.'\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fulltextsearch\n      description:\
  \ Full-text search across EDGAR filings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sec-edgar.fulltextsearch\n      with:\n        q: tools.q\n        dateRange: tools.dateRange\n        startdt: tools.startdt\n        enddt: tools.enddt\n        forms: tools.forms\n        entity: tools.entity\n        _source: tools._source\n        from: tools.from\n        hits.hits.total.value: tools.hits.hits.total.value\n      inputParameters:\n      - name: q\n        type: string\n        description: Full-text search query (Elasticsearch query string syntax)\n      - name: dateRange\n        type: string\n        description: Date range filter\n      - name: startdt\n        type: string\n        description: startdt\n      - name: enddt\n        type: string\n        description: enddt\n      - name: forms\n        type: string\n        description: Comma-separated list of form types to filter\n      - name: entity\n        type: string\n\
  \        description: Company name search filter\n      - name: _source\n        type: string\n        description: Response fields to include\n      - name: from\n        type: integer\n        description: Pagination offset\n      - name: hits.hits.total.value\n        type: integer\n        description: Maximum results to return\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sec-edgar/refs/heads/main/capabilities/sec-edgar-capability.yaml
tags:
- Sec
- Edgar
- API
tools:
- description: Get company filing submission history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompanysubmissions
- description: Get all XBRL facts for a company
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompanyfacts
- description: Get a single XBRL concept for a company
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompanyconcept
- description: Get all company values for a concept in a period
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getxbrlframes
- description: Full-text search across EDGAR filings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fulltextsearch
---
