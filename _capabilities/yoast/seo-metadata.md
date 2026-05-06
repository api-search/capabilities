---
categories: []
consumed_apis: []
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
- get full seo head metadata for a url including schema.org, og, and twitter card
- get seo head
- get a single wordpress post with full seo metadata
- wordpress
- get post with seo
- wordpress pages with yoast seo data
- single page with seo data
- get a wordpress page with full seo metadata including canonical, robots, and structured data
- schema
- retrieve full seo metadata for any url including meta tags, schema.org, open graph, and twitter card data
- get a wordpress post with full seo metadata including canonical, robots, and structured data
- headless cms
- list wordpress pages with their complete yoast seo metadata
- content audit
- content optimization
- list posts with seo
- list pages with seo
- wordpress posts with yoast seo data
- list all wordpress posts with seo metadata
- single post with seo data
- list wordpress posts with their complete yoast seo metadata
- seo
- metadata
- retrieve seo metadata for any url
- get a single wordpress page with full seo metadata
- list all wordpress pages with seo metadata
- yoast
- get page with seo
slug: seo-metadata
source_filename: seo-metadata.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Yoast SEO Metadata\n  description: Workflow capability for retrieving and managing SEO metadata from WordPress sites using the Yoast REST API.\n    Enables headless CMS, content auditing, and SEO monitoring workflows by providing unified access to SEO metadata, structured\n    data, and social sharing metadata for all WordPress posts and pages.\n  tags:\n  - Yoast\n  - SEO\n  - WordPress\n  - Metadata\n  - Headless CMS\n  - Content Audit\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    YOAST_SITE_URL: YOAST_SITE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: yoast-rest\n    baseUri: '{{YOAST_SITE_URL}}/wp-json'\n    description: Yoast REST API for SEO metadata retrieval from WordPress sites\n    resources:\n    - name: seo-head\n      path: /yoast/v1/get_head\n      description: Retrieve all SEO metadata for a given URL\n      operations:\n      - name: get-seo-head\n        method:\
  \ GET\n        description: Returns all SEO metadata for a URL including meta tags, Schema.org, OG, and Twitter Card data\n        inputParameters:\n        - name: url\n          in: query\n          type: string\n          required: true\n          description: Full URL of the page to retrieve SEO metadata for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: posts\n      path: /wp/v2/posts\n      description: WordPress posts with Yoast SEO metadata\n      operations:\n      - name: list-posts-with-seo\n        method: GET\n        description: Returns posts with Yoast SEO metadata (yoast_head and yoast_head_json)\n        inputParameters:\n        - name: slug\n          in: query\n          type: string\n          required: false\n          description: Filter by post slug\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page\
  \ number for pagination\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Number of posts per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-post-with-seo\n        method: GET\n        description: Returns a single post with Yoast SEO metadata\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: WordPress post ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pages\n      path: /wp/v2/pages\n      description: WordPress pages with Yoast SEO metadata\n      operations:\n      - name: list-pages-with-seo\n        method: GET\n        description: Returns pages with Yoast SEO metadata\n        inputParameters:\n        - name: slug\n   \
  \       in: query\n          type: string\n          required: false\n          description: Filter by page slug\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Number of pages per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-page-with-seo\n        method: GET\n        description: Returns a single page with Yoast SEO metadata\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: WordPress page ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ yoast-seo-api\n    description: Unified REST API for Yoast SEO metadata retrieval across all content types.\n    resources:\n    - path: /v1/seo-head\n      name: seo-head\n      description: Retrieve SEO metadata for any URL\n      operations:\n      - method: GET\n        name: get-seo-head\n        description: Get full SEO head metadata for a URL including Schema.org, OG, and Twitter Card\n        call: yoast-rest.get-seo-head\n        with:\n          url: rest.url\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/posts\n      name: posts\n      description: WordPress posts with Yoast SEO data\n      operations:\n      - method: GET\n        name: list-posts-with-seo\n        description: List all WordPress posts with SEO metadata\n        call: yoast-rest.list-posts-with-seo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/posts/{id}\n      name: post\n      description: Single post with SEO data\n\
  \      operations:\n      - method: GET\n        name: get-post-with-seo\n        description: Get a single WordPress post with full SEO metadata\n        call: yoast-rest.get-post-with-seo\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages\n      name: pages\n      description: WordPress pages with Yoast SEO data\n      operations:\n      - method: GET\n        name: list-pages-with-seo\n        description: List all WordPress pages with SEO metadata\n        call: yoast-rest.list-pages-with-seo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages/{id}\n      name: page\n      description: Single page with SEO data\n      operations:\n      - method: GET\n        name: get-page-with-seo\n        description: Get a single WordPress page with full SEO metadata\n        call: yoast-rest.get-page-with-seo\n        with:\n          id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: yoast-seo-mcp\n    transport: http\n    description: MCP server for AI-assisted SEO metadata retrieval and content auditing.\n    tools:\n    - name: get-seo-head\n      description: Retrieve full SEO metadata for any URL including meta tags, Schema.org, Open Graph, and Twitter Card data\n      hints:\n        readOnly: true\n        openWorld: true\n      call: yoast-rest.get-seo-head\n      with:\n        url: tools.url\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-posts-with-seo\n      description: List WordPress posts with their complete Yoast SEO metadata\n      hints:\n        readOnly: true\n        openWorld: true\n      call: yoast-rest.list-posts-with-seo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-post-with-seo\n      description: Get a WordPress post with full SEO metadata including canonical, robots,\
  \ and structured data\n      hints:\n        readOnly: true\n        openWorld: false\n      call: yoast-rest.get-post-with-seo\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pages-with-seo\n      description: List WordPress pages with their complete Yoast SEO metadata\n      hints:\n        readOnly: true\n        openWorld: true\n      call: yoast-rest.list-pages-with-seo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-page-with-seo\n      description: Get a WordPress page with full SEO metadata including canonical, robots, and structured data\n      hints:\n        readOnly: true\n        openWorld: false\n      call: yoast-rest.get-page-with-seo\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
