---
categories: []
consumed_apis: []
description: The U.S. Energy Information Administration (EIA) Open Data API v2 provides free programmatic access to EIA's open energy data, including time-series datasets organized by energy category. The API uses a hierarchical route structure where each route corresponds to a category or dataset, and metadata about child routes, available facets, frequencies, and data columns is returned by querying any parent route. An API key, obtained via free registration at https://www.eia.gov/opendata/register.php, is required on every request and must be supplied as a URL query parameter.
layout: capability
name: U.S. Energy Information Administration Open Data API
operations:
- description: List top-level data categories
  method: GET
  name: getroot
  path: /
- description: List electricity child routes
  method: GET
  name: getelectricityroutes
  path: /electricity
- description: Query electricity retail sales time series
  method: GET
  name: getelectricityretailsales
  path: /electricity/retail-sales/data
- description: List natural gas child routes
  method: GET
  name: getnaturalgasroutes
  path: /natural-gas
- description: Query natural gas price summary
  method: GET
  name: getnaturalgaspricesummary
  path: /natural-gas/pri/sum/data
- description: List petroleum child routes
  method: GET
  name: getpetroleumroutes
  path: /petroleum
- description: Query gasoline and diesel retail prices
  method: GET
  name: getpetroleumgasolinedieselprices
  path: /petroleum/pri/gnd/data
- description: List coal child routes
  method: GET
  name: getcoalroutes
  path: /coal
- description: List nuclear outage child routes
  method: GET
  name: getnuclearoutagesroutes
  path: /nuclear-outages
- description: Query total energy time series
  method: GET
  name: gettotalenergy
  path: /total-energy/data
- description: List international child routes
  method: GET
  name: getinternationalroutes
  path: /international
- description: Query State Energy Data System time series
  method: GET
  name: getstateenergydata
  path: /seds/data
- description: Query CO2 emissions aggregates
  method: GET
  name: getco2emissionsaggregates
  path: /co2-emissions/co2-emissions-aggregates/data
