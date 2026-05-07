---
categories: []
consumed_apis: []
description: Workflow capability for USACE water management operations including reservoir monitoring, flood control, navigation, and water quality. Combines CWMS time series data, location metadata, reservoir pool levels, and field measurements for comprehensive water resource management workflows.
layout: capability
name: USACE Water Management
operations:
- description: Get time series data for a water management location
  method: GET
  name: get-time-series
  path: /v1/timeseries
- description: Browse available time series identifiers
  method: GET
  name: get-time-series-catalog
  path: /v1/timeseries/catalog
- description: Get USACE monitoring locations
  method: GET
  name: get-locations
  path: /v1/locations
- description: Get details for a specific monitoring location
  method: GET
  name: get-location
  path: /v1/locations/{locationId}
- description: Browse all available USACE locations
  method: GET
  name: get-location-catalog
  path: /v1/locations/catalog
- description: Get location levels and flood stage thresholds
  method: GET
  name: get-levels
  path: /v1/levels
- description: Get rating curves for stage to discharge conversion
  method: GET
  name: get-ratings
  path: /v1/ratings
- description: Get USACE water projects
  method: GET
  name: get-projects
  path: /v1/projects
- description: Get reservoir pool storage zones
  method: GET
  name: get-pools
  path: /v1/pools
- description: Get field measurements from hydrographer site visits
  method: GET
  name: get-measurements
  path: /v1/measurements
- description: List USACE district offices
  method: GET
  name: get-offices
  path: /v1/offices
