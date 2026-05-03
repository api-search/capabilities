---
api_specs:
- filename: ncbi-e-utilities-openapi.yml
  format: yaml
  label: eutils
  slug: eutils
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/united-states-national-library-of-medicine/refs/heads/main/openapi/ncbi-e-utilities-openapi.yml
- filename: nlm-clinicaltrials-openapi.yml
  format: yaml
  label: clinicaltrials
  slug: clinicaltrials
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/united-states-national-library-of-medicine/refs/heads/main/openapi/nlm-clinicaltrials-openapi.yml
categories: []
consumed_apis:
- eutils
- clinicaltrials
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
- search ncbi database
- fetch full pubmed article records by pmid
- nlm
- retrieve a specific clinical trial
- get pubmed articles
- get trial
- search trials
- federal government
- get pubmed summaries
- genomics
- search pubmed for articles by query, author, or topic
- search clinicaltrials.gov for clinical trials
- get complete clinical trial record by nct id
- literature
- healthcare
- search any ncbi entrez database (nuccore, protein, snp, taxonomy, sra, etc.)
- pubmed
- search clinical trials by condition, intervention, or status
- get pubmed document summaries including title, authors, and journal for pmids
- search ncbi gene database
- retrieve pubmed article records
- search genes
- biomedical research
- search ncbi gene database for gene records
- search ncbi gene database for gene records by symbol, name, or description
- retrieve pubmed article abstracts for a list of pmids
- get pubmed abstracts
- search clinical trials
- search pubmed
- search clinicaltrials.gov for trials by condition, intervention, phase, or status
- clinical trials
- search pubmed biomedical literature database
- search pubmed for biomedical literature articles by topic, author, or keywords
- retrieve complete protocol, eligibility, and results for a clinical trial by nct id
- get clinical trial details
slug: biomedical-literature-research
source_filename: biomedical-literature-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"NLM Biomedical Literature and Clinical Research\"\n  description: >-\n    Unified capability for biomedical literature research and clinical trial\n    discovery workflows combining NCBI E-Utilities (PubMed, Entrez databases)\n    with ClinicalTrials.gov. Used by researchers, clinicians, bioinformaticians,\n    and healthcare professionals to search literature, find clinical trials,\n    retrieve gene data, and explore biomedical databases.\n  tags:\n    - Biomedical Research\n    - PubMed\n    - Clinical Trials\n    - Genomics\n    - Healthcare\n    - NLM\n    - Federal Government\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      NCBI_API_KEY: NCBI_API_KEY\n\ncapability:\n  consumes:\n    - import: eutils\n      location: ./shared/ncbi-e-utilities.yaml\n    - import: clinicaltrials\n      location: ./shared/nlm-clinicaltrials.yaml\n\n  exposes:\n    - type: rest\n      port:\
  \ 8080\n      namespace: nlm-research-api\n      description: \"Unified REST API for NLM biomedical literature and clinical research workflows.\"\n      resources:\n        - path: /v1/pubmed/search\n          name: pubmed-search\n          description: \"Search PubMed biomedical literature database\"\n          operations:\n            - method: GET\n              name: search-pubmed\n              description: \"Search PubMed for articles by query, author, or topic\"\n              call: \"eutils.search-database\"\n              with:\n                db: pubmed\n                term: \"rest.query\"\n                retmax: \"rest.limit\"\n                sort: \"rest.sort\"\n                mindate: \"rest.mindate\"\n                maxdate: \"rest.maxdate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pubmed/articles/{pmids}\n          name: pubmed-articles\n          description: \"Retrieve PubMed article\
  \ records\"\n          operations:\n            - method: GET\n              name: get-pubmed-articles\n              description: \"Fetch full PubMed article records by PMID\"\n              call: \"eutils.fetch-records\"\n              with:\n                db: pubmed\n                id: \"rest.pmids\"\n                rettype: abstract\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/gene/search\n          name: gene-search\n          description: \"Search NCBI Gene database\"\n          operations:\n            - method: GET\n              name: search-genes\n              description: \"Search NCBI Gene database for gene records\"\n              call: \"eutils.search-database\"\n              with:\n                db: gene\n                term: \"rest.query\"\n                retmax: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n   \
  \     - path: /v1/trials/search\n          name: trial-search\n          description: \"Search ClinicalTrials.gov for clinical trials\"\n          operations:\n            - method: GET\n              name: search-trials\n              description: \"Search clinical trials by condition, intervention, or status\"\n              call: \"clinicaltrials.search-studies\"\n              with:\n                query.cond: \"rest.condition\"\n                query.intr: \"rest.intervention\"\n                filter.overallStatus: \"rest.status\"\n                filter.phase: \"rest.phase\"\n                pageSize: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/trials/{nctId}\n          name: trial-detail\n          description: \"Retrieve a specific clinical trial\"\n          operations:\n            - method: GET\n              name: get-trial\n              description: \"Get complete clinical trial\
  \ record by NCT ID\"\n              call: \"clinicaltrials.get-study\"\n              with:\n                nctId: \"rest.nctId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: nlm-research-mcp\n      transport: http\n      description: \"MCP server for AI-assisted biomedical literature search and clinical research.\"\n      tools:\n        - name: search-pubmed\n          description: \"Search PubMed for biomedical literature articles by topic, author, or keywords\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"eutils.search-database\"\n          with:\n            db: pubmed\n            term: \"tools.query\"\n            retmax: \"tools.max_results\"\n            sort: \"tools.sort\"\n            mindate: \"tools.start_date\"\n            maxdate: \"tools.end_date\"\n          outputParameters:\n            - type: object\n   \
  \           mapping: \"$.\"\n\n        - name: get-pubmed-abstracts\n          description: \"Retrieve PubMed article abstracts for a list of PMIDs\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"eutils.fetch-records\"\n          with:\n            db: pubmed\n            id: \"tools.pmids\"\n            rettype: abstract\n            retmode: text\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-pubmed-summaries\n          description: \"Get PubMed document summaries including title, authors, and journal for PMIDs\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"eutils.get-summaries\"\n          with:\n            db: pubmed\n            id: \"tools.pmids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-genes\n          description: \"Search NCBI Gene database for\
  \ gene records by symbol, name, or description\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"eutils.search-database\"\n          with:\n            db: gene\n            term: \"tools.query\"\n            retmax: \"tools.max_results\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-clinical-trials\n          description: \"Search ClinicalTrials.gov for trials by condition, intervention, phase, or status\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"clinicaltrials.search-studies\"\n          with:\n            query.cond: \"tools.condition\"\n            query.intr: \"tools.intervention\"\n            query.spons: \"tools.sponsor\"\n            filter.overallStatus: \"tools.status\"\n            filter.phase: \"tools.phase\"\n            pageSize: \"tools.page_size\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: get-clinical-trial-details\n          description: \"Retrieve complete protocol, eligibility, and results for a clinical trial by NCT ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"clinicaltrials.get-study\"\n          with:\n            nctId: \"tools.nct_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-ncbi-database\n          description: \"Search any NCBI Entrez database (nuccore, protein, snp, taxonomy, sra, etc.)\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"eutils.search-database\"\n          with:\n            db: \"tools.database\"\n            term: \"tools.query\"\n            retmax: \"tools.max_results\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
