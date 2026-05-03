---
categories: []
consumed_apis:
- stack-overflow-api
- stack-overflow-teams-api
description: Unified workflow capability combining Stack Overflow's public Q&A search with Stack Overflow for Teams private knowledge base management. Enables developers and AI agents to search public Stack Overflow for programming solutions, find similar questions, and manage internal team knowledge through questions, answers, and articles.
layout: capability
name: Stack Overflow Developer Knowledge Management
operations:
- description: Get questions from Stack Overflow sorted by activity, votes, or creation date
  method: GET
  name: get-questions
  path: /v1/questions
- description: Search Stack Overflow questions by title text and tags
  method: GET
  name: search-questions
  path: /v1/search
- description: Advanced search with acceptance and filter options
  method: GET
  name: search-advanced
  path: /v1/search/advanced
- description: Find existing similar questions to avoid duplicates
  method: GET
  name: find-similar
  path: /v1/similar
- description: Get internal knowledge base questions
  method: GET
  name: get-team-questions
  path: /v1/teams/{team}/questions
- description: Create a new internal knowledge base question
  method: POST
  name: create-team-question
  path: /v1/teams/{team}/questions
- description: Get internal documentation articles
  method: GET
  name: get-team-articles
  path: /v1/teams/{team}/articles
- description: Create a new internal documentation article
  method: POST
  name: create-team-article
  path: /v1/teams/{team}/articles
- description: Get Stack Overflow programming tags
  method: GET
  name: get-tags
  path: /v1/tags
