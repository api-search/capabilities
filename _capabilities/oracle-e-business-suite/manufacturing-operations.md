---
categories:
- procurement-supply-chain
consumed_apis:
- oracle-manufacturing
- oracle-supply-chain
description: Manufacturing execution combining BOMs, routings, discrete jobs, WIP operations, and inventory management. Used by production managers and shop floor supervisors for manufacturing lifecycle.
layout: capability
name: Oracle EBS Manufacturing Operations
operations:
- description: List BOMs.
  method: GET
  name: get-bills-of-material
  path: /v1/bills-of-material
- description: List discrete jobs.
  method: GET
  name: get-discrete-jobs
  path: /v1/discrete-jobs
- description: List inventory items.
  method: GET
  name: get-inventory-items
  path: /v1/inventory-items
- description: List on-hand quantities.
  method: GET
  name: get-onhand-quantities
  path: /v1/onhand-quantities
personas: []
provider_name: Oracle E-Business Suite
provider_slug: oracle-e-business-suite
search_terms:
- mfg get bills of material
- list inventory items.
- list discrete jobs.
- complete an assembly.
- on-hand quantity management.
- retrieve wip operations.
- supply chain
- mfg get wip operations
- retrieve inventory items.
- mfg get routings
- get inventory items
- enterprise
- create a discrete job.
- inv get sales orders
- mfg issue material
- production
- issue material to a job.
- list boms.
- retrieve on-hand quantities.
- get bills of material
- erp
- business applications
- get discrete jobs
- retrieve bills of material.
- inv get onhand quantities
- inv get deliveries
- oracle
- get discrete job by id.
- manufacturing
- retrieve discrete jobs.
- mfg get discrete job by id
- inventory item management.
- retrieve routings.
- mfg get discrete jobs
- mfg get bill of material by id
- bom management.
- mfg create discrete job
- retrieve sales orders.
- get onhand quantities
- retrieve deliveries.
- get bom by id.
- inv get inventory items
- e-business suite
- mfg complete assembly
- list on-hand quantities.
- discrete job management.
slug: manufacturing-operations
source_filename: manufacturing-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Oracle EBS Manufacturing Operations\"\n  description: \"Manufacturing execution combining BOMs, routings, discrete jobs, WIP operations, and inventory management. Used by production managers and shop floor supervisors for manufacturing lifecycle.\"\n  tags:\n    - Oracle\n    - Manufacturing\n    - Supply Chain\n    - Production\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ORACLE_EBS_TOKEN: ORACLE_EBS_TOKEN\n\ncapability:\n  consumes:\n    - import: oracle-manufacturing\n      location: ./shared/manufacturing.yaml\n    - import: oracle-supply-chain\n      location: ./shared/supply-chain.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: manufacturing-operations-api\n      description: \"Unified REST API for Oracle EBS manufacturing operations.\"\n      resources:\n        - path: /v1/bills-of-material\n          name: bills-of-material\n          description:\
  \ \"BOM management.\"\n          operations:\n            - method: GET\n              name: get-bills-of-material\n              description: \"List BOMs.\"\n              call: \"oracle-manufacturing.get-bills-of-material\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/discrete-jobs\n          name: discrete-jobs\n          description: \"Discrete job management.\"\n          operations:\n            - method: GET\n              name: get-discrete-jobs\n              description: \"List discrete jobs.\"\n              call: \"oracle-manufacturing.get-discrete-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/inventory-items\n          name: inventory-items\n          description: \"Inventory item management.\"\n          operations:\n            - method: GET\n              name: get-inventory-items\n              description: \"List\
  \ inventory items.\"\n              call: \"oracle-supply-chain.get-inventory-items\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/onhand-quantities\n          name: onhand-quantities\n          description: \"On-hand quantity management.\"\n          operations:\n            - method: GET\n              name: get-onhand-quantities\n              description: \"List on-hand quantities.\"\n              call: \"oracle-supply-chain.get-onhand-quantities\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: manufacturing-operations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Oracle EBS manufacturing operations.\"\n      tools:\n        - name: mfg-get-bills-of-material\n          description: \"Retrieve bills of material.\"\n          hints:\n            readOnly: true\n          \
  \  openWorld: true\n          call: \"oracle-manufacturing.get-bills-of-material\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: mfg-get-bill-of-material-by-id\n          description: \"Get BOM by ID.\"\n          hints:\n            readOnly: true\n          call: \"oracle-manufacturing.get-bill-of-material-by-id\"\n          with:\n            billSequenceId: \"tools.bill_sequence_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: mfg-get-routings\n          description: \"Retrieve routings.\"\n          hints:\n            readOnly: true\n          call: \"oracle-manufacturing.get-routings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: mfg-get-discrete-jobs\n          description: \"Retrieve discrete jobs.\"\n          hints:\n            readOnly: true\n          call: \"oracle-manufacturing.get-discrete-jobs\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: mfg-create-discrete-job\n          description: \"Create a discrete job.\"\n          hints:\n            readOnly: false\n          call: \"oracle-manufacturing.create-discrete-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: mfg-get-discrete-job-by-id\n          description: \"Get discrete job by ID.\"\n          hints:\n            readOnly: true\n          call: \"oracle-manufacturing.get-discrete-job-by-id\"\n          with:\n            wipEntityId: \"tools.wip_entity_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: mfg-get-wip-operations\n          description: \"Retrieve WIP operations.\"\n          hints:\n            readOnly: true\n          call: \"oracle-manufacturing.get-wip-operations\"\n          outputParameters:\n            - type: object\n \
  \             mapping: \"$.\"\n        - name: mfg-complete-assembly\n          description: \"Complete an assembly.\"\n          hints:\n            readOnly: false\n          call: \"oracle-manufacturing.complete-assembly\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: mfg-issue-material\n          description: \"Issue material to a job.\"\n          hints:\n            readOnly: false\n          call: \"oracle-manufacturing.issue-material\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: inv-get-inventory-items\n          description: \"Retrieve inventory items.\"\n          hints:\n            readOnly: true\n          call: \"oracle-supply-chain.get-inventory-items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: inv-get-onhand-quantities\n          description: \"Retrieve on-hand quantities.\"\n          hints:\n\
  \            readOnly: true\n          call: \"oracle-supply-chain.get-onhand-quantities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: inv-get-sales-orders\n          description: \"Retrieve sales orders.\"\n          hints:\n            readOnly: true\n          call: \"oracle-supply-chain.get-sales-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: inv-get-deliveries\n          description: \"Retrieve deliveries.\"\n          hints:\n            readOnly: true\n          call: \"oracle-supply-chain.get-deliveries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-e-business-suite/refs/heads/main/capabilities/manufacturing-operations.yaml
