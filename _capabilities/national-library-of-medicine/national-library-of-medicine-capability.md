---
categories: []
consumed_apis: []
description: The Entrez Programming Utilities (E-utilities) are a public API to the NCBI Entrez system, providing access to all Entrez databases including PubMed, PMC, Gene, Nuccore, and Protein. The E-utilities are a suite of nine server-side programs that accept a fixed URL syntax for search, link, and retrieval operations. Maintained by the National Center for Biotechnology Information (NCBI), part of the U.S. National Library of Medicine.
layout: capability
name: NCBI E-utilities API
operations:
- description: Search a database
  method: GET
  name: esearch
  path: /esearch.fcgi
- description: Fetch full records by UID
  method: GET
  name: efetch
  path: /efetch.fcgi
- description: Retrieve document summaries
  method: GET
  name: esummary
  path: /esummary.fcgi
- description: Database statistics and field metadata
  method: GET
  name: einfo
  path: /einfo.fcgi
- description: Find related records across Entrez databases
  method: GET
  name: elink
  path: /elink.fcgi
- description: Post UIDs to the Entrez History server
  method: POST
  name: epost
  path: /epost.fcgi
- description: Spelling suggestions for a query term
  method: GET
  name: espell
  path: /espell.fcgi
- description: Match citations to PubMed UIDs
  method: GET
  name: ecitmatch
  path: /ecitmatch.cgi
- description: Global cross-database query
  method: GET
  name: egquery
  path: /egquery.fcgi
