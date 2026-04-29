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
- list all non-conformance reports for quality issue tracking.
- monitoring
- suppliers
- list all quality complaints.
- list fai manufacturing
- end-to-end quality management workflow covering inspections, fai, suppliers, and qms
- list complaints
- list suppliers
- list all quality complaints from customers.
- manufacturing, receiving, supplier, and customer inspections.
- part master data and inspection planning
- analytics
- list all receiving inspections.
- list manufacturing inspections
- list all part masters in the 1factory account.
- list part masters
- list all manufacturing inspections with optional filters.
- first article inspection records.
- all types of quality inspections (manufacturing, receiving, supplier, customer)
- supplier qualification and performance management
- list all suppliers.
- list ncrs
- list all manufacturing first article inspections.
- Production Manager
- list all corrective and preventive actions.
- list all manufacturing inspections.
- create or update a part master record.
- Quality Engineer
- manages supplier qualifications, receiving inspections, and supplier capas
- create manufacturing inspection
- monitors manufacturing inspections and work order quality status
- manufacturing
- list all part master records in the 1factory account.
- create a new manufacturing inspection record.
- data collection
- supplier management and qualification tracking.
- manage part master records and assembly relationships.
- quality management system records including ncrs, capas, and complaints.
- list all supplier records.
- Supplier Quality Manager
- create part master
- quality
- list receiving inspections
- list manufacturing fai
- create or update a part master entry.
- inspections
- list all non-conformance reports.
- quality management system records
- list capas
- manages inspection plans, reviews ncrs/capas, and tracks quality metrics
slug: 1factory-quality-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: 1Factory Quality Management\n  description: >-\n    Unified quality management workflow for 1Factory. Combines manufacturing inspections,\n    receiving inspections, supplier quality, customer quality, FAI, part master management,\n    and QMS records (NCRs, CAPAs, complaints) into a single workflow for quality engineers,\n    production managers, and supplier quality teams.\n  tags:\n    - Manufacturing\n    - Quality\n    - Inspections\n    - Suppliers\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      FACTORY_ORG_ID: FACTORY_ORG_ID\n      FACTORY_API_KEY: FACTORY_API_KEY\n\ncapability:\n  consumes:\n    - import: 1factory\n      location: ./shared/1factory.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: 1factory-quality-api\n      description: \"Unified REST API for 1Factory quality management workflows.\"\n      resources:\n        - path: /v1/part-masters\n\
  \          name: part-masters\n          description: \"Manage part master records and assembly relationships.\"\n          operations:\n            - method: GET\n              name: list-part-masters\n              description: \"List all part masters in the 1Factory account.\"\n              call: \"1factory.get-partmasters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: create-part-master\n              description: \"Create or update a part master entry.\"\n              call: \"1factory.put-partmasters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/inspections\n          name: inspections\n          description: \"Manufacturing, receiving, supplier, and customer inspections.\"\n          operations:\n            - method: GET\n              name: list-manufacturing-inspections\n              description:\
  \ \"List all manufacturing inspections.\"\n              call: \"1factory.get-mfg-inspections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-receiving-inspections\n              description: \"List all receiving inspections.\"\n              call: \"1factory.get-rec-inspections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/qms\n          name: qms\n          description: \"Quality Management System records including NCRs, CAPAs, and complaints.\"\n          operations:\n            - method: GET\n              name: list-ncrs\n              description: \"List all non-conformance reports.\"\n              call: \"1factory.get-qms-ncrs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-capas\n       \
  \       description: \"List all corrective and preventive actions.\"\n              call: \"1factory.get-qms-capas\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-complaints\n              description: \"List all quality complaints.\"\n              call: \"1factory.get-qms-complaints\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/suppliers\n          name: suppliers\n          description: \"Supplier management and qualification tracking.\"\n          operations:\n            - method: GET\n              name: list-suppliers\n              description: \"List all suppliers.\"\n              call: \"1factory.get-sup\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/fai\n          name: fai\n          description: \"First Article Inspection\
  \ records.\"\n          operations:\n            - method: GET\n              name: list-manufacturing-fai\n              description: \"List all manufacturing first article inspections.\"\n              call: \"1factory.get-mfg-fais\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: 1factory-quality-mcp\n      transport: http\n      description: \"MCP server for AI-assisted quality management using 1Factory APIs.\"\n      tools:\n        - name: list-part-masters\n          description: \"List all part master records in the 1Factory account.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"1factory.get-partmasters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-part-master\n          description: \"Create or update a part master record.\"\n          hints:\n        \
  \    readOnly: false\n            destructive: false\n          call: \"1factory.put-partmasters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-manufacturing-inspections\n          description: \"List all manufacturing inspections with optional filters.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"1factory.get-mfg-inspections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-manufacturing-inspection\n          description: \"Create a new manufacturing inspection record.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"1factory.post-mfg-inspections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-receiving-inspections\n          description: \"List all receiving inspections.\"\n          hints:\n\
  \            readOnly: true\n            openWorld: false\n          call: \"1factory.get-rec-inspections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-suppliers\n          description: \"List all supplier records.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"1factory.get-sup\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-ncrs\n          description: \"List all non-conformance reports for quality issue tracking.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"1factory.get-qms-ncrs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-capas\n          description: \"List all corrective and preventive actions.\"\n          hints:\n            readOnly: true\n            openWorld: false\n        \
  \  call: \"1factory.get-qms-capas\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-complaints\n          description: \"List all quality complaints from customers.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"1factory.get-qms-complaints\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-fai-manufacturing\n          description: \"List all manufacturing first article inspections.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"1factory.get-mfg-fais\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/1factory/refs/heads/main/capabilities/1factory-quality-management.yaml
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
