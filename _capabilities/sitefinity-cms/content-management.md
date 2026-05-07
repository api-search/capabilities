---
categories: []
consumed_apis: []
description: Unified capability for managing Sitefinity CMS content including news items, blog posts, events, and media. Enables content operations teams and developers to automate content lifecycle management, publish workflows, and headless content delivery integrations.
layout: capability
name: Sitefinity CMS Content Management
operations:
- description: List news items from Sitefinity CMS
  method: GET
  name: list-news-items
  path: /v1/news-items
- description: Create a new news item in Sitefinity CMS
  method: POST
  name: create-news-item
  path: /v1/news-items
- description: List blog posts from Sitefinity CMS
  method: GET
  name: list-blog-posts
  path: /v1/blog-posts
- description: Create a new blog post in Sitefinity CMS
  method: POST
  name: create-blog-post
  path: /v1/blog-posts
- description: List events from Sitefinity CMS
  method: GET
  name: list-events
  path: /v1/events
- description: Create a new event in Sitefinity CMS
  method: POST
  name: create-event
  path: /v1/events
personas: []
provider_name: Sitefinity CMS
provider_slug: sitefinity-cms
search_terms:
- list blog posts from sitefinity cms
- list events
- list news items from sitefinity cms with optional odata filtering
- publishing
- manage sitefinity blog posts
- manage sitefinity event content
- rest
- create news item
- create a new event in sitefinity cms
- list events from sitefinity cms
- sitefinity
- list news items from sitefinity cms
- create event
- list news items
- create blog post
- create a new blog post in sitefinity cms
- list blog posts from sitefinity cms with optional odata filtering
- .net
- content management
- list blog posts
- create a new news content item in sitefinity cms
- manage sitefinity news content
- headless cms
- list events from sitefinity cms with optional odata filtering
- create a new news item in sitefinity cms
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sitefinity CMS Content Management\n  description: Unified capability for managing Sitefinity CMS content including news items, blog posts, events, and media.\n    Enables content operations teams and developers to automate content lifecycle management, publish workflows, and headless\n    content delivery integrations.\n  tags:\n  - Sitefinity\n  - Content Management\n  - Headless CMS\n  - Publishing\n  - .NET\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SITEFINITY_AUTH_COOKIE: SITEFINITY_AUTH_COOKIE\n    SITEFINITY_BASE_URL: SITEFINITY_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: sitefinity-content\n    baseUri: '{{SITEFINITY_BASE_URL}}/api/default'\n    description: Sitefinity CMS Content API for managing content items\n    authentication:\n      type: apikey\n      key: .ASPXAUTH\n      value: '{{SITEFINITY_AUTH_COOKIE}}'\n      placement: cookie\n    resources:\n \
  \   - name: news-items\n      path: /newsitems\n      description: Manage news content items\n      operations:\n      - name: list-news-items\n        method: GET\n        description: List news items with OData filtering\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Max items to return\n        - name: $skip\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        - name: $orderby\n          in: query\n          type: string\n          required: false\n          description: OData orderby clause\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-news-item\n        method: POST\n   \
  \     description: Create a new news item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Title: '{{tools.title}}'\n            Content: '{{tools.content}}'\n            Summary: '{{tools.summary}}'\n    - name: blog-posts\n      path: /blogposts\n      description: Manage blog post content items\n      operations:\n      - name: list-blog-posts\n        method: GET\n        description: List blog posts with OData filtering\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Max items to return\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n      - name: create-blog-post\n        method: POST\n        description: Create a new blog post\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Title: '{{tools.title}}'\n            Content: '{{tools.content}}'\n    - name: events\n      path: /events\n      description: Manage event content items\n      operations:\n      - name: list-events\n        method: GET\n        description: List events with OData filtering\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Max items to return\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: create-event\n        method: POST\n        description: Create a new event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Title: '{{tools.title}}'\n            Content: '{{tools.content}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sitefinity-content-management-api\n    description: Unified REST API for Sitefinity CMS content management.\n    resources:\n    - path: /v1/news-items\n      name: news-items\n      description: Manage Sitefinity news content\n      operations:\n      - method: GET\n        name: list-news-items\n        description: List news items from Sitefinity CMS\n        call: sitefinity-content.list-news-items\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-news-item\n        description: Create a new\
  \ news item in Sitefinity CMS\n        call: sitefinity-content.create-news-item\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/blog-posts\n      name: blog-posts\n      description: Manage Sitefinity blog posts\n      operations:\n      - method: GET\n        name: list-blog-posts\n        description: List blog posts from Sitefinity CMS\n        call: sitefinity-content.list-blog-posts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-blog-post\n        description: Create a new blog post in Sitefinity CMS\n        call: sitefinity-content.create-blog-post\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Manage Sitefinity event content\n      operations:\n      - method: GET\n        name: list-events\n        description: List events from Sitefinity CMS\n        call: sitefinity-content.list-events\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-event\n        description: Create a new event in Sitefinity CMS\n        call: sitefinity-content.create-event\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sitefinity-content-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Sitefinity CMS content management.\n    tools:\n    - name: list-news-items\n      description: List news items from Sitefinity CMS with optional OData filtering\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sitefinity-content.list-news-items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-news-item\n      description: Create a new news content item in Sitefinity CMS\n      call: sitefinity-content.create-news-item\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: list-blog-posts\n      description: List blog posts from Sitefinity CMS with optional OData filtering\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sitefinity-content.list-blog-posts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-blog-post\n      description: Create a new blog post in Sitefinity CMS\n      call: sitefinity-content.create-blog-post\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-events\n      description: List events from Sitefinity CMS with optional OData filtering\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sitefinity-content.list-events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-event\n      description: Create a new event in Sitefinity CMS\n      call: sitefinity-content.create-event\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sitefinity-cms/refs/heads/main/capabilities/content-management.yaml
tags:
- Sitefinity
- Content Management
- Headless CMS
- Publishing
- .NET
tools:
- description: List news items from Sitefinity CMS with optional OData filtering
  hints:
    idempotent: true
    readOnly: true
  name: list-news-items
- description: Create a new news content item in Sitefinity CMS
  hints: {}
  name: create-news-item
- description: List blog posts from Sitefinity CMS with optional OData filtering
  hints:
    idempotent: true
    readOnly: true
  name: list-blog-posts
- description: Create a new blog post in Sitefinity CMS
  hints: {}
  name: create-blog-post
- description: List events from Sitefinity CMS with optional OData filtering
  hints:
    idempotent: true
    readOnly: true
  name: list-events
- description: Create a new event in Sitefinity CMS
  hints: {}
  name: create-event
---
