---
categories:
- content-management
consumed_apis:
- confluence-cloud-v2
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
- create a new confluence blog post.
- delete a confluence page by id.
- manage blog posts
- list all confluence spaces.
- update an existing blog post.
- list all confluence pages with optional filtering by space, status, and title.
- get comment
- delete page
- list all spaces
- list all blog posts with optional space filtering.
- manage comments
- knowledge base
- list page attachments
- update a blog post
- get a specific confluence page by its id.
- documentation
- delete blog post
- list child pages
- get a label by id
- get an attachment by id
- get a blog post by id
- get blog post
- update an existing confluence page title and body.
- list all blog posts
- manage attachments
- list all pages belonging to a specific space.
- get all labels applied to a specific page.
- create a footer comment on a page or blog post.
- delete a blog post
- manage confluence spaces
- page attachment management
- get labels for a page
- create a new page
- list spaces
- delete a blog post by id.
- get a page by id
- list pages in a space
- get attachment
- delete attachment
- delete an attachment by id.
- create an inline comment on a specific text selection in a page.
- page label management
- list inline comments on a specific page.
- get page
- child page navigation
- list footer comments on a specific page.
- update a page
- collaboration
- list all pages with optional filtering
- update blog post
- pages within a space
- delete an attachment
- list all file attachments on a specific page.
- get page labels
- list inline comments
- individual blog post operations
- page comment management
- create a new blog post
- delete a comment by id.
- confluence
- create footer comment
- list footer comments for a page
- get space
- list attachments for a page
- list blog posts
- delete a comment
- list pages
- create inline comment
- get a specific label by its id.
- get a specific confluence space by its id.
- create page
- delete a page
- get a specific comment by its id.
- label information
- get a space by id
- create a new confluence page in a space.
- get label
- individual page operations
- update page
- create blog post
- get a specific blog post by its id.
- list footer comments
- delete comment
- content management
- wiki
- manage confluence pages
- update comment
- update a comment
- update an existing comment.
- get a specific attachment by its id.
- list child pages of a specific page for navigating content hierarchies.
- individual space operations
- get a comment by id
- list pages in space
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Confluence Content Management\"\n  description: \"Unified workflow for managing Confluence content including pages, blog posts, comments, attachments, spaces, and labels. Used by content authors, knowledge managers, and platform administrators.\"\n  tags:\n    - Confluence\n    - Content Management\n    - Collaboration\n    - Wiki\n    - Knowledge Base\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      CONFLUENCE_API_TOKEN: CONFLUENCE_API_TOKEN\n      CONFLUENCE_EMAIL: CONFLUENCE_EMAIL\n\ncapability:\n  consumes:\n    - import: confluence-cloud-v2\n      location: ./shared/cloud-v2.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: confluence-content-api\n      description: \"Unified REST API for Confluence content management workflows.\"\n      resources:\n        - path: /v1/pages\n          name: pages\n          description: \"Manage Confluence pages\"\
  \n          operations:\n            - method: GET\n              name: list-pages\n              description: \"List all pages with optional filtering\"\n              call: \"confluence-cloud-v2.get-pages\"\n              with:\n                space-id: \"rest.space_id\"\n                status: \"rest.status\"\n                title: \"rest.title\"\n                cursor: \"rest.cursor\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-page\n              description: \"Create a new page\"\n              call: \"confluence-cloud-v2.create-page\"\n              with:\n                space_id: \"rest.space_id\"\n                title: \"rest.title\"\n                body: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages/{id}\n          name: page-by-id\n\
  \          description: \"Individual page operations\"\n          operations:\n            - method: GET\n              name: get-page\n              description: \"Get a page by ID\"\n              call: \"confluence-cloud-v2.get-page-by-id\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-page\n              description: \"Update a page\"\n              call: \"confluence-cloud-v2.update-page\"\n              with:\n                id: \"rest.id\"\n                title: \"rest.title\"\n                body: \"rest.body\"\n                version: \"rest.version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-page\n              description: \"Delete a page\"\n              call: \"confluence-cloud-v2.delete-page\"\n\
  \              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages/{id}/children\n          name: child-pages\n          description: \"Child page navigation\"\n          operations:\n            - method: GET\n              name: list-child-pages\n              description: \"List child pages\"\n              call: \"confluence-cloud-v2.get-child-pages\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages/{id}/labels\n          name: page-labels\n          description: \"Page label management\"\n          operations:\n            - method: GET\n              name: get-page-labels\n              description: \"Get labels for a page\"\n              call: \"confluence-cloud-v2.get-page-labels\"\n              with:\n                id: \"rest.id\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages/{id}/attachments\n          name: page-attachments\n          description: \"Page attachment management\"\n          operations:\n            - method: GET\n              name: list-page-attachments\n              description: \"List attachments for a page\"\n              call: \"confluence-cloud-v2.get-page-attachments\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pages/{id}/comments\n          name: page-comments\n          description: \"Page comment management\"\n          operations:\n            - method: GET\n              name: list-footer-comments\n              description: \"List footer comments for a page\"\n              call: \"confluence-cloud-v2.get-footer-comments\"\n              with:\n                id: \"rest.id\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/spaces\n          name: spaces\n          description: \"Manage Confluence spaces\"\n          operations:\n            - method: GET\n              name: list-spaces\n              description: \"List all spaces\"\n              call: \"confluence-cloud-v2.get-spaces\"\n              with:\n                cursor: \"rest.cursor\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/spaces/{id}\n          name: space-by-id\n          description: \"Individual space operations\"\n          operations:\n            - method: GET\n              name: get-space\n              description: \"Get a space by ID\"\n              call: \"confluence-cloud-v2.get-space-by-id\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n       \
  \         - type: object\n                  mapping: \"$.\"\n        - path: /v1/spaces/{id}/pages\n          name: space-pages\n          description: \"Pages within a space\"\n          operations:\n            - method: GET\n              name: list-pages-in-space\n              description: \"List pages in a space\"\n              call: \"confluence-cloud-v2.get-pages-in-space\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/blog-posts\n          name: blog-posts\n          description: \"Manage blog posts\"\n          operations:\n            - method: GET\n              name: list-blog-posts\n              description: \"List all blog posts\"\n              call: \"confluence-cloud-v2.get-blog-posts\"\n              with:\n                space-id: \"rest.space_id\"\n                cursor: \"rest.cursor\"\n                limit: \"rest.limit\"\n       \
  \       outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-blog-post\n              description: \"Create a new blog post\"\n              call: \"confluence-cloud-v2.create-blog-post\"\n              with:\n                space_id: \"rest.space_id\"\n                title: \"rest.title\"\n                body: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/blog-posts/{id}\n          name: blog-post-by-id\n          description: \"Individual blog post operations\"\n          operations:\n            - method: GET\n              name: get-blog-post\n              description: \"Get a blog post by ID\"\n              call: \"confluence-cloud-v2.get-blog-post-by-id\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n            - method: PUT\n              name: update-blog-post\n              description: \"Update a blog post\"\n              call: \"confluence-cloud-v2.update-blog-post\"\n              with:\n                id: \"rest.id\"\n                title: \"rest.title\"\n                body: \"rest.body\"\n                version: \"rest.version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-blog-post\n              description: \"Delete a blog post\"\n              call: \"confluence-cloud-v2.delete-blog-post\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/comments/{id}\n          name: comments\n          description: \"Manage comments\"\n          operations:\n            - method: GET\n              name: get-comment\n              description:\
  \ \"Get a comment by ID\"\n              call: \"confluence-cloud-v2.get-comment-by-id\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-comment\n              description: \"Update a comment\"\n              call: \"confluence-cloud-v2.update-comment\"\n              with:\n                id: \"rest.id\"\n                body: \"rest.body\"\n                version: \"rest.version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-comment\n              description: \"Delete a comment\"\n              call: \"confluence-cloud-v2.delete-comment\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/attachments/{id}\n\
  \          name: attachments\n          description: \"Manage attachments\"\n          operations:\n            - method: GET\n              name: get-attachment\n              description: \"Get an attachment by ID\"\n              call: \"confluence-cloud-v2.get-attachment-by-id\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-attachment\n              description: \"Delete an attachment\"\n              call: \"confluence-cloud-v2.delete-attachment\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/labels/{id}\n          name: labels\n          description: \"Label information\"\n          operations:\n            - method: GET\n              name: get-label\n              description: \"Get a label\
  \ by ID\"\n              call: \"confluence-cloud-v2.get-label-by-id\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: confluence-content-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Confluence content management.\"\n      tools:\n        - name: list-pages\n          description: \"List all Confluence pages with optional filtering by space, status, and title.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"confluence-cloud-v2.get-pages\"\n          with:\n            space-id: \"tools.space_id\"\n            status: \"tools.status\"\n            title: \"tools.title\"\n            cursor: \"tools.cursor\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-page\n\
  \          description: \"Create a new Confluence page in a space.\"\n          hints:\n            readOnly: false\n          call: \"confluence-cloud-v2.create-page\"\n          with:\n            space_id: \"tools.space_id\"\n            title: \"tools.title\"\n            body: \"tools.body\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-page\n          description: \"Get a specific Confluence page by its ID.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"confluence-cloud-v2.get-page-by-id\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-page\n          description: \"Update an existing Confluence page title and body.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"confluence-cloud-v2.update-page\"\n          with:\n\
  \            id: \"tools.id\"\n            title: \"tools.title\"\n            body: \"tools.body\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-page\n          description: \"Delete a Confluence page by ID.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"confluence-cloud-v2.delete-page\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-child-pages\n          description: \"List child pages of a specific page for navigating content hierarchies.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"confluence-cloud-v2.get-child-pages\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: get-page-labels\n          description: \"Get all labels applied to a specific page.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"confluence-cloud-v2.get-page-labels\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-page-attachments\n          description: \"List all file attachments on a specific page.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"confluence-cloud-v2.get-page-attachments\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-spaces\n          description: \"List all Confluence spaces.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"confluence-cloud-v2.get-spaces\"\n          with:\n    \
  \        cursor: \"tools.cursor\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-space\n          description: \"Get a specific Confluence space by its ID.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"confluence-cloud-v2.get-space-by-id\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pages-in-space\n          description: \"List all pages belonging to a specific space.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"confluence-cloud-v2.get-pages-in-space\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-blog-posts\n          description: \"List all blog posts with optional space\
  \ filtering.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"confluence-cloud-v2.get-blog-posts\"\n          with:\n            space-id: \"tools.space_id\"\n            cursor: \"tools.cursor\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-blog-post\n          description: \"Create a new Confluence blog post.\"\n          hints:\n            readOnly: false\n          call: \"confluence-cloud-v2.create-blog-post\"\n          with:\n            space_id: \"tools.space_id\"\n            title: \"tools.title\"\n            body: \"tools.body\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-blog-post\n          description: \"Get a specific blog post by its ID.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"confluence-cloud-v2.get-blog-post-by-id\"\
  \n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-blog-post\n          description: \"Update an existing blog post.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"confluence-cloud-v2.update-blog-post\"\n          with:\n            id: \"tools.id\"\n            title: \"tools.title\"\n            body: \"tools.body\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-blog-post\n          description: \"Delete a blog post by ID.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"confluence-cloud-v2.delete-blog-post\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n \
  \       - name: get-comment\n          description: \"Get a specific comment by its ID.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"confluence-cloud-v2.get-comment-by-id\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-footer-comment\n          description: \"Create a footer comment on a page or blog post.\"\n          hints:\n            readOnly: false\n          call: \"confluence-cloud-v2.create-footer-comment\"\n          with:\n            page_id: \"tools.page_id\"\n            body: \"tools.body\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-inline-comment\n          description: \"Create an inline comment on a specific text selection in a page.\"\n          hints:\n            readOnly: false\n          call: \"confluence-cloud-v2.create-inline-comment\"\
  \n          with:\n            page_id: \"tools.page_id\"\n            body: \"tools.body\"\n            properties: \"tools.properties\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-comment\n          description: \"Update an existing comment.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"confluence-cloud-v2.update-comment\"\n          with:\n            id: \"tools.id\"\n            body: \"tools.body\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-comment\n          description: \"Delete a comment by ID.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"confluence-cloud-v2.delete-comment\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: list-footer-comments\n          description: \"List footer comments on a specific page.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"confluence-cloud-v2.get-footer-comments\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-inline-comments\n          description: \"List inline comments on a specific page.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"confluence-cloud-v2.get-inline-comments\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-attachment\n          description: \"Get a specific attachment by its ID.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"confluence-cloud-v2.get-attachment-by-id\"\
  \n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-attachment\n          description: \"Delete an attachment by ID.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"confluence-cloud-v2.delete-attachment\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-label\n          description: \"Get a specific label by its ID.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"confluence-cloud-v2.get-label-by-id\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
