---
categories:
- compliance
consumed_apis: []
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
- governance
- search catalog
- list all data sources configured in the alation catalog.
- data intelligence
- list alation columns
- business glossary
- ai
- Data Analyst
- builds ai applications using alation's catalog context and search apis. integrates aggregated context into llm workflows for data discovery.
- data quality
- search alation catalog
- list alation policies
- list alation tables
- metadata management
- get upstream and downstream data lineage for a catalog object in alation, showing how data flows between tables and systems.
- manages data quality, governance policies, and business glossary in the alation catalog. assigns stewardship, creates glossary terms, and monitors data quality scores.
- list glossary terms
- get alation context
- get data quality scores for a catalog object in alation.
- search all alation catalog objects
- business glossary terms
- get aggregated context from alation for ai-powered data discovery. returns structured catalog information for a natural language query.
- get alation data quality
- list datasources
- data catalog
- get alation lineage
- get lineage
- unified data catalog search, lineage, governance, and discovery
- track data flows between systems and tables
- get data lineage
- lineage
- search the alation catalog
- get lineage for a catalog object
- list alation datasources
- search and browse catalog assets
- manage policies, glossary, and data quality
- data lineage
- discovers and explores data assets in the alation catalog. searches for tables and columns, reviews lineage, and accesses metadata to understand data context.
- AI Agent Developer
- list columns for a table in the alation catalog.
- list alation glossary terms
- list business glossary terms from the alation catalog.
- data governance
- list data governance policies in the alation catalog.
- search the alation data catalog for tables, columns, data sources, glossary terms, and articles. returns ranked results with metadata.
- search
- alation
- list data sources
- list tables in an alation schema or data source.
- list all data sources
- Data Steward
slug: data-intelligence
source_filename: data-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Alation Data Intelligence\n  description: Workflow capability for data intelligence operations combining catalog search, lineage tracking, governance,\n    and metadata management in the Alation platform. Enables data stewards, analysts, and AI agents to discover trusted data\n    assets, track data lineage, enforce governance policies, and maintain data quality.\n  tags:\n  - Alation\n  - Data Catalog\n  - Data Intelligence\n  - Governance\n  - Lineage\n  - Data Quality\n  - Search\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ALATION_HOST: ALATION_HOST\n    ALATION_TOKEN: ALATION_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: alation-data-catalog\n    baseUri: https://{{env.ALATION_HOST}}/integration/v2\n    description: Alation Data Catalog REST API\n    auth:\n      type: bearer\n      token: '{{env.ALATION_TOKEN}}'\n    resources:\n    - name: datasources\n      path: /datasource/\n\
  \      description: Data source connections\n      operations:\n      - name: list-datasources\n        method: GET\n        description: List all data sources in the Alation catalog\n        outputParameters:\n        - name: datasources\n          type: array\n          value: $.\n      - name: get-datasource\n        method: GET\n        description: Get a specific data source by ID\n        inputParameters:\n        - name: id\n          type: integer\n          in: path\n        outputParameters:\n        - name: datasource\n          type: object\n          value: $.\n    - name: schemas\n      path: /schema/\n      description: Database schemas\n      operations:\n      - name: list-schemas\n        method: GET\n        description: List schemas for a data source\n        inputParameters:\n        - name: ds_id\n          type: integer\n          in: query\n        outputParameters:\n        - name: schemas\n          type: array\n          value: $.\n    - name: tables\n      path:\
  \ /table/\n      description: Database tables\n      operations:\n      - name: list-tables\n        method: GET\n        description: List tables for a schema or data source\n        inputParameters:\n        - name: schema_id\n          type: integer\n          in: query\n        outputParameters:\n        - name: tables\n          type: array\n          value: $.\n      - name: get-table\n        method: GET\n        description: Get a specific table by ID\n        inputParameters:\n        - name: id\n          type: integer\n          in: path\n        outputParameters:\n        - name: table\n          type: object\n          value: $.\n    - name: columns\n      path: /attribute/\n      description: Table columns\n      operations:\n      - name: list-columns\n        method: GET\n        description: List columns for a table\n        inputParameters:\n        - name: table_id\n          type: integer\n          in: query\n        outputParameters:\n        - name: columns\n   \
  \       type: array\n          value: $.\n    - name: custom-fields\n      path: /custom_field_value/\n      description: Custom field values for catalog objects\n      operations:\n      - name: get-custom-field-values\n        method: GET\n        description: Get custom field values for a catalog object\n        inputParameters:\n        - name: object_type\n          type: string\n          in: query\n        - name: object_id\n          type: integer\n          in: query\n        outputParameters:\n        - name: custom_fields\n          type: array\n          value: $.\n      - name: update-custom-field-values\n        method: PUT\n        description: Batch update custom field values\n        inputParameters:\n        - name: body\n          type: array\n          in: body\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: alation-lineage\n    baseUri: https://{{env.ALATION_HOST}}/api/v1\n    description:\
  \ Alation Lineage REST API\n    auth:\n      type: bearer\n      token: '{{env.ALATION_TOKEN}}'\n    resources:\n    - name: dataflows\n      path: /dataflow/\n      description: Dataflow lineage objects\n      operations:\n      - name: list-dataflows\n        method: GET\n        description: List all dataflow objects\n        outputParameters:\n        - name: dataflows\n          type: array\n          value: $.\n      - name: create-dataflow\n        method: POST\n        description: Create a new dataflow object\n        inputParameters:\n        - name: body\n          type: object\n          in: body\n        outputParameters:\n        - name: dataflow\n          type: object\n          value: $.\n      - name: get-dataflow\n        method: GET\n        description: Get a specific dataflow by ID\n        inputParameters:\n        - name: id\n          type: integer\n          in: path\n        outputParameters:\n        - name: dataflow\n          type: object\n          value:\
  \ $.\n      - name: delete-dataflow\n        method: DELETE\n        description: Delete a dataflow object\n        inputParameters:\n        - name: id\n          type: integer\n          in: path\n    - name: lineage\n      path: /lineage/\n      description: Lineage graph retrieval\n      operations:\n      - name: get-lineage\n        method: GET\n        description: Get upstream and downstream lineage for a catalog object\n        inputParameters:\n        - name: object_type\n          type: string\n          in: query\n        - name: object_id\n          type: integer\n          in: query\n        - name: direction\n          type: string\n          in: query\n        outputParameters:\n        - name: lineage_graph\n          type: object\n          value: $.\n  - type: http\n    namespace: alation-governance\n    baseUri: https://{{env.ALATION_HOST}}/integration/v2\n    description: Alation Governance REST API\n    auth:\n      type: bearer\n      token: '{{env.ALATION_TOKEN}}'\n\
  \    resources:\n    - name: glossary-terms\n      path: /glossary_term/\n      description: Business glossary terms\n      operations:\n      - name: list-glossary-terms\n        method: GET\n        description: List business glossary terms\n        outputParameters:\n        - name: terms\n          type: array\n          value: $.\n      - name: create-glossary-term\n        method: POST\n        description: Create a glossary term\n        inputParameters:\n        - name: body\n          type: object\n          in: body\n        outputParameters:\n        - name: term\n          type: object\n          value: $.\n      - name: get-glossary-term\n        method: GET\n        description: Get a glossary term by ID\n        inputParameters:\n        - name: id\n          type: integer\n          in: path\n        outputParameters:\n        - name: term\n          type: object\n          value: $.\n    - name: policies\n      path: /policy/\n      description: Data governance policies\n\
  \      operations:\n      - name: list-policies\n        method: GET\n        description: List governance policies\n        outputParameters:\n        - name: policies\n          type: array\n          value: $.\n    - name: data-quality-rules\n      path: /data_quality/rule/\n      description: Data quality rules\n      operations:\n      - name: list-dq-rules\n        method: GET\n        description: List data quality rules\n        outputParameters:\n        - name: rules\n          type: array\n          value: $.\n    - name: data-quality-scores\n      path: /data_quality/score/\n      description: Data quality scores\n      operations:\n      - name: get-dq-scores\n        method: GET\n        description: Get data quality scores for a catalog object\n        inputParameters:\n        - name: object_type\n          type: string\n          in: query\n        - name: object_id\n          type: integer\n          in: query\n        outputParameters:\n        - name: scores\n     \
  \     type: array\n          value: $.\n  - type: http\n    namespace: alation-search\n    baseUri: https://{{env.ALATION_HOST}}/integration/v2\n    description: Alation Search REST API\n    auth:\n      type: bearer\n      token: '{{env.ALATION_TOKEN}}'\n    resources:\n    - name: search\n      path: /search/\n      description: Full-text catalog search\n      operations:\n      - name: search-catalog\n        method: GET\n        description: Search all catalog objects\n        inputParameters:\n        - name: q\n          type: string\n          in: query\n        - name: type\n          type: string\n          in: query\n        - name: limit\n          type: integer\n          in: query\n        outputParameters:\n        - name: results\n          type: object\n          value: $.\n    - name: aggregated-context\n      path: /aggregated_context/\n      description: Aggregated catalog context for AI applications\n      operations:\n      - name: get-aggregated-context\n        method:\
  \ POST\n        description: Get aggregated catalog context for a natural language query\n        inputParameters:\n        - name: body\n          type: object\n          in: body\n        outputParameters:\n        - name: context\n          type: object\n          value: $.\n    - name: articles\n      path: /article/\n      description: Catalog articles and wiki pages\n      operations:\n      - name: list-articles\n        method: GET\n        description: List catalog articles\n        outputParameters:\n        - name: articles\n          type: array\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: alation-data-intelligence-api\n    description: Unified REST API for Alation data intelligence workflows.\n    resources:\n    - path: /v1/search\n      name: search\n      description: Search the Alation catalog\n      operations:\n      - method: GET\n        name: search-catalog\n        description: Search all Alation catalog objects\n        call:\
  \ alation-search.search-catalog\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/datasources\n      name: datasources\n      description: List data sources\n      operations:\n      - method: GET\n        name: list-datasources\n        description: List all data sources\n        call: alation-data-catalog.list-datasources\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/lineage\n      name: lineage\n      description: Get data lineage\n      operations:\n      - method: GET\n        name: get-lineage\n        description: Get lineage for a catalog object\n        call: alation-lineage.get-lineage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/glossary\n      name: glossary\n      description: Business glossary terms\n      operations:\n      - method: GET\n        name: list-glossary-terms\n        description: List glossary terms\n        call: alation-governance.list-glossary-terms\n\
  \        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: alation-data-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted Alation data intelligence workflows.\n    tools:\n    - name: search-alation-catalog\n      description: Search the Alation data catalog for tables, columns, data sources, glossary terms, and articles. Returns\n        ranked results with metadata.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: alation-search.search-catalog\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-alation-context\n      description: Get aggregated context from Alation for AI-powered data discovery. Returns structured catalog information\n        for a natural language query.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: alation-search.get-aggregated-context\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-alation-datasources\n      description: List all data sources configured in the Alation catalog.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: alation-data-catalog.list-datasources\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-alation-tables\n      description: List tables in an Alation schema or data source.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: alation-data-catalog.list-tables\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-alation-columns\n      description: List columns for a table in the Alation catalog.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: alation-data-catalog.list-columns\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-alation-lineage\n      description: Get upstream and downstream data lineage for a catalog object in Alation,\
  \ showing how data flows between\n        tables and systems.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: alation-lineage.get-lineage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-alation-glossary-terms\n      description: List business glossary terms from the Alation catalog.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: alation-governance.list-glossary-terms\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-alation-data-quality\n      description: Get data quality scores for a catalog object in Alation.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: alation-governance.get-dq-scores\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-alation-policies\n      description: List data governance policies in the Alation catalog.\n      hints:\n        readOnly: true\n        openWorld: false\n\
  \      call: alation-governance.list-policies\n      outputParameters:\n      - type: array\n        mapping: $.\n"
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
