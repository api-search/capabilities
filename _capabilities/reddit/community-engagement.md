---
categories: []
consumed_apis: []
description: Unified capability for reading and engaging with Reddit community content. Combines the Reddit Data API for browsing posts, searching communities, and accessing user profiles. Used by community managers, content researchers, and social listening applications to monitor discussions, analyze sentiment, and engage with Reddit audiences.
layout: capability
name: Reddit Community Engagement
operations:
- description: Get authenticated user identity
  method: GET
  name: get-me
  path: /v1/me
- description: Get subreddit information and stats
  method: GET
  name: get-subreddit
  path: /v1/subreddits/{subreddit}
- description: Get trending hot posts
  method: GET
  name: get-hot-posts
  path: /v1/subreddits/{subreddit}/hot
- description: Get newest posts
  method: GET
  name: get-new-posts
  path: /v1/subreddits/{subreddit}/new
- description: Search Reddit content
  method: GET
  name: search
  path: /v1/search
- description: Submit a new post to a subreddit
  method: POST
  name: submit-post
  path: /v1/posts
personas: []
provider_name: Reddit
provider_slug: reddit
search_terms:
- get me
- search reddit content
- get metadata, description, subscriber count, and stats for a subreddit
- search reddit
- hot posts in a subreddit
- get the currently trending hot posts from a subreddit
- subreddit community information
- content
- submit a new post to a subreddit
- get authenticated user identity
- reddit
- communities
- get hot posts
- get subreddit
- get new posts
- get trending hot posts
- get newest posts
- search reddit for posts and discussions matching a query
- reddit search
- advertising
- submit post
- search
- social listening
- new posts in a subreddit
- get subreddit information and stats
- submit a new text post to a subreddit
- social news
- get the most recently submitted posts from a subreddit
- get current user
- social media
- get the identity of the currently authenticated reddit user
- post submission
- get subreddit info
- current user identity
slug: community-engagement
source_filename: community-engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Reddit Community Engagement\n  description: Unified capability for reading and engaging with Reddit community content. Combines the Reddit Data API for\n    browsing posts, searching communities, and accessing user profiles. Used by community managers, content researchers, and\n    social listening applications to monitor discussions, analyze sentiment, and engage with Reddit audiences.\n  tags:\n  - Communities\n  - Content\n  - Reddit\n  - Social Media\n  - Social Listening\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    REDDIT_ACCESS_TOKEN: REDDIT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: reddit-data\n    baseUri: https://oauth.reddit.com\n    description: Reddit Data API for accessing platform content and communities\n    authentication:\n      type: bearer\n      token: '{{REDDIT_ACCESS_TOKEN}}'\n    resources:\n    - name: me\n      path: /api/v1/me\n      description:\
  \ Current user identity and profile\n      operations:\n      - name: get-me\n        method: GET\n        description: Get current authenticated user identity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hot-listings\n      path: /r/{subreddit}/hot\n      description: Hot post listings for a subreddit\n      operations:\n      - name: get-hot-listings\n        method: GET\n        description: Get hot posts from a subreddit\n        inputParameters:\n        - name: subreddit\n          in: path\n          type: string\n          required: true\n          description: Subreddit name\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of posts to return (max 100)\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: new-listings\n      path: /r/{subreddit}/new\n      description: New post listings for a subreddit\n      operations:\n      - name: get-new-listings\n        method: GET\n        description: Get newest posts from a subreddit\n        inputParameters:\n        - name: subreddit\n          in: path\n          type: string\n          required: true\n          description: Subreddit name\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of posts to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subreddit-info\n      path: /r/{subreddit}/about\n      description: Subreddit community information\n      operations:\n      - name: get-subreddit-info\n        method: GET\n        description: Get subreddit\
  \ metadata and configuration\n        inputParameters:\n        - name: subreddit\n          in: path\n          type: string\n          required: true\n          description: Subreddit name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: Reddit search\n      operations:\n      - name: search-submissions\n        method: GET\n        description: Search Reddit submissions\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort order (relevance, hot, top, new)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: submit\n      path: /api/submit\n      description: Post submission\n      operations:\n      - name: submit-post\n        method: POST\n        description: Submit a new post to a subreddit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            sr: '{{tools.subreddit}}'\n            title: '{{tools.title}}'\n            text: '{{tools.text}}'\n            kind: self\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: reddit-community-rest\n    description: Unified REST API for Reddit community content access and engagement.\n    resources:\n    - path: /v1/me\n      name: me\n      description: Current user identity\n      operations:\n      - method: GET\n        name: get-me\n        description: Get authenticated user identity\n      \
  \  call: reddit-data.get-me\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subreddits/{subreddit}\n      name: subreddit\n      description: Subreddit community information\n      operations:\n      - method: GET\n        name: get-subreddit\n        description: Get subreddit information and stats\n        call: reddit-data.get-subreddit-info\n        with:\n          subreddit: rest.subreddit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subreddits/{subreddit}/hot\n      name: hot-posts\n      description: Hot posts in a subreddit\n      operations:\n      - method: GET\n        name: get-hot-posts\n        description: Get trending hot posts\n        call: reddit-data.get-hot-listings\n        with:\n          subreddit: rest.subreddit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subreddits/{subreddit}/new\n      name: new-posts\n      description: New\
  \ posts in a subreddit\n      operations:\n      - method: GET\n        name: get-new-posts\n        description: Get newest posts\n        call: reddit-data.get-new-listings\n        with:\n          subreddit: rest.subreddit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      description: Reddit search\n      operations:\n      - method: GET\n        name: search\n        description: Search Reddit content\n        call: reddit-data.search-submissions\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/posts\n      name: posts\n      description: Post submission\n      operations:\n      - method: POST\n        name: submit-post\n        description: Submit a new post to a subreddit\n        call: reddit-data.submit-post\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace:\
  \ reddit-community-mcp\n    transport: http\n    description: MCP server for AI-assisted Reddit community monitoring and engagement.\n    tools:\n    - name: get-current-user\n      description: Get the identity of the currently authenticated Reddit user\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reddit-data.get-me\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-subreddit-info\n      description: Get metadata, description, subscriber count, and stats for a subreddit\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reddit-data.get-subreddit-info\n      with:\n        subreddit: tools.subreddit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-hot-posts\n      description: Get the currently trending hot posts from a subreddit\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reddit-data.get-hot-listings\n      with:\n        subreddit:\
  \ tools.subreddit\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-new-posts\n      description: Get the most recently submitted posts from a subreddit\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reddit-data.get-new-listings\n      with:\n        subreddit: tools.subreddit\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-reddit\n      description: Search Reddit for posts and discussions matching a query\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reddit-data.search-submissions\n      with:\n        q: tools.query\n        sort: tools.sort\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-post\n      description: Submit a new text post to a subreddit\n      hints:\n        readOnly: false\n        openWorld: false\n      call: reddit-data.submit-post\n\
  \      with:\n        subreddit: tools.subreddit\n        title: tools.title\n        text: tools.text\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/reddit/refs/heads/main/capabilities/community-engagement.yaml
tags:
- Communities
- Content
- Reddit
- Social Media
- Social Listening
tools:
- description: Get the identity of the currently authenticated Reddit user
  hints:
    openWorld: false
    readOnly: true
  name: get-current-user
- description: Get metadata, description, subscriber count, and stats for a subreddit
  hints:
    openWorld: true
    readOnly: true
  name: get-subreddit-info
- description: Get the currently trending hot posts from a subreddit
  hints:
    openWorld: true
    readOnly: true
  name: get-hot-posts
- description: Get the most recently submitted posts from a subreddit
  hints:
    openWorld: true
    readOnly: true
  name: get-new-posts
- description: Search Reddit for posts and discussions matching a query
  hints:
    openWorld: true
    readOnly: true
  name: search-reddit
- description: Submit a new text post to a subreddit
  hints:
    openWorld: false
    readOnly: false
  name: submit-post
---
