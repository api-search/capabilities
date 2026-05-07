---
categories: []
consumed_apis: []
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
- update a carbon emission record
- create a new waste disposal record (landfill, recycled, composted, etc.)
- list energy consumption records
- list emission factors
- create water withdrawal
- list carbon emissions
- delete a carbon emission record
- get carbon emission
- create a new sustainability goal with baseline, target year, and reduction percentage
- list water withdrawal records
- update carbon emission
- create sustainability goal
- create waste disposal record
- create energy consumption
- carbon accounting
- list sustainability goals
- create a waste disposal record
- create a sustainability goal
- water withdrawal and consumption tracking
- create a water withdrawal record
- create a new energy consumption record for a facility
- create a new water withdrawal record for a facility
- list carbon emission records with optional scope and year filters
- create an energy consumption record
- get details for a specific carbon emission record
- carbon emissions
- query any sustainability data using soql for advanced esg reporting
- create waste disposal
- list energy consumption records by type (electricity, gas, renewable)
- delete carbon emission
- list waste disposal
- list water withdrawal
- update an existing carbon emission record
- esg
- net zero and sustainability goal management
- create a new carbon emission record
- list water withdrawal records by source
- climate
- emission factor catalog
- list waste disposal records by type and disposal method
- create water withdrawal record
- carbon emission record management (scope 1, 2, 3)
- get a specific carbon emission record
- sustainability
- list emission factors used for co2e calculations, filterable by category and region
- environmental
- create a new carbon emission record (scope 1, 2, or 3)
- list energy consumption
- list waste disposal records
- create carbon emission
- list sustainability goals including net zero targets and progress
- net zero
- individual emission record operations
- waste disposal tracking
- energy consumption tracking
- query sustainability data
- net zero cloud
- list carbon emission records filtered by scope and reporting year
- salesforce
slug: carbon-accounting
source_filename: carbon-accounting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesforce Net Zero Cloud Carbon Accounting\n  description: Unified workflow capability for carbon accounting and ESG reporting in Salesforce Net Zero Cloud. Combines\n    carbon emission tracking, energy consumption monitoring, sustainability goal management, and environmental data reporting\n    for sustainability teams.\n  tags:\n  - Salesforce\n  - Net Zero Cloud\n  - Carbon Accounting\n  - ESG\n  - Sustainability\n  - Climate\n  - Environmental\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: salesforce-net-zero\n    baseUri: https://{instance}.my.salesforce.com/services/data/v59.0\n    description: Salesforce Net Zero Cloud REST API\n    authentication:\n      type: bearer\n      token: '{{SALESFORCE_ACCESS_TOKEN}}'\n    resources:\n    - name: carbon-emissions\n      path: /sobjects/CarbonEmission\n\
  \      description: Carbon emission record management\n      operations:\n      - name: list-carbon-emissions\n        method: GET\n        description: List all carbon emission records\n        inputParameters:\n        - name: scope\n          in: query\n          type: integer\n          required: false\n          description: Filter by emission scope (1, 2, 3)\n        - name: reportingYear\n          in: query\n          type: integer\n          required: false\n          description: Filter by reporting year\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-carbon-emission\n        method: POST\n        description: Create a new carbon emission record\n        body:\n          type: json\n          data:\n            Scope: '{{tools.scope}}'\n            EmissionSource: '{{tools.emissionSource}}'\n            QuantityMtCO2e: '{{tools.quantityMtCO2e}}'\n            ReportingYear: '{{tools.reportingYear}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carbon-emission\n      path: /sobjects/CarbonEmission/{emissionId}\n      description: Individual carbon emission operations\n      operations:\n      - name: get-carbon-emission\n        method: GET\n        description: Get a specific carbon emission record\n        inputParameters:\n        - name: emissionId\n          in: path\n          type: string\n          required: true\n          description: Salesforce ID of the emission record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-carbon-emission\n        method: PATCH\n        description: Update a carbon emission record\n        inputParameters:\n        - name: emissionId\n          in: path\n          type: string\n          required: true\n          description: Salesforce ID of the emission\
  \ record\n        body:\n          type: json\n          data:\n            QuantityMtCO2e: '{{tools.quantityMtCO2e}}'\n            Description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-carbon-emission\n        method: DELETE\n        description: Delete a carbon emission record\n        inputParameters:\n        - name: emissionId\n          in: path\n          type: string\n          required: true\n          description: Salesforce ID of the emission record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: energy-consumption\n      path: /sobjects/EnergyConsumption\n      description: Energy consumption record management\n      operations:\n      - name: list-energy-consumption\n        method: GET\n        description: List energy consumption records\n        inputParameters:\n\
  \        - name: energyType\n          in: query\n          type: string\n          required: false\n          description: Filter by energy type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-energy-consumption\n        method: POST\n        description: Create an energy consumption record\n        body:\n          type: json\n          data:\n            EnergyType: '{{tools.energyType}}'\n            QuantityKWh: '{{tools.quantityKWh}}'\n            ReportingYear: '{{tools.reportingYear}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: energy-consumption-record\n      path: /sobjects/EnergyConsumption/{consumptionId}\n      description: Individual energy consumption record\n      operations:\n      - name: get-energy-consumption\n        method: GET\n        description: Get a specific energy\
  \ consumption record\n        inputParameters:\n        - name: consumptionId\n          in: path\n          type: string\n          required: true\n          description: Salesforce ID of the energy record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sustainability-goals\n      path: /sobjects/SustainabilityGoal\n      description: Sustainability goal management\n      operations:\n      - name: list-sustainability-goals\n        method: GET\n        description: List sustainability goals and net zero targets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-sustainability-goal\n        method: POST\n        description: Create a sustainability goal\n        body:\n          type: json\n          data:\n            GoalType: '{{tools.goalType}}'\n            BaselineYear: '{{tools.baselineYear}}'\n\
  \            TargetYear: '{{tools.targetYear}}'\n            ReductionTargetPercentage: '{{tools.reductionTargetPercentage}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: emission-factors\n      path: /sobjects/EmissionFactor\n      description: Emission factor catalog\n      operations:\n      - name: list-emission-factors\n        method: GET\n        description: List emission factors for calculations\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter by category\n        - name: region\n          in: query\n          type: string\n          required: false\n          description: Filter by region\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: waste-disposal\n      path: /sobjects/WasteDisposal\n\
  \      description: Waste disposal record management\n      operations:\n      - name: list-waste-disposal-records\n        method: GET\n        description: List waste disposal records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-waste-disposal-record\n        method: POST\n        description: Create a waste disposal record\n        body:\n          type: json\n          data:\n            WasteType: '{{tools.wasteType}}'\n            DisposalMethod: '{{tools.disposalMethod}}'\n            QuantityKg: '{{tools.quantityKg}}'\n            ReportingYear: '{{tools.reportingYear}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: water-withdrawal\n      path: /sobjects/WaterWithdrawal\n      description: Water withdrawal record management\n      operations:\n      - name: list-water-withdrawal-records\n\
  \        method: GET\n        description: List water withdrawal records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-water-withdrawal-record\n        method: POST\n        description: Create a water withdrawal record\n        body:\n          type: json\n          data:\n            WaterSource: '{{tools.waterSource}}'\n            QuantityCubicMeters: '{{tools.quantityCubicMeters}}'\n            ReportingYear: '{{tools.reportingYear}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sustainability-query\n      path: /query\n      description: SOQL query for sustainability data\n      operations:\n      - name: query-sustainability-data\n        method: GET\n        description: Query sustainability data with SOQL\n        inputParameters:\n        - name: q\n          in: query\n          type:\
  \ string\n          required: true\n          description: SOQL query string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: carbon-accounting-api\n    description: Unified REST API for carbon accounting and ESG reporting.\n    resources:\n    - path: /v1/emissions\n      name: carbon-emissions\n      description: Carbon emission record management (Scope 1, 2, 3)\n      operations:\n      - method: GET\n        name: list-carbon-emissions\n        description: List carbon emission records with optional scope and year filters\n        call: salesforce-net-zero.list-carbon-emissions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-carbon-emission\n        description: Create a new carbon emission record\n        call: salesforce-net-zero.create-carbon-emission\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/emissions/{emissionId}\n      name: carbon-emission\n      description: Individual emission record operations\n      operations:\n      - method: GET\n        name: get-carbon-emission\n        description: Get a specific carbon emission record\n        call: salesforce-net-zero.get-carbon-emission\n        with:\n          emissionId: rest.emissionId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-carbon-emission\n        description: Update a carbon emission record\n        call: salesforce-net-zero.update-carbon-emission\n        with:\n          emissionId: rest.emissionId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-carbon-emission\n        description: Delete a carbon emission record\n        call: salesforce-net-zero.delete-carbon-emission\n        with:\n          emissionId:\
  \ rest.emissionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/energy\n      name: energy-consumption\n      description: Energy consumption tracking\n      operations:\n      - method: GET\n        name: list-energy-consumption\n        description: List energy consumption records\n        call: salesforce-net-zero.list-energy-consumption\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-energy-consumption\n        description: Create an energy consumption record\n        call: salesforce-net-zero.create-energy-consumption\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/goals\n      name: sustainability-goals\n      description: Net zero and sustainability goal management\n      operations:\n      - method: GET\n        name: list-sustainability-goals\n        description: List sustainability goals\n        call: salesforce-net-zero.list-sustainability-goals\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-sustainability-goal\n        description: Create a sustainability goal\n        call: salesforce-net-zero.create-sustainability-goal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/emission-factors\n      name: emission-factors\n      description: Emission factor catalog\n      operations:\n      - method: GET\n        name: list-emission-factors\n        description: List emission factors\n        call: salesforce-net-zero.list-emission-factors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/waste\n      name: waste-disposal\n      description: Waste disposal tracking\n      operations:\n      - method: GET\n        name: list-waste-disposal\n        description: List waste disposal records\n        call: salesforce-net-zero.list-waste-disposal-records\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n      - method: POST\n        name: create-waste-disposal\n        description: Create a waste disposal record\n        call: salesforce-net-zero.create-waste-disposal-record\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/water\n      name: water-usage\n      description: Water withdrawal and consumption tracking\n      operations:\n      - method: GET\n        name: list-water-withdrawal\n        description: List water withdrawal records\n        call: salesforce-net-zero.list-water-withdrawal-records\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-water-withdrawal\n        description: Create a water withdrawal record\n        call: salesforce-net-zero.create-water-withdrawal-record\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: carbon-accounting-mcp\n \
  \   transport: http\n    description: MCP server for AI-assisted carbon accounting and ESG reporting.\n    tools:\n    - name: list-carbon-emissions\n      description: List carbon emission records filtered by scope and reporting year\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: salesforce-net-zero.list-carbon-emissions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-carbon-emission\n      description: Get details for a specific carbon emission record\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-net-zero.get-carbon-emission\n      with:\n        emissionId: tools.emissionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-carbon-emission\n      description: Create a new carbon emission record (Scope 1, 2, or 3)\n      hints:\n        readOnly: false\n        destructive: false\n      call: salesforce-net-zero.create-carbon-emission\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-carbon-emission\n      description: Update an existing carbon emission record\n      hints:\n        readOnly: false\n        idempotent: true\n      call: salesforce-net-zero.update-carbon-emission\n      with:\n        emissionId: tools.emissionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-carbon-emission\n      description: Delete a carbon emission record\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: salesforce-net-zero.delete-carbon-emission\n      with:\n        emissionId: tools.emissionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sustainability-goals\n      description: List sustainability goals including net zero targets and progress\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: salesforce-net-zero.list-sustainability-goals\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-sustainability-goal\n      description: Create a new sustainability goal with baseline, target year, and reduction percentage\n      hints:\n        readOnly: false\n        destructive: false\n      call: salesforce-net-zero.create-sustainability-goal\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-emission-factors\n      description: List emission factors used for CO2e calculations, filterable by category and region\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: salesforce-net-zero.list-emission-factors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-energy-consumption\n      description: List energy consumption records by type (electricity, gas, renewable)\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-net-zero.list-energy-consumption\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-energy-consumption\n      description: Create a new energy consumption record for a facility\n      hints:\n        readOnly: false\n        destructive: false\n      call: salesforce-net-zero.create-energy-consumption\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-waste-disposal-records\n      description: List waste disposal records by type and disposal method\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-net-zero.list-waste-disposal-records\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-waste-disposal-record\n      description: Create a new waste disposal record (landfill, recycled, composted, etc.)\n      hints:\n        readOnly: false\n        destructive: false\n      call: salesforce-net-zero.create-waste-disposal-record\n      outputParameters:\n      - type: object\n  \
  \      mapping: $.\n    - name: list-water-withdrawal-records\n      description: List water withdrawal records by source\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-net-zero.list-water-withdrawal-records\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-water-withdrawal-record\n      description: Create a new water withdrawal record for a facility\n      hints:\n        readOnly: false\n        destructive: false\n      call: salesforce-net-zero.create-water-withdrawal-record\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-sustainability-data\n      description: Query any sustainability data using SOQL for advanced ESG reporting\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-net-zero.query-sustainability-data\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
