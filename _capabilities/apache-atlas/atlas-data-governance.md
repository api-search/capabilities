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
- get entity
- get entity.
- get an atlas entity by guid.
- data governance
- list business glossaries for data governance.
- compliance
- get data lineage graph for an atlas entity.
- search entities
- create metadata entities in atlas for data governance.
- search atlas metadata entities by type and attributes.
- apache
- teams responsible for data quality, compliance, and metadata policies.
- create entities
- open source
- engineers tracking data lineage and managing metadata for pipelines.
- full-text search across all atlas metadata.
- list glossaries
- metadata management
- get lineage
- metadata discovery, lineage tracking, and governance workflow.
- Data Engineer
- data lineage
- metadata
- big data
- get entity lineage.
- hadoop
- fulltext search
- search entities.
- Data Governance Team
- apache atlas
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
