---
categories: []
consumed_apis: []
description: The unofficial Neighbortunes API provides access to setlists, shows, songs, venues, jamcharts, albums, metadata, links, uploads, and band appearances. No authentication is required.
layout: capability
name: Neighbortunes API
operations:
- description: List setlists
  method: GET
  name: listsetlists
  path: /setlists.{format}
- description: Get a setlist by ID
  method: GET
  name: getsetlist
  path: /setlists/{id}.{format}
- description: Query setlists by column value
  method: GET
  name: querysetlists
  path: /setlists/{column}/{value}.{format}
- description: Latest entries
  method: GET
  name: listlatest
  path: /latest.{format}
- description: List shows
  method: GET
  name: listshows
  path: /shows.{format}
- description: Get a show by ID
  method: GET
  name: getshow
  path: /shows/{id}.{format}
- description: List songs
  method: GET
  name: listsongs
  path: /songs.{format}
- description: Get a song by ID
  method: GET
  name: getsong
  path: /songs/{id}.{format}
- description: List venues
  method: GET
  name: listvenues
  path: /venues.{format}
- description: Get a venue by ID
  method: GET
  name: getvenue
  path: /venues/{id}.{format}
- description: List jamcharts
  method: GET
  name: listjamcharts
  path: /jamcharts.{format}
- description: List albums
  method: GET
  name: listalbums
  path: /albums.{format}
- description: List metadata
  method: GET
  name: listmetadata
  path: /metadata.{format}
- description: List links
  method: GET
  name: listlinks
  path: /links.{format}
- description: List uploads
  method: GET
  name: listuploads
  path: /uploads.{format}
- description: List appearances
  method: GET
  name: listappearances
  path: /appearances.{format}
- description: List unique values for a column
  method: GET
  name: listcolumn
  path: /list/{column}.{format}
