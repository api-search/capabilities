---
categories: []
consumed_apis:
- trustwell-genesis
- trustwell-foodlogiq
description: Unified food safety management capability combining Genesis Foods nutrition analysis and FoodLogiQ supply chain operations. Used by food manufacturers, quality managers, and regulatory compliance teams to formulate products, generate nutrition labels, manage supplier compliance, track quality incidents, maintain FSMA 204-compliant traceability records, and manage recall events from a single integrated platform.
layout: capability
name: Trustwell Food Safety Management
operations:
- description: Query food formulation data including nutrients and allergens.
  method: POST
  name: query-foods
  path: /v1/foods/query
- description: Get nutrient definitions.
  method: GET
  name: query-nutrients
  path: /v1/nutrients
- description: Get allergen definitions.
  method: GET
  name: query-allergens
  path: /v1/allergens
- description: Get regulatory standards by country.
  method: GET
  name: query-regulations
  path: /v1/regulations
- description: List supply chain suppliers.
  method: GET
  name: list-suppliers
  path: /v1/suppliers
- description: List quality incidents.
  method: GET
  name: list-quality-incidents
  path: /v1/quality/incidents
- description: Create quality incident.
  method: POST
  name: create-quality-incident
  path: /v1/quality/incidents
- description: List traceability lot records.
  method: GET
  name: list-lots
  path: /v1/traceability/lots
- description: List recall events.
  method: GET
  name: list-recalls
  path: /v1/recalls
- description: Create recall event.
  method: POST
  name: create-recall
  path: /v1/recalls
personas: []
provider_name: Trustwell
provider_slug: trustwell
search_terms:
- list traceability lot records.
- recall management
- list food recall and withdrawal events with status filtering.
- get allergen definitions.
- food formulation queries
- list supply chain suppliers.
- supply chain
- food formulation
- food safety
- create quality incident.
- nutrition
- create recall event.
- add a new supplier to the foodlogiq supply chain network.
- query food formulation data including nutrients and allergens.
- list food quality incidents with severity and status filtering for quality monitoring.
- generate and retrieve nutrition label images for us, canadian, eu, mexican, and australian regulatory formats.
- quality incidents
- get all standard and custom nutrient definitions from genesis foods.
- list recalls
- create a food quality incident report for a supplier or product safety issue.
- initiate a food product recall or withdrawal event (voluntary, mock, or regulatory).
- get regulatory standards by country.
- regulatory standards
- query labels
- list lots
- list fsma 204-compliant traceability lot records for farm-to-fork supply chain tracking.
- nutrition labeling
- query allergens
- get all allergen definitions for allergen declaration and labeling compliance.
- list quality incidents
- create supplier
- quality management
- allergen definitions
- query regulations
- list recall events.
- list food supply chain suppliers with status and compliance information.
- query nutrients
- compliance
- food technology
- create quality incident
- food labeling
- food industry
- list suppliers
- get nutrient definitions.
- list quality incidents.
- traceability
- supply chain suppliers
- fsma 204 traceability lots
- recall events
- create recall
- query foods
- get regulatory standards, nutrition claims, and labeling requirements by country and regulatory authority.
- nutrient definitions
- query food formulation data including nutrient content, allergen declarations, and label information from genesis foods.
slug: food-safety-management
source_filename: food-safety-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Trustwell Food Safety Management\"\n  description: >-\n    Unified food safety management capability combining Genesis Foods nutrition analysis\n    and FoodLogiQ supply chain operations. Used by food manufacturers, quality managers,\n    and regulatory compliance teams to formulate products, generate nutrition labels,\n    manage supplier compliance, track quality incidents, maintain FSMA 204-compliant\n    traceability records, and manage recall events from a single integrated platform.\n  tags:\n    - Food Safety\n    - Supply Chain\n    - Food Formulation\n    - Nutrition Labeling\n    - Traceability\n    - Compliance\n    - Quality Management\n    - Recall Management\n    - Food Industry\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRUSTWELL_API_KEY: TRUSTWELL_API_KEY\n\ncapability:\n  consumes:\n    - import: trustwell-genesis\n      location: ./shared/genesis-foods.yaml\n\
  \    - import: trustwell-foodlogiq\n      location: ./shared/foodlogiq.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: trustwell-food-safety-api\n      description: \"Unified REST API for food formulation, nutrition labeling, supply chain, and food safety management.\"\n      resources:\n        - path: /v1/foods/query\n          name: foods\n          description: \"Food formulation queries\"\n          operations:\n            - method: POST\n              name: query-foods\n              description: \"Query food formulation data including nutrients and allergens.\"\n              call: \"trustwell-genesis.query-foods\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/nutrients\n          name: nutrients\n          description: \"Nutrient definitions\"\n          operations:\n            - method: GET\n              name: query-nutrients\n              description: \"Get nutrient definitions.\"\
  \n              call: \"trustwell-genesis.query-nutrients\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/allergens\n          name: allergens\n          description: \"Allergen definitions\"\n          operations:\n            - method: GET\n              name: query-allergens\n              description: \"Get allergen definitions.\"\n              call: \"trustwell-genesis.query-allergens\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/regulations\n          name: regulations\n          description: \"Regulatory standards\"\n          operations:\n            - method: GET\n              name: query-regulations\n              description: \"Get regulatory standards by country.\"\n              call: \"trustwell-genesis.query-regulations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n        - path: /v1/suppliers\n          name: suppliers\n          description: \"Supply chain suppliers\"\n          operations:\n            - method: GET\n              name: list-suppliers\n              description: \"List supply chain suppliers.\"\n              call: \"trustwell-foodlogiq.list-suppliers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/quality/incidents\n          name: quality-incidents\n          description: \"Quality incidents\"\n          operations:\n            - method: GET\n              name: list-quality-incidents\n              description: \"List quality incidents.\"\n              call: \"trustwell-foodlogiq.list-quality-incidents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-quality-incident\n              description: \"Create quality incident.\"\n             \
  \ call: \"trustwell-foodlogiq.create-quality-incident\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/traceability/lots\n          name: lots\n          description: \"FSMA 204 traceability lots\"\n          operations:\n            - method: GET\n              name: list-lots\n              description: \"List traceability lot records.\"\n              call: \"trustwell-foodlogiq.list-lots\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/recalls\n          name: recalls\n          description: \"Recall events\"\n          operations:\n            - method: GET\n              name: list-recalls\n              description: \"List recall events.\"\n              call: \"trustwell-foodlogiq.list-recalls\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n         \
  \     name: create-recall\n              description: \"Create recall event.\"\n              call: \"trustwell-foodlogiq.create-recall\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: trustwell-food-safety-mcp\n      transport: http\n      description: \"MCP server for AI-assisted food formulation, nutrition compliance, supply chain monitoring, and food safety management.\"\n      tools:\n        - name: query-foods\n          description: \"Query food formulation data including nutrient content, allergen declarations, and label information from Genesis Foods.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trustwell-genesis.query-foods\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: query-nutrients\n          description: \"Get all standard and custom nutrient definitions from Genesis Foods.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trustwell-genesis.query-nutrients\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-allergens\n          description: \"Get all allergen definitions for allergen declaration and labeling compliance.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trustwell-genesis.query-allergens\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-labels\n          description: \"Generate and retrieve nutrition label images for US, Canadian, EU, Mexican, and Australian regulatory formats.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trustwell-genesis.query-labels\"\n  \
  \        with:\n            labelQuery: \"tools.labelQuery\"\n            variables: \"tools.variables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-regulations\n          description: \"Get regulatory standards, nutrition claims, and labeling requirements by country and regulatory authority.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trustwell-genesis.query-regulations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-suppliers\n          description: \"List food supply chain suppliers with status and compliance information.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trustwell-foodlogiq.list-suppliers\"\n          with:\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n      \
  \  - name: create-supplier\n          description: \"Add a new supplier to the FoodLogiQ supply chain network.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"trustwell-foodlogiq.create-supplier\"\n          with:\n            name: \"tools.name\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-quality-incidents\n          description: \"List food quality incidents with severity and status filtering for quality monitoring.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trustwell-foodlogiq.list-quality-incidents\"\n          with:\n            status: \"tools.status\"\n            severity: \"tools.severity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-quality-incident\n          description: \"Create a food quality incident\
  \ report for a supplier or product safety issue.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"trustwell-foodlogiq.create-quality-incident\"\n          with:\n            title: \"tools.title\"\n            severity: \"tools.severity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-lots\n          description: \"List FSMA 204-compliant traceability lot records for farm-to-fork supply chain tracking.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trustwell-foodlogiq.list-lots\"\n          with:\n            productId: \"tools.productId\"\n            fromDate: \"tools.fromDate\"\n            toDate: \"tools.toDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-recalls\n          description: \"List food recall and withdrawal events with status filtering.\"\n  \
  \        hints:\n            readOnly: true\n            openWorld: false\n          call: \"trustwell-foodlogiq.list-recalls\"\n          with:\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-recall\n          description: \"Initiate a food product recall or withdrawal event (voluntary, mock, or regulatory).\"\n          hints:\n            readOnly: false\n            destructive: false\n            openWorld: false\n          call: \"trustwell-foodlogiq.create-recall\"\n          with:\n            title: \"tools.title\"\n            reason: \"tools.reason\"\n            recallType: \"tools.recallType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trustwell/refs/heads/main/capabilities/food-safety-management.yaml
