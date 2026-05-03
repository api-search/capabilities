---
api_specs:
- filename: usgs-earthquake-api-openapi.yaml
  format: yaml
  label: usgs-earthquake
  slug: usgs-earthquake
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/u-s-geological-survey/refs/heads/main/openapi/usgs-earthquake-api-openapi.yaml
- filename: usgs-water-data-api-openapi.yaml
  format: yaml
  label: usgs-water
  slug: usgs-water
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/u-s-geological-survey/refs/heads/main/openapi/usgs-water-data-api-openapi.yaml
categories: []
consumed_apis:
- usgs-earthquake
- usgs-water
description: Workflow capability for geoscientists, emergency managers, hydrologists, and researchers to access USGS real-time earthquake data and water monitoring data. Combines the USGS Earthquake API and USGS Water Data API into a unified geoscience data service for hazard assessment, hydrology analysis, and natural resource monitoring.
layout: capability
name: USGS Geoscience Data Access
operations:
- description: Retrieve earthquake events from the USGS ComCat catalog.
  method: GET
  name: query-earthquakes
  path: /v1/earthquakes
- description: Return the number of earthquakes matching query parameters.
  method: GET
  name: count-earthquakes
  path: /v1/earthquakes/count
- description: Find USGS water monitoring locations by state or bounding box.
  method: GET
  name: get-monitoring-locations
  path: /v1/monitoring-locations
- description: Retrieve a specific USGS monitoring location by identifier.
  method: GET
  name: get-monitoring-location
  path: /v1/monitoring-locations/{featureId}
- description: Retrieve streamflow, stage, or other water quality time series.
  method: GET
  name: get-water-observations
  path: /v1/water-observations