personas: []
provider_name: Neighbortunes
provider_slug: neighbortunes
search_terms:
- list shows
- get a setlist by id
- list appearances
- listvenues
- list albums
- get a venue by id
- list links
- api
- neighbortunes
- listsetlists
- listmetadata
- listappearances
- listcolumn
- list uploads
- listsongs
- get a show by id
- list venues
- listlinks
- music
- query setlists by column value
- get a song by id
- list metadata
- list songs
- listjamcharts
- listuploads
- list unique values for a column
- querysetlists
- listalbums
- list jamcharts
- list setlists
- getsetlist
- setlists
- getsong
- getshow
- listlatest
- getvenue
- latest entries
- fan site
- listshows
slug: neighbortunes-capability
source_filename: neighbortunes-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Neighbortunes API\n  description: The unofficial Neighbortunes API provides access to setlists, shows, songs, venues, jamcharts, albums, metadata,\n    links, uploads, and band appearances. No authentication is required.\n  tags:\n  - Neighbortunes\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: neighbortunes\n    baseUri: https://neighbortunes.net/api/v2\n    description: Neighbortunes API HTTP API.\n    resources:\n    - name: setlists-format\n      path: /setlists.{format}\n      operations:\n      - name: listsetlists\n        method: GET\n        description: List setlists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: setlists-id-format\n      path: /setlists/{id}.{format}\n      operations:\n      - name: getsetlist\n        method: GET\n        description: Get a setlist\
  \ by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: setlists-column-value-format\n      path: /setlists/{column}/{value}.{format}\n      operations:\n      - name: querysetlists\n        method: GET\n        description: Query setlists by column value\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: latest-format\n      path: /latest.{format}\n      operations:\n      - name: listlatest\n        method: GET\n        description: Latest entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shows-format\n      path: /shows.{format}\n      operations:\n      - name: listshows\n        method: GET\n        description: List shows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n    - name: shows-id-format\n      path: /shows/{id}.{format}\n      operations:\n      - name: getshow\n        method: GET\n        description: Get a show by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: songs-format\n      path: /songs.{format}\n      operations:\n      - name: listsongs\n        method: GET\n        description: List songs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: songs-id-format\n      path: /songs/{id}.{format}\n      operations:\n      - name: getsong\n        method: GET\n        description: Get a song by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: venues-format\n      path: /venues.{format}\n      operations:\n      - name: listvenues\n\
  \        method: GET\n        description: List venues\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: venues-id-format\n      path: /venues/{id}.{format}\n      operations:\n      - name: getvenue\n        method: GET\n        description: Get a venue by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jamcharts-format\n      path: /jamcharts.{format}\n      operations:\n      - name: listjamcharts\n        method: GET\n        description: List jamcharts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: albums-format\n      path: /albums.{format}\n      operations:\n      - name: listalbums\n        method: GET\n        description: List albums\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: metadata-format\n      path: /metadata.{format}\n      operations:\n      - name: listmetadata\n        method: GET\n        description: List metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: links-format\n      path: /links.{format}\n      operations:\n      - name: listlinks\n        method: GET\n        description: List links\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: uploads-format\n      path: /uploads.{format}\n      operations:\n      - name: listuploads\n        method: GET\n        description: List uploads\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: appearances-format\n      path: /appearances.{format}\n      operations:\n\
  \      - name: listappearances\n        method: GET\n        description: List appearances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-column-format\n      path: /list/{column}.{format}\n      operations:\n      - name: listcolumn\n        method: GET\n        description: List unique values for a column\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: neighbortunes-rest\n    description: REST adapter for Neighbortunes API.\n    resources:\n    - path: /setlists.{format}\n      name: listsetlists\n      operations:\n      - method: GET\n        name: listsetlists\n        description: List setlists\n        call: neighbortunes.listsetlists\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /setlists/{id}.{format}\n\
  \      name: getsetlist\n      operations:\n      - method: GET\n        name: getsetlist\n        description: Get a setlist by ID\n        call: neighbortunes.getsetlist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /setlists/{column}/{value}.{format}\n      name: querysetlists\n      operations:\n      - method: GET\n        name: querysetlists\n        description: Query setlists by column value\n        call: neighbortunes.querysetlists\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /latest.{format}\n      name: listlatest\n      operations:\n      - method: GET\n        name: listlatest\n        description: Latest entries\n        call: neighbortunes.listlatest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shows.{format}\n      name: listshows\n      operations:\n      - method: GET\n        name: listshows\n        description: List shows\n        call: neighbortunes.listshows\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shows/{id}.{format}\n      name: getshow\n      operations:\n      - method: GET\n        name: getshow\n        description: Get a show by ID\n        call: neighbortunes.getshow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /songs.{format}\n      name: listsongs\n      operations:\n      - method: GET\n        name: listsongs\n        description: List songs\n        call: neighbortunes.listsongs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /songs/{id}.{format}\n      name: getsong\n      operations:\n      - method: GET\n        name: getsong\n        description: Get a song by ID\n        call: neighbortunes.getsong\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /venues.{format}\n      name: listvenues\n      operations:\n      - method: GET\n        name: listvenues\n     \
  \   description: List venues\n        call: neighbortunes.listvenues\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /venues/{id}.{format}\n      name: getvenue\n      operations:\n      - method: GET\n        name: getvenue\n        description: Get a venue by ID\n        call: neighbortunes.getvenue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jamcharts.{format}\n      name: listjamcharts\n      operations:\n      - method: GET\n        name: listjamcharts\n        description: List jamcharts\n        call: neighbortunes.listjamcharts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /albums.{format}\n      name: listalbums\n      operations:\n      - method: GET\n        name: listalbums\n        description: List albums\n        call: neighbortunes.listalbums\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata.{format}\n\
  \      name: listmetadata\n      operations:\n      - method: GET\n        name: listmetadata\n        description: List metadata\n        call: neighbortunes.listmetadata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /links.{format}\n      name: listlinks\n      operations:\n      - method: GET\n        name: listlinks\n        description: List links\n        call: neighbortunes.listlinks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /uploads.{format}\n      name: listuploads\n      operations:\n      - method: GET\n        name: listuploads\n        description: List uploads\n        call: neighbortunes.listuploads\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /appearances.{format}\n      name: listappearances\n      operations:\n      - method: GET\n        name: listappearances\n        description: List appearances\n        call: neighbortunes.listappearances\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /list/{column}.{format}\n      name: listcolumn\n      operations:\n      - method: GET\n        name: listcolumn\n        description: List unique values for a column\n        call: neighbortunes.listcolumn\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: neighbortunes-mcp\n    transport: http\n    description: MCP adapter for Neighbortunes API for AI agent use.\n    tools:\n    - name: listsetlists\n      description: List setlists\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.listsetlists\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsetlist\n      description: Get a setlist by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.getsetlist\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: querysetlists\n      description: Query setlists by column value\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.querysetlists\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlatest\n      description: Latest entries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.listlatest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listshows\n      description: List shows\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.listshows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getshow\n      description: Get a show by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.getshow\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsongs\n      description: List songs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.listsongs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsong\n      description: Get a song by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.getsong\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvenues\n      description: List venues\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.listvenues\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvenue\n      description: Get a venue by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.getvenue\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjamcharts\n      description: List jamcharts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.listjamcharts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listalbums\n      description: List albums\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.listalbums\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmetadata\n      description: List metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.listmetadata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlinks\n      description: List links\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ neighbortunes.listlinks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listuploads\n      description: List uploads\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.listuploads\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listappearances\n      description: List appearances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.listappearances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcolumn\n      description: List unique values for a column\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neighbortunes.listcolumn\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/neighbortunes/refs/heads/main/capabilities/neighbortunes-capability.yaml
tags:
- Neighbortunes
- API
tools:
- description: List setlists
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsetlists
- description: Get a setlist by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsetlist
- description: Query setlists by column value
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: querysetlists
- description: Latest entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlatest
- description: List shows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listshows
- description: Get a show by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getshow
- description: List songs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsongs
- description: Get a song by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsong
- description: List venues
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvenues
- description: Get a venue by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvenue
- description: List jamcharts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjamcharts
- description: List albums
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listalbums
- description: List metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmetadata
- description: List links
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlinks
- description: List uploads
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listuploads
- description: List appearances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listappearances
- description: List unique values for a column
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcolumn
---