tags:
- Food Safety
- Supply Chain
- Food Formulation
- Nutrition Labeling
- Traceability
- Compliance
- Quality Management
- Recall Management
- Food Industry
tools:
- description: Query food formulation data including nutrient content, allergen declarations, and label information from Genesis Foods.
  hints:
    openWorld: false
    readOnly: true
  name: query-foods
- description: Get all standard and custom nutrient definitions from Genesis Foods.
  hints:
    openWorld: false
    readOnly: true
  name: query-nutrients
- description: Get all allergen definitions for allergen declaration and labeling compliance.
  hints:
    openWorld: false
    readOnly: true
  name: query-allergens
- description: Generate and retrieve nutrition label images for US, Canadian, EU, Mexican, and Australian regulatory formats.
  hints:
    openWorld: false
    readOnly: true
  name: query-labels
- description: Get regulatory standards, nutrition claims, and labeling requirements by country and regulatory authority.
  hints:
    openWorld: false
    readOnly: true
  name: query-regulations
- description: List food supply chain suppliers with status and compliance information.
  hints:
    openWorld: false
    readOnly: true
  name: list-suppliers
- description: Add a new supplier to the FoodLogiQ supply chain network.
  hints:
    openWorld: false
    readOnly: false
  name: create-supplier
- description: List food quality incidents with severity and status filtering for quality monitoring.
  hints:
    openWorld: false
    readOnly: true
  name: list-quality-incidents
- description: Create a food quality incident report for a supplier or product safety issue.
  hints:
    openWorld: false
    readOnly: false
  name: create-quality-incident
- description: List FSMA 204-compliant traceability lot records for farm-to-fork supply chain tracking.
  hints:
    openWorld: false
    readOnly: true
  name: list-lots
- description: List food recall and withdrawal events with status filtering.
  hints:
    openWorld: false
    readOnly: true
  name: list-recalls
- description: Initiate a food product recall or withdrawal event (voluntary, mock, or regulatory).
  hints:
    destructive: false
    openWorld: false
    readOnly: false
  name: create-recall
---
