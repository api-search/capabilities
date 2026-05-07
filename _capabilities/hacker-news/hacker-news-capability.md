---
categories: []
consumed_apis: []
description: The official Hacker News API provides read-only access to items (stories, comments, jobs, Ask HNs, polls), users, and live data via Firebase. No authentication is required.
layout: capability
name: Hacker News API
operations:
- description: Get item by ID
  method: GET
  name: getitem
  path: /item/{id}.json
- description: Get user profile
  method: GET
  name: getuser
  path: /user/{username}.json
- description: Get max item ID
  method: GET
  name: getmaxitem
  path: /maxitem.json
- description: Get top stories
  method: GET
  name: gettopstories
  path: /topstories.json
- description: Get new stories
  method: GET
  name: getnewstories
  path: /newstories.json
- description: Get best stories
  method: GET
  name: getbeststories
  path: /beststories.json
- description: Get latest Ask HN stories
  method: GET
  name: getaskstories
  path: /askstories.json
- description: Get latest Show HN stories
  method: GET
  name: getshowstories
  path: /showstories.json
- description: Get latest job stories
  method: GET
  name: getjobstories
  path: /jobstories.json
- description: Get changed items and profiles
  method: GET
  name: getupdates
  path: /updates.json
personas: []
provider_name: Hacker News
provider_slug: hacker-news
search_terms:
- get latest ask hn stories
- get best stories
- y combinator
- get changed items and profiles
- api
- gettopstories
- get latest show hn stories
- getnewstories
- get max item id
- getuser
- get user profile
- technology news
- getitem
- getupdates
- get new stories
- get latest job stories
- developer community
- getaskstories
- get top stories
- getmaxitem
- getshowstories
- getjobstories
- get item by id
- getbeststories
- news
- hacker
slug: hacker-news-capability
source_filename: hacker-news-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Hacker News API\n  description: The official Hacker News API provides read-only access to items (stories, comments, jobs, Ask HNs, polls),\n    users, and live data via Firebase. No authentication is required.\n  tags:\n  - Hacker\n  - News\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hacker-news\n    baseUri: https://hacker-news.firebaseio.com/v0\n    description: Hacker News API HTTP API.\n    resources:\n    - name: item-id-json\n      path: /item/{id}.json\n      operations:\n      - name: getitem\n        method: GET\n        description: Get item by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Numeric item ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-username-json\n\
  \      path: /user/{username}.json\n      operations:\n      - name: getuser\n        method: GET\n        description: Get user profile\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: Case-sensitive HN username.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: maxitem-json\n      path: /maxitem.json\n      operations:\n      - name: getmaxitem\n        method: GET\n        description: Get max item ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: topstories-json\n      path: /topstories.json\n      operations:\n      - name: gettopstories\n        method: GET\n        description: Get top stories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n    - name: newstories-json\n      path: /newstories.json\n      operations:\n      - name: getnewstories\n        method: GET\n        description: Get new stories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: beststories-json\n      path: /beststories.json\n      operations:\n      - name: getbeststories\n        method: GET\n        description: Get best stories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: askstories-json\n      path: /askstories.json\n      operations:\n      - name: getaskstories\n        method: GET\n        description: Get latest Ask HN stories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: showstories-json\n      path: /showstories.json\n      operations:\n      - name:\
  \ getshowstories\n        method: GET\n        description: Get latest Show HN stories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobstories-json\n      path: /jobstories.json\n      operations:\n      - name: getjobstories\n        method: GET\n        description: Get latest job stories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: updates-json\n      path: /updates.json\n      operations:\n      - name: getupdates\n        method: GET\n        description: Get changed items and profiles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hacker-news-rest\n    description: REST adapter for Hacker News API.\n    resources:\n    - path: /item/{id}.json\n      name:\
  \ getitem\n      operations:\n      - method: GET\n        name: getitem\n        description: Get item by ID\n        call: hacker-news.getitem\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user/{username}.json\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Get user profile\n        call: hacker-news.getuser\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /maxitem.json\n      name: getmaxitem\n      operations:\n      - method: GET\n        name: getmaxitem\n        description: Get max item ID\n        call: hacker-news.getmaxitem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /topstories.json\n      name: gettopstories\n      operations:\n      - method: GET\n        name: gettopstories\n        description: Get top stories\n\
  \        call: hacker-news.gettopstories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /newstories.json\n      name: getnewstories\n      operations:\n      - method: GET\n        name: getnewstories\n        description: Get new stories\n        call: hacker-news.getnewstories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /beststories.json\n      name: getbeststories\n      operations:\n      - method: GET\n        name: getbeststories\n        description: Get best stories\n        call: hacker-news.getbeststories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /askstories.json\n      name: getaskstories\n      operations:\n      - method: GET\n        name: getaskstories\n        description: Get latest Ask HN stories\n        call: hacker-news.getaskstories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /showstories.json\n\
  \      name: getshowstories\n      operations:\n      - method: GET\n        name: getshowstories\n        description: Get latest Show HN stories\n        call: hacker-news.getshowstories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobstories.json\n      name: getjobstories\n      operations:\n      - method: GET\n        name: getjobstories\n        description: Get latest job stories\n        call: hacker-news.getjobstories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /updates.json\n      name: getupdates\n      operations:\n      - method: GET\n        name: getupdates\n        description: Get changed items and profiles\n        call: hacker-news.getupdates\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hacker-news-mcp\n    transport: http\n    description: MCP adapter for Hacker News API for AI agent use.\n    tools:\n   \
  \ - name: getitem\n      description: Get item by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hacker-news.getitem\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: Numeric item ID.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: Get user profile\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hacker-news.getuser\n      with:\n        username: tools.username\n      inputParameters:\n      - name: username\n        type: string\n        description: Case-sensitive HN username.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmaxitem\n      description: Get max item ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: hacker-news.getmaxitem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettopstories\n      description: Get top stories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hacker-news.gettopstories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnewstories\n      description: Get new stories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hacker-news.getnewstories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbeststories\n      description: Get best stories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hacker-news.getbeststories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaskstories\n      description: Get latest Ask HN stories\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: hacker-news.getaskstories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getshowstories\n      description: Get latest Show HN stories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hacker-news.getshowstories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjobstories\n      description: Get latest job stories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hacker-news.getjobstories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getupdates\n      description: Get changed items and profiles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hacker-news.getupdates\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hacker-news/refs/heads/main/capabilities/hacker-news-capability.yaml
tags:
- Hacker
- News
- API
tools:
- description: Get item by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getitem
- description: Get user profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Get max item ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmaxitem
- description: Get top stories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettopstories
- description: Get new stories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnewstories
- description: Get best stories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbeststories
- description: Get latest Ask HN stories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaskstories
- description: Get latest Show HN stories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getshowstories
- description: Get latest job stories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjobstories
- description: Get changed items and profiles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getupdates
---
