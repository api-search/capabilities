---
api_specs:
- filename: wegowise-openapi.yml
  format: yaml
  label: wegowise
  slug: wegowise
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/wegowise/refs/heads/main/openapi/wegowise-openapi.yml
categories: []
consumed_apis:
- wegowise
description: Capability for building energy and water benchmarking using the WegoWise API. Enables property managers and energy service providers to assess portfolio performance, identify underperforming buildings, track conservation progress, and benchmark against peers. Combines building management with meter data retrieval for comprehensive energy analysis.
layout: capability
name: WegoWise Building Energy Benchmarking
operations:
- description: List all utility companies supported for data import
  method: GET
  name: list-utility-companies
  path: /v1/utility-companies
- description: List all buildings in the portfolio
  method: GET
  name: list-buildings
  path: /v1/buildings
- description: Get building details and metadata
  method: GET
  name: get-building
  path: /v1/buildings/{id}
- description: Get normalized monthly energy usage data for benchmarking
  method: GET
  name: get-building-energy-data
  path: /v1/buildings/{id}/energy-data
- description: List utility meters for a building
  method: GET
  name: list-building-meters
  path: /v1/buildings/{id}/meters
- description: List apartment units in a building
  method: GET
  name: list-apartments
  path: /v1/buildings/{id}/apartments
- description: Get raw utility datapoints for a meter
  method: GET
  name: get-meter-raw-data
  path: /v1/meters/{id}/data
- description: Get most recent meter reading
  method: GET
  name: get-latest-datum
  path: /v1/meters/{id}/latest
- description: List data-only meters
  method: GET
  name: list-data-meters
  path: /v1/data-meters
- description: Create a meter with utility credentials for automated import
  method: POST
  name: create-data-meter
  path: /v1/data-meters