personas: []
provider_name: US Department of Defense
provider_slug: us-department-of-defense
search_terms:
- stage-discharge rating curves
- waterways
- single monitoring location
- get ratings
- usace projects and reservoirs
- browse available time series identifiers
- field measurements
- list usace offices
- get usace water monitoring locations with geographic coordinates and metadata. filter by district office to scope results.
- browse all available usace locations
- get pools
- get levels
- get location levels including flood stage thresholds, flood control pools, and operational levels for usace monitoring locations and reservoirs. essential for flood risk assessment.
- navigation
- get reservoir pool definitions including conservation pool, flood control pool, and surcharge storage zones for usace reservoirs.
- get flood stage levels
- get location
- get locations
- water management time series measurements
- get monitoring locations
- list all usace district offices with their identifiers. use to find the office id needed to scope other queries.
- get reservoir pool storage zones
- get location catalog
- list usace district offices
- searchable location catalog
- get time series catalog
- browse the catalog of available usace time series identifiers. useful for discovering what data is available for a district office before retrieving actual measurements.
- water monitoring locations
- get projects
- get field measurements from hydrographer site visits
- get field measurements collected by usace hydrographers during site visits. these include streamflow discharge measurements used for rating curve development and validation.
- reservoir pool definitions
- location levels and pool data
- browse time series catalog
- get measurements
- get usace water resource projects including reservoirs, navigation projects, and flood control structures with operational parameters.
- get usace water projects
- get stage discharge ratings
- get water time series
- defense
- get rating curves for stage to discharge conversion
- get monitoring location details
- get usace projects
- water management
- reservoirs
- get time series water measurements from a usace monitoring location. retrieves streamflow, stage, reservoir elevation, temperature, and other parameters. specify office, time series name, and time range.
- get details for a specific monitoring location
- get location levels and flood stage thresholds
- get detailed information for a specific usace monitoring location including coordinates, elevation datum, state, county, and description.
- get reservoir pools
- hydrology
- get rating curves used to convert stage (water level) measurements to discharge (streamflow) values. essential for computing streamflow from continuous stage data.
- get usace monitoring locations
- flood control
- get time series data for a water management location
- usace district offices
- federal government
- catalog of available time series
- get offices
- open data
- get field measurements
- get time series
- military
slug: water-management
source_filename: water-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: USACE Water Management\n  description: Workflow capability for USACE water management operations including reservoir monitoring, flood control, navigation,\n    and water quality. Combines CWMS time series data, location metadata, reservoir pool levels, and field measurements for\n    comprehensive water resource management workflows.\n  tags:\n  - Water Management\n  - Hydrology\n  - Reservoirs\n  - Flood Control\n  - Navigation\n  - Federal Government\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys: {}\ncapability:\n  consumes:\n  - type: http\n    namespace: cwms\n    baseUri: https://cwms-data.usace.army.mil/cwms-data/api/latest\n    description: USACE Corps Water Management System Data API\n    resources:\n    - name: timeseries\n      path: /timeseries\n      description: Water management time series data\n      operations:\n      - name: get-time-series\n        method: GET\n        description:\
  \ Get time series data for a location and parameter\n        inputParameters:\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: USACE district office ID\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Time series ID\n        - name: begin\n          in: query\n          type: string\n          required: false\n          description: Start of time window (ISO 8601)\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End of time window (ISO 8601)\n        - name: unit\n          in: query\n          type: string\n          required: false\n          description: Unit system (EN or SI)\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Response format (json, csv, xml)\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: timeseries-catalog\n      path: /timeseries/catalog\n      description: Time series catalog\n      operations:\n      - name: get-time-series-catalog\n        method: GET\n        description: Get catalog of available time series\n        inputParameters:\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: USACE district office ID\n        - name: page-size\n          in: query\n          type: integer\n          required: false\n          description: Number of entries per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: locations\n      path: /locations\n      description: CWMS monitoring locations\n      operations:\n      - name: get-locations\n        method: GET\n        description: Get monitoring locations\n        inputParameters:\n  \
  \      - name: office\n          in: query\n          type: string\n          required: false\n          description: USACE district office ID\n        - name: names\n          in: query\n          type: string\n          required: false\n          description: Pipe-separated list of location IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-location\n        method: GET\n        description: Get a specific monitoring location\n        inputParameters:\n        - name: locationId\n          in: path\n          type: string\n          required: true\n          description: Location identifier\n        - name: office\n          in: query\n          type: string\n          required: true\n          description: USACE district office ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: locations-catalog\n\
  \      path: /locations/catalog\n      description: Location catalog\n      operations:\n      - name: get-location-catalog\n        method: GET\n        description: Get searchable catalog of all locations\n        inputParameters:\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: USACE district office ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ratings\n      path: /ratings\n      description: Rating curves for stage-discharge conversion\n      operations:\n      - name: get-ratings\n        method: GET\n        description: Get rating curves\n        inputParameters:\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: USACE district office ID\n        - name: rating-id-mask\n          in: query\n          type: string\n          required: false\n   \
  \       description: Pattern to filter rating IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: levels\n      path: /levels\n      description: Location levels and pool data\n      operations:\n      - name: get-levels\n        method: GET\n        description: Get location levels and operational thresholds\n        inputParameters:\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: USACE district office ID\n        - name: location-id\n          in: query\n          type: string\n          required: false\n          description: Location identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: offices\n      path: /offices\n      description: USACE district offices\n      operations:\n      - name: get-offices\n        method: GET\n\
  \        description: Get list of USACE district offices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects\n      description: USACE projects and reservoirs\n      operations:\n      - name: get-projects\n        method: GET\n        description: Get USACE projects\n        inputParameters:\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: USACE district office ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: measurements\n      path: /measurements\n      description: Field measurements\n      operations:\n      - name: get-measurements\n        method: GET\n        description: Get field measurements from site visits\n        inputParameters:\n        - name: office\n          in: query\n          type:\
  \ string\n          required: false\n          description: USACE district office ID\n        - name: location-id\n          in: query\n          type: string\n          required: false\n          description: Location identifier\n        - name: begin\n          in: query\n          type: string\n          required: false\n          description: Start of time window\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End of time window\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pools\n      path: /pools\n      description: Reservoir pool definitions\n      operations:\n      - name: get-pools\n        method: GET\n        description: Get reservoir pool definitions\n        inputParameters:\n        - name: office\n          in: query\n          type: string\n          required: false\n          description: USACE district office\
  \ ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: water-management-api\n    description: Unified REST API for USACE water management data and monitoring.\n    resources:\n    - path: /v1/timeseries\n      name: timeseries\n      description: Water management time series measurements\n      operations:\n      - method: GET\n        name: get-time-series\n        description: Get time series data for a water management location\n        call: cwms.get-time-series\n        with:\n          office: rest.office\n          name: rest.name\n          begin: rest.begin\n          end: rest.end\n          unit: rest.unit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/timeseries/catalog\n      name: timeseries-catalog\n      description: Catalog of available time series\n      operations:\n      - method: GET\n \
  \       name: get-time-series-catalog\n        description: Browse available time series identifiers\n        call: cwms.get-time-series-catalog\n        with:\n          office: rest.office\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/locations\n      name: locations\n      description: Water monitoring locations\n      operations:\n      - method: GET\n        name: get-locations\n        description: Get USACE monitoring locations\n        call: cwms.get-locations\n        with:\n          office: rest.office\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/locations/{locationId}\n      name: location\n      description: Single monitoring location\n      operations:\n      - method: GET\n        name: get-location\n        description: Get details for a specific monitoring location\n        call: cwms.get-location\n        with:\n          locationId: rest.locationId\n          office: rest.office\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/locations/catalog\n      name: locations-catalog\n      description: Searchable location catalog\n      operations:\n      - method: GET\n        name: get-location-catalog\n        description: Browse all available USACE locations\n        call: cwms.get-location-catalog\n        with:\n          office: rest.office\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/levels\n      name: levels\n      description: Location levels and pool data\n      operations:\n      - method: GET\n        name: get-levels\n        description: Get location levels and flood stage thresholds\n        call: cwms.get-levels\n        with:\n          office: rest.office\n          location-id: rest.location_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ratings\n      name: ratings\n      description: Stage-discharge rating curves\n\
  \      operations:\n      - method: GET\n        name: get-ratings\n        description: Get rating curves for stage to discharge conversion\n        call: cwms.get-ratings\n        with:\n          office: rest.office\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects\n      name: projects\n      description: USACE projects and reservoirs\n      operations:\n      - method: GET\n        name: get-projects\n        description: Get USACE water projects\n        call: cwms.get-projects\n        with:\n          office: rest.office\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pools\n      name: pools\n      description: Reservoir pool definitions\n      operations:\n      - method: GET\n        name: get-pools\n        description: Get reservoir pool storage zones\n        call: cwms.get-pools\n        with:\n          office: rest.office\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n    - path: /v1/measurements\n      name: measurements\n      description: Field measurements\n      operations:\n      - method: GET\n        name: get-measurements\n        description: Get field measurements from hydrographer site visits\n        call: cwms.get-measurements\n        with:\n          office: rest.office\n          location-id: rest.location_id\n          begin: rest.begin\n          end: rest.end\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/offices\n      name: offices\n      description: USACE district offices\n      operations:\n      - method: GET\n        name: get-offices\n        description: List USACE district offices\n        call: cwms.get-offices\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: water-management-mcp\n    transport: http\n    description: MCP server for AI-assisted USACE water management monitoring, flood\
  \ risk analysis, and reservoir operations.\n    tools:\n    - name: get-water-time-series\n      description: Get time series water measurements from a USACE monitoring location. Retrieves streamflow, stage, reservoir\n        elevation, temperature, and other parameters. Specify office, time series name, and time range.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-time-series\n      with:\n        office: tools.office\n        name: tools.name\n        begin: tools.begin\n        end: tools.end\n        unit: tools.unit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: browse-time-series-catalog\n      description: Browse the catalog of available USACE time series identifiers. Useful for discovering what data is available\n        for a district office before retrieving actual measurements.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-time-series-catalog\n      with:\n      \
  \  office: tools.office\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-monitoring-locations\n      description: Get USACE water monitoring locations with geographic coordinates and metadata. Filter by district office\n        to scope results.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-locations\n      with:\n        office: tools.office\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-monitoring-location-details\n      description: Get detailed information for a specific USACE monitoring location including coordinates, elevation datum,\n        state, county, and description.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: cwms.get-location\n      with:\n        locationId: tools.location_id\n        office: tools.office\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-flood-stage-levels\n      description:\
  \ Get location levels including flood stage thresholds, flood control pools, and operational levels for USACE\n        monitoring locations and reservoirs. Essential for flood risk assessment.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-levels\n      with:\n        office: tools.office\n        location-id: tools.location_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-stage-discharge-ratings\n      description: Get rating curves used to convert stage (water level) measurements to discharge (streamflow) values. Essential\n        for computing streamflow from continuous stage data.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-ratings\n      with:\n        office: tools.office\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-usace-projects\n      description: Get USACE water resource projects including reservoirs, navigation projects,\
  \ and flood control structures\n        with operational parameters.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-projects\n      with:\n        office: tools.office\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-reservoir-pools\n      description: Get reservoir pool definitions including conservation pool, flood control pool, and surcharge storage zones\n        for USACE reservoirs.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-pools\n      with:\n        office: tools.office\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-field-measurements\n      description: Get field measurements collected by USACE hydrographers during site visits. These include streamflow discharge\n        measurements used for rating curve development and validation.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-measurements\n\
  \      with:\n        office: tools.office\n        location-id: tools.location_id\n        begin: tools.begin\n        end: tools.end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-usace-offices\n      description: List all USACE district offices with their identifiers. Use to find the office ID needed to scope other\n        queries.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cwms.get-offices\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/us-department-of-defense/refs/heads/main/capabilities/water-management.yaml
