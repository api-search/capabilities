---
categories: []
consumed_apis:
- jena-fuseki
description: Workflow capability for data engineers and knowledge graph architects to query, update, and manage RDF datasets using Apache Jena Fuseki.
layout: capability
name: Apache Jena SPARQL Data Management
operations:
- description: Execute SPARQL query
  method: GET
  name: sparql-query
  path: /v1/sparql
- description: List all datasets
  method: GET
  name: list-datasets
  path: /v1/datasets
- description: Create a dataset
  method: POST
  name: create-dataset
  path: /v1/datasets
personas: []
provider_name: Apache Jena
provider_slug: apache-jena
search_terms:
- execute a sparql update to insert or delete rdf triples
- sparql query
- sparql update
- java
- Data Engineer
- retrieve a named rdf graph from a dataset
- owl
- Knowledge Graph Architect
- knowledge graph
- rdf
- architects who design rdf schemas and knowledge graph structures
- open source
- create a dataset
- create dataset
- engineers who manage and query rdf datasets with sparql
- semantic web
- execute a sparql select query to retrieve rdf data from a fuseki dataset
- get graph
- apache jena
- list all datasets
- ontology
- sparql
- list datasets
- linked data
- execute sparql query
- list all rdf datasets available on the fuseki server
- create a new rdf dataset on the fuseki server
slug: sparql-data-management
source_filename: sparql-data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apache Jena SPARQL Data Management\"\n  description: \"Workflow capability for data engineers and knowledge graph architects to query, update, and manage RDF datasets using Apache Jena Fuseki.\"\n  tags:\n    - Apache Jena\n    - Knowledge Graph\n    - Linked Data\n    - RDF\n    - SPARQL\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      FUSEKI_PASSWORD: FUSEKI_PASSWORD\n\ncapability:\n  consumes:\n    - import: jena-fuseki\n      location: ./shared/fuseki-sparql-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: jena-sparql-management-api\n      description: \"Unified REST API for Apache Jena SPARQL data management.\"\n      resources:\n        - path: /v1/sparql\n          name: sparql\n          operations:\n            - method: GET\n              name: sparql-query\n              description: Execute SPARQL query\n              call: \"jena-fuseki.sparql-query-get\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/datasets\n          name: datasets\n          operations:\n            - method: GET\n              name: list-datasets\n              description: List all datasets\n              call: \"jena-fuseki.list-datasets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-dataset\n              description: Create a dataset\n              call: \"jena-fuseki.create-dataset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: jena-sparql-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SPARQL knowledge graph management.\"\n      tools:\n        - name: sparql-query\n          description: Execute a SPARQL SELECT query to retrieve\
  \ RDF data from a Fuseki dataset\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"jena-fuseki.sparql-query-get\"\n          with:\n            dataset: \"tools.dataset\"\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: sparql-update\n          description: Execute a SPARQL UPDATE to insert or delete RDF triples\n          hints:\n            readOnly: false\n          call: \"jena-fuseki.sparql-update\"\n          with:\n            dataset: \"tools.dataset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-datasets\n          description: List all RDF datasets available on the Fuseki server\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"jena-fuseki.list-datasets\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: create-dataset\n          description: Create a new RDF dataset on the Fuseki server\n          hints:\n            readOnly: false\n          call: \"jena-fuseki.create-dataset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-graph\n          description: Retrieve a named RDF graph from a dataset\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"jena-fuseki.get-graph\"\n          with:\n            dataset: \"tools.dataset\"\n            graph: \"tools.graph_uri\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-jena/refs/heads/main/capabilities/sparql-data-management.yaml
tags:
- Apache Jena
- Knowledge Graph
- Linked Data
- RDF
- SPARQL
tools:
- description: Execute a SPARQL SELECT query to retrieve RDF data from a Fuseki dataset
  hints:
    openWorld: true
    readOnly: true
  name: sparql-query
- description: Execute a SPARQL UPDATE to insert or delete RDF triples
  hints:
    readOnly: false
  name: sparql-update
- description: List all RDF datasets available on the Fuseki server
  hints:
    openWorld: true
    readOnly: true
  name: list-datasets
- description: Create a new RDF dataset on the Fuseki server
  hints:
    readOnly: false
  name: create-dataset
- description: Retrieve a named RDF graph from a dataset
  hints:
    openWorld: true
    readOnly: true
  name: get-graph
---
