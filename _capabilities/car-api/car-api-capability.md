---
categories: []
consumed_apis: []
description: 'Welcome to [CarAPIs vehicle API](https://carapi.app) documentation. The developer friendly Car API. Start developing with your vehicle API today — no fees, no signup. CarAPIs free vehicle data-set requires no account. Only pay when you''re ready to go live. The free data-set is limited to 2015-2020 vehicles. To access the full data-set you may [signup here](https://carapi.app/register) and then select a subscription plan. **Additional Documentation** For additional documentation please review [https://carapi.app/docs](https://carapi.app/docs). **SDKs** PHP SDK: [https://github.com/car-api-team/'
layout: capability
name: Car API
operations:
- description: Car API Get API Usage
  method: GET
  name: account-requests-get
  path: /api/account/requests
- description: Car API Get Today's API Usage
  method: GET
  name: account-requeststoday-get
  path: /api/account/requests-today
- description: Car API JWT Login
  method: POST
  name: auth-api-post
  path: /api/auth/login
- description: Car API Search vehicle bodies
  method: GET
  name: makemodeltrimbodies-index-get
  path: /api/bodies
- description: Car API Get Data Feed
  method: GET
  name: datafeeds-download-get
  path: /api/data-feeds/download
- description: Car API Data Feed Last Updated
  method: GET
  name: datafeeds-lastupdated-get
  path: /api/data-feeds/last-updated
- description: Car API Search vehicle engines
  method: GET
  name: makemodeltrimengines-index-get
  path: /api/engines
- description: Car API Search vehicle exterior colors
  method: GET
  name: makemodeltrimexteriorcolors-index-get
  path: /api/exterior-colors
- description: Car API Search vehicle interior colors
  method: GET
  name: makemodeltriminteriorcolors-index-get
  path: /api/interior-colors
- description: Car API Get Makes
  method: GET
  name: makes-index-get
  path: /api/makes
- description: Car API Search vehicle mileages
  method: GET
  name: makemodeltrimmileages-index-get
  path: /api/mileages
- description: Car API Get Models
  method: GET
  name: makemodels-index-get
  path: /api/models
- description: Car API Search trims
  method: GET
  name: makemodeltrims-index-get
  path: /api/trims
- description: Car API Get vehicle data.
  method: GET
  name: makemodeltrims-view-get
  path: /api/trims/{id}
- description: Car API Get Vehicle Attributes
  method: GET
  name: vehicleattributes-display-get
  path: /api/vehicle-attributes
- description: Car API Vin Decoder
  method: GET
  name: vindecoder-index-get
  path: /api/vin/{vin}
- description: Car API Get Years List
  method: GET
  name: years-index-get
  path: /api/years
