---
categories: []
consumed_apis: []
description: The FRED API allows developers to retrieve economic data from the Federal Reserve Bank of St. Louis including categories, releases, series, sources, tags, and observations across thousands of economic time series.
layout: capability
name: Federal Reserve FRED API
operations:
- description: Get a category
  method: GET
  name: getcategory
  path: /category
- description: Get child categories
  method: GET
  name: getcategorychildren
  path: /category/children
- description: Get series in a category
  method: GET
  name: getcategoryseries
  path: /category/series
- description: Get all releases
  method: GET
  name: getreleases
  path: /releases
- description: Get a release
  method: GET
  name: getrelease
  path: /release
- description: Get series for a release
  method: GET
  name: getreleaseseries
  path: /release/series
- description: Get a series
  method: GET
  name: getseries
  path: /series
- description: Get observations for a series
  method: GET
  name: getseriesobservations
  path: /series/observations
- description: Search series by text
  method: GET
  name: searchseries
  path: /series/search
- description: Get all sources
  method: GET
  name: getsources
  path: /sources
- description: Get a source
  method: GET
  name: getsource
  path: /source
- description: Get all tags
  method: GET
  name: gettags
  path: /tags
- description: Get related tags
  method: GET
  name: getrelatedtags
  path: /related_tags
personas: []
provider_name: Federal Reserve
provider_slug: federal-reserve
search_terms:
- getcategoryseries
- economics
- searchseries
- getseriesobservations
- search series by text
- get all sources
- get a category
- get observations for a series
- getreleaseseries
- get a release
- finance
- get series in a category
- get all tags
- get related tags
- getcategorychildren
- getreleases
- get all releases
- getsource
- getrelease
- getcategory
- getseries
- api
- getsources
- gettags
- getrelatedtags
- reserve
- federal government
- get child categories
- get a source
- federal
- get a series
- get series for a release
slug: federal-reserve-capability
source_filename: federal-reserve-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Federal Reserve FRED API\n  description: The FRED API allows developers to retrieve economic data from the Federal Reserve Bank of St. Louis including\n    categories, releases, series, sources, tags, and observations across thousands of economic time series.\n  tags:\n  - Federal\n  - Reserve\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: federal-reserve\n    baseUri: https://api.stlouisfed.org/fred\n    description: Federal Reserve FRED API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: api_key\n      value: '{{FEDERAL_RESERVE_TOKEN}}'\n    resources:\n    - name: category\n      path: /category\n      operations:\n      - name: getcategory\n        method: GET\n        description: Get a category\n        inputParameters:\n        - name: category_id\n          in: query\n          type: integer\n          required: true\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: category-children\n      path: /category/children\n      operations:\n      - name: getcategorychildren\n        method: GET\n        description: Get child categories\n        inputParameters:\n        - name: category_id\n          in: query\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: category-series\n      path: /category/series\n      operations:\n      - name: getcategoryseries\n        method: GET\n        description: Get series in a category\n        inputParameters:\n        - name: category_id\n          in: query\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ releases\n      path: /releases\n      operations:\n      - name: getreleases\n        method: GET\n        description: Get all releases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: release\n      path: /release\n      operations:\n      - name: getrelease\n        method: GET\n        description: Get a release\n        inputParameters:\n        - name: release_id\n          in: query\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: release-series\n      path: /release/series\n      operations:\n      - name: getreleaseseries\n        method: GET\n        description: Get series for a release\n        inputParameters:\n        - name: release_id\n          in: query\n          type: integer\n          required: true\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: series\n      path: /series\n      operations:\n      - name: getseries\n        method: GET\n        description: Get a series\n        inputParameters:\n        - name: series_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: series-observations\n      path: /series/observations\n      operations:\n      - name: getseriesobservations\n        method: GET\n        description: Get observations for a series\n        inputParameters:\n        - name: series_id\n          in: query\n          type: string\n          required: true\n        - name: observation_start\n          in: query\n          type: string\n        - name: observation_end\n          in: query\n          type: string\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: series-search\n      path: /series/search\n      operations:\n      - name: searchseries\n        method: GET\n        description: Search series by text\n        inputParameters:\n        - name: search_text\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sources\n      path: /sources\n      operations:\n      - name: getsources\n        method: GET\n        description: Get all sources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: source\n      path: /source\n      operations:\n      - name: getsource\n        method: GET\n        description: Get a source\n        inputParameters:\n        - name: source_id\n          in: query\n\
  \          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /tags\n      operations:\n      - name: gettags\n        method: GET\n        description: Get all tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: related-tags\n      path: /related_tags\n      operations:\n      - name: getrelatedtags\n        method: GET\n        description: Get related tags\n        inputParameters:\n        - name: tag_names\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: federal-reserve-rest\n    description: REST adapter for Federal Reserve FRED API.\n   \
  \ resources:\n    - path: /category\n      name: getcategory\n      operations:\n      - method: GET\n        name: getcategory\n        description: Get a category\n        call: federal-reserve.getcategory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /category/children\n      name: getcategorychildren\n      operations:\n      - method: GET\n        name: getcategorychildren\n        description: Get child categories\n        call: federal-reserve.getcategorychildren\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /category/series\n      name: getcategoryseries\n      operations:\n      - method: GET\n        name: getcategoryseries\n        description: Get series in a category\n        call: federal-reserve.getcategoryseries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /releases\n      name: getreleases\n      operations:\n      - method: GET\n        name: getreleases\n\
  \        description: Get all releases\n        call: federal-reserve.getreleases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /release\n      name: getrelease\n      operations:\n      - method: GET\n        name: getrelease\n        description: Get a release\n        call: federal-reserve.getrelease\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /release/series\n      name: getreleaseseries\n      operations:\n      - method: GET\n        name: getreleaseseries\n        description: Get series for a release\n        call: federal-reserve.getreleaseseries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /series\n      name: getseries\n      operations:\n      - method: GET\n        name: getseries\n        description: Get a series\n        call: federal-reserve.getseries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /series/observations\n\
  \      name: getseriesobservations\n      operations:\n      - method: GET\n        name: getseriesobservations\n        description: Get observations for a series\n        call: federal-reserve.getseriesobservations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /series/search\n      name: searchseries\n      operations:\n      - method: GET\n        name: searchseries\n        description: Search series by text\n        call: federal-reserve.searchseries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sources\n      name: getsources\n      operations:\n      - method: GET\n        name: getsources\n        description: Get all sources\n        call: federal-reserve.getsources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /source\n      name: getsource\n      operations:\n      - method: GET\n        name: getsource\n        description: Get a source\n        call:\
  \ federal-reserve.getsource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags\n      name: gettags\n      operations:\n      - method: GET\n        name: gettags\n        description: Get all tags\n        call: federal-reserve.gettags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /related_tags\n      name: getrelatedtags\n      operations:\n      - method: GET\n        name: getrelatedtags\n        description: Get related tags\n        call: federal-reserve.getrelatedtags\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: federal-reserve-mcp\n    transport: http\n    description: MCP adapter for Federal Reserve FRED API for AI agent use.\n    tools:\n    - name: getcategory\n      description: Get a category\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-reserve.getcategory\n\
  \      with:\n        category_id: tools.category_id\n      inputParameters:\n      - name: category_id\n        type: integer\n        description: category_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcategorychildren\n      description: Get child categories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-reserve.getcategorychildren\n      with:\n        category_id: tools.category_id\n      inputParameters:\n      - name: category_id\n        type: integer\n        description: category_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcategoryseries\n      description: Get series in a category\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-reserve.getcategoryseries\n      with:\n        category_id: tools.category_id\n      inputParameters:\n\
  \      - name: category_id\n        type: integer\n        description: category_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getreleases\n      description: Get all releases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-reserve.getreleases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrelease\n      description: Get a release\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-reserve.getrelease\n      with:\n        release_id: tools.release_id\n      inputParameters:\n      - name: release_id\n        type: integer\n        description: release_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getreleaseseries\n      description: Get series for a release\n      hints:\n        readOnly: true\n       \
  \ destructive: false\n        idempotent: true\n      call: federal-reserve.getreleaseseries\n      with:\n        release_id: tools.release_id\n      inputParameters:\n      - name: release_id\n        type: integer\n        description: release_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getseries\n      description: Get a series\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-reserve.getseries\n      with:\n        series_id: tools.series_id\n      inputParameters:\n      - name: series_id\n        type: string\n        description: series_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getseriesobservations\n      description: Get observations for a series\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-reserve.getseriesobservations\n\
  \      with:\n        series_id: tools.series_id\n        observation_start: tools.observation_start\n        observation_end: tools.observation_end\n      inputParameters:\n      - name: series_id\n        type: string\n        description: series_id\n        required: true\n      - name: observation_start\n        type: string\n        description: observation_start\n      - name: observation_end\n        type: string\n        description: observation_end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchseries\n      description: Search series by text\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-reserve.searchseries\n      with:\n        search_text: tools.search_text\n      inputParameters:\n      - name: search_text\n        type: string\n        description: search_text\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsources\n\
  \      description: Get all sources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-reserve.getsources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsource\n      description: Get a source\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-reserve.getsource\n      with:\n        source_id: tools.source_id\n      inputParameters:\n      - name: source_id\n        type: integer\n        description: source_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettags\n      description: Get all tags\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-reserve.gettags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrelatedtags\n      description: Get related tags\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-reserve.getrelatedtags\n      with:\n        tag_names: tools.tag_names\n      inputParameters:\n      - name: tag_names\n        type: string\n        description: tag_names\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FEDERAL_RESERVE_TOKEN: FEDERAL_RESERVE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/federal-reserve/refs/heads/main/capabilities/federal-reserve-capability.yaml
tags:
- Federal
- Reserve
- API
tools:
- description: Get a category
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcategory
- description: Get child categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcategorychildren
- description: Get series in a category
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcategoryseries
- description: Get all releases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreleases
- description: Get a release
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrelease
- description: Get series for a release
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreleaseseries
- description: Get a series
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getseries
- description: Get observations for a series
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getseriesobservations
- description: Search series by text
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchseries
- description: Get all sources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsources
- description: Get a source
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsource
- description: Get all tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettags
- description: Get related tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrelatedtags
---
