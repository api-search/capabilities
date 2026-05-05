---
api_specs:
- filename: commerce-gov-api-openapi.yml
  format: yaml
  label: commerce-gov
  slug: commerce-gov
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/us-department-of-commerce/refs/heads/main/openapi/commerce-gov-api-openapi.yml
categories: []
consumed_apis:
- commerce-gov
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
- open data
- media images from commerce department
- get commerce news article
- news
- federal government
- get news article
- list commerce department images
- get the full text of a specific commerce department news article by id. returns title, body, date, tags, and featured image.
- commerce
- get blog post
- list commerce blog posts
- list blogs
- list images and media assets published by the commerce department. useful for finding official images for news stories and publications.
- list commerce images
- get a specific commerce department news article
- blog posts from commerce department officials and bureaus
- economic data
- get a specific commerce department blog post
- trade
- list blog posts from commerce department officials and bureaus. blog posts provide policy commentary, program updates, and feature stories.
- get the full content of a specific commerce department blog post. returns author, body text, date, and topic tags.
- single commerce department news article
- list commerce department blog posts
- single commerce department blog post
- list commerce news
- get commerce blog post
- content
- standards
- climate
- list recent commerce department news articles
- latest news from the us department of commerce
- list news
- list images
- list recent news articles from the us department of commerce. use to monitor agency announcements, trade policy updates, economic reports, and bureau news from noaa, census, bea, ita, and nist.
slug: commerce-content
source_filename: commerce-content.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"US Department of Commerce Content\"\n  description: >-\n    Workflow capability for accessing US Department of Commerce news, blog posts,\n    and media content. Useful for journalists, researchers, policy analysts, and\n    citizens who need to monitor Commerce Department announcements, economic\n    reports, and agency updates.\n  tags:\n    - Commerce\n    - Federal Government\n    - News\n    - Content\n    - Open Data\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys: {}\n\ncapability:\n  consumes:\n    - import: commerce-gov\n      location: ./shared/commerce-gov-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: commerce-content-api\n      description: \"Unified REST API for accessing US Department of Commerce content.\"\n      resources:\n        - path: /v1/news\n          name: news\n          description: \"Latest news from the US Department of Commerce\"\
  \n          operations:\n            - method: GET\n              name: list-news\n              description: \"List recent Commerce Department news articles\"\n              call: \"commerce-gov.list-news\"\n              with:\n                page: \"rest.page\"\n                items_per_page: \"rest.items_per_page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/news/{id}\n          name: news-item\n          description: \"Single Commerce Department news article\"\n          operations:\n            - method: GET\n              name: get-news-article\n              description: \"Get a specific Commerce Department news article\"\n              call: \"commerce-gov.get-news-article\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/blogs\n          name: blogs\n          description:\
  \ \"Blog posts from Commerce Department officials and bureaus\"\n          operations:\n            - method: GET\n              name: list-blogs\n              description: \"List Commerce Department blog posts\"\n              call: \"commerce-gov.list-blogs\"\n              with:\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/blogs/{id}\n          name: blog-item\n          description: \"Single Commerce Department blog post\"\n          operations:\n            - method: GET\n              name: get-blog-post\n              description: \"Get a specific Commerce Department blog post\"\n              call: \"commerce-gov.get-blog-post\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/images\n          name: images\n          description: \"Media images\
  \ from Commerce Department\"\n          operations:\n            - method: GET\n              name: list-images\n              description: \"List Commerce Department images\"\n              call: \"commerce-gov.list-images\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: commerce-content-mcp\n      transport: http\n      description: \"MCP server for AI-assisted monitoring of US Department of Commerce announcements and content.\"\n      tools:\n        - name: list-commerce-news\n          description: >-\n            List recent news articles from the US Department of Commerce.\n            Use to monitor agency announcements, trade policy updates, economic reports,\n            and bureau news from NOAA, Census, BEA, ITA, and NIST.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"commerce-gov.list-news\"\n          with:\n         \
  \   page: \"tools.page\"\n            items_per_page: \"tools.items_per_page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-commerce-news-article\n          description: >-\n            Get the full text of a specific Commerce Department news article by ID.\n            Returns title, body, date, tags, and featured image.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"commerce-gov.get-news-article\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-commerce-blog-posts\n          description: >-\n            List blog posts from Commerce Department officials and bureaus.\n            Blog posts provide policy commentary, program updates, and feature stories.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"commerce-gov.list-blogs\"\
  \n          with:\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-commerce-blog-post\n          description: >-\n            Get the full content of a specific Commerce Department blog post.\n            Returns author, body text, date, and topic tags.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"commerce-gov.get-blog-post\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-commerce-images\n          description: >-\n            List images and media assets published by the Commerce Department.\n            Useful for finding official images for news stories and publications.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"commerce-gov.list-images\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n"
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
