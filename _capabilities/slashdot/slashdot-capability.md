---
categories: []
consumed_apis: []
description: Slashdot provides RSS 1.0 and Atom 1.0 feeds for programmatic access to technology news. Slashdot is a technology news aggregation and discussion site founded in 1997, covering open source, Linux, science, and technology. Feeds are available per topic section and are rate-limited to one request per 30 minutes per feed URL.
layout: capability
name: Slashdot RSS/Atom Feeds
operations:
- description: Get Main Feed
  method: GET
  name: getmainfeed
  path: /Slashdot/slashdotMain
- description: Get Main Feed (Atom)
  method: GET
  name: getmainfeedatom
  path: /Slashdot/slashdotMainatom
- description: Get Developers Feed
  method: GET
  name: getdevelopersfeed
  path: /Slashdot/slashdotDevelopers
- description: Get Linux Feed
  method: GET
  name: getlinuxfeed
  path: /Slashdot/slashdotLinux
- description: Get Apple Feed
  method: GET
  name: getapplefeed
  path: /Slashdot/slashdotApple
- description: Get Games Feed
  method: GET
  name: getgamesfeed
  path: /Slashdot/slashdotGames
- description: Get Science Feed
  method: GET
  name: getsciencefeed
  path: /Slashdot/slashdotScience
- description: Get Your Rights Online Feed
  method: GET
  name: getyourrightsonlinefeed
  path: /Slashdot/slashdotYourRightsOnline
