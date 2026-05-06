---
categories: []
consumed_apis: []
description: Workflow capability for discovering and retrieving programming knowledge from the Stack Exchange network. Enables developers, AI agents, and tools to search for questions, find answers, explore tags, and identify experts across Stack Overflow and other Stack Exchange sites.
layout: capability
name: Stack Exchange Knowledge Discovery
operations:
- description: Get questions from Stack Exchange sorted by activity, creation, or votes
  method: GET
  name: get-questions
  path: /v1/questions
- description: Get unanswered questions to identify knowledge gaps
  method: GET
  name: get-unanswered-questions
  path: /v1/unanswered
- description: Search Stack Exchange questions by title text and tags
  method: GET
  name: search-questions
  path: /v1/search
- description: Advanced search with acceptance status, body, and view count filters
  method: GET
  name: advanced-search
  path: /v1/search/advanced
- description: Get tags used to categorize questions on Stack Exchange
  method: GET
  name: get-tags
  path: /v1/tags
- description: Find Stack Exchange users and community experts
  method: GET
  name: get-users
  path: /v1/users
- description: List all Stack Exchange network sites
  method: GET
  name: get-sites
  path: /v1/sites
personas: []
provider_name: Stack Exchange
provider_slug: stack-exchange
search_terms:
- get users
- search questions by keyword
- questions that need answers
- developer tools
- search stack overflow and stack exchange for programming questions by keyword, topic, or technology tag
- get sites
- browse tags
- find unanswered questions on stack exchange that need community attention
- search questions
- find community experts
- get top questions
- community
- get unanswered questions to identify knowledge gaps
- find experts
- list stack exchange sites
- q&a
- get tags used to categorize questions on stack exchange
- browse tags on a stack exchange site to understand topic taxonomy
- get questions from stack exchange sorted by activity, creation, or votes
- list all sites in the stack exchange network to find the right community
- browse and filter questions
- knowledge discovery
- advanced search
- get top-voted or most-active questions on a stack exchange site optionally filtered by tag
- stack exchange
- get full details of specific stack exchange questions by id
- get unanswered questions
- get question details
- search programming questions
- find high-reputation users and experts on a stack exchange site by name
- advanced search with acceptance status, body, and view count filters
- search stack exchange questions by title text and tags
- list all stack exchange network sites
- stack exchange network sites
- get tags
- code
- search
- knowledge base
- perform advanced search of stack exchange with acceptance, vote, and tag filters
- advanced search questions
- get questions
- answers
- questions
- find stack exchange users and community experts
- advanced question search with multiple filters
slug: knowledge-discovery
source_filename: knowledge-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Stack Exchange Knowledge Discovery\n  description: Workflow capability for discovering and retrieving programming knowledge from the Stack Exchange network. Enables\n    developers, AI agents, and tools to search for questions, find answers, explore tags, and identify experts across Stack\n    Overflow and other Stack Exchange sites.\n  tags:\n  - Stack Exchange\n  - Knowledge Discovery\n  - Q&A\n  - Developer Tools\n  - Search\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STACK_EXCHANGE_ACCESS_TOKEN: STACK_EXCHANGE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: stack-exchange-api\n    baseUri: https://api.stackexchange.com/2.3\n    description: Stack Exchange network Q&A API v2.3\n    authentication:\n      type: apikey\n      key: access_token\n      value: '{{STACK_EXCHANGE_ACCESS_TOKEN}}'\n      placement: query\n    resources:\n    - name: questions\n      path:\
  \ /questions\n      description: Stack Exchange questions\n      operations:\n      - name: get-questions\n        method: GET\n        description: Get questions from a Stack Exchange site\n        inputParameters:\n        - name: site\n          in: query\n          type: string\n          required: true\n          description: Stack Exchange site identifier\n        - name: tagged\n          in: query\n          type: string\n          required: false\n          description: Semicolon-delimited tags to filter by\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort field (activity, creation, votes, hot, week, month)\n        - name: order\n          in: query\n          type: string\n          required: false\n          description: Sort order (asc, desc)\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pagesize\n  \
  \        in: query\n          type: integer\n          required: false\n          description: Items per page (max 100)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-unanswered-questions\n        method: GET\n        description: Get unanswered questions from a Stack Exchange site\n        inputParameters:\n        - name: site\n          in: query\n          type: string\n          required: true\n          description: Stack Exchange site identifier\n        - name: tagged\n          in: query\n          type: string\n          required: false\n          description: Filter by tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: questions-by-id\n      path: /questions/{ids}\n      description: Stack Exchange questions by ID\n      operations:\n      - name: get-questions-by-ids\n        method:\
  \ GET\n        description: Get specific questions by semicolon-delimited IDs\n        inputParameters:\n        - name: ids\n          in: path\n          type: string\n          required: true\n          description: Semicolon-delimited question IDs\n        - name: site\n          in: query\n          type: string\n          required: true\n          description: Stack Exchange site identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: answers\n      path: /answers\n      description: Stack Exchange answers\n      operations:\n      - name: get-answers\n        method: GET\n        description: Get all answers from a Stack Exchange site\n        inputParameters:\n        - name: site\n          in: query\n          type: string\n          required: true\n          description: Stack Exchange site identifier\n        - name: sort\n          in: query\n          type: string\n          required:\
  \ false\n          description: Sort field\n        - name: order\n          in: query\n          type: string\n          required: false\n          description: Sort order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: Search Stack Exchange questions\n      operations:\n      - name: search-questions\n        method: GET\n        description: Search questions by title text and tags\n        inputParameters:\n        - name: site\n          in: query\n          type: string\n          required: true\n          description: Stack Exchange site identifier\n        - name: intitle\n          in: query\n          type: string\n          required: false\n          description: Text to search in question titles\n        - name: tagged\n          in: query\n          type: string\n          required: false\n          description: Filter by tags\n       \
  \ outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-advanced\n      path: /search/advanced\n      description: Advanced search of Stack Exchange questions\n      operations:\n      - name: search-advanced\n        method: GET\n        description: Advanced question search with filtering by accepted status, body, tags, and user\n        inputParameters:\n        - name: site\n          in: query\n          type: string\n          required: true\n          description: Stack Exchange site identifier\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Full-text search query\n        - name: tagged\n          in: query\n          type: string\n          required: false\n          description: Filter by tags\n        - name: accepted\n          in: query\n          type: boolean\n          required: false\n          description: Filter for questions\
  \ with accepted answers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: Stack Exchange users\n      operations:\n      - name: get-users\n        method: GET\n        description: Get users from a Stack Exchange site\n        inputParameters:\n        - name: site\n          in: query\n          type: string\n          required: true\n          description: Stack Exchange site identifier\n        - name: inname\n          in: query\n          type: string\n          required: false\n          description: Filter by display name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /tags\n      description: Stack Exchange tags\n      operations:\n      - name: get-tags\n        method: GET\n        description: Get tags from a Stack Exchange site\n\
  \        inputParameters:\n        - name: site\n          in: query\n          type: string\n          required: true\n          description: Stack Exchange site identifier\n        - name: inname\n          in: query\n          type: string\n          required: false\n          description: Filter by tag name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites\n      path: /sites\n      description: Stack Exchange network sites\n      operations:\n      - name: get-sites\n        method: GET\n        description: Get all sites in the Stack Exchange network\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: knowledge-discovery-api\n    description: Unified REST API for Stack Exchange knowledge discovery and Q&A retrieval.\n    resources:\n    - path: /v1/questions\n\
  \      name: questions\n      description: Browse and filter questions\n      operations:\n      - method: GET\n        name: get-questions\n        description: Get questions from Stack Exchange sorted by activity, creation, or votes\n        call: stack-exchange-api.get-questions\n        with:\n          site: rest.site\n          tagged: rest.tagged\n          sort: rest.sort\n          order: rest.order\n          page: rest.page\n          pagesize: rest.pagesize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/unanswered\n      name: unanswered\n      description: Questions that need answers\n      operations:\n      - method: GET\n        name: get-unanswered-questions\n        description: Get unanswered questions to identify knowledge gaps\n        call: stack-exchange-api.get-unanswered-questions\n        with:\n          site: rest.site\n          tagged: rest.tagged\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/search\n      name: search\n      description: Search questions by keyword\n      operations:\n      - method: GET\n        name: search-questions\n        description: Search Stack Exchange questions by title text and tags\n        call: stack-exchange-api.search-questions\n        with:\n          site: rest.site\n          intitle: rest.intitle\n          tagged: rest.tagged\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search/advanced\n      name: advanced-search\n      description: Advanced question search with multiple filters\n      operations:\n      - method: GET\n        name: advanced-search\n        description: Advanced search with acceptance status, body, and view count filters\n        call: stack-exchange-api.search-advanced\n        with:\n          site: rest.site\n          q: rest.q\n          tagged: rest.tagged\n          accepted: rest.accepted\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/tags\n      name: tags\n      description: Browse tags\n      operations:\n      - method: GET\n        name: get-tags\n        description: Get tags used to categorize questions on Stack Exchange\n        call: stack-exchange-api.get-tags\n        with:\n          site: rest.site\n          inname: rest.inname\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: Find community experts\n      operations:\n      - method: GET\n        name: get-users\n        description: Find Stack Exchange users and community experts\n        call: stack-exchange-api.get-users\n        with:\n          site: rest.site\n          inname: rest.inname\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sites\n      name: sites\n      description: Stack Exchange network sites\n      operations:\n      - method: GET\n        name: get-sites\n    \
  \    description: List all Stack Exchange network sites\n        call: stack-exchange-api.get-sites\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: knowledge-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted knowledge discovery on the Stack Exchange network.\n    tools:\n    - name: search-programming-questions\n      description: Search Stack Overflow and Stack Exchange for programming questions by keyword, topic, or technology tag\n      hints:\n        readOnly: true\n        openWorld: true\n        idempotent: true\n      call: stack-exchange-api.search-questions\n      with:\n        site: tools.site\n        intitle: tools.intitle\n        tagged: tools.tagged\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: advanced-search-questions\n      description: Perform advanced search of Stack Exchange with acceptance, vote, and tag filters\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n        idempotent: true\n      call: stack-exchange-api.search-advanced\n      with:\n        site: tools.site\n        q: tools.q\n        tagged: tools.tagged\n        accepted: tools.accepted\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-top-questions\n      description: Get top-voted or most-active questions on a Stack Exchange site optionally filtered by tag\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stack-exchange-api.get-questions\n      with:\n        site: tools.site\n        tagged: tools.tagged\n        sort: tools.sort\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-unanswered-questions\n      description: Find unanswered questions on Stack Exchange that need community attention\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stack-exchange-api.get-unanswered-questions\n      with:\n   \
  \     site: tools.site\n        tagged: tools.tagged\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-question-details\n      description: Get full details of specific Stack Exchange questions by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stack-exchange-api.get-questions-by-ids\n      with:\n        ids: tools.ids\n        site: tools.site\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: browse-tags\n      description: Browse tags on a Stack Exchange site to understand topic taxonomy\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stack-exchange-api.get-tags\n      with:\n        site: tools.site\n        inname: tools.inname\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-experts\n      description: Find high-reputation users and experts on a Stack Exchange site by name\n      hints:\n        readOnly: true\n      \
  \  idempotent: true\n      call: stack-exchange-api.get-users\n      with:\n        site: tools.site\n        inname: tools.inname\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-stack-exchange-sites\n      description: List all sites in the Stack Exchange network to find the right community\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stack-exchange-api.get-sites\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stack-exchange/refs/heads/main/capabilities/knowledge-discovery.yaml
tags:
- Stack Exchange
- Knowledge Discovery
- Q&A
- Developer Tools
- Search
tools:
- description: Search Stack Overflow and Stack Exchange for programming questions by keyword, topic, or technology tag
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: search-programming-questions
- description: Perform advanced search of Stack Exchange with acceptance, vote, and tag filters
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: advanced-search-questions
- description: Get top-voted or most-active questions on a Stack Exchange site optionally filtered by tag
  hints:
    idempotent: true
    readOnly: true
  name: get-top-questions
- description: Find unanswered questions on Stack Exchange that need community attention
  hints:
    idempotent: true
    readOnly: true
  name: get-unanswered-questions
- description: Get full details of specific Stack Exchange questions by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-question-details
- description: Browse tags on a Stack Exchange site to understand topic taxonomy
  hints:
    idempotent: true
    readOnly: true
  name: browse-tags
- description: Find high-reputation users and experts on a Stack Exchange site by name
  hints:
    idempotent: true
    readOnly: true
  name: find-experts
- description: List all sites in the Stack Exchange network to find the right community
  hints:
    idempotent: true
    readOnly: true
  name: list-stack-exchange-sites
---
