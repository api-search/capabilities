---
categories: []
consumed_apis: []
description: Unified capability for biomedical literature research and clinical trial discovery workflows combining NCBI E-Utilities (PubMed, Entrez databases) with ClinicalTrials.gov. Used by researchers, clinicians, bioinformaticians, and healthcare professionals to search literature, find clinical trials, retrieve gene data, and explore biomedical databases.
layout: capability
name: NLM Biomedical Literature and Clinical Research
operations:
- description: Search PubMed for articles by query, author, or topic
  method: GET
  name: search-pubmed
  path: /v1/pubmed/search
- description: Fetch full PubMed article records by PMID
  method: GET
  name: get-pubmed-articles
  path: /v1/pubmed/articles/{pmids}
- description: Search NCBI Gene database for gene records
  method: GET
  name: search-genes
  path: /v1/gene/search
- description: Search clinical trials by condition, intervention, or status
  method: GET
  name: search-trials
  path: /v1/trials/search
- description: Get complete clinical trial record by NCT ID
  method: GET
  name: get-trial
  path: /v1/trials/{nctId}
personas: []
provider_name: United States National Library of Medicine
provider_slug: united-states-national-library-of-medicine
search_terms:
- get pubmed summaries
- search pubmed for articles by query, author, or topic
- retrieve a specific clinical trial
- search ncbi gene database for gene records by symbol, name, or description
- literature
- fetch full pubmed article records by pmid
- clinical trials
- search ncbi gene database for gene records
- retrieve complete protocol, eligibility, and results for a clinical trial by nct id
- get clinical trial details
- retrieve pubmed article records
- search pubmed biomedical literature database
- search ncbi database
- retrieve pubmed article abstracts for a list of pmids
- get pubmed abstracts
- healthcare
- pubmed
- search genes
- search clinical trials by condition, intervention, or status
- search any ncbi entrez database (nuccore, protein, snp, taxonomy, sra, etc.)
- search pubmed
- search clinicaltrials.gov for trials by condition, intervention, phase, or status
- nlm
- search ncbi gene database
- biomedical research
- get pubmed document summaries including title, authors, and journal for pmids
- search clinical trials
- get pubmed articles
- get trial
- federal government
- search trials
- genomics
- search clinicaltrials.gov for clinical trials
- get complete clinical trial record by nct id
- search pubmed for biomedical literature articles by topic, author, or keywords
slug: biomedical-literature-research
source_filename: biomedical-literature-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NLM Biomedical Literature and Clinical Research\n  description: Unified capability for biomedical literature research and clinical trial discovery workflows combining NCBI\n    E-Utilities (PubMed, Entrez databases) with ClinicalTrials.gov. Used by researchers, clinicians, bioinformaticians, and\n    healthcare professionals to search literature, find clinical trials, retrieve gene data, and explore biomedical databases.\n  tags:\n  - Biomedical Research\n  - PubMed\n  - Clinical Trials\n  - Genomics\n  - Healthcare\n  - NLM\n  - Federal Government\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    NCBI_API_KEY: NCBI_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: eutils\n    baseUri: https://eutils.ncbi.nlm.nih.gov/entrez/eutils\n    description: NCBI E-Utilities Entrez API\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{NCBI_API_KEY}}'\n      placement:\
  \ query\n    resources:\n    - name: search\n      path: /esearch.fcgi\n      description: Search Entrez databases\n      operations:\n      - name: search-database\n        method: GET\n        description: Search Entrez Database\n        inputParameters:\n        - name: db\n          in: query\n          type: string\n          required: true\n          description: Target database (pubmed, gene, nuccore, etc.)\n        - name: term\n          in: query\n          type: string\n          required: true\n          description: Search query with optional field tags\n        - name: retmax\n          in: query\n          type: integer\n          required: false\n          description: Max UIDs to return\n        - name: retstart\n          in: query\n          type: integer\n          required: false\n          description: Starting index\n        - name: retmode\n          in: query\n          type: string\n          required: false\n          description: Output format (json or xml)\n\
  \        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort order\n        - name: datetype\n          in: query\n          type: string\n          required: false\n          description: Date field type\n        - name: mindate\n          in: query\n          type: string\n          required: false\n          description: Minimum date\n        - name: maxdate\n          in: query\n          type: string\n          required: false\n          description: Maximum date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fetch\n      path: /efetch.fcgi\n      description: Retrieve full records from Entrez\n      operations:\n      - name: fetch-records\n        method: GET\n        description: Fetch Records\n        inputParameters:\n        - name: db\n          in: query\n          type: string\n          required: true\n          description:\
  \ Target database\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated UIDs\n        - name: rettype\n          in: query\n          type: string\n          required: false\n          description: Record type (abstract, medline, fasta, etc.)\n        - name: retmode\n          in: query\n          type: string\n          required: false\n          description: Output format (xml, text, json)\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: summary\n      path: /esummary.fcgi\n      description: Retrieve document summaries\n      operations:\n      - name: get-summaries\n        method: GET\n        description: Get Document Summaries\n        inputParameters:\n        - name: db\n          in: query\n          type: string\n          required: true\n          description: Target database\n        - name: id\n          in:\
  \ query\n          type: string\n          required: false\n          description: Comma-separated UIDs\n        - name: retmode\n          in: query\n          type: string\n          required: false\n          description: Output format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: link\n      path: /elink.fcgi\n      description: Find linked records across databases\n      operations:\n      - name: get-linkages\n        method: GET\n        description: Get Linked Records\n        inputParameters:\n        - name: dbfrom\n          in: query\n          type: string\n          required: true\n          description: Source database\n        - name: db\n          in: query\n          type: string\n          required: false\n          description: Target database\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: Source UIDs\n   \
  \     - name: linkname\n          in: query\n          type: string\n          required: false\n          description: Named link\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: clinicaltrials\n    baseUri: https://clinicaltrials.gov/api/v2\n    description: ClinicalTrials.gov REST API v2 - no authentication required\n    resources:\n    - name: studies\n      path: /studies\n      description: Search and retrieve clinical trial studies\n      operations:\n      - name: search-studies\n        method: GET\n        description: Search Clinical Trial Studies\n        inputParameters:\n        - name: query.term\n          in: query\n          type: string\n          required: false\n          description: Full-text search query\n        - name: query.cond\n          in: query\n          type: string\n          required: false\n          description: Condition or disease filter\n\
  \        - name: query.intr\n          in: query\n          type: string\n          required: false\n          description: Intervention or treatment filter\n        - name: query.spons\n          in: query\n          type: string\n          required: false\n          description: Sponsor filter\n        - name: filter.overallStatus\n          in: query\n          type: string\n          required: false\n          description: Overall status filter\n        - name: filter.phase\n          in: query\n          type: string\n          required: false\n          description: Clinical trial phase filter\n        - name: filter.studyType\n          in: query\n          type: string\n          required: false\n          description: Study type filter\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n    \
  \      description: Next page token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: study-by-id\n      path: /studies/{nctId}\n      description: Retrieve a specific clinical trial by NCT ID\n      operations:\n      - name: get-study\n        method: GET\n        description: Get Study by NCT ID\n        inputParameters:\n        - name: nctId\n          in: path\n          type: string\n          required: true\n          description: ClinicalTrials.gov NCT identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dataset-size\n      path: /stats/size\n      description: Get total count of studies matching criteria\n      operations:\n      - name: get-dataset-size\n        method: GET\n        description: Get Dataset Size\n        inputParameters:\n        - name: query.cond\n          in: query\n  \
  \        type: string\n          required: false\n          description: Condition filter for count\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nlm-research-api\n    description: Unified REST API for NLM biomedical literature and clinical research workflows.\n    resources:\n    - path: /v1/pubmed/search\n      name: pubmed-search\n      description: Search PubMed biomedical literature database\n      operations:\n      - method: GET\n        name: search-pubmed\n        description: Search PubMed for articles by query, author, or topic\n        call: eutils.search-database\n        with:\n          db: pubmed\n          term: rest.query\n          retmax: rest.limit\n          sort: rest.sort\n          mindate: rest.mindate\n          maxdate: rest.maxdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pubmed/articles/{pmids}\n\
  \      name: pubmed-articles\n      description: Retrieve PubMed article records\n      operations:\n      - method: GET\n        name: get-pubmed-articles\n        description: Fetch full PubMed article records by PMID\n        call: eutils.fetch-records\n        with:\n          db: pubmed\n          id: rest.pmids\n          rettype: abstract\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gene/search\n      name: gene-search\n      description: Search NCBI Gene database\n      operations:\n      - method: GET\n        name: search-genes\n        description: Search NCBI Gene database for gene records\n        call: eutils.search-database\n        with:\n          db: gene\n          term: rest.query\n          retmax: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trials/search\n      name: trial-search\n      description: Search ClinicalTrials.gov for clinical trials\n      operations:\n\
  \      - method: GET\n        name: search-trials\n        description: Search clinical trials by condition, intervention, or status\n        call: clinicaltrials.search-studies\n        with:\n          query.cond: rest.condition\n          query.intr: rest.intervention\n          filter.overallStatus: rest.status\n          filter.phase: rest.phase\n          pageSize: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trials/{nctId}\n      name: trial-detail\n      description: Retrieve a specific clinical trial\n      operations:\n      - method: GET\n        name: get-trial\n        description: Get complete clinical trial record by NCT ID\n        call: clinicaltrials.get-study\n        with:\n          nctId: rest.nctId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nlm-research-mcp\n    transport: http\n    description: MCP server for AI-assisted biomedical\
  \ literature search and clinical research.\n    tools:\n    - name: search-pubmed\n      description: Search PubMed for biomedical literature articles by topic, author, or keywords\n      hints:\n        readOnly: true\n        idempotent: true\n      call: eutils.search-database\n      with:\n        db: pubmed\n        term: tools.query\n        retmax: tools.max_results\n        sort: tools.sort\n        mindate: tools.start_date\n        maxdate: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pubmed-abstracts\n      description: Retrieve PubMed article abstracts for a list of PMIDs\n      hints:\n        readOnly: true\n        idempotent: true\n      call: eutils.fetch-records\n      with:\n        db: pubmed\n        id: tools.pmids\n        rettype: abstract\n        retmode: text\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pubmed-summaries\n      description: Get PubMed document summaries\
  \ including title, authors, and journal for PMIDs\n      hints:\n        readOnly: true\n        idempotent: true\n      call: eutils.get-summaries\n      with:\n        db: pubmed\n        id: tools.pmids\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-genes\n      description: Search NCBI Gene database for gene records by symbol, name, or description\n      hints:\n        readOnly: true\n        idempotent: true\n      call: eutils.search-database\n      with:\n        db: gene\n        term: tools.query\n        retmax: tools.max_results\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-clinical-trials\n      description: Search ClinicalTrials.gov for trials by condition, intervention, phase, or status\n      hints:\n        readOnly: true\n        idempotent: true\n      call: clinicaltrials.search-studies\n      with:\n        query.cond: tools.condition\n        query.intr: tools.intervention\n       \
  \ query.spons: tools.sponsor\n        filter.overallStatus: tools.status\n        filter.phase: tools.phase\n        pageSize: tools.page_size\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-clinical-trial-details\n      description: Retrieve complete protocol, eligibility, and results for a clinical trial by NCT ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: clinicaltrials.get-study\n      with:\n        nctId: tools.nct_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-ncbi-database\n      description: Search any NCBI Entrez database (nuccore, protein, snp, taxonomy, sra, etc.)\n      hints:\n        readOnly: true\n        idempotent: true\n      call: eutils.search-database\n      with:\n        db: tools.database\n        term: tools.query\n        retmax: tools.max_results\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/united-states-national-library-of-medicine/refs/heads/main/capabilities/biomedical-literature-research.yaml
