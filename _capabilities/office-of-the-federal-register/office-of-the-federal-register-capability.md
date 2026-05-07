---
categories: []
consumed_apis: []
description: Search, browse and learn about the Federal Register. Federal Register 2.0 is the unofficial daily publication for rules, proposed rules, and notices of Federal agencies and organizations, as well as executive orders and other presidential documents.
layout: capability
name: Office of the Federal Register API
operations:
- description: Search Federal Register Documents
  method: GET
  name: searchdocuments
  path: /documents.json
- description: Fetch a Single Document
  method: GET
  name: getdocument
  path: /documents/{document_number}.json
- description: Fetch Multiple Documents
  method: GET
  name: getdocuments
  path: /documents/{document_numbers}.json
- description: Document Counts By Facet
  method: GET
  name: getdocumentfacets
  path: /documents/facets/{facet}
- description: Fetch a Federal Register Issue Table of Contents
  method: GET
  name: getissue
  path: /issues/{publication_date}.json
- description: Search Public Inspection Documents
  method: GET
  name: searchpublicinspectiondocuments
  path: /public-inspection-documents.json
- description: Fetch a Single Public Inspection Document
  method: GET
  name: getpublicinspectiondocument
  path: /public-inspection-documents/{document_number}.json
- description: Fetch Current Public Inspection Documents
  method: GET
  name: getcurrentpublicinspectiondocuments
  path: /public-inspection-documents/current.json
- description: List Agencies
  method: GET
  name: listagencies
  path: /agencies
- description: Fetch a Single Agency
  method: GET
  name: getagency
  path: /agencies/{slug}
- description: Fetch a Single Image Package
  method: GET
  name: getimage
  path: /images/{identifier}
- description: List Suggested Searches
  method: GET
  name: listsuggestedsearches
  path: /suggested_searches
- description: Fetch a Single Suggested Search
  method: GET
  name: getsuggestedsearch
  path: /suggested_searches/{slug}
