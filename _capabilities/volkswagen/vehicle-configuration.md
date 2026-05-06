---
categories: []
consumed_apis: []
description: Self-contained capability for the Volkswagen OKAPI vehicle configurator workflow. Browses the VW Group product catalog across global markets, configures vehicles with options, validates buildability, and retrieves order information, WLTP emissions, and configuration images. Used by automotive retailers, configurator apps, and digital sales platforms.
layout: capability
name: Volkswagen Vehicle Configuration
operations:
- description: List countries where VW OKAPI is available.
  method: GET
  name: list-countries
  path: /v1/countries
- description: List brands available in the country.
  method: GET
  name: list-brands-by-country
  path: /v1/catalog/{countryCode}/brands
- description: List models for a brand.
  method: GET
  name: list-models-by-brand
  path: /v1/catalog/{countryCode}/brands/{brandId}/models
- description: List vehicle types.
  method: GET
  name: list-types-by-model
  path: /v1/catalog/{countryCode}/models/{modelId}/types
- description: List configurable options.
  method: GET
  name: list-options-by-type
  path: /v1/catalog/{countryCode}/types/{typeId}/options
- description: Check if configuration is buildable.
  method: POST
  name: check-buildability
  path: /v1/configuration/{countryCode}/check
- description: Get price and specs for a configuration.
  method: POST
  name: get-order-information
  path: /v1/configuration/{countryCode}/order
- description: Get WLTP fuel and emissions data.
  method: POST
  name: get-wltp-data
  path: /v1/configuration/{countryCode}/wltp
- description: Get vehicle image URLs.
  method: POST
  name: get-configuration-images
  path: /v1/configuration/{countryCode}/images
