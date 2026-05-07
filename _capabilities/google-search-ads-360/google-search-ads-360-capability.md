---
categories: []
consumed_apis: []
description: The Search Ads 360 Reporting API enables automated report downloading and programmatic access to search advertising campaign data using search and streaming query methods with a SQL-like query language.
layout: capability
name: Google Search Ads 360 Reporting API
operations:
- description: Google Search Ads 360 Reporting Search campaign data
  method: POST
  name: search
  path: /v0/customers/{customerId}/searchAds360:search
- description: Google Search Ads 360 Reporting Stream campaign data
  method: POST
  name: searchstream
  path: /v0/customers/{customerId}/searchAds360:searchStream
- description: Google Search Ads 360 Reporting Get a resource
  method: GET
  name: getresource
  path: /v0/{resourceName}
- description: Google Search Ads 360 Reporting List custom columns
  method: GET
  name: listcustomcolumns
  path: /v0/customers/{customerId}/customColumns
personas: []
provider_name: Google Search Ads 360 Reporting
provider_slug: google-search-ads-360
search_terms:
- keywords
- search ads 360
- google search ads 360 reporting search campaign data
- campaign management
- searchstream
- conversions
- getresource
- google search ads 360 reporting stream campaign data
- reporting
- search
- ads
- google
- search advertising
- api
- google search ads 360 reporting get a resource
- listcustomcolumns
- '360'
- google search ads 360 reporting list custom columns
slug: google-search-ads-360-capability
source_filename: google-search-ads-360-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Search Ads 360 Reporting API\n  description: The Search Ads 360 Reporting API enables automated report downloading and programmatic access to search advertising\n    campaign data using search and streaming query methods with a SQL-like query language.\n  tags:\n  - Google\n  - Search\n  - Ads\n  - '360'\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-search-ads-360\n    baseUri: https://searchads360.googleapis.com\n    description: Google Search Ads 360 Reporting API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_SEARCH_ADS_360_TOKEN}}'\n    resources:\n    - name: v0-customers-customerid-searchads360-search\n      path: /v0/customers/{customerId}/searchAds360:search\n      operations:\n      - name: search\n        method: POST\n        description: Google Search Ads 360 Reporting Search campaign data\n        inputParameters:\n\
  \        - name: customerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v0-customers-customerid-searchads360-searchstrea\n      path: /v0/customers/{customerId}/searchAds360:searchStream\n      operations:\n      - name: searchstream\n        method: POST\n        description: Google Search Ads 360 Reporting Stream campaign data\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v0-resourcename\n      path: /v0/{resourceName}\n      operations:\n      - name: getresource\n        method: GET\n        description: Google Search Ads 360 Reporting Get a resource\n        inputParameters:\n        - name: resourceName\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v0-customers-customerid-customcolumns\n      path: /v0/customers/{customerId}/customColumns\n      operations:\n      - name: listcustomcolumns\n        method: GET\n        description: Google Search Ads 360 Reporting List custom columns\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-search-ads-360-rest\n    description: REST adapter for Google Search Ads 360 Reporting API.\n    resources:\n    - path: /v0/customers/{customerId}/searchAds360:search\n      name: search\n      operations:\n      - method: POST\n  \
  \      name: search\n        description: Google Search Ads 360 Reporting Search campaign data\n        call: google-search-ads-360.search\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v0/customers/{customerId}/searchAds360:searchStream\n      name: searchstream\n      operations:\n      - method: POST\n        name: searchstream\n        description: Google Search Ads 360 Reporting Stream campaign data\n        call: google-search-ads-360.searchstream\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v0/{resourceName}\n      name: getresource\n      operations:\n      - method: GET\n        name: getresource\n        description: Google Search Ads 360 Reporting Get a resource\n        call: google-search-ads-360.getresource\n        with:\n          resourceName: rest.resourceName\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v0/customers/{customerId}/customColumns\n      name: listcustomcolumns\n      operations:\n      - method: GET\n        name: listcustomcolumns\n        description: Google Search Ads 360 Reporting List custom columns\n        call: google-search-ads-360.listcustomcolumns\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-search-ads-360-mcp\n    transport: http\n    description: MCP adapter for Google Search Ads 360 Reporting API for AI agent use.\n    tools:\n    - name: search\n      description: Google Search Ads 360 Reporting Search campaign data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-search-ads-360.search\n      with:\n        customerId: tools.customerId\n      inputParameters:\n      - name: customerId\n        type:\
  \ string\n        description: customerId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchstream\n      description: Google Search Ads 360 Reporting Stream campaign data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-search-ads-360.searchstream\n      with:\n        customerId: tools.customerId\n      inputParameters:\n      - name: customerId\n        type: string\n        description: customerId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getresource\n      description: Google Search Ads 360 Reporting Get a resource\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-search-ads-360.getresource\n      with:\n        resourceName: tools.resourceName\n      inputParameters:\n      - name: resourceName\n        type: string\n        description:\
  \ resourceName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcustomcolumns\n      description: Google Search Ads 360 Reporting List custom columns\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-search-ads-360.listcustomcolumns\n      with:\n        customerId: tools.customerId\n      inputParameters:\n      - name: customerId\n        type: string\n        description: customerId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_SEARCH_ADS_360_TOKEN: GOOGLE_SEARCH_ADS_360_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-search-ads-360/refs/heads/main/capabilities/google-search-ads-360-capability.yaml
tags:
- Google
- Search
- Ads
- '360'
- API
tools:
- description: Google Search Ads 360 Reporting Search campaign data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: search
- description: Google Search Ads 360 Reporting Stream campaign data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchstream
- description: Google Search Ads 360 Reporting Get a resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getresource
- description: Google Search Ads 360 Reporting List custom columns
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcustomcolumns
---
