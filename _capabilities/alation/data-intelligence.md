---
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
- Data Analyst
- governance
- list alation datasources
- search the alation data catalog for tables, columns, data sources, glossary terms, and articles. returns ranked results with metadata.
- manage policies, glossary, and data quality
- AI Agent Developer
- list tables in an alation schema or data source.
- get alation lineage
- data catalog
- get data quality scores for a catalog object in alation.
- list all data sources configured in the alation catalog.
- metadata management
- list data governance policies in the alation catalog.
- get alation data quality
- unified data catalog search, lineage, governance, and discovery
- business glossary terms
- list columns for a table in the alation catalog.
- data intelligence
- Data Steward
- get alation context
- get data lineage
- discovers and explores data assets in the alation catalog. searches for tables and columns, reviews lineage, and accesses metadata to understand data context.
- data governance
- search the alation catalog
- list business glossary terms from the alation catalog.
- list glossary terms
- lineage
- get lineage for a catalog object
- manages data quality, governance policies, and business glossary in the alation catalog. assigns stewardship, creates glossary terms, and monitors data quality scores.
- data lineage
- get aggregated context from alation for ai-powered data discovery. returns structured catalog information for a natural language query.
- search and browse catalog assets
- data quality
- search alation catalog
- track data flows between systems and tables
- list alation glossary terms
- ai
- list all data sources
- list alation columns
- list datasources
- list alation policies
- business glossary
- get upstream and downstream data lineage for a catalog object in alation, showing how data flows between tables and systems.
- list data sources
- list alation tables
- builds ai applications using alation's catalog context and search apis. integrates aggregated context into llm workflows for data discovery.
- search catalog
- get lineage
- search
- search all alation catalog objects
- alation
slug: data-intelligence
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