tags:
- Water Management
- Hydrology
- Reservoirs
- Flood Control
- Navigation
- Federal Government
tools:
- description: Get time series water measurements from a USACE monitoring location. Retrieves streamflow, stage, reservoir elevation, temperature, and other parameters. Specify office, time series name, and time range.
  hints:
    openWorld: true
    readOnly: true
  name: get-water-time-series
- description: Browse the catalog of available USACE time series identifiers. Useful for discovering what data is available for a district office before retrieving actual measurements.
  hints:
    openWorld: true
    readOnly: true
  name: browse-time-series-catalog
- description: Get USACE water monitoring locations with geographic coordinates and metadata. Filter by district office to scope results.
  hints:
    openWorld: true
    readOnly: true
  name: get-monitoring-locations
- description: Get detailed information for a specific USACE monitoring location including coordinates, elevation datum, state, county, and description.
  hints:
    openWorld: false
    readOnly: true
  name: get-monitoring-location-details
- description: Get location levels including flood stage thresholds, flood control pools, and operational levels for USACE monitoring locations and reservoirs. Essential for flood risk assessment.
  hints:
    openWorld: true
    readOnly: true
  name: get-flood-stage-levels
- description: Get rating curves used to convert stage (water level) measurements to discharge (streamflow) values. Essential for computing streamflow from continuous stage data.
  hints:
    openWorld: true
    readOnly: true
  name: get-stage-discharge-ratings
- description: Get USACE water resource projects including reservoirs, navigation projects, and flood control structures with operational parameters.
  hints:
    openWorld: true
    readOnly: true
  name: get-usace-projects
- description: Get reservoir pool definitions including conservation pool, flood control pool, and surcharge storage zones for USACE reservoirs.
  hints:
    openWorld: true
    readOnly: true
  name: get-reservoir-pools
- description: Get field measurements collected by USACE hydrographers during site visits. These include streamflow discharge measurements used for rating curve development and validation.
  hints:
    openWorld: true
    readOnly: true
  name: get-field-measurements
- description: List all USACE district offices with their identifiers. Use to find the office ID needed to scope other queries.
  hints:
    openWorld: true
    readOnly: true
  name: list-usace-offices
---