personas: []
provider_name: National Library of Medicine
provider_slug: national-library-of-medicine
search_terms:
- database statistics and field metadata
- retrieve document summaries
- fetch full records by uid
- api
- health
- efetch
- ecitmatch
- post uids to the entrez history server
- egquery
- library
- esummary
- search a database
- epost
- of
- elink
- find related records across entrez databases
- spelling suggestions for a query term
- einfo
- esearch
- espell
- match citations to pubmed uids
- medicine
- global cross-database query
- federal government
- national
slug: national-library-of-medicine-capability
source_filename: national-library-of-medicine-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NCBI E-utilities API\n  description: The Entrez Programming Utilities (E-utilities) are a public API to the NCBI Entrez system, providing access\n    to all Entrez databases including PubMed, PMC, Gene, Nuccore, and Protein. The E-utilities are a suite of nine server-side\n    programs that accept a fixed URL syntax for search, link, and retrieval operations. Maintained by the National Center\n    for Biotechnology Information (NCBI), part of the U.S. National Library of Medicine.\n  tags:\n  - National\n  - Library\n  - Of\n  - Medicine\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: national-library-of-medicine\n    baseUri: https://eutils.ncbi.nlm.nih.gov/entrez/eutils\n    description: NCBI E-utilities API HTTP API.\n    resources:\n    - name: esearch-fcgi\n      path: /esearch.fcgi\n      operations:\n      - name: esearch\n        method: GET\n        description:\
  \ Search a database\n        inputParameters:\n        - name: db\n          in: query\n          type: string\n          required: true\n          description: Database to search (e.g. pubmed, pmc, gene, protein, nuccore).\n        - name: term\n          in: query\n          type: string\n          required: true\n          description: Entrez text query, URL-encoded.\n        - name: usehistory\n          in: query\n          type: string\n          description: Set to 'y' to post UIDs to the History server.\n        - name: retmax\n          in: query\n          type: integer\n          description: Maximum number of UIDs to return (default 20, max 10000).\n        - name: retstart\n          in: query\n          type: integer\n          description: Sequential index of the first UID to return (zero-based).\n        - name: retmode\n          in: query\n          type: string\n          description: Output format.\n        - name: api_key\n          in: query\n          type: string\n\
  \          description: NCBI API key for higher rate limits.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: efetch-fcgi\n      path: /efetch.fcgi\n      operations:\n      - name: efetch\n        method: GET\n        description: Fetch full records by UID\n        inputParameters:\n        - name: db\n          in: query\n          type: string\n          required: true\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of UIDs or a WebEnv/query_key reference.\n        - name: rettype\n          in: query\n          type: string\n          description: Retrieval type (e.g. abstract, fasta, gb, medline).\n        - name: retmode\n          in: query\n          type: string\n          description: Retrieval mode (e.g. xml, text, json, asn.1).\n        - name: api_key\n          in: query\n          type: string\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: esummary-fcgi\n      path: /esummary.fcgi\n      operations:\n      - name: esummary\n        method: GET\n        description: Retrieve document summaries\n        inputParameters:\n        - name: db\n          in: query\n          type: string\n          required: true\n        - name: id\n          in: query\n          type: string\n          required: true\n        - name: version\n          in: query\n          type: string\n          description: Set to '2.0' for the newer DocSum schema.\n        - name: retmode\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: einfo-fcgi\n      path: /einfo.fcgi\n      operations:\n      - name: einfo\n        method: GET\n        description: Database statistics and field metadata\n\
  \        inputParameters:\n        - name: db\n          in: query\n          type: string\n        - name: retmode\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: elink-fcgi\n      path: /elink.fcgi\n      operations:\n      - name: elink\n        method: GET\n        description: Find related records across Entrez databases\n        inputParameters:\n        - name: dbfrom\n          in: query\n          type: string\n          required: true\n        - name: db\n          in: query\n          type: string\n        - name: id\n          in: query\n          type: string\n          required: true\n        - name: linkname\n          in: query\n          type: string\n        - name: cmd\n          in: query\n          type: string\n          description: Command mode (neighbor, neighbor_history, llinks, prlinks, etc.).\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: epost-fcgi\n      path: /epost.fcgi\n      operations:\n      - name: epost\n        method: POST\n        description: Post UIDs to the Entrez History server\n        inputParameters:\n        - name: db\n          in: query\n          type: string\n          required: true\n        - name: id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: espell-fcgi\n      path: /espell.fcgi\n      operations:\n      - name: espell\n        method: GET\n        description: Spelling suggestions for a query term\n        inputParameters:\n        - name: db\n          in: query\n          type: string\n          required: true\n        - name: term\n          in: query\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ecitmatch-cgi\n      path: /ecitmatch.cgi\n      operations:\n      - name: ecitmatch\n        method: GET\n        description: Match citations to PubMed UIDs\n        inputParameters:\n        - name: db\n          in: query\n          type: string\n          required: true\n        - name: rettype\n          in: query\n          type: string\n        - name: bdata\n          in: query\n          type: string\n          required: true\n          description: Pipe-delimited citation strings.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: egquery-fcgi\n      path: /egquery.fcgi\n      operations:\n      - name: egquery\n        method: GET\n        description: Global cross-database query\n        inputParameters:\n        - name: term\n          in: query\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: national-library-of-medicine-rest\n    description: REST adapter for NCBI E-utilities API.\n    resources:\n    - path: /esearch.fcgi\n      name: esearch\n      operations:\n      - method: GET\n        name: esearch\n        description: Search a database\n        call: national-library-of-medicine.esearch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /efetch.fcgi\n      name: efetch\n      operations:\n      - method: GET\n        name: efetch\n        description: Fetch full records by UID\n        call: national-library-of-medicine.efetch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /esummary.fcgi\n      name: esummary\n      operations:\n      - method: GET\n        name: esummary\n      \
  \  description: Retrieve document summaries\n        call: national-library-of-medicine.esummary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /einfo.fcgi\n      name: einfo\n      operations:\n      - method: GET\n        name: einfo\n        description: Database statistics and field metadata\n        call: national-library-of-medicine.einfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /elink.fcgi\n      name: elink\n      operations:\n      - method: GET\n        name: elink\n        description: Find related records across Entrez databases\n        call: national-library-of-medicine.elink\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /epost.fcgi\n      name: epost\n      operations:\n      - method: POST\n        name: epost\n        description: Post UIDs to the Entrez History server\n        call: national-library-of-medicine.epost\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /espell.fcgi\n      name: espell\n      operations:\n      - method: GET\n        name: espell\n        description: Spelling suggestions for a query term\n        call: national-library-of-medicine.espell\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ecitmatch.cgi\n      name: ecitmatch\n      operations:\n      - method: GET\n        name: ecitmatch\n        description: Match citations to PubMed UIDs\n        call: national-library-of-medicine.ecitmatch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /egquery.fcgi\n      name: egquery\n      operations:\n      - method: GET\n        name: egquery\n        description: Global cross-database query\n        call: national-library-of-medicine.egquery\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: national-library-of-medicine-mcp\n\
  \    transport: http\n    description: MCP adapter for NCBI E-utilities API for AI agent use.\n    tools:\n    - name: esearch\n      description: Search a database\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-library-of-medicine.esearch\n      with:\n        db: tools.db\n        term: tools.term\n        usehistory: tools.usehistory\n        retmax: tools.retmax\n        retstart: tools.retstart\n        retmode: tools.retmode\n        api_key: tools.api_key\n      inputParameters:\n      - name: db\n        type: string\n        description: Database to search (e.g. pubmed, pmc, gene, protein, nuccore).\n        required: true\n      - name: term\n        type: string\n        description: Entrez text query, URL-encoded.\n        required: true\n      - name: usehistory\n        type: string\n        description: Set to 'y' to post UIDs to the History server.\n      - name: retmax\n        type: integer\n        description:\
  \ Maximum number of UIDs to return (default 20, max 10000).\n      - name: retstart\n        type: integer\n        description: Sequential index of the first UID to return (zero-based).\n      - name: retmode\n        type: string\n        description: Output format.\n      - name: api_key\n        type: string\n        description: NCBI API key for higher rate limits.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: efetch\n      description: Fetch full records by UID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-library-of-medicine.efetch\n      with:\n        db: tools.db\n        id: tools.id\n        rettype: tools.rettype\n        retmode: tools.retmode\n        api_key: tools.api_key\n      inputParameters:\n      - name: db\n        type: string\n        description: db\n        required: true\n      - name: id\n        type: string\n        description: Comma-separated list of\
  \ UIDs or a WebEnv/query_key reference.\n        required: true\n      - name: rettype\n        type: string\n        description: Retrieval type (e.g. abstract, fasta, gb, medline).\n      - name: retmode\n        type: string\n        description: Retrieval mode (e.g. xml, text, json, asn.1).\n      - name: api_key\n        type: string\n        description: api_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: esummary\n      description: Retrieve document summaries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-library-of-medicine.esummary\n      with:\n        db: tools.db\n        id: tools.id\n        version: tools.version\n        retmode: tools.retmode\n      inputParameters:\n      - name: db\n        type: string\n        description: db\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      - name: version\n\
  \        type: string\n        description: Set to '2.0' for the newer DocSum schema.\n      - name: retmode\n        type: string\n        description: retmode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: einfo\n      description: Database statistics and field metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-library-of-medicine.einfo\n      with:\n        db: tools.db\n        retmode: tools.retmode\n      inputParameters:\n      - name: db\n        type: string\n        description: db\n      - name: retmode\n        type: string\n        description: retmode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: elink\n      description: Find related records across Entrez databases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-library-of-medicine.elink\n      with:\n        dbfrom:\
  \ tools.dbfrom\n        db: tools.db\n        id: tools.id\n        linkname: tools.linkname\n        cmd: tools.cmd\n      inputParameters:\n      - name: dbfrom\n        type: string\n        description: dbfrom\n        required: true\n      - name: db\n        type: string\n        description: db\n      - name: id\n        type: string\n        description: id\n        required: true\n      - name: linkname\n        type: string\n        description: linkname\n      - name: cmd\n        type: string\n        description: Command mode (neighbor, neighbor_history, llinks, prlinks, etc.).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: epost\n      description: Post UIDs to the Entrez History server\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: national-library-of-medicine.epost\n      with:\n        db: tools.db\n        id: tools.id\n      inputParameters:\n      - name: db\n        type:\
  \ string\n        description: db\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: espell\n      description: Spelling suggestions for a query term\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-library-of-medicine.espell\n      with:\n        db: tools.db\n        term: tools.term\n      inputParameters:\n      - name: db\n        type: string\n        description: db\n        required: true\n      - name: term\n        type: string\n        description: term\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ecitmatch\n      description: Match citations to PubMed UIDs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-library-of-medicine.ecitmatch\n      with:\n\
  \        db: tools.db\n        rettype: tools.rettype\n        bdata: tools.bdata\n      inputParameters:\n      - name: db\n        type: string\n        description: db\n        required: true\n      - name: rettype\n        type: string\n        description: rettype\n      - name: bdata\n        type: string\n        description: Pipe-delimited citation strings.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: egquery\n      description: Global cross-database query\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-library-of-medicine.egquery\n      with:\n        term: tools.term\n      inputParameters:\n      - name: term\n        type: string\n        description: term\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/national-library-of-medicine/refs/heads/main/capabilities/national-library-of-medicine-capability.yaml
tags:
- National
- Library
- Of
- Medicine
- API
tools:
- description: Search a database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: esearch
- description: Fetch full records by UID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: efetch
- description: Retrieve document summaries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: esummary
- description: Database statistics and field metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: einfo
- description: Find related records across Entrez databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: elink
- description: Post UIDs to the Entrez History server
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: epost
- description: Spelling suggestions for a query term
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: espell
- description: Match citations to PubMed UIDs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ecitmatch
- description: Global cross-database query
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: egquery
---
