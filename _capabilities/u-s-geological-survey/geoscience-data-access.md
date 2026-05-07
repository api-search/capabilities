---
categories: []
consumed_apis: []
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
- usgs
- get streamflow data
- geoscience
- locate usgs stream gages, groundwater monitoring wells, and other water quality monitoring stations by state, watershed (huc), or geographic bounding box.
- Hydrologist
- earthquake
- get water monitoring site
- real-time and historical seismic event data and hazard assessment
- search recent earthquakes
- find water monitoring sites
- retrieve streamflow (discharge in ft³/s) time series from a usgs stream gage. specify parameter code 00060 for discharge, 00065 for gage height, or other usgs parameter codes.
- retrieve groundwater level (depth to water table) observations from usgs groundwater monitoring wells. use parameter code 72019 for depth to water below land surface.
- unified workflow for earthquake researchers, hydrologists, emergency managers, and scientists to access usgs earthquake catalog and water monitoring data.
- list earthquake catalogs
- 'retrieve details for a specific usgs water monitoring site using its identifier (format: usgs-sitenumber, e.g., usgs-11169025).'
- Geoscientist
- natural hazard evaluation including earthquakes, floods, and landslides
- list all available usgs earthquake catalog sources used to filter earthquake queries.
- usgs water monitoring stations (stream gages, groundwater wells).
- get monitoring locations
- Researcher
- count earthquake events without returning full data.
- retrieve a specific usgs monitoring location by identifier.
- get water observations
- water
- retrieve earthquake events from the usgs comcat catalog.
- get monitoring location
- count earthquakes
- search the usgs earthquake catalog for recent seismic events. filter by time range, location (bounding box or circle), magnitude, depth, and alert level. returns geojson with event properties and geometry.
- water resources scientist analyzing streamflow, groundwater levels, and water quality using usgs monitoring data.
- natural resources
- hazard assessment
- retrieve streamflow, stage, or other water quality time series.
- Emergency Manager
- count earthquakes by criteria
- earth science
- time series water data from usgs monitoring locations.
- find usgs water monitoring locations by state or bounding box.
- get groundwater levels
- academic or agency researcher using usgs data for geological, hydrological, or environmental studies.
- hydrology
- get a single usgs water monitoring location.
- search usgs earthquake catalog data.
- return the number of earthquakes matching query parameters.
- federal government
- count the number of earthquakes matching specified criteria without retrieving full event data. useful for trend analysis and statistical queries.
- query earthquakes
- geological
- streamflow, groundwater, water quality, and flood monitoring
- researcher studying seismic activity, geological hazards, or earth processes using usgs earthquake and geophysical data.
- government or public safety official monitoring earthquakes and flood conditions for emergency response planning.
slug: geoscience-data-access
source_filename: geoscience-data-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: USGS Geoscience Data Access\n  description: Workflow capability for geoscientists, emergency managers, hydrologists, and researchers to access USGS real-time\n    earthquake data and water monitoring data. Combines the USGS Earthquake API and USGS Water Data API into a unified geoscience\n    data service for hazard assessment, hydrology analysis, and natural resource monitoring.\n  tags:\n  - USGS\n  - Geoscience\n  - Earthquake\n  - Water\n  - Hydrology\n  - Hazard Assessment\n  - Federal Government\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    USGS_WATER_API_KEY: USGS_WATER_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: usgs-earthquake\n    baseUri: https://earthquake.usgs.gov/fdsnws/event/1\n    description: USGS FDSN earthquake event web service.\n    resources:\n    - name: earthquake-events\n      path: /query\n      description: Query earthquake events from the USGS\
  \ ComCat catalog.\n      operations:\n      - name: query-earthquakes\n        method: GET\n        description: Search earthquake events by time, location, magnitude, and depth.\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Response format (geojson, csv, kml, quakeml).\n        - name: starttime\n          in: query\n          type: string\n          required: false\n          description: Start time in ISO8601 format.\n        - name: endtime\n          in: query\n          type: string\n          required: false\n          description: End time in ISO8601 format.\n        - name: minmagnitude\n          in: query\n          type: number\n          required: false\n          description: Minimum earthquake magnitude.\n        - name: maxmagnitude\n          in: query\n          type: number\n          required: false\n          description: Maximum earthquake magnitude.\n        - name:\
  \ minlatitude\n          in: query\n          type: number\n          required: false\n          description: Minimum latitude for bounding box.\n        - name: maxlatitude\n          in: query\n          type: number\n          required: false\n          description: Maximum latitude for bounding box.\n        - name: minlongitude\n          in: query\n          type: number\n          required: false\n          description: Minimum longitude for bounding box.\n        - name: maxlongitude\n          in: query\n          type: number\n          required: false\n          description: Maximum longitude for bounding box.\n        - name: latitude\n          in: query\n          type: number\n          required: false\n          description: Center latitude for circle filter.\n        - name: longitude\n          in: query\n          type: number\n          required: false\n          description: Center longitude for circle filter.\n        - name: maxradiuskm\n          in: query\n   \
  \       type: number\n          required: false\n          description: Search radius in kilometers.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of events (1-20000).\n        - name: orderby\n          in: query\n          type: string\n          required: false\n          description: Sort order (time, magnitude, etc.).\n        - name: alertlevel\n          in: query\n          type: string\n          required: false\n          description: PAGER alert level filter.\n        - name: reviewstatus\n          in: query\n          type: string\n          required: false\n          description: Filter by review status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: count-earthquakes\n        method: GET\n        description: Count earthquake events matching query parameters.\n        inputParameters:\n   \
  \     - name: starttime\n          in: query\n          type: string\n          required: false\n          description: Start time in ISO8601 format.\n        - name: endtime\n          in: query\n          type: string\n          required: false\n          description: End time in ISO8601 format.\n        - name: minmagnitude\n          in: query\n          type: number\n          required: false\n          description: Minimum magnitude.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: earthquake-catalogs\n      path: /catalogs\n      description: List available earthquake catalog sources.\n      operations:\n      - name: list-catalogs\n        method: GET\n        description: Return available earthquake catalog identifiers.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n\
  \    namespace: usgs-water\n    baseUri: https://api.waterdata.usgs.gov/ogcapi/v0\n    description: USGS Water Data OGC API for water monitoring data.\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{USGS_WATER_API_KEY}}'\n      placement: query\n    resources:\n    - name: monitoring-locations\n      path: /collections/monitoring-locations/items\n      description: USGS water monitoring locations (gages, wells, springs).\n      operations:\n      - name: get-monitoring-locations\n        method: GET\n        description: Retrieve water monitoring locations with optional spatial and attribute filters.\n        inputParameters:\n        - name: bbox\n          in: query\n          type: string\n          required: false\n          description: Bounding box as min_lon,min_lat,max_lon,max_lat.\n        - name: stateCd\n          in: query\n          type: string\n          required: false\n          description: Two-letter state FIPS code.\n        - name: huc\n\
  \          in: query\n          type: string\n          required: false\n          description: Hydrologic Unit Code.\n        - name: siteType\n          in: query\n          type: string\n          required: false\n          description: USGS site type code (ST, GW, LK, etc.).\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Starting offset for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitoring-location\n      path: /collections/monitoring-locations/items/{featureId}\n      description: Get a single USGS monitoring location by ID.\n      operations:\n      - name: get-monitoring-location\n        method: GET\n        description: Retrieve a single monitoring\
  \ location by its USGS site identifier.\n        inputParameters:\n        - name: featureId\n          in: path\n          type: string\n          required: true\n          description: Monitoring location identifier (e.g., USGS-11169025).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: time-series\n      path: /collections/time-series/items\n      description: USGS continuous and daily water data time series.\n      operations:\n      - name: get-time-series\n        method: GET\n        description: Retrieve water data time series observations.\n        inputParameters:\n        - name: monitoringLocationIdentifier\n          in: query\n          type: string\n          required: false\n          description: Filter by monitoring location identifier.\n        - name: observedPropertyId\n          in: query\n          type: string\n          required: false\n          description: USGS parameter\
  \ code (e.g., 00060 for streamflow).\n        - name: time\n          in: query\n          type: string\n          required: false\n          description: Temporal filter as ISO 8601 datetime or interval.\n        - name: bbox\n          in: query\n          type: string\n          required: false\n          description: Spatial bounding box filter.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of observations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: geoscience-data-api\n    description: Unified REST API for USGS geoscience data including earthquakes and water.\n    resources:\n    - path: /v1/earthquakes\n      name: earthquakes\n      description: Search USGS earthquake catalog data.\n      operations:\n      - method: GET\n        name: query-earthquakes\n\
  \        description: Retrieve earthquake events from the USGS ComCat catalog.\n        call: usgs-earthquake.query-earthquakes\n        with:\n          starttime: rest.starttime\n          endtime: rest.endtime\n          minmagnitude: rest.minmagnitude\n          maxmagnitude: rest.maxmagnitude\n          minlatitude: rest.minlatitude\n          maxlatitude: rest.maxlatitude\n          minlongitude: rest.minlongitude\n          maxlongitude: rest.maxlongitude\n          limit: rest.limit\n          alertlevel: rest.alertlevel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/earthquakes/count\n      name: earthquake-count\n      description: Count earthquake events without returning full data.\n      operations:\n      - method: GET\n        name: count-earthquakes\n        description: Return the number of earthquakes matching query parameters.\n        call: usgs-earthquake.count-earthquakes\n        with:\n          starttime: rest.starttime\n\
  \          endtime: rest.endtime\n          minmagnitude: rest.minmagnitude\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitoring-locations\n      name: monitoring-locations\n      description: USGS water monitoring stations (stream gages, groundwater wells).\n      operations:\n      - method: GET\n        name: get-monitoring-locations\n        description: Find USGS water monitoring locations by state or bounding box.\n        call: usgs-water.get-monitoring-locations\n        with:\n          bbox: rest.bbox\n          stateCd: rest.stateCd\n          huc: rest.huc\n          siteType: rest.siteType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitoring-locations/{featureId}\n      name: monitoring-location\n      description: Get a single USGS water monitoring location.\n      operations:\n      - method: GET\n        name: get-monitoring-location\n        description: Retrieve a specific\
  \ USGS monitoring location by identifier.\n        call: usgs-water.get-monitoring-location\n        with:\n          featureId: rest.featureId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/water-observations\n      name: water-observations\n      description: Time series water data from USGS monitoring locations.\n      operations:\n      - method: GET\n        name: get-water-observations\n        description: Retrieve streamflow, stage, or other water quality time series.\n        call: usgs-water.get-time-series\n        with:\n          monitoringLocationIdentifier: rest.locationId\n          observedPropertyId: rest.parameterId\n          time: rest.time\n          bbox: rest.bbox\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: geoscience-data-mcp\n    transport: http\n    description: MCP server for AI-assisted geoscience data analysis using USGS earthquake and water\
  \ APIs.\n    tools:\n    - name: search-recent-earthquakes\n      description: Search the USGS earthquake catalog for recent seismic events. Filter by time range, location (bounding\n        box or circle), magnitude, depth, and alert level. Returns GeoJSON with event properties and geometry.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usgs-earthquake.query-earthquakes\n      with:\n        starttime: tools.start_time\n        endtime: tools.end_time\n        minmagnitude: tools.min_magnitude\n        maxmagnitude: tools.max_magnitude\n        minlatitude: tools.min_lat\n        maxlatitude: tools.max_lat\n        minlongitude: tools.min_lon\n        maxlongitude: tools.max_lon\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: count-earthquakes-by-criteria\n      description: Count the number of earthquakes matching specified criteria without retrieving full event data. Useful\n        for trend\
  \ analysis and statistical queries.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usgs-earthquake.count-earthquakes\n      with:\n        starttime: tools.start_time\n        endtime: tools.end_time\n        minmagnitude: tools.min_magnitude\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-water-monitoring-sites\n      description: Locate USGS stream gages, groundwater monitoring wells, and other water quality monitoring stations by\n        state, watershed (HUC), or geographic bounding box.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usgs-water.get-monitoring-locations\n      with:\n        bbox: tools.bbox\n        stateCd: tools.state_code\n        huc: tools.huc\n        siteType: tools.site_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-water-monitoring-site\n      description: 'Retrieve details for a specific USGS water monitoring site using\
  \ its identifier (format: USGS-SITENUMBER,\n        e.g., USGS-11169025).'\n      hints:\n        readOnly: true\n        openWorld: false\n      call: usgs-water.get-monitoring-location\n      with:\n        featureId: tools.site_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-streamflow-data\n      description: Retrieve streamflow (discharge in ft³/s) time series from a USGS stream gage. Specify parameter code 00060\n        for discharge, 00065 for gage height, or other USGS parameter codes.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usgs-water.get-time-series\n      with:\n        monitoringLocationIdentifier: tools.site_id\n        observedPropertyId: tools.parameter_id\n        time: tools.time_range\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-groundwater-levels\n      description: Retrieve groundwater level (depth to water table) observations from USGS groundwater monitoring\
  \ wells.\n        Use parameter code 72019 for depth to water below land surface.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usgs-water.get-time-series\n      with:\n        monitoringLocationIdentifier: tools.well_id\n        observedPropertyId: tools.parameter_id\n        time: tools.time_range\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-earthquake-catalogs\n      description: List all available USGS earthquake catalog sources used to filter earthquake queries.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: usgs-earthquake.list-catalogs\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
