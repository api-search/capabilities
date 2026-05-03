---
categories: []
consumed_apis:
- cwms-data
description: Unified water data capability composing USACE CWMS Data API resources for water resource monitoring, flood forecasting, reservoir operations, and hydrological analysis. Used by water managers, flood forecasters, environmental engineers, and researchers accessing USACE real-time and historical water data.
layout: capability
name: USACE Water Data
operations:
- description: Get timeseries values for a monitored location and parameter
  method: GET
  name: get-timeseries
  path: /v1/timeseries
- description: List available CWMS timeseries identifiers
  method: GET
  name: list-timeseries
  path: /v1/timeseries/catalog
- description: List monitored water resource locations
  method: GET
  name: list-locations
  path: /v1/locations
- description: Get details for a specific monitored location
  method: GET
  name: get-location
  path: /v1/locations/{location-id}
- description: Retrieve rating tables for value conversion
  method: GET
  name: list-ratings
  path: /v1/ratings
- description: Get stage and elevation threshold levels
  method: GET
  name: list-levels
  path: /v1/levels
- description: List USACE reservoir projects and pool data
  method: GET
  name: list-reservoirs
  path: /v1/reservoirs
- description: List all USACE district offices
  method: GET
  name: list-offices
  path: /v1/offices
- description: Get catalog of available data by dataset type
  method: GET
  name: get-catalog
  path: /v1/catalog/{dataset}
personas: []
provider_name: US Army Corps of Engineers
provider_slug: us-army-corps-of-engineers
search_terms:
- get timeseries
- usace reservoir projects
- list available cwms timeseries identifiers
- open data
- retrieve rating tables for converting stage measurements to flow values
- list all usace district offices (lrn, swd, mvp, etc.)
- list available cwms timeseries identifiers for a given office
- water resources
- hydrological data
- list monitored water resource locations
- list usace offices
- retrieve real-time or historical streamflow timeseries data for a cwms location
- water management timeseries data (streamflow, stage, precipitation)
- military engineering
- federal government
- list reservoirs
- list offices
- list locations
- browse data catalog
- get flood stage levels
- list timeseries
- list all usace district offices
- reservoir operations
- flood forecasting
- get catalog of available data by dataset type
- usace district offices
- location level thresholds
- list levels
- get timeseries values for a monitored location and parameter
- browse available cwms data types (timeseries, locations, ratings, reservoirs)
- geospatial data
- catalog of available timeseries identifiers
- list cwms monitored locations (stream gages, reservoirs, weather stations)
- get details for a specific monitored location
- get streamflow data
- list usace reservoir projects and pool data
- get location details
- data catalog by dataset type
- get stage flow ratings
- get flood stage, conservation pool, and other threshold levels for locations
- single monitored location details
- list ratings
- get detailed information for a specific cwms monitored location
- list usace reservoir projects with storage and pool information
- get location
- cwms monitored locations
- stage-to-flow rating tables
- infrastructure
- get stage and elevation threshold levels
- retrieve rating tables for value conversion
- get catalog
slug: water-data
source_filename: water-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"USACE Water Data\"\n  description: >-\n    Unified water data capability composing USACE CWMS Data API resources for water resource\n    monitoring, flood forecasting, reservoir operations, and hydrological analysis. Used by\n    water managers, flood forecasters, environmental engineers, and researchers accessing\n    USACE real-time and historical water data.\n  tags:\n    - Water Resources\n    - Federal Government\n    - Flood Forecasting\n    - Reservoir Operations\n    - Hydrological Data\n    - Open Data\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\ncapability:\n  consumes:\n    - import: cwms-data\n      location: ./shared/cwms-data.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: water-data-api\n      description: \"Unified REST API for USACE water management data access.\"\n      resources:\n        - path: /v1/timeseries\n          name: timeseries\n          description: \"Water management\
  \ timeseries data (streamflow, stage, precipitation)\"\n          operations:\n            - method: GET\n              name: get-timeseries\n              description: \"Get timeseries values for a monitored location and parameter\"\n              call: \"cwms-data.get-timeseries\"\n              with:\n                name: \"rest.name\"\n                office: \"rest.office\"\n                unit: \"rest.unit\"\n                begin: \"rest.begin\"\n                end: \"rest.end\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/timeseries/catalog\n          name: timeseries-catalog\n          description: \"Catalog of available timeseries identifiers\"\n          operations:\n            - method: GET\n              name: list-timeseries\n              description: \"List available CWMS timeseries identifiers\"\n              call: \"cwms-data.get-timeseries-catalog\"\n              with:\n             \
  \   office: \"rest.office\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/locations\n          name: locations\n          description: \"CWMS monitored locations\"\n          operations:\n            - method: GET\n              name: list-locations\n              description: \"List monitored water resource locations\"\n              call: \"cwms-data.get-locations\"\n              with:\n                office: \"rest.office\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/locations/{location-id}\n          name: location\n          description: \"Single monitored location details\"\n          operations:\n            - method: GET\n              name: get-location\n              description: \"Get details for a specific monitored location\"\n              call: \"cwms-data.get-location\"\n              with:\n                location-id:\
  \ \"rest.location-id\"\n                office: \"rest.office\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ratings\n          name: ratings\n          description: \"Stage-to-flow rating tables\"\n          operations:\n            - method: GET\n              name: list-ratings\n              description: \"Retrieve rating tables for value conversion\"\n              call: \"cwms-data.get-ratings\"\n              with:\n                office: \"rest.office\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/levels\n          name: levels\n          description: \"Location level thresholds\"\n          operations:\n            - method: GET\n              name: list-levels\n              description: \"Get stage and elevation threshold levels\"\n              call: \"cwms-data.get-levels\"\n              with:\n                office:\
  \ \"rest.office\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/reservoirs\n          name: reservoirs\n          description: \"USACE reservoir projects\"\n          operations:\n            - method: GET\n              name: list-reservoirs\n              description: \"List USACE reservoir projects and pool data\"\n              call: \"cwms-data.get-reservoirs\"\n              with:\n                office: \"rest.office\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/offices\n          name: offices\n          description: \"USACE district offices\"\n          operations:\n            - method: GET\n              name: list-offices\n              description: \"List all USACE district offices\"\n              call: \"cwms-data.get-offices\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n        - path: /v1/catalog/{dataset}\n          name: catalog\n          description: \"Data catalog by dataset type\"\n          operations:\n            - method: GET\n              name: get-catalog\n              description: \"Get catalog of available data by dataset type\"\n              call: \"cwms-data.get-catalog\"\n              with:\n                dataset: \"rest.dataset\"\n                office: \"rest.office\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: water-data-mcp\n      transport: http\n      description: \"MCP server for AI-assisted USACE water resource data access and analysis.\"\n      tools:\n        - name: get-streamflow-data\n          description: \"Retrieve real-time or historical streamflow timeseries data for a CWMS location\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms-data.get-timeseries\"\
  \n          with:\n            name: \"tools.name\"\n            office: \"tools.office\"\n            unit: \"tools.unit\"\n            begin: \"tools.begin\"\n            end: \"tools.end\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-timeseries\n          description: \"List available CWMS timeseries identifiers for a given office\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms-data.get-timeseries-catalog\"\n          with:\n            office: \"tools.office\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-locations\n          description: \"List CWMS monitored locations (stream gages, reservoirs, weather stations)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms-data.get-locations\"\n          with:\n            office: \"tools.office\"\n         \
  \ outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-location-details\n          description: \"Get detailed information for a specific CWMS monitored location\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms-data.get-location\"\n          with:\n            location-id: \"tools.location-id\"\n            office: \"tools.office\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-stage-flow-ratings\n          description: \"Retrieve rating tables for converting stage measurements to flow values\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms-data.get-ratings\"\n          with:\n            office: \"tools.office\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-flood-stage-levels\n          description: \"Get flood\
  \ stage, conservation pool, and other threshold levels for locations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms-data.get-levels\"\n          with:\n            office: \"tools.office\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-reservoirs\n          description: \"List USACE reservoir projects with storage and pool information\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms-data.get-reservoirs\"\n          with:\n            office: \"tools.office\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-usace-offices\n          description: \"List all USACE district offices (LRN, SWD, MVP, etc.)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms-data.get-offices\"\n          outputParameters:\n         \
  \   - type: object\n              mapping: \"$.\"\n\n        - name: browse-data-catalog\n          description: \"Browse available CWMS data types (TIMESERIES, LOCATIONS, RATINGS, RESERVOIRS)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms-data.get-catalog\"\n          with:\n            dataset: \"tools.dataset\"\n            office: \"tools.office\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/us-army-corps-of-engineers/refs/heads/main/capabilities/water-data.yaml
