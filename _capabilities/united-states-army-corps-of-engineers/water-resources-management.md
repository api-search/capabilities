---
api_specs:
- filename: cwms-data-api-openapi.yml
  format: yaml
  label: cwms
  slug: cwms
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/united-states-army-corps-of-engineers/refs/heads/main/openapi/cwms-data-api-openapi.yml
categories: []
consumed_apis:
- cwms
description: Unified workflow capability for accessing U.S. Army Corps of Engineers water resource data. Combines location discovery, real-time time series measurements, hydrological forecasts, and project information for water management, flood monitoring, and operational decision support.
layout: capability
name: USACE Water Resources Management
operations:
- description: Browse available time series, locations, or ratings in CWMS
  method: GET
  name: get-catalog
  path: /v1/catalog
- description: Get all USACE locations filtered by office or name pattern
  method: GET
  name: get-locations
  path: /v1/locations
- description: Get detailed data for a specific USACE location
  method: GET
  name: get-location
  path: /v1/locations/{location-id}
- description: Get time series data for a location (stage, flow, elevation, etc.)
  method: GET
  name: get-timeseries
  path: /v1/timeseries
- description: Get the most recent readings for current conditions monitoring
  method: GET
  name: get-recent-timeseries
  path: /v1/timeseries/recent
- description: Get location levels for flood stage and pool elevation thresholds
  method: GET
  name: get-levels
  path: /v1/levels
- description: Get rating tables for converting stage to flow
  method: GET
  name: get-ratings
  path: /v1/ratings
- description: Get hydrological forecast instances
  method: GET
  name: get-forecast-instances
  path: /v1/forecasts
- description: Get USACE projects including dams, locks, and reservoirs
  method: GET
  name: get-projects
  path: /v1/projects
- description: Get river basin information for USACE water management areas
  method: GET
  name: get-basins
  path: /v1/basins
