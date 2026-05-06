---
categories: []
consumed_apis: []
description: OpenAQ is a nonprofit organization providing universal access to air quality data to empower a global community of changemakers to solve air inequality-the unequal access to clean air.
layout: capability
name: OpenAQ
operations:
- description: OpenAQ Get an instrument by ID
  method: GET
  name: instrument-get-v3-instruments-instruments-id-get
  path: /v3/instruments/{instruments_id}
- description: OpenAQ Get instruments
  method: GET
  name: instruments-get-v3-instruments-get
  path: /v3/instruments
- description: OpenAQ Get instruments by manufacturer ID
  method: GET
  name: get-instruments-by-manufacturer-v3-manufacturers
  path: /v3/manufacturers/{manufacturers_id}/instruments
- description: OpenAQ Get a location by ID
  method: GET
  name: location-get-v3-locations-locations-id-get
  path: /v3/locations/{locations_id}
- description: OpenAQ Get locations
  method: GET
  name: locations-get-v3-locations-get
  path: /v3/locations
- description: OpenAQ Get an instrument by ID
  method: GET
  name: license-get-v3-licenses-licenses-id-get
  path: /v3/licenses/{licenses_id}
- description: OpenAQ Get licenses
  method: GET
  name: instruments-get-v3-licenses-get
  path: /v3/licenses
- description: OpenAQ Get a parameter by ID
  method: GET
  name: parameter-get-v3-parameters-parameters-id-get
  path: /v3/parameters/{parameters_id}
- description: OpenAQ Get a parameters
  method: GET
  name: parameters-get-v3-parameters-get
  path: /v3/parameters
- description: OpenAQ Get a country by ID
  method: GET
  name: country-get-v3-countries-countries-id-get
  path: /v3/countries/{countries_id}
- description: OpenAQ Get countries
  method: GET
  name: countries-get-v3-countries-get
  path: /v3/countries
- description: OpenAQ Get a manufacturer by ID
  method: GET
  name: manufacturer-get-v3-manufacturers-manufacturers-
  path: /v3/manufacturers/{manufacturers_id}
- description: OpenAQ Get manufacturers
  method: GET
  name: manufacturers-get-v3-manufacturers-get
  path: /v3/manufacturers
- description: OpenAQ Get measurements by sensor ID
  method: GET
  name: sensor-measurements-get-v3-sensors-sensors-id-me
  path: /v3/sensors/{sensors_id}/measurements
- description: OpenAQ Get measurements aggregated to hours by sensor ID
  method: GET
  name: sensor-measurements-aggregated-get-hourly-v3-sen
  path: /v3/sensors/{sensors_id}/measurements/hourly
- description: OpenAQ Get measurements aggregated to days by sensor ID
  method: GET
  name: sensor-measurements-aggregated-get-daily-v3-sens
  path: /v3/sensors/{sensors_id}/measurements/daily
- description: OpenAQ Get measurements aggregated to hour by sensor ID
  method: GET
  name: sensor-hourly-measurements-get-v3-sensors-sensor
  path: /v3/sensors/{sensors_id}/hours
- description: OpenAQ Get measurements aggregated from hour to day by sensor ID
  method: GET
  name: sensor-hourly-measurements-aggregate-to-day-get-
  path: /v3/sensors/{sensors_id}/hours/daily
- description: OpenAQ Get measurements aggregated from hour to month by sensor ID
  method: GET
  name: sensor-hourly-measurements-aggregate-to-month-ge
  path: /v3/sensors/{sensors_id}/hours/monthly
- description: OpenAQ Get measurements aggregated from hour to year by sensor ID
  method: GET
  name: sensor-hourly-measurements-aggregate-to-year-get
  path: /v3/sensors/{sensors_id}/hours/yearly
- description: OpenAQ Get measurements aggregated from hour to day of week by sensor ID
  method: GET
  name: sensor-hourly-measurements-aggregate-to-hod-get-
  path: /v3/sensors/{sensors_id}/hours/hourofday
- description: OpenAQ Get measurements aggregated from hour to day of week by sensor ID
  method: GET
  name: sensor-hourly-measurements-aggregate-to-dow-get-
  path: /v3/sensors/{sensors_id}/hours/dayofweek
- description: OpenAQ Get measurements aggregated from hour to day of week by sensor ID
  method: GET
  name: sensor-hourly-measurements-aggregate-to-moy-get-
  path: /v3/sensors/{sensors_id}/hours/monthofyear
- description: OpenAQ Get measurements aggregated from day to day of week by sensor ID
  method: GET
  name: sensor-daily-measurements-aggregate-to-dow-get-v
  path: /v3/sensors/{sensors_id}/days/dayofweek
