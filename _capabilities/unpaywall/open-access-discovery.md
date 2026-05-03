---
api_specs:
- filename: unpaywall-openapi.yml
  format: yaml
  label: unpaywall
  slug: unpaywall
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/unpaywall/refs/heads/main/openapi/unpaywall-openapi.yml
categories: []
consumed_apis:
- unpaywall
description: Workflow capability for discovering free, legal full-text versions of scholarly articles using Unpaywall. Enables researchers, librarians, and developers to check open access status by DOI and search for articles by title. Returns full-text URLs, license information, and repository/publisher source details.
layout: capability
name: Unpaywall Open Access Discovery
operations:
- description: Get open access status and full-text links for an article
  method: GET
  name: get-oa-status
  path: /v1/articles/{doi}
- description: Search articles by title with optional OA filter
  method: GET
  name: search-articles
  path: /v1/search
personas: []
provider_name: Unpaywall
provider_slug: unpaywall
search_terms:
- doi
- open access lookup by doi
- academic
- title-based article search
- libraries
- search open access articles
- open access
- check open access
- scholarly articles
- research
- unpaywall
- get oa status
- get open access status and full-text links for an article
- search the unpaywall database by article title to find scholarly articles and their open access status. optionally filter to only open access results. returns up to 50 results per page with relevance scores.
- science
- search articles by title with optional oa filter
- search articles
- check if a scholarly article (identified by doi) has a free, legal open access version and return all available full-text links with license, host type (publisher/repository), and version information.
slug: open-access-discovery
source_filename: open-access-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Unpaywall Open Access Discovery\n  description: >-\n    Workflow capability for discovering free, legal full-text versions of scholarly\n    articles using Unpaywall. Enables researchers, librarians, and developers to\n    check open access status by DOI and search for articles by title. Returns\n    full-text URLs, license information, and repository/publisher source details.\n  tags:\n    - Unpaywall\n    - Open Access\n    - Research\n    - Scholarly Articles\n    - Academic\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNPAYWALL_EMAIL: UNPAYWALL_EMAIL\n\ncapability:\n  consumes:\n    - import: unpaywall\n      location: ./shared/unpaywall.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: unpaywall-discovery-api\n      description: Unified REST API for open access article discovery via Unpaywall.\n      resources:\n        - path: /v1/articles/{doi}\n\
  \          name: article-by-doi\n          description: Open access lookup by DOI\n          operations:\n            - method: GET\n              name: get-oa-status\n              description: Get open access status and full-text links for an article\n              call: \"unpaywall.get-by-doi\"\n              with:\n                doi: \"rest.doi\"\n                email: \"rest.email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/search\n          name: article-search\n          description: Title-based article search\n          operations:\n            - method: GET\n              name: search-articles\n              description: Search articles by title with optional OA filter\n              call: \"unpaywall.search-by-title\"\n              with:\n                query: \"rest.query\"\n                email: \"rest.email\"\n                is_oa: \"rest.is_oa\"\n                page: \"rest.page\"\n \
  \             outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: unpaywall-discovery-mcp\n      transport: http\n      description: MCP server for AI-assisted open access scholarly article discovery.\n      tools:\n        - name: check-open-access\n          description: >-\n            Check if a scholarly article (identified by DOI) has a free, legal\n            open access version and return all available full-text links with\n            license, host type (publisher/repository), and version information.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"unpaywall.get-by-doi\"\n          with:\n            doi: \"tools.doi\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-open-access-articles\n          description: >-\n            Search the Unpaywall\
  \ database by article title to find scholarly articles\n            and their open access status. Optionally filter to only open access results.\n            Returns up to 50 results per page with relevance scores.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"unpaywall.search-by-title\"\n          with:\n            query: \"tools.query\"\n            email: \"tools.email\"\n            is_oa: \"tools.is_oa\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unpaywall/refs/heads/main/capabilities/open-access-discovery.yaml
tags:
- Unpaywall
- Open Access
- Research
- Scholarly Articles
- Academic
tools:
- description: Check if a scholarly article (identified by DOI) has a free, legal open access version and return all available full-text links with license, host type (publisher/repository), and version information.
  hints:
    openWorld: true
    readOnly: true
  name: check-open-access
- description: Search the Unpaywall database by article title to find scholarly articles and their open access status. Optionally filter to only open access results. Returns up to 50 results per page with relevance scores.
  hints:
    openWorld: true
    readOnly: true
  name: search-open-access-articles
---
