---
categories: []
consumed_apis:
- salesforce-net-zero
description: Unified workflow capability for carbon accounting and ESG reporting in Salesforce Net Zero Cloud. Combines carbon emission tracking, energy consumption monitoring, sustainability goal management, and environmental data reporting for sustainability teams.
layout: capability
name: Salesforce Net Zero Cloud Carbon Accounting
operations:
- description: List carbon emission records with optional scope and year filters
  method: GET
  name: list-carbon-emissions
  path: /v1/emissions
- description: Create a new carbon emission record
  method: POST
  name: create-carbon-emission
  path: /v1/emissions
- description: Get a specific carbon emission record
  method: GET
  name: get-carbon-emission
  path: /v1/emissions/{emissionId}
- description: Update a carbon emission record
  method: PATCH
  name: update-carbon-emission
  path: /v1/emissions/{emissionId}
- description: Delete a carbon emission record
  method: DELETE
  name: delete-carbon-emission
  path: /v1/emissions/{emissionId}
- description: List energy consumption records
  method: GET
  name: list-energy-consumption
  path: /v1/energy
- description: Create an energy consumption record
  method: POST
  name: create-energy-consumption
  path: /v1/energy
- description: List sustainability goals
  method: GET
  name: list-sustainability-goals
  path: /v1/goals
- description: Create a sustainability goal
  method: POST
  name: create-sustainability-goal
  path: /v1/goals
- description: List emission factors
  method: GET
  name: list-emission-factors
  path: /v1/emission-factors
- description: List waste disposal records
  method: GET
  name: list-waste-disposal
  path: /v1/waste
- description: Create a waste disposal record
  method: POST
  name: create-waste-disposal
  path: /v1/waste
- description: List water withdrawal records
  method: GET
  name: list-water-withdrawal
  path: /v1/water
- description: Create a water withdrawal record
  method: POST
  name: create-water-withdrawal
  path: /v1/water
