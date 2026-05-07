---
categories: []
consumed_apis: []
description: The Google Photos Library API allows you to manage photos, videos, and albums in Google Photos. You can create and manage albums, upload and retrieve media items, and share albums with other users.
layout: capability
name: Google Photos Library API
operations:
- description: List media items
  method: GET
  name: listmediaitems
  path: /mediaItems
- description: Create media items
  method: POST
  name: batchcreatemediaitems
  path: /mediaItems
- description: Get a media item
  method: GET
  name: getmediaitem
  path: /mediaItems/{mediaItemId}
- description: Search media items
  method: POST
  name: searchmediaitems
  path: /mediaItems:search
- description: List albums
  method: GET
  name: listalbums
  path: /albums
- description: Create an album
  method: POST
  name: createalbum
  path: /albums
- description: Get an album
  method: GET
  name: getalbum
  path: /albums/{albumId}
- description: List shared albums
  method: GET
  name: listsharedalbums
  path: /sharedAlbums
personas: []
provider_name: Google Photos Library
provider_slug: google-photos
search_terms:
- batchcreatemediaitems
- list albums
- albums
- sharing
- listsharedalbums
- photos
- api
- list media items
- create media items
- search media items
- google
- createalbum
- searchmediaitems
- getalbum
- getmediaitem
- list shared albums
- create an album
- storage
- media
- listmediaitems
- images
- get a media item
- listalbums
- get an album
slug: google-photos-capability
source_filename: google-photos-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Photos Library API\n  description: The Google Photos Library API allows you to manage photos, videos, and albums in Google Photos. You can create\n    and manage albums, upload and retrieve media items, and share albums with other users.\n  tags:\n  - Google\n  - Photos\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-photos\n    baseUri: https://photoslibrary.googleapis.com/v1\n    description: Google Photos Library API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_PHOTOS_TOKEN}}'\n    resources:\n    - name: mediaitems\n      path: /mediaItems\n      operations:\n      - name: listmediaitems\n        method: GET\n        description: List media items\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: batchcreatemediaitems\n        method: POST\n        description: Create media items\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mediaitems-mediaitemid\n      path: /mediaItems/{mediaItemId}\n      operations:\n      - name: getmediaitem\n        method: GET\n        description: Get a media item\n        inputParameters:\n        - name: mediaItemId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mediaitems-search\n      path: /mediaItems:search\n      operations:\n      - name: searchmediaitems\n        method: POST\n        description: Search media items\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: albums\n      path: /albums\n      operations:\n      - name: listalbums\n        method: GET\n        description: List albums\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createalbum\n        method: POST\n        description: Create an album\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: albums-albumid\n      path: /albums/{albumId}\n      operations:\n      - name: getalbum\n        method: GET\n        description: Get an album\n        inputParameters:\n        - name: albumId\n          in: path\n          type: string\n   \
  \       required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sharedalbums\n      path: /sharedAlbums\n      operations:\n      - name: listsharedalbums\n        method: GET\n        description: List shared albums\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-photos-rest\n    description: REST adapter for Google Photos Library API.\n    resources:\n    - path: /mediaItems\n      name: listmediaitems\n      operations:\n      - method: GET\n        name: listmediaitems\n        description: List media items\n        call: google-photos.listmediaitems\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /mediaItems\n      name: batchcreatemediaitems\n      operations:\n      - method: POST\n        name: batchcreatemediaitems\n        description: Create media items\n        call: google-photos.batchcreatemediaitems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mediaItems/{mediaItemId}\n      name: getmediaitem\n      operations:\n      - method: GET\n        name: getmediaitem\n        description: Get a media item\n        call: google-photos.getmediaitem\n        with:\n          mediaItemId: rest.mediaItemId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mediaItems:search\n      name: searchmediaitems\n      operations:\n      - method: POST\n        name: searchmediaitems\n        description: Search media items\n        call: google-photos.searchmediaitems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /albums\n      name: listalbums\n      operations:\n      - method: GET\n        name: listalbums\n        description: List albums\n        call: google-photos.listalbums\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /albums\n      name: createalbum\n      operations:\n      - method: POST\n        name: createalbum\n        description: Create an album\n        call: google-photos.createalbum\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /albums/{albumId}\n      name: getalbum\n      operations:\n      - method: GET\n        name: getalbum\n        description: Get an album\n        call: google-photos.getalbum\n        with:\n          albumId: rest.albumId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sharedAlbums\n      name: listsharedalbums\n      operations:\n      - method: GET\n        name: listsharedalbums\n        description: List shared albums\n \
  \       call: google-photos.listsharedalbums\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-photos-mcp\n    transport: http\n    description: MCP adapter for Google Photos Library API for AI agent use.\n    tools:\n    - name: listmediaitems\n      description: List media items\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-photos.listmediaitems\n      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batchcreatemediaitems\n      description: Create media items\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n    \
  \  call: google-photos.batchcreatemediaitems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmediaitem\n      description: Get a media item\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-photos.getmediaitem\n      with:\n        mediaItemId: tools.mediaItemId\n      inputParameters:\n      - name: mediaItemId\n        type: string\n        description: mediaItemId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchmediaitems\n      description: Search media items\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-photos.searchmediaitems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listalbums\n      description: List albums\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-photos.listalbums\n\
  \      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createalbum\n      description: Create an album\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-photos.createalbum\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getalbum\n      description: Get an album\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-photos.getalbum\n      with:\n        albumId: tools.albumId\n      inputParameters:\n      - name: albumId\n        type: string\n        description: albumId\n        required: true\n      outputParameters:\n      - type: object\n      \
  \  mapping: $.\n    - name: listsharedalbums\n      description: List shared albums\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-photos.listsharedalbums\n      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_PHOTOS_TOKEN: GOOGLE_PHOTOS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-photos/refs/heads/main/capabilities/google-photos-capability.yaml
tags:
- Google
- Photos
- API
tools:
- description: List media items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmediaitems
- description: Create media items
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: batchcreatemediaitems
- description: Get a media item
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmediaitem
- description: Search media items
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchmediaitems
- description: List albums
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listalbums
- description: Create an album
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createalbum
- description: Get an album
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getalbum
- description: List shared albums
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsharedalbums
---
