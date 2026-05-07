---
categories: []
consumed_apis: []
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
- civil engineering
- engineering
- get ratings
- get river basin information for usace water management areas
- location levels (flood stage, normal pool)
- search usace locations
- get flood stage thresholds and normal pool levels for usace locations
- usace water resource projects
- get time series data for a location (stage, flow, elevation, etc.)
- get river basins
- get rating tables for converting stage to flow
- get detailed data for a specific usace location
- browse available time series, locations, or ratings in cwms
- dam operations
- get levels
- get hydrological forecast instances
- hydrological forecasts
- get flood stage levels
- get location
- get locations
- stage-discharge rating tables
- get information about usace water resource projects including dams, locks, reservoirs, and flood control structures
- cwms time series measurements
- get timeseries
- single usace location
- get river basin information for usace water management regions
- get projects
- browse the cwms data catalog to discover available time series, locations, and ratings for usace water resources
- get rating curves that convert stage height to streamflow discharge at usace gages
- get location details
- get usace projects including dams, locks, and reservoirs
- river basin information
- get recent timeseries
- get all usace locations filtered by office or name pattern
- get time series measurements (stage, streamflow, reservoir elevation, precipitation) for a usace location over a time period
- get stage discharge ratings
- get the most recent readings for current conditions monitoring
- browse water data catalog
- usace
- water management
- get detailed information for a specific usace location including coordinates, elevation, and type
- search for usace-managed locations (dams, reservoirs, stream gages) by name, office, or region
- usace-managed location data
- get the most recent real-time water condition readings for usace monitoring stations
- get usace projects
- current water conditions
- hydrology
- get forecast instances
- flood monitoring
- get current water conditions
- browse available cwms water data catalog
- get location levels for flood stage and pool elevation thresholds
- get hydrological forecasts for usace project areas including flood predictions and reservoir operations
- federal government
- water resources
- get catalog
- get hydrological forecasts
- get water measurements
- get basins
slug: water-resources-management
source_filename: water-resources-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: USACE Water Resources Management\n  description: Unified workflow capability for accessing U.S. Army Corps of Engineers water resource data. Combines location\n    discovery, real-time time series measurements, hydrological forecasts, and project information for water management, flood\n    monitoring, and operational decision support.\n  tags:\n  - Water Management\n  - Hydrology\n  - Federal Government\n  - USACE\n  - Flood Monitoring\n  - Dam Operations\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CWMS_API_TOKEN: CWMS_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: cwms\n    baseUri: https://cwms-data.usace.army.mil/cwms-data\n    description: USACE Corps Water Management System REST Data API\n    authentication:\n      type: bearer\n      token: '{{CWMS_API_TOKEN}}'\n    resources:\n    - name: catalog\n      path: /catalog/{datastore-type}\n      description: Browse\
  \ available CWMS data catalog\n      operations:\n      - name: get-catalog\n        method: GET\n        description: Returns catalog of available time series, locations, or ratings\n        inputParameters:\n        - name: datastore-type\n          in: path\n          type: string\n          required: true\n          description: 'Data type: TIMESERIES, LOCATIONS, or RATINGS'\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: Three-character USACE district office code\n        - name: like\n          in: query\n          type: string\n          required: false\n          description: CWMS wildcard filter pattern\n        - name: page-size\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: locations\n     \
  \ path: /locations\n      description: USACE location data\n      operations:\n      - name: get-locations\n        method: GET\n        description: Returns location data for USACE-managed sites\n        inputParameters:\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: Three-character USACE district office code\n        - name: names\n          in: query\n          type: string\n          required: false\n          description: Comma-separated location names or wildcard pattern\n        - name: unit\n          in: query\n          type: string\n          required: false\n          description: 'Unit system: EN (English) or SI (metric)'\n        - name: datum\n          in: query\n          type: string\n          required: false\n          description: Vertical datum (NAVD88, NGVD29)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: location\n      path: /locations/{location-id}\n      description: Single USACE location\n      operations:\n      - name: get-location\n        method: GET\n        description: Returns data for a specific USACE location\n        inputParameters:\n        - name: location-id\n          in: path\n          type: string\n          required: true\n          description: The CWMS location identifier\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: Three-character USACE district office code\n        - name: unit\n          in: query\n          type: string\n          required: false\n          description: 'Unit system: EN or SI'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: timeseries\n      path: /timeseries\n      description: CWMS time series data\n      operations:\n      - name: get-timeseries\n        method: GET\n\
  \        description: Returns time series data for a specified time window\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: CWMS time series identifier\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: Three-character USACE district office code\n        - name: unit\n          in: query\n          type: string\n          required: false\n          description: Measurement unit for returned data\n        - name: datum\n          in: query\n          type: string\n          required: false\n          description: Vertical datum for elevation values\n        - name: begin\n          in: query\n          type: string\n          required: false\n          description: Start of time window (ISO 8601 or ms since epoch)\n        - name: end\n          in: query\n          type: string\n          required: false\n          description:\
  \ End of time window (ISO 8601 or ms since epoch)\n        - name: timezone\n          in: query\n          type: string\n          required: false\n          description: Timezone for date/time interpretation\n        - name: page-size\n          in: query\n          type: integer\n          required: false\n          description: Number of values per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: timeseries-recent\n      path: /timeseries/recent\n      description: Most recent CWMS time series values\n      operations:\n      - name: get-recent-timeseries\n        method: GET\n        description: Returns the most recent time series values for current conditions\n        inputParameters:\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: Three-character USACE district office code\n        - name: name\n          in: query\n\
  \          type: string\n          required: false\n          description: Time series identifier or wildcard pattern\n        - name: recently-changed-within\n          in: query\n          type: string\n          required: false\n          description: ISO 8601 duration (e.g., PT2H for 2 hours)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: levels\n      path: /levels\n      description: CWMS location levels\n      operations:\n      - name: get-levels\n        method: GET\n        description: Returns location levels including flood stage and normal pool\n        inputParameters:\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: Three-character USACE district office code\n        - name: location-id\n          in: query\n          type: string\n          required: false\n          description: Location identifier\n       \
  \ - name: unit\n          in: query\n          type: string\n          required: false\n          description: 'Unit system: EN or SI'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ratings\n      path: /ratings\n      description: CWMS rating tables\n      operations:\n      - name: get-ratings\n        method: GET\n        description: Returns rating tables for converting between measured values\n        inputParameters:\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: Three-character USACE district office code\n        - name: rating-id\n          in: query\n          type: string\n          required: false\n          description: Rating identifier (supports wildcards)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: basins\n      path:\
  \ /basins\n      description: River basin information\n      operations:\n      - name: get-basins\n        method: GET\n        description: Returns river basin information for USACE water management areas\n        inputParameters:\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: Three-character USACE district office code\n        - name: basin-id\n          in: query\n          type: string\n          required: false\n          description: Basin identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecast-spec\n      path: /forecast-spec\n      description: Forecast specifications\n      operations:\n      - name: get-forecast-specs\n        method: GET\n        description: Returns forecast specifications available in CWMS\n        inputParameters:\n        - name: office\n          in: query\n          type: string\n\
  \          required: false\n          description: Three-character USACE district office code\n        - name: spec-id-mask\n          in: query\n          type: string\n          required: false\n          description: Forecast spec ID filter mask\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecast-instance\n      path: /forecast-instance\n      description: Forecast instances with time series data\n      operations:\n      - name: get-forecast-instances\n        method: GET\n        description: Returns forecast instances with associated time series data\n        inputParameters:\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: Three-character USACE district office code\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Forecast spec name\n        - name:\
  \ forecast-date\n          in: query\n          type: string\n          required: false\n          description: Forecast issue date (ISO 8601)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects\n      description: USACE water resource projects\n      operations:\n      - name: get-projects\n        method: GET\n        description: Returns USACE water resource projects (dams, locks, reservoirs)\n        inputParameters:\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: Three-character USACE district office code\n        - name: id-mask\n          in: query\n          type: string\n          required: false\n          description: Project ID filter mask\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: parameters\n\
  \      path: /parameters\n      description: CWMS physical parameters\n      operations:\n      - name: get-parameters\n        method: GET\n        description: Returns the list of physical parameters in CWMS\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: version\n      path: /version\n      description: API version information\n      operations:\n      - name: get-version\n        method: GET\n        description: Returns the current version of the CWMS Data API\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: usace-water-resources-api\n    description: Unified REST API for USACE water resources management and monitoring.\n    resources:\n    - path: /v1/catalog\n      name: catalog\n      description: Browse available CWMS water data catalog\n      operations:\n\
  \      - method: GET\n        name: get-catalog\n        description: Browse available time series, locations, or ratings in CWMS\n        call: cwms.get-catalog\n        with:\n          datastore-type: rest.datastore-type\n          office: rest.office\n          like: rest.like\n          page-size: rest.page-size\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/locations\n      name: locations\n      description: USACE-managed location data\n      operations:\n      - method: GET\n        name: get-locations\n        description: Get all USACE locations filtered by office or name pattern\n        call: cwms.get-locations\n        with:\n          office: rest.office\n          names: rest.names\n          unit: rest.unit\n          datum: rest.datum\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/locations/{location-id}\n      name: location\n      description: Single USACE location\n      operations:\n\
  \      - method: GET\n        name: get-location\n        description: Get detailed data for a specific USACE location\n        call: cwms.get-location\n        with:\n          location-id: rest.location-id\n          office: rest.office\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/timeseries\n      name: timeseries\n      description: CWMS time series measurements\n      operations:\n      - method: GET\n        name: get-timeseries\n        description: Get time series data for a location (stage, flow, elevation, etc.)\n        call: cwms.get-timeseries\n        with:\n          name: rest.name\n          office: rest.office\n          begin: rest.begin\n          end: rest.end\n          unit: rest.unit\n          timezone: rest.timezone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/timeseries/recent\n      name: recent-conditions\n      description: Current water conditions\n      operations:\n\
  \      - method: GET\n        name: get-recent-timeseries\n        description: Get the most recent readings for current conditions monitoring\n        call: cwms.get-recent-timeseries\n        with:\n          office: rest.office\n          name: rest.name\n          recently-changed-within: rest.recently-changed-within\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/levels\n      name: levels\n      description: Location levels (flood stage, normal pool)\n      operations:\n      - method: GET\n        name: get-levels\n        description: Get location levels for flood stage and pool elevation thresholds\n        call: cwms.get-levels\n        with:\n          office: rest.office\n          location-id: rest.location-id\n          unit: rest.unit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ratings\n      name: ratings\n      description: Stage-discharge rating tables\n      operations:\n      -\
  \ method: GET\n        name: get-ratings\n        description: Get rating tables for converting stage to flow\n        call: cwms.get-ratings\n        with:\n          office: rest.office\n          rating-id: rest.rating-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/forecasts\n      name: forecasts\n      description: Hydrological forecasts\n      operations:\n      - method: GET\n        name: get-forecast-instances\n        description: Get hydrological forecast instances\n        call: cwms.get-forecast-instances\n        with:\n          office: rest.office\n          name: rest.name\n          forecast-date: rest.forecast-date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects\n      name: projects\n      description: USACE water resource projects\n      operations:\n      - method: GET\n        name: get-projects\n        description: Get USACE projects including dams, locks, and reservoirs\n\
  \        call: cwms.get-projects\n        with:\n          office: rest.office\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/basins\n      name: basins\n      description: River basin information\n      operations:\n      - method: GET\n        name: get-basins\n        description: Get river basin information for USACE water management areas\n        call: cwms.get-basins\n        with:\n          office: rest.office\n          basin-id: rest.basin-id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: usace-water-resources-mcp\n    transport: http\n    description: MCP server for AI-assisted USACE water resources monitoring and analysis.\n    tools:\n    - name: browse-water-data-catalog\n      description: Browse the CWMS data catalog to discover available time series, locations, and ratings for USACE water\n        resources\n      hints:\n        readOnly: true\n     \
  \   openWorld: true\n      call: cwms.get-catalog\n      with:\n        datastore-type: tools.datastore-type\n        office: tools.office\n        like: tools.like\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-usace-locations\n      description: Search for USACE-managed locations (dams, reservoirs, stream gages) by name, office, or region\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-locations\n      with:\n        office: tools.office\n        names: tools.names\n        unit: tools.unit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-location-details\n      description: Get detailed information for a specific USACE location including coordinates, elevation, and type\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-location\n      with:\n        location-id: tools.location-id\n        office: tools.office\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-water-measurements\n      description: Get time series measurements (stage, streamflow, reservoir elevation, precipitation) for a USACE location\n        over a time period\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-timeseries\n      with:\n        name: tools.name\n        office: tools.office\n        begin: tools.begin\n        end: tools.end\n        unit: tools.unit\n        timezone: tools.timezone\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-current-water-conditions\n      description: Get the most recent real-time water condition readings for USACE monitoring stations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-recent-timeseries\n      with:\n        office: tools.office\n        name: tools.name\n        recently-changed-within: tools.recently-changed-within\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-flood-stage-levels\n      description: Get flood stage thresholds and normal pool levels for USACE locations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-levels\n      with:\n        office: tools.office\n        location-id: tools.location-id\n        unit: tools.unit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-stage-discharge-ratings\n      description: Get rating curves that convert stage height to streamflow discharge at USACE gages\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-ratings\n      with:\n        office: tools.office\n        rating-id: tools.rating-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-hydrological-forecasts\n      description: Get hydrological forecasts for USACE project areas including flood predictions and reservoir operations\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: cwms.get-forecast-instances\n      with:\n        office: tools.office\n        name: tools.name\n        forecast-date: tools.forecast-date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-usace-projects\n      description: Get information about USACE water resource projects including dams, locks, reservoirs, and flood control\n        structures\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-projects\n      with:\n        office: tools.office\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-river-basins\n      description: Get river basin information for USACE water management regions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-basins\n      with:\n        office: tools.office\n        basin-id: tools.basin-id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
