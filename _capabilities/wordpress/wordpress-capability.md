---
categories: []
consumed_apis: []
description: The WordPress REST API provides endpoints for WordPress data types that allow developers to interact with sites remotely by sending and receiving JSON objects. It is the backbone of the WordPress Block Editor and enables headless CMS, mobile apps, and third-party integrations.
layout: capability
name: WordPress REST API
operations:
- description: WordPress List Posts
  method: GET
  name: listposts
  path: /wp/v2/posts
- description: WordPress Create Post
  method: POST
  name: createpost
  path: /wp/v2/posts
- description: WordPress Get Post
  method: GET
  name: getpost
  path: /wp/v2/posts/{id}
- description: WordPress Update Post
  method: PUT
  name: updatepost
  path: /wp/v2/posts/{id}
- description: WordPress Delete Post
  method: DELETE
  name: deletepost
  path: /wp/v2/posts/{id}
- description: WordPress List Pages
  method: GET
  name: listpages
  path: /wp/v2/pages
- description: WordPress Create Page
  method: POST
  name: createpage
  path: /wp/v2/pages
- description: WordPress Get Page
  method: GET
  name: getpage
  path: /wp/v2/pages/{id}
- description: WordPress List Media
  method: GET
  name: listmedia
  path: /wp/v2/media
- description: WordPress Get Media Item
  method: GET
  name: getmedia
  path: /wp/v2/media/{id}
- description: WordPress List Comments
  method: GET
  name: listcomments
  path: /wp/v2/comments
- description: WordPress Create Comment
  method: POST
  name: createcomment
  path: /wp/v2/comments
- description: WordPress List Users
  method: GET
  name: listusers
  path: /wp/v2/users
- description: WordPress Get User
  method: GET
  name: getuser
  path: /wp/v2/users/{id}
- description: WordPress List Categories
  method: GET
  name: listcategories
  path: /wp/v2/categories
- description: WordPress Create Category
  method: POST
  name: createcategory
  path: /wp/v2/categories
- description: WordPress List Tags
  method: GET
  name: listtags
  path: /wp/v2/tags
- description: WordPress Search Content
  method: GET
  name: searchcontent
  path: /wp/v2/search
- description: WordPress Get Settings
  method: GET
  name: getsettings
  path: /wp/v2/settings
- description: WordPress List Themes
  method: GET
  name: listthemes
  path: /wp/v2/themes
- description: WordPress List Plugins
  method: GET
  name: listplugins
  path: /wp/v2/plugins
- description: WordPress List Post Types
  method: GET
  name: listposttypes
  path: /wp/v2/types
- description: WordPress List Reusable Blocks
  method: GET
  name: listblocks
  path: /wp/v2/blocks
- description: WordPress List Block Types
  method: GET
  name: listblocktypes
  path: /wp/v2/block-types