personas: []
provider_name: Salesforce Net Zero Cloud
provider_slug: salesforce-net-zero-cloud
search_terms:
- list sustainability goals including net zero targets and progress
- list carbon emissions
- individual emission record operations
- create a sustainability goal
- water withdrawal and consumption tracking
- create a water withdrawal record
- waste disposal tracking
- list energy consumption records by type (electricity, gas, renewable)
- list energy consumption
- list energy consumption records
- get details for a specific carbon emission record
- list waste disposal records
- carbon emission record management (scope 1, 2, 3)
- net zero and sustainability goal management
- create an energy consumption record
- list waste disposal records by type and disposal method
- carbon emissions
- salesforce
- environmental
- create waste disposal
- query sustainability data
- list water withdrawal records
- emission factor catalog
- get a specific carbon emission record
- list water withdrawal records by source
- create waste disposal record
- update carbon emission
- sustainability
- delete a carbon emission record
- create energy consumption
- create sustainability goal
- create a new sustainability goal with baseline, target year, and reduction percentage
- list sustainability goals
- net zero cloud
- esg
- update a carbon emission record
- list emission factors
- carbon accounting
- list water withdrawal
- list carbon emission records with optional scope and year filters
- energy consumption tracking
- create carbon emission
- get carbon emission
- delete carbon emission
- query any sustainability data using soql for advanced esg reporting
- update an existing carbon emission record
- list waste disposal
- create a waste disposal record
- create a new carbon emission record
- create water withdrawal
- create a new carbon emission record (scope 1, 2, or 3)
- climate
- create a new waste disposal record (landfill, recycled, composted, etc.)
- create water withdrawal record
- net zero
- create a new water withdrawal record for a facility
- list emission factors used for co2e calculations, filterable by category and region
- create a new energy consumption record for a facility
- list carbon emission records filtered by scope and reporting year
slug: carbon-accounting
source_filename: carbon-accounting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce Net Zero Cloud Carbon Accounting\"\n  description: >-\n    Unified workflow capability for carbon accounting and ESG reporting\n    in Salesforce Net Zero Cloud. Combines carbon emission tracking,\n    energy consumption monitoring, sustainability goal management, and\n    environmental data reporting for sustainability teams.\n  tags:\n    - Salesforce\n    - Net Zero Cloud\n    - Carbon Accounting\n    - ESG\n    - Sustainability\n    - Climate\n    - Environmental\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: salesforce-net-zero\n      location: ./shared/net-zero-cloud-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: carbon-accounting-api\n      description: \"Unified REST API for carbon accounting and ESG reporting.\"\n      resources:\n\
  \        - path: /v1/emissions\n          name: carbon-emissions\n          description: \"Carbon emission record management (Scope 1, 2, 3)\"\n          operations:\n            - method: GET\n              name: list-carbon-emissions\n              description: \"List carbon emission records with optional scope and year filters\"\n              call: \"salesforce-net-zero.list-carbon-emissions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-carbon-emission\n              description: \"Create a new carbon emission record\"\n              call: \"salesforce-net-zero.create-carbon-emission\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/emissions/{emissionId}\n          name: carbon-emission\n          description: \"Individual emission record operations\"\n          operations:\n            - method: GET\n\
  \              name: get-carbon-emission\n              description: \"Get a specific carbon emission record\"\n              call: \"salesforce-net-zero.get-carbon-emission\"\n              with:\n                emissionId: \"rest.emissionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-carbon-emission\n              description: \"Update a carbon emission record\"\n              call: \"salesforce-net-zero.update-carbon-emission\"\n              with:\n                emissionId: \"rest.emissionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-carbon-emission\n              description: \"Delete a carbon emission record\"\n              call: \"salesforce-net-zero.delete-carbon-emission\"\n              with:\n                emissionId: \"rest.emissionId\"\n \
  \             outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/energy\n          name: energy-consumption\n          description: \"Energy consumption tracking\"\n          operations:\n            - method: GET\n              name: list-energy-consumption\n              description: \"List energy consumption records\"\n              call: \"salesforce-net-zero.list-energy-consumption\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-energy-consumption\n              description: \"Create an energy consumption record\"\n              call: \"salesforce-net-zero.create-energy-consumption\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/goals\n          name: sustainability-goals\n          description: \"Net zero and sustainability goal management\"\n\
  \          operations:\n            - method: GET\n              name: list-sustainability-goals\n              description: \"List sustainability goals\"\n              call: \"salesforce-net-zero.list-sustainability-goals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-sustainability-goal\n              description: \"Create a sustainability goal\"\n              call: \"salesforce-net-zero.create-sustainability-goal\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/emission-factors\n          name: emission-factors\n          description: \"Emission factor catalog\"\n          operations:\n            - method: GET\n              name: list-emission-factors\n              description: \"List emission factors\"\n              call: \"salesforce-net-zero.list-emission-factors\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/waste\n          name: waste-disposal\n          description: \"Waste disposal tracking\"\n          operations:\n            - method: GET\n              name: list-waste-disposal\n              description: \"List waste disposal records\"\n              call: \"salesforce-net-zero.list-waste-disposal-records\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-waste-disposal\n              description: \"Create a waste disposal record\"\n              call: \"salesforce-net-zero.create-waste-disposal-record\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/water\n          name: water-usage\n          description: \"Water withdrawal and consumption tracking\"\n          operations:\n            - method: GET\n            \
  \  name: list-water-withdrawal\n              description: \"List water withdrawal records\"\n              call: \"salesforce-net-zero.list-water-withdrawal-records\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-water-withdrawal\n              description: \"Create a water withdrawal record\"\n              call: \"salesforce-net-zero.create-water-withdrawal-record\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: carbon-accounting-mcp\n      transport: http\n      description: \"MCP server for AI-assisted carbon accounting and ESG reporting.\"\n      tools:\n        - name: list-carbon-emissions\n          description: \"List carbon emission records filtered by scope and reporting year\"\n          hints:\n            readOnly: true\n            idempotent: true\n     \
  \       openWorld: true\n          call: \"salesforce-net-zero.list-carbon-emissions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-carbon-emission\n          description: \"Get details for a specific carbon emission record\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-net-zero.get-carbon-emission\"\n          with:\n            emissionId: \"tools.emissionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-carbon-emission\n          description: \"Create a new carbon emission record (Scope 1, 2, or 3)\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-net-zero.create-carbon-emission\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-carbon-emission\n          description: \"Update\
  \ an existing carbon emission record\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"salesforce-net-zero.update-carbon-emission\"\n          with:\n            emissionId: \"tools.emissionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-carbon-emission\n          description: \"Delete a carbon emission record\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"salesforce-net-zero.delete-carbon-emission\"\n          with:\n            emissionId: \"tools.emissionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sustainability-goals\n          description: \"List sustainability goals including net zero targets and progress\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n  \
  \        call: \"salesforce-net-zero.list-sustainability-goals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-sustainability-goal\n          description: \"Create a new sustainability goal with baseline, target year, and reduction percentage\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-net-zero.create-sustainability-goal\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-emission-factors\n          description: \"List emission factors used for CO2e calculations, filterable by category and region\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"salesforce-net-zero.list-emission-factors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-energy-consumption\n    \
  \      description: \"List energy consumption records by type (electricity, gas, renewable)\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-net-zero.list-energy-consumption\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-energy-consumption\n          description: \"Create a new energy consumption record for a facility\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-net-zero.create-energy-consumption\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-waste-disposal-records\n          description: \"List waste disposal records by type and disposal method\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-net-zero.list-waste-disposal-records\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n        - name: create-waste-disposal-record\n          description: \"Create a new waste disposal record (landfill, recycled, composted, etc.)\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-net-zero.create-waste-disposal-record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-water-withdrawal-records\n          description: \"List water withdrawal records by source\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-net-zero.list-water-withdrawal-records\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-water-withdrawal-record\n          description: \"Create a new water withdrawal record for a facility\"\n          hints:\n            readOnly: false\n            destructive: false\n          call:\
  \ \"salesforce-net-zero.create-water-withdrawal-record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-sustainability-data\n          description: \"Query any sustainability data using SOQL for advanced ESG reporting\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-net-zero.query-sustainability-data\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce-net-zero-cloud/refs/heads/main/capabilities/carbon-accounting.yaml
