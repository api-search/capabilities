---
categories: []
consumed_apis: []
description: Workflow capability for accessing US Department of Commerce news, blog posts, and media content. Useful for journalists, researchers, policy analysts, and citizens who need to monitor Commerce Department announcements, economic reports, and agency updates.
layout: capability
name: US Department of Commerce Content
operations:
- description: List recent Commerce Department news articles
  method: GET
  name: list-news
  path: /v1/news
- description: Get a specific Commerce Department news article
  method: GET
  name: get-news-article
  path: /v1/news/{id}
- description: List Commerce Department blog posts
  method: GET
  name: list-blogs
  path: /v1/blogs
- description: Get a specific Commerce Department blog post
  method: GET
  name: get-blog-post
  path: /v1/blogs/{id}
- description: List Commerce Department images
  method: GET
  name: list-images
  path: /v1/images
personas: []
provider_name: US Department of Commerce
provider_slug: us-department-of-commerce
search_terms:
- list commerce department images
- list commerce news
- list images
- list recent commerce department news articles
- get commerce blog post
- list blog posts from commerce department officials and bureaus. blog posts provide policy commentary, program updates, and feature stories.
- standards
- get the full text of a specific commerce department news article by id. returns title, body, date, tags, and featured image.
- get news article
- list recent news articles from the us department of commerce. use to monitor agency announcements, trade policy updates, economic reports, and bureau news from noaa, census, bea, ita, and nist.
- get a specific commerce department blog post
- list blogs
- get commerce news article
- blog posts from commerce department officials and bureaus
- get a specific commerce department news article
- content
- list commerce blog posts
- trade
- get blog post
- economic data
- list images and media assets published by the commerce department. useful for finding official images for news stories and publications.
- climate
- list news
- get the full content of a specific commerce department blog post. returns author, body text, date, and topic tags.
- list commerce images
- federal government
- single commerce department news article
- list commerce department blog posts
- open data
- commerce
- single commerce department blog post
- news
- media images from commerce department
- latest news from the us department of commerce
slug: commerce-content
source_filename: commerce-content.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: US Department of Commerce Content\n  description: Workflow capability for accessing US Department of Commerce news, blog posts, and media content. Useful for\n    journalists, researchers, policy analysts, and citizens who need to monitor Commerce Department announcements, economic\n    reports, and agency updates.\n  tags:\n  - Commerce\n  - Federal Government\n  - News\n  - Content\n  - Open Data\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys: {}\ncapability:\n  consumes:\n  - type: http\n    namespace: commerce-gov\n    baseUri: https://www.commerce.gov\n    description: Content API for Commerce.gov news, blogs, and images\n    resources:\n    - name: news\n      path: /api/news\n      description: News articles published on Commerce.gov\n      operations:\n      - name: list-news\n        method: GET\n        description: List news articles\n        inputParameters:\n        - name: page\n    \
  \      in: query\n          type: integer\n          required: false\n          description: Page number for pagination\n        - name: items_per_page\n          in: query\n          type: integer\n          required: false\n          description: Number of items per page\n        - name: sort_order\n          in: query\n          type: string\n          required: false\n          description: Sort direction (ASC or DESC)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-news-article\n        method: GET\n        description: Get a specific news article by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: News article identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blogs\n      path: /api/blog\n  \
  \    description: Blog posts published on Commerce.gov\n      operations:\n      - name: list-blogs\n        method: GET\n        description: List blog posts\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination\n        - name: items_per_page\n          in: query\n          type: integer\n          required: false\n          description: Number of items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-blog-post\n        method: GET\n        description: Get a specific blog post by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Blog post identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: images\n      path: /api/image\n      description: Images published on Commerce.gov\n      operations:\n      - name: list-images\n        method: GET\n        description: List images\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: commerce-content-api\n    description: Unified REST API for accessing US Department of Commerce content.\n    resources:\n    - path: /v1/news\n      name: news\n      description: Latest news from the US Department of Commerce\n      operations:\n      - method: GET\n        name: list-news\n        description: List recent Commerce Department news articles\n        call: commerce-gov.list-news\n        with:\n          page: rest.page\n\
  \          items_per_page: rest.items_per_page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/news/{id}\n      name: news-item\n      description: Single Commerce Department news article\n      operations:\n      - method: GET\n        name: get-news-article\n        description: Get a specific Commerce Department news article\n        call: commerce-gov.get-news-article\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/blogs\n      name: blogs\n      description: Blog posts from Commerce Department officials and bureaus\n      operations:\n      - method: GET\n        name: list-blogs\n        description: List Commerce Department blog posts\n        call: commerce-gov.list-blogs\n        with:\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/blogs/{id}\n      name: blog-item\n      description:\
  \ Single Commerce Department blog post\n      operations:\n      - method: GET\n        name: get-blog-post\n        description: Get a specific Commerce Department blog post\n        call: commerce-gov.get-blog-post\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/images\n      name: images\n      description: Media images from Commerce Department\n      operations:\n      - method: GET\n        name: list-images\n        description: List Commerce Department images\n        call: commerce-gov.list-images\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: commerce-content-mcp\n    transport: http\n    description: MCP server for AI-assisted monitoring of US Department of Commerce announcements and content.\n    tools:\n    - name: list-commerce-news\n      description: List recent news articles from the US Department of Commerce. Use to\
  \ monitor agency announcements, trade\n        policy updates, economic reports, and bureau news from NOAA, Census, BEA, ITA, and NIST.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: commerce-gov.list-news\n      with:\n        page: tools.page\n        items_per_page: tools.items_per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-commerce-news-article\n      description: Get the full text of a specific Commerce Department news article by ID. Returns title, body, date, tags,\n        and featured image.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: commerce-gov.get-news-article\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-commerce-blog-posts\n      description: List blog posts from Commerce Department officials and bureaus. Blog posts provide policy commentary, program\n        updates, and feature stories.\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: commerce-gov.list-blogs\n      with:\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-commerce-blog-post\n      description: Get the full content of a specific Commerce Department blog post. Returns author, body text, date, and\n        topic tags.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: commerce-gov.get-blog-post\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-commerce-images\n      description: List images and media assets published by the Commerce Department. Useful for finding official images for\n        news stories and publications.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: commerce-gov.list-images\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/us-department-of-commerce/refs/heads/main/capabilities/commerce-content.yaml
tags:
- Commerce
- Federal Government
- News
- Content
- Open Data
tools:
- description: List recent news articles from the US Department of Commerce. Use to monitor agency announcements, trade policy updates, economic reports, and bureau news from NOAA, Census, BEA, ITA, and NIST.
  hints:
    openWorld: true
    readOnly: true
  name: list-commerce-news
- description: Get the full text of a specific Commerce Department news article by ID. Returns title, body, date, tags, and featured image.
  hints:
    openWorld: false
    readOnly: true
  name: get-commerce-news-article
- description: List blog posts from Commerce Department officials and bureaus. Blog posts provide policy commentary, program updates, and feature stories.
  hints:
    openWorld: true
    readOnly: true
  name: list-commerce-blog-posts
- description: Get the full content of a specific Commerce Department blog post. Returns author, body text, date, and topic tags.
  hints:
    openWorld: false
    readOnly: true
  name: get-commerce-blog-post
- description: List images and media assets published by the Commerce Department. Useful for finding official images for news stories and publications.
  hints:
    openWorld: true
    readOnly: true
  name: list-commerce-images
---
