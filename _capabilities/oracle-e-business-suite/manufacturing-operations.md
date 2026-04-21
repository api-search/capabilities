---
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
- manufacturing
- get discrete job by id.
- retrieve on-hand quantities.
- erp
- mfg complete assembly
- mfg get discrete jobs
- mfg get discrete job by id
- list discrete jobs.
- list inventory items.
- production
- inventory item management.
- retrieve sales orders.
- inv get sales orders
- bom management.
- get onhand quantities
- mfg get bills of material
- enterprise
- create a discrete job.
- get bills of material
- inv get onhand quantities
- supply chain
- complete an assembly.
- business applications
- mfg get wip operations
- get bom by id.
- get inventory items
- mfg get bill of material by id
- retrieve bills of material.
- inv get deliveries
- e-business suite
- list boms.
- oracle
- inv get inventory items
- retrieve routings.
- issue material to a job.
- get discrete jobs
- discrete job management.
- retrieve wip operations.
- retrieve inventory items.
- retrieve discrete jobs.
- retrieve deliveries.
- mfg create discrete job
- list on-hand quantities.
- on-hand quantity management.
- mfg issue material
- mfg get routings
slug: manufacturing-operations
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
