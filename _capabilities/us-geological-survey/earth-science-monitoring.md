---
api_specs:
- filename: usgs-earthquake-catalog-openapi.yml
  format: yaml
  label: usgs-earthquake
  slug: usgs-earthquake
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/us-geological-survey/refs/heads/main/openapi/usgs-earthquake-catalog-openapi.yml
- filename: usgs-water-data-openapi.yml
  format: yaml
  label: usgs-water
  slug: usgs-water
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/us-geological-survey/refs/heads/main/openapi/usgs-water-data-openapi.yml
categories: []
consumed_apis:
- usgs-earthquake
- usgs-water
description: Workflow capability for USGS earth science monitoring combining earthquake catalog data and water resources data. Supports hazard assessment, natural disaster response, environmental monitoring, and scientific research workflows combining seismic activity data with hydrological measurements.
layout: capability
name: USGS Earth Science Monitoring
operations:
- description: Query earthquake catalog by time, location, and magnitude
  method: GET
  name: query-earthquakes
  path: /v1/earthquakes
- description: Count earthquakes matching query parameters
  method: GET
  name: count-earthquakes
  path: /v1/earthquake-counts
- description: Get continuous water measurements from monitoring stations
  method: GET
  name: query-water-measurements
  path: /v1/water-measurements
- description: Get daily water data summaries
  method: GET
  name: query-daily-water-values
  path: /v1/daily-water-values
- description: Find water monitoring stations by geography
  method: GET
  name: query-monitoring-stations
  path: /v1/monitoring-stations
