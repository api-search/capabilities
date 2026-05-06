---
categories: []
consumed_apis: []
description: The Marvel Comics API allows developers to access information about Marvel's extensive catalog of characters, comics, creators, events, series, and stories. All requests must be authenticated using a public key, timestamp, and MD5 hash of the timestamp + private key + public key, supplied as query parameters.
layout: capability
name: Marvel Comics API
operations:
- description: List characters
  method: GET
  name: listcharacters
  path: /characters
- description: Get character by ID
  method: GET
  name: getcharacter
  path: /characters/{characterId}
- description: List comics for a character
  method: GET
  name: listcharactercomics
  path: /characters/{characterId}/comics
- description: List comics
  method: GET
  name: listcomics
  path: /comics
- description: Get comic by ID
  method: GET
  name: getcomic
  path: /comics/{comicId}
- description: List creators
  method: GET
  name: listcreators
  path: /creators
- description: Get creator by ID
  method: GET
  name: getcreator
  path: /creators/{creatorId}
- description: List events
  method: GET
  name: listevents
  path: /events
- description: Get event by ID
  method: GET
  name: getevent
  path: /events/{eventId}
- description: List series
  method: GET
  name: listseries
  path: /series
- description: Get series by ID
  method: GET
  name: getseries
  path: /series/{seriesId}
- description: List stories
  method: GET
  name: liststories
  path: /stories
- description: Get story by ID
  method: GET
  name: getstory
  path: /stories/{storyId}