personas: []
provider_name: United States Army Corps of Engineers
provider_slug: united-states-army-corps-of-engineers
search_terms:
- browse available cwms water data catalog
- get river basin information for usace water management areas
- federal government
- get forecast instances
- search usace locations
- get catalog
- browse water data catalog
- get location
- get usace projects including dams, locks, and reservoirs
- search for usace-managed locations (dams, reservoirs, stream gages) by name, office, or region
- get hydrological forecast instances
- get levels
- hydrological forecasts
- water management
- get hydrological forecasts for usace project areas including flood predictions and reservoir operations
- cwms time series measurements
- get rating tables for converting stage to flow
- get hydrological forecasts
- get flood stage levels
- water resources
- get current water conditions
- get detailed data for a specific usace location
- get location details
- browse the cwms data catalog to discover available time series, locations, and ratings for usace water resources
- usace-managed location data
- engineering
- flood monitoring
- get usace projects
- single usace location
- usace
- get recent timeseries
- usace water resource projects
- get the most recent real-time water condition readings for usace monitoring stations
- river basin information
- civil engineering
- get flood stage thresholds and normal pool levels for usace locations
- dam operations
- stage-discharge rating tables
- location levels (flood stage, normal pool)
- get location levels for flood stage and pool elevation thresholds
- get detailed information for a specific usace location including coordinates, elevation, and type
- browse available time series, locations, or ratings in cwms
- get the most recent readings for current conditions monitoring
- get locations
- get all usace locations filtered by office or name pattern
- get timeseries
- hydrology
- get projects
- get time series data for a location (stage, flow, elevation, etc.)
- get ratings
- get rating curves that convert stage height to streamflow discharge at usace gages
- get stage discharge ratings
- get river basins
- current water conditions
- get time series measurements (stage, streamflow, reservoir elevation, precipitation) for a usace location over a time period
- get information about usace water resource projects including dams, locks, reservoirs, and flood control structures
- get river basin information for usace water management regions
- get water measurements
- get basins
slug: water-resources-management
source_filename: water-resources-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"USACE Water Resources Management\"\n  description: >-\n    Unified workflow capability for accessing U.S. Army Corps of Engineers water\n    resource data. Combines location discovery, real-time time series measurements,\n    hydrological forecasts, and project information for water management, flood\n    monitoring, and operational decision support.\n  tags:\n    - Water Management\n    - Hydrology\n    - Federal Government\n    - USACE\n    - Flood Monitoring\n    - Dam Operations\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      CWMS_API_TOKEN: CWMS_API_TOKEN\n\ncapability:\n  consumes:\n    - import: cwms\n      location: ./shared/cwms-data-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: usace-water-resources-api\n      description: \"Unified REST API for USACE water resources management and monitoring.\"\n      resources:\n        - path: /v1/catalog\n\
  \          name: catalog\n          description: \"Browse available CWMS water data catalog\"\n          operations:\n            - method: GET\n              name: get-catalog\n              description: \"Browse available time series, locations, or ratings in CWMS\"\n              call: \"cwms.get-catalog\"\n              with:\n                datastore-type: \"rest.datastore-type\"\n                office: \"rest.office\"\n                like: \"rest.like\"\n                page-size: \"rest.page-size\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/locations\n          name: locations\n          description: \"USACE-managed location data\"\n          operations:\n            - method: GET\n              name: get-locations\n              description: \"Get all USACE locations filtered by office or name pattern\"\n              call: \"cwms.get-locations\"\n              with:\n                office: \"rest.office\"\
  \n                names: \"rest.names\"\n                unit: \"rest.unit\"\n                datum: \"rest.datum\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/locations/{location-id}\n          name: location\n          description: \"Single USACE location\"\n          operations:\n            - method: GET\n              name: get-location\n              description: \"Get detailed data for a specific USACE location\"\n              call: \"cwms.get-location\"\n              with:\n                location-id: \"rest.location-id\"\n                office: \"rest.office\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/timeseries\n          name: timeseries\n          description: \"CWMS time series measurements\"\n          operations:\n            - method: GET\n              name: get-timeseries\n              description: \"Get time\
  \ series data for a location (stage, flow, elevation, etc.)\"\n              call: \"cwms.get-timeseries\"\n              with:\n                name: \"rest.name\"\n                office: \"rest.office\"\n                begin: \"rest.begin\"\n                end: \"rest.end\"\n                unit: \"rest.unit\"\n                timezone: \"rest.timezone\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/timeseries/recent\n          name: recent-conditions\n          description: \"Current water conditions\"\n          operations:\n            - method: GET\n              name: get-recent-timeseries\n              description: \"Get the most recent readings for current conditions monitoring\"\n              call: \"cwms.get-recent-timeseries\"\n              with:\n                office: \"rest.office\"\n                name: \"rest.name\"\n                recently-changed-within: \"rest.recently-changed-within\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/levels\n          name: levels\n          description: \"Location levels (flood stage, normal pool)\"\n          operations:\n            - method: GET\n              name: get-levels\n              description: \"Get location levels for flood stage and pool elevation thresholds\"\n              call: \"cwms.get-levels\"\n              with:\n                office: \"rest.office\"\n                location-id: \"rest.location-id\"\n                unit: \"rest.unit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ratings\n          name: ratings\n          description: \"Stage-discharge rating tables\"\n          operations:\n            - method: GET\n              name: get-ratings\n              description: \"Get rating tables for converting stage to flow\"\n              call: \"cwms.get-ratings\"\
  \n              with:\n                office: \"rest.office\"\n                rating-id: \"rest.rating-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/forecasts\n          name: forecasts\n          description: \"Hydrological forecasts\"\n          operations:\n            - method: GET\n              name: get-forecast-instances\n              description: \"Get hydrological forecast instances\"\n              call: \"cwms.get-forecast-instances\"\n              with:\n                office: \"rest.office\"\n                name: \"rest.name\"\n                forecast-date: \"rest.forecast-date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects\n          name: projects\n          description: \"USACE water resource projects\"\n          operations:\n            - method: GET\n              name: get-projects\n        \
  \      description: \"Get USACE projects including dams, locks, and reservoirs\"\n              call: \"cwms.get-projects\"\n              with:\n                office: \"rest.office\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/basins\n          name: basins\n          description: \"River basin information\"\n          operations:\n            - method: GET\n              name: get-basins\n              description: \"Get river basin information for USACE water management areas\"\n              call: \"cwms.get-basins\"\n              with:\n                office: \"rest.office\"\n                basin-id: \"rest.basin-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: usace-water-resources-mcp\n      transport: http\n      description: \"MCP server for AI-assisted USACE water resources monitoring\
  \ and analysis.\"\n      tools:\n        - name: browse-water-data-catalog\n          description: \"Browse the CWMS data catalog to discover available time series, locations, and ratings for USACE water resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms.get-catalog\"\n          with:\n            datastore-type: \"tools.datastore-type\"\n            office: \"tools.office\"\n            like: \"tools.like\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-usace-locations\n          description: \"Search for USACE-managed locations (dams, reservoirs, stream gages) by name, office, or region\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms.get-locations\"\n          with:\n            office: \"tools.office\"\n            names: \"tools.names\"\n            unit: \"tools.unit\"\n          outputParameters:\n    \
  \        - type: object\n              mapping: \"$.\"\n\n        - name: get-location-details\n          description: \"Get detailed information for a specific USACE location including coordinates, elevation, and type\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms.get-location\"\n          with:\n            location-id: \"tools.location-id\"\n            office: \"tools.office\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-water-measurements\n          description: \"Get time series measurements (stage, streamflow, reservoir elevation, precipitation) for a USACE location over a time period\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms.get-timeseries\"\n          with:\n            name: \"tools.name\"\n            office: \"tools.office\"\n            begin: \"tools.begin\"\n            end: \"tools.end\"\n    \
  \        unit: \"tools.unit\"\n            timezone: \"tools.timezone\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-current-water-conditions\n          description: \"Get the most recent real-time water condition readings for USACE monitoring stations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms.get-recent-timeseries\"\n          with:\n            office: \"tools.office\"\n            name: \"tools.name\"\n            recently-changed-within: \"tools.recently-changed-within\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-flood-stage-levels\n          description: \"Get flood stage thresholds and normal pool levels for USACE locations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms.get-levels\"\n          with:\n            office: \"tools.office\"\n\
  \            location-id: \"tools.location-id\"\n            unit: \"tools.unit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-stage-discharge-ratings\n          description: \"Get rating curves that convert stage height to streamflow discharge at USACE gages\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms.get-ratings\"\n          with:\n            office: \"tools.office\"\n            rating-id: \"tools.rating-id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-hydrological-forecasts\n          description: \"Get hydrological forecasts for USACE project areas including flood predictions and reservoir operations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms.get-forecast-instances\"\n          with:\n            office: \"tools.office\"\n            name:\
  \ \"tools.name\"\n            forecast-date: \"tools.forecast-date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-usace-projects\n          description: \"Get information about USACE water resource projects including dams, locks, reservoirs, and flood control structures\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms.get-projects\"\n          with:\n            office: \"tools.office\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-river-basins\n          description: \"Get river basin information for USACE water management regions\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cwms.get-basins\"\n          with:\n            office: \"tools.office\"\n            basin-id: \"tools.basin-id\"\n          outputParameters:\n            - type: object\n         \
  \     mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/united-states-army-corps-of-engineers/refs/heads/main/capabilities/water-resources-management.yaml
