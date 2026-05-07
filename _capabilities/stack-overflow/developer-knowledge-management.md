---
categories: []
consumed_apis: []
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
- stack overflow
- create team article
- get team questions
- find existing similar questions to avoid duplicates
- create a new internal knowledge base question
- create team question
- browse stack overflow tags to explore programming languages, frameworks, and technologies
- get questions from an internal stack overflow for teams knowledge base
- create a new question in a stack overflow for teams internal knowledge base
- get top stackoverflow questions
- get knowledge articles from a stack overflow for teams workspace
- teams
- internal team q&a questions
- browse programming technology tags
- browse programming tags
- questions
- knowledge management
- search stack overflow questions by title text and tags
- internal team knowledge articles
- knowledge base
- advanced stack overflow question search
- q&a
- get questions
- get internal documentation articles
- browse stack overflow questions
- answers
- developer tools
- search stackoverflow
- get top-voted or most-active stack overflow questions by programming language or topic tag
- create a new knowledge article in a stack overflow for teams workspace
- create a new internal documentation article
- developer community
- get team articles
- get internal knowledge base questions
- search stack overflow for programming questions, solutions, and code examples by keyword or technology tag
- advanced search stackoverflow
- get questions from stack overflow sorted by activity, votes, or creation date
- search stack overflow questions
- advanced stack overflow search with filters for accepted answers, minimum answers, tags, and view count
- find similar questions before asking new ones
- programming
- find similar
- search
- advanced search with acceptance and filter options
- get stack overflow programming tags
- code
- search advanced
- get tags
- find existing stack overflow questions similar to a given title to avoid duplicates
- find similar stackoverflow questions
- search questions
slug: developer-knowledge-management
source_filename: developer-knowledge-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Stack Overflow Developer Knowledge Management\n  description: Unified workflow capability combining Stack Overflow's public Q&A search with Stack Overflow for Teams private\n    knowledge base management. Enables developers and AI agents to search public Stack Overflow for programming solutions,\n    find similar questions, and manage internal team knowledge through questions, answers, and articles.\n  tags:\n  - Stack Overflow\n  - Knowledge Management\n  - Developer Community\n  - Q&A\n  - Teams\n  - Search\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STACK_OVERFLOW_ACCESS_TOKEN: STACK_OVERFLOW_ACCESS_TOKEN\n    STACK_OVERFLOW_TEAMS_PAT: STACK_OVERFLOW_TEAMS_PAT\ncapability:\n  consumes:\n  - type: http\n    namespace: stack-overflow-api\n    baseUri: https://api.stackexchange.com/2.3\n    description: Stack Overflow public API v2.3\n    authentication:\n      type: apikey\n      key: access_token\n\
  \      value: '{{STACK_OVERFLOW_ACCESS_TOKEN}}'\n      placement: query\n    resources:\n    - name: questions\n      path: /questions\n      description: Stack Overflow questions\n      operations:\n      - name: get-questions\n        method: GET\n        description: Get questions from Stack Overflow\n        inputParameters:\n        - name: site\n          in: query\n          type: string\n          required: true\n          description: Must be stackoverflow\n        - name: tagged\n          in: query\n          type: string\n          required: false\n          description: Filter by programming language or topic tags\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort by activity, creation, votes, hot, week, month\n        - name: order\n          in: query\n          type: string\n          required: false\n          description: Sort order (asc, desc)\n        - name: page\n          in: query\n        \
  \  type: integer\n          required: false\n          description: Page number\n        - name: pagesize\n          in: query\n          type: integer\n          required: false\n          description: Results per page (max 100)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: Search Stack Overflow questions\n      operations:\n      - name: search-questions\n        method: GET\n        description: Search Stack Overflow questions by title and tags\n        inputParameters:\n        - name: site\n          in: query\n          type: string\n          required: true\n          description: Must be stackoverflow\n        - name: intitle\n          in: query\n          type: string\n          required: false\n          description: Text to search in question titles\n        - name: tagged\n          in: query\n          type: string\n          required:\
  \ false\n          description: Filter by tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-advanced\n      path: /search/advanced\n      description: Advanced Stack Overflow question search\n      operations:\n      - name: search-advanced\n        method: GET\n        description: Advanced question search with multiple filter options\n        inputParameters:\n        - name: site\n          in: query\n          type: string\n          required: true\n          description: Must be stackoverflow\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Full-text search query\n        - name: tagged\n          in: query\n          type: string\n          required: false\n          description: Filter by tags\n        - name: accepted\n          in: query\n          type: boolean\n          required: false\n          description:\
  \ Filter for questions with accepted answers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: similar\n      path: /similar\n      description: Find similar questions on Stack Overflow\n      operations:\n      - name: find-similar-questions\n        method: GET\n        description: Find questions similar to a given title\n        inputParameters:\n        - name: site\n          in: query\n          type: string\n          required: true\n          description: Must be stackoverflow\n        - name: title\n          in: query\n          type: string\n          required: true\n          description: Question title to find similar questions for\n        - name: tagged\n          in: query\n          type: string\n          required: false\n          description: Filter similar questions by tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: tags\n      path: /tags\n      description: Stack Overflow programming tags\n      operations:\n      - name: get-tags\n        method: GET\n        description: Get programming tags on Stack Overflow\n        inputParameters:\n        - name: site\n          in: query\n          type: string\n          required: true\n          description: Must be stackoverflow\n        - name: inname\n          in: query\n          type: string\n          required: false\n          description: Filter tags by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: Stack Overflow users\n      operations:\n      - name: get-users\n        method: GET\n        description: Get Stack Overflow users\n        inputParameters:\n        - name: site\n          in: query\n          type: string\n          required: true\n          description:\
  \ Must be stackoverflow\n        - name: inname\n          in: query\n          type: string\n          required: false\n          description: Filter users by display name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: stack-overflow-teams-api\n    baseUri: https://api.stackoverflowteams.com/v3\n    description: Stack Overflow for Teams API v3\n    authentication:\n      type: bearer\n      token: '{{STACK_OVERFLOW_TEAMS_PAT}}'\n    resources:\n    - name: team-questions\n      path: /teams/{team}/questions\n      description: Team workspace questions\n      operations:\n      - name: get-team-questions\n        method: GET\n        description: Get questions in a Stack Overflow for Teams workspace\n        inputParameters:\n        - name: team\n          in: path\n          type: string\n          required: true\n          description: Team workspace slug\n        - name:\
  \ sort\n          in: query\n          type: string\n          required: false\n          description: Sort field\n        - name: order\n          in: query\n          type: string\n          required: false\n          description: Sort order\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pagesize\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-team-question\n        method: POST\n        description: Create a new question in a Stack Overflow for Teams workspace\n        inputParameters:\n        - name: team\n          in: path\n          type: string\n          required: true\n          description: Team workspace slug\n        body:\n          type: json\n          data:\n\
  \            title: '{{tools.title}}'\n            body: '{{tools.body}}'\n            tags: '{{tools.tags}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: team-articles\n      path: /teams/{team}/articles\n      description: Team knowledge articles\n      operations:\n      - name: get-team-articles\n        method: GET\n        description: Get knowledge articles in a Stack Overflow for Teams workspace\n        inputParameters:\n        - name: team\n          in: path\n          type: string\n          required: true\n          description: Team workspace slug\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pagesize\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n      - name: create-team-article\n        method: POST\n        description: Create a new knowledge article in a Stack Overflow for Teams workspace\n        inputParameters:\n        - name: team\n          in: path\n          type: string\n          required: true\n          description: Team workspace slug\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            body: '{{tools.body}}'\n            tags: '{{tools.tags}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: team-users\n      path: /teams/{team}/users\n      description: Team workspace users\n      operations:\n      - name: get-team-users\n        method: GET\n        description: Get users in a Stack Overflow for Teams workspace\n        inputParameters:\n        - name: team\n          in: path\n          type: string\n\
  \          required: true\n          description: Team workspace slug\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: team-tags\n      path: /teams/{team}/tags\n      description: Team workspace tags\n      operations:\n      - name: get-team-tags\n        method: GET\n        description: Get tags in a Stack Overflow for Teams workspace\n        inputParameters:\n        - name: team\n          in: path\n          type: string\n          required: true\n          description: Team workspace slug\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: developer-knowledge-api\n    description: Unified REST API for Stack Overflow public search and Teams knowledge management.\n    resources:\n    - path: /v1/questions\n      name: questions\n      description: Browse Stack\
  \ Overflow questions\n      operations:\n      - method: GET\n        name: get-questions\n        description: Get questions from Stack Overflow sorted by activity, votes, or creation date\n        call: stack-overflow-api.get-questions\n        with:\n          site: rest.site\n          tagged: rest.tagged\n          sort: rest.sort\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      description: Search Stack Overflow questions\n      operations:\n      - method: GET\n        name: search-questions\n        description: Search Stack Overflow questions by title text and tags\n        call: stack-overflow-api.search-questions\n        with:\n          site: rest.site\n          intitle: rest.intitle\n          tagged: rest.tagged\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search/advanced\n      name: advanced-search\n      description: Advanced Stack Overflow question\
  \ search\n      operations:\n      - method: GET\n        name: search-advanced\n        description: Advanced search with acceptance and filter options\n        call: stack-overflow-api.search-advanced\n        with:\n          site: rest.site\n          q: rest.q\n          tagged: rest.tagged\n          accepted: rest.accepted\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/similar\n      name: similar-questions\n      description: Find similar questions before asking new ones\n      operations:\n      - method: GET\n        name: find-similar\n        description: Find existing similar questions to avoid duplicates\n        call: stack-overflow-api.find-similar-questions\n        with:\n          site: rest.site\n          title: rest.title\n          tagged: rest.tagged\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams/{team}/questions\n      name: team-questions\n      description: Internal\
  \ team Q&A questions\n      operations:\n      - method: GET\n        name: get-team-questions\n        description: Get internal knowledge base questions\n        call: stack-overflow-teams-api.get-team-questions\n        with:\n          team: rest.team\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-team-question\n        description: Create a new internal knowledge base question\n        call: stack-overflow-teams-api.create-team-question\n        with:\n          team: rest.team\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams/{team}/articles\n      name: team-articles\n      description: Internal team knowledge articles\n      operations:\n      - method: GET\n        name: get-team-articles\n        description: Get internal documentation articles\n        call: stack-overflow-teams-api.get-team-articles\n        with:\n          team: rest.team\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-team-article\n        description: Create a new internal documentation article\n        call: stack-overflow-teams-api.create-team-article\n        with:\n          team: rest.team\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tags\n      name: tags\n      description: Browse programming technology tags\n      operations:\n      - method: GET\n        name: get-tags\n        description: Get Stack Overflow programming tags\n        call: stack-overflow-api.get-tags\n        with:\n          site: rest.site\n          inname: rest.inname\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: developer-knowledge-mcp\n    transport: http\n    description: MCP server for AI-assisted developer knowledge discovery and team knowledge management.\n    tools:\n    - name: search-stackoverflow\n \
  \     description: Search Stack Overflow for programming questions, solutions, and code examples by keyword or technology\n        tag\n      hints:\n        readOnly: true\n        openWorld: true\n        idempotent: true\n      call: stack-overflow-api.search-questions\n      with:\n        site: tools.site\n        intitle: tools.intitle\n        tagged: tools.tagged\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: advanced-search-stackoverflow\n      description: Advanced Stack Overflow search with filters for accepted answers, minimum answers, tags, and view count\n      hints:\n        readOnly: true\n        openWorld: true\n        idempotent: true\n      call: stack-overflow-api.search-advanced\n      with:\n        site: tools.site\n        q: tools.q\n        tagged: tools.tagged\n        accepted: tools.accepted\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-similar-stackoverflow-questions\n      description:\
  \ Find existing Stack Overflow questions similar to a given title to avoid duplicates\n      hints:\n        readOnly: true\n        openWorld: true\n        idempotent: true\n      call: stack-overflow-api.find-similar-questions\n      with:\n        site: tools.site\n        title: tools.title\n        tagged: tools.tagged\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-top-stackoverflow-questions\n      description: Get top-voted or most-active Stack Overflow questions by programming language or topic tag\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stack-overflow-api.get-questions\n      with:\n        site: tools.site\n        tagged: tools.tagged\n        sort: tools.sort\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: browse-programming-tags\n      description: Browse Stack Overflow tags to explore programming languages, frameworks, and technologies\n      hints:\n        readOnly:\
  \ true\n        idempotent: true\n      call: stack-overflow-api.get-tags\n      with:\n        site: tools.site\n        inname: tools.inname\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-team-questions\n      description: Get questions from an internal Stack Overflow for Teams knowledge base\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stack-overflow-teams-api.get-team-questions\n      with:\n        team: tools.team\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-team-question\n      description: Create a new question in a Stack Overflow for Teams internal knowledge base\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: stack-overflow-teams-api.create-team-question\n      with:\n        team: tools.team\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-team-articles\n      description:\
  \ Get knowledge articles from a Stack Overflow for Teams workspace\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stack-overflow-teams-api.get-team-articles\n      with:\n        team: tools.team\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-team-article\n      description: Create a new knowledge article in a Stack Overflow for Teams workspace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: stack-overflow-teams-api.create-team-article\n      with:\n        team: tools.team\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
