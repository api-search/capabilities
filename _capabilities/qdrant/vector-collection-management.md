---
categories:
- vector-search
- runtime
consumed_apis:
- qdrant-rest
description: Manage Qdrant collections that back enterprise RAG and MCP retrieval workloads — list collections, get collection info, search and upsert points, delete by filter, and snapshot for backup. Built for a developer environment where AI tooling indexes evidence of API change pulled from GitLab, Jira, Confluence, Slack, and Google Docs into a vector store the writer can query.
layout: capability
name: Qdrant Vector Collection Management
operations:
- description: List all collections in the Qdrant instance
  method: GET
  name: list-collections
  path: /collections
- description: Get information about a specific collection including config and point count
  method: GET
  name: get-collection-info
  path: /collections/{collection_name}
- description: Search for nearest-neighbor points in a collection by vector
  method: POST
  name: search-points
  path: /collections/{collection_name}/points/search
- description: Upsert points into a collection with vectors and payload
  method: PUT
  name: upsert-points
  path: /collections/{collection_name}/points
- description: Delete points from a collection by filter
  method: POST
  name: delete-points
  path: /collections/{collection_name}/points/delete
- description: Create a snapshot of a collection for backup
  method: POST
  name: create-snapshot
  path: /collections/{collection_name}/snapshots
personas:
- Platform Engineer
- API Architect
provider_name: Qdrant
provider_slug: qdrant
search_terms:
- list qdrant collections
- get collection info
- search points by vector
- upsert points
- delete points by filter
- create snapshot
- vector store backup
- rag retrieval workload
- mcp vector backend
- enterprise rag inventory
- ai tooling collection management
- api change evidence index
- platform engineer vector ops
- nearest neighbor search
- collection config inspection
- point count audit
- snapshot for backup
- qdrant collection lifecycle
- custom qdrant image runtime
- semantic search over evidence
slug: vector-collection-management
tags:
- Qdrant
- Vector Search
- RAG
- MCP
- Collections
tools:
- description: List all collections in the Qdrant instance to inventory the vector backends powering RAG
  hints:
    openWorld: false
    readOnly: true
  name: list-collections
- description: Get information about a specific collection including config, vector size, and point count
  hints:
    openWorld: false
    readOnly: true
  name: get-collection-info
- description: Search for nearest-neighbor points in a collection by vector to retrieve evidence of API change
  hints:
    openWorld: false
    readOnly: true
  name: search-points
- description: Upsert points into a collection with vectors and payload to index new evidence
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: upsert-points
- description: Delete points from a collection by filter to prune stale evidence
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-points
- description: Create a snapshot of a collection for backup before a destructive reindex
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-snapshot
---
