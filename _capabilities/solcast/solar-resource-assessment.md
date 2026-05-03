---
api_specs:
- filename: solcast-openapi.yml
  format: yaml
  label: solcast
  slug: solcast
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/solcast/refs/heads/main/openapi/solcast-openapi.yml
categories: []
consumed_apis:
- solcast
description: Workflow capability for solar resource assessment, project financing, and long-term yield analysis. Combines historical irradiance, rooftop and advanced PV power histories, TMY data, historical soiling models, and PV site management. Used by project developers, asset managers, banks, and energy consultants performing bankable resource assessments and yield studies.
layout: capability
name: Solcast Solar Resource Assessment
operations:
- description: Get historical irradiance and weather for up to 31 days at a time.
  method: GET
  name: get-historic-radiation-and-weather
  path: /v1/historic/radiation-and-weather
- description: Get historical rooftop PV power estimated actuals for a location.
  method: GET
  name: get-historic-rooftop-pv-power
  path: /v1/historic/rooftop-pv-power
- description: Get historical advanced PV power actuals for a registered site.
  method: GET
  name: get-historic-advanced-pv-power
  path: /v1/historic/advanced-pv-power
- description: Get historical soiling loss using the Kimber model.
  method: GET
  name: get-historic-soiling-kimber
  path: /v1/historic/soiling
- description: Get TMY irradiance and weather for a location.
  method: GET
  name: get-tmy-radiation-and-weather
  path: /v1/tmy/radiation-and-weather
- description: Get TMY rooftop PV power data for a location.
  method: GET
  name: get-tmy-rooftop-pv-power
  path: /v1/tmy/rooftop-pv-power
- description: List all registered PV power sites.
  method: GET
  name: list-pv-power-sites
  path: /v1/pv-power-sites
- description: Create a new PV power site.
  method: POST
  name: create-pv-power-site
  path: /v1/pv-power-sites
- description: Get a specific PV power site.
  method: GET
  name: get-pv-power-site
  path: /v1/pv-power-sites/{resource_id}
- description: Partially update a PV power site.
  method: PATCH
  name: patch-pv-power-site
  path: /v1/pv-power-sites/{resource_id}
- description: Fully overwrite a PV power site.
  method: PUT
  name: update-pv-power-site
  path: /v1/pv-power-sites/{resource_id}
- description: Delete a PV power site.
  method: DELETE
  name: delete-pv-power-site
  path: /v1/pv-power-sites/{resource_id}