personas: []
provider_name: Office of the Federal Register
provider_slug: office-of-the-federal-register
search_terms:
- fetch a single agency
- federal
- getissue
- getpublicinspectiondocument
- getsuggestedsearch
- listagencies
- api
- fetch a single document
- search public inspection documents
- getagency
- register
- fetch a single image package
- regulations
- document counts by facet
- fetch a single suggested search
- getdocumentfacets
- search federal register documents
- federal register
- fetch a federal register issue table of contents
- listsuggestedsearches
- getimage
- of
- searchdocuments
- fetch multiple documents
- fetch a single public inspection document
- fetch current public inspection documents
- executive orders
- the
- getcurrentpublicinspectiondocuments
- list suggested searches
- getdocument
- searchpublicinspectiondocuments
- federal government
- office
- getdocuments
- list agencies
slug: office-of-the-federal-register-capability
source_filename: office-of-the-federal-register-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Office of the Federal Register API\n  description: Search, browse and learn about the Federal Register. Federal Register 2.0 is the unofficial daily publication\n    for rules, proposed rules, and notices of Federal agencies and organizations, as well as executive orders and other presidential\n    documents.\n  tags:\n  - Office\n  - Of\n  - The\n  - Federal\n  - Register\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: office-of-the-federal-register\n    baseUri: https://www.federalregister.gov/api/v1\n    description: Office of the Federal Register API HTTP API.\n    resources:\n    - name: documents-json\n      path: /documents.json\n      operations:\n      - name: searchdocuments\n        method: GET\n        description: Search Federal Register Documents\n        inputParameters:\n        - name: per_page\n          in: query\n          type: integer\n        \
  \  description: Number of results per page (max 1000).\n        - name: page\n          in: query\n          type: integer\n          description: Page number of results.\n        - name: order\n          in: query\n          type: string\n          description: Order of results (relevance, newest, oldest, executive_order_number).\n        - name: conditions[term]\n          in: query\n          type: string\n          description: Full text search term.\n        - name: conditions[publication_date][gte]\n          in: query\n          type: string\n          description: Publication date greater than or equal to (YYYY-MM-DD).\n        - name: conditions[publication_date][lte]\n          in: query\n          type: string\n          description: Publication date less than or equal to (YYYY-MM-DD).\n        - name: conditions[type][]\n          in: query\n          type: string\n          description: Document type (RULE, PRORULE, NOTICE, PRESDOCU).\n        - name: conditions[agencies][]\n\
  \          in: query\n          type: string\n          description: Agency slug filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-document-number-json\n      path: /documents/{document_number}.json\n      operations:\n      - name: getdocument\n        method: GET\n        description: Fetch a Single Document\n        inputParameters:\n        - name: document_number\n          in: path\n          type: string\n          required: true\n          description: The document number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-document-numbers-json\n      path: /documents/{document_numbers}.json\n      operations:\n      - name: getdocuments\n        method: GET\n        description: Fetch Multiple Documents\n        inputParameters:\n        - name: document_numbers\n         \
  \ in: path\n          type: string\n          required: true\n          description: Comma-separated document numbers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-facets-facet\n      path: /documents/facets/{facet}\n      operations:\n      - name: getdocumentfacets\n        method: GET\n        description: Document Counts By Facet\n        inputParameters:\n        - name: facet\n          in: path\n          type: string\n          required: true\n          description: Facet to aggregate by.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: issues-publication-date-json\n      path: /issues/{publication_date}.json\n      operations:\n      - name: getissue\n        method: GET\n        description: Fetch a Federal Register Issue Table of Contents\n        inputParameters:\n        - name: publication_date\n\
  \          in: path\n          type: string\n          required: true\n          description: Publication date (YYYY-MM-DD).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: public-inspection-documents-json\n      path: /public-inspection-documents.json\n      operations:\n      - name: searchpublicinspectiondocuments\n        method: GET\n        description: Search Public Inspection Documents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: public-inspection-documents-document-number-json\n      path: /public-inspection-documents/{document_number}.json\n      operations:\n      - name: getpublicinspectiondocument\n        method: GET\n        description: Fetch a Single Public Inspection Document\n        inputParameters:\n        - name: document_number\n          in: path\n          type: string\n     \
  \     required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: public-inspection-documents-current-json\n      path: /public-inspection-documents/current.json\n      operations:\n      - name: getcurrentpublicinspectiondocuments\n        method: GET\n        description: Fetch Current Public Inspection Documents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agencies\n      path: /agencies\n      operations:\n      - name: listagencies\n        method: GET\n        description: List Agencies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agencies-slug\n      path: /agencies/{slug}\n      operations:\n      - name: getagency\n        method: GET\n        description: Fetch a Single Agency\n        inputParameters:\n\
  \        - name: slug\n          in: path\n          type: string\n          required: true\n          description: The agency slug.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-identifier\n      path: /images/{identifier}\n      operations:\n      - name: getimage\n        method: GET\n        description: Fetch a Single Image Package\n        inputParameters:\n        - name: identifier\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: suggested-searches\n      path: /suggested_searches\n      operations:\n      - name: listsuggestedsearches\n        method: GET\n        description: List Suggested Searches\n        inputParameters:\n        - name: conditions[sections]\n          in: query\n          type: string\n          description:\
  \ Filter to a specific section.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: suggested-searches-slug\n      path: /suggested_searches/{slug}\n      operations:\n      - name: getsuggestedsearch\n        method: GET\n        description: Fetch a Single Suggested Search\n        inputParameters:\n        - name: slug\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: office-of-the-federal-register-rest\n    description: REST adapter for Office of the Federal Register API.\n    resources:\n    - path: /documents.json\n      name: searchdocuments\n      operations:\n      - method: GET\n        name: searchdocuments\n        description: Search Federal Register Documents\n        call: office-of-the-federal-register.searchdocuments\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{document_number}.json\n      name: getdocument\n      operations:\n      - method: GET\n        name: getdocument\n        description: Fetch a Single Document\n        call: office-of-the-federal-register.getdocument\n        with:\n          document_number: rest.document_number\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/{document_numbers}.json\n      name: getdocuments\n      operations:\n      - method: GET\n        name: getdocuments\n        description: Fetch Multiple Documents\n        call: office-of-the-federal-register.getdocuments\n        with:\n          document_numbers: rest.document_numbers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/facets/{facet}\n      name: getdocumentfacets\n      operations:\n      - method: GET\n        name: getdocumentfacets\n        description:\
  \ Document Counts By Facet\n        call: office-of-the-federal-register.getdocumentfacets\n        with:\n          facet: rest.facet\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /issues/{publication_date}.json\n      name: getissue\n      operations:\n      - method: GET\n        name: getissue\n        description: Fetch a Federal Register Issue Table of Contents\n        call: office-of-the-federal-register.getissue\n        with:\n          publication_date: rest.publication_date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public-inspection-documents.json\n      name: searchpublicinspectiondocuments\n      operations:\n      - method: GET\n        name: searchpublicinspectiondocuments\n        description: Search Public Inspection Documents\n        call: office-of-the-federal-register.searchpublicinspectiondocuments\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /public-inspection-documents/{document_number}.json\n      name: getpublicinspectiondocument\n      operations:\n      - method: GET\n        name: getpublicinspectiondocument\n        description: Fetch a Single Public Inspection Document\n        call: office-of-the-federal-register.getpublicinspectiondocument\n        with:\n          document_number: rest.document_number\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public-inspection-documents/current.json\n      name: getcurrentpublicinspectiondocuments\n      operations:\n      - method: GET\n        name: getcurrentpublicinspectiondocuments\n        description: Fetch Current Public Inspection Documents\n        call: office-of-the-federal-register.getcurrentpublicinspectiondocuments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agencies\n      name: listagencies\n      operations:\n      - method: GET\n        name: listagencies\n      \
  \  description: List Agencies\n        call: office-of-the-federal-register.listagencies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agencies/{slug}\n      name: getagency\n      operations:\n      - method: GET\n        name: getagency\n        description: Fetch a Single Agency\n        call: office-of-the-federal-register.getagency\n        with:\n          slug: rest.slug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images/{identifier}\n      name: getimage\n      operations:\n      - method: GET\n        name: getimage\n        description: Fetch a Single Image Package\n        call: office-of-the-federal-register.getimage\n        with:\n          identifier: rest.identifier\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /suggested_searches\n      name: listsuggestedsearches\n      operations:\n      - method: GET\n        name: listsuggestedsearches\n  \
  \      description: List Suggested Searches\n        call: office-of-the-federal-register.listsuggestedsearches\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /suggested_searches/{slug}\n      name: getsuggestedsearch\n      operations:\n      - method: GET\n        name: getsuggestedsearch\n        description: Fetch a Single Suggested Search\n        call: office-of-the-federal-register.getsuggestedsearch\n        with:\n          slug: rest.slug\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: office-of-the-federal-register-mcp\n    transport: http\n    description: MCP adapter for Office of the Federal Register API for AI agent use.\n    tools:\n    - name: searchdocuments\n      description: Search Federal Register Documents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: office-of-the-federal-register.searchdocuments\n\
  \      with:\n        per_page: tools.per_page\n        page: tools.page\n        order: tools.order\n        conditions[term]: tools.conditions[term]\n        conditions[publication_date][gte]: tools.conditions[publication_date][gte]\n        conditions[publication_date][lte]: tools.conditions[publication_date][lte]\n        conditions[type][]: tools.conditions[type][]\n        conditions[agencies][]: tools.conditions[agencies][]\n      inputParameters:\n      - name: per_page\n        type: integer\n        description: Number of results per page (max 1000).\n      - name: page\n        type: integer\n        description: Page number of results.\n      - name: order\n        type: string\n        description: Order of results (relevance, newest, oldest, executive_order_number).\n      - name: conditions[term]\n        type: string\n        description: Full text search term.\n      - name: conditions[publication_date][gte]\n        type: string\n        description: Publication date\
  \ greater than or equal to (YYYY-MM-DD).\n      - name: conditions[publication_date][lte]\n        type: string\n        description: Publication date less than or equal to (YYYY-MM-DD).\n      - name: conditions[type][]\n        type: string\n        description: Document type (RULE, PRORULE, NOTICE, PRESDOCU).\n      - name: conditions[agencies][]\n        type: string\n        description: Agency slug filter.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdocument\n      description: Fetch a Single Document\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: office-of-the-federal-register.getdocument\n      with:\n        document_number: tools.document_number\n      inputParameters:\n      - name: document_number\n        type: string\n        description: The document number.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdocuments\n\
  \      description: Fetch Multiple Documents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: office-of-the-federal-register.getdocuments\n      with:\n        document_numbers: tools.document_numbers\n      inputParameters:\n      - name: document_numbers\n        type: string\n        description: Comma-separated document numbers.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdocumentfacets\n      description: Document Counts By Facet\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: office-of-the-federal-register.getdocumentfacets\n      with:\n        facet: tools.facet\n      inputParameters:\n      - name: facet\n        type: string\n        description: Facet to aggregate by.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getissue\n      description:\
  \ Fetch a Federal Register Issue Table of Contents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: office-of-the-federal-register.getissue\n      with:\n        publication_date: tools.publication_date\n      inputParameters:\n      - name: publication_date\n        type: string\n        description: Publication date (YYYY-MM-DD).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchpublicinspectiondocuments\n      description: Search Public Inspection Documents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: office-of-the-federal-register.searchpublicinspectiondocuments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpublicinspectiondocument\n      description: Fetch a Single Public Inspection Document\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: office-of-the-federal-register.getpublicinspectiondocument\n      with:\n        document_number: tools.document_number\n      inputParameters:\n      - name: document_number\n        type: string\n        description: document_number\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcurrentpublicinspectiondocuments\n      description: Fetch Current Public Inspection Documents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: office-of-the-federal-register.getcurrentpublicinspectiondocuments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listagencies\n      description: List Agencies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: office-of-the-federal-register.listagencies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getagency\n\
  \      description: Fetch a Single Agency\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: office-of-the-federal-register.getagency\n      with:\n        slug: tools.slug\n      inputParameters:\n      - name: slug\n        type: string\n        description: The agency slug.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getimage\n      description: Fetch a Single Image Package\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: office-of-the-federal-register.getimage\n      with:\n        identifier: tools.identifier\n      inputParameters:\n      - name: identifier\n        type: string\n        description: identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsuggestedsearches\n      description: List Suggested Searches\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: office-of-the-federal-register.listsuggestedsearches\n      with:\n        conditions[sections]: tools.conditions[sections]\n      inputParameters:\n      - name: conditions[sections]\n        type: string\n        description: Filter to a specific section.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsuggestedsearch\n      description: Fetch a Single Suggested Search\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: office-of-the-federal-register.getsuggestedsearch\n      with:\n        slug: tools.slug\n      inputParameters:\n      - name: slug\n        type: string\n        description: slug\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/office-of-the-federal-register/refs/heads/main/capabilities/office-of-the-federal-register-capability.yaml
tags:
- Office
- Of
- The
- Federal
- Register
- API
tools:
- description: Search Federal Register Documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchdocuments
- description: Fetch a Single Document
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocument
- description: Fetch Multiple Documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocuments
- description: Document Counts By Facet
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocumentfacets
- description: Fetch a Federal Register Issue Table of Contents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getissue
- description: Search Public Inspection Documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchpublicinspectiondocuments
- description: Fetch a Single Public Inspection Document
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpublicinspectiondocument
- description: Fetch Current Public Inspection Documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentpublicinspectiondocuments
- description: List Agencies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listagencies
- description: Fetch a Single Agency
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getagency
- description: Fetch a Single Image Package
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getimage
- description: List Suggested Searches
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsuggestedsearches
- description: Fetch a Single Suggested Search
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsuggestedsearch
---