personas: []
provider_name: WordPress
provider_slug: wordpress
search_terms:
- getpost
- wordpress get media item
- wordpress get user
- listcategories
- wordpress list comments
- createcomment
- listmedia
- api
- wordpress update post
- updatepost
- wordpress list media
- wordpress create category
- wordpress get page
- wordpress list plugins
- listblocks
- listblocktypes
- wordpress create page
- getmedia
- wordpress search content
- listposttypes
- open source
- createpost
- listcomments
- getuser
- listtags
- listpages
- wordpress create post
- cms
- wordpress get post
- listthemes
- createpage
- getsettings
- wordpress list pages
- wordpress
- wordpress list categories
- listplugins
- listposts
- wordpress get settings
- wordpress list themes
- content management
- getpage
- wordpress list post types
- listusers
- wordpress delete post
- wordpress list block types
- wordpress list users
- searchcontent
- deletepost
- wordpress create comment
- wordpress list tags
- wordpress list reusable blocks
- createcategory
- wordpress list posts
slug: wordpress-capability
source_filename: wordpress-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WordPress REST API\n  description: The WordPress REST API provides endpoints for WordPress data types that allow developers to interact with sites\n    remotely by sending and receiving JSON objects. It is the backbone of the WordPress Block Editor and enables headless\n    CMS, mobile apps, and third-party integrations.\n  tags:\n  - Wordpress\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: wordpress\n    baseUri: https://example.com/wp-json\n    description: WordPress REST API HTTP API.\n    authentication:\n      type: apikey\n      in: cookie\n      name: wordpress_logged_in\n      value: '{{WORDPRESS_TOKEN}}'\n    resources:\n    - name: wp-v2-posts\n      path: /wp/v2/posts\n      operations:\n      - name: listposts\n        method: GET\n        description: WordPress List Posts\n        inputParameters:\n        - name: context\n          in: query\n        \
  \  type: string\n          description: Scope under which the request is made; determines fields present in response.\n        - name: page\n          in: query\n          type: integer\n          description: Current page of the collection.\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of items to be returned in result set.\n        - name: search\n          in: query\n          type: string\n          description: Limit results to those matching a string.\n        - name: status\n          in: query\n          type: string\n          description: Limit result set to posts assigned one or more statuses.\n        - name: author\n          in: query\n          type: array\n          description: Limit result set to posts assigned to specific authors.\n        - name: categories\n          in: query\n          type: array\n          description: Limit result set to items with specific terms assigned in the categories taxonomy.\n\
  \        - name: tags\n          in: query\n          type: array\n          description: Limit result set to items with specific terms assigned in the tags taxonomy.\n        - name: orderby\n          in: query\n          type: string\n          description: Sort collection by object attribute.\n        - name: order\n          in: query\n          type: string\n          description: Order sort attribute ascending or descending.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpost\n        method: POST\n        description: WordPress Create Post\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-posts-id\n      path: /wp/v2/posts/{id}\n      operations:\n      - name: getpost\n        method: GET\n        description: WordPress Get Post\n        inputParameters:\n        - name: id\n       \
  \   in: path\n          type: integer\n          required: true\n          description: Unique identifier for the post.\n        - name: context\n          in: query\n          type: string\n          description: Scope under which the request is made.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepost\n        method: PUT\n        description: WordPress Update Post\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier for the post.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepost\n        method: DELETE\n        description: WordPress Delete Post\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description:\
  \ Unique identifier for the post.\n        - name: force\n          in: query\n          type: boolean\n          description: Whether to bypass trash and force deletion.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-pages\n      path: /wp/v2/pages\n      operations:\n      - name: listpages\n        method: GET\n        description: WordPress List Pages\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Current page of the collection.\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of items to be returned.\n        - name: status\n          in: query\n          type: string\n          description: Limit result set to pages with a specific status.\n        - name: parent\n          in: query\n          type: integer\n          description: Limit result set to\
  \ pages with a specific parent ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpage\n        method: POST\n        description: WordPress Create Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-pages-id\n      path: /wp/v2/pages/{id}\n      operations:\n      - name: getpage\n        method: GET\n        description: WordPress Get Page\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier for the page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-media\n      path: /wp/v2/media\n      operations:\n      - name: listmedia\n        method: GET\n        description: WordPress List Media\n\
  \        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Current page of the collection.\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of items to be returned.\n        - name: media_type\n          in: query\n          type: string\n          description: Limit result set to attachments of a particular media type.\n        - name: mime_type\n          in: query\n          type: string\n          description: Limit result set to attachments of a specific MIME type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-media-id\n      path: /wp/v2/media/{id}\n      operations:\n      - name: getmedia\n        method: GET\n        description: WordPress Get Media Item\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required:\
  \ true\n          description: Unique identifier for the media item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-comments\n      path: /wp/v2/comments\n      operations:\n      - name: listcomments\n        method: GET\n        description: WordPress List Comments\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Current page of the collection.\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of items to be returned.\n        - name: post\n          in: query\n          type: array\n          description: Limit result set to comments assigned to specific post IDs.\n        - name: status\n          in: query\n          type: string\n          description: Limit result set to comments assigned a specific status.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createcomment\n        method: POST\n        description: WordPress Create Comment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-users\n      path: /wp/v2/users\n      operations:\n      - name: listusers\n        method: GET\n        description: WordPress List Users\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Current page of the collection.\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of items to be returned.\n        - name: roles\n          in: query\n          type: array\n          description: Limit result set to users matching at least one specific role.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: wp-v2-users-id\n      path: /wp/v2/users/{id}\n      operations:\n      - name: getuser\n        method: GET\n        description: WordPress Get User\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier for the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-categories\n      path: /wp/v2/categories\n      operations:\n      - name: listcategories\n        method: GET\n        description: WordPress List Categories\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Current page of the collection.\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of items.\n        - name: search\n          in: query\n          type: string\n\
  \          description: Limit results to matching categories.\n        - name: hide_empty\n          in: query\n          type: boolean\n          description: Whether to hide terms not assigned to any posts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcategory\n        method: POST\n        description: WordPress Create Category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-tags\n      path: /wp/v2/tags\n      operations:\n      - name: listtags\n        method: GET\n        description: WordPress List Tags\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Current page of the collection.\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of items.\n        -\
  \ name: search\n          in: query\n          type: string\n          description: Limit results to matching tags.\n        - name: hide_empty\n          in: query\n          type: boolean\n          description: Whether to hide terms not assigned to any posts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-search\n      path: /wp/v2/search\n      operations:\n      - name: searchcontent\n        method: GET\n        description: WordPress Search Content\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: true\n          description: Limit results to those matching a string.\n        - name: type\n          in: query\n          type: string\n          description: Limit results to items of an object type.\n        - name: subtype\n          in: query\n          type: string\n          description: Limit results to items of one\
  \ or more object subtypes.\n        - name: page\n          in: query\n          type: integer\n          description: Current page of the collection.\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of items to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-settings\n      path: /wp/v2/settings\n      operations:\n      - name: getsettings\n        method: GET\n        description: WordPress Get Settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-themes\n      path: /wp/v2/themes\n      operations:\n      - name: listthemes\n        method: GET\n        description: WordPress List Themes\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Limit result\
  \ set to themes assigned one or more statuses.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-plugins\n      path: /wp/v2/plugins\n      operations:\n      - name: listplugins\n        method: GET\n        description: WordPress List Plugins\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-types\n      path: /wp/v2/types\n      operations:\n      - name: listposttypes\n        method: GET\n        description: WordPress List Post Types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-blocks\n      path: /wp/v2/blocks\n      operations:\n      - name: listblocks\n        method: GET\n        description: WordPress List Reusable Blocks\n        inputParameters:\n        - name: page\n          in: query\n\
  \          type: integer\n          description: Current page of the collection.\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of items.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wp-v2-block-types\n      path: /wp/v2/block-types\n      operations:\n      - name: listblocktypes\n        method: GET\n        description: WordPress List Block Types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: wordpress-rest\n    description: REST adapter for WordPress REST API.\n    resources:\n    - path: /wp/v2/posts\n      name: listposts\n      operations:\n      - method: GET\n        name: listposts\n        description: WordPress List Posts\n        call: wordpress.listposts\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /wp/v2/posts\n      name: createpost\n      operations:\n      - method: POST\n        name: createpost\n        description: WordPress Create Post\n        call: wordpress.createpost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/posts/{id}\n      name: getpost\n      operations:\n      - method: GET\n        name: getpost\n        description: WordPress Get Post\n        call: wordpress.getpost\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/posts/{id}\n      name: updatepost\n      operations:\n      - method: PUT\n        name: updatepost\n        description: WordPress Update Post\n        call: wordpress.updatepost\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/posts/{id}\n      name: deletepost\n      operations:\n\
  \      - method: DELETE\n        name: deletepost\n        description: WordPress Delete Post\n        call: wordpress.deletepost\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/pages\n      name: listpages\n      operations:\n      - method: GET\n        name: listpages\n        description: WordPress List Pages\n        call: wordpress.listpages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/pages\n      name: createpage\n      operations:\n      - method: POST\n        name: createpage\n        description: WordPress Create Page\n        call: wordpress.createpage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/pages/{id}\n      name: getpage\n      operations:\n      - method: GET\n        name: getpage\n        description: WordPress Get Page\n        call: wordpress.getpage\n        with:\n          id: rest.id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/media\n      name: listmedia\n      operations:\n      - method: GET\n        name: listmedia\n        description: WordPress List Media\n        call: wordpress.listmedia\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/media/{id}\n      name: getmedia\n      operations:\n      - method: GET\n        name: getmedia\n        description: WordPress Get Media Item\n        call: wordpress.getmedia\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/comments\n      name: listcomments\n      operations:\n      - method: GET\n        name: listcomments\n        description: WordPress List Comments\n        call: wordpress.listcomments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/comments\n      name: createcomment\n      operations:\n\
  \      - method: POST\n        name: createcomment\n        description: WordPress Create Comment\n        call: wordpress.createcomment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: WordPress List Users\n        call: wordpress.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/users/{id}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: WordPress Get User\n        call: wordpress.getuser\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/categories\n      name: listcategories\n      operations:\n      - method: GET\n        name: listcategories\n        description: WordPress List Categories\n        call: wordpress.listcategories\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/categories\n      name: createcategory\n      operations:\n      - method: POST\n        name: createcategory\n        description: WordPress Create Category\n        call: wordpress.createcategory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/tags\n      name: listtags\n      operations:\n      - method: GET\n        name: listtags\n        description: WordPress List Tags\n        call: wordpress.listtags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/search\n      name: searchcontent\n      operations:\n      - method: GET\n        name: searchcontent\n        description: WordPress Search Content\n        call: wordpress.searchcontent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/settings\n      name: getsettings\n      operations:\n      - method: GET\n\
  \        name: getsettings\n        description: WordPress Get Settings\n        call: wordpress.getsettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/themes\n      name: listthemes\n      operations:\n      - method: GET\n        name: listthemes\n        description: WordPress List Themes\n        call: wordpress.listthemes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/plugins\n      name: listplugins\n      operations:\n      - method: GET\n        name: listplugins\n        description: WordPress List Plugins\n        call: wordpress.listplugins\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/types\n      name: listposttypes\n      operations:\n      - method: GET\n        name: listposttypes\n        description: WordPress List Post Types\n        call: wordpress.listposttypes\n        outputParameters:\n        - type: object\n        \
  \  mapping: $.\n    - path: /wp/v2/blocks\n      name: listblocks\n      operations:\n      - method: GET\n        name: listblocks\n        description: WordPress List Reusable Blocks\n        call: wordpress.listblocks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wp/v2/block-types\n      name: listblocktypes\n      operations:\n      - method: GET\n        name: listblocktypes\n        description: WordPress List Block Types\n        call: wordpress.listblocktypes\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: wordpress-mcp\n    transport: http\n    description: MCP adapter for WordPress REST API for AI agent use.\n    tools:\n    - name: listposts\n      description: WordPress List Posts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: wordpress.listposts\n      with:\n        context: tools.context\n        page:\
  \ tools.page\n        per_page: tools.per_page\n        search: tools.search\n        status: tools.status\n        author: tools.author\n        categories: tools.categories\n        tags: tools.tags\n        orderby: tools.orderby\n        order: tools.order\n      inputParameters:\n      - name: context\n        type: string\n        description: Scope under which the request is made; determines fields present in response.\n      - name: page\n        type: integer\n        description: Current page of the collection.\n      - name: per_page\n        type: integer\n        description: Maximum number of items to be returned in result set.\n      - name: search\n        type: string\n        description: Limit results to those matching a string.\n      - name: status\n        type: string\n        description: Limit result set to posts assigned one or more statuses.\n      - name: author\n        type: array\n        description: Limit result set to posts assigned to specific authors.\n\
  \      - name: categories\n        type: array\n        description: Limit result set to items with specific terms assigned in the categories taxonomy.\n      - name: tags\n        type: array\n        description: Limit result set to items with specific terms assigned in the tags taxonomy.\n      - name: orderby\n        type: string\n        description: Sort collection by object attribute.\n      - name: order\n        type: string\n        description: Order sort attribute ascending or descending.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpost\n      description: WordPress Create Post\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: wordpress.createpost\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpost\n      description: WordPress Get Post\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ wordpress.getpost\n      with:\n        id: tools.id\n        context: tools.context\n      inputParameters:\n      - name: id\n        type: integer\n        description: Unique identifier for the post.\n        required: true\n      - name: context\n        type: string\n        description: Scope under which the request is made.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepost\n      description: WordPress Update Post\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: wordpress.updatepost\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: Unique identifier for the post.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletepost\n      description: WordPress Delete Post\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n\
  \      call: wordpress.deletepost\n      with:\n        id: tools.id\n        force: tools.force\n      inputParameters:\n      - name: id\n        type: integer\n        description: Unique identifier for the post.\n        required: true\n      - name: force\n        type: boolean\n        description: Whether to bypass trash and force deletion.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpages\n      description: WordPress List Pages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: wordpress.listpages\n      with:\n        page: tools.page\n        per_page: tools.per_page\n        status: tools.status\n        parent: tools.parent\n      inputParameters:\n      - name: page\n        type: integer\n        description: Current page of the collection.\n      - name: per_page\n        type: integer\n        description: Maximum number of items to be returned.\n      - name: status\n      \
  \  type: string\n        description: Limit result set to pages with a specific status.\n      - name: parent\n        type: integer\n        description: Limit result set to pages with a specific parent ID.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpage\n      description: WordPress Create Page\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: wordpress.createpage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpage\n      description: WordPress Get Page\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: wordpress.getpage\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: Unique identifier for the page.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmedia\n      description:\
  \ WordPress List Media\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: wordpress.listmedia\n      with:\n        page: tools.page\n        per_page: tools.per_page\n        media_type: tools.media_type\n        mime_type: tools.mime_type\n      inputParameters:\n      - name: page\n        type: integer\n        description: Current page of the collection.\n      - name: per_page\n        type: integer\n        description: Maximum number of items to be returned.\n      - name: media_type\n        type: string\n        description: Limit result set to attachments of a particular media type.\n      - name: mime_type\n        type: string\n        description: Limit result set to attachments of a specific MIME type.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmedia\n      description: WordPress Get Media Item\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: wordpress.getmedia\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: Unique identifier for the media item.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcomments\n      description: WordPress List Comments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: wordpress.listcomments\n      with:\n        page: tools.page\n        per_page: tools.per_page\n        post: tools.post\n        status: tools.status\n      inputParameters:\n      - name: page\n        type: integer\n        description: Current page of the collection.\n      - name: per_page\n        type: integer\n        description: Maximum number of items to be returned.\n      - name: post\n        type: array\n        description: Limit result set to comments assigned to specific post IDs.\n      - name: status\n     \
  \   type: string\n        description: Limit result set to comments assigned a specific status.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcomment\n      description: WordPress Create Comment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: wordpress.createcomment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: WordPress List Users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: wordpress.listusers\n      with:\n        page: tools.page\n        per_page: tools.per_page\n        roles: tools.roles\n      inputParameters:\n      - name: page\n        type: integer\n        description: Current page of the collection.\n      - name: per_page\n        type: integer\n        description: Maximum number of items to be returned.\n      - name: roles\n        type: array\n \
  \       description: Limit result set to users matching at least one specific role.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: WordPress Get User\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: wordpress.getuser\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: Unique identifier for the user.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcategories\n      description: WordPress List Categories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: wordpress.listcategories\n      with:\n        page: tools.page\n        per_page: tools.per_page\n        search: tools.search\n        hide_empty: tools.hide_empty\n      inputParameters:\n      - name: page\n        type: integer\n     \
  \   description: Current page of the collection.\n      - name: per_page\n        type: integer\n        description: Maximum number of items.\n      - name: search\n        type: string\n        description: Limit results to matching categories.\n      - name: hide_empty\n        type: boolean\n        description: Whether to hide terms not assigned to any posts.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcategory\n      description: WordPress Create Category\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: wordpress.createcategory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtags\n      description: WordPress List Tags\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: wordpress.listtags\n      with:\n        page: tools.page\n        per_page: tools.per_page\n        search: tools.search\n\
  \        hide_empty: tools.hide_empty\n      inputParameters:\n      - name: page\n        type: integer\n        description: Current page of the collection.\n      - name: per_page\n        type: integer\n        description: Maximum number of items.\n      - name: search\n        type: string\n        description: Limit results to matching tags.\n      - name: hide_empty\n        type: boolean\n        description: Whether to hide terms not assigned to any posts.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchcontent\n      description: WordPress Search Content\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: wordpress.searchcontent\n      with:\n        search: tools.search\n        type: tools.type\n        subtype: tools.subtype\n        page: tools.page\n        per_page: tools.per_page\n      inputParameters:\n      - name: search\n        type: string\n        description: Limit results\
  \ to those matching a string.\n        required: true\n      - name: type\n        type: string\n        description: Limit results to items of an object type.\n      - name: subtype\n        type: string\n        description: Limit results to items of one or more object subtypes.\n      - name: page\n        type: integer\n        description: Current page of the collection.\n      - name: per_page\n        type: integer\n        description: Maximum number of items to return.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsettings\n      description: WordPress Get Settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: wordpress.getsettings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listthemes\n      description: WordPress List Themes\n      hints:\n    \n\n# --- truncated at 32 KB (33 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/wordpress/refs/heads/main/capabilities/wordpress-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/wordpress/refs/heads/main/capabilities/wordpress-capability.yaml
tags:
- Wordpress
- API
tools:
- description: WordPress List Posts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listposts
- description: WordPress Create Post
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpost
- description: WordPress Get Post
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpost
- description: WordPress Update Post
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepost
- description: WordPress Delete Post
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepost
- description: WordPress List Pages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpages
- description: WordPress Create Page
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpage
- description: WordPress Get Page
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpage
- description: WordPress List Media
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmedia
- description: WordPress Get Media Item
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmedia
- description: WordPress List Comments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcomments
- description: WordPress Create Comment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcomment
- description: WordPress List Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: WordPress Get User
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: WordPress List Categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcategories
- description: WordPress Create Category
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcategory
- description: WordPress List Tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtags
- description: WordPress Search Content
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcontent
- description: WordPress Get Settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsettings
- description: WordPress List Themes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listthemes
- description: WordPress List Plugins
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listplugins
- description: WordPress List Post Types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listposttypes
- description: WordPress List Reusable Blocks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listblocks
- description: WordPress List Block Types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listblocktypes
---