personas: []
provider_name: US Geological Survey
provider_slug: us-geological-survey
search_terms:
- query water measurements
- query daily water values
- count earthquakes matching query parameters
- get real-time streamflow and water level measurements from a usgs monitoring station. specify station id (e.g., usgs-01646500) and optional parameter code (00060 = discharge cfs, 00065 = gage height ft).
- count earthquakes
- get daily water data summaries
- get continuous water measurements from monitoring stations
- geospatial
- federal government
- earth science
- query earthquake events
- hazards
- find usgs monitoring stations
- water monitoring station locations
- earthquake events from usgs national earthquake information center
- earthquakes
- daily summary water data
- query monitoring stations
- get historical daily water data (mean, max, min values) for a usgs monitoring station. useful for flood analysis, drought assessment, and long-term trend analysis.
- get daily water statistics
- find usgs water monitoring stations by state, type, or geographic bounding box. returns location details including coordinates, huc codes, and monitoring parameters available at each station.
- get streamflow data
- count seismic events
- query earthquake catalog by time, location, and magnitude
- water data
- environment
- query the usgs earthquake catalog for seismic events. filter by time range, geographic bounding box, or circular area, magnitude range, and depth. returns geojson featurecollection with event properties including magnitude, location, depth, and pager alert level.
- count earthquakes in the usgs catalog without retrieving full event data. useful for assessing seismic activity levels in a region or time period.
- earthquake count statistics
- find water monitoring stations by geography
- environmental monitoring
- real-time water measurements from usgs monitoring stations
- query earthquakes
slug: earth-science-monitoring
source_filename: earth-science-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"USGS Earth Science Monitoring\"\n  description: >-\n    Workflow capability for USGS earth science monitoring combining earthquake\n    catalog data and water resources data. Supports hazard assessment, natural\n    disaster response, environmental monitoring, and scientific research workflows\n    combining seismic activity data with hydrological measurements.\n  tags:\n    - Earthquakes\n    - Water Data\n    - Earth Science\n    - Hazards\n    - Environmental Monitoring\n    - Federal Government\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      USGS_WATER_API_KEY: USGS_WATER_API_KEY\n\ncapability:\n  consumes:\n    - import: usgs-earthquake\n      location: ./shared/usgs-earthquake-catalog.yaml\n    - import: usgs-water\n      location: ./shared/usgs-water-data.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: earth-science-api\n      description: \"\
  Unified REST API for USGS earth science monitoring combining earthquake and water data.\"\n      resources:\n        - path: /v1/earthquakes\n          name: earthquakes\n          description: \"Earthquake events from USGS National Earthquake Information Center\"\n          operations:\n            - method: GET\n              name: query-earthquakes\n              description: \"Query earthquake catalog by time, location, and magnitude\"\n              call: \"usgs-earthquake.query-earthquakes\"\n              with:\n                starttime: \"rest.starttime\"\n                endtime: \"rest.endtime\"\n                minmagnitude: \"rest.minmagnitude\"\n                minlatitude: \"rest.minlatitude\"\n                maxlatitude: \"rest.maxlatitude\"\n                minlongitude: \"rest.minlongitude\"\n                maxlongitude: \"rest.maxlongitude\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/earthquake-counts\n          name: earthquake-counts\n          description: \"Earthquake count statistics\"\n          operations:\n            - method: GET\n              name: count-earthquakes\n              description: \"Count earthquakes matching query parameters\"\n              call: \"usgs-earthquake.count-earthquakes\"\n              with:\n                starttime: \"rest.starttime\"\n                endtime: \"rest.endtime\"\n                minmagnitude: \"rest.minmagnitude\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/water-measurements\n          name: water-measurements\n          description: \"Real-time water measurements from USGS monitoring stations\"\n          operations:\n            - method: GET\n              name: query-water-measurements\n              description: \"Get continuous water measurements from monitoring stations\"\n              call: \"\
  usgs-water.query-continuous-values\"\n              with:\n                monitoringLocationIdentifier: \"rest.site_id\"\n                parameterCode: \"rest.parameter_code\"\n                datetime: \"rest.datetime\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/daily-water-values\n          name: daily-water-values\n          description: \"Daily summary water data\"\n          operations:\n            - method: GET\n              name: query-daily-water-values\n              description: \"Get daily water data summaries\"\n              call: \"usgs-water.query-daily-values\"\n              with:\n                monitoringLocationIdentifier: \"rest.site_id\"\n                parameterCode: \"rest.parameter_code\"\n                datetime: \"rest.datetime\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/monitoring-stations\n     \
  \     name: monitoring-stations\n          description: \"Water monitoring station locations\"\n          operations:\n            - method: GET\n              name: query-monitoring-stations\n              description: \"Find water monitoring stations by geography\"\n              call: \"usgs-water.query-monitoring-locations\"\n              with:\n                stateCd: \"rest.state\"\n                bbox: \"rest.bbox\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: earth-science-mcp\n      transport: http\n      description: \"MCP server for AI-assisted USGS earth science monitoring, hazard assessment, and water resources analysis.\"\n      tools:\n        - name: query-earthquake-events\n          description: >-\n            Query the USGS earthquake catalog for seismic events. Filter by time range,\n            geographic bounding box, or circular area, magnitude range,\
  \ and depth.\n            Returns GeoJSON FeatureCollection with event properties including magnitude,\n            location, depth, and PAGER alert level.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usgs-earthquake.query-earthquakes\"\n          with:\n            starttime: \"tools.starttime\"\n            endtime: \"tools.endtime\"\n            minmagnitude: \"tools.minmagnitude\"\n            maxmagnitude: \"tools.maxmagnitude\"\n            minlatitude: \"tools.minlatitude\"\n            maxlatitude: \"tools.maxlatitude\"\n            minlongitude: \"tools.minlongitude\"\n            maxlongitude: \"tools.maxlongitude\"\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            maxradiuskm: \"tools.maxradiuskm\"\n            limit: \"tools.limit\"\n            orderby: \"tools.orderby\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: count-seismic-events\n\
  \          description: >-\n            Count earthquakes in the USGS catalog without retrieving full event data.\n            Useful for assessing seismic activity levels in a region or time period.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usgs-earthquake.count-earthquakes\"\n          with:\n            starttime: \"tools.starttime\"\n            endtime: \"tools.endtime\"\n            minmagnitude: \"tools.minmagnitude\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-streamflow-data\n          description: >-\n            Get real-time streamflow and water level measurements from a USGS\n            monitoring station. Specify station ID (e.g., USGS-01646500) and\n            optional parameter code (00060 = discharge cfs, 00065 = gage height ft).\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usgs-water.query-continuous-values\"\
  \n          with:\n            monitoringLocationIdentifier: \"tools.site_id\"\n            parameterCode: \"tools.parameter_code\"\n            datetime: \"tools.datetime\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-daily-water-statistics\n          description: >-\n            Get historical daily water data (mean, max, min values) for a USGS\n            monitoring station. Useful for flood analysis, drought assessment,\n            and long-term trend analysis.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usgs-water.query-daily-values\"\n          with:\n            monitoringLocationIdentifier: \"tools.site_id\"\n            parameterCode: \"tools.parameter_code\"\n            datetime: \"tools.datetime\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-usgs-monitoring-stations\n\
  \          description: >-\n            Find USGS water monitoring stations by state, type, or geographic bounding\n            box. Returns location details including coordinates, HUC codes, and\n            monitoring parameters available at each station.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usgs-water.query-monitoring-locations\"\n          with:\n            stateCd: \"tools.state\"\n            monitoringLocationType: \"tools.type\"\n            bbox: \"tools.bbox\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/us-geological-survey/refs/heads/main/capabilities/earth-science-monitoring.yaml
tags:
- Earthquakes
- Water Data
- Earth Science
- Hazards
- Environmental Monitoring
- Federal Government
tools:
- description: Query the USGS earthquake catalog for seismic events. Filter by time range, geographic bounding box, or circular area, magnitude range, and depth. Returns GeoJSON FeatureCollection with event properties including magnitude, location, depth, and PAGER alert level.
  hints:
    openWorld: true
    readOnly: true
  name: query-earthquake-events
- description: Count earthquakes in the USGS catalog without retrieving full event data. Useful for assessing seismic activity levels in a region or time period.
  hints:
    openWorld: true
    readOnly: true
  name: count-seismic-events
- description: Get real-time streamflow and water level measurements from a USGS monitoring station. Specify station ID (e.g., USGS-01646500) and optional parameter code (00060 = discharge cfs, 00065 = gage height ft).
  hints:
    openWorld: true
    readOnly: true
  name: get-streamflow-data
- description: Get historical daily water data (mean, max, min values) for a USGS monitoring station. Useful for flood analysis, drought assessment, and long-term trend analysis.
  hints:
    openWorld: true
    readOnly: true
  name: get-daily-water-statistics
- description: Find USGS water monitoring stations by state, type, or geographic bounding box. Returns location details including coordinates, HUC codes, and monitoring parameters available at each station.
  hints:
    openWorld: true
    readOnly: true
  name: find-usgs-monitoring-stations
---