- description: OpenAQ Get measurements aggregated from day to day of week by sensor ID
  method: GET
  name: sensor-daily-measurements-aggregate-to-moy-get-v
  path: /v3/sensors/{sensors_id}/days/monthofyear
- description: OpenAQ Get measurements aggregated to day by sensor ID
  method: GET
  name: sensor-daily-get-v3-sensors-sensors-id-days-get
  path: /v3/sensors/{sensors_id}/days
- description: OpenAQ Get measurements aggregated from hour to month by sensor ID
  method: GET
  name: sensor-daily-aggregate-to-month-get-v3-sensors-s
  path: /v3/sensors/{sensors_id}/days/monthly
- description: OpenAQ Get measurements aggregated from day to year by sensor ID
  method: GET
  name: sensor-daily-aggregate-to-year-get-v3-sensors-se
  path: /v3/sensors/{sensors_id}/days/yearly
- description: OpenAQ Get measurements aggregated to year by sensor ID
  method: GET
  name: sensor-yearly-get-v3-sensors-sensors-id-years-ge
  path: /v3/sensors/{sensors_id}/years
- description: OpenAQ Get a owner by ID
  method: GET
  name: owner-get-v3-owners-owners-id-get
  path: /v3/owners/{owners_id}
- description: OpenAQ Get owners
  method: GET
  name: owners-get-v3-owners-get
  path: /v3/owners
- description: OpenAQ Get a provider by ID
  method: GET
  name: provider-get-v3-providers-providers-id-get
  path: /v3/providers/{providers_id}
- description: OpenAQ Get providers
  method: GET
  name: providers-get-v3-providers-get
  path: /v3/providers
- description: OpenAQ Get sensors by location ID
  method: GET
  name: sensors-get-v3-locations-locations-id-sensors-ge
  path: /v3/locations/{locations_id}/sensors
- description: OpenAQ Get a sensor by ID
  method: GET
  name: sensor-get-v3-sensors-sensors-id-get
  path: /v3/sensors/{sensors_id}
- description: OpenAQ Parameters Latest Get
  method: GET
  name: parameters-latest-get-v3-parameters-parameters-i
  path: /v3/parameters/{parameters_id}/latest
- description: OpenAQ Get a location's latest measurements
  method: GET
  name: location-latest-get-v3-locations-locations-id-la
  path: /v3/locations/{locations_id}/latest
- description: OpenAQ Get flags by location ID
  method: GET
  name: location-flags-get-v3-locations-locations-id-fla
  path: /v3/locations/{locations_id}/flags
- description: OpenAQ Get flags by sensor ID
  method: GET
  name: sensor-flags-get-v3-sensors-sensor-id-flags-get
  path: /v3/sensors/{sensor_id}/flags
- description: OpenAQ Get averaged values
  method: GET
  name: averages-v2-get-v2-averages-get
  path: /v2/averages
- description: OpenAQ Get cities
  method: GET
  name: cities-get-v2-cities-get
  path: /v2/cities
- description: OpenAQ Get cities
  method: GET
  name: cities-getv1-v1-cities-get
  path: /v1/cities
- description: OpenAQ Get country by ID
  method: GET
  name: countries-by-path-v2-countries-country-id-get
  path: /v2/countries/{country_id}
- description: OpenAQ Get country by ID
  method: GET
  name: countries-by-path-v1-countries-country-id-get
  path: /v1/countries/{country_id}
- description: OpenAQ Get countries
  method: GET
  name: countries-get-v2-countries-get
  path: /v2/countries
- description: OpenAQ Get countries
  method: GET
  name: countries-getv1-v1-countries-get
  path: /v1/countries
- description: OpenAQ Get a location by ID
  method: GET
  name: get-v2-location-by-id-v2-locations-location-id-g
  path: /v2/locations/{location_id}
- description: OpenAQ Get locations
  method: GET
  name: locations-get-v2-locations-get
  path: /v2/locations
- description: OpenAQ Get latest measurements by location ID
  method: GET
  name: get-v2-latest-by-id-v2-latest-location-id-get
  path: /v2/latest/{location_id}
- description: OpenAQ Get latest measurements
  method: GET
  name: latest-get-v2-latest-get
  path: /v2/latest
- description: OpenAQ Get latest measurements by location ID
  method: GET
  name: get-v1-latest-by-id-v1-latest-location-id-get
  path: /v1/latest/{location_id}
- description: OpenAQ Get latest measurements
  method: GET
  name: latest-v1-get-v1-latest-get
  path: /v1/latest
- description: OpenAQ Get location by ID
  method: GET
  name: get-v1-locations-by-id-v1-locations-location-id-
  path: /v1/locations/{location_id}
- description: OpenAQ Get locations
  method: GET
  name: locationsv1-get-v1-locations-get
  path: /v1/locations