personas: []
provider_name: Slashdot
provider_slug: slashdot
search_terms:
- getdevelopersfeed
- getlinuxfeed
- getmainfeedatom
- getsciencefeed
- get your rights online feed
- get science feed
- get linux feed
- getapplefeed
- technology news
- get developers feed
- slashdot
- open source
- get apple feed
- get main feed (atom)
- get games feed
- getgamesfeed
- api
- media
- get main feed
- getyourrightsonlinefeed
- getmainfeed
- rss
slug: slashdot-capability
source_filename: slashdot-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Slashdot RSS/Atom Feeds\n  description: Slashdot provides RSS 1.0 and Atom 1.0 feeds for programmatic access to technology news. Slashdot is a technology\n    news aggregation and discussion site founded in 1997, covering open source, Linux, science, and technology. Feeds are\n    available per topic section and are rate-limited to one request per 30 minutes per feed URL.\n  tags:\n  - Slashdot\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: slashdot\n    baseUri: https://rss.slashdot.org\n    description: Slashdot RSS/Atom Feeds HTTP API.\n    resources:\n    - name: slashdot-slashdotmain\n      path: /Slashdot/slashdotMain\n      operations:\n      - name: getmainfeed\n        method: GET\n        description: Get Main Feed\n        inputParameters:\n        - name: content_type\n          in: query\n          type: string\n          description: Set to 'rss' to get\
  \ RSS format explicitly\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: slashdot-slashdotmainatom\n      path: /Slashdot/slashdotMainatom\n      operations:\n      - name: getmainfeedatom\n        method: GET\n        description: Get Main Feed (Atom)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: slashdot-slashdotdevelopers\n      path: /Slashdot/slashdotDevelopers\n      operations:\n      - name: getdevelopersfeed\n        method: GET\n        description: Get Developers Feed\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: slashdot-slashdotlinux\n      path: /Slashdot/slashdotLinux\n      operations:\n      - name: getlinuxfeed\n        method: GET\n        description: Get Linux Feed\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: slashdot-slashdotapple\n      path: /Slashdot/slashdotApple\n      operations:\n      - name: getapplefeed\n        method: GET\n        description: Get Apple Feed\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: slashdot-slashdotgames\n      path: /Slashdot/slashdotGames\n      operations:\n      - name: getgamesfeed\n        method: GET\n        description: Get Games Feed\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: slashdot-slashdotscience\n      path: /Slashdot/slashdotScience\n      operations:\n      - name: getsciencefeed\n        method: GET\n        description: Get Science Feed\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: slashdot-slashdotyourrightsonline\n      path: /Slashdot/slashdotYourRightsOnline\n      operations:\n      - name: getyourrightsonlinefeed\n        method: GET\n        description: Get Your Rights Online Feed\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: slashdot-rest\n    description: REST adapter for Slashdot RSS/Atom Feeds.\n    resources:\n    - path: /Slashdot/slashdotMain\n      name: getmainfeed\n      operations:\n      - method: GET\n        name: getmainfeed\n        description: Get Main Feed\n        call: slashdot.getmainfeed\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Slashdot/slashdotMainatom\n      name: getmainfeedatom\n      operations:\n      - method: GET\n        name: getmainfeedatom\n        description: Get Main Feed (Atom)\n        call: slashdot.getmainfeedatom\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Slashdot/slashdotDevelopers\n      name: getdevelopersfeed\n      operations:\n      - method: GET\n        name: getdevelopersfeed\n        description: Get Developers Feed\n        call: slashdot.getdevelopersfeed\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Slashdot/slashdotLinux\n      name: getlinuxfeed\n      operations:\n      - method: GET\n        name: getlinuxfeed\n        description: Get Linux Feed\n        call: slashdot.getlinuxfeed\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Slashdot/slashdotApple\n      name: getapplefeed\n      operations:\n      - method: GET\n        name: getapplefeed\n        description: Get Apple Feed\n        call: slashdot.getapplefeed\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Slashdot/slashdotGames\n      name: getgamesfeed\n\
  \      operations:\n      - method: GET\n        name: getgamesfeed\n        description: Get Games Feed\n        call: slashdot.getgamesfeed\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Slashdot/slashdotScience\n      name: getsciencefeed\n      operations:\n      - method: GET\n        name: getsciencefeed\n        description: Get Science Feed\n        call: slashdot.getsciencefeed\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Slashdot/slashdotYourRightsOnline\n      name: getyourrightsonlinefeed\n      operations:\n      - method: GET\n        name: getyourrightsonlinefeed\n        description: Get Your Rights Online Feed\n        call: slashdot.getyourrightsonlinefeed\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: slashdot-mcp\n    transport: http\n    description: MCP adapter for Slashdot RSS/Atom Feeds for AI agent use.\n\
  \    tools:\n    - name: getmainfeed\n      description: Get Main Feed\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: slashdot.getmainfeed\n      with:\n        content_type: tools.content_type\n      inputParameters:\n      - name: content_type\n        type: string\n        description: Set to 'rss' to get RSS format explicitly\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmainfeedatom\n      description: Get Main Feed (Atom)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: slashdot.getmainfeedatom\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdevelopersfeed\n      description: Get Developers Feed\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: slashdot.getdevelopersfeed\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: getlinuxfeed\n      description: Get Linux Feed\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: slashdot.getlinuxfeed\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapplefeed\n      description: Get Apple Feed\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: slashdot.getapplefeed\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgamesfeed\n      description: Get Games Feed\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: slashdot.getgamesfeed\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsciencefeed\n      description: Get Science Feed\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: slashdot.getsciencefeed\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: getyourrightsonlinefeed\n      description: Get Your Rights Online Feed\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: slashdot.getyourrightsonlinefeed\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/slashdot/refs/heads/main/capabilities/slashdot-capability.yaml
tags:
- Slashdot
- API
tools:
- description: Get Main Feed
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmainfeed
- description: Get Main Feed (Atom)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmainfeedatom
- description: Get Developers Feed
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdevelopersfeed
- description: Get Linux Feed
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlinuxfeed
- description: Get Apple Feed
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplefeed
- description: Get Games Feed
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgamesfeed
- description: Get Science Feed
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsciencefeed
- description: Get Your Rights Online Feed
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getyourrightsonlinefeed
---