tags:
- Water Management
- Hydrology
- Federal Government
- USACE
- Flood Monitoring
- Dam Operations
tools:
- description: Browse the CWMS data catalog to discover available time series, locations, and ratings for USACE water resources
  hints:
    openWorld: true
    readOnly: true
  name: browse-water-data-catalog
- description: Search for USACE-managed locations (dams, reservoirs, stream gages) by name, office, or region
  hints:
    openWorld: true
    readOnly: true
  name: search-usace-locations
- description: Get detailed information for a specific USACE location including coordinates, elevation, and type
  hints:
    openWorld: true
    readOnly: true
  name: get-location-details
- description: Get time series measurements (stage, streamflow, reservoir elevation, precipitation) for a USACE location over a time period
  hints:
    openWorld: true
    readOnly: true
  name: get-water-measurements
- description: Get the most recent real-time water condition readings for USACE monitoring stations
  hints:
    openWorld: true
    readOnly: true
  name: get-current-water-conditions
- description: Get flood stage thresholds and normal pool levels for USACE locations
  hints:
    openWorld: true
    readOnly: true
  name: get-flood-stage-levels
- description: Get rating curves that convert stage height to streamflow discharge at USACE gages
  hints:
    openWorld: true
    readOnly: true
  name: get-stage-discharge-ratings
- description: Get hydrological forecasts for USACE project areas including flood predictions and reservoir operations
  hints:
    openWorld: true
    readOnly: true
  name: get-hydrological-forecasts
- description: Get information about USACE water resource projects including dams, locks, reservoirs, and flood control structures
  hints:
    openWorld: true
    readOnly: true
  name: get-usace-projects
- description: Get river basin information for USACE water management regions
  hints:
    openWorld: true
    readOnly: true
  name: get-river-basins
---