tags:
- Biomedical Research
- PubMed
- Clinical Trials
- Genomics
- Healthcare
- NLM
- Federal Government
tools:
- description: Search PubMed for biomedical literature articles by topic, author, or keywords
  hints:
    idempotent: true
    readOnly: true
  name: search-pubmed
- description: Retrieve PubMed article abstracts for a list of PMIDs
  hints:
    idempotent: true
    readOnly: true
  name: get-pubmed-abstracts
- description: Get PubMed document summaries including title, authors, and journal for PMIDs
  hints:
    idempotent: true
    readOnly: true
  name: get-pubmed-summaries
- description: Search NCBI Gene database for gene records by symbol, name, or description
  hints:
    idempotent: true
    readOnly: true
  name: search-genes
- description: Search ClinicalTrials.gov for trials by condition, intervention, phase, or status
  hints:
    idempotent: true
    readOnly: true
  name: search-clinical-trials
- description: Retrieve complete protocol, eligibility, and results for a clinical trial by NCT ID
  hints:
    idempotent: true
    readOnly: true
  name: get-clinical-trial-details
- description: Search any NCBI Entrez database (nuccore, protein, snp, taxonomy, sra, etc.)
  hints:
    idempotent: true
    readOnly: true
  name: search-ncbi-database
---
