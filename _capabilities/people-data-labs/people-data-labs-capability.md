---
categories: []
consumed_apis: []
description: People Data Labs (PDL) provides APIs for enriching and building people and company profiles at scale. The API offers person enrichment, person search, person identification, company enrichment, company search, IP enrichment, and job posting search across a dataset of professional profiles and organizations.
layout: capability
name: People Data Labs API
operations:
- description: Enrich a person profile
  method: GET
  name: get-person-enrich
  path: /person/enrich
- description: Search for person profiles
  method: GET
  name: get-person-search
  path: /person/search
- description: Identify a person
  method: GET
  name: get-person-identify
  path: /person/identify
- description: Bulk person enrichment
  method: POST
  name: post-person-bulk
  path: /person/bulk
- description: Enrich a company profile
  method: GET
  name: get-company-enrich
  path: /company/enrich
- description: Search for companies
  method: GET
  name: get-company-search
  path: /company/search
- description: IP enrichment
  method: GET
  name: get-ip-enrich
  path: /ip/enrich
- description: Search job postings
  method: GET
  name: get-job-posting-search
  path: /job_posting/search
- description: Autocomplete suggestions
  method: GET
  name: get-autocomplete
  path: /autocomplete
personas: []
provider_name: People Data Labs
provider_slug: people-data-labs
search_terms:
- get company enrich
- identity resolution
- search for person profiles
- api
- b2b
- get ip enrich
- identify a person
- search job postings
- autocomplete suggestions
- ip enrichment
- get autocomplete
- enrich a person profile
- enrich a company profile
- people
- search for companies
- bulk person enrichment
- post person bulk
- data
- get person identify
- get company search
- get person enrich
- get person search
- labs
- get job posting search
- people data
slug: people-data-labs-capability
source_filename: people-data-labs-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: People Data Labs API\n  description: People Data Labs (PDL) provides APIs for enriching and building people and company profiles at scale. The API\n    offers person enrichment, person search, person identification, company enrichment, company search, IP enrichment, and\n    job posting search across a dataset of professional profiles and organizations.\n  tags:\n  - People\n  - Data\n  - Labs\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: people-data-labs\n    baseUri: https://api.peopledatalabs.com/v5\n    description: People Data Labs API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{PEOPLE_DATA_LABS_TOKEN}}'\n    resources:\n    - name: person-enrich\n      path: /person/enrich\n      operations:\n      - name: get-person-enrich\n        method: GET\n        description: Enrich a person profile\n   \
  \     inputParameters:\n        - name: email\n          in: query\n          type: string\n        - name: phone\n          in: query\n          type: string\n        - name: profile\n          in: query\n          type: string\n        - name: first_name\n          in: query\n          type: string\n        - name: last_name\n          in: query\n          type: string\n        - name: company\n          in: query\n          type: string\n        - name: min_likelihood\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: person-search\n      path: /person/search\n      operations:\n      - name: get-person-search\n        method: GET\n        description: Search for person profiles\n        inputParameters:\n        - name: sql\n          in: query\n          type: string\n        - name: query\n          in: query\n          type: string\n        - name:\
  \ size\n          in: query\n          type: integer\n        - name: from\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: person-identify\n      path: /person/identify\n      operations:\n      - name: get-person-identify\n        method: GET\n        description: Identify a person\n        inputParameters:\n        - name: email\n          in: query\n          type: string\n        - name: phone\n          in: query\n          type: string\n        - name: first_name\n          in: query\n          type: string\n        - name: last_name\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: person-bulk\n      path: /person/bulk\n      operations:\n      - name: post-person-bulk\n        method: POST\n        description:\
  \ Bulk person enrichment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: company-enrich\n      path: /company/enrich\n      operations:\n      - name: get-company-enrich\n        method: GET\n        description: Enrich a company profile\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n        - name: website\n          in: query\n          type: string\n        - name: profile\n          in: query\n          type: string\n        - name: ticker\n          in: query\n          type: string\n        - name: location\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: company-search\n      path: /company/search\n      operations:\n      - name: get-company-search\n        method: GET\n        description: Search for companies\n\
  \        inputParameters:\n        - name: sql\n          in: query\n          type: string\n        - name: query\n          in: query\n          type: string\n        - name: size\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ip-enrich\n      path: /ip/enrich\n      operations:\n      - name: get-ip-enrich\n        method: GET\n        description: IP enrichment\n        inputParameters:\n        - name: ip\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-posting-search\n      path: /job_posting/search\n      operations:\n      - name: get-job-posting-search\n        method: GET\n        description: Search job postings\n        inputParameters:\n        - name: sql\n          in: query\n\
  \          type: string\n        - name: query\n          in: query\n          type: string\n        - name: size\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: autocomplete\n      path: /autocomplete\n      operations:\n      - name: get-autocomplete\n        method: GET\n        description: Autocomplete suggestions\n        inputParameters:\n        - name: field\n          in: query\n          type: string\n          required: true\n        - name: text\n          in: query\n          type: string\n        - name: size\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: people-data-labs-rest\n    description: REST adapter for People Data Labs API.\n    resources:\n  \
  \  - path: /person/enrich\n      name: get-person-enrich\n      operations:\n      - method: GET\n        name: get-person-enrich\n        description: Enrich a person profile\n        call: people-data-labs.get-person-enrich\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /person/search\n      name: get-person-search\n      operations:\n      - method: GET\n        name: get-person-search\n        description: Search for person profiles\n        call: people-data-labs.get-person-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /person/identify\n      name: get-person-identify\n      operations:\n      - method: GET\n        name: get-person-identify\n        description: Identify a person\n        call: people-data-labs.get-person-identify\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /person/bulk\n      name: post-person-bulk\n      operations:\n      - method:\
  \ POST\n        name: post-person-bulk\n        description: Bulk person enrichment\n        call: people-data-labs.post-person-bulk\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /company/enrich\n      name: get-company-enrich\n      operations:\n      - method: GET\n        name: get-company-enrich\n        description: Enrich a company profile\n        call: people-data-labs.get-company-enrich\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /company/search\n      name: get-company-search\n      operations:\n      - method: GET\n        name: get-company-search\n        description: Search for companies\n        call: people-data-labs.get-company-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ip/enrich\n      name: get-ip-enrich\n      operations:\n      - method: GET\n        name: get-ip-enrich\n        description: IP enrichment\n        call: people-data-labs.get-ip-enrich\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job_posting/search\n      name: get-job-posting-search\n      operations:\n      - method: GET\n        name: get-job-posting-search\n        description: Search job postings\n        call: people-data-labs.get-job-posting-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /autocomplete\n      name: get-autocomplete\n      operations:\n      - method: GET\n        name: get-autocomplete\n        description: Autocomplete suggestions\n        call: people-data-labs.get-autocomplete\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: people-data-labs-mcp\n    transport: http\n    description: MCP adapter for People Data Labs API for AI agent use.\n    tools:\n    - name: get-person-enrich\n      description: Enrich a person profile\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: people-data-labs.get-person-enrich\n      with:\n        email: tools.email\n        phone: tools.phone\n        profile: tools.profile\n        first_name: tools.first_name\n        last_name: tools.last_name\n        company: tools.company\n        min_likelihood: tools.min_likelihood\n      inputParameters:\n      - name: email\n        type: string\n        description: email\n      - name: phone\n        type: string\n        description: phone\n      - name: profile\n        type: string\n        description: profile\n      - name: first_name\n        type: string\n        description: first_name\n      - name: last_name\n        type: string\n        description: last_name\n      - name: company\n        type: string\n        description: company\n      - name: min_likelihood\n        type: integer\n        description: min_likelihood\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-person-search\n\
  \      description: Search for person profiles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: people-data-labs.get-person-search\n      with:\n        sql: tools.sql\n        query: tools.query\n        size: tools.size\n        from: tools.from\n      inputParameters:\n      - name: sql\n        type: string\n        description: sql\n      - name: query\n        type: string\n        description: query\n      - name: size\n        type: integer\n        description: size\n      - name: from\n        type: integer\n        description: from\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-person-identify\n      description: Identify a person\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: people-data-labs.get-person-identify\n      with:\n        email: tools.email\n        phone: tools.phone\n        first_name: tools.first_name\n    \
  \    last_name: tools.last_name\n      inputParameters:\n      - name: email\n        type: string\n        description: email\n      - name: phone\n        type: string\n        description: phone\n      - name: first_name\n        type: string\n        description: first_name\n      - name: last_name\n        type: string\n        description: last_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-person-bulk\n      description: Bulk person enrichment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: people-data-labs.post-person-bulk\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-company-enrich\n      description: Enrich a company profile\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: people-data-labs.get-company-enrich\n      with:\n        name: tools.name\n        website: tools.website\n \
  \       profile: tools.profile\n        ticker: tools.ticker\n        location: tools.location\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n      - name: website\n        type: string\n        description: website\n      - name: profile\n        type: string\n        description: profile\n      - name: ticker\n        type: string\n        description: ticker\n      - name: location\n        type: string\n        description: location\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-company-search\n      description: Search for companies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: people-data-labs.get-company-search\n      with:\n        sql: tools.sql\n        query: tools.query\n        size: tools.size\n      inputParameters:\n      - name: sql\n        type: string\n        description: sql\n      - name: query\n        type: string\n   \
  \     description: query\n      - name: size\n        type: integer\n        description: size\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ip-enrich\n      description: IP enrichment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: people-data-labs.get-ip-enrich\n      with:\n        ip: tools.ip\n      inputParameters:\n      - name: ip\n        type: string\n        description: ip\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-posting-search\n      description: Search job postings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: people-data-labs.get-job-posting-search\n      with:\n        sql: tools.sql\n        query: tools.query\n        size: tools.size\n      inputParameters:\n      - name: sql\n        type: string\n        description: sql\n      - name: query\n\
  \        type: string\n        description: query\n      - name: size\n        type: integer\n        description: size\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-autocomplete\n      description: Autocomplete suggestions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: people-data-labs.get-autocomplete\n      with:\n        field: tools.field\n        text: tools.text\n        size: tools.size\n      inputParameters:\n      - name: field\n        type: string\n        description: field\n        required: true\n      - name: text\n        type: string\n        description: text\n      - name: size\n        type: integer\n        description: size\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PEOPLE_DATA_LABS_TOKEN: PEOPLE_DATA_LABS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/people-data-labs/refs/heads/main/capabilities/people-data-labs-capability.yaml
tags:
- People
- Data
- Labs
- API
tools:
- description: Enrich a person profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-person-enrich
- description: Search for person profiles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-person-search
- description: Identify a person
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-person-identify
- description: Bulk person enrichment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-person-bulk
- description: Enrich a company profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-company-enrich
- description: Search for companies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-company-search
- description: IP enrichment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-ip-enrich
- description: Search job postings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-job-posting-search
- description: Autocomplete suggestions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-autocomplete
---
