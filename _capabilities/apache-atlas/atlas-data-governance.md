---
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
- apache
- engineers tracking data lineage and managing metadata for pipelines.
- big data
- apache atlas
- get entity lineage.
- get entity.
- metadata discovery, lineage tracking, and governance workflow.
- metadata
- hadoop
- metadata management
- get an atlas entity by guid.
- Data Governance Team
- full-text search across all atlas metadata.
- get entity
- list glossaries
- fulltext search
- teams responsible for data quality, compliance, and metadata policies.
- data governance
- create entities
- compliance
- Data Engineer
- list business glossaries for data governance.
- search entities
- create metadata entities in atlas for data governance.
- get lineage
- get data lineage graph for an atlas entity.
- search atlas metadata entities by type and attributes.
- data lineage
- search entities.
- open source
slug: atlas-data-governance
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
