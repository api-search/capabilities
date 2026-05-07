---
categories:
- content-management
consumed_apis: []
description: Unified workflow for managing Confluence content including pages, blog posts, comments, attachments, spaces, and labels. Used by content authors, knowledge managers, and platform administrators.
layout: capability
name: Confluence Content Management
operations:
- description: List all pages with optional filtering
  method: GET
  name: list-pages
  path: /v1/pages
- description: Create a new page
  method: POST
  name: create-page
  path: /v1/pages
- description: Get a page by ID
  method: GET
  name: get-page
  path: /v1/pages/{id}
- description: Update a page
  method: PUT
  name: update-page
  path: /v1/pages/{id}
- description: Delete a page
  method: DELETE
  name: delete-page
  path: /v1/pages/{id}
- description: List child pages
  method: GET
  name: list-child-pages
  path: /v1/pages/{id}/children
- description: Get labels for a page
  method: GET
  name: get-page-labels
  path: /v1/pages/{id}/labels
- description: List attachments for a page
  method: GET
  name: list-page-attachments
  path: /v1/pages/{id}/attachments
- description: List footer comments for a page
  method: GET
  name: list-footer-comments
  path: /v1/pages/{id}/comments
- description: List all spaces
  method: GET
  name: list-spaces
  path: /v1/spaces
- description: Get a space by ID
  method: GET
  name: get-space
  path: /v1/spaces/{id}
- description: List pages in a space
  method: GET
  name: list-pages-in-space
  path: /v1/spaces/{id}/pages
- description: List all blog posts
  method: GET
  name: list-blog-posts
  path: /v1/blog-posts
- description: Create a new blog post
  method: POST
  name: create-blog-post
  path: /v1/blog-posts
- description: Get a blog post by ID
  method: GET
  name: get-blog-post
  path: /v1/blog-posts/{id}
- description: Update a blog post
  method: PUT
  name: update-blog-post
  path: /v1/blog-posts/{id}
- description: Delete a blog post
  method: DELETE
  name: delete-blog-post
  path: /v1/blog-posts/{id}
- description: Get a comment by ID
  method: GET
  name: get-comment
  path: /v1/comments/{id}
- description: Update a comment
  method: PUT
  name: update-comment
  path: /v1/comments/{id}
- description: Delete a comment
  method: DELETE
  name: delete-comment
  path: /v1/comments/{id}
- description: Get an attachment by ID
  method: GET
  name: get-attachment
  path: /v1/attachments/{id}
- description: Delete an attachment
  method: DELETE
  name: delete-attachment
  path: /v1/attachments/{id}
- description: Get a label by ID
  method: GET
  name: get-label
  path: /v1/labels/{id}
