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
- list on-hand quantities.
- list boms.
- mfg complete assembly
- supply chain
- erp
- retrieve wip operations.
- mfg issue material
- oracle
- issue material to a job.
- mfg get discrete job by id
- retrieve discrete jobs.
- inv get sales orders
- get discrete jobs
- get bom by id.
- production
- get onhand quantities
- get discrete job by id.
- inv get inventory items
- on-hand quantity management.
- business applications
- enterprise
- list inventory items.
- mfg get wip operations
- get inventory items
- discrete job management.
- mfg create discrete job
- mfg get bill of material by id
- mfg get bills of material
- e-business suite
- retrieve routings.
- bom management.
- mfg get routings
- inv get onhand quantities
- inventory item management.
- retrieve deliveries.
- inv get deliveries
- get bills of material
- list discrete jobs.
- retrieve inventory items.
- retrieve sales orders.
- retrieve bills of material.
- complete an assembly.
- mfg get discrete jobs
- retrieve on-hand quantities.
- manufacturing
- create a discrete job.
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
