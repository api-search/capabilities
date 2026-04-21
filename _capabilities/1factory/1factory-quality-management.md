---
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
- list fai manufacturing
- list all part masters in the 1factory account.
- Quality Engineer
- list all non-conformance reports.
- manufacturing
- list all quality complaints.
- manages supplier qualifications, receiving inspections, and supplier capas
- analytics
- Production Manager
- first article inspection records.
- list all manufacturing first article inspections.
- supplier management and qualification tracking.
- list all part master records in the 1factory account.
- list all suppliers.
- manage part master records and assembly relationships.
- inspections
- quality management system records
- list manufacturing inspections
- supplier qualification and performance management
- list all non-conformance reports for quality issue tracking.
- list all manufacturing inspections.
- list manufacturing fai
- suppliers
- create or update a part master record.
- create a new manufacturing inspection record.
- create manufacturing inspection
- list all supplier records.
- list all corrective and preventive actions.
- manages inspection plans, reviews ncrs/capas, and tracks quality metrics
- part master data and inspection planning
- create part master
- manufacturing, receiving, supplier, and customer inspections.
- monitors manufacturing inspections and work order quality status
- data collection
- list ncrs
- list capas
- list suppliers
- monitoring
- list receiving inspections
- list all quality complaints from customers.
- quality
- end-to-end quality management workflow covering inspections, fai, suppliers, and qms
- list all manufacturing inspections with optional filters.
- create or update a part master entry.
- list all receiving inspections.
- all types of quality inspections (manufacturing, receiving, supplier, customer)
- quality management system records including ncrs, capas, and complaints.
- list complaints
- list part masters
- Supplier Quality Manager
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
