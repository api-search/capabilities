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
- list all rdf datasets available on the fuseki server
- engineers who manage and query rdf datasets with sparql
- architects who design rdf schemas and knowledge graph structures
- list all datasets
- list datasets
- execute a sparql update to insert or delete rdf triples
- create a new rdf dataset on the fuseki server
- java
- apache jena
- rdf
- retrieve a named rdf graph from a dataset
- linked data
- owl
- execute sparql query
- execute a sparql select query to retrieve rdf data from a fuseki dataset
- ontology
- knowledge graph
- sparql query
- semantic web
- sparql
- Knowledge Graph Architect
- create dataset
- get graph
- Data Engineer
- sparql update
- create a dataset
- open source
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