personas: []
provider_name: Confluence
provider_slug: confluence
search_terms:
- label information
- list footer comments on a specific page.
- list attachments for a page
- get a specific comment by its id.
- confluence
- get a specific label by its id.
- delete an attachment
- list pages in a space
- delete a blog post
- documentation
- get space
- list footer comments for a page
- delete a page
- update an existing comment.
- list footer comments
- get a space by id
- list pages
- create a new confluence blog post.
- get page
- child page navigation
- get a specific blog post by its id.
- update comment
- delete an attachment by id.
- update a comment
- individual blog post operations
- list all spaces
- delete attachment
- get a specific attachment by its id.
- delete blog post
- collaboration
- list all blog posts with optional space filtering.
- list all confluence spaces.
- delete a comment
- get blog post
- create an inline comment on a specific text selection in a page.
- individual space operations
- get a specific confluence page by its id.
- page attachment management
- create blog post
- manage comments
- pages within a space
- create footer comment
- get labels for a page
- list pages in space
- list page attachments
- get a label by id
- get all labels applied to a specific page.
- get a page by id
- manage confluence spaces
- delete page
- list all pages with optional filtering
- list all blog posts
- get an attachment by id
- create a new confluence page in a space.
- create a footer comment on a page or blog post.
- delete a blog post by id.
- get a specific confluence space by its id.
- list all confluence pages with optional filtering by space, status, and title.
- delete a comment by id.
- list inline comments
- list all pages belonging to a specific space.
- manage confluence pages
- manage attachments
- list child pages
- get a blog post by id
- manage blog posts
- list child pages of a specific page for navigating content hierarchies.
- update an existing blog post.
- individual page operations
- update an existing confluence page title and body.
- delete comment
- create inline comment
- get comment
- delete a confluence page by id.
- page comment management
- list inline comments on a specific page.
- get page labels
- wiki
- update page
- create a new blog post
- knowledge base
- page label management
- update a page
- list all file attachments on a specific page.
- get label
- update blog post
- content management
- list blog posts
- get a comment by id
- create page
- update a blog post
- get attachment
- list spaces
- create a new page
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Confluence Content Management\n  description: Unified workflow for managing Confluence content including pages, blog posts, comments, attachments, spaces,\n    and labels. Used by content authors, knowledge managers, and platform administrators.\n  tags:\n  - Confluence\n  - Content Management\n  - Collaboration\n  - Wiki\n  - Knowledge Base\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CONFLUENCE_API_TOKEN: CONFLUENCE_API_TOKEN\n    CONFLUENCE_EMAIL: CONFLUENCE_EMAIL\ncapability:\n  consumes:\n  - type: http\n    namespace: confluence-cloud-v2\n    baseUri: https://{domain}.atlassian.net/wiki/api/v2\n    description: Next generation Confluence Cloud REST API with improved performance and new features.\n    authentication:\n      type: basic\n      username: '{{CONFLUENCE_EMAIL}}'\n      password: '{{CONFLUENCE_API_TOKEN}}'\n    resources:\n    - name: pages\n      path: /pages\n      description:\
  \ Manage Confluence pages\n      operations:\n      - name: get-pages\n        method: GET\n        description: Returns all pages with optional filtering by space, status, and title.\n        inputParameters:\n        - name: space-id\n          in: query\n          type: string\n          required: false\n          description: Filter by space ID\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by page status\n        - name: title\n          in: query\n          type: string\n          required: false\n          description: Filter by page title\n        - name: body-format\n          in: query\n          type: string\n          required: false\n          description: Body format to return\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: limit\n          in: query\n          type: integer\n          required:\
  \ false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-page\n        method: POST\n        description: Creates a new page in a Confluence space.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            spaceId: '{{tools.space_id}}'\n            title: '{{tools.title}}'\n            body: '{{tools.body}}'\n    - name: page-by-id\n      path: /pages/{id}\n      description: Manage individual pages by ID\n      operations:\n      - name: get-page-by-id\n        method: GET\n        description: Returns a specific page by its ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The page\
  \ ID\n        - name: body-format\n          in: query\n          type: string\n          required: false\n          description: Body format to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-page\n        method: PUT\n        description: Updates a page by its ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The page ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            body: '{{tools.body}}'\n            version: '{{tools.version}}'\n      - name: delete-page\n        method: DELETE\n        description: Deletes a page by its ID.\n        inputParameters:\n        - name: id\n          in: path\n         \
  \ type: string\n          required: true\n          description: The page ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: child-pages\n      path: /pages/{id}/children\n      description: Retrieve child pages\n      operations:\n      - name: get-child-pages\n        method: GET\n        description: Returns child pages of a specific page.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The parent page ID\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: page-labels\n      path: /pages/{id}/labels\n      description: Manage page labels\n      operations:\n      - name: get-page-labels\n        method: GET\n        description: Returns labels for a specific page.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The page ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces\n      path: /spaces\n      description: Manage Confluence spaces\n      operations:\n      - name: get-spaces\n        method: GET\n        description: Returns all spaces with optional filtering.\n        inputParameters:\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description:\
  \ Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: space-by-id\n      path: /spaces/{id}\n      description: Retrieve a specific space\n      operations:\n      - name: get-space-by-id\n        method: GET\n        description: Returns a specific space by its ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The space ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pages-in-space\n      path: /spaces/{id}/pages\n      description: Retrieve pages within a space\n      operations:\n      - name: get-pages-in-space\n        method: GET\n        description: Returns pages belonging to a specific space.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n\
  \          required: true\n          description: The space ID\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comments\n      path: /comments/{id}\n      description: Manage comments\n      operations:\n      - name: get-comment-by-id\n        method: GET\n        description: Returns a specific comment by its ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The comment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-comment\n\
  \        method: PUT\n        description: Updates a comment by its ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The comment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            body: '{{tools.body}}'\n            version: '{{tools.version}}'\n      - name: delete-comment\n        method: DELETE\n        description: Deletes a comment by its ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The comment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: footer-comments\n      path: /footer-comments\n      description: Create footer comments\n      operations:\n    \
  \  - name: create-footer-comment\n        method: POST\n        description: Creates a footer comment on a page or blog post.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            pageId: '{{tools.page_id}}'\n            body: '{{tools.body}}'\n    - name: inline-comments\n      path: /inline-comments\n      description: Create inline comments\n      operations:\n      - name: create-inline-comment\n        method: POST\n        description: Creates an inline comment on a page.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            pageId: '{{tools.page_id}}'\n            body: '{{tools.body}}'\n            inlineCommentProperties: '{{tools.properties}}'\n\
  \    - name: page-footer-comments\n      path: /pages/{id}/footer-comments\n      description: Retrieve page footer comments\n      operations:\n      - name: get-footer-comments\n        method: GET\n        description: Returns footer comments for a specific page.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The page ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: page-inline-comments\n      path: /pages/{id}/inline-comments\n      description: Retrieve page inline comments\n      operations:\n      - name: get-inline-comments\n        method: GET\n        description: Returns inline comments for a specific page.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The page ID\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: child-comments\n      path: /comments/{id}/children\n      description: Retrieve child comments\n      operations:\n      - name: get-child-comments\n        method: GET\n        description: Returns child comments of a specific comment.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The parent comment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blog-posts\n      path: /blogposts\n      description: Manage blog posts\n      operations:\n      - name: get-blog-posts\n        method: GET\n        description: Returns all blog posts.\n        inputParameters:\n        - name: space-id\n          in: query\n          type: string\n          required: false\n          description: Filter by space\
  \ ID\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-blog-post\n        method: POST\n        description: Creates a new blog post.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            spaceId: '{{tools.space_id}}'\n            title: '{{tools.title}}'\n            body: '{{tools.body}}'\n    - name: blog-post-by-id\n      path: /blogposts/{id}\n      description: Manage individual blog posts\n      operations:\n      - name: get-blog-post-by-id\n\
  \        method: GET\n        description: Returns a specific blog post by its ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The blog post ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-blog-post\n        method: PUT\n        description: Updates a blog post by its ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The blog post ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            body: '{{tools.body}}'\n            version: '{{tools.version}}'\n      - name: delete-blog-post\n        method: DELETE\n        description:\
  \ Deletes a blog post by its ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The blog post ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: attachments\n      path: /attachments/{id}\n      description: Manage attachments\n      operations:\n      - name: get-attachment-by-id\n        method: GET\n        description: Returns a specific attachment by its ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The attachment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-attachment\n        method: DELETE\n        description: Deletes an attachment by its ID.\n        inputParameters:\n        - name: id\n    \
  \      in: path\n          type: string\n          required: true\n          description: The attachment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: page-attachments\n      path: /pages/{id}/attachments\n      description: Retrieve page attachments\n      operations:\n      - name: get-page-attachments\n        method: GET\n        description: Returns attachments for a specific page.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The page ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: labels\n      path: /labels/{id}\n      description: Retrieve label information\n      operations:\n      - name: get-label-by-id\n        method: GET\n        description: Returns a specific label by its ID.\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: string\n          required: true\n          description: The label ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: confluence-content-api\n    description: Unified REST API for Confluence content management workflows.\n    resources:\n    - path: /v1/pages\n      name: pages\n      description: Manage Confluence pages\n      operations:\n      - method: GET\n        name: list-pages\n        description: List all pages with optional filtering\n        call: confluence-cloud-v2.get-pages\n        with:\n          space-id: rest.space_id\n          status: rest.status\n          title: rest.title\n          cursor: rest.cursor\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-page\n        description:\
  \ Create a new page\n        call: confluence-cloud-v2.create-page\n        with:\n          space_id: rest.space_id\n          title: rest.title\n          body: rest.body\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages/{id}\n      name: page-by-id\n      description: Individual page operations\n      operations:\n      - method: GET\n        name: get-page\n        description: Get a page by ID\n        call: confluence-cloud-v2.get-page-by-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-page\n        description: Update a page\n        call: confluence-cloud-v2.update-page\n        with:\n          id: rest.id\n          title: rest.title\n          body: rest.body\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-page\n    \
  \    description: Delete a page\n        call: confluence-cloud-v2.delete-page\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages/{id}/children\n      name: child-pages\n      description: Child page navigation\n      operations:\n      - method: GET\n        name: list-child-pages\n        description: List child pages\n        call: confluence-cloud-v2.get-child-pages\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages/{id}/labels\n      name: page-labels\n      description: Page label management\n      operations:\n      - method: GET\n        name: get-page-labels\n        description: Get labels for a page\n        call: confluence-cloud-v2.get-page-labels\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages/{id}/attachments\n      name:\
  \ page-attachments\n      description: Page attachment management\n      operations:\n      - method: GET\n        name: list-page-attachments\n        description: List attachments for a page\n        call: confluence-cloud-v2.get-page-attachments\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages/{id}/comments\n      name: page-comments\n      description: Page comment management\n      operations:\n      - method: GET\n        name: list-footer-comments\n        description: List footer comments for a page\n        call: confluence-cloud-v2.get-footer-comments\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spaces\n      name: spaces\n      description: Manage Confluence spaces\n      operations:\n      - method: GET\n        name: list-spaces\n        description: List all spaces\n        call: confluence-cloud-v2.get-spaces\n\
  \        with:\n          cursor: rest.cursor\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spaces/{id}\n      name: space-by-id\n      description: Individual space operations\n      operations:\n      - method: GET\n        name: get-space\n        description: Get a space by ID\n        call: confluence-cloud-v2.get-space-by-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spaces/{id}/pages\n      name: space-pages\n      description: Pages within a space\n      operations:\n      - method: GET\n        name: list-pages-in-space\n        description: List pages in a space\n        call: confluence-cloud-v2.get-pages-in-space\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/blog-posts\n      name: blog-posts\n      description: Manage blog posts\n   \
  \   operations:\n      - method: GET\n        name: list-blog-posts\n        description: List all blog posts\n        call: confluence-cloud-v2.get-blog-posts\n        with:\n          space-id: rest.space_id\n          cursor: rest.cursor\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-blog-post\n        description: Create a new blog post\n        call: confluence-cloud-v2.create-blog-post\n        with:\n          space_id: rest.space_id\n          title: rest.title\n          body: rest.body\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/blog-posts/{id}\n      name: blog-post-by-id\n      description: Individual blog post operations\n      operations:\n      - method: GET\n        name: get-blog-post\n        description: Get a blog post by ID\n        call: confluence-cloud-v2.get-blog-post-by-id\n        with:\n          id: rest.id\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-blog-post\n        description: Update a blog post\n        call: confluence-cloud-v2.update-blog-post\n        with:\n          id: rest.id\n          title: rest.title\n          body: rest.body\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-blog-post\n        description: Delete a blog post\n        call: confluence-cloud-v2.delete-blog-post\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/comments/{id}\n      name: comments\n      description: Manage comments\n      operations:\n      - method: GET\n        name: get-comment\n        description: Get a comment by ID\n        call: confluence-cloud-v2.get-comment-by-id\n        with:\n          id: rest.id\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n      - method: PUT\n        name: update-comment\n        description: Update a comment\n        call: confluence-cloud-v2.update-comment\n        with:\n          id: rest.id\n          body: rest.body\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-comment\n        description: Delete a comment\n        call: confluence-cloud-v2.delete-comment\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/attachments/{id}\n      name: attachments\n      description: Manage attachments\n      operations:\n      - method: GET\n        name: get-attachment\n        description: Get an attachment by ID\n        call: confluence-cloud-v2.get-attachment-by-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n     \
  \ - method: DELETE\n        name: delete-attachment\n        description: Delete an attachment\n        call: confluence-cloud-v2.delete-attachment\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/labels/{id}\n      name: labels\n      description: Label information\n      operations:\n      - method: GET\n        name: get-label\n        description: Get a label by ID\n        call: confluence-cloud-v2.get-label-by-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: confluence-content-mcp\n    transport: http\n    description: MCP server for AI-assisted Confluence content management.\n    tools:\n    - name: list-pages\n      description: List all Confluence pages with optional filtering by space, status, and title.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: confluence-cloud-v2.get-pages\n\
  \      with:\n        space-id: tools.space_id\n        status: tools.status\n        title: tools.title\n        cursor: tools.cursor\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-page\n      description: Create a new Confluence page in a space.\n      hints:\n        readOnly: false\n      call: confluence-cloud-v2.create-page\n      with:\n        space_id: tools.space_id\n        title: tools.title\n        body: tools.body\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-page\n      description: Get a specific Confluence page by its ID.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: confluence-cloud-v2.get-page-by-id\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-page\n      description: Update an existing Confluence page title and body.\n      hints:\n        readOnly: false\n\
  \        idempotent: true\n      call: confluence-cloud-v2.update-page\n      with:\n        id: tools.id\n        title: tools.title\n        body: tools.body\n        version: tools.version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-page\n      description: Delete a Confluence page by ID.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: confluence-cloud-v2.delete-page\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-child-pages\n      description: List child pages of a specific page for navigating content hierarchies.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: confluence-cloud-v2.get-child-pages\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-page-labels\n      description: Get all labels applied to a specific\
  \ page.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: confluence-cloud-v2.get-page-labels\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-page-attachments\n      description: List all file attachments on a specific page.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: confluence-cloud-v2.get-page-attachments\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-spaces\n      description: List all Confluence spaces.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: confluence-cloud-v2.get-spaces\n      with:\n        cursor: tools.cursor\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-space\n      description: Get a specific Confluence space by its ID.\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: confluence-cloud-v2.get-space-by-id\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pages-in-space\n      description: List all pages belonging to a specific space.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: confluence-cloud-v2.get-pages-in-space\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-blog-posts\n      description: List all blog posts with optional space filtering.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: confluence-cloud-v2.get-blog-posts\n      with:\n        space-id: tools.space_id\n        cursor: tools.cursor\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-blog-post\n      description: Create a new Confluence blog post.\n      hints:\n        readOnly: false\n      call: confluence-cloud-v2.create-blog-post\n\
  \      with:\n        space_id: tools.space_id\n        title: tools.title\n        body: tools.body\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-blog-post\n      description: Get a specific blog post by its ID.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: confluence-cloud-v2.get-blog-post-by-id\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-blog-post\n      description: Update an existing blog post.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: confluence-cloud-v2.update-blog-post\n      with:\n        id: tools.id\n        title: tools.title\n        body: tools.body\n        version: tools.version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-blog-post\n      description: Delete a blog post by ID.\n      hints:\n        readOnly: false\n        destructive: true\n \
  \       idempotent: true\n      call: confluence-cloud-v2.delete-blog-post\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-comment\n      description: Get a specific comment by its ID.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: confluence-cloud-v2.get-comment-by-id\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-footer-comment\n      description: Create a footer comment on a page or blog post.\n      hints:\n        readOnly: false\n      call: confluence-cloud-v2.create-footer-comment\n      with:\n        page_id: tools.page_id\n        body: tools.body\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-inline-comment\n      description: Create an inline comment on a specific text selection in a page.\n      hints:\n        readOnly: false\n      call: confluence-cloud-v2.create-inline-comment\n\
  \      with:\n        page_id: tools.page_id\n        body: tools.body\n        properties: tools.properties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-comment\n      description: Update an existing comment.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: confluence-cloud-v2.update-comment\n      with:\n        id: tools.id\n        body: tools.body\n        version: tools.version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-comment\n      description: Delete a comment by ID.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: confluence-cloud-v2.delete-comment\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-footer-comments\n      description: List footer comments on a specific page.\n      hints:\n        readOnly: true\n        openWorld: true\n\
  \      call: confluence-cloud-v2.get-footer-comments\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-inline-comments\n      description: List inline comments on a specific page.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: confluence-cloud-v2.get-inline-comments\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-attachment\n      description: Get a specific attachment by its ID.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: confluence-cloud-v2.get-attachment-by-id\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-attachment\n      description: Delete an attachment by ID.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: confluence-cloud-v2.delete-attachment\n \
  \     with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-label\n      description: Get a specific label by its ID.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: confluence-cloud-v2.get-label-by-id\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/confluence/refs/heads/main/capabilities/content-management.yaml
