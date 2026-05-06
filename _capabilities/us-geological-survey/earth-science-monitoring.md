---
categories: []
consumed_apis: []
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
- get streamflow data
- water data
- earthquake count statistics
- earth science
- real-time water measurements from usgs monitoring stations
- count earthquakes matching query parameters
- geospatial
- environmental monitoring
- get daily water statistics
- query daily water values
- query earthquake events
- count earthquakes
- query earthquakes
- find water monitoring stations by geography
- earthquakes
- hazards
- environment
- get continuous water measurements from monitoring stations
- water monitoring station locations
- query water measurements
- find usgs monitoring stations
- query the usgs earthquake catalog for seismic events. filter by time range, geographic bounding box, or circular area, magnitude range, and depth. returns geojson featurecollection with event properties including magnitude, location, depth, and pager alert level.
- count seismic events
- count earthquakes in the usgs catalog without retrieving full event data. useful for assessing seismic activity levels in a region or time period.
- query earthquake catalog by time, location, and magnitude
- earthquake events from usgs national earthquake information center
- find usgs water monitoring stations by state, type, or geographic bounding box. returns location details including coordinates, huc codes, and monitoring parameters available at each station.
- query monitoring stations
- federal government
- get real-time streamflow and water level measurements from a usgs monitoring station. specify station id (e.g., usgs-01646500) and optional parameter code (00060 = discharge cfs, 00065 = gage height ft).
- get historical daily water data (mean, max, min values) for a usgs monitoring station. useful for flood analysis, drought assessment, and long-term trend analysis.
- get daily water data summaries
- daily summary water data
slug: earth-science-monitoring
source_filename: earth-science-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: USGS Earth Science Monitoring\n  description: Workflow capability for USGS earth science monitoring combining earthquake catalog data and water resources\n    data. Supports hazard assessment, natural disaster response, environmental monitoring, and scientific research workflows\n    combining seismic activity data with hydrological measurements.\n  tags:\n  - Earthquakes\n  - Water Data\n  - Earth Science\n  - Hazards\n  - Environmental Monitoring\n  - Federal Government\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    USGS_WATER_API_KEY: USGS_WATER_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: usgs-earthquake\n    baseUri: https://earthquake.usgs.gov/fdsnws/event/1\n    description: USGS FDSN Event Web Service for earthquake catalog access\n    resources:\n    - name: earthquakes\n      path: /query\n      description: Earthquake catalog query\n      operations:\n      - name:\
  \ query-earthquakes\n        method: GET\n        description: Query earthquake catalog with spatial, temporal, and magnitude filters\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Output format (geojson, quakeml, kml, csv, text)\n        - name: starttime\n          in: query\n          type: string\n          required: false\n          description: Start time (ISO 8601)\n        - name: endtime\n          in: query\n          type: string\n          required: false\n          description: End time (ISO 8601)\n        - name: minmagnitude\n          in: query\n          type: number\n          required: false\n          description: Minimum magnitude\n        - name: maxmagnitude\n          in: query\n          type: number\n          required: false\n          description: Maximum magnitude\n        - name: minlatitude\n          in: query\n          type: number\n          required: false\n\
  \          description: Southern boundary latitude\n        - name: maxlatitude\n          in: query\n          type: number\n          required: false\n          description: Northern boundary latitude\n        - name: minlongitude\n          in: query\n          type: number\n          required: false\n          description: Western boundary longitude\n        - name: maxlongitude\n          in: query\n          type: number\n          required: false\n          description: Eastern boundary longitude\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of events to return\n        - name: orderby\n          in: query\n          type: string\n          required: false\n          description: Sort order (time, magnitude)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: earthquake-count\n      path: /count\n      description:\
  \ Count earthquakes matching query parameters\n      operations:\n      - name: count-earthquakes\n        method: GET\n        description: Count earthquakes without returning full data\n        inputParameters:\n        - name: starttime\n          in: query\n          type: string\n          required: false\n          description: Start time\n        - name: endtime\n          in: query\n          type: string\n          required: false\n          description: End time\n        - name: minmagnitude\n          in: query\n          type: number\n          required: false\n          description: Minimum magnitude\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: usgs-water\n    baseUri: https://api.waterdata.usgs.gov/ogcapi/v0\n    description: USGS Water Data OGC APIs\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{USGS_WATER_API_KEY}}'\n      placement:\
  \ query\n    resources:\n    - name: continuous-values\n      path: /collections/continuous-values/items\n      description: Real-time continuous sensor measurements\n      operations:\n      - name: query-continuous-values\n        method: GET\n        description: Query continuous water measurement data\n        inputParameters:\n        - name: monitoringLocationIdentifier\n          in: query\n          type: string\n          required: false\n          description: USGS monitoring location ID\n        - name: parameterCode\n          in: query\n          type: string\n          required: false\n          description: USGS parameter code\n        - name: datetime\n          in: query\n          type: string\n          required: false\n          description: Temporal filter (ISO 8601)\n        - name: bbox\n          in: query\n          type: string\n          required: false\n          description: Bounding box for spatial filtering\n        - name: limit\n          in: query\n  \
  \        type: integer\n          required: false\n          description: Maximum features to return\n        - name: f\n          in: query\n          type: string\n          required: false\n          description: Response format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: daily-values\n      path: /collections/daily-values/items\n      description: Daily summary water data\n      operations:\n      - name: query-daily-values\n        method: GET\n        description: Query daily water data summaries\n        inputParameters:\n        - name: monitoringLocationIdentifier\n          in: query\n          type: string\n          required: false\n          description: USGS monitoring location ID\n        - name: parameterCode\n          in: query\n          type: string\n          required: false\n          description: USGS parameter code\n        - name: datetime\n          in: query\n    \
  \      type: string\n          required: false\n          description: Temporal filter\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum features to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitoring-locations\n      path: /collections/monitoring-locations/items\n      description: Water monitoring station metadata\n      operations:\n      - name: query-monitoring-locations\n        method: GET\n        description: Query water monitoring locations\n        inputParameters:\n        - name: monitoringLocationIdentifier\n          in: query\n          type: string\n          required: false\n          description: USGS monitoring location ID\n        - name: monitoringLocationType\n          in: query\n          type: string\n          required: false\n          description: Location type (Stream, Lake,\
  \ Well)\n        - name: stateCd\n          in: query\n          type: string\n          required: false\n          description: Two-letter state code\n        - name: bbox\n          in: query\n          type: string\n          required: false\n          description: Spatial bounding box\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum features to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: earth-science-api\n    description: Unified REST API for USGS earth science monitoring combining earthquake and water data.\n    resources:\n    - path: /v1/earthquakes\n      name: earthquakes\n      description: Earthquake events from USGS National Earthquake Information Center\n      operations:\n      - method: GET\n        name: query-earthquakes\n        description:\
  \ Query earthquake catalog by time, location, and magnitude\n        call: usgs-earthquake.query-earthquakes\n        with:\n          starttime: rest.starttime\n          endtime: rest.endtime\n          minmagnitude: rest.minmagnitude\n          minlatitude: rest.minlatitude\n          maxlatitude: rest.maxlatitude\n          minlongitude: rest.minlongitude\n          maxlongitude: rest.maxlongitude\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/earthquake-counts\n      name: earthquake-counts\n      description: Earthquake count statistics\n      operations:\n      - method: GET\n        name: count-earthquakes\n        description: Count earthquakes matching query parameters\n        call: usgs-earthquake.count-earthquakes\n        with:\n          starttime: rest.starttime\n          endtime: rest.endtime\n          minmagnitude: rest.minmagnitude\n        outputParameters:\n        - type: object\n         \
  \ mapping: $.\n    - path: /v1/water-measurements\n      name: water-measurements\n      description: Real-time water measurements from USGS monitoring stations\n      operations:\n      - method: GET\n        name: query-water-measurements\n        description: Get continuous water measurements from monitoring stations\n        call: usgs-water.query-continuous-values\n        with:\n          monitoringLocationIdentifier: rest.site_id\n          parameterCode: rest.parameter_code\n          datetime: rest.datetime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/daily-water-values\n      name: daily-water-values\n      description: Daily summary water data\n      operations:\n      - method: GET\n        name: query-daily-water-values\n        description: Get daily water data summaries\n        call: usgs-water.query-daily-values\n        with:\n          monitoringLocationIdentifier: rest.site_id\n          parameterCode: rest.parameter_code\n\
  \          datetime: rest.datetime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitoring-stations\n      name: monitoring-stations\n      description: Water monitoring station locations\n      operations:\n      - method: GET\n        name: query-monitoring-stations\n        description: Find water monitoring stations by geography\n        call: usgs-water.query-monitoring-locations\n        with:\n          stateCd: rest.state\n          bbox: rest.bbox\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: earth-science-mcp\n    transport: http\n    description: MCP server for AI-assisted USGS earth science monitoring, hazard assessment, and water resources analysis.\n    tools:\n    - name: query-earthquake-events\n      description: Query the USGS earthquake catalog for seismic events. Filter by time range, geographic bounding box, or\n        circular area, magnitude range,\
  \ and depth. Returns GeoJSON FeatureCollection with event properties including magnitude,\n        location, depth, and PAGER alert level.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usgs-earthquake.query-earthquakes\n      with:\n        starttime: tools.starttime\n        endtime: tools.endtime\n        minmagnitude: tools.minmagnitude\n        maxmagnitude: tools.maxmagnitude\n        minlatitude: tools.minlatitude\n        maxlatitude: tools.maxlatitude\n        minlongitude: tools.minlongitude\n        maxlongitude: tools.maxlongitude\n        latitude: tools.latitude\n        longitude: tools.longitude\n        maxradiuskm: tools.maxradiuskm\n        limit: tools.limit\n        orderby: tools.orderby\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: count-seismic-events\n      description: Count earthquakes in the USGS catalog without retrieving full event data. Useful for assessing seismic\n        activity levels in\
  \ a region or time period.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usgs-earthquake.count-earthquakes\n      with:\n        starttime: tools.starttime\n        endtime: tools.endtime\n        minmagnitude: tools.minmagnitude\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-streamflow-data\n      description: Get real-time streamflow and water level measurements from a USGS monitoring station. Specify station ID\n        (e.g., USGS-01646500) and optional parameter code (00060 = discharge cfs, 00065 = gage height ft).\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usgs-water.query-continuous-values\n      with:\n        monitoringLocationIdentifier: tools.site_id\n        parameterCode: tools.parameter_code\n        datetime: tools.datetime\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-daily-water-statistics\n      description:\
  \ Get historical daily water data (mean, max, min values) for a USGS monitoring station. Useful for flood\n        analysis, drought assessment, and long-term trend analysis.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usgs-water.query-daily-values\n      with:\n        monitoringLocationIdentifier: tools.site_id\n        parameterCode: tools.parameter_code\n        datetime: tools.datetime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-usgs-monitoring-stations\n      description: Find USGS water monitoring stations by state, type, or geographic bounding box. Returns location details\n        including coordinates, HUC codes, and monitoring parameters available at each station.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usgs-water.query-monitoring-locations\n      with:\n        stateCd: tools.state\n        monitoringLocationType: tools.type\n        bbox: tools.bbox\n        limit:\
  \ tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
