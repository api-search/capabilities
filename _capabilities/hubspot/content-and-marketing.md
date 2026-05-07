---
categories:
- content-management
consumed_apis: []
description: Unified workflow for marketing managers to manage blog content, authors, landing pages, site pages, domains, analytics events, and transactional email. Combines CMS and marketing APIs into a single content operations interface.
layout: capability
name: HubSpot Content And Marketing
operations:
- description: List all blog posts
  method: GET
  name: list-blog-posts
  path: /v1/blog-posts
- description: Create a blog post
  method: POST
  name: create-blog-post
  path: /v1/blog-posts
- description: Get a blog post
  method: GET
  name: get-blog-post
  path: /v1/blog-posts/{objectId}
- description: Update a blog post
  method: PATCH
  name: update-blog-post
  path: /v1/blog-posts/{objectId}
- description: Archive a blog post
  method: DELETE
  name: archive-blog-post
  path: /v1/blog-posts/{objectId}
- description: List all blog authors
  method: GET
  name: list-blog-authors
  path: /v1/blog-authors
- description: Retrieve analytics events
  method: GET
  name: list-events
  path: /v1/events
- description: List available event types
  method: GET
  name: list-event-types
  path: /v1/event-types
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- individual blog post
- analytics
- hubspot
- get analytics events
- operations
- list events
- list available analytics event types
- clone blog post
- create a blog post
- retrieve analytics events
- list all blog posts
- push blog post live
- list all blog posts in hubspot
- get a blog post
- get blog post revisions
- commerce
- create a new blog post
- list blog authors
- list all blog authors
- clone an existing blog post
- list available event types
- crm
- update an existing blog post
- blog author management
- content
- schedule a blog post for publication
- cms
- schedule blog post
- get blog post
- get revision history for a blog post
- get a blog author by id
- create blog post
- create a new blog author
- update blog post
- create blog author
- blog
- marketing
- list blog posts
- retrieve analytics event data for crm objects
- get event types
- blog post management
- sales
- analytics events
- update a blog post
- event type definitions
- list event types
- push a draft blog post to live
- get blog author
- customer service
- get a specific blog post by id
- archive a blog post
- marketing automation
- archive blog post
- email marketing
slug: content-and-marketing
source_filename: content-and-marketing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HubSpot Content And Marketing\n  description: Unified workflow for marketing managers to manage blog content, authors, landing pages, site pages, domains,\n    analytics events, and transactional email. Combines CMS and marketing APIs into a single content operations interface.\n  tags:\n  - HubSpot\n  - Marketing\n  - Content\n  - CMS\n  - Blog\n  - Analytics\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: blog-posts\n    baseUri: https://api.hubapi.com\n    description: HubSpot Blog Posts API for creating, publishing, and managing blog content.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: posts\n      path: /cms/v3/blogs/posts\n      description: Blog post management\n      operations:\n      - name: list-blog-posts\n        method:\
  \ GET\n        description: List all blog posts\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results per page\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: archived\n          in: query\n          type: boolean\n          required: false\n          description: Whether to return archived posts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-blog-post\n        method: POST\n        description: Create a new blog post\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            contentGroupId: '{{tools.contentGroupId}}'\n\
  \            postBody: '{{tools.postBody}}'\n    - name: post-by-id\n      path: /cms/v3/blogs/posts/{objectId}\n      description: Individual blog post operations\n      operations:\n      - name: get-blog-post\n        method: GET\n        description: Retrieve a blog post by ID\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n          description: The blog post ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-blog-post\n        method: PATCH\n        description: Update a blog post\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n          description: The blog post ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n   \
  \       data:\n            name: '{{tools.name}}'\n            postBody: '{{tools.postBody}}'\n      - name: archive-blog-post\n        method: DELETE\n        description: Archive a blog post\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n          description: The blog post ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedule\n      path: /cms/v3/blogs/posts/schedule\n      description: Blog post scheduling\n      operations:\n      - name: schedule-blog-post\n        method: POST\n        description: Schedule a blog post for publication\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            id: '{{tools.id}}'\n            publishDate: '{{tools.publishDate}}'\n    - name: clone\n\
  \      path: /cms/v3/blogs/posts/clone\n      description: Blog post cloning\n      operations:\n      - name: clone-blog-post\n        method: POST\n        description: Clone a blog post\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            id: '{{tools.id}}'\n    - name: push-live\n      path: /cms/v3/blogs/posts/{objectId}/draft/push-live\n      description: Push draft to live\n      operations:\n      - name: push-blog-post-live\n        method: POST\n        description: Push draft to live version\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n          description: The blog post ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: revisions\n      path: /cms/v3/blogs/posts/{objectId}/revisions\n\
  \      description: Blog post revision history\n      operations:\n      - name: get-blog-post-revisions\n        method: GET\n        description: Get revision history for a blog post\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n          description: The blog post ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: blog-authors\n    baseUri: https://api.hubapi.com\n    description: HubSpot Blog Authors API for managing blog author profiles.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: authors\n      path: /cms/v3/blogs/authors\n      description: Blog author profiles\n      operations:\n      - name: list-blog-authors\n        method: GET\n        description: List all blog authors\n        inputParameters:\n        - name: limit\n  \
  \        in: query\n          type: integer\n          required: false\n          description: Maximum number of results per page\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: archived\n          in: query\n          type: boolean\n          required: false\n          description: Whether to return archived authors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-blog-author\n        method: POST\n        description: Create a new blog author\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            slug: '{{tools.slug}}'\n            email: '{{tools.email}}'\n            bio: '{{tools.bio}}'\n\
  \    - name: author-by-id\n      path: /cms/v3/blogs/authors/{objectId}\n      description: Individual blog author operations\n      operations:\n      - name: get-blog-author\n        method: GET\n        description: Retrieve a blog author by ID\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n          description: The blog author ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-blog-author\n        method: PATCH\n        description: Update a blog author\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n          description: The blog author ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name:\
  \ '{{tools.name}}'\n            bio: '{{tools.bio}}'\n      - name: archive-blog-author\n        method: DELETE\n        description: Archive a blog author\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n          description: The blog author ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: batch-read\n      path: /cms/v3/blogs/authors/batch/read\n      description: Batch read blog authors\n      operations:\n      - name: batch-read-blog-authors\n        method: POST\n        description: Read multiple blog authors by IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n    - name: batch-create\n      path: /cms/v3/blogs/authors/batch/create\n     \
  \ description: Batch create blog authors\n      operations:\n      - name: batch-create-blog-authors\n        method: POST\n        description: Create multiple blog authors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n    - name: batch-archive\n      path: /cms/v3/blogs/authors/batch/archive\n      description: Batch archive blog authors\n      operations:\n      - name: batch-archive-blog-authors\n        method: POST\n        description: Archive multiple blog authors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n  - type: http\n    namespace: analytics-events\n    baseUri: https://api.hubapi.com\n    description: HubSpot Analytics Events\
  \ API for retrieving event completion data from CRM objects.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: event-instances\n      path: /events/v3/events\n      description: Event instances for CRM objects\n      operations:\n      - name: get-event-instances\n        method: GET\n        description: Retrieve instances of event completion data\n        inputParameters:\n        - name: objectType\n          in: query\n          type: string\n          required: false\n          description: The type of CRM object to filter on\n        - name: objectId\n          in: query\n          type: string\n          required: false\n          description: The ID of the CRM object to filter events\n        - name: eventType\n          in: query\n          type: string\n          required: false\n          description: Filter by specific event type name\n        - name: occurredAfter\n          in: query\n          type: string\n  \
  \        required: false\n          description: Filter for events after this ISO 8601 datetime\n        - name: occurredBefore\n          in: query\n          type: string\n          required: false\n          description: Filter for events before this ISO 8601 datetime\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort direction based on event timestamp\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results per page\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor for the next page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-types\n      path: /events/v3/events/event-types\n      description: Available event type definitions\n      operations:\n\
  \      - name: get-event-types\n        method: GET\n        description: Retrieve available event types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: cms-pages-api\n    baseUri: https://api.hubapi.com\n    description: The CMS Pages API provides endpoints for creating and managing site pages and landing pages hosted on HubSpot.\n      You can create, retrieve, update, publish, and delete both site pages and landing pages p\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: site-pages\n      path: /site-pages\n      description: site-pages operations\n      operations:\n      - name: listsitepages\n        method: GET\n        description: HubSpot List Site Pages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsitepage\n\
  \        method: POST\n        description: HubSpot Create a Site Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getsitepage\n        method: GET\n        description: HubSpot Get a Site Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesitepage\n        method: PATCH\n        description: HubSpot Update a Site Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesitepage\n        method: DELETE\n        description: HubSpot Delete a Site Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: push-live\n      path: /push-live\n      description: push-live operations\n      operations:\n      - name:\
  \ publishsitepage\n        method: POST\n        description: HubSpot Publish a Site Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: landing-pages\n      path: /landing-pages\n      description: landing-pages operations\n      operations:\n      - name: listlandingpages\n        method: GET\n        description: HubSpot List Landing Pages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlandingpage\n        method: POST\n        description: HubSpot Create a Landing Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getlandingpage\n        method: GET\n        description: HubSpot Get a Landing Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: deletelandingpage\n        method: DELETE\n        description: HubSpot Delete a Landing Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: domains-api\n    baseUri: https://api.hubapi.com\n    description: 'The HubSpot CMS Domains API allows you to retrieve information about domains connected to a HubSpot CMS\n      site.\n\n\n      Use this API to:\n\n      - List all domains connected to your HubSpot account\n\n      - Get detailed info'\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: domains\n      path: /domains\n      description: domains operations\n      operations:\n      - name: listdomains\n        method: GET\n        description: HubSpot List All Domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n      - name: getdomainbyid\n        method: GET\n        description: HubSpot Get a Domain by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: marketing-emal-api\n    baseUri: https://api.hubapi.com\n    description: 'The HubSpot Marketing Transactional Email API enables you to send transactional emails and manage SMTP tokens.\n\n\n      Use this API to:\n\n      - Create and manage SMTP API tokens for sending transactional emails\n\n      - '\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: smtp-tokens\n      path: /smtp-tokens\n      description: smtp-tokens operations\n      operations:\n      - name: listsmtptokens\n        method: GET\n        description: HubSpot List All SMTP Tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: createsmtptoken\n        method: POST\n        description: HubSpot Create an SMTP Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getsmtptokenbyid\n        method: GET\n        description: HubSpot Get an SMTP Token by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesmtptoken\n        method: DELETE\n        description: HubSpot Delete an SMTP Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: password-reset\n      path: /password-reset\n      description: password-reset operations\n      operations:\n      - name: resetsmtptokenpassword\n        method: POST\n        description: HubSpot Reset SMTP Token Password\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: send\n      path: /send\n      description: send operations\n      operations:\n      - name: sendtransactionalemail\n        method: POST\n        description: HubSpot Send a Transactional Email\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: content-marketing-api\n    description: Unified REST API for content creation, publishing, and marketing analytics.\n    resources:\n    - path: /v1/blog-posts\n      name: blog-posts\n      description: Blog post management\n      operations:\n      - method: GET\n        name: list-blog-posts\n        description: List all blog posts\n        call: blog-posts.list-blog-posts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-blog-post\n        description: Create\
  \ a blog post\n        call: blog-posts.create-blog-post\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/blog-posts/{objectId}\n      name: blog-post-by-id\n      description: Individual blog post\n      operations:\n      - method: GET\n        name: get-blog-post\n        description: Get a blog post\n        call: blog-posts.get-blog-post\n        with:\n          objectId: rest.objectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-blog-post\n        description: Update a blog post\n        call: blog-posts.update-blog-post\n        with:\n          objectId: rest.objectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: archive-blog-post\n        description: Archive a blog post\n        call: blog-posts.archive-blog-post\n        with:\n          objectId: rest.objectId\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n    - path: /v1/blog-authors\n      name: blog-authors\n      description: Blog author management\n      operations:\n      - method: GET\n        name: list-blog-authors\n        description: List all blog authors\n        call: blog-authors.list-blog-authors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Analytics events\n      operations:\n      - method: GET\n        name: list-events\n        description: Retrieve analytics events\n        call: analytics-events.get-event-instances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-types\n      name: event-types\n      description: Event type definitions\n      operations:\n      - method: GET\n        name: list-event-types\n        description: List available event types\n        call: analytics-events.get-event-types\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: content-marketing-mcp\n    transport: http\n    description: MCP server for AI-assisted content creation, blog management, and marketing analytics.\n    tools:\n    - name: list-blog-posts\n      description: List all blog posts in HubSpot\n      hints:\n        readOnly: true\n        idempotent: true\n      call: blog-posts.list-blog-posts\n      with:\n        limit: tools.limit\n        after: tools.after\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-blog-post\n      description: Get a specific blog post by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: blog-posts.get-blog-post\n      with:\n        objectId: tools.objectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-blog-post\n      description: Create a new blog post\n      hints:\n        readOnly: false\n      call: blog-posts.create-blog-post\n\
  \      with:\n        name: tools.name\n        contentGroupId: tools.contentGroupId\n        postBody: tools.postBody\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-blog-post\n      description: Update an existing blog post\n      hints:\n        readOnly: false\n        idempotent: true\n      call: blog-posts.update-blog-post\n      with:\n        objectId: tools.objectId\n        name: tools.name\n        postBody: tools.postBody\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: schedule-blog-post\n      description: Schedule a blog post for publication\n      hints:\n        readOnly: false\n      call: blog-posts.schedule-blog-post\n      with:\n        id: tools.id\n        publishDate: tools.publishDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clone-blog-post\n      description: Clone an existing blog post\n      hints:\n        readOnly: false\n      call: blog-posts.clone-blog-post\n\
  \      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: push-blog-post-live\n      description: Push a draft blog post to live\n      hints:\n        readOnly: false\n      call: blog-posts.push-blog-post-live\n      with:\n        objectId: tools.objectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-blog-authors\n      description: List all blog authors\n      hints:\n        readOnly: true\n        idempotent: true\n      call: blog-authors.list-blog-authors\n      with:\n        limit: tools.limit\n        after: tools.after\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-blog-author\n      description: Get a blog author by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: blog-authors.get-blog-author\n      with:\n        objectId: tools.objectId\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: create-blog-author\n      description: Create a new blog author\n      hints:\n        readOnly: false\n      call: blog-authors.create-blog-author\n      with:\n        name: tools.name\n        email: tools.email\n        bio: tools.bio\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-analytics-events\n      description: Retrieve analytics event data for CRM objects\n      hints:\n        readOnly: true\n        idempotent: true\n      call: analytics-events.get-event-instances\n      with:\n        objectType: tools.objectType\n        objectId: tools.objectId\n        eventType: tools.eventType\n        occurredAfter: tools.occurredAfter\n        occurredBefore: tools.occurredBefore\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-event-types\n      description: List available analytics event types\n      hints:\n        readOnly: true\n        idempotent: true\n      call: analytics-events.get-event-types\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: archive-blog-post\n      description: Archive a blog post\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: blog-posts.archive-blog-post\n      with:\n        objectId: tools.objectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-blog-post-revisions\n      description: Get revision history for a blog post\n      hints:\n        readOnly: true\n        idempotent: true\n      call: blog-posts.get-blog-post-revisions\n      with:\n        objectId: tools.objectId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hubspot/refs/heads/main/capabilities/content-and-marketing.yaml
