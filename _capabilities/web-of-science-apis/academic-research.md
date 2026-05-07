---
categories: []
consumed_apis: []
description: Unified academic research workflow combining Web of Science Starter and Expanded APIs for bibliographic search, citation analysis, journal discovery, and bibliometric reporting. Used by researchers, librarians, and data analysts to automate literature review and citation analysis.
layout: capability
name: Web of Science Academic Research
operations:
- description: Search Web of Science documents
  method: GET
  name: search-documents
  path: /v1/documents/search
- description: Get document by UID
  method: GET
  name: get-document
  path: /v1/documents/{uid}
- description: Search journals by ISSN or name
  method: GET
  name: search-journals
  path: /v1/journals
- description: Get citing articles
  method: GET
  name: get-citing-articles
  path: /v1/citations/citing
- description: Get document reference list
  method: GET
  name: get-references
  path: /v1/citations/references
- description: Get related records
  method: GET
  name: get-related-records
  path: /v1/citations/related
- description: Get citation report for query
  method: GET
  name: get-citation-report
  path: /v1/reports/citations/{queryId}
personas: []
provider_name: Web of Science APIs
provider_slug: web-of-science-apis
search_terms:
- articles citing a document
- get references
- get full bibliographic details for a specific web of science document by uid
- find related research
- search journals
- search web of science documents
- search literature
- get document reference list
- document references
- individual document
- journal search
- retrieve a full web of science record directly by its unique identifier
- search documents
- science
- get record by uid
- get document
- citation report
- academic
- find all papers that have cited a specific article (forward citation tracking)
- research
- search web of science literature using advanced query syntax (e.g., ts=climate change and py=2020-2024)
- get journal details
- get the complete reference list of a paper (backward citation tracking)
- get document by uid
- bibliometrics
- generate a bibliometric citation report including h-index and year-by-year citation counts
- scholarly
- related records
- discover research papers related to a given article based on shared references
- look up a journal in web of science by issn or name to get impact metrics
- run advanced web of science search with full field tag syntax for comprehensive literature review
- get citation report for query
- get citation report
- get paper details
- get related records
- find citing papers
- generate citation report
- get detailed information about a journal including jcr profile and categories
- search journals by issn or name
- citations
- find journal
- get citing articles
- literature review
- advanced search
- document search
slug: academic-research
source_filename: academic-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Web of Science Academic Research\n  description: Unified academic research workflow combining Web of Science Starter and Expanded APIs for bibliographic search,\n    citation analysis, journal discovery, and bibliometric reporting. Used by researchers, librarians, and data analysts to\n    automate literature review and citation analysis.\n  tags:\n  - Research\n  - Academic\n  - Bibliometrics\n  - Citations\n  - Literature Review\n  - Science\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WOS_API_KEY: WOS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: wos-starter\n    baseUri: https://api.clarivate.com/apis/wos-starter/v1\n    description: Web of Science Starter API for document and journal search.\n    resources:\n    - name: documents\n      path: /documents\n      description: Document search and retrieval\n      operations:\n      - name: search-documents\n        method:\
  \ GET\n        description: Search Web of Science documents\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Advanced query syntax string\n        - name: db\n          in: query\n          type: string\n          required: false\n          description: Database to search\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of records to return\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: document\n      path: /documents/{uid}\n      description: Individual document retrieval\n      operations:\n      - name: get-document\n        method: GET\n        description: Get a specific document\
  \ by UID\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n          description: Web of Science unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: journals\n      path: /journals\n      description: Journal search and retrieval\n      operations:\n      - name: search-journals\n        method: GET\n        description: Search journals by ISSN or name\n        inputParameters:\n        - name: issn\n          in: query\n          type: string\n          required: false\n          description: Journal ISSN\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Free-text search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: journal\n      path: /journals/{id}\n\
  \      description: Individual journal retrieval\n      operations:\n      - name: get-journal\n        method: GET\n        description: Get journal details by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Web of Science journal identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: wos-expanded\n    baseUri: https://api.clarivate.com/api/wos\n    description: Web of Science API Expanded for full bibliometric analysis.\n    resources:\n    - name: search\n      path: /\n      description: Document search operations\n      operations:\n      - name: search-documents\n        method: GET\n        description: Search Web of Science documents\n        inputParameters:\n        - name: databaseId\n          in: query\n          type: string\n          required: true\n          description:\
  \ Database to search\n        - name: usrQuery\n          in: query\n          type: string\n          required: true\n          description: Advanced search query\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Number of records\n        - name: firstRecord\n          in: query\n          type: integer\n          required: false\n          description: Starting record for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query-results\n      path: /query/{queryId}\n      description: Paginate through query results\n      operations:\n      - name: get-query-results\n        method: GET\n        description: Get results from a previous search query\n        inputParameters:\n        - name: queryId\n          in: path\n          type: integer\n          required: true\n          description: Query identifier from search\n\
  \        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Number of records\n        - name: firstRecord\n          in: query\n          type: integer\n          required: false\n          description: Starting record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: record-ids\n      path: /recordids/{queryId}\n      description: Get record UIDs from a query\n      operations:\n      - name: get-record-ids\n        method: GET\n        description: Get only UIDs from a query result set\n        inputParameters:\n        - name: queryId\n          in: path\n          type: integer\n          required: true\n          description: Query identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: record-by-id\n      path: /id/{uniqueId}\n      description:\
  \ Retrieve records by UID\n      operations:\n      - name: get-record-by-id\n        method: GET\n        description: Get records by WOS unique identifier\n        inputParameters:\n        - name: uniqueId\n          in: path\n          type: string\n          required: true\n          description: WOS unique identifier(s)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: citing\n      path: /citing\n      description: Find citing articles\n      operations:\n      - name: get-citing-articles\n        method: GET\n        description: Get articles citing a specific document\n        inputParameters:\n        - name: databaseId\n          in: query\n          type: string\n          required: true\n          description: Database identifier\n        - name: uniqueId\n          in: query\n          type: string\n          required: true\n          description: WOS UID of the cited article\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: references\n      path: /references\n      description: Get document references\n      operations:\n      - name: get-references\n        method: GET\n        description: Get the reference list of a document\n        inputParameters:\n        - name: databaseId\n          in: query\n          type: string\n          required: true\n          description: Database identifier\n        - name: uniqueId\n          in: query\n          type: string\n          required: true\n          description: WOS UID of the document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: related\n      path: /related\n      description: Find related records\n      operations:\n      - name: get-related-records\n        method: GET\n        description: Get records sharing cited references\
  \ with a document\n        inputParameters:\n        - name: databaseId\n          in: query\n          type: string\n          required: true\n          description: Database identifier\n        - name: uniqueId\n          in: query\n          type: string\n          required: true\n          description: WOS UID of the source document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: citation-report\n      path: /citation-report/{queryId}\n      description: Citation report generation\n      operations:\n      - name: get-citation-report\n        method: GET\n        description: Generate citation report for a query result set\n        inputParameters:\n        - name: queryId\n          in: path\n          type: integer\n          required: true\n          description: Query identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: academic-research-api\n    description: Unified REST API for Web of Science academic research operations.\n    resources:\n    - path: /v1/documents/search\n      name: document-search\n      description: Document search\n      operations:\n      - method: GET\n        name: search-documents\n        description: Search Web of Science documents\n        call: wos-starter.search-documents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents/{uid}\n      name: document\n      description: Individual document\n      operations:\n      - method: GET\n        name: get-document\n        description: Get document by UID\n        call: wos-starter.get-document\n        with:\n          uid: rest.uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/journals\n      name: journals\n      description: Journal search\n      operations:\n\
  \      - method: GET\n        name: search-journals\n        description: Search journals by ISSN or name\n        call: wos-starter.search-journals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/citations/citing\n      name: citing-articles\n      description: Articles citing a document\n      operations:\n      - method: GET\n        name: get-citing-articles\n        description: Get citing articles\n        call: wos-expanded.get-citing-articles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/citations/references\n      name: references\n      description: Document references\n      operations:\n      - method: GET\n        name: get-references\n        description: Get document reference list\n        call: wos-expanded.get-references\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/citations/related\n      name: related-records\n      description: Related\
  \ records\n      operations:\n      - method: GET\n        name: get-related-records\n        description: Get related records\n        call: wos-expanded.get-related-records\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/citations/{queryId}\n      name: citation-report\n      description: Citation report\n      operations:\n      - method: GET\n        name: get-citation-report\n        description: Get citation report for query\n        call: wos-expanded.get-citation-report\n        with:\n          queryId: rest.queryId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9094\n    namespace: academic-research-mcp\n    transport: http\n    description: MCP server for AI-assisted Web of Science academic research.\n    tools:\n    - name: search-literature\n      description: Search Web of Science literature using advanced query syntax (e.g., TS=climate change AND PY=2020-2024)\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: wos-starter.search-documents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-paper-details\n      description: Get full bibliographic details for a specific Web of Science document by UID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wos-starter.get-document\n      with:\n        uid: tools.uid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-journal\n      description: Look up a journal in Web of Science by ISSN or name to get impact metrics\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wos-starter.search-journals\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-journal-details\n      description: Get detailed information about a journal including JCR profile and categories\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wos-starter.get-journal\n\
  \      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: advanced-search\n      description: Run advanced Web of Science search with full field tag syntax for comprehensive literature review\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wos-expanded.search-documents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-citing-papers\n      description: Find all papers that have cited a specific article (forward citation tracking)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wos-expanded.get-citing-articles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-references\n      description: Get the complete reference list of a paper (backward citation tracking)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wos-expanded.get-references\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: find-related-research\n      description: Discover research papers related to a given article based on shared references\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wos-expanded.get-related-records\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-citation-report\n      description: Generate a bibliometric citation report including h-index and year-by-year citation counts\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wos-expanded.get-citation-report\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-record-by-uid\n      description: Retrieve a full Web of Science record directly by its unique identifier\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wos-expanded.get-record-by-id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/web-of-science-apis/refs/heads/main/capabilities/academic-research.yaml
