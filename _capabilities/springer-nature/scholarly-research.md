---
categories: []
consumed_apis: []
description: Workflow capability for discovering and accessing Springer Nature scholarly content. Combines metadata search and open access APIs for comprehensive literature discovery. Used by researchers, data scientists, bibliometricians, and academic application developers.
layout: capability
name: Springer Nature - Scholarly Research Discovery
operations:
- description: Search all Springer Nature publications by keyword, author, DOI, ISSN, or subject
  method: GET
  name: search-publications
  path: /v1/publications
- description: Search freely available open access articles and chapters
  method: GET
  name: search-open-access
  path: /v1/open-access
personas: []
provider_name: Springer Nature
provider_slug: springer-nature
search_terms:
- scientific publishing
- academic publishing
- 'search springer nature''s 14m+ scholarly publications. use field qualifiers: doi:10.1007/..., title:machine learning, author:smith, issn:0028-4793, subject:computer science, onlinedatefrom:2024-01-01'
- search freely available open access articles and chapters
- research
- find journal articles
- find publications by author
- full text
- bibliometrics
- search open access articles
- look up a specific springer nature publication by its doi
- search open access springer nature content
- search springer nature open access articles and chapters that are freely available. returns metadata with links to full-text html and pdf content.
- literature discovery
- find publications by doi
- scholarly content
- find all springer nature publications by a specific author name
- search publications
- open access
- search all springer nature publications by keyword, author, doi, issn, or subject
- search springer nature publication metadata
- find articles published in a specific springer nature journal by issn
- search open access
slug: scholarly-research
source_filename: scholarly-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Springer Nature - Scholarly Research Discovery\n  description: Workflow capability for discovering and accessing Springer Nature scholarly content. Combines metadata search\n    and open access APIs for comprehensive literature discovery. Used by researchers, data scientists, bibliometricians, and\n    academic application developers.\n  tags:\n  - Academic Publishing\n  - Bibliometrics\n  - Full Text\n  - Literature Discovery\n  - Open Access\n  - Research\n  - Scholarly Content\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPRINGER_NATURE_API_KEY: SPRINGER_NATURE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: springer-nature-meta\n    baseUri: https://api.springernature.com/meta/v2\n    description: Springer Nature versioned metadata API\n    authentication:\n      type: apikey\n      key: X-ApiKey\n      value: '{{env.SPRINGER_NATURE_API_KEY}}'\n      placement: header\n\
  \    resources:\n    - name: metadata-search\n      path: /json\n      description: Search Springer Nature publication metadata\n      operations:\n      - name: search-publications\n        method: GET\n        description: Search metadata for scholarly publications with field qualifiers\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query string with field qualifiers (doi:, title:, author:, issn:, subject:)\n        - name: s\n          in: query\n          type: integer\n          required: false\n          description: Start record (1-based)\n        - name: p\n          in: query\n          type: integer\n          required: false\n          description: Results per page (max 100)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: springer-nature-openaccess\n    baseUri: https://api.springernature.com/openaccess\n\
  \    description: Springer Nature Open Access content API\n    authentication:\n      type: apikey\n      key: X-ApiKey\n      value: '{{env.SPRINGER_NATURE_API_KEY}}'\n      placement: header\n    resources:\n    - name: open-access-search\n      path: /json\n      description: Search open access publications\n      operations:\n      - name: search-open-access\n        method: GET\n        description: Search open access articles and chapters\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query with field qualifiers\n        - name: s\n          in: query\n          type: integer\n          required: false\n          description: Start record (1-based)\n        - name: p\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: scholarly-research-api\n    description: Unified REST API for Springer Nature scholarly content discovery.\n    resources:\n    - path: /v1/publications\n      name: publications\n      description: Search Springer Nature publication metadata\n      operations:\n      - method: GET\n        name: search-publications\n        description: Search all Springer Nature publications by keyword, author, DOI, ISSN, or subject\n        call: springer-nature-meta.search-publications\n        with:\n          q: rest.q\n          s: rest.s\n          p: rest.p\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/open-access\n      name: open-access\n      description: Search open access Springer Nature content\n      operations:\n      - method: GET\n        name: search-open-access\n        description: Search freely available open access articles and chapters\n        call: springer-nature-openaccess.search-open-access\n\
  \        with:\n          q: rest.q\n          s: rest.s\n          p: rest.p\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: scholarly-research-mcp\n    transport: http\n    description: MCP server for AI-assisted scholarly literature discovery via Springer Nature.\n    tools:\n    - name: search-publications\n      description: 'Search Springer Nature''s 14M+ scholarly publications. Use field qualifiers: doi:10.1007/..., title:machine\n        learning, author:Smith, issn:0028-4793, subject:Computer Science, onlinedatefrom:2024-01-01'\n      hints:\n        readOnly: true\n        openWorld: true\n      call: springer-nature-meta.search-publications\n      with:\n        q: tools.query\n        s: tools.start\n        p: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-open-access-articles\n      description: Search Springer Nature open access articles and chapters\
  \ that are freely available. Returns metadata with\n        links to full-text HTML and PDF content.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: springer-nature-openaccess.search-open-access\n      with:\n        q: tools.query\n        s: tools.start\n        p: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-publications-by-doi\n      description: Look up a specific Springer Nature publication by its DOI\n      hints:\n        readOnly: true\n        openWorld: false\n      call: springer-nature-meta.search-publications\n      with:\n        q: tools.doi\n        p: '1'\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-publications-by-author\n      description: Find all Springer Nature publications by a specific author name\n      hints:\n        readOnly: true\n        openWorld: true\n      call: springer-nature-meta.search-publications\n      with:\n        q: tools.authorQuery\n\
  \        s: tools.start\n        p: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-journal-articles\n      description: Find articles published in a specific Springer Nature journal by ISSN\n      hints:\n        readOnly: true\n        openWorld: true\n      call: springer-nature-meta.search-publications\n      with:\n        q: tools.issnQuery\n        s: tools.start\n        p: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/springer-nature/refs/heads/main/capabilities/scholarly-research.yaml
tags:
- Academic Publishing
- Bibliometrics
- Full Text
- Literature Discovery
- Open Access
- Research
- Scholarly Content
tools:
- description: 'Search Springer Nature''s 14M+ scholarly publications. Use field qualifiers: doi:10.1007/..., title:machine learning, author:Smith, issn:0028-4793, subject:Computer Science, onlinedatefrom:2024-01-01'
  hints:
    openWorld: true
    readOnly: true
  name: search-publications
- description: Search Springer Nature open access articles and chapters that are freely available. Returns metadata with links to full-text HTML and PDF content.
  hints:
    openWorld: true
    readOnly: true
  name: search-open-access-articles
- description: Look up a specific Springer Nature publication by its DOI
  hints:
    openWorld: false
    readOnly: true
  name: find-publications-by-doi
- description: Find all Springer Nature publications by a specific author name
  hints:
    openWorld: true
    readOnly: true
  name: find-publications-by-author
- description: Find articles published in a specific Springer Nature journal by ISSN
  hints:
    openWorld: true
    readOnly: true
  name: find-journal-articles
---
