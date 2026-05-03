---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Disability Employment Procurement
operations: []
personas: []
provider_name: US AbilityOne Commission
provider_slug: us-abilityone-commission
search_terms:
- disability employment
- federal agency managers overseeing abilityone compliance across the agency
- accessibility
- federal procurement workflow for identifying and ordering products and services from abilityone nonprofit agencies under the jwod act mandate
- procurement
- federal contracting officers responsible for verifying abilityone mandatory source requirements
- federal government
- acquisition personnel searching for compliant sources for products and services
- nonprofit
slug: disability-employment-procurement
source_filename: disability-employment-procurement.yaml
source_heading: Capability Spec
source_yaml: "name: AbilityOne Disability Employment Procurement\ndescription: >-\n  Workflow capability for the AbilityOne Program procurement operations. Enables\n  federal contracting officers, procurement specialists, and acquisition teams\n  to search the AbilityOne Procurement List, verify mandatory source requirements\n  under the Javits-Wagner-O'Day Act, and identify nonprofit agencies employing\n  people who are blind or have significant disabilities.\nversion: '1.0.0'\nmcp:\n  port: 9080\nrest:\n  port: 8080\npersonas:\n  - name: Contracting Officer\n    description: >-\n      Federal contracting officers verifying mandatory source requirements and\n      identifying AbilityOne sources for procurement actions\n  - name: Procurement Specialist\n    description: >-\n      Acquisition personnel searching the Procurement List to find compliant\n      sources for products and services\n  - name: Agency Procurement Manager\n    description: >-\n      Federal agency procurement managers\
  \ managing AbilityOne compliance\n      across their agency's acquisition portfolio\ntools:\n  - name: search_procurement_products\n    description: Search the AbilityOne Procurement List for products by NSN or description\n    operationId: searchProducts\n    api: procurement-list-api\n    parameters:\n      - name: nsn\n        description: National Stock Number to search for\n      - name: description\n        description: Product description keyword\n      - name: nonprofit\n        description: Filter by NIB or SourceAmerica affiliate\n  - name: get_product_by_nsn\n    description: Look up a specific product on the Procurement List by National Stock Number\n    operationId: getProduct\n    api: procurement-list-api\n    parameters:\n      - name: nsn\n        description: The National Stock Number (format xxxx-xx-xxx-xxxx)\n  - name: search_procurement_services\n    description: Search the AbilityOne Procurement List for services by type and location\n    operationId: searchServices\n\
  \    api: procurement-list-api\n    parameters:\n      - name: serviceType\n        description: Type of service (Custodial, Grounds Maintenance, Food Service, etc.)\n      - name: state\n        description: State where service is needed\n  - name: list_nonprofit_agencies\n    description: Find AbilityOne-participating nonprofit agencies by state or affiliate\n    operationId: listAgencies\n    api: procurement-list-api\n    parameters:\n      - name: affiliate\n        description: Filter by NIB or SourceAmerica\n      - name: state\n        description: State abbreviation to filter by\n  - name: download_products_report\n    description: Download the complete Procurement List products report for offline reference\n    operationId: downloadProductReport\n    api: procurement-list-api\n    parameters:\n      - name: format\n        description: Output format (excel or csv)\n      - name: affiliate\n        description: Filter by nonprofit affiliate\n  - name: download_services_report\n\
  \    description: Download the complete Procurement List services report for offline reference\n    operationId: downloadServiceReport\n    api: procurement-list-api\n    parameters:\n      - name: format\n        description: Output format (excel or csv)\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/us-abilityone-commission/refs/heads/main/capabilities/disability-employment-procurement.yaml
tags: []
tools: []
---