personas: []
provider_name: Solcast
provider_slug: solcast
search_terms:
- update pv power site
- permanently delete a registered pv power site.
- project finance
- get historic soiling kimber
- get historical soiling loss estimates using the hsu model.
- renewable energy
- get historical rooftop pv power estimated actuals for a location.
- get historical irradiance and weather for up to 31 days at a time.
- tmy
- get tmy irradiance and weather for a location.
- partially update a pv power site.
- delete pv power site
- list pv power sites
- get historic soiling hsu
- get historic rooftop pv power
- get historical advanced pv power actuals for a registered site. use for detailed yield analysis with site-specific pv model.
- get typical meteorological year irradiance and weather (2007-2023). use for long-run average yield studies and project feasibility.
- list all registered pv power sites for this account.
- delete a pv power site.
- historical soiling loss data using kimber or hsu models.
- get tmy radiation and weather
- manage registered pv power sites for advanced model access.
- get historic advanced pv power
- get historical advanced pv power actuals for a registered site.
- resource assessment
- get historical soiling loss estimates using the kimber model. use for yield loss analysis and cleaning schedule optimization.
- get specifications for a specific registered pv power site.
- solar
- partially update an existing pv power site's specifications (e.g., update capacity or tilt after hardware changes).
- individual pv power site management.
- energy
- typical meteorological year rooftop pv power (2007-2023).
- get historical rooftop pv power estimated actuals from 2007 onwards. use for yield analysis and performance benchmarking.
- historical rooftop pv power data from 2007 onwards.
- get historical soiling loss using the kimber model.
- pv power
- soiling
- get tmy rooftop pv power
- get typical meteorological year rooftop pv power data (2007-2023). use for annual yield estimation and project financing.
- patch pv power site
- register a new pv power site with solcast for advanced pv power model access. requires site name, latitude, and longitude.
- fully replace an existing pv power site's specifications.
- irradiance
- fully overwrite a pv power site.
- get pv power site
- get a specific pv power site.
- typical meteorological year irradiance and weather (2007-2023).
- create pv power site
- historical data
- get historic radiation and weather
- historical advanced pv power data for registered sites.
- get tmy rooftop pv power data for a location.
- forecasting
- list all registered pv power sites.
- historical irradiance and weather data from 2007 onwards.
- weather
- yield analysis
- create a new pv power site.
- get historical solar irradiance and weather from 2007 to 7 days before present (up to 31 days per call). use for bankable resource assessment and p50/p90 yield studies.
slug: solar-resource-assessment
source_filename: solar-resource-assessment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Solcast Solar Resource Assessment\"\n  description: >-\n    Workflow capability for solar resource assessment, project financing, and\n    long-term yield analysis. Combines historical irradiance, rooftop and advanced\n    PV power histories, TMY data, historical soiling models, and PV site management.\n    Used by project developers, asset managers, banks, and energy consultants performing\n    bankable resource assessments and yield studies.\n  tags:\n    - Solar\n    - Resource Assessment\n    - Historical Data\n    - TMY\n    - PV Power\n    - Soiling\n    - Project Finance\n    - Yield Analysis\n    - Renewable Energy\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SOLCAST_API_KEY: SOLCAST_API_KEY\n\ncapability:\n  consumes:\n    - import: solcast\n      location: ./shared/solcast.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: solar-resource-assessment-api\n\
  \      description: \"Unified REST API for solar resource assessment and long-term yield analysis.\"\n      resources:\n        - path: /v1/historic/radiation-and-weather\n          name: historic-radiation-and-weather\n          description: \"Historical irradiance and weather data from 2007 onwards.\"\n          operations:\n            - method: GET\n              name: get-historic-radiation-and-weather\n              description: \"Get historical irradiance and weather for up to 31 days at a time.\"\n              call: \"solcast.get-historic-radiation-and-weather\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n                start: \"rest.start\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/historic/rooftop-pv-power\n          name: historic-rooftop-pv-power\n          description: \"Historical rooftop PV power data from 2007 onwards.\"\
  \n          operations:\n            - method: GET\n              name: get-historic-rooftop-pv-power\n              description: \"Get historical rooftop PV power estimated actuals for a location.\"\n              call: \"solcast.get-historic-rooftop-pv-power\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n                start: \"rest.start\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/historic/advanced-pv-power\n          name: historic-advanced-pv-power\n          description: \"Historical advanced PV power data for registered sites.\"\n          operations:\n            - method: GET\n              name: get-historic-advanced-pv-power\n              description: \"Get historical advanced PV power actuals for a registered site.\"\n              call: \"solcast.get-historic-advanced-pv-power\"\n              with:\n                resource_id:\
  \ \"rest.resource_id\"\n                start: \"rest.start\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/historic/soiling\n          name: historic-soiling\n          description: \"Historical soiling loss data using Kimber or HSU models.\"\n          operations:\n            - method: GET\n              name: get-historic-soiling-kimber\n              description: \"Get historical soiling loss using the Kimber model.\"\n              call: \"solcast.get-historic-soiling-kimber\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n                start: \"rest.start\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tmy/radiation-and-weather\n          name: tmy-radiation-and-weather\n          description: \"Typical Meteorological Year irradiance and weather (2007-2023).\"\
  \n          operations:\n            - method: GET\n              name: get-tmy-radiation-and-weather\n              description: \"Get TMY irradiance and weather for a location.\"\n              call: \"solcast.get-tmy-radiation-and-weather\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tmy/rooftop-pv-power\n          name: tmy-rooftop-pv-power\n          description: \"Typical Meteorological Year rooftop PV power (2007-2023).\"\n          operations:\n            - method: GET\n              name: get-tmy-rooftop-pv-power\n              description: \"Get TMY rooftop PV power data for a location.\"\n              call: \"solcast.get-tmy-rooftop-pv-power\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pv-power-sites\n          name: pv-power-sites\n          description: \"Manage registered PV power sites for advanced model access.\"\n          operations:\n            - method: GET\n              name: list-pv-power-sites\n              description: \"List all registered PV power sites.\"\n              call: \"solcast.list-pv-power-sites\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-pv-power-site\n              description: \"Create a new PV power site.\"\n              call: \"solcast.create-pv-power-site\"\n              with:\n                name: \"rest.name\"\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pv-power-sites/{resource_id}\n\
  \          name: pv-power-site\n          description: \"Individual PV power site management.\"\n          operations:\n            - method: GET\n              name: get-pv-power-site\n              description: \"Get a specific PV power site.\"\n              call: \"solcast.get-pv-power-site\"\n              with:\n                resource_id: \"rest.resource_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: PATCH\n              name: patch-pv-power-site\n              description: \"Partially update a PV power site.\"\n              call: \"solcast.patch-pv-power-site\"\n              with:\n                resource_id: \"rest.resource_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: PUT\n              name: update-pv-power-site\n              description: \"Fully overwrite a PV power site.\"\n              call: \"solcast.update-pv-power-site\"\
  \n              with:\n                resource_id: \"rest.resource_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: DELETE\n              name: delete-pv-power-site\n              description: \"Delete a PV power site.\"\n              call: \"solcast.delete-pv-power-site\"\n              with:\n                resource_id: \"rest.resource_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: solar-resource-assessment-mcp\n      transport: http\n      description: \"MCP server for AI-assisted solar resource assessment and long-term yield analysis.\"\n      tools:\n        - name: get-historic-radiation-and-weather\n          description: \"Get historical solar irradiance and weather from 2007 to 7 days before present (up to 31 days per call). Use for bankable resource assessment and P50/P90 yield studies.\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-historic-radiation-and-weather\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            start: \"tools.start\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-historic-rooftop-pv-power\n          description: \"Get historical rooftop PV power estimated actuals from 2007 onwards. Use for yield analysis and performance benchmarking.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-historic-rooftop-pv-power\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            start: \"tools.start\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-historic-advanced-pv-power\n          description:\
  \ \"Get historical advanced PV power actuals for a registered site. Use for detailed yield analysis with site-specific PV model.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-historic-advanced-pv-power\"\n          with:\n            resource_id: \"tools.resource_id\"\n            start: \"tools.start\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-historic-soiling-kimber\n          description: \"Get historical soiling loss estimates using the Kimber model. Use for yield loss analysis and cleaning schedule optimization.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-historic-soiling-kimber\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            start: \"tools.start\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: get-historic-soiling-hsu\n          description: \"Get historical soiling loss estimates using the HSU model.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-historic-soiling-hsu\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            start: \"tools.start\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-tmy-radiation-and-weather\n          description: \"Get Typical Meteorological Year irradiance and weather (2007-2023). Use for long-run average yield studies and project feasibility.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-tmy-radiation-and-weather\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: get-tmy-rooftop-pv-power\n          description: \"Get Typical Meteorological Year rooftop PV power data (2007-2023). Use for annual yield estimation and project financing.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-tmy-rooftop-pv-power\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-pv-power-sites\n          description: \"List all registered PV power sites for this account.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"solcast.list-pv-power-sites\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-pv-power-site\n          description: \"Get specifications for a specific registered PV power site.\"\
  \n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"solcast.get-pv-power-site\"\n          with:\n            resource_id: \"tools.resource_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-pv-power-site\n          description: \"Register a new PV power site with Solcast for advanced PV power model access. Requires site name, latitude, and longitude.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"solcast.create-pv-power-site\"\n          with:\n            name: \"tools.name\"\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            capacity: \"tools.capacity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: patch-pv-power-site\n          description: \"Partially update an existing PV power site's\
  \ specifications (e.g., update capacity or tilt after hardware changes).\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"solcast.patch-pv-power-site\"\n          with:\n            resource_id: \"tools.resource_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-pv-power-site\n          description: \"Fully replace an existing PV power site's specifications.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"solcast.update-pv-power-site\"\n          with:\n            resource_id: \"tools.resource_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-pv-power-site\n          description: \"Permanently delete a registered PV power site.\"\n          hints:\n            readOnly: false\n            destructive:\
  \ true\n            idempotent: true\n          call: \"solcast.delete-pv-power-site\"\n          with:\n            resource_id: \"tools.resource_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/solcast/refs/heads/main/capabilities/solar-resource-assessment.yaml
