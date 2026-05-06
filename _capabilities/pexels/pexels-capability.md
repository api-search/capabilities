---
categories: []
consumed_apis: []
description: The Pexels API provides programmatic access to Pexels' free stock photo and video library, plus curated collections. Use it to search photos and videos, fetch curated and popular media, and integrate Pexels content into apps and websites.
layout: capability
name: Pexels API
operations:
- description: Search Photos
  method: GET
  name: searchphotos
  path: /search
- description: Curated Photos
  method: GET
  name: getcuratedphotos
  path: /curated
- description: Get Photo
  method: GET
  name: getphoto
  path: /photos/{id}
- description: Search Videos
  method: GET
  name: searchvideos
  path: /videos/search
- description: Popular Videos
  method: GET
  name: getpopularvideos
  path: /videos/popular
- description: Get Video
  method: GET
  name: getvideo
  path: /videos/videos/{id}
- description: Featured Collections
  method: GET
  name: getfeaturedcollections
  path: /collections/featured
- description: My Collections
  method: GET
  name: getmycollections
  path: /collections
- description: Collection Media
  method: GET
  name: getcollectionmedia
  path: /collections/{id}
personas: []
provider_name: Pexels
provider_slug: pexels
search_terms:
- getmycollections
- photos
- searchvideos
- getcuratedphotos
- get photo
- curated photos
- getphoto
- pexels
- getvideo
- videos
- popular videos
- getfeaturedcollections
- search photos
- collection media
- search videos
- get video
- getcollectionmedia
- api
- my collections
- searchphotos
- getpopularvideos
- stock media
- featured collections
slug: pexels-capability
source_filename: pexels-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Pexels API\n  description: The Pexels API provides programmatic access to Pexels' free stock photo and video library, plus curated collections.\n    Use it to search photos and videos, fetch curated and popular media, and integrate Pexels content into apps and websites.\n  tags:\n  - Pexels\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pexels\n    baseUri: https://api.pexels.com/v1\n    description: Pexels API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{PEXELS_TOKEN}}'\n    resources:\n    - name: search\n      path: /search\n      operations:\n      - name: searchphotos\n        method: GET\n        description: Search Photos\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search keyword such as \"Ocean\"\
  \ or \"Tigers\".\n        - name: orientation\n          in: query\n          type: string\n        - name: size\n          in: query\n          type: string\n        - name: color\n          in: query\n          type: string\n        - name: locale\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n        - name: per_page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: curated\n      path: /curated\n      operations:\n      - name: getcuratedphotos\n        method: GET\n        description: Curated Photos\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n        - name: per_page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: photos-id\n      path: /photos/{id}\n      operations:\n      - name: getphoto\n        method: GET\n        description: Get Photo\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: videos-search\n      path: /videos/search\n      operations:\n      - name: searchvideos\n        method: GET\n        description: Search Videos\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        - name: orientation\n          in: query\n          type: string\n        - name: size\n          in: query\n          type: string\n        - name: locale\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n        - name: per_page\n          in: query\n \
  \         type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: videos-popular\n      path: /videos/popular\n      operations:\n      - name: getpopularvideos\n        method: GET\n        description: Popular Videos\n        inputParameters:\n        - name: min_width\n          in: query\n          type: integer\n        - name: min_height\n          in: query\n          type: integer\n        - name: min_duration\n          in: query\n          type: integer\n        - name: max_duration\n          in: query\n          type: integer\n        - name: page\n          in: query\n          type: integer\n        - name: per_page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: videos-videos-id\n      path: /videos/videos/{id}\n      operations:\n      -\
  \ name: getvideo\n        method: GET\n        description: Get Video\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: collections-featured\n      path: /collections/featured\n      operations:\n      - name: getfeaturedcollections\n        method: GET\n        description: Featured Collections\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n        - name: per_page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: collections\n      path: /collections\n      operations:\n      - name: getmycollections\n        method: GET\n        description: My Collections\n        inputParameters:\n        - name: page\n\
  \          in: query\n          type: integer\n        - name: per_page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: collections-id\n      path: /collections/{id}\n      operations:\n      - name: getcollectionmedia\n        method: GET\n        description: Collection Media\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: type\n          in: query\n          type: string\n        - name: sort\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n        - name: per_page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pexels-rest\n\
  \    description: REST adapter for Pexels API.\n    resources:\n    - path: /search\n      name: searchphotos\n      operations:\n      - method: GET\n        name: searchphotos\n        description: Search Photos\n        call: pexels.searchphotos\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /curated\n      name: getcuratedphotos\n      operations:\n      - method: GET\n        name: getcuratedphotos\n        description: Curated Photos\n        call: pexels.getcuratedphotos\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /photos/{id}\n      name: getphoto\n      operations:\n      - method: GET\n        name: getphoto\n        description: Get Photo\n        call: pexels.getphoto\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /videos/search\n      name: searchvideos\n      operations:\n      - method: GET\n        name: searchvideos\n\
  \        description: Search Videos\n        call: pexels.searchvideos\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /videos/popular\n      name: getpopularvideos\n      operations:\n      - method: GET\n        name: getpopularvideos\n        description: Popular Videos\n        call: pexels.getpopularvideos\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /videos/videos/{id}\n      name: getvideo\n      operations:\n      - method: GET\n        name: getvideo\n        description: Get Video\n        call: pexels.getvideo\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /collections/featured\n      name: getfeaturedcollections\n      operations:\n      - method: GET\n        name: getfeaturedcollections\n        description: Featured Collections\n        call: pexels.getfeaturedcollections\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /collections\n      name: getmycollections\n      operations:\n      - method: GET\n        name: getmycollections\n        description: My Collections\n        call: pexels.getmycollections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /collections/{id}\n      name: getcollectionmedia\n      operations:\n      - method: GET\n        name: getcollectionmedia\n        description: Collection Media\n        call: pexels.getcollectionmedia\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pexels-mcp\n    transport: http\n    description: MCP adapter for Pexels API for AI agent use.\n    tools:\n    - name: searchphotos\n      description: Search Photos\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pexels.searchphotos\n      with:\n       \
  \ query: tools.query\n        orientation: tools.orientation\n        size: tools.size\n        color: tools.color\n        locale: tools.locale\n        page: tools.page\n        per_page: tools.per_page\n      inputParameters:\n      - name: query\n        type: string\n        description: Search keyword such as \"Ocean\" or \"Tigers\".\n        required: true\n      - name: orientation\n        type: string\n        description: orientation\n      - name: size\n        type: string\n        description: size\n      - name: color\n        type: string\n        description: color\n      - name: locale\n        type: string\n        description: locale\n      - name: page\n        type: integer\n        description: page\n      - name: per_page\n        type: integer\n        description: per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcuratedphotos\n      description: Curated Photos\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: pexels.getcuratedphotos\n      with:\n        page: tools.page\n        per_page: tools.per_page\n      inputParameters:\n      - name: page\n        type: integer\n        description: page\n      - name: per_page\n        type: integer\n        description: per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getphoto\n      description: Get Photo\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pexels.getphoto\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchvideos\n      description: Search Videos\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pexels.searchvideos\n      with:\n        query: tools.query\n\
  \        orientation: tools.orientation\n        size: tools.size\n        locale: tools.locale\n        page: tools.page\n        per_page: tools.per_page\n      inputParameters:\n      - name: query\n        type: string\n        description: query\n        required: true\n      - name: orientation\n        type: string\n        description: orientation\n      - name: size\n        type: string\n        description: size\n      - name: locale\n        type: string\n        description: locale\n      - name: page\n        type: integer\n        description: page\n      - name: per_page\n        type: integer\n        description: per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpopularvideos\n      description: Popular Videos\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pexels.getpopularvideos\n      with:\n        min_width: tools.min_width\n        min_height: tools.min_height\n \
  \       min_duration: tools.min_duration\n        max_duration: tools.max_duration\n        page: tools.page\n        per_page: tools.per_page\n      inputParameters:\n      - name: min_width\n        type: integer\n        description: min_width\n      - name: min_height\n        type: integer\n        description: min_height\n      - name: min_duration\n        type: integer\n        description: min_duration\n      - name: max_duration\n        type: integer\n        description: max_duration\n      - name: page\n        type: integer\n        description: page\n      - name: per_page\n        type: integer\n        description: per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvideo\n      description: Get Video\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pexels.getvideo\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description:\
  \ id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfeaturedcollections\n      description: Featured Collections\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pexels.getfeaturedcollections\n      with:\n        page: tools.page\n        per_page: tools.per_page\n      inputParameters:\n      - name: page\n        type: integer\n        description: page\n      - name: per_page\n        type: integer\n        description: per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmycollections\n      description: My Collections\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pexels.getmycollections\n      with:\n        page: tools.page\n        per_page: tools.per_page\n      inputParameters:\n      - name: page\n        type: integer\n        description: page\n      - name: per_page\n\
  \        type: integer\n        description: per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcollectionmedia\n      description: Collection Media\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pexels.getcollectionmedia\n      with:\n        id: tools.id\n        type: tools.type\n        sort: tools.sort\n        page: tools.page\n        per_page: tools.per_page\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      - name: type\n        type: string\n        description: type\n      - name: sort\n        type: string\n        description: sort\n      - name: page\n        type: integer\n        description: page\n      - name: per_page\n        type: integer\n        description: per_page\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PEXELS_TOKEN: PEXELS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pexels/refs/heads/main/capabilities/pexels-capability.yaml
tags:
- Pexels
- API
tools:
- description: Search Photos
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchphotos
- description: Curated Photos
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcuratedphotos
- description: Get Photo
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getphoto
- description: Search Videos
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchvideos
- description: Popular Videos
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpopularvideos
- description: Get Video
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvideo
- description: Featured Collections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfeaturedcollections
- description: My Collections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmycollections
- description: Collection Media
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcollectionmedia
---
