---
categories: []
consumed_apis: []
description: The Blogger API v3 allows you to create, read, update, and delete Blogger resources including blogs, posts, pages, comments, and users. You can integrate Blogger content into your application using RESTful operations.
layout: capability
name: Google Blogger API
operations:
- description: Get a blog
  method: GET
  name: getblog
  path: /blogs/{blogId}
- description: Get a blog by URL
  method: GET
  name: getblogbyurl
  path: /blogs/byurl
- description: List blogs by user
  method: GET
  name: listblogsbyuser
  path: /users/{userId}/blogs
- description: List posts
  method: GET
  name: listposts
  path: /blogs/{blogId}/posts
- description: Create a post
  method: POST
  name: insertpost
  path: /blogs/{blogId}/posts
- description: Get a post
  method: GET
  name: getpost
  path: /blogs/{blogId}/posts/{postId}
- description: Update a post
  method: PUT
  name: updatepost
  path: /blogs/{blogId}/posts/{postId}
- description: Patch a post
  method: PATCH
  name: patchpost
  path: /blogs/{blogId}/posts/{postId}
- description: Delete a post
  method: DELETE
  name: deletepost
  path: /blogs/{blogId}/posts/{postId}
- description: Search posts
  method: GET
  name: searchposts
  path: /blogs/{blogId}/posts/search
- description: List pages
  method: GET
  name: listpages
  path: /blogs/{blogId}/pages
- description: Create a page
  method: POST
  name: insertpage
  path: /blogs/{blogId}/pages
- description: List comments
  method: GET
  name: listcomments
  path: /blogs/{blogId}/posts/{postId}/comments
- description: Get a comment
  method: GET
  name: getcomment
  path: /blogs/{blogId}/posts/{postId}/comments/{commentId}
- description: Delete a comment
  method: DELETE
  name: deletecomment
  path: /blogs/{blogId}/posts/{postId}/comments/{commentId}
- description: Get a user
  method: GET
  name: getuser
  path: /users/{userId}
