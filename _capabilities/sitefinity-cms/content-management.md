---
categories: []
consumed_apis:
- sitefinity-content
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
- create a new event in sitefinity cms
- rest
- .net
- create event
- manage sitefinity news content
- list events
- publishing
- list blog posts
- create blog post
- create news item
- list blog posts from sitefinity cms with optional odata filtering
- manage sitefinity blog posts
- list news items
- create a new news item in sitefinity cms
- create a new blog post in sitefinity cms
- list events from sitefinity cms with optional odata filtering
- create a new news content item in sitefinity cms
- headless cms
- sitefinity
- manage sitefinity event content
- content management
- list news items from sitefinity cms
- list blog posts from sitefinity cms
- list news items from sitefinity cms with optional odata filtering
- list events from sitefinity cms
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sitefinity CMS Content Management\"\n  description: >-\n    Unified capability for managing Sitefinity CMS content including news items,\n    blog posts, events, and media. Enables content operations teams and developers\n    to automate content lifecycle management, publish workflows, and headless\n    content delivery integrations.\n  tags:\n    - Sitefinity\n    - Content Management\n    - Headless CMS\n    - Publishing\n    - .NET\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SITEFINITY_AUTH_COOKIE: SITEFINITY_AUTH_COOKIE\n      SITEFINITY_BASE_URL: SITEFINITY_BASE_URL\n\ncapability:\n  consumes:\n    - import: sitefinity-content\n      location: ./shared/content-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sitefinity-content-management-api\n      description: \"Unified REST API for Sitefinity CMS content management.\"\n      resources:\n\
  \        - path: /v1/news-items\n          name: news-items\n          description: \"Manage Sitefinity news content\"\n          operations:\n            - method: GET\n              name: list-news-items\n              description: \"List news items from Sitefinity CMS\"\n              call: \"sitefinity-content.list-news-items\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-news-item\n              description: \"Create a new news item in Sitefinity CMS\"\n              call: \"sitefinity-content.create-news-item\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/blog-posts\n          name: blog-posts\n          description: \"Manage Sitefinity blog posts\"\n          operations:\n            - method: GET\n              name: list-blog-posts\n              description: \"List blog posts from Sitefinity\
  \ CMS\"\n              call: \"sitefinity-content.list-blog-posts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-blog-post\n              description: \"Create a new blog post in Sitefinity CMS\"\n              call: \"sitefinity-content.create-blog-post\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events\n          name: events\n          description: \"Manage Sitefinity event content\"\n          operations:\n            - method: GET\n              name: list-events\n              description: \"List events from Sitefinity CMS\"\n              call: \"sitefinity-content.list-events\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-event\n              description: \"Create a new event in Sitefinity\
  \ CMS\"\n              call: \"sitefinity-content.create-event\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sitefinity-content-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Sitefinity CMS content management.\"\n      tools:\n        - name: list-news-items\n          description: \"List news items from Sitefinity CMS with optional OData filtering\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sitefinity-content.list-news-items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-news-item\n          description: \"Create a new news content item in Sitefinity CMS\"\n          call: \"sitefinity-content.create-news-item\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name:\
  \ list-blog-posts\n          description: \"List blog posts from Sitefinity CMS with optional OData filtering\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sitefinity-content.list-blog-posts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-blog-post\n          description: \"Create a new blog post in Sitefinity CMS\"\n          call: \"sitefinity-content.create-blog-post\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-events\n          description: \"List events from Sitefinity CMS with optional OData filtering\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sitefinity-content.list-events\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-event\n          description: \"Create a new event in Sitefinity\
  \ CMS\"\n          call: \"sitefinity-content.create-event\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
