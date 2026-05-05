---
categories: []
consumed_apis:
- wikibase-rest
description: Unified capability for reading and writing to the Wikidata knowledge graph. Combines Wikibase REST API operations for entity retrieval, statement management, and structured data writing. Intended for data engineers, knowledge graph analysts, and AI/ML pipelines that need programmatic access to Wikidata's 100M+ entities.
layout: capability
name: Wikidata Knowledge Graph Access
operations:
- description: Create a new Wikidata item
  method: POST
  name: create-item
  path: /v1/entities/items
- description: Get a Wikidata item by Q-ID
  method: GET
  name: get-item
  path: /v1/entities/items/{item_id}
- description: Get label for an item in a specific language
  method: GET
  name: get-item-label
  path: /v1/entities/items/{item_id}/labels/{language_code}
- description: Get all statements for an item
  method: GET
  name: get-item-statements
  path: /v1/entities/items/{item_id}/statements
- description: Add a statement to an item
  method: POST
  name: add-item-statement
  path: /v1/entities/items/{item_id}/statements
- description: Get a statement by ID
  method: GET
  name: get-statement
  path: /v1/statements/{statement_id}
- description: Delete a statement
  method: DELETE
  name: delete-statement
  path: /v1/statements/{statement_id}
- description: Get a property by P-ID
  method: GET
  name: get-property
  path: /v1/entities/properties/{property_id}
