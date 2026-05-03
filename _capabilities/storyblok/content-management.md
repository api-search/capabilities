---
categories: []
consumed_apis:
- storyblok-cdn
- storyblok-mapi
description: Unified capability for managing and delivering Storyblok headless CMS content. Combines the Content Delivery API for fetching published content and the Management API for creating, editing, and publishing content programmatically. Supports content migration, editorial automation, CI/CD pipelines, and headless site generation workflows.
layout: capability
name: Storyblok Content Management
operations:
- description: List published stories (delivery)
  method: GET
  name: list-stories
  path: /v1/stories
- description: Get a story by full slug (delivery)
  method: GET
  name: get-story
  path: /v1/stories/{slug}
- description: List stories via management API
  method: GET
  name: list-manage-stories
  path: /v1/manage/spaces/{space-id}/stories
- description: Create a new story
  method: POST
  name: create-story
  path: /v1/manage/spaces/{space-id}/stories
- description: Publish a story
  method: POST
  name: publish-story
  path: /v1/manage/spaces/{space-id}/stories/{story-id}/publish
- description: List component schemas
  method: GET
  name: list-components
  path: /v1/manage/spaces/{space-id}/components
- description: List media assets
  method: GET
  name: list-assets
  path: /v1/manage/spaces/{space-id}/assets
- description: Get story link tree for navigation
  method: GET
  name: list-links
  path: /v1/links
- description: List datasources
  method: GET
  name: list-datasources
  path: /v1/datasources
personas: []
provider_name: Storyblok
provider_slug: storyblok
search_terms:
- mapi publish story
- assets
- list manage stories
- get the story url tree for building navigation menus or sitemaps
- mapi list assets
- visual editor
- list published stories (delivery)
- content story operations
- list links
- list stories
- publish story
- list media assets in the space asset library
- content management
- list datasources
- get story link tree for navigation
- publish a story
- list all stories including drafts via management api
- image optimization
- list component schemas to understand content structure
- list assets
- publish a story to make it live on the content delivery api
- webhooks
- mapi update story
- cdn list datasource entries
- list published stories from the content delivery api with filtering by slug prefix, full-text search, and pagination support.
- management story operations
- stories
- list media assets
- cdn list links
- mapi list components
- mapi list stories
- cdn list stories
- mapi create story
- update the content or metadata of an existing story
- get a story by full slug (delivery)
- list stories via management api
- rest api
- create story
- permanently delete a story from the space
- list webhook endpoints configured in the space
- mapi list webhooks
- components
- content delivery
- cdn get story
- headless cms
- get story
- fetch options, translations, or config data from a datasource
- list components
- mapi delete story
- cms
- retrieve a specific published story by its full url slug
- create a new story
- list component schemas
- create a new story in a storyblok space
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Storyblok Content Management\"\n  description: >-\n    Unified capability for managing and delivering Storyblok headless CMS content.\n    Combines the Content Delivery API for fetching published content and the\n    Management API for creating, editing, and publishing content programmatically.\n    Supports content migration, editorial automation, CI/CD pipelines, and\n    headless site generation workflows.\n  tags:\n    - Assets\n    - CMS\n    - Components\n    - Content Delivery\n    - Content Management\n    - Headless CMS\n    - Stories\n    - Webhooks\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STORYBLOK_CDN_TOKEN: STORYBLOK_CDN_TOKEN\n      STORYBLOK_MANAGEMENT_TOKEN: STORYBLOK_MANAGEMENT_TOKEN\n\ncapability:\n  consumes:\n    - import: storyblok-cdn\n      location: ./shared/content-delivery.yaml\n    - import: storyblok-mapi\n      location: ./shared/management.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: storyblok-content-api\n      description: \"Unified REST API for Storyblok content management and delivery.\"\n      resources:\n        - path: /v1/stories\n          name: stories\n          description: \"Content story operations\"\n          operations:\n            - method: GET\n              name: list-stories\n              description: \"List published stories (delivery)\"\n              call: \"storyblok-cdn.list-stories\"\n              with:\n                version: \"rest.version\"\n                starts_with: \"rest.starts_with\"\n                per_page: \"rest.per_page\"\n                page: \"rest.page\"\n                search_term: \"rest.search_term\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/stories/{slug}\n          name: story-by-slug\n          operations:\n            - method: GET\n              name: get-story\n\
  \              description: \"Get a story by full slug (delivery)\"\n              call: \"storyblok-cdn.get-story-by-slug\"\n              with:\n                slug: \"rest.slug\"\n                version: \"rest.version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/manage/spaces/{space-id}/stories\n          name: manage-stories\n          description: \"Management story operations\"\n          operations:\n            - method: GET\n              name: list-manage-stories\n              description: \"List stories via management API\"\n              call: \"storyblok-mapi.list-management-stories\"\n              with:\n                space_id: \"rest.space-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-story\n              description: \"Create a new story\"\n              call: \"storyblok-mapi.create-story\"\
  \n              with:\n                space_id: \"rest.space-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/manage/spaces/{space-id}/stories/{story-id}/publish\n          name: publish-story\n          operations:\n            - method: POST\n              name: publish-story\n              description: \"Publish a story\"\n              call: \"storyblok-mapi.publish-story\"\n              with:\n                space_id: \"rest.space-id\"\n                story_id: \"rest.story-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/manage/spaces/{space-id}/components\n          name: components\n          operations:\n            - method: GET\n              name: list-components\n              description: \"List component schemas\"\n              call: \"storyblok-mapi.list-components\"\n              with:\n                space_id:\
  \ \"rest.space-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/manage/spaces/{space-id}/assets\n          name: assets\n          operations:\n            - method: GET\n              name: list-assets\n              description: \"List media assets\"\n              call: \"storyblok-mapi.list-assets\"\n              with:\n                space_id: \"rest.space-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/links\n          name: links\n          operations:\n            - method: GET\n              name: list-links\n              description: \"Get story link tree for navigation\"\n              call: \"storyblok-cdn.list-links\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/datasources\n          name: datasources\n          operations:\n          \
  \  - method: GET\n              name: list-datasources\n              description: \"List datasources\"\n              call: \"storyblok-cdn.list-datasources\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: storyblok-content-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Storyblok content management.\"\n      tools:\n        - name: cdn-list-stories\n          description: >-\n            List published stories from the Content Delivery API with filtering\n            by slug prefix, full-text search, and pagination support.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"storyblok-cdn.list-stories\"\n          with:\n            version: \"tools.version\"\n            starts_with: \"tools.starts_with\"\n            per_page: \"tools.per_page\"\n            page: \"tools.page\"\n            search_term: \"\
  tools.search_term\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cdn-get-story\n          description: \"Retrieve a specific published story by its full URL slug\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"storyblok-cdn.get-story-by-slug\"\n          with:\n            slug: \"tools.slug\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cdn-list-links\n          description: \"Get the story URL tree for building navigation menus or sitemaps\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"storyblok-cdn.list-links\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cdn-list-datasource-entries\n          description: \"Fetch options, translations, or config data from a datasource\"\
  \n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"storyblok-cdn.list-datasource-entries\"\n          with:\n            datasource: \"tools.datasource\"\n            dimension: \"tools.dimension\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: mapi-list-stories\n          description: \"List all stories including drafts via management API\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"storyblok-mapi.list-management-stories\"\n          with:\n            space_id: \"tools.space_id\"\n            per_page: \"tools.per_page\"\n            page: \"tools.page\"\n            text_search: \"tools.text_search\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: mapi-create-story\n          description: \"Create a new story in a Storyblok space\"\n          hints:\n            readOnly:\
  \ false\n            destructive: false\n            idempotent: false\n          call: \"storyblok-mapi.create-story\"\n          with:\n            space_id: \"tools.space_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: mapi-update-story\n          description: \"Update the content or metadata of an existing story\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"storyblok-mapi.update-story\"\n          with:\n            space_id: \"tools.space_id\"\n            story_id: \"tools.story_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: mapi-publish-story\n          description: \"Publish a story to make it live on the Content Delivery API\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"storyblok-mapi.publish-story\"\
  \n          with:\n            space_id: \"tools.space_id\"\n            story_id: \"tools.story_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: mapi-delete-story\n          description: \"Permanently delete a story from the space\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"storyblok-mapi.delete-story\"\n          with:\n            space_id: \"tools.space_id\"\n            story_id: \"tools.story_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: mapi-list-components\n          description: \"List component schemas to understand content structure\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"storyblok-mapi.list-components\"\n          with:\n            space_id: \"tools.space_id\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n\n        - name: mapi-list-assets\n          description: \"List media assets in the space asset library\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"storyblok-mapi.list-assets\"\n          with:\n            space_id: \"tools.space_id\"\n            search: \"tools.search\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: mapi-list-webhooks\n          description: \"List webhook endpoints configured in the space\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"storyblok-mapi.list-webhooks\"\n          with:\n            space_id: \"tools.space_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/storyblok/refs/heads/main/capabilities/content-management.yaml