personas: []
provider_name: U.S. Geological Survey
provider_slug: u-s-geological-survey
search_terms:
- Researcher
- retrieve earthquake events from the usgs comcat catalog.
- return the number of earthquakes matching query parameters.
- get a single usgs water monitoring location.
- geological
- count earthquakes
- researcher studying seismic activity, geological hazards, or earth processes using usgs earthquake and geophysical data.
- retrieve a specific usgs monitoring location by identifier.
- earthquake
- count earthquake events without returning full data.
- get water monitoring site
- search recent earthquakes
- geoscience
- retrieve groundwater level (depth to water table) observations from usgs groundwater monitoring wells. use parameter code 72019 for depth to water below land surface.
- locate usgs stream gages, groundwater monitoring wells, and other water quality monitoring stations by state, watershed (huc), or geographic bounding box.
- federal government
- earth science
- retrieve streamflow, stage, or other water quality time series.
- usgs water monitoring stations (stream gages, groundwater wells).
- hydrology
- count the number of earthquakes matching specified criteria without retrieving full event data. useful for trend analysis and statistical queries.
- count earthquakes by criteria
- streamflow, groundwater, water quality, and flood monitoring
- natural hazard evaluation including earthquakes, floods, and landslides
- water resources scientist analyzing streamflow, groundwater levels, and water quality using usgs monitoring data.
- water
- natural resources
- Geoscientist
- retrieve streamflow (discharge in ft³/s) time series from a usgs stream gage. specify parameter code 00060 for discharge, 00065 for gage height, or other usgs parameter codes.
- government or public safety official monitoring earthquakes and flood conditions for emergency response planning.
- list earthquake catalogs
- search the usgs earthquake catalog for recent seismic events. filter by time range, location (bounding box or circle), magnitude, depth, and alert level. returns geojson with event properties and geometry.
- unified workflow for earthquake researchers, hydrologists, emergency managers, and scientists to access usgs earthquake catalog and water monitoring data.
- usgs
- get monitoring location
- academic or agency researcher using usgs data for geological, hydrological, or environmental studies.
- get streamflow data
- list all available usgs earthquake catalog sources used to filter earthquake queries.
- get monitoring locations
- real-time and historical seismic event data and hazard assessment
- 'retrieve details for a specific usgs water monitoring site using its identifier (format: usgs-sitenumber, e.g., usgs-11169025).'
- Emergency Manager
- hazard assessment
- search usgs earthquake catalog data.
- get water observations
- find water monitoring sites
- time series water data from usgs monitoring locations.
- get groundwater levels
- find usgs water monitoring locations by state or bounding box.
- Hydrologist
- query earthquakes
slug: geoscience-data-access
source_filename: geoscience-data-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"USGS Geoscience Data Access\"\n  description: >-\n    Workflow capability for geoscientists, emergency managers, hydrologists,\n    and researchers to access USGS real-time earthquake data and water monitoring\n    data. Combines the USGS Earthquake API and USGS Water Data API into a unified\n    geoscience data service for hazard assessment, hydrology analysis, and\n    natural resource monitoring.\n  tags:\n    - USGS\n    - Geoscience\n    - Earthquake\n    - Water\n    - Hydrology\n    - Hazard Assessment\n    - Federal Government\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      USGS_WATER_API_KEY: USGS_WATER_API_KEY\n\ncapability:\n  consumes:\n    - import: usgs-earthquake\n      location: ./shared/usgs-earthquake-api.yaml\n    - import: usgs-water\n      location: ./shared/usgs-water-data-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: geoscience-data-api\n\
  \      description: \"Unified REST API for USGS geoscience data including earthquakes and water.\"\n      resources:\n        - path: /v1/earthquakes\n          name: earthquakes\n          description: \"Search USGS earthquake catalog data.\"\n          operations:\n            - method: GET\n              name: query-earthquakes\n              description: \"Retrieve earthquake events from the USGS ComCat catalog.\"\n              call: \"usgs-earthquake.query-earthquakes\"\n              with:\n                starttime: \"rest.starttime\"\n                endtime: \"rest.endtime\"\n                minmagnitude: \"rest.minmagnitude\"\n                maxmagnitude: \"rest.maxmagnitude\"\n                minlatitude: \"rest.minlatitude\"\n                maxlatitude: \"rest.maxlatitude\"\n                minlongitude: \"rest.minlongitude\"\n                maxlongitude: \"rest.maxlongitude\"\n                limit: \"rest.limit\"\n                alertlevel: \"rest.alertlevel\"\n    \
  \          outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/earthquakes/count\n          name: earthquake-count\n          description: \"Count earthquake events without returning full data.\"\n          operations:\n            - method: GET\n              name: count-earthquakes\n              description: \"Return the number of earthquakes matching query parameters.\"\n              call: \"usgs-earthquake.count-earthquakes\"\n              with:\n                starttime: \"rest.starttime\"\n                endtime: \"rest.endtime\"\n                minmagnitude: \"rest.minmagnitude\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/monitoring-locations\n          name: monitoring-locations\n          description: \"USGS water monitoring stations (stream gages, groundwater wells).\"\n          operations:\n            - method: GET\n              name:\
  \ get-monitoring-locations\n              description: \"Find USGS water monitoring locations by state or bounding box.\"\n              call: \"usgs-water.get-monitoring-locations\"\n              with:\n                bbox: \"rest.bbox\"\n                stateCd: \"rest.stateCd\"\n                huc: \"rest.huc\"\n                siteType: \"rest.siteType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/monitoring-locations/{featureId}\n          name: monitoring-location\n          description: \"Get a single USGS water monitoring location.\"\n          operations:\n            - method: GET\n              name: get-monitoring-location\n              description: \"Retrieve a specific USGS monitoring location by identifier.\"\n              call: \"usgs-water.get-monitoring-location\"\n              with:\n                featureId: \"rest.featureId\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n        - path: /v1/water-observations\n          name: water-observations\n          description: \"Time series water data from USGS monitoring locations.\"\n          operations:\n            - method: GET\n              name: get-water-observations\n              description: \"Retrieve streamflow, stage, or other water quality time series.\"\n              call: \"usgs-water.get-time-series\"\n              with:\n                monitoringLocationIdentifier: \"rest.locationId\"\n                observedPropertyId: \"rest.parameterId\"\n                time: \"rest.time\"\n                bbox: \"rest.bbox\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: geoscience-data-mcp\n      transport: http\n      description: \"MCP server for AI-assisted geoscience data analysis using USGS earthquake and water APIs.\"\n      tools:\n     \
  \   - name: search-recent-earthquakes\n          description: >-\n            Search the USGS earthquake catalog for recent seismic events. Filter\n            by time range, location (bounding box or circle), magnitude, depth,\n            and alert level. Returns GeoJSON with event properties and geometry.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usgs-earthquake.query-earthquakes\"\n          with:\n            starttime: \"tools.start_time\"\n            endtime: \"tools.end_time\"\n            minmagnitude: \"tools.min_magnitude\"\n            maxmagnitude: \"tools.max_magnitude\"\n            minlatitude: \"tools.min_lat\"\n            maxlatitude: \"tools.max_lat\"\n            minlongitude: \"tools.min_lon\"\n            maxlongitude: \"tools.max_lon\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: count-earthquakes-by-criteria\n  \
  \        description: >-\n            Count the number of earthquakes matching specified criteria without\n            retrieving full event data. Useful for trend analysis and statistical\n            queries.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usgs-earthquake.count-earthquakes\"\n          with:\n            starttime: \"tools.start_time\"\n            endtime: \"tools.end_time\"\n            minmagnitude: \"tools.min_magnitude\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-water-monitoring-sites\n          description: >-\n            Locate USGS stream gages, groundwater monitoring wells, and other\n            water quality monitoring stations by state, watershed (HUC), or\n            geographic bounding box.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usgs-water.get-monitoring-locations\"\n          with:\n\
  \            bbox: \"tools.bbox\"\n            stateCd: \"tools.state_code\"\n            huc: \"tools.huc\"\n            siteType: \"tools.site_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-water-monitoring-site\n          description: >-\n            Retrieve details for a specific USGS water monitoring site using its\n            identifier (format: USGS-SITENUMBER, e.g., USGS-11169025).\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"usgs-water.get-monitoring-location\"\n          with:\n            featureId: \"tools.site_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-streamflow-data\n          description: >-\n            Retrieve streamflow (discharge in ft³/s) time series from a USGS\n            stream gage. Specify parameter code 00060 for discharge, 00065 for\n            gage height, or other\
  \ USGS parameter codes.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usgs-water.get-time-series\"\n          with:\n            monitoringLocationIdentifier: \"tools.site_id\"\n            observedPropertyId: \"tools.parameter_id\"\n            time: \"tools.time_range\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-groundwater-levels\n          description: >-\n            Retrieve groundwater level (depth to water table) observations from\n            USGS groundwater monitoring wells. Use parameter code 72019 for\n            depth to water below land surface.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usgs-water.get-time-series\"\n          with:\n            monitoringLocationIdentifier: \"tools.well_id\"\n            observedPropertyId: \"tools.parameter_id\"\n            time: \"tools.time_range\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: list-earthquake-catalogs\n          description: >-\n            List all available USGS earthquake catalog sources used to filter\n            earthquake queries.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"usgs-earthquake.list-catalogs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/u-s-geological-survey/refs/heads/main/capabilities/geoscience-data-access.yaml