- description: OpenAQ Get measurements
  method: GET
  name: measurements-get-v2-measurements-get
  path: /v2/measurements
- description: OpenAQ Get a list of measurements
  method: GET
  name: measurements-get-v1-v1-measurements-get
  path: /v1/measurements
- description: OpenAQ Get parameters
  method: GET
  name: parameters-get-v2-parameters-get
  path: /v2/parameters
- description: OpenAQ Get parameters
  method: GET
  name: parameters-getv1-v1-parameters-get
  path: /v1/parameters
- description: OpenAQ Project by ID
  method: GET
  name: projects-get-v2-projects-project-id-get
  path: /v2/projects/{project_id}
- description: OpenAQ Projects
  method: GET
  name: projects-get-v2-projects-get
  path: /v2/projects
personas: []
provider_name: OpenAQ
provider_slug: openaq
search_terms:
- get v1 locations by id v1 locations location id
- sensor hourly measurements get v3 sensors sensor
- sensor hourly measurements aggregate to dow get
- sensor daily get v3 sensors sensors id days get
- location latest get v3 locations locations id la
- sensor hourly measurements aggregate to day get
- openaq get a list of measurements
- sensor hourly measurements aggregate to year get
- parameters get v2 parameters get
- data quality
- openaq get manufacturers
- openaq get a country by id
- openaq get a parameter by id
- measurements get v1 v1 measurements get
- openaq get a sensor by id
- openaq get a location's latest measurements
- sensor hourly measurements aggregate to month ge
- openaq get a owner by id
- openaq projects
- api
- openaq get a parameters
- openaq get countries
- get v1 latest by id v1 latest location id get
- openaq get instruments
- countries getv1 v1 countries get
- openaq get averaged values
- data
- sensor daily measurements aggregate to moy get v
- openaq get an instrument by id
- openaq get location by id
- get v2 latest by id v2 latest location id get
- sensor flags get v3 sensors sensor id flags get
- country get v3 countries countries id get
- license get v3 licenses licenses id get
- sensor measurements get v3 sensors sensors id me
- sensor measurements aggregated get hourly v3 sen
- sensors get v3 locations locations id sensors ge
- countries get v2 countries get
- latest v1 get v1 latest get
- instruments get v3 instruments get
- openaq get licenses
- manufacturers get v3 manufacturers get
- openaq get flags by sensor id
- openaq get measurements aggregated to year by sensor id
- openaq get latest measurements
- openaq get flags by location id
- parameters get v3 parameters get
- averages v2 get v2 averages get
- cities getv1 v1 cities get
- openaq get measurements aggregated to day by sensor id
- location flags get v3 locations locations id fla
- openaq get measurements by sensor id
- openaq get measurements aggregated from hour to day by sensor id
- openaq
- countries get v3 countries get
- countries by path v2 countries country id get
- locationsv1 get v1 locations get
- provider get v3 providers providers id get
- openaq get measurements aggregated from hour to day of week by sensor id
- locations get v2 locations get
- openaq get instruments by manufacturer id
- location get v3 locations locations id get
- openaq get providers
- openaq get measurements aggregated from hour to month by sensor id
- instruments get v3 licenses get
- openaq get a location by id
- openaq get measurements aggregated to hours by sensor id
- locations get v3 locations get
- openaq parameters latest get
- projects get v2 projects get
- sensor daily aggregate to month get v3 sensors s
- openaq get a provider by id
- openaq get cities
- get instruments by manufacturer v3 manufacturers
- countries by path v1 countries country id get
- openaq get measurements aggregated from day to day of week by sensor id
- openaq get owners
- owners get v3 owners get
- openaq get latest measurements by location id
- openaq get sensors by location id
- openaq get locations
- sensor get v3 sensors sensors id get
- providers get v3 providers get
- sensor measurements aggregated get daily v3 sens
- sensor yearly get v3 sensors sensors id years ge
- cities get v2 cities get
- openaq get parameters
- openaq get measurements aggregated to hour by sensor id
- openaq get measurements
- parameters getv1 v1 parameters get
- parameters latest get v3 parameters parameters i
- openaq get a manufacturer by id
- sensor hourly measurements aggregate to hod get
- projects get v2 projects project id get
- measurements get v2 measurements get
- owner get v3 owners owners id get
- get v2 location by id v2 locations location id g
- openaq get measurements aggregated from day to year by sensor id
- sensor daily aggregate to year get v3 sensors se
- openaq get measurements aggregated to days by sensor id
- latest get v2 latest get
- openaq get country by id
- sensor daily measurements aggregate to dow get v
- openaq project by id
- parameter get v3 parameters parameters id get
- openaq get measurements aggregated from hour to year by sensor id
- sensor hourly measurements aggregate to moy get
- instrument get v3 instruments instruments id get
- manufacturer get v3 manufacturers manufacturers
slug: openaq-capability
source_filename: openaq-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenAQ\n  description: OpenAQ is a nonprofit organization providing universal access to air quality data to empower a global community\n    of changemakers to solve air inequality-the unequal access to clean air.\n  tags:\n  - Openaq\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: openaq\n    baseUri: https://api.example.com\n    description: OpenAQ HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{OPENAQ_TOKEN}}'\n    resources:\n    - name: v3-instruments-instruments-id\n      path: /v3/instruments/{instruments_id}\n      operations:\n      - name: instrument-get-v3-instruments-instruments-id-get\n        method: GET\n        description: OpenAQ Get an instrument by ID\n        inputParameters:\n        - name: instruments_id\n          in: path\n          type: integer\n          required: true\n         \
  \ description: Limit the results to a specific instruments id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-instruments\n      path: /v3/instruments\n      operations:\n      - name: instruments-get-v3-instruments-get\n        method: GET\n        description: OpenAQ Get instruments\n        inputParameters:\n        - name: order_by\n          in: query\n          type: string\n          description: The field by which to order results\n        - name: sort_order\n          in: query\n          type: string\n          description: Sort results ascending or descending. Default ASC\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return\
  \ first page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-manufacturers-manufacturers-id-instruments\n      path: /v3/manufacturers/{manufacturers_id}/instruments\n      operations:\n      - name: get-instruments-by-manufacturer-v3-manufacturers\n        method: GET\n        description: OpenAQ Get instruments by manufacturer ID\n        inputParameters:\n        - name: manufacturers_id\n          in: path\n          type: integer\n          required: true\n          description: Limit results to a specific manufacturer id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-locations-locations-id\n      path: /v3/locations/{locations_id}\n      operations:\n      - name: location-get-v3-locations-locations-id-get\n        method: GET\n        description: OpenAQ Get a location by ID\n   \
  \     inputParameters:\n        - name: locations_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific location by id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-locations\n      path: /v3/locations\n      operations:\n      - name: locations-get-v3-locations-get\n        method: GET\n        description: OpenAQ Get locations\n        inputParameters:\n        - name: coordinates\n          in: query\n          type: string\n          description: WGS 84 Coordinate pair in form latitude,longitude. Supports up to 4 decimal points of precision, additional\n            decimal precision will be truncated in the query e.g\n        - name: radius\n          in: query\n          type: string\n          description: Search radius from coordinates as center in meters. Maximum of 25,000 (25km) defaults to 1000 (1km)\n   \
  \         e.g. radius=1000\n        - name: providers_id\n          in: query\n          type: string\n          description: Limit the results to a specific provider or multiple providers with a single provider ID or a comma\n            delimited list of IDs\n        - name: parameters_id\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        - name: owner_contacts_id\n          in: query\n          type: string\n          description: Limit the results to a specific owner by owner ID with a single owner ID or comma delimited list of\n            IDs\n        - name: manufacturers_id\n          in: query\n          type: string\n        - name: order_by\n\
  \          in: query\n          type: string\n          description: The field by which to order results\n        - name: sort_order\n          in: query\n          type: string\n          description: Sort results ascending or descending. Default ASC\n        - name: licenses_id\n          in: query\n          type: string\n        - name: monitor\n          in: query\n          type: string\n          description: Is the location considered a reference monitor?\n        - name: mobile\n          in: query\n          type: string\n          description: Is the location considered a mobile location?\n        - name: instruments_id\n          in: query\n          type: string\n        - name: iso\n          in: query\n          type: string\n          description: Limit the results to a specific country using ISO 3166-1 alpha-2 code\n        - name: countries_id\n          in: query\n          type: string\n          description: Limit the results to a specific country or countries by country\
  \ ID as a single country ID or a comma\n            delimited list of IDs\n        - name: bbox\n          in: query\n          type: string\n          description: 'geospatial bounding box of Min X, min Y, max X, max Y in WGS 84 coordinates. Up to 4 decimal points\n            of precision, addtional decimal precision will be truncated '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-licenses-licenses-id\n      path: /v3/licenses/{licenses_id}\n      operations:\n      - name: license-get-v3-licenses-licenses-id-get\n        method: GET\n        description: OpenAQ Get an instrument by ID\n        inputParameters:\n        - name: licenses_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific licenses id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n    - name: v3-licenses\n      path: /v3/licenses\n      operations:\n      - name: instruments-get-v3-licenses-get\n        method: GET\n        description: OpenAQ Get licenses\n        inputParameters:\n        - name: order_by\n          in: query\n          type: string\n          description: The field by which to order results\n        - name: sort_order\n          in: query\n          type: string\n          description: Sort results ascending or descending. Default ASC\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-parameters-parameters-id\n\
  \      path: /v3/parameters/{parameters_id}\n      operations:\n      - name: parameter-get-v3-parameters-parameters-id-get\n        method: GET\n        description: OpenAQ Get a parameter by ID\n        inputParameters:\n        - name: parameters_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific parameters id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-parameters\n      path: /v3/parameters\n      operations:\n      - name: parameters-get-v3-parameters-get\n        method: GET\n        description: OpenAQ Get a parameters\n        inputParameters:\n        - name: order_by\n          in: query\n          type: string\n          description: The field by which to order results\n        - name: sort_order\n          in: query\n          type: string\n          description: Sort results ascending or descending.\
  \ Default ASC\n        - name: parameter_type\n          in: query\n          type: string\n          description: Limit the results to a specific parameters type\n        - name: coordinates\n          in: query\n          type: string\n          description: WGS 84 Coordinate pair in form latitude,longitude. Supports up to 4 decimal points of precision, additional\n            decimal precision will be truncated in the query e.g\n        - name: radius\n          in: query\n          type: string\n          description: Search radius from coordinates as center in meters. Maximum of 25,000 (25km) defaults to 1000 (1km)\n            e.g. radius=1000\n        - name: bbox\n          in: query\n          type: string\n          description: 'geospatial bounding box of Min X, min Y, max X, max Y in WGS 84 coordinates. Up to 4 decimal points\n            of precision, addtional decimal precision will be truncated '\n        - name: iso\n          in: query\n          type: string\n       \
  \   description: Limit the results to a specific country using ISO 3166-1 alpha-2 code\n        - name: countries_id\n          in: query\n          type: string\n          description: Limit the results to a specific country or countries by country ID as a single country ID or a comma\n            delimited list of IDs\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-countries-countries-id\n      path: /v3/countries/{countries_id}\n      operations:\n      - name: country-get-v3-countries-countries-id-get\n        method: GET\n        description: OpenAQ Get\
  \ a country by ID\n        inputParameters:\n        - name: countries_id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-countries\n      path: /v3/countries\n      operations:\n      - name: countries-get-v3-countries-get\n        method: GET\n        description: OpenAQ Get countries\n        inputParameters:\n        - name: order_by\n          in: query\n          type: string\n          description: The field by which to order results\n        - name: sort_order\n          in: query\n          type: string\n          description: Sort results ascending or descending. Default ASC\n        - name: providers_id\n          in: query\n          type: string\n          description: Limit the results to a specific provider or multiple providers with a single provider ID or a comma\n            delimited list of IDs\n      \
  \  - name: parameters_id\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-manufacturers-manufacturers-id\n      path: /v3/manufacturers/{manufacturers_id}\n      operations:\n      - name: manufacturer-get-v3-manufacturers-manufacturers-\n        method: GET\n        description: OpenAQ Get a manufacturer by ID\n        inputParameters:\n        - name: manufacturers_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific manufacturers id\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-manufacturers\n      path: /v3/manufacturers\n      operations:\n      - name: manufacturers-get-v3-manufacturers-get\n        method: GET\n        description: OpenAQ Get manufacturers\n        inputParameters:\n        - name: order_by\n          in: query\n          type: string\n          description: The field by which to order results\n        - name: sort_order\n          in: query\n          type: string\n          description: Sort results ascending or descending. Default ASC\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-measurements\n      path: /v3/sensors/{sensors_id}/measurements\n      operations:\n      - name: sensor-measurements-get-v3-sensors-sensors-id-me\n        method: GET\n        description: OpenAQ Get measurements by sensor ID\n        inputParameters:\n        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific sensors id\n        - name: datetime_to\n          in: query\n          type: string\n          description: To when?\n        - name: datetime_from\n          in: query\n          type: string\n          description: From when?\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type:\
  \ integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-measurements-hourly\n      path: /v3/sensors/{sensors_id}/measurements/hourly\n      operations:\n      - name: sensor-measurements-aggregated-get-hourly-v3-sen\n        method: GET\n        description: OpenAQ Get measurements aggregated to hours by sensor ID\n        inputParameters:\n        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific sensors id\n        - name: datetime_to\n          in: query\n          type: string\n          description: To when?\n        - name: datetime_from\n          in: query\n          type: string\n          description: From when?\n        - name: limit\n          in: query\n          type:\
  \ integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-measurements-daily\n      path: /v3/sensors/{sensors_id}/measurements/daily\n      operations:\n      - name: sensor-measurements-aggregated-get-daily-v3-sens\n        method: GET\n        description: OpenAQ Get measurements aggregated to days by sensor ID\n        inputParameters:\n        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific sensors id\n        - name: datetime_to\n          in: query\n          type: string\n          description: To when?\n\
  \        - name: datetime_from\n          in: query\n          type: string\n          description: From when?\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-hours\n      path: /v3/sensors/{sensors_id}/hours\n      operations:\n      - name: sensor-hourly-measurements-get-v3-sensors-sensor\n        method: GET\n        description: OpenAQ Get measurements aggregated to hour by sensor ID\n        inputParameters:\n        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n          description: Limit\
  \ the results to a specific sensors id\n        - name: datetime_to\n          in: query\n          type: string\n          description: To when?\n        - name: datetime_from\n          in: query\n          type: string\n          description: From when?\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-hours-daily\n      path: /v3/sensors/{sensors_id}/hours/daily\n      operations:\n      - name: sensor-hourly-measurements-aggregate-to-day-get-\n        method: GET\n        description: OpenAQ Get measurements aggregated from hour to day\
  \ by sensor ID\n        inputParameters:\n        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific sensors id\n        - name: datetime_to\n          in: query\n          type: string\n          description: To when?\n        - name: datetime_from\n          in: query\n          type: string\n          description: From when?\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-hours-monthly\n      path: /v3/sensors/{sensors_id}/hours/monthly\n    \
  \  operations:\n      - name: sensor-hourly-measurements-aggregate-to-month-ge\n        method: GET\n        description: OpenAQ Get measurements aggregated from hour to month by sensor ID\n        inputParameters:\n        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific sensors id\n        - name: datetime_to\n          in: query\n          type: string\n          description: To when?\n        - name: datetime_from\n          in: query\n          type: string\n          description: From when?\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-hours-yearly\n      path: /v3/sensors/{sensors_id}/hours/yearly\n      operations:\n      - name: sensor-hourly-measurements-aggregate-to-year-get\n        method: GET\n        description: OpenAQ Get measurements aggregated from hour to year by sensor ID\n        inputParameters:\n        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific sensors id\n        - name: datetime_to\n          in: query\n          type: string\n          description: To when?\n        - name: datetime_from\n          in: query\n          type: string\n          description: From when?\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n        \
  \  type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-hours-hourofday\n      path: /v3/sensors/{sensors_id}/hours/hourofday\n      operations:\n      - name: sensor-hourly-measurements-aggregate-to-hod-get-\n        method: GET\n        description: OpenAQ Get measurements aggregated from hour to day of week by sensor ID\n        inputParameters:\n        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific sensors id\n        - name: datetime_to\n          in: query\n          type: string\n          description: To when?\n        - name: datetime_from\n          in: query\n          type: string\n          description: From when?\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-hours-dayofweek\n      path: /v3/sensors/{sensors_id}/hours/dayofweek\n      operations:\n      - name: sensor-hourly-measurements-aggregate-to-dow-get-\n        method: GET\n        description: OpenAQ Get measurements aggregated from hour to day of week by sensor ID\n        inputParameters:\n        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific sensors id\n        - name: datetime_to\n          in: query\n          type: string\n          description: To when?\n        - name: datetime_from\n          in: query\n          type: string\n          description: From when?\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-hours-monthofyear\n      path: /v3/sensors/{sensors_id}/hours/monthofyear\n\
  \      operations:\n      - name: sensor-hourly-measurements-aggregate-to-moy-get-\n        method: GET\n        description: OpenAQ Get measurements aggregated from hour to day of week by sensor ID\n        inputParameters:\n        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific sensors id\n        - name: datetime_to\n          in: query\n          type: string\n          description: To when?\n        - name: datetime_from\n          in: query\n          type: string\n          description: From when?\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-days-dayofweek\n      path: /v3/sensors/{sensors_id}/days/dayofweek\n      operations:\n      - name: sensor-daily-measurements-aggregate-to-dow-get-v\n        method: GET\n        description: OpenAQ Get measurements aggregated\
  \ from day to day of week by sensor ID\n        inputParameters:\n        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific sensors id\n        - name: date_to\n          in: query\n          type: string\n          description: To when?\n        - name: date_from\n          in: query\n          type: string\n          description: From when?\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-days-monthofyear\n      path: /v3/sensors/{sensors_id}/days/monthofyear\n      operations:\n      - name: sensor-daily-measurements-aggregate-to-moy-get-v\n        method: GET\n        description: OpenAQ Get measurements aggregated from day to day of week by sensor ID\n        inputParameters:\n        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n\
  \          description: Limit the results to a specific sensors id\n        - name: date_to\n          in: query\n          type: string\n          description: To when?\n        - name: date_from\n          in: query\n          type: string\n          description: From when?\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-days\n      path: /v3/sensors/{sensors_id}/days\n      operations:\n      - name: sensor-daily-get-v3-sensors-sensors-id-days-get\n        method: GET\n        description: OpenAQ Get measurements aggregated to day by sensor ID\n        inputParameters:\n        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific sensors id\n        - name: date_to\n          in: query\n          type: string\n          description: To when?\n        - name: date_from\n         \
  \ in: query\n          type: string\n          description: From when?\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-days-monthly\n      path: /v3/sensors/{sensors_id}/days/monthly\n      operations:\n      - name: sensor-daily-aggregate-to-month-get-v3-sensors-s\n        method: GET\n        description: OpenAQ Get measurements aggregated from hour to month by sensor ID\n        inputParameters:\n        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to\
  \ a specific sensors id\n        - name: date_to\n          in: query\n          type: string\n          description: To when?\n        - name: date_from\n          in: query\n          type: string\n          description: From when?\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-days-yearly\n      path: /v3/sensors/{sensors_id}/days/yearly\n      operations:\n      - name: sensor-daily-aggregate-to-year-get-v3-sensors-se\n        method: GET\n        description: OpenAQ Get measurements aggregated from day to year by sensor ID\n        inputParameters:\n\
  \        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific sensors id\n        - name: date_to\n          in: query\n          type: string\n          description: To when?\n        - name: date_from\n          in: query\n          type: string\n          description: From when?\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-sensors-sensors-id-years\n      path: /v3/sensors/{sensors_id}/years\n      operations:\n      - name: sensor-yearly-get-v3-sensors-sensors-id-years-ge\n\
  \        method: GET\n        description: OpenAQ Get measurements aggregated to year by sensor ID\n        inputParameters:\n        - name: sensors_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific sensors id\n        - name: date_to\n          in: query\n          type: string\n          description: To when?\n        - name: date_from\n          in: query\n          type: string\n          description: From when?\n        - name: limit\n          in: query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-owners-owners-id\n\
  \      path: /v3/owners/{owners_id}\n      operations:\n      - name: owner-get-v3-owners-owners-id-get\n        method: GET\n        description: OpenAQ Get a owner by ID\n        inputParameters:\n        - name: owners_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific owner by id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-owners\n      path: /v3/owners\n      operations:\n      - name: owners-get-v3-owners-get\n        method: GET\n        description: OpenAQ Get owners\n        inputParameters:\n        - name: order_by\n          in: query\n          type: string\n          description: The field by which to order results\n        - name: sort_order\n          in: query\n          type: string\n          description: Sort results ascending or descending. Default ASC\n        - name: limit\n          in:\
  \ query\n          type: integer\n          description: Change the number of results returned. e.g. limit=100 will return up to 100 results\n        - name: page\n          in: query\n          type: integer\n          description: Paginate through results. e.g. page=1 will return first page of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-providers-providers-id\n      path: /v3/providers/{providers_id}\n      operations:\n      - name: provider-get-v3-providers-providers-id-get\n        method: GET\n        description: OpenAQ Get a provider by ID\n        inputParameters:\n        - name: providers_id\n          in: path\n          type: integer\n          required: true\n          description: Limit the results to a specific provider by id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-providers\n\
  \      path: /v3/providers\n      operations:\n      - name: providers-get-v3-providers-get\n        method: GET\n        description: OpenAQ Get providers\n        inputParameters:\n        - name: order_by\n          in: query\n          type: string\n          description: The field by which to order results\n        - name: sort_order\n          in: query\n          type: string\n          description: Sort results ascending or descending. Default ASC\n        - name: parameters_id\n          in: query\n          type: string\n        - name: monitor\n          in: query\n          type: string\n          description: Is the location considered a reference monitor?\n     \n\n# --- truncated at 32 KB (176 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/openaq/refs/heads/main/capabilities/openaq-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/openaq/refs/heads/main/capabilities/openaq-capability.yaml
