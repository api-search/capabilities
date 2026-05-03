---
categories: []
consumed_apis:
- snowplow-console
description: Unified workflow capability for governing Snowplow behavioral data pipelines. Provides data engineers, analytics engineers, and data product managers with programmatic control over the data structure lifecycle (schema authoring, validation, deployment), data product (tracking plan) management, and event specification governance. Ensures data quality through schema validation before production deployment.
layout: capability
name: Snowplow Data Pipeline Governance
operations:
- description: List Data Structures
  method: GET
  name: list-data-structures
  path: /v1/data-structures
- description: Get Data Structure
  method: GET
  name: get-data-structure
  path: /v1/data-structures/{hash}
- description: Get Data Structure Deployments
  method: GET
  name: get-deployments
  path: /v1/data-structures/{hash}/deployments
- description: Validate Data Structure
  method: POST
  name: validate-schema
  path: /v1/schema-validations
- description: Deploy Data Structure
  method: POST
  name: deploy-schema
  path: /v1/schema-deployments
- description: List Data Products
  method: GET
  name: list-data-products
  path: /v1/data-products
- description: Create Data Product
  method: POST
  name: create-data-product
  path: /v1/data-products
- description: Get Data Product
  method: GET
  name: get-data-product
  path: /v1/data-products/{id}
personas: []
provider_name: Snowplow
provider_slug: snowplow
search_terms:
- data pipeline
- get details of a specific snowplow data product (tracking plan)
- create data product
- get deployment history for a snowplow event schema across validated, dev, and prod environments
- get deployments
- open source
- analytics platform
- deploy a snowplow event schema to a registry environment (validated, dev, or prod)
- get a specific event schema
- deploy schema
- behavioral data
- data engineering
- data collection
- manage snowplow event schemas
- get data product
- validate schema
- list all snowplow event schemas (data structures) in the organization
- manage tracking plans (data products)
- deploy event schemas to registry environments
- event tracking
- get a specific tracking plan
- schema management
- deploy data structure
- validate event schemas before deployment
- get data structure
- snowplow
- validate data structure
- data governance
- create a new snowplow data product (tracking plan) for organizing event specifications
- get details of a specific snowplow event schema by its sha-256 hash
- view deployment history for an event schema
- list data structures
- list data products
- list all snowplow data products (tracking plans) with their event specifications
- validate a snowplow json event schema before deploying to the registry
- get data structure deployments
slug: data-pipeline-governance
source_filename: data-pipeline-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Snowplow Data Pipeline Governance\"\n  description: >-\n    Unified workflow capability for governing Snowplow behavioral data pipelines.\n    Provides data engineers, analytics engineers, and data product managers with\n    programmatic control over the data structure lifecycle (schema authoring,\n    validation, deployment), data product (tracking plan) management, and event\n    specification governance. Ensures data quality through schema validation\n    before production deployment.\n  tags:\n    - Analytics Platform\n    - Behavioral Data\n    - Data Engineering\n    - Data Governance\n    - Event Tracking\n    - Schema Management\n    - Snowplow\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SNOWPLOW_JWT_TOKEN: SNOWPLOW_JWT_TOKEN\n      SNOWPLOW_ORG_ID: SNOWPLOW_ORG_ID\n\ncapability:\n  consumes:\n    - import: snowplow-console\n      location: ./shared/console-api.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: snowplow-governance-api\n      description: \"Unified REST API for Snowplow data pipeline governance and schema management.\"\n      resources:\n        - path: /v1/data-structures\n          name: data-structures\n          description: \"Manage Snowplow event schemas\"\n          operations:\n            - method: GET\n              name: list-data-structures\n              description: \"List Data Structures\"\n              call: \"snowplow-console.list-data-structures\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/data-structures/{hash}\n          name: data-structure\n          description: \"Get a specific event schema\"\n          operations:\n            - method: GET\n              name: get-data-structure\n              description: \"Get Data Structure\"\n              call: \"snowplow-console.get-data-structure\"\n              with:\n\
  \                dataStructureHash: \"rest.hash\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/data-structures/{hash}/deployments\n          name: data-structure-deployments\n          description: \"View deployment history for an event schema\"\n          operations:\n            - method: GET\n              name: get-deployments\n              description: \"Get Data Structure Deployments\"\n              call: \"snowplow-console.get-data-structure-deployments\"\n              with:\n                dataStructureHash: \"rest.hash\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/schema-validations\n          name: schema-validations\n          description: \"Validate event schemas before deployment\"\n          operations:\n            - method: POST\n              name: validate-schema\n              description: \"Validate Data Structure\"\
  \n              call: \"snowplow-console.validate-data-structure\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/schema-deployments\n          name: schema-deployments\n          description: \"Deploy event schemas to registry environments\"\n          operations:\n            - method: POST\n              name: deploy-schema\n              description: \"Deploy Data Structure\"\n              call: \"snowplow-console.deploy-data-structure\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/data-products\n          name: data-products\n          description: \"Manage tracking plans (data products)\"\n          operations:\n            - method: GET\n              name: list-data-products\n              description: \"List Data Products\"\n              call: \"snowplow-console.list-data-products\"\n              outputParameters:\n      \
  \          - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-data-product\n              description: \"Create Data Product\"\n              call: \"snowplow-console.create-data-product\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/data-products/{id}\n          name: data-product\n          description: \"Get a specific tracking plan\"\n          operations:\n            - method: GET\n              name: get-data-product\n              description: \"Get Data Product\"\n              call: \"snowplow-console.get-data-product\"\n              with:\n                dataProductId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: snowplow-governance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Snowplow data pipeline\
  \ governance and schema lifecycle management.\"\n      tools:\n        - name: list-data-structures\n          description: \"List all Snowplow event schemas (data structures) in the organization\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"snowplow-console.list-data-structures\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-data-structure\n          description: \"Get details of a specific Snowplow event schema by its SHA-256 hash\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"snowplow-console.get-data-structure\"\n          with:\n            dataStructureHash: \"tools.dataStructureHash\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-data-structure-deployments\n          description: \"Get deployment history for a Snowplow event schema across VALIDATED, DEV,\
  \ and PROD environments\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"snowplow-console.get-data-structure-deployments\"\n          with:\n            dataStructureHash: \"tools.dataStructureHash\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: validate-data-structure\n          description: \"Validate a Snowplow JSON event schema before deploying to the registry\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"snowplow-console.validate-data-structure\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: deploy-data-structure\n          description: \"Deploy a Snowplow event schema to a registry environment (VALIDATED, DEV, or PROD)\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"snowplow-console.deploy-data-structure\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-data-products\n          description: \"List all Snowplow data products (tracking plans) with their event specifications\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"snowplow-console.list-data-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-data-product\n          description: \"Get details of a specific Snowplow data product (tracking plan)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"snowplow-console.get-data-product\"\n          with:\n            dataProductId: \"tools.dataProductId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-data-product\n          description: \"Create a new Snowplow data product (tracking plan) for organizing\
  \ event specifications\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"snowplow-console.create-data-product\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snowplow/refs/heads/main/capabilities/data-pipeline-governance.yaml