personas: []
provider_name: Energy Information Administration
provider_slug: energy-information-administration
search_terms:
- list top-level data categories
- query electricity retail sales time series
- getelectricityretailsales
- information
- getpetroleumgasolinedieselprices
- query state energy data system time series
- getinternationalroutes
- query natural gas price summary
- list coal child routes
- getroot
- list international child routes
- query co2 emissions aggregates
- getnaturalgasroutes
- list petroleum child routes
- list electricity child routes
- query gasoline and diesel retail prices
- api
- energy
- administration
- gettotalenergy
- getelectricityroutes
- getpetroleumroutes
- federal government
- getnaturalgaspricesummary
- getnuclearoutagesroutes
- list natural gas child routes
- getcoalroutes
- list nuclear outage child routes
- getstateenergydata
- query total energy time series
- getco2emissionsaggregates
- open data
slug: energy-information-administration-capability
source_filename: energy-information-administration-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: U.S. Energy Information Administration Open Data API\n  description: The U.S. Energy Information Administration (EIA) Open Data API v2 provides free programmatic access to EIA's\n    open energy data, including time-series datasets organized by energy category. The API uses a hierarchical route structure\n    where each route corresponds to a category or dataset, and metadata about child routes, available facets, frequencies,\n    and data columns is returned by querying any parent route. An API key, obtained via free registration at https://www.eia.gov/opendata/register.php,\n    is required on every request and must be supplied as a URL query parameter.\n  tags:\n  - Energy\n  - Information\n  - Administration\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: energy-information-administration\n    baseUri: https://api.eia.gov/v2\n    description: U.S. Energy Information\
  \ Administration Open Data API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: api_key\n      value: '{{ENERGY_INFORMATION_ADMINISTRATION_TOKEN}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: getroot\n        method: GET\n        description: List top-level data categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: electricity\n      path: /electricity\n      operations:\n      - name: getelectricityroutes\n        method: GET\n        description: List electricity child routes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: electricity-retail-sales-data\n      path: /electricity/retail-sales/data\n      operations:\n      - name: getelectricityretailsales\n        method: GET\n        description: Query electricity retail sales\
  \ time series\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: natural-gas\n      path: /natural-gas\n      operations:\n      - name: getnaturalgasroutes\n        method: GET\n        description: List natural gas child routes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: natural-gas-pri-sum-data\n      path: /natural-gas/pri/sum/data\n      operations:\n      - name: getnaturalgaspricesummary\n        method: GET\n        description: Query natural gas price summary\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: petroleum\n      path: /petroleum\n      operations:\n      - name: getpetroleumroutes\n        method: GET\n        description: List petroleum child routes\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: petroleum-pri-gnd-data\n      path: /petroleum/pri/gnd/data\n      operations:\n      - name: getpetroleumgasolinedieselprices\n        method: GET\n        description: Query gasoline and diesel retail prices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: coal\n      path: /coal\n      operations:\n      - name: getcoalroutes\n        method: GET\n        description: List coal child routes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nuclear-outages\n      path: /nuclear-outages\n      operations:\n      - name: getnuclearoutagesroutes\n        method: GET\n        description: List nuclear outage child routes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n    - name: total-energy-data\n      path: /total-energy/data\n      operations:\n      - name: gettotalenergy\n        method: GET\n        description: Query total energy time series\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: international\n      path: /international\n      operations:\n      - name: getinternationalroutes\n        method: GET\n        description: List international child routes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: seds-data\n      path: /seds/data\n      operations:\n      - name: getstateenergydata\n        method: GET\n        description: Query State Energy Data System time series\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: co2-emissions-co2-emissions-aggregates-data\n\
  \      path: /co2-emissions/co2-emissions-aggregates/data\n      operations:\n      - name: getco2emissionsaggregates\n        method: GET\n        description: Query CO2 emissions aggregates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: energy-information-administration-rest\n    description: REST adapter for U.S. Energy Information Administration Open Data API.\n    resources:\n    - path: /\n      name: getroot\n      operations:\n      - method: GET\n        name: getroot\n        description: List top-level data categories\n        call: energy-information-administration.getroot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /electricity\n      name: getelectricityroutes\n      operations:\n      - method: GET\n        name: getelectricityroutes\n        description: List electricity child routes\n    \
  \    call: energy-information-administration.getelectricityroutes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /electricity/retail-sales/data\n      name: getelectricityretailsales\n      operations:\n      - method: GET\n        name: getelectricityretailsales\n        description: Query electricity retail sales time series\n        call: energy-information-administration.getelectricityretailsales\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /natural-gas\n      name: getnaturalgasroutes\n      operations:\n      - method: GET\n        name: getnaturalgasroutes\n        description: List natural gas child routes\n        call: energy-information-administration.getnaturalgasroutes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /natural-gas/pri/sum/data\n      name: getnaturalgaspricesummary\n      operations:\n      - method: GET\n        name: getnaturalgaspricesummary\n\
  \        description: Query natural gas price summary\n        call: energy-information-administration.getnaturalgaspricesummary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /petroleum\n      name: getpetroleumroutes\n      operations:\n      - method: GET\n        name: getpetroleumroutes\n        description: List petroleum child routes\n        call: energy-information-administration.getpetroleumroutes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /petroleum/pri/gnd/data\n      name: getpetroleumgasolinedieselprices\n      operations:\n      - method: GET\n        name: getpetroleumgasolinedieselprices\n        description: Query gasoline and diesel retail prices\n        call: energy-information-administration.getpetroleumgasolinedieselprices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /coal\n      name: getcoalroutes\n      operations:\n      - method: GET\n\
  \        name: getcoalroutes\n        description: List coal child routes\n        call: energy-information-administration.getcoalroutes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nuclear-outages\n      name: getnuclearoutagesroutes\n      operations:\n      - method: GET\n        name: getnuclearoutagesroutes\n        description: List nuclear outage child routes\n        call: energy-information-administration.getnuclearoutagesroutes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /total-energy/data\n      name: gettotalenergy\n      operations:\n      - method: GET\n        name: gettotalenergy\n        description: Query total energy time series\n        call: energy-information-administration.gettotalenergy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /international\n      name: getinternationalroutes\n      operations:\n      - method: GET\n        name: getinternationalroutes\n\
  \        description: List international child routes\n        call: energy-information-administration.getinternationalroutes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /seds/data\n      name: getstateenergydata\n      operations:\n      - method: GET\n        name: getstateenergydata\n        description: Query State Energy Data System time series\n        call: energy-information-administration.getstateenergydata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /co2-emissions/co2-emissions-aggregates/data\n      name: getco2emissionsaggregates\n      operations:\n      - method: GET\n        name: getco2emissionsaggregates\n        description: Query CO2 emissions aggregates\n        call: energy-information-administration.getco2emissionsaggregates\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: energy-information-administration-mcp\n\
  \    transport: http\n    description: MCP adapter for U.S. Energy Information Administration Open Data API for AI agent use.\n    tools:\n    - name: getroot\n      description: List top-level data categories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-information-administration.getroot\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getelectricityroutes\n      description: List electricity child routes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-information-administration.getelectricityroutes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getelectricityretailsales\n      description: Query electricity retail sales time series\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-information-administration.getelectricityretailsales\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnaturalgasroutes\n      description: List natural gas child routes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-information-administration.getnaturalgasroutes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnaturalgaspricesummary\n      description: Query natural gas price summary\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-information-administration.getnaturalgaspricesummary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpetroleumroutes\n      description: List petroleum child routes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-information-administration.getpetroleumroutes\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getpetroleumgasolinedieselprices\n      description: Query gasoline and diesel retail prices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-information-administration.getpetroleumgasolinedieselprices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcoalroutes\n      description: List coal child routes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-information-administration.getcoalroutes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnuclearoutagesroutes\n      description: List nuclear outage child routes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-information-administration.getnuclearoutagesroutes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettotalenergy\n      description:\
  \ Query total energy time series\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-information-administration.gettotalenergy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinternationalroutes\n      description: List international child routes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-information-administration.getinternationalroutes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstateenergydata\n      description: Query State Energy Data System time series\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-information-administration.getstateenergydata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getco2emissionsaggregates\n      description: Query CO2 emissions aggregates\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-information-administration.getco2emissionsaggregates\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ENERGY_INFORMATION_ADMINISTRATION_TOKEN: ENERGY_INFORMATION_ADMINISTRATION_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/energy-information-administration/refs/heads/main/capabilities/energy-information-administration-capability.yaml
tags:
- Energy
- Information
- Administration
- API
tools:
- description: List top-level data categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroot
- description: List electricity child routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getelectricityroutes
- description: Query electricity retail sales time series
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getelectricityretailsales
- description: List natural gas child routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnaturalgasroutes
- description: Query natural gas price summary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnaturalgaspricesummary
- description: List petroleum child routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpetroleumroutes
- description: Query gasoline and diesel retail prices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpetroleumgasolinedieselprices
- description: List coal child routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcoalroutes
- description: List nuclear outage child routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnuclearoutagesroutes
- description: Query total energy time series
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettotalenergy
- description: List international child routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinternationalroutes
- description: Query State Energy Data System time series
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstateenergydata
- description: Query CO2 emissions aggregates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getco2emissionsaggregates
---
