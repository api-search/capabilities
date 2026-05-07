---
categories: []
consumed_apis: []
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
- statements (claims) for an item
- add a new factual statement (claim) to a wikidata item. specify the property p-id and value. requires oauth2 authentication.
- add a statement to an item
- wikidata items (q-entities)
- rdf-compatible representation for semantic web and ontology alignment
- get a statement by id
- wikidata properties (p-entities)
- delete an incorrect or outdated statement from a wikidata item by statement id. requires oauth2 authentication.
- add item statement
- get label for an item in a specific language
- get statement
- individual statement operations
- structured, linked entity data representing real-world facts
- create a new wikidata item
- wikidata
- get property definition
- retrieve the label for a wikidata entity in a specific language by bcp 47 language code.
- unified read/write access to wikidata knowledge graph entities and statements
- get entity label
- create item
- retrieve a wikidata entity (item or property) with all labels, descriptions, aliases, sitelinks, and statements by q-id or p-id.
- Knowledge Graph Analyst
- retrieve a wikidata property definition including its datatype, labels, and descriptions. useful for understanding what a p-id represents.
- item labels by language
- delete statement
- cc0-licensed public domain data accessible without authentication for reads
- get entity statements
- add fact
- create a new wikidata item with labels, descriptions, aliases, and initial statements. requires oauth2 authentication.
- remove fact
- sparql
- retrieve structured factual claims (statements) for a wikidata entity, optionally filtered by property id (e.g. p31 for 'instance of').
- get item label
- semantic web
- knowledge graph
- get entity
- automated pipeline using wikidata as a factual grounding source for llms
- get a property by p-id
- wikipedia
- AI/ML Pipeline
- Data Engineer
- linked data
- engineer ingesting and enriching datasets with wikidata linked data facts
- get a wikidata item by q-id
- get property
- get item
- get all statements for an item
- create entity
- get item statements
- open data
- analyst navigating entity relationships and property hierarchies in wikidata
- delete a statement
- single wikidata item
slug: knowledge-graph-access
source_filename: knowledge-graph-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Wikidata Knowledge Graph Access\n  description: Unified capability for reading and writing to the Wikidata knowledge graph. Combines Wikibase REST API operations\n    for entity retrieval, statement management, and structured data writing. Intended for data engineers, knowledge graph\n    analysts, and AI/ML pipelines that need programmatic access to Wikidata's 100M+ entities.\n  tags:\n  - Wikidata\n  - Knowledge Graph\n  - Linked Data\n  - Semantic Web\n  - Open Data\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WIKIDATA_OAUTH_TOKEN: WIKIDATA_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: wikibase-rest\n    baseUri: https://www.wikidata.org/w/rest.php/wikibase/v0\n    description: Wikibase REST API for reading and writing Wikidata entities.\n    authentication:\n      type: bearer\n      token: '{{WIKIDATA_OAUTH_TOKEN}}'\n    resources:\n    - name: items\n      path:\
  \ /entities/items\n      description: Wikidata item (Q-entity) operations\n      operations:\n      - name: create-item\n        method: POST\n        description: Create a new Wikidata item\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            labels: '{{tools.labels}}'\n            descriptions: '{{tools.descriptions}}'\n            statements: '{{tools.statements}}'\n    - name: item\n      path: /entities/items/{item_id}\n      description: Single Wikidata item operations\n      operations:\n      - name: get-item\n        method: GET\n        description: Get a Wikidata item by ID\n        inputParameters:\n        - name: item_id\n          in: path\n          type: string\n          required: true\n          description: Wikidata item ID (e.g. Q42)\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n      - name: patch-item\n        method: PATCH\n        description: Update a Wikidata item via JSON patch\n        inputParameters:\n        - name: item_id\n          in: path\n          type: string\n          required: true\n          description: Wikidata item ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            patch: '{{tools.patch}}'\n            comment: '{{tools.comment}}'\n    - name: item-labels\n      path: /entities/items/{item_id}/labels/{language_code}\n      description: Item label operations\n      operations:\n      - name: get-item-label\n        method: GET\n        description: Get a label for an item in a specific language\n        inputParameters:\n        - name: item_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Wikidata item ID\n        - name: language_code\n          in: path\n          type: string\n          required: true\n          description: BCP 47 language code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n      - name: set-item-label\n        method: PUT\n        description: Set a label for an item in a specific language\n        inputParameters:\n        - name: item_id\n          in: path\n          type: string\n          required: true\n          description: Wikidata item ID\n        - name: language_code\n          in: path\n          type: string\n          required: true\n          description: BCP 47 language code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            label: '{{tools.label}}'\n            comment: '{{tools.comment}}'\n    - name: item-statements\n\
  \      path: /entities/items/{item_id}/statements\n      description: Item statement (claim) operations\n      operations:\n      - name: get-item-statements\n        method: GET\n        description: Get all statements for a Wikidata item\n        inputParameters:\n        - name: item_id\n          in: path\n          type: string\n          required: true\n          description: Wikidata item ID\n        - name: property\n          in: query\n          type: string\n          required: false\n          description: Filter by property ID (e.g. P31)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-item-statement\n        method: POST\n        description: Add a new statement to a Wikidata item\n        inputParameters:\n        - name: item_id\n          in: path\n          type: string\n          required: true\n          description: Wikidata item ID\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            property: '{{tools.property}}'\n            value: '{{tools.value}}'\n    - name: statements\n      path: /statements/{statement_id}\n      description: Individual statement operations\n      operations:\n      - name: get-statement\n        method: GET\n        description: Get a single statement by ID\n        inputParameters:\n        - name: statement_id\n          in: path\n          type: string\n          required: true\n          description: Statement ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-statement\n        method: DELETE\n        description: Delete a statement from an item\n        inputParameters:\n        - name: statement_id\n          in: path\n          type: string\n          required: true\n        \
  \  description: Statement ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: properties\n      path: /entities/properties/{property_id}\n      description: Wikidata property operations\n      operations:\n      - name: get-property\n        method: GET\n        description: Get a Wikidata property by ID\n        inputParameters:\n        - name: property_id\n          in: path\n          type: string\n          required: true\n          description: Wikidata property ID (e.g. P31)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: wikidata-knowledge-graph-api\n    description: Unified REST API for Wikidata knowledge graph access and editing.\n    resources:\n    - path: /v1/entities/items\n      name: items\n      description: Wikidata items (Q-entities)\n     \
  \ operations:\n      - method: POST\n        name: create-item\n        description: Create a new Wikidata item\n        call: wikibase-rest.create-item\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/items/{item_id}\n      name: item\n      description: Single Wikidata item\n      operations:\n      - method: GET\n        name: get-item\n        description: Get a Wikidata item by Q-ID\n        call: wikibase-rest.get-item\n        with:\n          item_id: rest.item_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/items/{item_id}/labels/{language_code}\n      name: item-label\n      description: Item labels by language\n      operations:\n      - method: GET\n        name: get-item-label\n        description: Get label for an item in a specific language\n        call: wikibase-rest.get-item-label\n        with:\n          item_id: rest.item_id\n          language_code: rest.language_code\n\
  \        outputParameters:\n        - type: string\n          mapping: $.\n    - path: /v1/entities/items/{item_id}/statements\n      name: item-statements\n      description: Statements (claims) for an item\n      operations:\n      - method: GET\n        name: get-item-statements\n        description: Get all statements for an item\n        call: wikibase-rest.get-item-statements\n        with:\n          item_id: rest.item_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-item-statement\n        description: Add a statement to an item\n        call: wikibase-rest.add-item-statement\n        with:\n          item_id: rest.item_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/statements/{statement_id}\n      name: statement\n      description: Individual statement operations\n      operations:\n      - method: GET\n        name: get-statement\n        description: Get a statement\
  \ by ID\n        call: wikibase-rest.get-statement\n        with:\n          statement_id: rest.statement_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-statement\n        description: Delete a statement\n        call: wikibase-rest.delete-statement\n        with:\n          statement_id: rest.statement_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/properties/{property_id}\n      name: property\n      description: Wikidata properties (P-entities)\n      operations:\n      - method: GET\n        name: get-property\n        description: Get a property by P-ID\n        call: wikibase-rest.get-property\n        with:\n          property_id: rest.property_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: wikidata-knowledge-graph-mcp\n    transport: http\n    description: MCP server for AI-assisted\
  \ Wikidata knowledge graph access and enrichment.\n    tools:\n    - name: get-entity\n      description: Retrieve a Wikidata entity (item or property) with all labels, descriptions, aliases, sitelinks, and statements\n        by Q-ID or P-ID.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: wikibase-rest.get-item\n      with:\n        item_id: tools.entity_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-entity-statements\n      description: Retrieve structured factual claims (statements) for a Wikidata entity, optionally filtered by property\n        ID (e.g. P31 for 'instance of').\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: wikibase-rest.get-item-statements\n      with:\n        item_id: tools.item_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-entity-label\n      description: Retrieve the label\
  \ for a Wikidata entity in a specific language by BCP 47 language code.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: wikibase-rest.get-item-label\n      with:\n        item_id: tools.item_id\n        language_code: tools.language_code\n      outputParameters:\n      - type: string\n        mapping: $.\n    - name: get-property-definition\n      description: Retrieve a Wikidata property definition including its datatype, labels, and descriptions. Useful for understanding\n        what a P-ID represents.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: wikibase-rest.get-property\n      with:\n        property_id: tools.property_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-entity\n      description: Create a new Wikidata item with labels, descriptions, aliases, and initial statements. Requires OAuth2\n        authentication.\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n      call: wikibase-rest.create-item\n      with:\n        labels: tools.labels\n        descriptions: tools.descriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-fact\n      description: Add a new factual statement (claim) to a Wikidata item. Specify the property P-ID and value. Requires OAuth2\n        authentication.\n      hints:\n        readOnly: false\n        destructive: false\n      call: wikibase-rest.add-item-statement\n      with:\n        item_id: tools.item_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-fact\n      description: Delete an incorrect or outdated statement from a Wikidata item by statement ID. Requires OAuth2 authentication.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: wikibase-rest.delete-statement\n      with:\n        statement_id: tools.statement_id\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n"
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
