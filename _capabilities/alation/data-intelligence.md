---
categories:
- compliance
consumed_apis:
- alation-data-catalog
- alation-lineage
- alation-governance
- alation-search
description: Workflow capability for data intelligence operations combining catalog search, lineage tracking, governance, and metadata management in the Alation platform. Enables data stewards, analysts, and AI agents to discover trusted data assets, track data lineage, enforce governance policies, and maintain data quality.
layout: capability
name: Alation Data Intelligence
operations:
- description: Search all Alation catalog objects
  method: GET
  name: search-catalog
  path: /v1/search
- description: List all data sources
  method: GET
  name: list-datasources
  path: /v1/datasources
- description: Get lineage for a catalog object
  method: GET
  name: get-lineage
  path: /v1/lineage
- description: List glossary terms
  method: GET
  name: list-glossary-terms
  path: /v1/glossary
personas: []
provider_name: Alation
provider_slug: alation
search_terms:
- search the alation data catalog for tables, columns, data sources, glossary terms, and articles. returns ranked results with metadata.
- discovers and explores data assets in the alation catalog. searches for tables and columns, reviews lineage, and accesses metadata to understand data context.
- business glossary
- Data Steward
- AI Agent Developer
- get alation context
- track data flows between systems and tables
- list alation tables
- search catalog
- get alation data quality
- list alation policies
- list tables in an alation schema or data source.
- list all data sources
- list alation columns
- unified data catalog search, lineage, governance, and discovery
- manages data quality, governance policies, and business glossary in the alation catalog. assigns stewardship, creates glossary terms, and monitors data quality scores.
- governance
- lineage
- list alation glossary terms
- list data sources
- search all alation catalog objects
- get data quality scores for a catalog object in alation.
- search alation catalog
- search and browse catalog assets
- data lineage
- get lineage
- Data Analyst
- list all data sources configured in the alation catalog.
- data catalog
- search the alation catalog
- ai
- get lineage for a catalog object
- manage policies, glossary, and data quality
- data intelligence
- data quality
- metadata management
- alation
- builds ai applications using alation's catalog context and search apis. integrates aggregated context into llm workflows for data discovery.
- get alation lineage
- list datasources
- search
- list business glossary terms from the alation catalog.
- get aggregated context from alation for ai-powered data discovery. returns structured catalog information for a natural language query.
- get upstream and downstream data lineage for a catalog object in alation, showing how data flows between tables and systems.
- list glossary terms
- data governance
- business glossary terms
- list data governance policies in the alation catalog.
- list alation datasources
- get data lineage
- list columns for a table in the alation catalog.
slug: data-intelligence
source_filename: data-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Alation Data Intelligence\n  description: >-\n    Workflow capability for data intelligence operations combining catalog search,\n    lineage tracking, governance, and metadata management in the Alation platform.\n    Enables data stewards, analysts, and AI agents to discover trusted data assets,\n    track data lineage, enforce governance policies, and maintain data quality.\n  tags:\n    - Alation\n    - Data Catalog\n    - Data Intelligence\n    - Governance\n    - Lineage\n    - Data Quality\n    - Search\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ALATION_HOST: ALATION_HOST\n      ALATION_TOKEN: ALATION_TOKEN\n\ncapability:\n  consumes:\n    - import: alation-data-catalog\n      location: ./shared/data-catalog-api.yaml\n    - import: alation-lineage\n      location: ./shared/lineage-api.yaml\n    - import: alation-governance\n      location: ./shared/governance-api.yaml\n\
  \    - import: alation-search\n      location: ./shared/search-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: alation-data-intelligence-api\n      description: Unified REST API for Alation data intelligence workflows.\n      resources:\n        - path: /v1/search\n          name: search\n          description: Search the Alation catalog\n          operations:\n            - method: GET\n              name: search-catalog\n              description: Search all Alation catalog objects\n              call: \"alation-search.search-catalog\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/datasources\n          name: datasources\n          description: List data sources\n          operations:\n            - method: GET\n              name: list-datasources\n              description: List all data sources\n              call: \"alation-data-catalog.list-datasources\"\n              outputParameters:\n\
  \                - type: array\n                  mapping: \"$.\"\n        - path: /v1/lineage\n          name: lineage\n          description: Get data lineage\n          operations:\n            - method: GET\n              name: get-lineage\n              description: Get lineage for a catalog object\n              call: \"alation-lineage.get-lineage\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/glossary\n          name: glossary\n          description: Business glossary terms\n          operations:\n            - method: GET\n              name: list-glossary-terms\n              description: List glossary terms\n              call: \"alation-governance.list-glossary-terms\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: alation-data-intelligence-mcp\n      transport: http\n      description: MCP server\
  \ for AI-assisted Alation data intelligence workflows.\n      tools:\n        - name: search-alation-catalog\n          description: >-\n            Search the Alation data catalog for tables, columns, data sources,\n            glossary terms, and articles. Returns ranked results with metadata.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"alation-search.search-catalog\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-alation-context\n          description: >-\n            Get aggregated context from Alation for AI-powered data discovery.\n            Returns structured catalog information for a natural language query.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"alation-search.get-aggregated-context\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-alation-datasources\n\
  \          description: List all data sources configured in the Alation catalog.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"alation-data-catalog.list-datasources\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: list-alation-tables\n          description: List tables in an Alation schema or data source.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"alation-data-catalog.list-tables\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: list-alation-columns\n          description: List columns for a table in the Alation catalog.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"alation-data-catalog.list-columns\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-alation-lineage\n  \
  \        description: >-\n            Get upstream and downstream data lineage for a catalog object in Alation,\n            showing how data flows between tables and systems.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"alation-lineage.get-lineage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-alation-glossary-terms\n          description: List business glossary terms from the Alation catalog.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"alation-governance.list-glossary-terms\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-alation-data-quality\n          description: Get data quality scores for a catalog object in Alation.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"alation-governance.get-dq-scores\"\n         \
  \ outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: list-alation-policies\n          description: List data governance policies in the Alation catalog.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"alation-governance.list-policies\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/alation/refs/heads/main/capabilities/data-intelligence.yaml
tags:
- Alation
- Data Catalog
- Data Intelligence
- Governance
- Lineage
- Data Quality
- Search
tools:
- description: Search the Alation data catalog for tables, columns, data sources, glossary terms, and articles. Returns ranked results with metadata.
  hints:
    openWorld: false
    readOnly: true
  name: search-alation-catalog
- description: Get aggregated context from Alation for AI-powered data discovery. Returns structured catalog information for a natural language query.
  hints:
    openWorld: false
    readOnly: true
  name: get-alation-context
- description: List all data sources configured in the Alation catalog.
  hints:
    openWorld: false
    readOnly: true
  name: list-alation-datasources
- description: List tables in an Alation schema or data source.
  hints:
    openWorld: false
    readOnly: true
  name: list-alation-tables
- description: List columns for a table in the Alation catalog.
  hints:
    openWorld: false
    readOnly: true
  name: list-alation-columns
- description: Get upstream and downstream data lineage for a catalog object in Alation, showing how data flows between tables and systems.
  hints:
    openWorld: false
    readOnly: true
  name: get-alation-lineage
- description: List business glossary terms from the Alation catalog.
  hints:
    openWorld: false
    readOnly: true
  name: list-alation-glossary-terms
- description: Get data quality scores for a catalog object in Alation.
  hints:
    openWorld: false
    readOnly: true
  name: get-alation-data-quality
- description: List data governance policies in the Alation catalog.
  hints:
    openWorld: false
    readOnly: true
  name: list-alation-policies
---