personas: []
provider_name: WegoWise
provider_slug: wegowise
search_terms:
- manually add a utility usage datapoint to a meter
- building portfolio management
- create a meter connected to a utility company for automated data import
- get detailed information about a specific building including size and type
- get latest meter reading
- create data meter
- utility data
- property management
- multifamily
- list all utility companies supported for data import
- list buildings
- list data-only meters for automated utility data import
- get normalized monthly energy usage data for benchmarking
- create meter datapoint
- list utility meters for a building
- list apartments
- list data meters
- get building details and metadata
- get normalized monthly energy usage data for a building - use for benchmarking and trend analysis
- get the most recent utility reading for a meter
- energy efficiency
- get most recent meter reading
- list building meters
- list utility companies
- get latest datum
- building energy
- get building
- sustainability
- list data-only meters
- create a meter with utility credentials for automated import
- get raw utility datapoints for a meter
- list all apartment units within a building
- get raw utility usage datapoints for a meter including billing period data
- list apartment units in a building
- wegowise
- get building energy data
- list all buildings in the wegowise portfolio with metadata
- monthly energy and water usage data
- supported utility companies for automated data import
- list utility companies available for automated meter data import
- get meter raw data
- list all buildings in the portfolio
- benchmarking
- list all utility meters associated with a building
slug: building-energy-benchmarking
source_filename: building-energy-benchmarking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WegoWise Building Energy Benchmarking\"\n  description: >-\n    Capability for building energy and water benchmarking using the WegoWise API.\n    Enables property managers and energy service providers to assess portfolio\n    performance, identify underperforming buildings, track conservation progress,\n    and benchmark against peers. Combines building management with meter data\n    retrieval for comprehensive energy analysis.\n  tags:\n    - WegoWise\n    - Building Energy\n    - Benchmarking\n    - Energy Efficiency\n    - Property Management\n    - Sustainability\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WEGOWISE_OAUTH_KEY: WEGOWISE_OAUTH_KEY\n      WEGOWISE_OAUTH_SECRET: WEGOWISE_OAUTH_SECRET\n      WEGOWISE_TOKEN: WEGOWISE_TOKEN\n      WEGOWISE_TOKEN_SECRET: WEGOWISE_TOKEN_SECRET\n\ncapability:\n  consumes:\n    - import: wegowise\n      location: ./shared/wegowise.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: wegowise-benchmarking-api\n      description: \"Unified REST API for WegoWise building energy benchmarking.\"\n      resources:\n        - path: /v1/utility-companies\n          name: utility-companies\n          description: \"Supported utility companies for automated data import\"\n          operations:\n            - method: GET\n              name: list-utility-companies\n              description: \"List all utility companies supported for data import\"\n              call: \"wegowise.list-utility-companies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/buildings\n          name: buildings\n          description: \"Building portfolio management\"\n          operations:\n            - method: GET\n              name: list-buildings\n              description: \"List all buildings in the portfolio\"\n              call: \"wegowise.list-buildings\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/buildings/{id}\n          name: building\n          operations:\n            - method: GET\n              name: get-building\n              description: \"Get building details and metadata\"\n              call: \"wegowise.get-building\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/buildings/{id}/energy-data\n          name: building-energy-data\n          description: \"Monthly energy and water usage data\"\n          operations:\n            - method: GET\n              name: get-building-energy-data\n              description: \"Get normalized monthly energy usage data for benchmarking\"\n              call: \"wegowise.get-building-data\"\n              with:\n                id: \"rest.id\"\n                data_type: \"rest.data_type\"\
  \n                unit: \"rest.unit\"\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/buildings/{id}/meters\n          name: building-meters\n          operations:\n            - method: GET\n              name: list-building-meters\n              description: \"List utility meters for a building\"\n              call: \"wegowise.list-building-meters\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/buildings/{id}/apartments\n          name: building-apartments\n          operations:\n            - method: GET\n              name: list-apartments\n              description: \"List apartment units in a building\"\n              call: \"wegowise.list-apartments\"\n              with:\n         \
  \       id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/meters/{id}/data\n          name: meter-data\n          operations:\n            - method: GET\n              name: get-meter-raw-data\n              description: \"Get raw utility datapoints for a meter\"\n              call: \"wegowise.get-meter-raw-data\"\n              with:\n                id: \"rest.id\"\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/meters/{id}/latest\n          name: meter-latest\n          operations:\n            - method: GET\n              name: get-latest-datum\n              description: \"Get most recent meter reading\"\n              call: \"wegowise.get-latest-datum\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/data-meters\n          name: data-meters\n          operations:\n            - method: GET\n              name: list-data-meters\n              description: \"List data-only meters\"\n              call: \"wegowise.list-data-meters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-data-meter\n              description: \"Create a meter with utility credentials for automated import\"\n              call: \"wegowise.create-data-meter\"\n              with:\n                account_number: \"rest.account_number\"\n                utility_company_id: \"rest.utility_company_id\"\n                data_type: \"rest.data_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: wegowise-benchmarking-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted building energy benchmarking and analysis.\"\n      tools:\n        - name: list-utility-companies\n          description: \"List utility companies available for automated meter data import\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wegowise.list-utility-companies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-buildings\n          description: \"List all buildings in the WegoWise portfolio with metadata\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wegowise.list-buildings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-building\n          description: \"Get detailed information about a specific building including size and type\"\n          hints:\n            readOnly: true\n        \
  \  call: \"wegowise.get-building\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-building-energy-data\n          description: \"Get normalized monthly energy usage data for a building - use for benchmarking and trend analysis\"\n          hints:\n            readOnly: true\n          call: \"wegowise.get-building-data\"\n          with:\n            id: \"tools.id\"\n            data_type: \"tools.data_type\"\n            unit: \"tools.unit\"\n            start_date: \"tools.start_date\"\n            end_date: \"tools.end_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-building-meters\n          description: \"List all utility meters associated with a building\"\n          hints:\n            readOnly: true\n          call: \"wegowise.list-building-meters\"\n          with:\n            id: \"tools.id\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-apartments\n          description: \"List all apartment units within a building\"\n          hints:\n            readOnly: true\n          call: \"wegowise.list-apartments\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-meter-raw-data\n          description: \"Get raw utility usage datapoints for a meter including billing period data\"\n          hints:\n            readOnly: true\n          call: \"wegowise.get-meter-raw-data\"\n          with:\n            id: \"tools.id\"\n            start_date: \"tools.start_date\"\n            end_date: \"tools.end_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-latest-meter-reading\n          description: \"Get the most recent utility reading for a meter\"\n\
  \          hints:\n            readOnly: true\n          call: \"wegowise.get-latest-datum\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-meter-datapoint\n          description: \"Manually add a utility usage datapoint to a meter\"\n          hints:\n            readOnly: false\n          call: \"wegowise.create-meter-datapoint\"\n          with:\n            id: \"tools.id\"\n            start_date: \"tools.start_date\"\n            end_date: \"tools.end_date\"\n            total_charge: \"tools.total_charge\"\n            kwh: \"tools.kwh\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-data-meters\n          description: \"List data-only meters for automated utility data import\"\n          hints:\n            readOnly: true\n          call: \"wegowise.list-data-meters\"\n          outputParameters:\n   \
  \         - type: object\n              mapping: \"$.\"\n\n        - name: create-data-meter\n          description: \"Create a meter connected to a utility company for automated data import\"\n          hints:\n            readOnly: false\n          call: \"wegowise.create-data-meter\"\n          with:\n            account_number: \"tools.account_number\"\n            utility_company_id: \"tools.utility_company_id\"\n            data_type: \"tools.data_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/wegowise/refs/heads/main/capabilities/building-energy-benchmarking.yaml
tags:
- WegoWise
- Building Energy
- Benchmarking
- Energy Efficiency
- Property Management
- Sustainability
tools:
- description: List utility companies available for automated meter data import
  hints:
    openWorld: true
    readOnly: true
  name: list-utility-companies
- description: List all buildings in the WegoWise portfolio with metadata
  hints:
    openWorld: true
    readOnly: true
  name: list-buildings
- description: Get detailed information about a specific building including size and type
  hints:
    readOnly: true
  name: get-building
- description: Get normalized monthly energy usage data for a building - use for benchmarking and trend analysis
  hints:
    readOnly: true
  name: get-building-energy-data
- description: List all utility meters associated with a building
  hints:
    readOnly: true
  name: list-building-meters
- description: List all apartment units within a building
  hints:
    readOnly: true
  name: list-apartments
- description: Get raw utility usage datapoints for a meter including billing period data
  hints:
    readOnly: true
  name: get-meter-raw-data
- description: Get the most recent utility reading for a meter
  hints:
    readOnly: true
  name: get-latest-meter-reading
- description: Manually add a utility usage datapoint to a meter
  hints:
    readOnly: false
  name: create-meter-datapoint
- description: List data-only meters for automated utility data import
  hints:
    readOnly: true
  name: list-data-meters
- description: Create a meter connected to a utility company for automated data import
  hints:
    readOnly: false
  name: create-data-meter
---