personas: []
provider_name: Volkswagen
provider_slug: volkswagen
search_terms:
- explore trim levels and engine variants for a vehicle model.
- models by brand and market.
- sales
- get which options are available, unavailable, or required for the current configuration.
- cars
- list configurable options.
- check if a combination of selected options forms a buildable vehicle.
- list models by brand
- list models for a brand.
- get available config choices
- explore vehicle types
- product data
- get car price and specs
- get type options
- list countries
- validate car config
- get full pricing, standard equipment list, and technical specifications for a configuration.
- check if configuration is buildable.
- vehicle images for configuration.
- wltp emissions data.
- list vw markets
- get image urls showing the configured vehicle with selected exterior color and options.
- browse vehicle models for a vw group brand in a specific market.
- volkswagen
- get wltp data
- get order data for configuration.
- list supported markets.
- list types by model
- get order information
- get wltp fuel and emissions data.
- list brands available in the country.
- vehicle types by model.
- get price and specs for a configuration.
- browse vehicle models
- list options by type
- automotive
- get all configurable options for a vehicle type (colors, wheels, interiors, packages).
- get wltp fuel consumption and co2 emissions data for a vehicle configuration.
- get car emissions
- configurator
- vehicles
- automobiles
- list vw group brands (volkswagen, audi, seat, skoda, cupra, etc.) available in a market.
- fix an invalid configuration by finding the nearest buildable option combination.
- list all countries where volkswagen okapi vehicle configuration is available.
- get configuration images
- vw group brands in a market.
- get car images
- validate a vehicle configuration.
- fix car config
- get vehicle image urls.
- configurable options for a type.
- list vehicle types.
- list brands by country
- list countries where vw okapi is available.
- vehicle configuration
- list vw brands
- check buildability
slug: vehicle-configuration
source_filename: vehicle-configuration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\n\ninfo:\n  label: \"Volkswagen Vehicle Configuration\"\n  description: >-\n    Self-contained capability for the Volkswagen OKAPI vehicle configurator\n    workflow. Browses the VW Group product catalog across global markets,\n    configures vehicles with options, validates buildability, and retrieves\n    order information, WLTP emissions, and configuration images. Used by\n    automotive retailers, configurator apps, and digital sales platforms.\n  tags:\n    - Volkswagen\n    - Automotive\n    - Vehicle Configuration\n    - Product Data\n    - Configurator\n    - Sales\n  created: \"2026-05-03\"\n  modified: \"2026-05-05\"\n\nbinds:\n  - namespace: env\n    keys:\n      VOLKSWAGEN_OKAPI_TOKEN: VOLKSWAGEN_OKAPI_TOKEN\n\ncapability:\n  consumes:\n    - type: http\n      namespace: volkswagen-okapi\n      baseUri: https://productdata.volkswagenag.com/v3\n      description: \"Volkswagen OKAPI product data and configuration API.\"\n      authentication:\n\
  \        type: bearer\n        token: \"{{VOLKSWAGEN_OKAPI_TOKEN}}\"\n      resources:\n        - name: countries\n          path: /countries\n          description: \"List supported markets.\"\n          operations:\n            - name: list-countries\n              method: GET\n              description: \"List all countries where OKAPI vehicle configuration is available.\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n\n        - name: brands\n          path: /catalog/{countryCode}/brands\n          description: \"VW Group brands by market.\"\n          operations:\n            - name: list-brands-by-country\n              method: GET\n              description: \"List VW Group brands available in a country.\"\n              inputParameters:\n                - name: countryCode\n                  in: path\n                  type: string\n                  required:\
  \ true\n                  description: \"ISO 3166-2 market code (e.g. DE, GB, US).\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n\n        - name: models\n          path: /catalog/{countryCode}/brands/{brandId}/models\n          description: \"Models by brand and market.\"\n          operations:\n            - name: list-models-by-brand\n              method: GET\n              description: \"List vehicle models for a brand in a market.\"\n              inputParameters:\n                - name: countryCode\n                  in: path\n                  type: string\n                  required: true\n                - name: brandId\n                  in: path\n                  type: string\n                  required: true\n                  description: \"Brand UUID.\"\n              outputRawFormat: json\n              outputParameters:\n                - name:\
  \ result\n                  type: object\n                  value: \"$.\"\n\n        - name: types\n          path: /catalog/{countryCode}/models/{modelId}/types\n          description: \"Vehicle types by model.\"\n          operations:\n            - name: list-types-by-model\n              method: GET\n              description: \"List vehicle types (trims, engine variants) for a model.\"\n              inputParameters:\n                - name: countryCode\n                  in: path\n                  type: string\n                  required: true\n                - name: modelId\n                  in: path\n                  type: string\n                  required: true\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n\n        - name: options\n          path: /catalog/{countryCode}/types/{typeId}/options\n          description: \"Configurable options for a vehicle\
  \ type.\"\n          operations:\n            - name: list-options-by-type\n              method: GET\n              description: \"List all configurable options for a vehicle type.\"\n              inputParameters:\n                - name: countryCode\n                  in: path\n                  type: string\n                  required: true\n                - name: typeId\n                  in: path\n                  type: string\n                  required: true\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n\n        - name: buildability\n          path: /operation/{countryCode}/check\n          description: \"Validate a vehicle configuration.\"\n          operations:\n            - name: check-buildability\n              method: POST\n              description: \"Check whether a configuration is buildable.\"\n              inputParameters:\n                -\
  \ name: countryCode\n                  in: path\n                  type: string\n                  required: true\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n              body:\n                type: json\n                data:\n                  typeId: \"{{tools.typeId}}\"\n                  selectedOptions: \"{{tools.selectedOptions}}\"\n\n        - name: recover\n          path: /operation/{countryCode}/recover\n          description: \"Recover a buildable configuration.\"\n          operations:\n            - name: recover-configuration\n              method: POST\n              description: \"Return nearest valid configuration for an unbuildable selection.\"\n              inputParameters:\n                - name: countryCode\n                  in: path\n                  type: string\n                  required: true\n              outputRawFormat: json\n\
  \              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n              body:\n                type: json\n                data:\n                  typeId: \"{{tools.typeId}}\"\n                  selectedOptions: \"{{tools.selectedOptions}}\"\n\n        - name: configure\n          path: /operation/{countryCode}/configure\n          description: \"Get available options for current config.\"\n          operations:\n            - name: get-configuration-options\n              method: POST\n              description: \"List available, unavailable, and required options.\"\n              inputParameters:\n                - name: countryCode\n                  in: path\n                  type: string\n                  required: true\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n              body:\n\
  \                type: json\n                data:\n                  typeId: \"{{tools.typeId}}\"\n                  selectedOptions: \"{{tools.selectedOptions}}\"\n\n        - name: wltp\n          path: /operation/{countryCode}/wltp\n          description: \"WLTP emissions data for a configuration.\"\n          operations:\n            - name: get-wltp-data\n              method: POST\n              description: \"Get WLTP fuel consumption and CO2 emissions for a configuration.\"\n              inputParameters:\n                - name: countryCode\n                  in: path\n                  type: string\n                  required: true\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n              body:\n                type: json\n                data:\n                  typeId: \"{{tools.typeId}}\"\n                  selectedOptions: \"{{tools.selectedOptions}}\"\
  \n\n        - name: images\n          path: /operation/{countryCode}/images\n          description: \"Vehicle images for a configuration.\"\n          operations:\n            - name: get-configuration-images\n              method: POST\n              description: \"Get image URLs for the configured vehicle.\"\n              inputParameters:\n                - name: countryCode\n                  in: path\n                  type: string\n                  required: true\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n              body:\n                type: json\n                data:\n                  typeId: \"{{tools.typeId}}\"\n                  selectedOptions: \"{{tools.selectedOptions}}\"\n\n        - name: order\n          path: /operation/{countryCode}/order\n          description: \"Order information for a configuration.\"\n          operations:\n       \
  \     - name: get-order-information\n              method: POST\n              description: \"Get pricing, standard equipment, and technical data.\"\n              inputParameters:\n                - name: countryCode\n                  in: path\n                  type: string\n                  required: true\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n              body:\n                type: json\n                data:\n                  typeId: \"{{tools.typeId}}\"\n                  selectedOptions: \"{{tools.selectedOptions}}\"\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: volkswagen-config-api\n      description: \"Unified REST API for VW vehicle configuration and product data.\"\n      resources:\n        - path: /v1/countries\n          name: countries\n          description: \"List supported markets.\"\n          operations:\n    \
  \        - method: GET\n              name: list-countries\n              description: \"List countries where VW OKAPI is available.\"\n              call: \"volkswagen-okapi.list-countries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/catalog/{countryCode}/brands\n          name: brands\n          description: \"VW Group brands in a market.\"\n          operations:\n            - method: GET\n              name: list-brands-by-country\n              description: \"List brands available in the country.\"\n              call: \"volkswagen-okapi.list-brands-by-country\"\n              with:\n                countryCode: \"rest.countryCode\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/catalog/{countryCode}/brands/{brandId}/models\n          name: models\n          description: \"Models by brand and market.\"\n          operations:\n\
  \            - method: GET\n              name: list-models-by-brand\n              description: \"List models for a brand.\"\n              call: \"volkswagen-okapi.list-models-by-brand\"\n              with:\n                countryCode: \"rest.countryCode\"\n                brandId: \"rest.brandId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/catalog/{countryCode}/models/{modelId}/types\n          name: types\n          description: \"Vehicle types by model.\"\n          operations:\n            - method: GET\n              name: list-types-by-model\n              description: \"List vehicle types.\"\n              call: \"volkswagen-okapi.list-types-by-model\"\n              with:\n                countryCode: \"rest.countryCode\"\n                modelId: \"rest.modelId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/catalog/{countryCode}/types/{typeId}/options\n\
  \          name: options\n          description: \"Configurable options for a type.\"\n          operations:\n            - method: GET\n              name: list-options-by-type\n              description: \"List configurable options.\"\n              call: \"volkswagen-okapi.list-options-by-type\"\n              with:\n                countryCode: \"rest.countryCode\"\n                typeId: \"rest.typeId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/configuration/{countryCode}/check\n          name: buildability\n          description: \"Validate a vehicle configuration.\"\n          operations:\n            - method: POST\n              name: check-buildability\n              description: \"Check if configuration is buildable.\"\n              call: \"volkswagen-okapi.check-buildability\"\n              with:\n                countryCode: \"rest.countryCode\"\n              outputParameters:\n          \
  \      - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/configuration/{countryCode}/order\n          name: order\n          description: \"Get order data for configuration.\"\n          operations:\n            - method: POST\n              name: get-order-information\n              description: \"Get price and specs for a configuration.\"\n              call: \"volkswagen-okapi.get-order-information\"\n              with:\n                countryCode: \"rest.countryCode\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/configuration/{countryCode}/wltp\n          name: wltp\n          description: \"WLTP emissions data.\"\n          operations:\n            - method: POST\n              name: get-wltp-data\n              description: \"Get WLTP fuel and emissions data.\"\n              call: \"volkswagen-okapi.get-wltp-data\"\n              with:\n                countryCode: \"rest.countryCode\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/configuration/{countryCode}/images\n          name: images\n          description: \"Vehicle images for configuration.\"\n          operations:\n            - method: POST\n              name: get-configuration-images\n              description: \"Get vehicle image URLs.\"\n              call: \"volkswagen-okapi.get-configuration-images\"\n              with:\n                countryCode: \"rest.countryCode\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: volkswagen-config-mcp\n      transport: http\n      description: \"MCP server for AI-assisted VW vehicle configuration and product lookup.\"\n      tools:\n        - name: list-vw-markets\n          description: \"List all countries where Volkswagen OKAPI vehicle configuration is available.\"\n          hints:\n\
  \            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"volkswagen-okapi.list-countries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-vw-brands\n          description: \"List VW Group brands (Volkswagen, Audi, SEAT, Skoda, CUPRA, etc.) available in a market.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"volkswagen-okapi.list-brands-by-country\"\n          with:\n            countryCode: \"tools.countryCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: browse-vehicle-models\n          description: \"Browse vehicle models for a VW Group brand in a specific market.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"volkswagen-okapi.list-models-by-brand\"\
  \n          with:\n            countryCode: \"tools.countryCode\"\n            brandId: \"tools.brandId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: explore-vehicle-types\n          description: \"Explore trim levels and engine variants for a vehicle model.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"volkswagen-okapi.list-types-by-model\"\n          with:\n            countryCode: \"tools.countryCode\"\n            modelId: \"tools.modelId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-type-options\n          description: \"Get all configurable options for a vehicle type (colors, wheels, interiors, packages).\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"volkswagen-okapi.list-options-by-type\"\
  \n          with:\n            countryCode: \"tools.countryCode\"\n            typeId: \"tools.typeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: validate-car-config\n          description: \"Check if a combination of selected options forms a buildable vehicle.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"volkswagen-okapi.check-buildability\"\n          with:\n            countryCode: \"tools.countryCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: fix-car-config\n          description: \"Fix an invalid configuration by finding the nearest buildable option combination.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"volkswagen-okapi.recover-configuration\"\n          with:\n            countryCode:\
  \ \"tools.countryCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-available-config-choices\n          description: \"Get which options are available, unavailable, or required for the current configuration.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"volkswagen-okapi.get-configuration-options\"\n          with:\n            countryCode: \"tools.countryCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-car-emissions\n          description: \"Get WLTP fuel consumption and CO2 emissions data for a vehicle configuration.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"volkswagen-okapi.get-wltp-data\"\n          with:\n            countryCode: \"tools.countryCode\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-car-images\n          description: \"Get image URLs showing the configured vehicle with selected exterior color and options.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"volkswagen-okapi.get-configuration-images\"\n          with:\n            countryCode: \"tools.countryCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-car-price-and-specs\n          description: \"Get full pricing, standard equipment list, and technical specifications for a configuration.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"volkswagen-okapi.get-order-information\"\n          with:\n            countryCode: \"tools.countryCode\"\n          outputParameters:\n            - type: object\n           \
  \   mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/volkswagen/refs/heads/main/capabilities/vehicle-configuration.yaml
tags:
- Volkswagen
- Automotive
- Vehicle Configuration
- Product Data
- Configurator
- Sales
tools:
- description: List all countries where Volkswagen OKAPI vehicle configuration is available.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-vw-markets
- description: List VW Group brands (Volkswagen, Audi, SEAT, Skoda, CUPRA, etc.) available in a market.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-vw-brands
- description: Browse vehicle models for a VW Group brand in a specific market.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: browse-vehicle-models
- description: Explore trim levels and engine variants for a vehicle model.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: explore-vehicle-types
- description: Get all configurable options for a vehicle type (colors, wheels, interiors, packages).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-type-options
- description: Check if a combination of selected options forms a buildable vehicle.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: validate-car-config
- description: Fix an invalid configuration by finding the nearest buildable option combination.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fix-car-config
- description: Get which options are available, unavailable, or required for the current configuration.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-available-config-choices
- description: Get WLTP fuel consumption and CO2 emissions data for a vehicle configuration.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-car-emissions
- description: Get image URLs showing the configured vehicle with selected exterior color and options.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-car-images
- description: Get full pricing, standard equipment list, and technical specifications for a configuration.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-car-price-and-specs
---
