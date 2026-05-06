---
categories:
- compliance
consumed_apis: []
description: Unified capability for Apache Atlas data governance workflows including metadata discovery, lineage tracking, entity management, and glossary management. Used by data governance teams and data engineers.
layout: capability
name: Apache Atlas Data Governance
operations:
- description: Get entity.
  method: GET
  name: get-entity
  path: /v1/entities/{guid}
- description: Search entities.
  method: GET
  name: search-entities
  path: /v1/search
- description: Get entity lineage.
  method: GET
  name: get-lineage
  path: /v1/lineage/{guid}
personas: []
provider_name: Apache Atlas
provider_slug: apache-atlas
search_terms:
- create metadata entities in atlas for data governance.
- get an atlas entity by guid.
- apache atlas
- search entities.
- full-text search across all atlas metadata.
- big data
- list business glossaries for data governance.
- search entities
- metadata discovery, lineage tracking, and governance workflow.
- Data Engineer
- apache
- compliance
- metadata management
- data governance
- open source
- get entity.
- teams responsible for data quality, compliance, and metadata policies.
- hadoop
- get lineage
- list glossaries
- create entities
- data lineage
- get data lineage graph for an atlas entity.
- get entity
- fulltext search
- get entity lineage.
- search atlas metadata entities by type and attributes.
- metadata
- engineers tracking data lineage and managing metadata for pipelines.
- Data Governance Team
slug: atlas-data-governance
source_filename: atlas-data-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Atlas Data Governance\n  description: Unified capability for Apache Atlas data governance workflows including metadata discovery, lineage tracking,\n    entity management, and glossary management. Used by data governance teams and data engineers.\n  tags:\n  - Apache Atlas\n  - Data Governance\n  - Metadata Management\n  - Data Lineage\n  - Compliance\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ATLAS_USERNAME: ATLAS_USERNAME\n    ATLAS_PASSWORD: ATLAS_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: atlas-rest\n    baseUri: http://localhost:21000/api/atlas\n    description: Apache Atlas REST API.\n    authentication:\n      type: basic\n      username: '{{ATLAS_USERNAME}}'\n      password: '{{ATLAS_PASSWORD}}'\n    resources:\n    - name: entities\n      path: /v2/entity\n      description: Manage metadata entities.\n      operations:\n      - name: get-entity\n  \
  \      method: GET\n        description: Get entity by GUID.\n        inputParameters:\n        - name: guid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-entities\n        method: POST\n        description: Create or update entities in bulk.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-entity\n        method: DELETE\n        description: Delete entity by GUID.\n        inputParameters:\n        - name: guid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /v2/search\n      description: Search and discover metadata.\n\
  \      operations:\n      - name: basic-search\n        method: GET\n        description: Search entities by type and attributes.\n        inputParameters:\n        - name: typeName\n          in: query\n          type: string\n          required: false\n        - name: query\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fulltext-search\n        method: GET\n        description: Full-text search across all entities.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lineage\n      path: /v2/lineage\n      description: Retrieve entity lineage.\n      operations:\n      - name: get-lineage\n        method: GET\n     \
  \   description: Get lineage for an entity.\n        inputParameters:\n        - name: guid\n          in: path\n          type: string\n          required: true\n        - name: direction\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: glossary\n      path: /v2/glossary\n      description: Manage business glossary.\n      operations:\n      - name: list-glossaries\n        method: GET\n        description: List all glossaries.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-glossary\n        method: POST\n        description: Create a glossary.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \  exposes:\n  - type: rest\n    port: 8080\n    namespace: atlas-governance-api\n    description: Unified REST API for Atlas data governance.\n    resources:\n    - path: /v1/entities/{guid}\n      name: entities\n      operations:\n      - method: GET\n        name: get-entity\n        description: Get entity.\n        call: atlas-rest.get-entity\n        with:\n          guid: rest.guid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      operations:\n      - method: GET\n        name: search-entities\n        description: Search entities.\n        call: atlas-rest.basic-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lineage/{guid}\n      name: lineage\n      operations:\n      - method: GET\n        name: get-lineage\n        description: Get entity lineage.\n        call: atlas-rest.get-lineage\n        with:\n          guid: rest.guid\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: atlas-governance-mcp\n    transport: http\n    description: MCP server for AI-assisted data governance with Apache Atlas.\n    tools:\n    - name: get-entity\n      description: Get an Atlas entity by GUID.\n      hints:\n        readOnly: true\n      call: atlas-rest.get-entity\n      with:\n        guid: tools.guid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-entities\n      description: Search Atlas metadata entities by type and attributes.\n      hints:\n        readOnly: true\n      call: atlas-rest.basic-search\n      with:\n        typeName: tools.typeName\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fulltext-search\n      description: Full-text search across all Atlas metadata.\n      hints:\n        readOnly: true\n      call: atlas-rest.fulltext-search\n      with:\n        query:\
  \ tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-lineage\n      description: Get data lineage graph for an Atlas entity.\n      hints:\n        readOnly: true\n      call: atlas-rest.get-lineage\n      with:\n        guid: tools.guid\n        direction: tools.direction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-entities\n      description: Create metadata entities in Atlas for data governance.\n      hints:\n        readOnly: false\n      call: atlas-rest.create-entities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-glossaries\n      description: List business glossaries for data governance.\n      hints:\n        readOnly: true\n      call: atlas-rest.list-glossaries\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-atlas/refs/heads/main/capabilities/atlas-data-governance.yaml
tags:
- Apache Atlas
- Data Governance
- Metadata Management
- Data Lineage
- Compliance
tools:
- description: Get an Atlas entity by GUID.
  hints:
    readOnly: true
  name: get-entity
- description: Search Atlas metadata entities by type and attributes.
  hints:
    readOnly: true
  name: search-entities
- description: Full-text search across all Atlas metadata.
  hints:
    readOnly: true
  name: fulltext-search
- description: Get data lineage graph for an Atlas entity.
  hints:
    readOnly: true
  name: get-lineage
- description: Create metadata entities in Atlas for data governance.
  hints:
    readOnly: false
  name: create-entities
- description: List business glossaries for data governance.
  hints:
    readOnly: true
  name: list-glossaries
---