tags:
- Research
- Academic
- Bibliometrics
- Citations
- Literature Review
- Science
tools:
- description: Search Web of Science literature using advanced query syntax (e.g., TS=climate change AND PY=2020-2024)
  hints:
    openWorld: true
    readOnly: true
  name: search-literature
- description: Get full bibliographic details for a specific Web of Science document by UID
  hints:
    openWorld: false
    readOnly: true
  name: get-paper-details
- description: Look up a journal in Web of Science by ISSN or name to get impact metrics
  hints:
    openWorld: false
    readOnly: true
  name: find-journal
- description: Get detailed information about a journal including JCR profile and categories
  hints:
    openWorld: false
    readOnly: true
  name: get-journal-details
- description: Run advanced Web of Science search with full field tag syntax for comprehensive literature review
  hints:
    openWorld: true
    readOnly: true
  name: advanced-search
- description: Find all papers that have cited a specific article (forward citation tracking)
  hints:
    openWorld: true
    readOnly: true
  name: find-citing-papers
- description: Get the complete reference list of a paper (backward citation tracking)
  hints:
    openWorld: false
    readOnly: true
  name: get-references
- description: Discover research papers related to a given article based on shared references
  hints:
    openWorld: true
    readOnly: true
  name: find-related-research
- description: Generate a bibliometric citation report including h-index and year-by-year citation counts
  hints:
    openWorld: false
    readOnly: true
  name: generate-citation-report
- description: Retrieve a full Web of Science record directly by its unique identifier
  hints:
    openWorld: false
    readOnly: true
  name: get-record-by-uid
---
