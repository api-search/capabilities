---
categories:
- compliance
consumed_apis:
- atlas-rest
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
- search atlas metadata entities by type and attributes.
- list glossaries
- open source
- engineers tracking data lineage and managing metadata for pipelines.
- get entity lineage.
- fulltext search
- list business glossaries for data governance.
- create metadata entities in atlas for data governance.
- data governance
- Data Engineer
- apache
- apache atlas
- metadata
- get data lineage graph for an atlas entity.
- Data Governance Team
- metadata discovery, lineage tracking, and governance workflow.
- hadoop
- create entities
- search entities
- get entity.
- compliance
- metadata management
- data lineage
- get lineage
- search entities.
- big data
- teams responsible for data quality, compliance, and metadata policies.
- get an atlas entity by guid.
- get entity
- full-text search across all atlas metadata.
slug: atlas-data-governance
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Apache Atlas Data Governance\n  description: Unified capability for Apache Atlas data governance workflows \n    including metadata discovery, lineage tracking, entity management, and \n    glossary management. Used by data governance teams and data engineers.\n  tags:\n  - Apache Atlas\n  - Data Governance\n  - Metadata Management\n  - Data Lineage\n  - Compliance\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    ATLAS_USERNAME: ATLAS_USERNAME\n    ATLAS_PASSWORD: ATLAS_PASSWORD\ncapability:\n  consumes:\n  - import: atlas-rest\n    location: ./shared/atlas-rest.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: atlas-governance-api\n    description: Unified REST API for Atlas data governance.\n    resources:\n    - path: /v1/entities/{guid}\n      name: entities\n      operations:\n      - method: GET\n        name: get-entity\n        description: Get entity.\n        call: atlas-rest.get-entity\n\
  \        with:\n          guid: rest.guid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      operations:\n      - method: GET\n        name: search-entities\n        description: Search entities.\n        call: atlas-rest.basic-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lineage/{guid}\n      name: lineage\n      operations:\n      - method: GET\n        name: get-lineage\n        description: Get entity lineage.\n        call: atlas-rest.get-lineage\n        with:\n          guid: rest.guid\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: atlas-governance-mcp\n    transport: http\n    description: MCP server for AI-assisted data governance with Apache Atlas.\n    tools:\n    - name: get-entity\n      description: Get an Atlas entity by GUID.\n      hints:\n        readOnly: true\n      call:\
  \ atlas-rest.get-entity\n      with:\n        guid: tools.guid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-entities\n      description: Search Atlas metadata entities by type and attributes.\n      hints:\n        readOnly: true\n      call: atlas-rest.basic-search\n      with:\n        typeName: tools.typeName\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fulltext-search\n      description: Full-text search across all Atlas metadata.\n      hints:\n        readOnly: true\n      call: atlas-rest.fulltext-search\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-lineage\n      description: Get data lineage graph for an Atlas entity.\n      hints:\n        readOnly: true\n      call: atlas-rest.get-lineage\n      with:\n        guid: tools.guid\n        direction: tools.direction\n      outputParameters:\n  \
  \    - type: object\n        mapping: $.\n    - name: create-entities\n      description: Create metadata entities in Atlas for data governance.\n      hints:\n        readOnly: false\n      call: atlas-rest.create-entities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-glossaries\n      description: List business glossaries for data governance.\n      hints:\n        readOnly: true\n      call: atlas-rest.list-glossaries\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
