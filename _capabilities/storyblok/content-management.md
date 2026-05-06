---
categories: []
consumed_apis: []
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
- webhooks
- list manage stories
- cdn list links
- create a new story in a storyblok space
- list links
- list components
- content story operations
- publish story
- cdn list stories
- rest api
- assets
- management story operations
- list published stories (delivery)
- list component schemas
- get story
- mapi update story
- list media assets
- list all stories including drafts via management api
- list published stories from the content delivery api with filtering by slug prefix, full-text search, and pagination support.
- mapi list stories
- list component schemas to understand content structure
- list webhook endpoints configured in the space
- mapi create story
- cdn list datasource entries
- publish a story
- visual editor
- content management
- publish a story to make it live on the content delivery api
- list media assets in the space asset library
- list stories via management api
- image optimization
- headless cms
- stories
- content delivery
- create a new story
- retrieve a specific published story by its full url slug
- create story
- list stories
- mapi delete story
- fetch options, translations, or config data from a datasource
- mapi list components
- list assets
- permanently delete a story from the space
- get a story by full slug (delivery)
- mapi list webhooks
- update the content or metadata of an existing story
- get the story url tree for building navigation menus or sitemaps
- cms
- cdn get story
- list datasources
- mapi publish story
- get story link tree for navigation
- mapi list assets
- components
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Storyblok Content Management\n  description: Unified capability for managing and delivering Storyblok headless CMS content. Combines the Content Delivery\n    API for fetching published content and the Management API for creating, editing, and publishing content programmatically.\n    Supports content migration, editorial automation, CI/CD pipelines, and headless site generation workflows.\n  tags:\n  - Assets\n  - CMS\n  - Components\n  - Content Delivery\n  - Content Management\n  - Headless CMS\n  - Stories\n  - Webhooks\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STORYBLOK_CDN_TOKEN: STORYBLOK_CDN_TOKEN\n    STORYBLOK_MANAGEMENT_TOKEN: STORYBLOK_MANAGEMENT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: storyblok-cdn\n    baseUri: https://api.storyblok.com/v2/cdn\n    description: Storyblok Content Delivery API v2\n    authentication:\n      type: apikey\n      key: token\n\
  \      value: '{{STORYBLOK_CDN_TOKEN}}'\n      placement: query\n    resources:\n    - name: stories\n      path: /stories\n      description: Published story content\n      operations:\n      - name: list-stories\n        method: GET\n        description: List published stories with filtering and pagination\n        inputParameters:\n        - name: version\n          in: query\n          type: string\n          required: false\n          description: 'Content version: published or draft'\n        - name: starts_with\n          in: query\n          type: string\n          required: false\n          description: Filter stories by slug prefix\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page (max 200)\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination\n        - name: sort_by\n          in: query\n      \
  \    type: string\n          required: false\n          description: Field to sort by\n        - name: search_term\n          in: query\n          type: string\n          required: false\n          description: Full-text search query\n        - name: filter_query\n          in: query\n          type: string\n          required: false\n          description: Filter stories by component field values\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-story-by-slug\n        method: GET\n        description: Retrieve a single story by its full slug\n        inputParameters:\n        - name: slug\n          in: path\n          type: string\n          required: true\n          description: Full slug of the story\n        - name: version\n          in: query\n          type: string\n          required: false\n          description: 'Content version: published or draft'\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-story-by-id\n        method: GET\n        description: Retrieve a single story by its numeric ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Numeric story ID\n        - name: version\n          in: query\n          type: string\n          required: false\n          description: Content version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasources\n      path: /datasources\n      description: Reusable key-value datasources\n      operations:\n      - name: list-datasources\n        method: GET\n        description: List datasources in the space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ list-datasource-entries\n        method: GET\n        description: List entries from a datasource\n        inputParameters:\n        - name: datasource\n          in: query\n          type: string\n          required: false\n          description: Datasource slug to filter entries\n        - name: dimension\n          in: query\n          type: string\n          required: false\n          description: Dimension (locale) for entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: links\n      path: /links\n      description: Story URL tree for navigation\n      operations:\n      - name: list-links\n        method: GET\n        description: List all story links for sitemap or navigation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /tags\n      description: Story tags\n      operations:\n\
  \      - name: list-tags\n        method: GET\n        description: List all tags used in stories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: storyblok-mapi\n    baseUri: https://mapi.storyblok.com/v1\n    description: Storyblok Management API\n    authentication:\n      type: bearer\n      token: '{{STORYBLOK_MANAGEMENT_TOKEN}}'\n    resources:\n    - name: spaces\n      path: /spaces/{space_id}\n      description: Space configuration and metadata\n      operations:\n      - name: get-space\n        method: GET\n        description: Retrieve space details and configuration\n        inputParameters:\n        - name: space_id\n          in: path\n          type: integer\n          required: true\n          description: Numeric space identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: stories\n      path: /spaces/{space_id}/stories\n      description: Story CRUD operations\n      operations:\n      - name: list-management-stories\n        method: GET\n        description: List stories in a space with pagination\n        inputParameters:\n        - name: space_id\n          in: path\n          type: integer\n          required: true\n          description: Space identifier\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: text_search\n          in: query\n          type: string\n          required: false\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-story\n        method: POST\n       \
  \ description: Create a new story in the space\n        inputParameters:\n        - name: space_id\n          in: path\n          type: integer\n          required: true\n          description: Space identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            story: '{{tools.story}}'\n      - name: get-story\n        method: GET\n        description: Retrieve a story by ID\n        inputParameters:\n        - name: space_id\n          in: path\n          type: integer\n          required: true\n          description: Space identifier\n        - name: story_id\n          in: path\n          type: integer\n          required: true\n          description: Story identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-story\n        method: PUT\n\
  \        description: Update an existing story\n        inputParameters:\n        - name: space_id\n          in: path\n          type: integer\n          required: true\n          description: Space identifier\n        - name: story_id\n          in: path\n          type: integer\n          required: true\n          description: Story identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            story: '{{tools.story}}'\n      - name: delete-story\n        method: DELETE\n        description: Delete a story\n        inputParameters:\n        - name: space_id\n          in: path\n          type: integer\n          required: true\n          description: Space identifier\n        - name: story_id\n          in: path\n          type: integer\n          required: true\n          description: Story identifier\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: publish-story\n        method: GET\n        description: Publish a story\n        inputParameters:\n        - name: space_id\n          in: path\n          type: integer\n          required: true\n          description: Space identifier\n        - name: story_id\n          in: path\n          type: integer\n          required: true\n          description: Story identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unpublish-story\n        method: GET\n        description: Unpublish a story\n        inputParameters:\n        - name: space_id\n          in: path\n          type: integer\n          required: true\n          description: Space identifier\n        - name: story_id\n          in: path\n          type: integer\n          required: true\n          description: Story identifier\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: components\n      path: /spaces/{space_id}/components\n      description: Component schema management\n      operations:\n      - name: list-components\n        method: GET\n        description: List component definitions in a space\n        inputParameters:\n        - name: space_id\n          in: path\n          type: integer\n          required: true\n          description: Space identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-component\n        method: GET\n        description: Retrieve a component definition by ID\n        inputParameters:\n        - name: space_id\n          in: path\n          type: integer\n          required: true\n          description: Space identifier\n        - name: component_id\n          in: path\n          type: integer\n         \
  \ required: true\n          description: Component identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets\n      path: /spaces/{space_id}/assets\n      description: Asset library management\n      operations:\n      - name: list-assets\n        method: GET\n        description: List assets in the space library\n        inputParameters:\n        - name: space_id\n          in: path\n          type: integer\n          required: true\n          description: Space identifier\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search query\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /spaces/{space_id}/webhook_endpoints\n      description: Webhook endpoint management\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List webhook endpoints configured in the space\n        inputParameters:\n        - name: space_id\n          in: path\n          type: integer\n          required: true\n          description: Space identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a new webhook endpoint\n        inputParameters:\n        - name: space_id\n          in: path\n          type: integer\n          required: true\n          description: Space identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            webhook_endpoint: '{{tools.webhook_endpoint}}'\n      - name: delete-webhook\n        method: DELETE\n        description: Delete a webhook endpoint\n        inputParameters:\n        - name: space_id\n          in: path\n          type: integer\n          required: true\n          description: Space identifier\n        - name: webhook_id\n          in: path\n          type: integer\n          required: true\n          description: Webhook identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: storyblok-content-api\n    description: Unified REST API for Storyblok content management and delivery.\n    resources:\n    - path: /v1/stories\n      name: stories\n      description: Content story operations\n      operations:\n      - method:\
  \ GET\n        name: list-stories\n        description: List published stories (delivery)\n        call: storyblok-cdn.list-stories\n        with:\n          version: rest.version\n          starts_with: rest.starts_with\n          per_page: rest.per_page\n          page: rest.page\n          search_term: rest.search_term\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stories/{slug}\n      name: story-by-slug\n      operations:\n      - method: GET\n        name: get-story\n        description: Get a story by full slug (delivery)\n        call: storyblok-cdn.get-story-by-slug\n        with:\n          slug: rest.slug\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/manage/spaces/{space-id}/stories\n      name: manage-stories\n      description: Management story operations\n      operations:\n      - method: GET\n        name: list-manage-stories\n        description: List\
  \ stories via management API\n        call: storyblok-mapi.list-management-stories\n        with:\n          space_id: rest.space-id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-story\n        description: Create a new story\n        call: storyblok-mapi.create-story\n        with:\n          space_id: rest.space-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/manage/spaces/{space-id}/stories/{story-id}/publish\n      name: publish-story\n      operations:\n      - method: POST\n        name: publish-story\n        description: Publish a story\n        call: storyblok-mapi.publish-story\n        with:\n          space_id: rest.space-id\n          story_id: rest.story-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/manage/spaces/{space-id}/components\n      name: components\n      operations:\n      - method: GET\n        name:\
  \ list-components\n        description: List component schemas\n        call: storyblok-mapi.list-components\n        with:\n          space_id: rest.space-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/manage/spaces/{space-id}/assets\n      name: assets\n      operations:\n      - method: GET\n        name: list-assets\n        description: List media assets\n        call: storyblok-mapi.list-assets\n        with:\n          space_id: rest.space-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/links\n      name: links\n      operations:\n      - method: GET\n        name: list-links\n        description: Get story link tree for navigation\n        call: storyblok-cdn.list-links\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/datasources\n      name: datasources\n      operations:\n      - method: GET\n        name: list-datasources\n        description:\
  \ List datasources\n        call: storyblok-cdn.list-datasources\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: storyblok-content-mcp\n    transport: http\n    description: MCP server for AI-assisted Storyblok content management.\n    tools:\n    - name: cdn-list-stories\n      description: List published stories from the Content Delivery API with filtering by slug prefix, full-text search, and\n        pagination support.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: storyblok-cdn.list-stories\n      with:\n        version: tools.version\n        starts_with: tools.starts_with\n        per_page: tools.per_page\n        page: tools.page\n        search_term: tools.search_term\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cdn-get-story\n      description: Retrieve a specific published story by its full URL slug\n      hints:\n        readOnly: true\n\
  \        openWorld: false\n      call: storyblok-cdn.get-story-by-slug\n      with:\n        slug: tools.slug\n        version: tools.version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cdn-list-links\n      description: Get the story URL tree for building navigation menus or sitemaps\n      hints:\n        readOnly: true\n        openWorld: false\n      call: storyblok-cdn.list-links\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cdn-list-datasource-entries\n      description: Fetch options, translations, or config data from a datasource\n      hints:\n        readOnly: true\n        openWorld: false\n      call: storyblok-cdn.list-datasource-entries\n      with:\n        datasource: tools.datasource\n        dimension: tools.dimension\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mapi-list-stories\n      description: List all stories including drafts via management API\n      hints:\n\
  \        readOnly: true\n        openWorld: false\n      call: storyblok-mapi.list-management-stories\n      with:\n        space_id: tools.space_id\n        per_page: tools.per_page\n        page: tools.page\n        text_search: tools.text_search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mapi-create-story\n      description: Create a new story in a Storyblok space\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: storyblok-mapi.create-story\n      with:\n        space_id: tools.space_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mapi-update-story\n      description: Update the content or metadata of an existing story\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: storyblok-mapi.update-story\n      with:\n        space_id: tools.space_id\n        story_id: tools.story_id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: mapi-publish-story\n      description: Publish a story to make it live on the Content Delivery API\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: storyblok-mapi.publish-story\n      with:\n        space_id: tools.space_id\n        story_id: tools.story_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mapi-delete-story\n      description: Permanently delete a story from the space\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: storyblok-mapi.delete-story\n      with:\n        space_id: tools.space_id\n        story_id: tools.story_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mapi-list-components\n      description: List component schemas to understand content structure\n      hints:\n        readOnly: true\n        openWorld: false\n      call:\
  \ storyblok-mapi.list-components\n      with:\n        space_id: tools.space_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mapi-list-assets\n      description: List media assets in the space asset library\n      hints:\n        readOnly: true\n        openWorld: false\n      call: storyblok-mapi.list-assets\n      with:\n        space_id: tools.space_id\n        search: tools.search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: mapi-list-webhooks\n      description: List webhook endpoints configured in the space\n      hints:\n        readOnly: true\n        openWorld: false\n      call: storyblok-mapi.list-webhooks\n      with:\n        space_id: tools.space_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