tags:
- Confluence
- Content Management
- Collaboration
- Wiki
- Knowledge Base
tools:
- description: List all Confluence pages with optional filtering by space, status, and title.
  hints:
    openWorld: true
    readOnly: true
  name: list-pages
- description: Create a new Confluence page in a space.
  hints:
    readOnly: false
  name: create-page
- description: Get a specific Confluence page by its ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-page
- description: Update an existing Confluence page title and body.
  hints:
    idempotent: true
    readOnly: false
  name: update-page
- description: Delete a Confluence page by ID.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-page
- description: List child pages of a specific page for navigating content hierarchies.
  hints:
    openWorld: true
    readOnly: true
  name: list-child-pages
- description: Get all labels applied to a specific page.
  hints:
    openWorld: true
    readOnly: true
  name: get-page-labels
- description: List all file attachments on a specific page.
  hints:
    openWorld: true
    readOnly: true
  name: list-page-attachments
- description: List all Confluence spaces.
  hints:
    openWorld: true
    readOnly: true
  name: list-spaces
- description: Get a specific Confluence space by its ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-space
- description: List all pages belonging to a specific space.
  hints:
    openWorld: true
    readOnly: true
  name: list-pages-in-space
- description: List all blog posts with optional space filtering.
  hints:
    openWorld: true
    readOnly: true
  name: list-blog-posts
- description: Create a new Confluence blog post.
  hints:
    readOnly: false
  name: create-blog-post
- description: Get a specific blog post by its ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-blog-post
- description: Update an existing blog post.
  hints:
    idempotent: true
    readOnly: false
  name: update-blog-post
- description: Delete a blog post by ID.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-blog-post
- description: Get a specific comment by its ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-comment
- description: Create a footer comment on a page or blog post.
  hints:
    readOnly: false
  name: create-footer-comment
- description: Create an inline comment on a specific text selection in a page.
  hints:
    readOnly: false
  name: create-inline-comment
- description: Update an existing comment.
  hints:
    idempotent: true
    readOnly: false
  name: update-comment
- description: Delete a comment by ID.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-comment
- description: List footer comments on a specific page.
  hints:
    openWorld: true
    readOnly: true
  name: list-footer-comments
- description: List inline comments on a specific page.
  hints:
    openWorld: true
    readOnly: true
  name: list-inline-comments
- description: Get a specific attachment by its ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-attachment
- description: Delete an attachment by ID.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-attachment
- description: Get a specific label by its ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-label
---
