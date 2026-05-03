---
categories: []
consumed_apis:
- wos-starter
- wos-expanded
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
- individual document
- citations
- search web of science literature using advanced query syntax (e.g., ts=climate change and py=2020-2024)
- research
- search documents
- discover research papers related to a given article based on shared references
- science
- find journal
- get references
- journal search
- get document by uid
- look up a journal in web of science by issn or name to get impact metrics
- get citation report
- find all papers that have cited a specific article (forward citation tracking)
- search literature
- get full bibliographic details for a specific web of science document by uid
- related records
- get detailed information about a journal including jcr profile and categories
- get document reference list
- get citing articles
- search journals by issn or name
- search journals
- find related research
- generate a bibliometric citation report including h-index and year-by-year citation counts
- get the complete reference list of a paper (backward citation tracking)
- run advanced web of science search with full field tag syntax for comprehensive literature review
- citation report
- get related records
- scholarly
- get document
- retrieve a full web of science record directly by its unique identifier
- generate citation report
- bibliometrics
- search web of science documents
- get record by uid
- academic
- get journal details
- literature review
- get citation report for query
- get paper details
- document references
- find citing papers
- advanced search
- document search
- articles citing a document
slug: academic-research
source_filename: academic-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Web of Science Academic Research\"\n  description: \"Unified academic research workflow combining Web of Science Starter and Expanded APIs for bibliographic search, citation analysis, journal discovery, and bibliometric reporting. Used by researchers, librarians, and data analysts to automate literature review and citation analysis.\"\n  tags:\n    - Research\n    - Academic\n    - Bibliometrics\n    - Citations\n    - Literature Review\n    - Science\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WOS_API_KEY: WOS_API_KEY\n\ncapability:\n  consumes:\n    - import: wos-starter\n      location: ./shared/web-of-science-starter-api.yaml\n    - import: wos-expanded\n      location: ./shared/web-of-science-expanded-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: academic-research-api\n      description: \"Unified REST API for Web of Science academic\
  \ research operations.\"\n      resources:\n        - path: /v1/documents/search\n          name: document-search\n          description: \"Document search\"\n          operations:\n            - method: GET\n              name: search-documents\n              description: \"Search Web of Science documents\"\n              call: \"wos-starter.search-documents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/{uid}\n          name: document\n          description: \"Individual document\"\n          operations:\n            - method: GET\n              name: get-document\n              description: \"Get document by UID\"\n              call: \"wos-starter.get-document\"\n              with:\n                uid: \"rest.uid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/journals\n          name: journals\n          description: \"\
  Journal search\"\n          operations:\n            - method: GET\n              name: search-journals\n              description: \"Search journals by ISSN or name\"\n              call: \"wos-starter.search-journals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/citations/citing\n          name: citing-articles\n          description: \"Articles citing a document\"\n          operations:\n            - method: GET\n              name: get-citing-articles\n              description: \"Get citing articles\"\n              call: \"wos-expanded.get-citing-articles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/citations/references\n          name: references\n          description: \"Document references\"\n          operations:\n            - method: GET\n              name: get-references\n              description: \"Get document reference\
  \ list\"\n              call: \"wos-expanded.get-references\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/citations/related\n          name: related-records\n          description: \"Related records\"\n          operations:\n            - method: GET\n              name: get-related-records\n              description: \"Get related records\"\n              call: \"wos-expanded.get-related-records\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/citations/{queryId}\n          name: citation-report\n          description: \"Citation report\"\n          operations:\n            - method: GET\n              name: get-citation-report\n              description: \"Get citation report for query\"\n              call: \"wos-expanded.get-citation-report\"\n              with:\n                queryId: \"rest.queryId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9094\n      namespace: academic-research-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Web of Science academic research.\"\n      tools:\n        - name: search-literature\n          description: \"Search Web of Science literature using advanced query syntax (e.g., TS=climate change AND PY=2020-2024)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wos-starter.search-documents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-paper-details\n          description: \"Get full bibliographic details for a specific Web of Science document by UID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wos-starter.get-document\"\n          with:\n            uid: \"tools.uid\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n        - name: find-journal\n          description: \"Look up a journal in Web of Science by ISSN or name to get impact metrics\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wos-starter.search-journals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-journal-details\n          description: \"Get detailed information about a journal including JCR profile and categories\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wos-starter.get-journal\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: advanced-search\n          description: \"Run advanced Web of Science search with full field tag syntax for comprehensive literature review\"\n          hints:\n            readOnly: true\n   \
  \         openWorld: true\n          call: \"wos-expanded.search-documents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-citing-papers\n          description: \"Find all papers that have cited a specific article (forward citation tracking)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wos-expanded.get-citing-articles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-references\n          description: \"Get the complete reference list of a paper (backward citation tracking)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wos-expanded.get-references\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-related-research\n          description: \"Discover research papers related to a given article based on shared\
  \ references\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wos-expanded.get-related-records\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: generate-citation-report\n          description: \"Generate a bibliometric citation report including h-index and year-by-year citation counts\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wos-expanded.get-citation-report\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-record-by-uid\n          description: \"Retrieve a full Web of Science record directly by its unique identifier\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wos-expanded.get-record-by-id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
