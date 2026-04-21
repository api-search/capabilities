---
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
- architects who design rdf schemas and knowledge graph structures
- sparql update
- apache jena
- list all rdf datasets available on the fuseki server
- sparql query
- execute sparql query
- engineers who manage and query rdf datasets with sparql
- rdf
- linked data
- knowledge graph
- Knowledge Graph Architect
- retrieve a named rdf graph from a dataset
- java
- list all datasets
- Data Engineer
- execute a sparql select query to retrieve rdf data from a fuseki dataset
- list datasets
- get graph
- semantic web
- sparql
- owl
- create a dataset
- create dataset
- ontology
- open source
- create a new rdf dataset on the fuseki server
slug: sparql-data-management
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