tags:
- USGS
- Geoscience
- Earthquake
- Water
- Hydrology
- Hazard Assessment
- Federal Government
tools:
- description: Search the USGS earthquake catalog for recent seismic events. Filter by time range, location (bounding box or circle), magnitude, depth, and alert level. Returns GeoJSON with event properties and geometry.
  hints:
    openWorld: true
    readOnly: true
  name: search-recent-earthquakes
- description: Count the number of earthquakes matching specified criteria without retrieving full event data. Useful for trend analysis and statistical queries.
  hints:
    openWorld: true
    readOnly: true
  name: count-earthquakes-by-criteria
- description: Locate USGS stream gages, groundwater monitoring wells, and other water quality monitoring stations by state, watershed (HUC), or geographic bounding box.
  hints:
    openWorld: true
    readOnly: true
  name: find-water-monitoring-sites
- description: 'Retrieve details for a specific USGS water monitoring site using its identifier (format: USGS-SITENUMBER, e.g., USGS-11169025).'
  hints:
    openWorld: false
    readOnly: true
  name: get-water-monitoring-site
- description: Retrieve streamflow (discharge in ft³/s) time series from a USGS stream gage. Specify parameter code 00060 for discharge, 00065 for gage height, or other USGS parameter codes.
  hints:
    openWorld: true
    readOnly: true
  name: get-streamflow-data
- description: Retrieve groundwater level (depth to water table) observations from USGS groundwater monitoring wells. Use parameter code 72019 for depth to water below land surface.
  hints:
    openWorld: true
    readOnly: true
  name: get-groundwater-levels
- description: List all available USGS earthquake catalog sources used to filter earthquake queries.
  hints:
    openWorld: false
    readOnly: true
  name: list-earthquake-catalogs
---