personas: []
provider_name: Google Blogger
provider_slug: google-blogger
search_terms:
- get a post
- update a post
- getpost
- patch a post
- api
- getblog
- updatepost
- pages
- publishing
- getcomment
- get a blog
- deletecomment
- getblogbyurl
- comments
- blogging
- google
- listcomments
- getuser
- blogger
- listpages
- list comments
- get a user
- create a page
- cms
- delete a comment
- get a blog by url
- delete a post
- searchposts
- insertpage
- list posts
- insertpost
- listposts
- list pages
- create a post
- listblogsbyuser
- patchpost
- posts
- list blogs by user
- deletepost
- get a comment
- search posts
slug: google-blogger-capability
source_filename: google-blogger-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Blogger API\n  description: The Blogger API v3 allows you to create, read, update, and delete Blogger resources including blogs, posts,\n    pages, comments, and users. You can integrate Blogger content into your application using RESTful operations.\n  tags:\n  - Google\n  - Blogger\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-blogger\n    baseUri: https://www.googleapis.com/blogger/v3\n    description: Google Blogger API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_BLOGGER_TOKEN}}'\n    resources:\n    - name: blogs-blogid\n      path: /blogs/{blogId}\n      operations:\n      - name: getblog\n        method: GET\n        description: Get a blog\n        inputParameters:\n        - name: blogId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: blogs-byurl\n      path: /blogs/byurl\n      operations:\n      - name: getblogbyurl\n        method: GET\n        description: Get a blog by URL\n        inputParameters:\n        - name: url\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-blogs\n      path: /users/{userId}/blogs\n      operations:\n      - name: listblogsbyuser\n        method: GET\n        description: List blogs by user\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blogs-blogid-posts\n      path: /blogs/{blogId}/posts\n      operations:\n      - name:\
  \ listposts\n        method: GET\n        description: List posts\n        inputParameters:\n        - name: blogId\n          in: path\n          type: string\n          required: true\n        - name: maxResults\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: labels\n          in: query\n          type: string\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        - name: status\n          in: query\n          type: string\n        - name: orderBy\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertpost\n        method: POST\n        description: Create a post\n        inputParameters:\n        - name: blogId\n          in: path\n          type: string\n          required:\
  \ true\n        - name: isDraft\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blogs-blogid-posts-postid\n      path: /blogs/{blogId}/posts/{postId}\n      operations:\n      - name: getpost\n        method: GET\n        description: Get a post\n        inputParameters:\n        - name: blogId\n          in: path\n          type: string\n          required: true\n        - name: postId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepost\n        method: PUT\n        description: Update a post\n        inputParameters:\n        - name: blogId\n          in: path\n          type: string\n          required: true\n        - name: postId\n          in: path\n          type: string\n  \
  \        required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchpost\n        method: PATCH\n        description: Patch a post\n        inputParameters:\n        - name: blogId\n          in: path\n          type: string\n          required: true\n        - name: postId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepost\n        method: DELETE\n        description: Delete a post\n        inputParameters:\n        - name: blogId\n          in: path\n          type: string\n          required: true\n        - name: postId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: blogs-blogid-posts-search\n      path: /blogs/{blogId}/posts/search\n      operations:\n      - name: searchposts\n        method: GET\n        description: Search posts\n        inputParameters:\n        - name: blogId\n          in: path\n          type: string\n          required: true\n        - name: q\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blogs-blogid-pages\n      path: /blogs/{blogId}/pages\n      operations:\n      - name: listpages\n        method: GET\n        description: List pages\n        inputParameters:\n        - name: blogId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertpage\n        method: POST\n        description:\
  \ Create a page\n        inputParameters:\n        - name: blogId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blogs-blogid-posts-postid-comments\n      path: /blogs/{blogId}/posts/{postId}/comments\n      operations:\n      - name: listcomments\n        method: GET\n        description: List comments\n        inputParameters:\n        - name: blogId\n          in: path\n          type: string\n          required: true\n        - name: postId\n          in: path\n          type: string\n          required: true\n        - name: maxResults\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blogs-blogid-posts-postid-comments-commentid\n\
  \      path: /blogs/{blogId}/posts/{postId}/comments/{commentId}\n      operations:\n      - name: getcomment\n        method: GET\n        description: Get a comment\n        inputParameters:\n        - name: blogId\n          in: path\n          type: string\n          required: true\n        - name: postId\n          in: path\n          type: string\n          required: true\n        - name: commentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecomment\n        method: DELETE\n        description: Delete a comment\n        inputParameters:\n        - name: blogId\n          in: path\n          type: string\n          required: true\n        - name: postId\n          in: path\n          type: string\n          required: true\n        - name: commentId\n          in: path\n          type: string\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid\n      path: /users/{userId}\n      operations:\n      - name: getuser\n        method: GET\n        description: Get a user\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-blogger-rest\n    description: REST adapter for Google Blogger API.\n    resources:\n    - path: /blogs/{blogId}\n      name: getblog\n      operations:\n      - method: GET\n        name: getblog\n        description: Get a blog\n        call: google-blogger.getblog\n        with:\n          blogId: rest.blogId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /blogs/byurl\n      name: getblogbyurl\n      operations:\n      - method: GET\n        name: getblogbyurl\n        description: Get a blog by URL\n        call: google-blogger.getblogbyurl\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/blogs\n      name: listblogsbyuser\n      operations:\n      - method: GET\n        name: listblogsbyuser\n        description: List blogs by user\n        call: google-blogger.listblogsbyuser\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blogs/{blogId}/posts\n      name: listposts\n      operations:\n      - method: GET\n        name: listposts\n        description: List posts\n        call: google-blogger.listposts\n        with:\n          blogId: rest.blogId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blogs/{blogId}/posts\n      name: insertpost\n      operations:\n\
  \      - method: POST\n        name: insertpost\n        description: Create a post\n        call: google-blogger.insertpost\n        with:\n          blogId: rest.blogId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blogs/{blogId}/posts/{postId}\n      name: getpost\n      operations:\n      - method: GET\n        name: getpost\n        description: Get a post\n        call: google-blogger.getpost\n        with:\n          blogId: rest.blogId\n          postId: rest.postId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blogs/{blogId}/posts/{postId}\n      name: updatepost\n      operations:\n      - method: PUT\n        name: updatepost\n        description: Update a post\n        call: google-blogger.updatepost\n        with:\n          blogId: rest.blogId\n          postId: rest.postId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blogs/{blogId}/posts/{postId}\n\
  \      name: patchpost\n      operations:\n      - method: PATCH\n        name: patchpost\n        description: Patch a post\n        call: google-blogger.patchpost\n        with:\n          blogId: rest.blogId\n          postId: rest.postId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blogs/{blogId}/posts/{postId}\n      name: deletepost\n      operations:\n      - method: DELETE\n        name: deletepost\n        description: Delete a post\n        call: google-blogger.deletepost\n        with:\n          blogId: rest.blogId\n          postId: rest.postId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blogs/{blogId}/posts/search\n      name: searchposts\n      operations:\n      - method: GET\n        name: searchposts\n        description: Search posts\n        call: google-blogger.searchposts\n        with:\n          blogId: rest.blogId\n        outputParameters:\n        - type: object\n         \
  \ mapping: $.\n    - path: /blogs/{blogId}/pages\n      name: listpages\n      operations:\n      - method: GET\n        name: listpages\n        description: List pages\n        call: google-blogger.listpages\n        with:\n          blogId: rest.blogId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blogs/{blogId}/pages\n      name: insertpage\n      operations:\n      - method: POST\n        name: insertpage\n        description: Create a page\n        call: google-blogger.insertpage\n        with:\n          blogId: rest.blogId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blogs/{blogId}/posts/{postId}/comments\n      name: listcomments\n      operations:\n      - method: GET\n        name: listcomments\n        description: List comments\n        call: google-blogger.listcomments\n        with:\n          blogId: rest.blogId\n          postId: rest.postId\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /blogs/{blogId}/posts/{postId}/comments/{commentId}\n      name: getcomment\n      operations:\n      - method: GET\n        name: getcomment\n        description: Get a comment\n        call: google-blogger.getcomment\n        with:\n          blogId: rest.blogId\n          postId: rest.postId\n          commentId: rest.commentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blogs/{blogId}/posts/{postId}/comments/{commentId}\n      name: deletecomment\n      operations:\n      - method: DELETE\n        name: deletecomment\n        description: Delete a comment\n        call: google-blogger.deletecomment\n        with:\n          blogId: rest.blogId\n          postId: rest.postId\n          commentId: rest.commentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n\
  \        description: Get a user\n        call: google-blogger.getuser\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-blogger-mcp\n    transport: http\n    description: MCP adapter for Google Blogger API for AI agent use.\n    tools:\n    - name: getblog\n      description: Get a blog\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-blogger.getblog\n      with:\n        blogId: tools.blogId\n      inputParameters:\n      - name: blogId\n        type: string\n        description: blogId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getblogbyurl\n      description: Get a blog by URL\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-blogger.getblogbyurl\n      with:\n        url: tools.url\n\
  \      inputParameters:\n      - name: url\n        type: string\n        description: url\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listblogsbyuser\n      description: List blogs by user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-blogger.listblogsbyuser\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listposts\n      description: List posts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-blogger.listposts\n      with:\n        blogId: tools.blogId\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n        labels: tools.labels\n        startDate: tools.startDate\n        endDate:\
  \ tools.endDate\n        status: tools.status\n        orderBy: tools.orderBy\n      inputParameters:\n      - name: blogId\n        type: string\n        description: blogId\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: labels\n        type: string\n        description: labels\n      - name: startDate\n        type: string\n        description: startDate\n      - name: endDate\n        type: string\n        description: endDate\n      - name: status\n        type: string\n        description: status\n      - name: orderBy\n        type: string\n        description: orderBy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertpost\n      description: Create a post\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-blogger.insertpost\n    \
  \  with:\n        blogId: tools.blogId\n        isDraft: tools.isDraft\n      inputParameters:\n      - name: blogId\n        type: string\n        description: blogId\n        required: true\n      - name: isDraft\n        type: boolean\n        description: isDraft\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpost\n      description: Get a post\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-blogger.getpost\n      with:\n        blogId: tools.blogId\n        postId: tools.postId\n      inputParameters:\n      - name: blogId\n        type: string\n        description: blogId\n        required: true\n      - name: postId\n        type: string\n        description: postId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepost\n      description: Update a post\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: true\n      call: google-blogger.updatepost\n      with:\n        blogId: tools.blogId\n        postId: tools.postId\n      inputParameters:\n      - name: blogId\n        type: string\n        description: blogId\n        required: true\n      - name: postId\n        type: string\n        description: postId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchpost\n      description: Patch a post\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-blogger.patchpost\n      with:\n        blogId: tools.blogId\n        postId: tools.postId\n      inputParameters:\n      - name: blogId\n        type: string\n        description: blogId\n        required: true\n      - name: postId\n        type: string\n        description: postId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletepost\n   \
  \   description: Delete a post\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-blogger.deletepost\n      with:\n        blogId: tools.blogId\n        postId: tools.postId\n      inputParameters:\n      - name: blogId\n        type: string\n        description: blogId\n        required: true\n      - name: postId\n        type: string\n        description: postId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchposts\n      description: Search posts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-blogger.searchposts\n      with:\n        blogId: tools.blogId\n        q: tools.q\n      inputParameters:\n      - name: blogId\n        type: string\n        description: blogId\n        required: true\n      - name: q\n        type: string\n        description: q\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listpages\n      description: List pages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-blogger.listpages\n      with:\n        blogId: tools.blogId\n      inputParameters:\n      - name: blogId\n        type: string\n        description: blogId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertpage\n      description: Create a page\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-blogger.insertpage\n      with:\n        blogId: tools.blogId\n      inputParameters:\n      - name: blogId\n        type: string\n        description: blogId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcomments\n      description: List comments\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: google-blogger.listcomments\n      with:\n        blogId: tools.blogId\n        postId: tools.postId\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: blogId\n        type: string\n        description: blogId\n        required: true\n      - name: postId\n        type: string\n        description: postId\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcomment\n      description: Get a comment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-blogger.getcomment\n      with:\n        blogId: tools.blogId\n        postId: tools.postId\n        commentId: tools.commentId\n      inputParameters:\n      -\
  \ name: blogId\n        type: string\n        description: blogId\n        required: true\n      - name: postId\n        type: string\n        description: postId\n        required: true\n      - name: commentId\n        type: string\n        description: commentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecomment\n      description: Delete a comment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-blogger.deletecomment\n      with:\n        blogId: tools.blogId\n        postId: tools.postId\n        commentId: tools.commentId\n      inputParameters:\n      - name: blogId\n        type: string\n        description: blogId\n        required: true\n      - name: postId\n        type: string\n        description: postId\n        required: true\n      - name: commentId\n        type: string\n        description: commentId\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getuser\n      description: Get a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-blogger.getuser\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_BLOGGER_TOKEN: GOOGLE_BLOGGER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-blogger/refs/heads/main/capabilities/google-blogger-capability.yaml
tags:
- Google
- Blogger
- API
tools:
- description: Get a blog
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getblog
- description: Get a blog by URL
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getblogbyurl
- description: List blogs by user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listblogsbyuser
- description: List posts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listposts
- description: Create a post
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertpost
- description: Get a post
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpost
- description: Update a post
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepost
- description: Patch a post
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchpost
- description: Delete a post
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepost
- description: Search posts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchposts
- description: List pages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpages
- description: Create a page
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertpage
- description: List comments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcomments
- description: Get a comment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcomment
- description: Delete a comment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecomment
- description: Get a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
---