tags:
- Assets
- CMS
- Components
- Content Delivery
- Content Management
- Headless CMS
- Stories
- Webhooks
tools:
- description: List published stories from the Content Delivery API with filtering by slug prefix, full-text search, and pagination support.
  hints:
    openWorld: false
    readOnly: true
  name: cdn-list-stories
- description: Retrieve a specific published story by its full URL slug
  hints:
    openWorld: false
    readOnly: true
  name: cdn-get-story
- description: Get the story URL tree for building navigation menus or sitemaps
  hints:
    openWorld: false
    readOnly: true
  name: cdn-list-links
- description: Fetch options, translations, or config data from a datasource
  hints:
    openWorld: false
    readOnly: true
  name: cdn-list-datasource-entries
- description: List all stories including drafts via management API
  hints:
    openWorld: false
    readOnly: true
  name: mapi-list-stories
- description: Create a new story in a Storyblok space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: mapi-create-story
- description: Update the content or metadata of an existing story
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: mapi-update-story
- description: Publish a story to make it live on the Content Delivery API
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: mapi-publish-story
- description: Permanently delete a story from the space
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: mapi-delete-story
- description: List component schemas to understand content structure
  hints:
    openWorld: false
    readOnly: true
  name: mapi-list-components
- description: List media assets in the space asset library
  hints:
    openWorld: false
    readOnly: true
  name: mapi-list-assets
- description: List webhook endpoints configured in the space
  hints:
    openWorld: false
    readOnly: true
  name: mapi-list-webhooks
---