tags:
- Oracle
- Manufacturing
- Supply Chain
- Production
tools:
- description: Retrieve bills of material.
  hints:
    openWorld: true
    readOnly: true
  name: mfg-get-bills-of-material
- description: Get BOM by ID.
  hints:
    readOnly: true
  name: mfg-get-bill-of-material-by-id
- description: Retrieve routings.
  hints:
    readOnly: true
  name: mfg-get-routings
- description: Retrieve discrete jobs.
  hints:
    readOnly: true
  name: mfg-get-discrete-jobs
- description: Create a discrete job.
  hints:
    readOnly: false
  name: mfg-create-discrete-job
- description: Get discrete job by ID.
  hints:
    readOnly: true
  name: mfg-get-discrete-job-by-id
- description: Retrieve WIP operations.
  hints:
    readOnly: true
  name: mfg-get-wip-operations
- description: Complete an assembly.
  hints:
    readOnly: false
  name: mfg-complete-assembly
- description: Issue material to a job.
  hints:
    readOnly: false
  name: mfg-issue-material
- description: Retrieve inventory items.
  hints:
    readOnly: true
  name: inv-get-inventory-items
- description: Retrieve on-hand quantities.
  hints:
    readOnly: true
  name: inv-get-onhand-quantities
- description: Retrieve sales orders.
  hints:
    readOnly: true
  name: inv-get-sales-orders
- description: Retrieve deliveries.
  hints:
    readOnly: true
  name: inv-get-deliveries
---
