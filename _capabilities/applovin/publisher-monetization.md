---
categories: []
consumed_apis: []
description: Workflow capability for mobile app publishers monetizing with AppLovin MAX. Combines MAX ad unit management with MAX revenue reporting so a single mediation/ops role can configure waterfalls, run experiments, manage test devices, and pull revenue analytics.
layout: capability
name: AppLovin Publisher Monetization
operations:
- description: List ad units.
  method: GET
  name: list-ad-units
  path: /v1/ad-units
- description: Create an ad unit.
  method: POST
  name: create-ad-unit
  path: /v1/ad-units
- description: Get a single ad unit by ID.
  method: GET
  name: get-ad-unit
  path: /v1/ad-units/{ad_unit_id}
- description: Update an ad unit.
  method: POST
  name: update-ad-unit
  path: /v1/ad-units/{ad_unit_id}
- description: List test devices.
  method: GET
  name: list-test-devices
  path: /v1/test-devices
- description: Register a test device.
  method: POST
  name: create-test-device
  path: /v1/test-devices
- description: Get aggregated MAX revenue rows.
  method: GET
  name: get-revenue-report
  path: /v1/revenue-report
personas: []
provider_name: AppLovin
provider_slug: applovin
search_terms:
- app monetization
- get ad unit
- user acquisition
- conversion tracking
- get revenue report
- get a single ad unit by id.
- list ad units.
- get a max ad unit by id.
- mobile
- max revenue analytics.
- update a max ad unit (partial).
- applovin
- create a new max ad unit.
- update an ad unit.
- create an ad unit.
- adtech
- register a new max test device.
- create ad unit
- list max ad units.
- max ad units.
- list test devices.
- list max test devices.
- get max revenue report rows.
- max
- list ad units
- update ad unit
- monetization
- max test devices.
- register a test device.
- get aggregated max revenue rows.
- create test device
- list test devices
- publisher
- advertising
- mediation
- marketing technology
- single max ad unit.
slug: publisher-monetization
source_filename: publisher-monetization.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AppLovin Publisher Monetization\n  description: Workflow capability for mobile app publishers monetizing with AppLovin MAX. Combines MAX ad unit management\n    with MAX revenue reporting so a single mediation/ops role can configure waterfalls, run experiments, manage test devices,\n    and pull revenue analytics.\n  tags:\n  - AppLovin\n  - MAX\n  - Mediation\n  - Monetization\n  - Publisher\n  created: '2026-05-05'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APPLOVIN_MANAGEMENT_KEY: APPLOVIN_MANAGEMENT_KEY\n    APPLOVIN_REPORT_KEY: APPLOVIN_REPORT_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: applovin-max-ad-unit-management\n    baseUri: https://o.applovin.com/mediation/v1\n    description: MAX mediation management API.\n    authentication:\n      type: apikey\n      key: Api-Key\n      value: '{{APPLOVIN_MANAGEMENT_KEY}}'\n      placement: header\n    resources:\n    - name: ad-units\n      path:\
  \ /ad_units\n      description: Ad unit collection.\n      operations:\n      - name: list-ad-units\n        method: GET\n        description: List all ad units.\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Optional fields to include.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max rows.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ad-unit\n      path: /ad_unit\n      description: Single ad unit.\n      operations:\n      - name: create-ad-unit\n        method: POST\n        description: Create a new ad unit.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            platform: '{{tools.platform}}'\n            package_name: '{{tools.package_name}}'\n            ad_format: '{{tools.ad_format}}'\n    - name: ad-unit-detail\n      path: /ad_unit/{ad_unit_id}\n      description: Single ad unit by ID.\n      operations:\n      - name: get-ad-unit\n        method: GET\n        description: Get an ad unit by ID.\n        inputParameters:\n        - name: ad_unit_id\n          in: path\n          type: string\n          required: true\n          description: Ad unit identifier.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated optional fields.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-ad-unit\n        method: POST\n\
  \        description: Update an ad unit (partial update).\n        inputParameters:\n        - name: ad_unit_id\n          in: path\n          type: string\n          required: true\n          description: Ad unit identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: '{{tools.body}}'\n    - name: test-devices\n      path: /test_devices\n      description: Test devices.\n      operations:\n      - name: list-test-devices\n        method: GET\n        description: List test devices.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: test-device\n      path: /test_device\n      description: Single test device.\n      operations:\n      - name: create-test-device\n        method: POST\n        description: Register a new test device.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            device_id: '{{tools.device_id}}'\n            disabled: '{{tools.disabled}}'\n            network: '{{tools.network}}'\n  - type: http\n    namespace: applovin-max-revenue-reporting\n    baseUri: https://r.applovin.com\n    description: AppLovin MAX revenue reporting endpoint.\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{APPLOVIN_REPORT_KEY}}'\n      placement: query\n    resources:\n    - name: revenue-report\n      path: /maxReport\n      description: Aggregated MAX revenue rows.\n      operations:\n      - name: get-max-revenue-report\n        method: GET\n        description: Get MAX Revenue Report for a date range.\n        inputParameters:\n        - name: columns\n          in: query\n          type: string\n          required: true\n          description:\
  \ Comma-separated list of report columns.\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start date YYYY-MM-DD.\n        - name: end\n          in: query\n          type: string\n          required: true\n          description: End date YYYY-MM-DD (within 45 days of start).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Response format json or csv.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum rows.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: publisher-monetization-api\n    description:\
  \ Unified REST API for AppLovin publisher monetization workflows.\n    resources:\n    - path: /v1/ad-units\n      name: ad-units\n      description: MAX ad units.\n      operations:\n      - method: GET\n        name: list-ad-units\n        description: List ad units.\n        call: applovin-max-ad-unit-management.list-ad-units\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-ad-unit\n        description: Create an ad unit.\n        call: applovin-max-ad-unit-management.create-ad-unit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ad-units/{ad_unit_id}\n      name: ad-unit\n      description: Single MAX ad unit.\n      operations:\n      - method: GET\n        name: get-ad-unit\n        description: Get a single ad unit by ID.\n        call: applovin-max-ad-unit-management.get-ad-unit\n        with:\n          ad_unit_id: rest.ad_unit_id\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n      - method: POST\n        name: update-ad-unit\n        description: Update an ad unit.\n        call: applovin-max-ad-unit-management.update-ad-unit\n        with:\n          ad_unit_id: rest.ad_unit_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/test-devices\n      name: test-devices\n      description: MAX test devices.\n      operations:\n      - method: GET\n        name: list-test-devices\n        description: List test devices.\n        call: applovin-max-ad-unit-management.list-test-devices\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-test-device\n        description: Register a test device.\n        call: applovin-max-ad-unit-management.create-test-device\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/revenue-report\n      name: revenue-report\n      description: MAX revenue\
  \ analytics.\n      operations:\n      - method: GET\n        name: get-revenue-report\n        description: Get aggregated MAX revenue rows.\n        call: applovin-max-revenue-reporting.get-max-revenue-report\n        with:\n          columns: rest.columns\n          start: rest.start\n          end: rest.end\n          format: rest.format\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: publisher-monetization-mcp\n    transport: http\n    description: MCP server for AI-assisted MAX mediation and revenue analytics.\n    tools:\n    - name: list-ad-units\n      description: List MAX ad units.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: applovin-max-ad-unit-management.list-ad-units\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ad-unit\n      description: Get a MAX ad unit by ID.\n      hints:\n        readOnly: true\n        openWorld: true\n  \
  \    call: applovin-max-ad-unit-management.get-ad-unit\n      with:\n        ad_unit_id: tools.ad_unit_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-ad-unit\n      description: Create a new MAX ad unit.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: applovin-max-ad-unit-management.create-ad-unit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-ad-unit\n      description: Update a MAX ad unit (partial).\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: applovin-max-ad-unit-management.update-ad-unit\n      with:\n        ad_unit_id: tools.ad_unit_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-test-devices\n      description: List MAX test devices.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: applovin-max-ad-unit-management.list-test-devices\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-test-device\n      description: Register a new MAX test device.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: applovin-max-ad-unit-management.create-test-device\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-revenue-report\n      description: Get MAX revenue report rows.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: applovin-max-revenue-reporting.get-max-revenue-report\n      with:\n        columns: tools.columns\n        start: tools.start\n        end: tools.end\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/applovin/refs/heads/main/capabilities/publisher-monetization.yaml
tags:
- AppLovin
- MAX
- Mediation
- Monetization
- Publisher
tools:
- description: List MAX ad units.
  hints:
    openWorld: true
    readOnly: true
  name: list-ad-units
- description: Get a MAX ad unit by ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-ad-unit
- description: Create a new MAX ad unit.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-ad-unit
- description: Update a MAX ad unit (partial).
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-ad-unit
- description: List MAX test devices.
  hints:
    openWorld: true
    readOnly: true
  name: list-test-devices
- description: Register a new MAX test device.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-test-device
- description: Get MAX revenue report rows.
  hints:
    openWorld: true
    readOnly: true
  name: get-revenue-report
---
