---
categories: []
consumed_apis: []
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
- deploy event schemas to registry environments
- analytics platform
- get data product
- deploy a snowplow event schema to a registry environment (validated, dev, or prod)
- list all snowplow event schemas (data structures) in the organization
- list all snowplow data products (tracking plans) with their event specifications
- data engineering
- manage snowplow event schemas
- get deployments
- create data product
- validate data structure
- validate schema
- data collection
- event tracking
- open source
- get deployment history for a snowplow event schema across validated, dev, and prod environments
- view deployment history for an event schema
- validate event schemas before deployment
- validate a snowplow json event schema before deploying to the registry
- deploy schema
- get details of a specific snowplow event schema by its sha-256 hash
- behavioral data
- deploy data structure
- list data structures
- create a new snowplow data product (tracking plan) for organizing event specifications
- get a specific event schema
- get details of a specific snowplow data product (tracking plan)
- schema management
- data governance
- snowplow
- get a specific tracking plan
- get data structure
- data pipeline
- manage tracking plans (data products)
- list data products
- get data structure deployments
slug: data-pipeline-governance
source_filename: data-pipeline-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Snowplow Data Pipeline Governance\n  description: Unified workflow capability for governing Snowplow behavioral data pipelines. Provides data engineers, analytics\n    engineers, and data product managers with programmatic control over the data structure lifecycle (schema authoring, validation,\n    deployment), data product (tracking plan) management, and event specification governance. Ensures data quality through\n    schema validation before production deployment.\n  tags:\n  - Analytics Platform\n  - Behavioral Data\n  - Data Engineering\n  - Data Governance\n  - Event Tracking\n  - Schema Management\n  - Snowplow\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SNOWPLOW_JWT_TOKEN: SNOWPLOW_JWT_TOKEN\n    SNOWPLOW_ORG_ID: SNOWPLOW_ORG_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: snowplow-console\n    baseUri: https://console.snowplowanalytics.com/api/msc/v1\n    description:\
  \ Snowplow Console API for behavioral data platform management\n    authentication:\n      type: bearer\n      token: '{{SNOWPLOW_JWT_TOKEN}}'\n    resources:\n    - name: data-structures\n      path: /organizations/{{SNOWPLOW_ORG_ID}}/data-structures/v1\n      description: List all data structures in the organization\n      operations:\n      - name: list-data-structures\n        method: GET\n        description: List Data Structures\n        inputParameters:\n        - name: vendor\n          in: query\n          type: string\n          required: false\n          description: Filter by schema vendor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-structure\n      path: /organizations/{{SNOWPLOW_ORG_ID}}/data-structures/v1/{dataStructureHash}\n      description: Get a specific data structure by hash\n      operations:\n      - name: get-data-structure\n        method: GET\n        description:\
  \ Get Data Structure\n        inputParameters:\n        - name: dataStructureHash\n          in: path\n          type: string\n          required: true\n          description: SHA-256 hash of the data structure\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: validate-data-structure\n      path: /organizations/{{SNOWPLOW_ORG_ID}}/data-structures/v1/validation-requests\n      description: Validate a JSON schema before deployment\n      operations:\n      - name: validate-data-structure\n        method: POST\n        description: Validate Data Structure\n        body:\n          type: json\n          data:\n            meta: '{{tools.meta}}'\n            data: '{{tools.schema}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deploy-data-structure\n      path: /organizations/{{SNOWPLOW_ORG_ID}}/data-structures/v1/deployment-requests\n\
  \      description: Deploy a data structure to a registry environment\n      operations:\n      - name: deploy-data-structure\n        method: POST\n        description: Deploy Data Structure\n        body:\n          type: json\n          data:\n            dataStructureHash: '{{tools.dataStructureHash}}'\n            version: '{{tools.version}}'\n            target: '{{tools.target}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-products\n      path: /organizations/{{SNOWPLOW_ORG_ID}}/data-products/v2\n      description: List and create data products (tracking plans)\n      operations:\n      - name: list-data-products\n        method: GET\n        description: List Data Products\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-data-product\n        method: POST\n        description: Create\
  \ Data Product\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-product\n      path: /organizations/{{SNOWPLOW_ORG_ID}}/data-products/v2/{dataProductId}\n      description: Get a specific data product\n      operations:\n      - name: get-data-product\n        method: GET\n        description: Get Data Product\n        inputParameters:\n        - name: dataProductId\n          in: path\n          type: string\n          required: true\n          description: Data product UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-structure-deployments\n      path: /organizations/{{SNOWPLOW_ORG_ID}}/data-structures/v1/{dataStructureHash}/deployments\n      description:\
  \ View deployment history for a data structure\n      operations:\n      - name: get-data-structure-deployments\n        method: GET\n        description: Get Data Structure Deployments\n        inputParameters:\n        - name: dataStructureHash\n          in: path\n          type: string\n          required: true\n          description: Data structure hash\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: snowplow-governance-api\n    description: Unified REST API for Snowplow data pipeline governance and schema management.\n    resources:\n    - path: /v1/data-structures\n      name: data-structures\n      description: Manage Snowplow event schemas\n      operations:\n      - method: GET\n        name: list-data-structures\n        description: List Data Structures\n        call: snowplow-console.list-data-structures\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n    - path: /v1/data-structures/{hash}\n      name: data-structure\n      description: Get a specific event schema\n      operations:\n      - method: GET\n        name: get-data-structure\n        description: Get Data Structure\n        call: snowplow-console.get-data-structure\n        with:\n          dataStructureHash: rest.hash\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-structures/{hash}/deployments\n      name: data-structure-deployments\n      description: View deployment history for an event schema\n      operations:\n      - method: GET\n        name: get-deployments\n        description: Get Data Structure Deployments\n        call: snowplow-console.get-data-structure-deployments\n        with:\n          dataStructureHash: rest.hash\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/schema-validations\n      name: schema-validations\n   \
  \   description: Validate event schemas before deployment\n      operations:\n      - method: POST\n        name: validate-schema\n        description: Validate Data Structure\n        call: snowplow-console.validate-data-structure\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/schema-deployments\n      name: schema-deployments\n      description: Deploy event schemas to registry environments\n      operations:\n      - method: POST\n        name: deploy-schema\n        description: Deploy Data Structure\n        call: snowplow-console.deploy-data-structure\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-products\n      name: data-products\n      description: Manage tracking plans (data products)\n      operations:\n      - method: GET\n        name: list-data-products\n        description: List Data Products\n        call: snowplow-console.list-data-products\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n      - method: POST\n        name: create-data-product\n        description: Create Data Product\n        call: snowplow-console.create-data-product\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-products/{id}\n      name: data-product\n      description: Get a specific tracking plan\n      operations:\n      - method: GET\n        name: get-data-product\n        description: Get Data Product\n        call: snowplow-console.get-data-product\n        with:\n          dataProductId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: snowplow-governance-mcp\n    transport: http\n    description: MCP server for AI-assisted Snowplow data pipeline governance and schema lifecycle management.\n    tools:\n    - name: list-data-structures\n      description: List all Snowplow event schemas (data structures) in the organization\n\
  \      hints:\n        readOnly: true\n        openWorld: false\n      call: snowplow-console.list-data-structures\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-data-structure\n      description: Get details of a specific Snowplow event schema by its SHA-256 hash\n      hints:\n        readOnly: true\n        openWorld: false\n      call: snowplow-console.get-data-structure\n      with:\n        dataStructureHash: tools.dataStructureHash\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-data-structure-deployments\n      description: Get deployment history for a Snowplow event schema across VALIDATED, DEV, and PROD environments\n      hints:\n        readOnly: true\n        openWorld: false\n      call: snowplow-console.get-data-structure-deployments\n      with:\n        dataStructureHash: tools.dataStructureHash\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validate-data-structure\n\
  \      description: Validate a Snowplow JSON event schema before deploying to the registry\n      hints:\n        readOnly: false\n        destructive: false\n      call: snowplow-console.validate-data-structure\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deploy-data-structure\n      description: Deploy a Snowplow event schema to a registry environment (VALIDATED, DEV, or PROD)\n      hints:\n        readOnly: false\n        destructive: false\n      call: snowplow-console.deploy-data-structure\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-data-products\n      description: List all Snowplow data products (tracking plans) with their event specifications\n      hints:\n        readOnly: true\n        openWorld: false\n      call: snowplow-console.list-data-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-data-product\n      description: Get details of a specific Snowplow\
  \ data product (tracking plan)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: snowplow-console.get-data-product\n      with:\n        dataProductId: tools.dataProductId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-data-product\n      description: Create a new Snowplow data product (tracking plan) for organizing event specifications\n      hints:\n        readOnly: false\n        destructive: false\n      call: snowplow-console.create-data-product\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
