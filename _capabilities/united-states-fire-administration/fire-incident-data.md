---
api_specs:
- filename: openfema-fire-data-openapi.yml
  format: yaml
  label: openfema
  slug: openfema
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/united-states-fire-administration/refs/heads/main/openapi/openfema-fire-data-openapi.yml
categories: []
consumed_apis:
- openfema
description: Capability for fire incident data research and emergency management analysis using the OpenFEMA API. Combines fire disaster declarations, FEMA dataset discovery, and summary-level emergency data to support fire safety researchers, emergency managers, and public safety analysts.
layout: capability
name: USFA Fire Incident Data and Analysis
operations:
- description: List all available OpenFEMA datasets
  method: GET
  name: list-datasets
  path: /v1/datasets
- description: Get field descriptions for a specific dataset
  method: GET
  name: list-dataset-fields
  path: /v1/datasets/fields
- description: List FEMA fire disaster declarations with optional filters
  method: GET
  name: list-fire-disasters
  path: /v1/fire-disasters
- description: Get disaster declarations with authorized assistance programs
  method: GET
  name: list-disaster-summaries
  path: /v1/disasters/summaries
personas: []
provider_name: United States Fire Administration
provider_slug: united-states-fire-administration
search_terms:
- federal government
- get field-level data dictionary for a dataset
- disaster analysis
- fire safety
- list disaster summaries
- get dataset fields
- get data dictionary and field descriptions for a specific openfema dataset
- list dataset fields
- fema
- discover available openfema datasets and their metadata
- list openfema datasets
- public safety
- get disaster declarations with authorized assistance programs
- get field descriptions for a specific dataset
- list fema fire disaster declarations with optional filters
- list datasets
- get summarized disaster declarations showing which fema assistance programs were authorized
- get disaster program summaries
- list fire disasters
- list all available datasets on the openfema platform with descriptions and last update times
- get fire disaster declarations
- fire-type fema disaster declarations
- list all available openfema datasets
- usfa
- emergency management
- retrieve fema fire disaster declarations filtered by state, date, or other criteria
- summarized disaster declarations with program details
slug: fire-incident-data
source_filename: fire-incident-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"USFA Fire Incident Data and Analysis\"\n  description: >-\n    Capability for fire incident data research and emergency management\n    analysis using the OpenFEMA API. Combines fire disaster declarations,\n    FEMA dataset discovery, and summary-level emergency data to support\n    fire safety researchers, emergency managers, and public safety analysts.\n  tags:\n    - Fire Safety\n    - Emergency Management\n    - Disaster Analysis\n    - USFA\n    - FEMA\n    - Federal Government\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys: {}\n\ncapability:\n  consumes:\n    - import: openfema\n      location: ./shared/openfema-fire-data.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: usfa-fire-data-api\n      description: \"Unified REST API for USFA fire incident data and emergency management analysis.\"\n      resources:\n        - path: /v1/datasets\n          name:\
  \ datasets\n          description: \"Discover available OpenFEMA datasets and their metadata\"\n          operations:\n            - method: GET\n              name: list-datasets\n              description: \"List all available OpenFEMA datasets\"\n              call: \"openfema.list-datasets\"\n              with:\n                $top: \"rest.top\"\n                $select: \"rest.select\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/datasets/fields\n          name: dataset-fields\n          description: \"Get field-level data dictionary for a dataset\"\n          operations:\n            - method: GET\n              name: list-dataset-fields\n              description: \"Get field descriptions for a specific dataset\"\n              call: \"openfema.list-dataset-fields\"\n              with:\n                $filter: \"rest.datasetName\"\n              outputParameters:\n                - type: object\n \
  \                 mapping: \"$.\"\n\n        - path: /v1/fire-disasters\n          name: fire-disasters\n          description: \"Fire-type FEMA disaster declarations\"\n          operations:\n            - method: GET\n              name: list-fire-disasters\n              description: \"List FEMA fire disaster declarations with optional filters\"\n              call: \"openfema.get-disaster-declarations\"\n              with:\n                $filter: \"rest.filter\"\n                $top: \"rest.top\"\n                $skip: \"rest.skip\"\n                $orderby: \"rest.orderby\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/disasters/summaries\n          name: disaster-summaries\n          description: \"Summarized disaster declarations with program details\"\n          operations:\n            - method: GET\n              name: list-disaster-summaries\n              description: \"Get disaster declarations\
  \ with authorized assistance programs\"\n              call: \"openfema.get-disaster-summaries\"\n              with:\n                $filter: \"rest.filter\"\n                $top: \"rest.top\"\n                $skip: \"rest.skip\"\n                $orderby: \"rest.orderby\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: usfa-fire-data-mcp\n      transport: http\n      description: \"MCP server for AI-assisted fire safety research and emergency management analysis.\"\n      tools:\n        - name: list-openfema-datasets\n          description: \"List all available datasets on the OpenFEMA platform with descriptions and last update times\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"openfema.list-datasets\"\n          with:\n            $top: \"tools.top\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: get-dataset-fields\n          description: \"Get data dictionary and field descriptions for a specific OpenFEMA dataset\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"openfema.list-dataset-fields\"\n          with:\n            $filter: \"tools.dataset_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-fire-disaster-declarations\n          description: \"Retrieve FEMA fire disaster declarations filtered by state, date, or other criteria\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"openfema.get-disaster-declarations\"\n          with:\n            $filter: \"tools.filter\"\n            $top: \"tools.top\"\n            $orderby: \"tools.orderby\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-disaster-program-summaries\n          description:\
  \ \"Get summarized disaster declarations showing which FEMA assistance programs were authorized\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"openfema.get-disaster-summaries\"\n          with:\n            $filter: \"tools.filter\"\n            $top: \"tools.top\"\n            $count: \"tools.include_count\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/united-states-fire-administration/refs/heads/main/capabilities/fire-incident-data.yaml
tags:
- Fire Safety
- Emergency Management
- Disaster Analysis
- USFA
- FEMA
- Federal Government
tools:
- description: List all available datasets on the OpenFEMA platform with descriptions and last update times
  hints:
    idempotent: true
    readOnly: true
  name: list-openfema-datasets
- description: Get data dictionary and field descriptions for a specific OpenFEMA dataset
  hints:
    idempotent: true
    readOnly: true
  name: get-dataset-fields
- description: Retrieve FEMA fire disaster declarations filtered by state, date, or other criteria
  hints:
    idempotent: true
    readOnly: true
  name: get-fire-disaster-declarations
- description: Get summarized disaster declarations showing which FEMA assistance programs were authorized
  hints:
    idempotent: true
    readOnly: true
  name: get-disaster-program-summaries
---