tags:
- Water Resources
- Federal Government
- Flood Forecasting
- Reservoir Operations
- Hydrological Data
- Open Data
tools:
- description: Retrieve real-time or historical streamflow timeseries data for a CWMS location
  hints:
    openWorld: true
    readOnly: true
  name: get-streamflow-data
- description: List available CWMS timeseries identifiers for a given office
  hints:
    openWorld: true
    readOnly: true
  name: list-timeseries
- description: List CWMS monitored locations (stream gages, reservoirs, weather stations)
  hints:
    openWorld: true
    readOnly: true
  name: list-locations
- description: Get detailed information for a specific CWMS monitored location
  hints:
    openWorld: true
    readOnly: true
  name: get-location-details
- description: Retrieve rating tables for converting stage measurements to flow values
  hints:
    openWorld: true
    readOnly: true
  name: get-stage-flow-ratings
- description: Get flood stage, conservation pool, and other threshold levels for locations
  hints:
    openWorld: true
    readOnly: true
  name: get-flood-stage-levels
- description: List USACE reservoir projects with storage and pool information
  hints:
    openWorld: true
    readOnly: true
  name: list-reservoirs
- description: List all USACE district offices (LRN, SWD, MVP, etc.)
  hints:
    openWorld: true
    readOnly: true
  name: list-usace-offices
- description: Browse available CWMS data types (TIMESERIES, LOCATIONS, RATINGS, RESERVOIRS)
  hints:
    openWorld: true
    readOnly: true
  name: browse-data-catalog
---
