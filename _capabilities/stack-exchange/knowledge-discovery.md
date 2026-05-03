---
categories: []
consumed_apis:
- stack-exchange-api
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
- knowledge base
- get top-voted or most-active questions on a stack exchange site optionally filtered by tag
- search stack exchange questions by title text and tags
- code
- stack exchange network sites
- search questions
- answers
- get tags
- get users
- perform advanced search of stack exchange with acceptance, vote, and tag filters
- get unanswered questions
- community
- get tags used to categorize questions on stack exchange
- browse tags
- get sites
- find community experts
- search stack overflow and stack exchange for programming questions by keyword, topic, or technology tag
- search questions by keyword
- search
- find unanswered questions on stack exchange that need community attention
- advanced search with acceptance status, body, and view count filters
- list all stack exchange network sites
- get top questions
- developer tools
- browse and filter questions
- get question details
- stack exchange
- find stack exchange users and community experts
- advanced search questions
- browse tags on a stack exchange site to understand topic taxonomy
- get unanswered questions to identify knowledge gaps
- find high-reputation users and experts on a stack exchange site by name
- knowledge discovery
- get questions from stack exchange sorted by activity, creation, or votes
- get full details of specific stack exchange questions by id
- get questions
- list all sites in the stack exchange network to find the right community
- q&a
- list stack exchange sites
- search programming questions
- advanced question search with multiple filters
- advanced search
- questions
- find experts
- questions that need answers
slug: knowledge-discovery
source_filename: knowledge-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Stack Exchange Knowledge Discovery\"\n  description: >-\n    Workflow capability for discovering and retrieving programming knowledge from\n    the Stack Exchange network. Enables developers, AI agents, and tools to search\n    for questions, find answers, explore tags, and identify experts across Stack\n    Overflow and other Stack Exchange sites.\n  tags:\n    - Stack Exchange\n    - Knowledge Discovery\n    - Q&A\n    - Developer Tools\n    - Search\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STACK_EXCHANGE_ACCESS_TOKEN: STACK_EXCHANGE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: stack-exchange-api\n      location: ./shared/stack-exchange-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: knowledge-discovery-api\n      description: \"Unified REST API for Stack Exchange knowledge discovery and Q&A retrieval.\"\n      resources:\n \
  \       - path: /v1/questions\n          name: questions\n          description: \"Browse and filter questions\"\n          operations:\n            - method: GET\n              name: get-questions\n              description: \"Get questions from Stack Exchange sorted by activity, creation, or votes\"\n              call: \"stack-exchange-api.get-questions\"\n              with:\n                site: \"rest.site\"\n                tagged: \"rest.tagged\"\n                sort: \"rest.sort\"\n                order: \"rest.order\"\n                page: \"rest.page\"\n                pagesize: \"rest.pagesize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/unanswered\n          name: unanswered\n          description: \"Questions that need answers\"\n          operations:\n            - method: GET\n              name: get-unanswered-questions\n              description: \"Get unanswered questions to identify knowledge\
  \ gaps\"\n              call: \"stack-exchange-api.get-unanswered-questions\"\n              with:\n                site: \"rest.site\"\n                tagged: \"rest.tagged\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/search\n          name: search\n          description: \"Search questions by keyword\"\n          operations:\n            - method: GET\n              name: search-questions\n              description: \"Search Stack Exchange questions by title text and tags\"\n              call: \"stack-exchange-api.search-questions\"\n              with:\n                site: \"rest.site\"\n                intitle: \"rest.intitle\"\n                tagged: \"rest.tagged\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/search/advanced\n          name: advanced-search\n          description: \"Advanced question search with multiple\
  \ filters\"\n          operations:\n            - method: GET\n              name: advanced-search\n              description: \"Advanced search with acceptance status, body, and view count filters\"\n              call: \"stack-exchange-api.search-advanced\"\n              with:\n                site: \"rest.site\"\n                q: \"rest.q\"\n                tagged: \"rest.tagged\"\n                accepted: \"rest.accepted\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tags\n          name: tags\n          description: \"Browse tags\"\n          operations:\n            - method: GET\n              name: get-tags\n              description: \"Get tags used to categorize questions on Stack Exchange\"\n              call: \"stack-exchange-api.get-tags\"\n              with:\n                site: \"rest.site\"\n                inname: \"rest.inname\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: \"Find community experts\"\n          operations:\n            - method: GET\n              name: get-users\n              description: \"Find Stack Exchange users and community experts\"\n              call: \"stack-exchange-api.get-users\"\n              with:\n                site: \"rest.site\"\n                inname: \"rest.inname\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sites\n          name: sites\n          description: \"Stack Exchange network sites\"\n          operations:\n            - method: GET\n              name: get-sites\n              description: \"List all Stack Exchange network sites\"\n              call: \"stack-exchange-api.get-sites\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n    \
  \  port: 9090\n      namespace: knowledge-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted knowledge discovery on the Stack Exchange network.\"\n      tools:\n        - name: search-programming-questions\n          description: \"Search Stack Overflow and Stack Exchange for programming questions by keyword, topic, or technology tag\"\n          hints:\n            readOnly: true\n            openWorld: true\n            idempotent: true\n          call: \"stack-exchange-api.search-questions\"\n          with:\n            site: \"tools.site\"\n            intitle: \"tools.intitle\"\n            tagged: \"tools.tagged\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: advanced-search-questions\n          description: \"Perform advanced search of Stack Exchange with acceptance, vote, and tag filters\"\n          hints:\n            readOnly: true\n            openWorld: true\n            idempotent:\
  \ true\n          call: \"stack-exchange-api.search-advanced\"\n          with:\n            site: \"tools.site\"\n            q: \"tools.q\"\n            tagged: \"tools.tagged\"\n            accepted: \"tools.accepted\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-top-questions\n          description: \"Get top-voted or most-active questions on a Stack Exchange site optionally filtered by tag\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stack-exchange-api.get-questions\"\n          with:\n            site: \"tools.site\"\n            tagged: \"tools.tagged\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-unanswered-questions\n          description: \"Find unanswered questions on Stack Exchange that need community attention\"\n          hints:\n            readOnly: true\n\
  \            idempotent: true\n          call: \"stack-exchange-api.get-unanswered-questions\"\n          with:\n            site: \"tools.site\"\n            tagged: \"tools.tagged\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-question-details\n          description: \"Get full details of specific Stack Exchange questions by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stack-exchange-api.get-questions-by-ids\"\n          with:\n            ids: \"tools.ids\"\n            site: \"tools.site\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: browse-tags\n          description: \"Browse tags on a Stack Exchange site to understand topic taxonomy\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stack-exchange-api.get-tags\"\n          with:\n            site: \"tools.site\"\
  \n            inname: \"tools.inname\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-experts\n          description: \"Find high-reputation users and experts on a Stack Exchange site by name\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stack-exchange-api.get-users\"\n          with:\n            site: \"tools.site\"\n            inname: \"tools.inname\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-stack-exchange-sites\n          description: \"List all sites in the Stack Exchange network to find the right community\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stack-exchange-api.get-sites\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