tags:
- Salesforce
- Net Zero Cloud
- Carbon Accounting
- ESG
- Sustainability
- Climate
- Environmental
tools:
- description: List carbon emission records filtered by scope and reporting year
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-carbon-emissions
- description: Get details for a specific carbon emission record
  hints:
    idempotent: true
    readOnly: true
  name: get-carbon-emission
- description: Create a new carbon emission record (Scope 1, 2, or 3)
  hints:
    destructive: false
    readOnly: false
  name: create-carbon-emission
- description: Update an existing carbon emission record
  hints:
    idempotent: true
    readOnly: false
  name: update-carbon-emission
- description: Delete a carbon emission record
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-carbon-emission
- description: List sustainability goals including net zero targets and progress
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-sustainability-goals
- description: Create a new sustainability goal with baseline, target year, and reduction percentage
  hints:
    destructive: false
    readOnly: false
  name: create-sustainability-goal
- description: List emission factors used for CO2e calculations, filterable by category and region
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-emission-factors
- description: List energy consumption records by type (electricity, gas, renewable)
  hints:
    idempotent: true
    readOnly: true
  name: list-energy-consumption
- description: Create a new energy consumption record for a facility
  hints:
    destructive: false
    readOnly: false
  name: create-energy-consumption
- description: List waste disposal records by type and disposal method
  hints:
    idempotent: true
    readOnly: true
  name: list-waste-disposal-records
- description: Create a new waste disposal record (landfill, recycled, composted, etc.)
  hints:
    destructive: false
    readOnly: false
  name: create-waste-disposal-record
- description: List water withdrawal records by source
  hints:
    idempotent: true
    readOnly: true
  name: list-water-withdrawal-records
- description: Create a new water withdrawal record for a facility
  hints:
    destructive: false
    readOnly: false
  name: create-water-withdrawal-record
- description: Query any sustainability data using SOQL for advanced ESG reporting
  hints:
    idempotent: true
    readOnly: true
  name: query-sustainability-data
---