tags:
- Solar
- Resource Assessment
- Historical Data
- TMY
- PV Power
- Soiling
- Project Finance
- Yield Analysis
- Renewable Energy
tools:
- description: Get historical solar irradiance and weather from 2007 to 7 days before present (up to 31 days per call). Use for bankable resource assessment and P50/P90 yield studies.
  hints:
    openWorld: true
    readOnly: true
  name: get-historic-radiation-and-weather
- description: Get historical rooftop PV power estimated actuals from 2007 onwards. Use for yield analysis and performance benchmarking.
  hints:
    openWorld: true
    readOnly: true
  name: get-historic-rooftop-pv-power
- description: Get historical advanced PV power actuals for a registered site. Use for detailed yield analysis with site-specific PV model.
  hints:
    openWorld: true
    readOnly: true
  name: get-historic-advanced-pv-power
- description: Get historical soiling loss estimates using the Kimber model. Use for yield loss analysis and cleaning schedule optimization.
  hints:
    openWorld: true
    readOnly: true
  name: get-historic-soiling-kimber
- description: Get historical soiling loss estimates using the HSU model.
  hints:
    openWorld: true
    readOnly: true
  name: get-historic-soiling-hsu
- description: Get Typical Meteorological Year irradiance and weather (2007-2023). Use for long-run average yield studies and project feasibility.
  hints:
    openWorld: true
    readOnly: true
  name: get-tmy-radiation-and-weather
- description: Get Typical Meteorological Year rooftop PV power data (2007-2023). Use for annual yield estimation and project financing.
  hints:
    openWorld: true
    readOnly: true
  name: get-tmy-rooftop-pv-power
- description: List all registered PV power sites for this account.
  hints:
    openWorld: false
    readOnly: true
  name: list-pv-power-sites
- description: Get specifications for a specific registered PV power site.
  hints:
    openWorld: false
    readOnly: true
  name: get-pv-power-site
- description: Register a new PV power site with Solcast for advanced PV power model access. Requires site name, latitude, and longitude.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-pv-power-site
- description: Partially update an existing PV power site's specifications (e.g., update capacity or tilt after hardware changes).
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: patch-pv-power-site
- description: Fully replace an existing PV power site's specifications.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-pv-power-site
- description: Permanently delete a registered PV power site.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-pv-power-site
---
