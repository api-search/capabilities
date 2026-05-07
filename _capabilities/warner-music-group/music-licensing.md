---
categories: []
consumed_apis: []
description: Unified workflow for Warner Music Group music licensing operations. Enables content creators, developers, and licensing professionals to search the WMG catalog, discover tracks, and submit license requests for sync, mechanical, digital, and performance rights for recordings and compositions from Warner Records, Atlantic Records, Elektra, and Warner Chappell Music.
layout: capability
name: Warner Music Group Music Licensing
operations:
- description: Search WMG catalog for recordings and compositions
  method: GET
  name: search-catalog
  path: /v1/catalog/search
- description: Get track details by ISRC code
  method: GET
  name: get-track
  path: /v1/tracks/{isrc}
- description: Get artist information and catalog summary
  method: GET
  name: get-artist
  path: /v1/artists/{artistId}
- description: List license requests
  method: GET
  name: list-licenses
  path: /v1/licenses
- description: Submit a new music license request
  method: POST
  name: request-license
  path: /v1/licenses
personas: []
provider_name: Warner Music Group
provider_slug: warner-music-group
search_terms:
- get artist profile and catalog information from the wmg roster
- search catalog
- music licensing
- streaming
- submit a synchronization license request for use in film, tv, or advertising
- licensing
- publishing
- sync licensing
- get track details by isrc code
- request sync license
- artist profile data
- get artist
- search wmg catalog for recordings and compositions
- get track by isrc
- get detailed information about a wmg recording using its isrc code
- music
- get artist information and catalog summary
- search the warner music group catalog for recordings and compositions by artist, title, or genre
- catalog
- list license requests
- get track
- individual track details
- entertainment
- search wmg catalog
- music catalog discovery
- rights management
- list submitted music license requests and their approval status
- warner music group
- submit a new music license request
- request license
- list licenses
- license request management
slug: music-licensing
source_filename: music-licensing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Warner Music Group Music Licensing\n  description: Unified workflow for Warner Music Group music licensing operations. Enables content creators, developers, and\n    licensing professionals to search the WMG catalog, discover tracks, and submit license requests for sync, mechanical,\n    digital, and performance rights for recordings and compositions from Warner Records, Atlantic Records, Elektra, and Warner\n    Chappell Music.\n  tags:\n  - Warner Music Group\n  - Music Licensing\n  - Sync Licensing\n  - Catalog\n  - Rights Management\n  - Entertainment\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WMG_ACCESS_TOKEN: WMG_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: wmg-licensing\n    baseUri: https://api.wmg.com\n    description: Warner Music Group Licensing API\n    authentication:\n      type: bearer\n      token: '{{WMG_ACCESS_TOKEN}}'\n    resources:\n    - name:\
  \ catalog-search\n      path: /v1/catalog/search\n      description: Music catalog search\n      operations:\n      - name: search-catalog\n        method: GET\n        description: Search WMG catalog for recordings and compositions\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Recording, composition, or both\n        - name: label\n          in: query\n          type: string\n          required: false\n          description: Filter by label\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: track\n      path: /v1/tracks/{isrc}\n      description: Track details by ISRC\n      operations:\n      - name: get-track\n        method: GET\n        description: Get track details by ISRC code\n        inputParameters:\n        - name: isrc\n          in: path\n          type: string\n          required: true\n          description: International Standard Recording Code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: artist\n      path: /v1/artists/{artistId}\n      description: Artist information\n      operations:\n      - name: get-artist\n        method: GET\n        description: Get artist profile and catalog summary\n        inputParameters:\n        - name: artistId\n          in: path\n          type: string\n          required: true\n          description: WMG artist identifier\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: licenses\n      path: /v1/licenses\n      description: License request management\n      operations:\n      - name: list-licenses\n        method: GET\n        description: List submitted license requests\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        - name: licenseType\n          in: query\n          type: string\n          required: false\n          description: Filter by license type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: request-license\n        method: POST\n        description: Submit a new music license request\n        inputParameters:\n        - name: trackIsrc\n          in: body\n          type: string\n          required: true\n      \
  \    description: ISRC of the recording to license\n        - name: licenseType\n          in: body\n          type: string\n          required: true\n          description: Type of license (sync, mechanical, digital, performance)\n        - name: territory\n          in: body\n          type: string\n          required: true\n          description: License territory\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            trackIsrc: '{{tools.trackIsrc}}'\n            licenseType: '{{tools.licenseType}}'\n            useCase: '{{tools.useCase}}'\n            territory: '{{tools.territory}}'\n            startDate: '{{tools.startDate}}'\n            endDate: '{{tools.endDate}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: wmg-music-api\n    description: Unified REST API for WMG music licensing and catalog operations.\n    resources:\n  \
  \  - path: /v1/catalog/search\n      name: catalog-search\n      description: Music catalog discovery\n      operations:\n      - method: GET\n        name: search-catalog\n        description: Search WMG catalog for recordings and compositions\n        call: wmg-licensing.search-catalog\n        with:\n          q: rest.q\n          type: rest.type\n          label: rest.label\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tracks/{isrc}\n      name: track\n      description: Individual track details\n      operations:\n      - method: GET\n        name: get-track\n        description: Get track details by ISRC code\n        call: wmg-licensing.get-track\n        with:\n          isrc: rest.isrc\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/artists/{artistId}\n      name: artist\n      description: Artist profile data\n      operations:\n\
  \      - method: GET\n        name: get-artist\n        description: Get artist information and catalog summary\n        call: wmg-licensing.get-artist\n        with:\n          artistId: rest.artistId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/licenses\n      name: licenses\n      description: License request management\n      operations:\n      - method: GET\n        name: list-licenses\n        description: List license requests\n        call: wmg-licensing.list-licenses\n        with:\n          status: rest.status\n          licenseType: rest.licenseType\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: request-license\n        description: Submit a new music license request\n        call: wmg-licensing.request-license\n        with:\n          trackIsrc: rest.trackIsrc\n          licenseType: rest.licenseType\n          territory: rest.territory\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: wmg-music-mcp\n    transport: http\n    description: MCP server for AI-assisted WMG music licensing and catalog discovery.\n    tools:\n    - name: search-wmg-catalog\n      description: Search the Warner Music Group catalog for recordings and compositions by artist, title, or genre\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wmg-licensing.search-catalog\n      with:\n        q: tools.q\n        type: tools.type\n        label: tools.label\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-track-by-isrc\n      description: Get detailed information about a WMG recording using its ISRC code\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wmg-licensing.get-track\n      with:\n        isrc: tools.isrc\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-artist\n      description:\
  \ Get artist profile and catalog information from the WMG roster\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wmg-licensing.get-artist\n      with:\n        artistId: tools.artistId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-licenses\n      description: List submitted music license requests and their approval status\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wmg-licensing.list-licenses\n      with:\n        status: tools.status\n        licenseType: tools.licenseType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: request-sync-license\n      description: Submit a synchronization license request for use in film, TV, or advertising\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: wmg-licensing.request-license\n      with:\n        trackIsrc: tools.trackIsrc\n        licenseType: tools.licenseType\n\
  \        territory: tools.territory\n        useCase: tools.useCase\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/warner-music-group/refs/heads/main/capabilities/music-licensing.yaml
tags:
- Warner Music Group
- Music Licensing
- Sync Licensing
- Catalog
- Rights Management
- Entertainment
tools:
- description: Search the Warner Music Group catalog for recordings and compositions by artist, title, or genre
  hints:
    openWorld: true
    readOnly: true
  name: search-wmg-catalog
- description: Get detailed information about a WMG recording using its ISRC code
  hints:
    openWorld: false
    readOnly: true
  name: get-track-by-isrc
- description: Get artist profile and catalog information from the WMG roster
  hints:
    openWorld: false
    readOnly: true
  name: get-artist
- description: List submitted music license requests and their approval status
  hints:
    openWorld: false
    readOnly: true
  name: list-licenses
- description: Submit a synchronization license request for use in film, TV, or advertising
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: request-sync-license
---
