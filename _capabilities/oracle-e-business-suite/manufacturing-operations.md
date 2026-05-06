---
categories:
- procurement-supply-chain
consumed_apis: []
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
- issue material to a job.
- inv get inventory items
- manufacturing
- mfg create discrete job
- get inventory items
- retrieve routings.
- retrieve discrete jobs.
- retrieve on-hand quantities.
- list discrete jobs.
- bom management.
- list on-hand quantities.
- get bom by id.
- mfg complete assembly
- list inventory items.
- retrieve bills of material.
- get discrete job by id.
- mfg get discrete job by id
- enterprise
- mfg get discrete jobs
- get bills of material
- mfg get wip operations
- discrete job management.
- erp
- retrieve deliveries.
- complete an assembly.
- supply chain
- production
- oracle
- retrieve wip operations.
- business applications
- on-hand quantity management.
- mfg issue material
- mfg get routings
- get discrete jobs
- inv get sales orders
- inv get deliveries
- mfg get bills of material
- mfg get bill of material by id
- create a discrete job.
- inventory item management.
- list boms.
- inv get onhand quantities
- retrieve inventory items.
- retrieve sales orders.
- get onhand quantities
- e-business suite
slug: manufacturing-operations
source_filename: manufacturing-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle EBS Manufacturing Operations\n  description: Manufacturing execution combining BOMs, routings, discrete jobs, WIP operations, and inventory management.\n    Used by production managers and shop floor supervisors for manufacturing lifecycle.\n  tags:\n  - Oracle\n  - Manufacturing\n  - Supply Chain\n  - Production\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ORACLE_EBS_TOKEN: ORACLE_EBS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: oracle-manufacturing\n    baseUri: https://{instance}.oracle.com/webservices/rest\n    description: Oracle EBS Manufacturing API for managing production operations.\n    authentication:\n      type: bearer\n      token: '{{ORACLE_EBS_TOKEN}}'\n    resources:\n    - name: bills-of-material\n      path: /bom/bills\n      description: Bills of Material.\n      operations:\n      - name: get-bills-of-material\n        method: GET\n        description:\
  \ Retrieve bills of material.\n        inputParameters:\n        - name: organizationId\n          in: query\n          type: integer\n          required: false\n          description: Organization identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bill-of-material\n      path: /bom/bills/{billSequenceId}\n      description: Specific bill of material.\n      operations:\n      - name: get-bill-of-material-by-id\n        method: GET\n        description: Get bill of material by ID.\n        inputParameters:\n        - name: billSequenceId\n          in: path\n          type: integer\n          required: true\n          description: Bill sequence identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routings\n      path: /bom/routings\n      description: Manufacturing routings.\n      operations:\n\
  \      - name: get-routings\n        method: GET\n        description: Retrieve routings.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: discrete-jobs\n      path: /wip/discrete-jobs\n      description: Discrete manufacturing jobs.\n      operations:\n      - name: get-discrete-jobs\n        method: GET\n        description: Retrieve discrete jobs.\n        inputParameters:\n        - name: organizationId\n          in: query\n          type: integer\n          required: false\n          description: Organization identifier.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Job status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-discrete-job\n        method: POST\n        description: Create a discrete job.\n        body:\n\
  \          type: json\n          data:\n            organizationId: '{{tools.organization_id}}'\n            assemblyItemId: '{{tools.assembly_item_id}}'\n            startQuantity: '{{tools.start_quantity}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: discrete-job\n      path: /wip/discrete-jobs/{wipEntityId}\n      description: Specific discrete job.\n      operations:\n      - name: get-discrete-job-by-id\n        method: GET\n        description: Get discrete job by ID.\n        inputParameters:\n        - name: wipEntityId\n          in: path\n          type: integer\n          required: true\n          description: WIP entity identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wip-operations\n      path: /wip/operations\n      description: WIP operations.\n      operations:\n      - name:\
  \ get-wip-operations\n        method: GET\n        description: Retrieve WIP operations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assembly-completion\n      path: /wip/completions\n      description: Assembly completions.\n      operations:\n      - name: complete-assembly\n        method: POST\n        description: Complete an assembly.\n        body:\n          type: json\n          data:\n            wipEntityId: '{{tools.wip_entity_id}}'\n            quantity: '{{tools.quantity}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: material-issues\n      path: /wip/material-issues\n      description: Material issue transactions.\n      operations:\n      - name: issue-material\n        method: POST\n        description: Issue material to a job.\n        body:\n          type: json\n          data:\n\
  \            wipEntityId: '{{tools.wip_entity_id}}'\n            inventoryItemId: '{{tools.inventory_item_id}}'\n            quantity: '{{tools.quantity}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: oracle-supply-chain\n    baseUri: https://{instance}.oracle.com/webservices/rest\n    description: Oracle EBS Supply Chain API for managing procurement and inventory.\n    authentication:\n      type: bearer\n      token: '{{ORACLE_EBS_TOKEN}}'\n    resources:\n    - name: purchase-orders\n      path: /po/purchase-orders\n      description: Purchase order management.\n      operations:\n      - name: get-purchase-orders\n        method: GET\n        description: Retrieve purchase orders.\n        inputParameters:\n        - name: vendorId\n          in: query\n          type: integer\n          required: false\n          description: Vendor identifier.\n        - name: status\n\
  \          in: query\n          type: string\n          required: false\n          description: PO status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-purchase-order\n        method: POST\n        description: Create a purchase order.\n        body:\n          type: json\n          data:\n            vendorId: '{{tools.vendor_id}}'\n            lines: '{{tools.lines}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: purchase-order\n      path: /po/purchase-orders/{poHeaderId}\n      description: Specific purchase order.\n      operations:\n      - name: get-purchase-order-by-id\n        method: GET\n        description: Get purchase order by ID.\n        inputParameters:\n        - name: poHeaderId\n          in: path\n          type: integer\n          required: true\n          description:\
  \ PO header identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-purchase-order\n        method: PUT\n        description: Update a purchase order.\n        inputParameters:\n        - name: poHeaderId\n          in: path\n          type: integer\n          required: true\n          description: PO header identifier.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: requisitions\n      path: /po/requisitions\n      description: Purchase requisitions.\n      operations:\n      - name: get-requisitions\n        method: GET\n        description: Retrieve requisitions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ suppliers\n      path: /po/suppliers\n      description: Supplier management.\n      operations:\n      - name: get-suppliers\n        method: GET\n        description: Retrieve suppliers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sales-orders\n      path: /oe/sales-orders\n      description: Sales order management.\n      operations:\n      - name: get-sales-orders\n        method: GET\n        description: Retrieve sales orders.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-sales-order\n        method: POST\n        description: Create a sales order.\n        body:\n          type: json\n          data:\n            customerId: '{{tools.customer_id}}'\n            lines: '{{tools.lines}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: inventory-items\n      path: /inv/items\n      description: Inventory items.\n      operations:\n      - name: get-inventory-items\n        method: GET\n        description: Retrieve inventory items.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: onhand-quantities\n      path: /inv/onhand\n      description: On-hand inventory quantities.\n      operations:\n      - name: get-onhand-quantities\n        method: GET\n        description: Retrieve on-hand quantities.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deliveries\n      path: /wsh/deliveries\n      description: Shipping deliveries.\n      operations:\n      - name: get-deliveries\n        method: GET\n        description: Retrieve deliveries.\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: manufacturing-operations-api\n    description: Unified REST API for Oracle EBS manufacturing operations.\n    resources:\n    - path: /v1/bills-of-material\n      name: bills-of-material\n      description: BOM management.\n      operations:\n      - method: GET\n        name: get-bills-of-material\n        description: List BOMs.\n        call: oracle-manufacturing.get-bills-of-material\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/discrete-jobs\n      name: discrete-jobs\n      description: Discrete job management.\n      operations:\n      - method: GET\n        name: get-discrete-jobs\n        description: List discrete jobs.\n        call: oracle-manufacturing.get-discrete-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/inventory-items\n      name: inventory-items\n\
  \      description: Inventory item management.\n      operations:\n      - method: GET\n        name: get-inventory-items\n        description: List inventory items.\n        call: oracle-supply-chain.get-inventory-items\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/onhand-quantities\n      name: onhand-quantities\n      description: On-hand quantity management.\n      operations:\n      - method: GET\n        name: get-onhand-quantities\n        description: List on-hand quantities.\n        call: oracle-supply-chain.get-onhand-quantities\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: manufacturing-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted Oracle EBS manufacturing operations.\n    tools:\n    - name: mfg-get-bills-of-material\n      description: Retrieve bills of material.\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: oracle-manufacturing.get-bills-of-material\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mfg-get-bill-of-material-by-id\n      description: Get BOM by ID.\n      hints:\n        readOnly: true\n      call: oracle-manufacturing.get-bill-of-material-by-id\n      with:\n        billSequenceId: tools.bill_sequence_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mfg-get-routings\n      description: Retrieve routings.\n      hints:\n        readOnly: true\n      call: oracle-manufacturing.get-routings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mfg-get-discrete-jobs\n      description: Retrieve discrete jobs.\n      hints:\n        readOnly: true\n      call: oracle-manufacturing.get-discrete-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mfg-create-discrete-job\n      description: Create a discrete job.\n      hints:\n       \
  \ readOnly: false\n      call: oracle-manufacturing.create-discrete-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mfg-get-discrete-job-by-id\n      description: Get discrete job by ID.\n      hints:\n        readOnly: true\n      call: oracle-manufacturing.get-discrete-job-by-id\n      with:\n        wipEntityId: tools.wip_entity_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mfg-get-wip-operations\n      description: Retrieve WIP operations.\n      hints:\n        readOnly: true\n      call: oracle-manufacturing.get-wip-operations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mfg-complete-assembly\n      description: Complete an assembly.\n      hints:\n        readOnly: false\n      call: oracle-manufacturing.complete-assembly\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mfg-issue-material\n      description: Issue material to a job.\n   \
  \   hints:\n        readOnly: false\n      call: oracle-manufacturing.issue-material\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inv-get-inventory-items\n      description: Retrieve inventory items.\n      hints:\n        readOnly: true\n      call: oracle-supply-chain.get-inventory-items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inv-get-onhand-quantities\n      description: Retrieve on-hand quantities.\n      hints:\n        readOnly: true\n      call: oracle-supply-chain.get-onhand-quantities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inv-get-sales-orders\n      description: Retrieve sales orders.\n      hints:\n        readOnly: true\n      call: oracle-supply-chain.get-sales-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inv-get-deliveries\n      description: Retrieve deliveries.\n      hints:\n        readOnly: true\n      call:\
  \ oracle-supply-chain.get-deliveries\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