tags:
- HubSpot
- Marketing
- Content
- CMS
- Blog
- Analytics
tools:
- description: List all blog posts in HubSpot
  hints:
    idempotent: true
    readOnly: true
  name: list-blog-posts
- description: Get a specific blog post by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-blog-post
- description: Create a new blog post
  hints:
    readOnly: false
  name: create-blog-post
- description: Update an existing blog post
  hints:
    idempotent: true
    readOnly: false
  name: update-blog-post
- description: Schedule a blog post for publication
  hints:
    readOnly: false
  name: schedule-blog-post
- description: Clone an existing blog post
  hints:
    readOnly: false
  name: clone-blog-post
- description: Push a draft blog post to live
  hints:
    readOnly: false
  name: push-blog-post-live
- description: List all blog authors
  hints:
    idempotent: true
    readOnly: true
  name: list-blog-authors
- description: Get a blog author by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-blog-author
- description: Create a new blog author
  hints:
    readOnly: false
  name: create-blog-author
- description: Retrieve analytics event data for CRM objects
  hints:
    idempotent: true
    readOnly: true
  name: get-analytics-events
- description: List available analytics event types
  hints:
    idempotent: true
    readOnly: true
  name: get-event-types
- description: Archive a blog post
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: archive-blog-post
- description: Get revision history for a blog post
  hints:
    idempotent: true
    readOnly: true
  name: get-blog-post-revisions
---