tags:
- Openaq
- API
tools:
- description: OpenAQ Get an instrument by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: instrument-get-v3-instruments-instruments-id-get
- description: OpenAQ Get instruments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: instruments-get-v3-instruments-get
- description: OpenAQ Get instruments by manufacturer ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-instruments-by-manufacturer-v3-manufacturers
- description: OpenAQ Get a location by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: location-get-v3-locations-locations-id-get
- description: OpenAQ Get locations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: locations-get-v3-locations-get
- description: OpenAQ Get an instrument by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: license-get-v3-licenses-licenses-id-get
- description: OpenAQ Get licenses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: instruments-get-v3-licenses-get
- description: OpenAQ Get a parameter by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: parameter-get-v3-parameters-parameters-id-get
- description: OpenAQ Get a parameters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: parameters-get-v3-parameters-get
- description: OpenAQ Get a country by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: country-get-v3-countries-countries-id-get
- description: OpenAQ Get countries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: countries-get-v3-countries-get
- description: OpenAQ Get a manufacturer by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: manufacturer-get-v3-manufacturers-manufacturers-
- description: OpenAQ Get manufacturers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: manufacturers-get-v3-manufacturers-get
- description: OpenAQ Get measurements by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-measurements-get-v3-sensors-sensors-id-me
- description: OpenAQ Get measurements aggregated to hours by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-measurements-aggregated-get-hourly-v3-sen
- description: OpenAQ Get measurements aggregated to days by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-measurements-aggregated-get-daily-v3-sens
- description: OpenAQ Get measurements aggregated to hour by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-hourly-measurements-get-v3-sensors-sensor
- description: OpenAQ Get measurements aggregated from hour to day by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-hourly-measurements-aggregate-to-day-get-
- description: OpenAQ Get measurements aggregated from hour to month by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-hourly-measurements-aggregate-to-month-ge
- description: OpenAQ Get measurements aggregated from hour to year by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-hourly-measurements-aggregate-to-year-get
- description: OpenAQ Get measurements aggregated from hour to day of week by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-hourly-measurements-aggregate-to-hod-get-
- description: OpenAQ Get measurements aggregated from hour to day of week by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-hourly-measurements-aggregate-to-dow-get-
- description: OpenAQ Get measurements aggregated from hour to day of week by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-hourly-measurements-aggregate-to-moy-get-
- description: OpenAQ Get measurements aggregated from day to day of week by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-daily-measurements-aggregate-to-dow-get-v
- description: OpenAQ Get measurements aggregated from day to day of week by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-daily-measurements-aggregate-to-moy-get-v
- description: OpenAQ Get measurements aggregated to day by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-daily-get-v3-sensors-sensors-id-days-get
- description: OpenAQ Get measurements aggregated from hour to month by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-daily-aggregate-to-month-get-v3-sensors-s
- description: OpenAQ Get measurements aggregated from day to year by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-daily-aggregate-to-year-get-v3-sensors-se
- description: OpenAQ Get measurements aggregated to year by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-yearly-get-v3-sensors-sensors-id-years-ge
- description: OpenAQ Get a owner by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: owner-get-v3-owners-owners-id-get
- description: OpenAQ Get owners
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: owners-get-v3-owners-get
- description: OpenAQ Get a provider by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: provider-get-v3-providers-providers-id-get
- description: OpenAQ Get providers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: providers-get-v3-providers-get
- description: OpenAQ Get sensors by location ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensors-get-v3-locations-locations-id-sensors-ge
- description: OpenAQ Get a sensor by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-get-v3-sensors-sensors-id-get
- description: OpenAQ Parameters Latest Get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: parameters-latest-get-v3-parameters-parameters-i
- description: OpenAQ Get a location's latest measurements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: location-latest-get-v3-locations-locations-id-la
- description: OpenAQ Get flags by location ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: location-flags-get-v3-locations-locations-id-fla
- description: OpenAQ Get flags by sensor ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sensor-flags-get-v3-sensors-sensor-id-flags-get
- description: OpenAQ Get averaged values
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: averages-v2-get-v2-averages-get
- description: OpenAQ Get cities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: cities-get-v2-cities-get
- description: OpenAQ Get cities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: cities-getv1-v1-cities-get
- description: OpenAQ Get country by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: countries-by-path-v2-countries-country-id-get
- description: OpenAQ Get country by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: countries-by-path-v1-countries-country-id-get
- description: OpenAQ Get countries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: countries-get-v2-countries-get
- description: OpenAQ Get countries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: countries-getv1-v1-countries-get
- description: OpenAQ Get a location by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-location-by-id-v2-locations-location-id-g
- description: OpenAQ Get locations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: locations-get-v2-locations-get
- description: OpenAQ Get latest measurements by location ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-latest-by-id-v2-latest-location-id-get
- description: OpenAQ Get latest measurements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: latest-get-v2-latest-get
- description: OpenAQ Get latest measurements by location ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-latest-by-id-v1-latest-location-id-get
- description: OpenAQ Get latest measurements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: latest-v1-get-v1-latest-get
- description: OpenAQ Get location by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-locations-by-id-v1-locations-location-id-
- description: OpenAQ Get locations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: locationsv1-get-v1-locations-get
- description: OpenAQ Get measurements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: measurements-get-v2-measurements-get
- description: OpenAQ Get a list of measurements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: measurements-get-v1-v1-measurements-get
- description: OpenAQ Get parameters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: parameters-get-v2-parameters-get
- description: OpenAQ Get parameters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: parameters-getv1-v1-parameters-get
- description: OpenAQ Project by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: projects-get-v2-projects-project-id-get
- description: OpenAQ Projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: projects-get-v2-projects-get
---