personas: []
provider_name: Marvel
provider_slug: marvel
search_terms:
- list events
- listcharacters
- listevents
- getcomic
- get creator by id
- get comic by id
- list creators
- get story by id
- getcharacter
- listcreators
- listseries
- creators
- stories
- getcreator
- getseries
- list stories
- api
- listcharactercomics
- list comics
- get event by id
- list comics for a character
- liststories
- media
- comics
- getstory
- list series
- entertainment
- list characters
- characters
- series
- get character by id
- get series by id
- getevent
- events
- marvel
- listcomics
slug: marvel-capability
source_filename: marvel-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Marvel Comics API\n  description: The Marvel Comics API allows developers to access information about Marvel's extensive catalog of characters,\n    comics, creators, events, series, and stories. All requests must be authenticated using a public key, timestamp, and MD5\n    hash of the timestamp + private key + public key, supplied as query parameters.\n  tags:\n  - Marvel\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: marvel\n    baseUri: https://gateway.marvel.com/v1/public\n    description: Marvel Comics API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: apikey\n      value: '{{MARVEL_TOKEN}}'\n    resources:\n    - name: characters\n      path: /characters\n      operations:\n      - name: listcharacters\n        method: GET\n        description: List characters\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: characters-characterid\n      path: /characters/{characterId}\n      operations:\n      - name: getcharacter\n        method: GET\n        description: Get character by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: characters-characterid-comics\n      path: /characters/{characterId}/comics\n      operations:\n      - name: listcharactercomics\n        method: GET\n        description: List comics for a character\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comics\n      path: /comics\n      operations:\n      - name: listcomics\n        method: GET\n        description: List comics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comics-comicid\n\
  \      path: /comics/{comicId}\n      operations:\n      - name: getcomic\n        method: GET\n        description: Get comic by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: creators\n      path: /creators\n      operations:\n      - name: listcreators\n        method: GET\n        description: List creators\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: creators-creatorid\n      path: /creators/{creatorId}\n      operations:\n      - name: getcreator\n        method: GET\n        description: Get creator by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events\n      operations:\n      - name: listevents\n        method: GET\n        description: List events\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-eventid\n      path: /events/{eventId}\n      operations:\n      - name: getevent\n        method: GET\n        description: Get event by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: series\n      path: /series\n      operations:\n      - name: listseries\n        method: GET\n        description: List series\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: series-seriesid\n      path: /series/{seriesId}\n      operations:\n      - name: getseries\n        method: GET\n        description: Get series by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stories\n      path: /stories\n    \
  \  operations:\n      - name: liststories\n        method: GET\n        description: List stories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stories-storyid\n      path: /stories/{storyId}\n      operations:\n      - name: getstory\n        method: GET\n        description: Get story by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: marvel-rest\n    description: REST adapter for Marvel Comics API.\n    resources:\n    - path: /characters\n      name: listcharacters\n      operations:\n      - method: GET\n        name: listcharacters\n        description: List characters\n        call: marvel.listcharacters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /characters/{characterId}\n      name: getcharacter\n    \
  \  operations:\n      - method: GET\n        name: getcharacter\n        description: Get character by ID\n        call: marvel.getcharacter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /characters/{characterId}/comics\n      name: listcharactercomics\n      operations:\n      - method: GET\n        name: listcharactercomics\n        description: List comics for a character\n        call: marvel.listcharactercomics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /comics\n      name: listcomics\n      operations:\n      - method: GET\n        name: listcomics\n        description: List comics\n        call: marvel.listcomics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /comics/{comicId}\n      name: getcomic\n      operations:\n      - method: GET\n        name: getcomic\n        description: Get comic by ID\n        call: marvel.getcomic\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /creators\n      name: listcreators\n      operations:\n      - method: GET\n        name: listcreators\n        description: List creators\n        call: marvel.listcreators\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /creators/{creatorId}\n      name: getcreator\n      operations:\n      - method: GET\n        name: getcreator\n        description: Get creator by ID\n        call: marvel.getcreator\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events\n      name: listevents\n      operations:\n      - method: GET\n        name: listevents\n        description: List events\n        call: marvel.listevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events/{eventId}\n      name: getevent\n      operations:\n      - method: GET\n        name: getevent\n        description: Get event by ID\n        call:\
  \ marvel.getevent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /series\n      name: listseries\n      operations:\n      - method: GET\n        name: listseries\n        description: List series\n        call: marvel.listseries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /series/{seriesId}\n      name: getseries\n      operations:\n      - method: GET\n        name: getseries\n        description: Get series by ID\n        call: marvel.getseries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stories\n      name: liststories\n      operations:\n      - method: GET\n        name: liststories\n        description: List stories\n        call: marvel.liststories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stories/{storyId}\n      name: getstory\n      operations:\n      - method: GET\n        name: getstory\n        description:\
  \ Get story by ID\n        call: marvel.getstory\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: marvel-mcp\n    transport: http\n    description: MCP adapter for Marvel Comics API for AI agent use.\n    tools:\n    - name: listcharacters\n      description: List characters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marvel.listcharacters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcharacter\n      description: Get character by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marvel.getcharacter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcharactercomics\n      description: List comics for a character\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marvel.listcharactercomics\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcomics\n      description: List comics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marvel.listcomics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcomic\n      description: Get comic by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marvel.getcomic\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcreators\n      description: List creators\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marvel.listcreators\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcreator\n      description: Get creator by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marvel.getcreator\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listevents\n      description: List events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marvel.listevents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getevent\n      description: Get event by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marvel.getevent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listseries\n      description: List series\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marvel.listseries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getseries\n      description: Get series by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marvel.getseries\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: liststories\n      description: List stories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marvel.liststories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstory\n      description: Get story by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marvel.getstory\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MARVEL_TOKEN: MARVEL_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/marvel/refs/heads/main/capabilities/marvel-capability.yaml
tags:
- Marvel
- API
tools:
- description: List characters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcharacters
- description: Get character by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcharacter
- description: List comics for a character
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcharactercomics
- description: List comics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcomics
- description: Get comic by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcomic
- description: List creators
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcreators
- description: Get creator by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcreator
- description: List events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listevents
- description: Get event by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getevent
- description: List series
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listseries
- description: Get series by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getseries
- description: List stories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststories
- description: Get story by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstory
---
