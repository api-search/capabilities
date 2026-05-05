---
api_specs:
- filename: yoast-rest-openapi.yml
  format: yaml
  label: yoast-rest
  slug: yoast-rest
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/yoast/refs/heads/main/openapi/yoast-rest-openapi.yml
categories: []
consumed_apis:
- yoast-rest
description: Workflow capability for retrieving and managing SEO metadata from WordPress sites using the Yoast REST API. Enables headless CMS, content auditing, and SEO monitoring workflows by providing unified access to SEO metadata, structured data, and social sharing metadata for all WordPress posts and pages.
layout: capability
name: Yoast SEO Metadata
operations:
- description: Get full SEO head metadata for a URL including Schema.org, OG, and Twitter Card
  method: GET
  name: get-seo-head
  path: /v1/seo-head
- description: List all WordPress posts with SEO metadata
  method: GET
  name: list-posts-with-seo
  path: /v1/posts
- description: Get a single WordPress post with full SEO metadata
  method: GET
  name: get-post-with-seo
  path: /v1/posts/{id}
- description: List all WordPress pages with SEO metadata
  method: GET
  name: list-pages-with-seo
  path: /v1/pages
- description: Get a single WordPress page with full SEO metadata
  method: GET
  name: get-page-with-seo
  path: /v1/pages/{id}
personas: []
provider_name: Yoast
provider_slug: yoast
search_terms:
- yoast
- single page with seo data
- schema
- wordpress
- get page with seo
- wordpress posts with yoast seo data
- get a single wordpress page with full seo metadata
- metadata
- retrieve seo metadata for any url
- list all wordpress posts with seo metadata
- list pages with seo
- list wordpress pages with their complete yoast seo metadata
- get a single wordpress post with full seo metadata
- list posts with seo
- get full seo head metadata for a url including schema.org, og, and twitter card
- get a wordpress page with full seo metadata including canonical, robots, and structured data
- retrieve full seo metadata for any url including meta tags, schema.org, open graph, and twitter card data
- list all wordpress pages with seo metadata
- seo
- content audit
- get a wordpress post with full seo metadata including canonical, robots, and structured data
- get seo head
- wordpress pages with yoast seo data
- list wordpress posts with their complete yoast seo metadata
- headless cms
- content optimization
- single post with seo data
- get post with seo
slug: seo-metadata
source_filename: seo-metadata.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Yoast SEO Metadata\"\n  description: >-\n    Workflow capability for retrieving and managing SEO metadata from WordPress sites\n    using the Yoast REST API. Enables headless CMS, content auditing, and SEO monitoring\n    workflows by providing unified access to SEO metadata, structured data, and social\n    sharing metadata for all WordPress posts and pages.\n  tags:\n    - Yoast\n    - SEO\n    - WordPress\n    - Metadata\n    - Headless CMS\n    - Content Audit\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      YOAST_SITE_URL: YOAST_SITE_URL\n\ncapability:\n  consumes:\n    - import: yoast-rest\n      location: ./shared/yoast-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: yoast-seo-api\n      description: \"Unified REST API for Yoast SEO metadata retrieval across all content types.\"\n      resources:\n        - path: /v1/seo-head\n          name:\
  \ seo-head\n          description: \"Retrieve SEO metadata for any URL\"\n          operations:\n            - method: GET\n              name: get-seo-head\n              description: \"Get full SEO head metadata for a URL including Schema.org, OG, and Twitter Card\"\n              call: \"yoast-rest.get-seo-head\"\n              with:\n                url: \"rest.url\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/posts\n          name: posts\n          description: \"WordPress posts with Yoast SEO data\"\n          operations:\n            - method: GET\n              name: list-posts-with-seo\n              description: \"List all WordPress posts with SEO metadata\"\n              call: \"yoast-rest.list-posts-with-seo\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/posts/{id}\n          name: post\n          description: \"Single\
  \ post with SEO data\"\n          operations:\n            - method: GET\n              name: get-post-with-seo\n              description: \"Get a single WordPress post with full SEO metadata\"\n              call: \"yoast-rest.get-post-with-seo\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pages\n          name: pages\n          description: \"WordPress pages with Yoast SEO data\"\n          operations:\n            - method: GET\n              name: list-pages-with-seo\n              description: \"List all WordPress pages with SEO metadata\"\n              call: \"yoast-rest.list-pages-with-seo\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pages/{id}\n          name: page\n          description: \"Single page with SEO data\"\n          operations:\n            - method: GET\n\
  \              name: get-page-with-seo\n              description: \"Get a single WordPress page with full SEO metadata\"\n              call: \"yoast-rest.get-page-with-seo\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: yoast-seo-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SEO metadata retrieval and content auditing.\"\n      tools:\n        - name: get-seo-head\n          description: \"Retrieve full SEO metadata for any URL including meta tags, Schema.org, Open Graph, and Twitter Card data\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"yoast-rest.get-seo-head\"\n          with:\n            url: \"tools.url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-posts-with-seo\n      \
  \    description: \"List WordPress posts with their complete Yoast SEO metadata\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"yoast-rest.list-posts-with-seo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-post-with-seo\n          description: \"Get a WordPress post with full SEO metadata including canonical, robots, and structured data\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"yoast-rest.get-post-with-seo\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-pages-with-seo\n          description: \"List WordPress pages with their complete Yoast SEO metadata\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"yoast-rest.list-pages-with-seo\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-page-with-seo\n          description: \"Get a WordPress page with full SEO metadata including canonical, robots, and structured data\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"yoast-rest.get-page-with-seo\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/yoast/refs/heads/main/capabilities/seo-metadata.yaml
tags:
- Yoast
- SEO
- WordPress
- Metadata
- Headless CMS
- Content Audit
tools:
- description: Retrieve full SEO metadata for any URL including meta tags, Schema.org, Open Graph, and Twitter Card data
  hints:
    openWorld: true
    readOnly: true
  name: get-seo-head
- description: List WordPress posts with their complete Yoast SEO metadata
  hints:
    openWorld: true
    readOnly: true
  name: list-posts-with-seo
- description: Get a WordPress post with full SEO metadata including canonical, robots, and structured data
  hints:
    openWorld: false
    readOnly: true
  name: get-post-with-seo
- description: List WordPress pages with their complete Yoast SEO metadata
  hints:
    openWorld: true
    readOnly: true
  name: list-pages-with-seo
- description: Get a WordPress page with full SEO metadata including canonical, robots, and structured data
  hints:
    openWorld: false
    readOnly: true
  name: get-page-with-seo
---