personas: []
provider_name: Stack Overflow
provider_slug: stack-overflow
search_terms:
- knowledge base
- create team question
- code
- create a new knowledge article in a stack overflow for teams workspace
- search questions
- get stack overflow programming tags
- create a new internal knowledge base question
- answers
- get tags
- get top-voted or most-active stack overflow questions by programming language or topic tag
- create a new question in a stack overflow for teams internal knowledge base
- search advanced
- browse programming tags
- get team questions
- find similar
- search stack overflow for programming questions, solutions, and code examples by keyword or technology tag
- create a new internal documentation article
- get knowledge articles from a stack overflow for teams workspace
- search stack overflow questions by title text and tags
- knowledge management
- search
- programming
- browse stack overflow tags to explore programming languages, frameworks, and technologies
- search stack overflow questions
- developer community
- search stackoverflow
- advanced stack overflow question search
- stack overflow
- get internal knowledge base questions
- developer tools
- advanced stack overflow search with filters for accepted answers, minimum answers, tags, and view count
- find similar questions before asking new ones
- advanced search stackoverflow
- advanced search with acceptance and filter options
- browse programming technology tags
- find existing similar questions to avoid duplicates
- get internal documentation articles
- find similar stackoverflow questions
- get top stackoverflow questions
- get questions from an internal stack overflow for teams knowledge base
- get questions
- teams
- internal team knowledge articles
- find existing stack overflow questions similar to a given title to avoid duplicates
- get team articles
- q&a
- create team article
- get questions from stack overflow sorted by activity, votes, or creation date
- questions
- internal team q&a questions
- browse stack overflow questions
slug: developer-knowledge-management
source_filename: developer-knowledge-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Stack Overflow Developer Knowledge Management\"\n  description: >-\n    Unified workflow capability combining Stack Overflow's public Q&A search\n    with Stack Overflow for Teams private knowledge base management. Enables\n    developers and AI agents to search public Stack Overflow for programming\n    solutions, find similar questions, and manage internal team knowledge\n    through questions, answers, and articles.\n  tags:\n    - Stack Overflow\n    - Knowledge Management\n    - Developer Community\n    - Q&A\n    - Teams\n    - Search\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STACK_OVERFLOW_ACCESS_TOKEN: STACK_OVERFLOW_ACCESS_TOKEN\n      STACK_OVERFLOW_TEAMS_PAT: STACK_OVERFLOW_TEAMS_PAT\n\ncapability:\n  consumes:\n    - import: stack-overflow-api\n      location: ./shared/stack-overflow-api.yaml\n    - import: stack-overflow-teams-api\n      location: ./shared/stack-overflow-teams-api.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: developer-knowledge-api\n      description: \"Unified REST API for Stack Overflow public search and Teams knowledge management.\"\n      resources:\n        - path: /v1/questions\n          name: questions\n          description: \"Browse Stack Overflow questions\"\n          operations:\n            - method: GET\n              name: get-questions\n              description: \"Get questions from Stack Overflow sorted by activity, votes, or creation date\"\n              call: \"stack-overflow-api.get-questions\"\n              with:\n                site: \"rest.site\"\n                tagged: \"rest.tagged\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/search\n          name: search\n          description: \"Search Stack Overflow questions\"\n          operations:\n            - method: GET\n            \
  \  name: search-questions\n              description: \"Search Stack Overflow questions by title text and tags\"\n              call: \"stack-overflow-api.search-questions\"\n              with:\n                site: \"rest.site\"\n                intitle: \"rest.intitle\"\n                tagged: \"rest.tagged\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/search/advanced\n          name: advanced-search\n          description: \"Advanced Stack Overflow question search\"\n          operations:\n            - method: GET\n              name: search-advanced\n              description: \"Advanced search with acceptance and filter options\"\n              call: \"stack-overflow-api.search-advanced\"\n              with:\n                site: \"rest.site\"\n                q: \"rest.q\"\n                tagged: \"rest.tagged\"\n                accepted: \"rest.accepted\"\n              outputParameters:\n    \
  \            - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/similar\n          name: similar-questions\n          description: \"Find similar questions before asking new ones\"\n          operations:\n            - method: GET\n              name: find-similar\n              description: \"Find existing similar questions to avoid duplicates\"\n              call: \"stack-overflow-api.find-similar-questions\"\n              with:\n                site: \"rest.site\"\n                title: \"rest.title\"\n                tagged: \"rest.tagged\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/teams/{team}/questions\n          name: team-questions\n          description: \"Internal team Q&A questions\"\n          operations:\n            - method: GET\n              name: get-team-questions\n              description: \"Get internal knowledge base questions\"\n              call: \"stack-overflow-teams-api.get-team-questions\"\
  \n              with:\n                team: \"rest.team\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-team-question\n              description: \"Create a new internal knowledge base question\"\n              call: \"stack-overflow-teams-api.create-team-question\"\n              with:\n                team: \"rest.team\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/teams/{team}/articles\n          name: team-articles\n          description: \"Internal team knowledge articles\"\n          operations:\n            - method: GET\n              name: get-team-articles\n              description: \"Get internal documentation articles\"\n              call: \"stack-overflow-teams-api.get-team-articles\"\n              with:\n                team: \"rest.team\"\n              outputParameters:\n         \
  \       - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-team-article\n              description: \"Create a new internal documentation article\"\n              call: \"stack-overflow-teams-api.create-team-article\"\n              with:\n                team: \"rest.team\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tags\n          name: tags\n          description: \"Browse programming technology tags\"\n          operations:\n            - method: GET\n              name: get-tags\n              description: \"Get Stack Overflow programming tags\"\n              call: \"stack-overflow-api.get-tags\"\n              with:\n                site: \"rest.site\"\n                inname: \"rest.inname\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: developer-knowledge-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted developer knowledge discovery and team knowledge management.\"\n      tools:\n        - name: search-stackoverflow\n          description: \"Search Stack Overflow for programming questions, solutions, and code examples by keyword or technology tag\"\n          hints:\n            readOnly: true\n            openWorld: true\n            idempotent: true\n          call: \"stack-overflow-api.search-questions\"\n          with:\n            site: \"tools.site\"\n            intitle: \"tools.intitle\"\n            tagged: \"tools.tagged\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: advanced-search-stackoverflow\n          description: \"Advanced Stack Overflow search with filters for accepted answers, minimum answers, tags, and view count\"\n          hints:\n            readOnly: true\n            openWorld: true\n            idempotent: true\n          call:\
  \ \"stack-overflow-api.search-advanced\"\n          with:\n            site: \"tools.site\"\n            q: \"tools.q\"\n            tagged: \"tools.tagged\"\n            accepted: \"tools.accepted\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-similar-stackoverflow-questions\n          description: \"Find existing Stack Overflow questions similar to a given title to avoid duplicates\"\n          hints:\n            readOnly: true\n            openWorld: true\n            idempotent: true\n          call: \"stack-overflow-api.find-similar-questions\"\n          with:\n            site: \"tools.site\"\n            title: \"tools.title\"\n            tagged: \"tools.tagged\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-top-stackoverflow-questions\n          description: \"Get top-voted or most-active Stack Overflow questions by programming language or topic\
  \ tag\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stack-overflow-api.get-questions\"\n          with:\n            site: \"tools.site\"\n            tagged: \"tools.tagged\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: browse-programming-tags\n          description: \"Browse Stack Overflow tags to explore programming languages, frameworks, and technologies\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stack-overflow-api.get-tags\"\n          with:\n            site: \"tools.site\"\n            inname: \"tools.inname\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-team-questions\n          description: \"Get questions from an internal Stack Overflow for Teams knowledge base\"\n          hints:\n            readOnly: true\n   \
  \         idempotent: true\n          call: \"stack-overflow-teams-api.get-team-questions\"\n          with:\n            team: \"tools.team\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-team-question\n          description: \"Create a new question in a Stack Overflow for Teams internal knowledge base\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stack-overflow-teams-api.create-team-question\"\n          with:\n            team: \"tools.team\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-team-articles\n          description: \"Get knowledge articles from a Stack Overflow for Teams workspace\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stack-overflow-teams-api.get-team-articles\"\n          with:\n            team: \"\
  tools.team\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-team-article\n          description: \"Create a new knowledge article in a Stack Overflow for Teams workspace\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"stack-overflow-teams-api.create-team-article\"\n          with:\n            team: \"tools.team\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stack-overflow/refs/heads/main/capabilities/developer-knowledge-management.yaml
tags:
- Stack Overflow
- Knowledge Management
- Developer Community
- Q&A
- Teams
- Search
tools:
- description: Search Stack Overflow for programming questions, solutions, and code examples by keyword or technology tag
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: search-stackoverflow
- description: Advanced Stack Overflow search with filters for accepted answers, minimum answers, tags, and view count
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: advanced-search-stackoverflow
- description: Find existing Stack Overflow questions similar to a given title to avoid duplicates
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: find-similar-stackoverflow-questions
- description: Get top-voted or most-active Stack Overflow questions by programming language or topic tag
  hints:
    idempotent: true
    readOnly: true
  name: get-top-stackoverflow-questions
- description: Browse Stack Overflow tags to explore programming languages, frameworks, and technologies
  hints:
    idempotent: true
    readOnly: true
  name: browse-programming-tags
- description: Get questions from an internal Stack Overflow for Teams knowledge base
  hints:
    idempotent: true
    readOnly: true
  name: get-team-questions
- description: Create a new question in a Stack Overflow for Teams internal knowledge base
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-team-question
- description: Get knowledge articles from a Stack Overflow for Teams workspace
  hints:
    idempotent: true
    readOnly: true
  name: get-team-articles
- description: Create a new knowledge article in a Stack Overflow for Teams workspace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-team-article
---