personas: []
provider_name: Car API (carapi.app)
provider_slug: car-api
search_terms:
- car api get today's api usage
- car api get api usage
- makemodeltrims view get
- car api get data feed
- makemodels index get
- vehicleattributes display get
- car api jwt login
- makemodeltrimbodies index get
- api
- license plate decoder
- car api search vehicle exterior colors
- car api search vehicle bodies
- car api search vehicle engines
- automobiles
- car
- datafeeds download get
- makemodeltriminteriorcolors index get
- car api vin decoder
- vehicles
- vehicle specifications
- auth api post
- car api search trims
- car api get models
- obd-ii
- makemodeltrims index get
- car api search vehicle mileages
- vin decoder
- account requests get
- account requeststoday get
- cars
- makes index get
- makemodeltrimengines index get
- car api get vehicle data.
- car api get vehicle attributes
- car api get years list
- automotive data
- car api search vehicle interior colors
- car api get makes
- makemodeltrimexteriorcolors index get
- datafeeds lastupdated get
- vindecoder index get
- car api data feed last updated
- years index get
- makemodeltrimmileages index get
- vehicle api
- power sports
slug: car-api-capability
source_filename: car-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Car API\n  description: 'Welcome to [CarAPIs vehicle API](https://carapi.app) documentation. The developer friendly Car API. Start\n    developing with your vehicle API today — no fees, no signup. CarAPIs free vehicle data-set requires no account. Only pay\n    when you''re ready to go live. The free data-set is limited to 2015-2020 vehicles. To access the full data-set you may\n    [signup here](https://carapi.app/register) and then select a subscription plan. **Additional Documentation** For additional\n    documentation please review [https://carapi.app/docs](https://carapi.app/docs). **SDKs** PHP SDK: [https://github.com/car-api-team/'\n  tags:\n  - Car\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: car-api\n    baseUri: https://carapi.app\n    description: Car API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CAR_API_TOKEN}}'\n  \
  \  resources:\n    - name: api-account-requests\n      path: /api/account/requests\n      operations:\n      - name: account-requests-get\n        method: GET\n        description: Car API Get API Usage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-account-requests-today\n      path: /api/account/requests-today\n      operations:\n      - name: account-requeststoday-get\n        method: GET\n        description: Car API Get Today's API Usage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-auth-login\n      path: /api/auth/login\n      operations:\n      - name: auth-api-post\n        method: POST\n        description: Car API JWT Login\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-bodies\n      path:\
  \ /api/bodies\n      operations:\n      - name: makemodeltrimbodies-index-get\n        method: GET\n        description: Car API Search vehicle bodies\n        inputParameters:\n        - name: sort\n          in: query\n          type: string\n        - name: verbose\n          in: query\n          type: string\n          description: Includes make, model and trim\n        - name: make_model_id\n          in: query\n          type: string\n        - name: make_id\n          in: query\n          type: string\n        - name: year\n          in: query\n          type: string\n        - name: make\n          in: query\n          type: string\n        - name: model\n          in: query\n          type: string\n        - name: trim\n          in: query\n          type: string\n        - name: make_model_trim_id\n          in: query\n          type: string\n        - name: type\n          in: query\n          type: string\n        - name: doors\n          in: query\n          type: string\n\
  \        - name: json\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-data-feeds-download\n      path: /api/data-feeds/download\n      operations:\n      - name: datafeeds-download-get\n        method: GET\n        description: Car API Get Data Feed\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-data-feeds-last-updated\n      path: /api/data-feeds/last-updated\n      operations:\n      - name: datafeeds-lastupdated-get\n        method: GET\n        description: Car API Data Feed Last Updated\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-engines\n      path: /api/engines\n      operations:\n      - name: makemodeltrimengines-index-get\n        method: GET\n\
  \        description: Car API Search vehicle engines\n        inputParameters:\n        - name: sort\n          in: query\n          type: string\n        - name: verbose\n          in: query\n          type: string\n          description: Includes make, model and trim\n        - name: make_model_trim_id\n          in: query\n          type: string\n        - name: cylinders\n          in: query\n          type: string\n        - name: size\n          in: query\n          type: string\n        - name: horsepower_hp\n          in: query\n          type: string\n        - name: valves\n          in: query\n          type: string\n        - name: valve_timing\n          in: query\n          type: string\n        - name: cam_type\n          in: query\n          type: string\n        - name: drive_type\n          in: query\n          type: string\n        - name: transmission\n          in: query\n          type: string\n        - name: engine_type\n          in: query\n          type: string\n\
  \        - name: fuel_type\n          in: query\n          type: string\n        - name: make_model_id\n          in: query\n          type: string\n        - name: make_id\n          in: query\n          type: string\n        - name: year\n          in: query\n          type: string\n        - name: make\n          in: query\n          type: string\n        - name: model\n          in: query\n          type: string\n        - name: trim\n          in: query\n          type: string\n        - name: json\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-exterior-colors\n      path: /api/exterior-colors\n      operations:\n      - name: makemodeltrimexteriorcolors-index-get\n        method: GET\n        description: Car API Search vehicle exterior colors\n        inputParameters:\n        - name: sort\n          in: query\n          type: string\n   \
  \     - name: verbose\n          in: query\n          type: string\n          description: Includes make, model and trim\n        - name: make_model_trim_id\n          in: query\n          type: string\n        - name: make_model_id\n          in: query\n          type: string\n        - name: make_id\n          in: query\n          type: string\n        - name: name\n          in: query\n          type: string\n        - name: rgb\n          in: query\n          type: string\n        - name: year\n          in: query\n          type: string\n        - name: make\n          in: query\n          type: string\n        - name: model\n          in: query\n          type: string\n        - name: trim\n          in: query\n          type: string\n        - name: json\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-interior-colors\n      path: /api/interior-colors\n\
  \      operations:\n      - name: makemodeltriminteriorcolors-index-get\n        method: GET\n        description: Car API Search vehicle interior colors\n        inputParameters:\n        - name: sort\n          in: query\n          type: string\n        - name: verbose\n          in: query\n          type: string\n          description: Includes make, model and trim\n        - name: make_model_trim_id\n          in: query\n          type: string\n        - name: make_model_id\n          in: query\n          type: string\n        - name: make_id\n          in: query\n          type: string\n        - name: name\n          in: query\n          type: string\n        - name: rgb\n          in: query\n          type: string\n        - name: year\n          in: query\n          type: string\n        - name: make\n          in: query\n          type: string\n        - name: model\n          in: query\n          type: string\n        - name: trim\n          in: query\n          type: string\n\
  \        - name: json\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-makes\n      path: /api/makes\n      operations:\n      - name: makes-index-get\n        method: GET\n        description: Car API Get Makes\n        inputParameters:\n        - name: sort\n          in: query\n          type: string\n        - name: make\n          in: query\n          type: string\n        - name: year\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-mileages\n      path: /api/mileages\n      operations:\n      - name: makemodeltrimmileages-index-get\n        method: GET\n        description: Car API Search vehicle mileages\n        inputParameters:\n        - name: sort\n          in: query\n          type: string\n     \
  \   - name: verbose\n          in: query\n          type: string\n          description: Includes make, model and trim\n        - name: make_model_trim_id\n          in: query\n          type: string\n        - name: combined_mpg\n          in: query\n          type: string\n        - name: epa_city_mpg\n          in: query\n          type: string\n        - name: epa_highway_mpg\n          in: query\n          type: string\n        - name: range_city\n          in: query\n          type: string\n        - name: range_highway\n          in: query\n          type: string\n        - name: make_model_id\n          in: query\n          type: string\n        - name: make_id\n          in: query\n          type: string\n        - name: year\n          in: query\n          type: string\n        - name: make\n          in: query\n          type: string\n        - name: model\n          in: query\n          type: string\n        - name: trim\n          in: query\n          type: string\n      \
  \  - name: json\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-models\n      path: /api/models\n      operations:\n      - name: makemodels-index-get\n        method: GET\n        description: Car API Get Models\n        inputParameters:\n        - name: sort\n          in: query\n          type: string\n        - name: verbose\n          in: query\n          type: string\n          description: Includes make and model\n        - name: year\n          in: query\n          type: string\n        - name: make\n          in: query\n          type: string\n        - name: model\n          in: query\n          type: string\n        - name: make_id\n          in: query\n          type: string\n        - name: json\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: api-trims\n      path: /api/trims\n      operations:\n      - name: makemodeltrims-index-get\n        method: GET\n        description: Car API Search trims\n        inputParameters:\n        - name: sort\n          in: query\n          type: string\n        - name: verbose\n          in: query\n          type: string\n          description: Includes make, model and trim\n        - name: year\n          in: query\n          type: string\n        - name: make\n          in: query\n          type: string\n        - name: model\n          in: query\n          type: string\n        - name: trim\n          in: query\n          type: string\n        - name: make_model_id\n          in: query\n          type: string\n        - name: make_id\n          in: query\n          type: string\n        - name: json\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: api-trims-id\n      path: /api/trims/{id}\n      operations:\n      - name: makemodeltrims-view-get\n        method: GET\n        description: Car API Get vehicle data.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-vehicle-attributes\n      path: /api/vehicle-attributes\n      operations:\n      - name: vehicleattributes-display-get\n        method: GET\n        description: Car API Get Vehicle Attributes\n        inputParameters:\n        - name: attribute\n          in: query\n          type: string\n          description: The attribute options to be returned\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-vin-vin\n      path: /api/vin/{vin}\n \
  \     operations:\n      - name: vindecoder-index-get\n        method: GET\n        description: Car API Vin Decoder\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n        - name: verbose\n          in: query\n          type: string\n          description: 'Includes body, engine, and mileage data (default: no)'\n        - name: all_trims\n          in: query\n          type: string\n          description: 'Includes all trims for the matching model (default: no)'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-years\n      path: /api/years\n      operations:\n      - name: years-index-get\n        method: GET\n        description: Car API Get Years List\n        inputParameters:\n        - name: year\n          in: query\n          type: string\n        - name: make\n          in: query\n          type: string\n        - name:\
  \ model\n          in: query\n          type: string\n        - name: trim\n          in: query\n          type: string\n        - name: make_model_id\n          in: query\n          type: string\n        - name: make_id\n          in: query\n          type: string\n        - name: json\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: car-api-rest\n    description: REST adapter for Car API.\n    resources:\n    - path: /api/account/requests\n      name: account-requests-get\n      operations:\n      - method: GET\n        name: account-requests-get\n        description: Car API Get API Usage\n        call: car-api.account-requests-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/account/requests-today\n      name: account-requeststoday-get\n      operations:\n\
  \      - method: GET\n        name: account-requeststoday-get\n        description: Car API Get Today's API Usage\n        call: car-api.account-requeststoday-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/auth/login\n      name: auth-api-post\n      operations:\n      - method: POST\n        name: auth-api-post\n        description: Car API JWT Login\n        call: car-api.auth-api-post\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/bodies\n      name: makemodeltrimbodies-index-get\n      operations:\n      - method: GET\n        name: makemodeltrimbodies-index-get\n        description: Car API Search vehicle bodies\n        call: car-api.makemodeltrimbodies-index-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/data-feeds/download\n      name: datafeeds-download-get\n      operations:\n      - method: GET\n        name: datafeeds-download-get\n\
  \        description: Car API Get Data Feed\n        call: car-api.datafeeds-download-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/data-feeds/last-updated\n      name: datafeeds-lastupdated-get\n      operations:\n      - method: GET\n        name: datafeeds-lastupdated-get\n        description: Car API Data Feed Last Updated\n        call: car-api.datafeeds-lastupdated-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/engines\n      name: makemodeltrimengines-index-get\n      operations:\n      - method: GET\n        name: makemodeltrimengines-index-get\n        description: Car API Search vehicle engines\n        call: car-api.makemodeltrimengines-index-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/exterior-colors\n      name: makemodeltrimexteriorcolors-index-get\n      operations:\n      - method: GET\n        name: makemodeltrimexteriorcolors-index-get\n\
  \        description: Car API Search vehicle exterior colors\n        call: car-api.makemodeltrimexteriorcolors-index-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/interior-colors\n      name: makemodeltriminteriorcolors-index-get\n      operations:\n      - method: GET\n        name: makemodeltriminteriorcolors-index-get\n        description: Car API Search vehicle interior colors\n        call: car-api.makemodeltriminteriorcolors-index-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/makes\n      name: makes-index-get\n      operations:\n      - method: GET\n        name: makes-index-get\n        description: Car API Get Makes\n        call: car-api.makes-index-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/mileages\n      name: makemodeltrimmileages-index-get\n      operations:\n      - method: GET\n        name: makemodeltrimmileages-index-get\n\
  \        description: Car API Search vehicle mileages\n        call: car-api.makemodeltrimmileages-index-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/models\n      name: makemodels-index-get\n      operations:\n      - method: GET\n        name: makemodels-index-get\n        description: Car API Get Models\n        call: car-api.makemodels-index-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/trims\n      name: makemodeltrims-index-get\n      operations:\n      - method: GET\n        name: makemodeltrims-index-get\n        description: Car API Search trims\n        call: car-api.makemodeltrims-index-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/trims/{id}\n      name: makemodeltrims-view-get\n      operations:\n      - method: GET\n        name: makemodeltrims-view-get\n        description: Car API Get vehicle data.\n        call: car-api.makemodeltrims-view-get\n\
  \        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/vehicle-attributes\n      name: vehicleattributes-display-get\n      operations:\n      - method: GET\n        name: vehicleattributes-display-get\n        description: Car API Get Vehicle Attributes\n        call: car-api.vehicleattributes-display-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/vin/{vin}\n      name: vindecoder-index-get\n      operations:\n      - method: GET\n        name: vindecoder-index-get\n        description: Car API Vin Decoder\n        call: car-api.vindecoder-index-get\n        with:\n          vin: rest.vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/years\n      name: years-index-get\n      operations:\n      - method: GET\n        name: years-index-get\n        description: Car API Get Years List\n        call: car-api.years-index-get\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: car-api-mcp\n    transport: http\n    description: MCP adapter for Car API for AI agent use.\n    tools:\n    - name: account-requests-get\n      description: Car API Get API Usage\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: car-api.account-requests-get\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: account-requeststoday-get\n      description: Car API Get Today's API Usage\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: car-api.account-requeststoday-get\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-api-post\n      description: Car API JWT Login\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: car-api.auth-api-post\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: makemodeltrimbodies-index-get\n      description: Car API Search vehicle bodies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: car-api.makemodeltrimbodies-index-get\n      with:\n        sort: tools.sort\n        verbose: tools.verbose\n        make_model_id: tools.make_model_id\n        make_id: tools.make_id\n        year: tools.year\n        make: tools.make\n        model: tools.model\n        trim: tools.trim\n        make_model_trim_id: tools.make_model_trim_id\n        type: tools.type\n        doors: tools.doors\n        json: tools.json\n      inputParameters:\n      - name: sort\n        type: string\n        description: sort\n      - name: verbose\n        type: string\n        description: Includes make, model and trim\n      - name: make_model_id\n        type: string\n        description: make_model_id\n      - name: make_id\n        type:\
  \ string\n        description: make_id\n      - name: year\n        type: string\n        description: year\n      - name: make\n        type: string\n        description: make\n      - name: model\n        type: string\n        description: model\n      - name: trim\n        type: string\n        description: trim\n      - name: make_model_trim_id\n        type: string\n        description: make_model_trim_id\n      - name: type\n        type: string\n        description: type\n      - name: doors\n        type: string\n        description: doors\n      - name: json\n        type: string\n        description: json\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: datafeeds-download-get\n      description: Car API Get Data Feed\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: car-api.datafeeds-download-get\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: datafeeds-lastupdated-get\n\
  \      description: Car API Data Feed Last Updated\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: car-api.datafeeds-lastupdated-get\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: makemodeltrimengines-index-get\n      description: Car API Search vehicle engines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: car-api.makemodeltrimengines-index-get\n      with:\n        sort: tools.sort\n        verbose: tools.verbose\n        make_model_trim_id: tools.make_model_trim_id\n        cylinders: tools.cylinders\n        size: tools.size\n        horsepower_hp: tools.horsepower_hp\n        valves: tools.valves\n        valve_timing: tools.valve_timing\n        cam_type: tools.cam_type\n        drive_type: tools.drive_type\n        transmission: tools.transmission\n        engine_type: tools.engine_type\n        fuel_type: tools.fuel_type\n        make_model_id:\
  \ tools.make_model_id\n        make_id: tools.make_id\n        year: tools.year\n        make: tools.make\n        model: tools.model\n        trim: tools.trim\n        json: tools.json\n      inputParameters:\n      - name: sort\n        type: string\n        description: sort\n      - name: verbose\n        type: string\n        description: Includes make, model and trim\n      - name: make_model_trim_id\n        type: string\n        description: make_model_trim_id\n      - name: cylinders\n        type: string\n        description: cylinders\n      - name: size\n        type: string\n        description: size\n      - name: horsepower_hp\n        type: string\n        description: horsepower_hp\n      - name: valves\n        type: string\n        description: valves\n      - name: valve_timing\n        type: string\n        description: valve_timing\n      - name: cam_type\n        type: string\n        description: cam_type\n      - name: drive_type\n        type: string\n       \
  \ description: drive_type\n      - name: transmission\n        type: string\n        description: transmission\n      - name: engine_type\n        type: string\n        description: engine_type\n      - name: fuel_type\n        type: string\n        description: fuel_type\n      - name: make_model_id\n        type: string\n        description: make_model_id\n      - name: make_id\n        type: string\n        description: make_id\n      - name: year\n        type: string\n        description: year\n      - name: make\n        type: string\n        description: make\n      - name: model\n        type: string\n        description: model\n      - name: trim\n        type: string\n        description: trim\n      - name: json\n        type: string\n        description: json\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: makemodeltrimexteriorcolors-index-get\n      description: Car API Search vehicle exterior colors\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: car-api.makemodeltrimexteriorcolors-index-get\n      with:\n        sort: tools.sort\n        verbose: tools.verbose\n        make_model_trim_id: tools.make_model_trim_id\n        make_model_id: tools.make_model_id\n        make_id: tools.make_id\n        name: tools.name\n        rgb: tools.rgb\n        year: tools.year\n        make: tools.make\n        model: tools.model\n        trim: tools.trim\n        json: tools.json\n      inputParameters:\n      - name: sort\n        type: string\n        description: sort\n      - name: verbose\n        type: string\n        description: Includes make, model and trim\n      - name: make_model_trim_id\n        type: string\n        description: make_model_trim_id\n      - name: make_model_id\n        type: string\n        description: make_model_id\n      - name: make_id\n        type: string\n        description: make_id\n      - name: name\n        type: string\n        description:\
  \ name\n      - name: rgb\n        type: string\n        description: rgb\n      - name: year\n        type: string\n        description: year\n      - name: make\n        type: string\n        description: make\n      - name: model\n        type: string\n        description: model\n      - name: trim\n        type: string\n        description: trim\n      - name: json\n        type: string\n        description: json\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: makemodeltriminteriorcolors-index-get\n      description: Car API Search vehicle interior colors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: car-api.makemodeltriminteriorcolors-index-get\n      with:\n        sort: tools.sort\n        verbose: tools.verbose\n        make_model_trim_id: tools.make_model_trim_id\n        make_model_id: tools.make_model_id\n        make_id: tools.make_id\n        name: tools.name\n        rgb: tools.rgb\n\
  \        year: tools.year\n        make: tools.make\n        model: tools.model\n        trim: tools.trim\n        json: tools.json\n      inputParameters:\n      - name: sort\n        type: string\n        description: sort\n      - name: verbose\n        type: string\n        description: Includes make, model and trim\n      - name: make_model_trim_id\n        type: string\n        description: make_model_trim_id\n      - name: make_model_id\n        type: string\n        description: make_model_id\n      - name: make_id\n        type: string\n        description: make_id\n      - name: name\n        type: string\n        description: name\n      - name: rgb\n        type: string\n        description: rgb\n      - name: year\n        type: string\n        description: year\n      - name: make\n        type: string\n        description: make\n      - name: model\n        type: string\n        description: model\n      - name: trim\n        type: string\n        description: trim\n   \
  \   - name: json\n        type: string\n        description: json\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: makes-index-get\n      description: Car API Get Makes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: car-api.makes-index-get\n      with:\n        sort: tools.sort\n        make: tools.make\n        year: tools.year\n      inputParameters:\n      - name: sort\n        type: string\n        description: sort\n      - name: make\n        type: string\n        description: make\n      - name: year\n        type: string\n        description: year\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: makemodeltrimmileages-index-get\n      description: Car API Search vehicle mileages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: car-api.makemodeltrimmileages-index-get\n      with:\n        sort: tools.sort\n\
  \        verbose: tools.verbose\n        make_model_trim_id: tools.make_model_trim_id\n        combined_mpg: tools.combined_mpg\n        epa_city_mpg: tools.epa_city_mpg\n        epa_highway_mpg: tools.epa_highway_mpg\n        range_city: tools.range_city\n        range_highway: tools.range_highway\n        make_model_id: tools.make_model_id\n        make_id: tools.make_id\n        year: tools.year\n        make: tools.make\n        model: tools.model\n        trim: tools.trim\n        json: tools.json\n      inputParameters:\n      - name: sort\n        type: string\n        description: sort\n      - name: verbose\n        type: string\n        description: Includes make, model and trim\n      - name: make_model_trim_id\n        type: string\n        description: make_model_trim_id\n      - name: combined_mpg\n        type: string\n        description: combined_mpg\n      - name: epa_city_mpg\n        type: string\n        description: epa_city_mpg\n      - name: epa_highway_mpg\n  \
  \      type: string\n        description: epa_highway_mpg\n      - name: range_city\n        type: string\n        description: range_city\n      - name: range_highway\n        type: string\n        description: range_highway\n      - name: make_model_id\n        type: string\n        description: make_model_id\n      - name: make_id\n        type: string\n        description: make_id\n      - name: year\n        type: string\n        description: year\n      - name: make\n        type: string\n        description: make\n      - name: model\n        type: string\n        description: model\n      - name: trim\n        type: string\n        description: trim\n      - name: json\n        type: string\n        description: json\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: makemodels-index-get\n      description: Car API Get Models\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: car-api.makemodels-index-get\n\
  \      with:\n        sort: tools.sort\n        verbose: tools.verbose\n        year: tools.year\n        make: tools.make\n        model: tools.model\n        make_id: tools.make_id\n        json: tools.json\n      inputParameters:\n      - name: sort\n        type: string\n        description: sort\n      - name: verbose\n        type: string\n        description: Includes make and model\n      - name: year\n        type: string\n        description: year\n      - name: make\n        type: string\n        description: make\n      - name: model\n        type: string\n        description: model\n      - name: make_id\n        type: string\n        description: make_id\n      - name: json\n        type: string\n        description: json\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: makemodeltrims-index-get\n      description: Car API Search trims\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: car-api.makemodeltrims-index-get\n\
  \      with:\n        sort: tools.sort\n        verbose: tools.verbose\n        year: tools.year\n        make: tools.make\n        model: tools.model\n        trim: tools.trim\n        make_model_id: tools.make_model_id\n        make_id: tools.make_id\n        json: tools.json\n      inputParameters:\n      - name: sort\n        type: string\n        description: sort\n      - name: verbose\n        type: string\n        description: Includes make, model and trim\n      - name: year\n        type: string\n        description: year\n      - name: make\n        type: string\n        description: make\n      - name: model\n        type: string\n        description: model\n      - name: trim\n        type: string\n        description: trim\n      - name: make_model_id\n        type: string\n        description: make_model_id\n      - name: make_id\n        type: string\n  \n\n# --- truncated at 32 KB (34 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/car-api/refs/heads/main/capabilities/car-api-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/car-api/refs/heads/main/capabilities/car-api-capability.yaml
tags:
- Car
- Api
- API
tools:
- description: Car API Get API Usage
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: account-requests-get
- description: Car API Get Today's API Usage
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: account-requeststoday-get
- description: Car API JWT Login
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auth-api-post
- description: Car API Search vehicle bodies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: makemodeltrimbodies-index-get
- description: Car API Get Data Feed
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: datafeeds-download-get
- description: Car API Data Feed Last Updated
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: datafeeds-lastupdated-get
- description: Car API Search vehicle engines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: makemodeltrimengines-index-get
- description: Car API Search vehicle exterior colors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: makemodeltrimexteriorcolors-index-get
- description: Car API Search vehicle interior colors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: makemodeltriminteriorcolors-index-get
- description: Car API Get Makes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: makes-index-get
- description: Car API Search vehicle mileages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: makemodeltrimmileages-index-get
- description: Car API Get Models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: makemodels-index-get
- description: Car API Search trims
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: makemodeltrims-index-get
- description: Car API Get vehicle data.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: makemodeltrims-view-get
- description: Car API Get Vehicle Attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: vehicleattributes-display-get
- description: Car API Vin Decoder
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: vindecoder-index-get
- description: Car API Get Years List
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: years-index-get
---