tags:
- Analytics Platform
- Behavioral Data
- Data Engineering
- Data Governance
- Event Tracking
- Schema Management
- Snowplow
tools:
- description: List all Snowplow event schemas (data structures) in the organization
  hints:
    openWorld: false
    readOnly: true
  name: list-data-structures
- description: Get details of a specific Snowplow event schema by its SHA-256 hash
  hints:
    openWorld: false
    readOnly: true
  name: get-data-structure
- description: Get deployment history for a Snowplow event schema across VALIDATED, DEV, and PROD environments
  hints:
    openWorld: false
    readOnly: true
  name: get-data-structure-deployments
- description: Validate a Snowplow JSON event schema before deploying to the registry
  hints:
    destructive: false
    readOnly: false
  name: validate-data-structure
- description: Deploy a Snowplow event schema to a registry environment (VALIDATED, DEV, or PROD)
  hints:
    destructive: false
    readOnly: false
  name: deploy-data-structure
- description: List all Snowplow data products (tracking plans) with their event specifications
  hints:
    openWorld: false
    readOnly: true
  name: list-data-products
- description: Get details of a specific Snowplow data product (tracking plan)
  hints:
    openWorld: false
    readOnly: true
  name: get-data-product
- description: Create a new Snowplow data product (tracking plan) for organizing event specifications
  hints:
    destructive: false
    readOnly: false
  name: create-data-product
---