personas: []
provider_name: Wikidata
provider_slug: wikidata
search_terms:
- open data
- get all statements for an item
- delete a statement
- unified read/write access to wikidata knowledge graph entities and statements
- statements (claims) for an item
- add fact
- create a new wikidata item with labels, descriptions, aliases, and initial statements. requires oauth2 authentication.
- create item
- get entity
- structured, linked entity data representing real-world facts
- delete an incorrect or outdated statement from a wikidata item by statement id. requires oauth2 authentication.
- individual statement operations
- retrieve a wikidata entity (item or property) with all labels, descriptions, aliases, sitelinks, and statements by q-id or p-id.
- retrieve the label for a wikidata entity in a specific language by bcp 47 language code.
- Knowledge Graph Analyst
- get entity statements
- get a statement by id
- Data Engineer
- linked data
- remove fact
- create entity
- get statement
- get entity label
- sparql
- wikidata items (q-entities)
- add a new factual statement (claim) to a wikidata item. specify the property p-id and value. requires oauth2 authentication.
- get item label
- get label for an item in a specific language
- wikidata
- get item statements
- get property definition
- rdf-compatible representation for semantic web and ontology alignment
- engineer ingesting and enriching datasets with wikidata linked data facts
- cc0-licensed public domain data accessible without authentication for reads
- single wikidata item
- get a wikidata item by q-id
- semantic web
- retrieve a wikidata property definition including its datatype, labels, and descriptions. useful for understanding what a p-id represents.
- get a property by p-id
- delete statement
- retrieve structured factual claims (statements) for a wikidata entity, optionally filtered by property id (e.g. p31 for 'instance of').
- AI/ML Pipeline
- get item
- automated pipeline using wikidata as a factual grounding source for llms
- item labels by language
- knowledge graph
- wikipedia
- get property
- add a statement to an item
- create a new wikidata item
- add item statement
- wikidata properties (p-entities)
- analyst navigating entity relationships and property hierarchies in wikidata
slug: knowledge-graph-access
source_filename: knowledge-graph-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Wikidata Knowledge Graph Access\"\n  description: >-\n    Unified capability for reading and writing to the Wikidata knowledge graph.\n    Combines Wikibase REST API operations for entity retrieval, statement management,\n    and structured data writing. Intended for data engineers, knowledge graph analysts,\n    and AI/ML pipelines that need programmatic access to Wikidata's 100M+ entities.\n  tags:\n    - Wikidata\n    - Knowledge Graph\n    - Linked Data\n    - Semantic Web\n    - Open Data\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WIKIDATA_OAUTH_TOKEN: WIKIDATA_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: wikibase-rest\n      location: ./shared/wikibase-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: wikidata-knowledge-graph-api\n      description: \"Unified REST API for Wikidata knowledge graph access and editing.\"\n \
  \     resources:\n        - path: /v1/entities/items\n          name: items\n          description: \"Wikidata items (Q-entities)\"\n          operations:\n            - method: POST\n              name: create-item\n              description: \"Create a new Wikidata item\"\n              call: \"wikibase-rest.create-item\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/entities/items/{item_id}\n          name: item\n          description: \"Single Wikidata item\"\n          operations:\n            - method: GET\n              name: get-item\n              description: \"Get a Wikidata item by Q-ID\"\n              call: \"wikibase-rest.get-item\"\n              with:\n                item_id: \"rest.item_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/entities/items/{item_id}/labels/{language_code}\n          name: item-label\n  \
  \        description: \"Item labels by language\"\n          operations:\n            - method: GET\n              name: get-item-label\n              description: \"Get label for an item in a specific language\"\n              call: \"wikibase-rest.get-item-label\"\n              with:\n                item_id: \"rest.item_id\"\n                language_code: \"rest.language_code\"\n              outputParameters:\n                - type: string\n                  mapping: \"$.\"\n\n        - path: /v1/entities/items/{item_id}/statements\n          name: item-statements\n          description: \"Statements (claims) for an item\"\n          operations:\n            - method: GET\n              name: get-item-statements\n              description: \"Get all statements for an item\"\n              call: \"wikibase-rest.get-item-statements\"\n              with:\n                item_id: \"rest.item_id\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n            - method: POST\n              name: add-item-statement\n              description: \"Add a statement to an item\"\n              call: \"wikibase-rest.add-item-statement\"\n              with:\n                item_id: \"rest.item_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/statements/{statement_id}\n          name: statement\n          description: \"Individual statement operations\"\n          operations:\n            - method: GET\n              name: get-statement\n              description: \"Get a statement by ID\"\n              call: \"wikibase-rest.get-statement\"\n              with:\n                statement_id: \"rest.statement_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: DELETE\n              name: delete-statement\n              description: \"Delete a statement\"\n              call:\
  \ \"wikibase-rest.delete-statement\"\n              with:\n                statement_id: \"rest.statement_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/entities/properties/{property_id}\n          name: property\n          description: \"Wikidata properties (P-entities)\"\n          operations:\n            - method: GET\n              name: get-property\n              description: \"Get a property by P-ID\"\n              call: \"wikibase-rest.get-property\"\n              with:\n                property_id: \"rest.property_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: wikidata-knowledge-graph-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Wikidata knowledge graph access and enrichment.\"\n      tools:\n        - name: get-entity\n          description: \"Retrieve\
  \ a Wikidata entity (item or property) with all labels, descriptions, aliases, sitelinks, and statements by Q-ID or P-ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"wikibase-rest.get-item\"\n          with:\n            item_id: \"tools.entity_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-entity-statements\n          description: \"Retrieve structured factual claims (statements) for a Wikidata entity, optionally filtered by property ID (e.g. P31 for 'instance of').\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"wikibase-rest.get-item-statements\"\n          with:\n            item_id: \"tools.item_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-entity-label\n          description: \"Retrieve\
  \ the label for a Wikidata entity in a specific language by BCP 47 language code.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"wikibase-rest.get-item-label\"\n          with:\n            item_id: \"tools.item_id\"\n            language_code: \"tools.language_code\"\n          outputParameters:\n            - type: string\n              mapping: \"$.\"\n\n        - name: get-property-definition\n          description: \"Retrieve a Wikidata property definition including its datatype, labels, and descriptions. Useful for understanding what a P-ID represents.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"wikibase-rest.get-property\"\n          with:\n            property_id: \"tools.property_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-entity\n          description: \"Create a new Wikidata item with labels, descriptions,\
  \ aliases, and initial statements. Requires OAuth2 authentication.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"wikibase-rest.create-item\"\n          with:\n            labels: \"tools.labels\"\n            descriptions: \"tools.descriptions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: add-fact\n          description: \"Add a new factual statement (claim) to a Wikidata item. Specify the property P-ID and value. Requires OAuth2 authentication.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"wikibase-rest.add-item-statement\"\n          with:\n            item_id: \"tools.item_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: remove-fact\n          description: \"Delete an incorrect or outdated statement from a Wikidata item by statement ID. Requires OAuth2\
  \ authentication.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"wikibase-rest.delete-statement\"\n          with:\n            statement_id: \"tools.statement_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/wikidata/refs/heads/main/capabilities/knowledge-graph-access.yaml
tags:
- Wikidata
- Knowledge Graph
- Linked Data
- Semantic Web
- Open Data
tools:
- description: Retrieve a Wikidata entity (item or property) with all labels, descriptions, aliases, sitelinks, and statements by Q-ID or P-ID.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-entity
- description: Retrieve structured factual claims (statements) for a Wikidata entity, optionally filtered by property ID (e.g. P31 for 'instance of').
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-entity-statements
- description: Retrieve the label for a Wikidata entity in a specific language by BCP 47 language code.
  hints:
    idempotent: true
    readOnly: true
  name: get-entity-label
- description: Retrieve a Wikidata property definition including its datatype, labels, and descriptions. Useful for understanding what a P-ID represents.
  hints:
    idempotent: true
    readOnly: true
  name: get-property-definition
- description: Create a new Wikidata item with labels, descriptions, aliases, and initial statements. Requires OAuth2 authentication.
  hints:
    destructive: false
    readOnly: false
  name: create-entity
- description: Add a new factual statement (claim) to a Wikidata item. Specify the property P-ID and value. Requires OAuth2 authentication.
  hints:
    destructive: false
    readOnly: false
  name: add-fact
- description: Delete an incorrect or outdated statement from a Wikidata item by statement ID. Requires OAuth2 authentication.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-fact
---
