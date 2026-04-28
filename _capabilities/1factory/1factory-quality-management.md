---
categories:
- procurement-supply-chain
consumed_apis:
- 1factory
description: Unified quality management workflow for 1Factory. Combines manufacturing inspections, receiving inspections, supplier quality, customer quality, FAI, part master management, and QMS records (NCRs, CAPAs, complaints) into a single workflow for quality engineers, production managers, and supplier quality teams.
layout: capability
name: 1Factory Quality Management
operations:
- description: List all part masters in the 1Factory account.
  method: GET
  name: list-part-masters
  path: /v1/part-masters
- description: Create or update a part master entry.
  method: PUT
  name: create-part-master
  path: /v1/part-masters
- description: List all manufacturing inspections.
  method: GET
  name: list-manufacturing-inspections
  path: /v1/inspections
- description: List all receiving inspections.
  method: GET
  name: list-receiving-inspections
  path: /v1/inspections
- description: List all non-conformance reports.
  method: GET
  name: list-ncrs
  path: /v1/qms
- description: List all corrective and preventive actions.
  method: GET
  name: list-capas
  path: /v1/qms
- description: List all quality complaints.
  method: GET
  name: list-complaints
  path: /v1/qms
- description: List all suppliers.
  method: GET
  name: list-suppliers
  path: /v1/suppliers
- description: List all manufacturing first article inspections.
  method: GET
  name: list-manufacturing-fai
  path: /v1/fai
personas: []
provider_name: 1Factory
provider_slug: 1factory
search_terms:
- manages inspection plans, reviews ncrs/capas, and tracks quality metrics
- all types of quality inspections (manufacturing, receiving, supplier, customer)
- list part masters
- create or update a part master entry.
- list all manufacturing inspections with optional filters.
- part master data and inspection planning
- create a new manufacturing inspection record.
- end-to-end quality management workflow covering inspections, fai, suppliers, and qms
- list all non-conformance reports.
- list all supplier records.
- quality
- Supplier Quality Manager
- manage part master records and assembly relationships.
- manufacturing
- list capas
- quality management system records including ncrs, capas, and complaints.
- list complaints
- manufacturing, receiving, supplier, and customer inspections.
- supplier qualification and performance management
- list all suppliers.
- list all quality complaints.
- manages supplier qualifications, receiving inspections, and supplier capas
- list fai manufacturing
- list all part masters in the 1factory account.
- list receiving inspections
- monitoring
- list all manufacturing first article inspections.
- list all quality complaints from customers.
- inspections
- list all receiving inspections.
- list ncrs
- first article inspection records.
- list manufacturing fai
- analytics
- Production Manager
- Quality Engineer
- list all corrective and preventive actions.
- list all non-conformance reports for quality issue tracking.
- monitors manufacturing inspections and work order quality status
- list suppliers
- quality management system records
- create part master
- list all manufacturing inspections.
- list all part master records in the 1factory account.
- supplier management and qualification tracking.
- create manufacturing inspection
- create or update a part master record.
- data collection
- suppliers
- list manufacturing inspections
slug: 1factory-quality-management
tags:
- Manufacturing
- Quality
- Inspections
- Suppliers
tools:
- description: List all part master records in the 1Factory account.
  hints:
    openWorld: false
    readOnly: true
  name: list-part-masters
- description: Create or update a part master record.
  hints:
    destructive: false
    readOnly: false
  name: create-part-master
- description: List all manufacturing inspections with optional filters.
  hints:
    openWorld: false
    readOnly: true
  name: list-manufacturing-inspections
- description: Create a new manufacturing inspection record.
  hints:
    destructive: false
    readOnly: false
  name: create-manufacturing-inspection
- description: List all receiving inspections.
  hints:
    openWorld: false
    readOnly: true
  name: list-receiving-inspections
- description: List all supplier records.
  hints:
    openWorld: false
    readOnly: true
  name: list-suppliers
- description: List all non-conformance reports for quality issue tracking.
  hints:
    openWorld: false
    readOnly: true
  name: list-ncrs
- description: List all corrective and preventive actions.
  hints:
    openWorld: false
    readOnly: true
  name: list-capas
- description: List all quality complaints from customers.
  hints:
    openWorld: false
    readOnly: true
  name: list-complaints
- description: List all manufacturing first article inspections.
  hints:
    openWorld: false
    readOnly: true
  name: list-fai-manufacturing
---
