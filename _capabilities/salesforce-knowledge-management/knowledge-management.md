---
categories: []
consumed_apis: []
description: 'Unified workflow capability for managing Salesforce Knowledge articles across the full article lifecycle: creation, editing, categorization, publishing, and surfacing relevant articles for case deflection and agent assistance.'
layout: capability
name: Salesforce Knowledge Management
operations:
- description: List all knowledge articles
  method: GET
  name: list-knowledge-articles
  path: /v1/articles
- description: Create a knowledge article draft
  method: POST
  name: create-knowledge-article
  path: /v1/articles
- description: Get a knowledge article
  method: GET
  name: get-knowledge-article
  path: /v1/articles/{articleId}
- description: Get full article content
  method: GET
  name: get-article-detail
  path: /v1/articles/{articleId}/detail
- description: Publish knowledge articles
  method: POST
  name: publish-articles
  path: /v1/articles/publish
- description: Search knowledge articles
  method: GET
  name: search-articles
  path: /v1/search
- description: Get article suggestions
  method: GET
  name: get-suggestions
  path: /v1/suggestions
- description: List data category groups
  method: GET
  name: list-categories
  path: /v1/categories
personas: []
provider_name: Salesforce Knowledge Management
provider_slug: salesforce-knowledge-management
search_terms:
- get article suggestions
- knowledge article management
- knowledge article search
- individual article operations
- get full article content
- get article full content
- knowledge management
- get suggestions
- publish knowledge articles
- search knowledge articles by keywords, channel, and category filters
- list categories within a data category group
- publish articles
- update knowledge article
- create a new draft knowledge article
- documentation
- publish article versions
- get article suggestions for case
- get knowledge article
- article suggestions for cases
- search articles
- get article detail
- get metadata for a specific knowledge article by id
- crm
- update an existing knowledge article draft
- delete a knowledge article draft version
- full article content
- list all knowledge articles in the salesforce org
- support
- list data category groups used to organize knowledge articles
- list knowledge articles
- create a knowledge article draft
- list categories
- search knowledge articles
- get a knowledge article
- publish knowledge article versions to configured channels
- list data categories
- list data category groups
- create knowledge article
- list all knowledge articles
- data category management
- customer service
- delete knowledge article
- articles
- get the full body content and metadata of a knowledge article
- salesforce
- get relevant article suggestions based on case subject or description
slug: knowledge-management
source_filename: knowledge-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesforce Knowledge Management\n  description: 'Unified workflow capability for managing Salesforce Knowledge articles across the full article lifecycle:\n    creation, editing, categorization, publishing, and surfacing relevant articles for case deflection and agent assistance.'\n  tags:\n  - Salesforce\n  - Knowledge Management\n  - Articles\n  - Support\n  - CRM\n  - Customer Service\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: salesforce-knowledge\n    baseUri: https://{instance}.salesforce.com/services/data/v59.0\n    description: Salesforce Knowledge Management REST API\n    authentication:\n      type: bearer\n      token: '{{SALESFORCE_ACCESS_TOKEN}}'\n    resources:\n    - name: knowledge-articles\n      path: /sobjects/KnowledgeArticle\n      description: Knowledge article listing\n\
  \      operations:\n      - name: list-knowledge-articles\n        method: GET\n        description: List all knowledge articles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: knowledge-article\n      path: /sobjects/KnowledgeArticle/{articleId}\n      description: Individual article metadata\n      operations:\n      - name: get-knowledge-article\n        method: GET\n        description: Get a specific knowledge article\n        inputParameters:\n        - name: articleId\n          in: path\n          type: string\n          required: true\n          description: Salesforce ID of the article\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: knowledge-article-versions\n      path: /sobjects/KnowledgeArticleVersion\n      description: Article version creation\n      operations:\n      - name: create-knowledge-article\n\
  \        method: POST\n        description: Create a new knowledge article draft\n        body:\n          type: json\n          data:\n            Title: '{{tools.title}}'\n            UrlName: '{{tools.urlName}}'\n            Summary: '{{tools.summary}}'\n            Language: '{{tools.language}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: knowledge-article-version\n      path: /sobjects/KnowledgeArticleVersion/{versionId}\n      description: Article version operations\n      operations:\n      - name: update-knowledge-article\n        method: PATCH\n        description: Update a knowledge article version\n        inputParameters:\n        - name: versionId\n          in: path\n          type: string\n          required: true\n          description: Salesforce ID of the article version\n        body:\n          type: json\n          data:\n            Title: '{{tools.title}}'\n          \
  \  Summary: '{{tools.summary}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-knowledge-article\n        method: DELETE\n        description: Delete a knowledge article version\n        inputParameters:\n        - name: versionId\n          in: path\n          type: string\n          required: true\n          description: Salesforce ID of the article version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-articles\n      path: /support/knowledgeArticles\n      description: Knowledge article search\n      operations:\n      - name: search-knowledge-articles\n        method: GET\n        description: Search and retrieve knowledge articles by channel and category\n        inputParameters:\n        - name: channel\n          in: query\n          type: string\n          required: false\n    \
  \      description: Channel to filter articles\n        - name: categories\n          in: query\n          type: string\n          required: false\n          description: Category filter\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort field\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: article-detail\n      path: /support/knowledgeArticles/{articleId}\n      description: Full article content retrieval\n      operations:\n      - name: get-knowledge-article-detail\n        method: GET\n        description: Get full content of a knowledge article\n        inputParameters:\n        - name: articleId\n          in: path\n          type: string\n          required: true\n          description:\
  \ Salesforce ID of the article\n        - name: channel\n          in: query\n          type: string\n          required: false\n          description: Channel context\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: publish-articles\n      path: /actions/standard/publishKnowledgeArticles\n      description: Article publishing action\n      operations:\n      - name: publish-knowledge-articles\n        method: POST\n        description: Publish one or more knowledge article versions\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: category-groups\n      path: /support/dataCategoryGroups\n      description: Data category groups\n      operations:\n      - name: list-data-category-groups\n        method: GET\n      \
  \  description: List data category groups for knowledge\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-categories\n      path: /support/dataCategoryGroups/{group}/dataCategories\n      description: Categories within a group\n      operations:\n      - name: list-data-categories\n        method: GET\n        description: List categories in a data category group\n        inputParameters:\n        - name: group\n          in: path\n          type: string\n          required: true\n          description: Category group API name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: suggested-articles\n      path: /support/suggestedArticles\n      description: Article suggestions for cases\n      operations:\n      - name: get-suggested-articles\n        method: GET\n        description: Get article suggestions\
  \ based on case content\n        inputParameters:\n        - name: subject\n          in: query\n          type: string\n          required: false\n          description: Case subject for matching\n        - name: description\n          in: query\n          type: string\n          required: false\n          description: Case description for matching\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max number of suggestions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: knowledge-management-api\n    description: Unified REST API for Salesforce Knowledge Management.\n    resources:\n    - path: /v1/articles\n      name: articles\n      description: Knowledge article management\n      operations:\n      - method: GET\n        name: list-knowledge-articles\n        description: List\
  \ all knowledge articles\n        call: salesforce-knowledge.list-knowledge-articles\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-knowledge-article\n        description: Create a knowledge article draft\n        call: salesforce-knowledge.create-knowledge-article\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/articles/{articleId}\n      name: article\n      description: Individual article operations\n      operations:\n      - method: GET\n        name: get-knowledge-article\n        description: Get a knowledge article\n        call: salesforce-knowledge.get-knowledge-article\n        with:\n          articleId: rest.articleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/articles/{articleId}/detail\n      name: article-detail\n      description: Full article content\n      operations:\n      - method: GET\n        name: get-article-detail\n\
  \        description: Get full article content\n        call: salesforce-knowledge.get-knowledge-article-detail\n        with:\n          articleId: rest.articleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/articles/publish\n      name: publish-articles\n      description: Publish article versions\n      operations:\n      - method: POST\n        name: publish-articles\n        description: Publish knowledge articles\n        call: salesforce-knowledge.publish-knowledge-articles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      description: Knowledge article search\n      operations:\n      - method: GET\n        name: search-articles\n        description: Search knowledge articles\n        call: salesforce-knowledge.search-knowledge-articles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/suggestions\n      name: suggestions\n\
  \      description: Article suggestions for cases\n      operations:\n      - method: GET\n        name: get-suggestions\n        description: Get article suggestions\n        call: salesforce-knowledge.get-suggested-articles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/categories\n      name: categories\n      description: Data category management\n      operations:\n      - method: GET\n        name: list-categories\n        description: List data category groups\n        call: salesforce-knowledge.list-data-category-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: knowledge-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Salesforce Knowledge Management.\n    tools:\n    - name: list-knowledge-articles\n      description: List all knowledge articles in the Salesforce org\n      hints:\n        readOnly: true\n        idempotent:\
  \ true\n        openWorld: true\n      call: salesforce-knowledge.list-knowledge-articles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-knowledge-article\n      description: Get metadata for a specific knowledge article by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-knowledge.get-knowledge-article\n      with:\n        articleId: tools.articleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-article-full-content\n      description: Get the full body content and metadata of a knowledge article\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-knowledge.get-knowledge-article-detail\n      with:\n        articleId: tools.articleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-knowledge-articles\n      description: Search knowledge articles by keywords, channel, and category filters\n    \
  \  hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: salesforce-knowledge.search-knowledge-articles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-article-suggestions-for-case\n      description: Get relevant article suggestions based on case subject or description\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-knowledge.get-suggested-articles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-knowledge-article\n      description: Create a new draft knowledge article\n      hints:\n        readOnly: false\n        destructive: false\n      call: salesforce-knowledge.create-knowledge-article\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-knowledge-article\n      description: Update an existing knowledge article draft\n      hints:\n        readOnly: false\n        idempotent: true\n     \
  \ call: salesforce-knowledge.update-knowledge-article\n      with:\n        versionId: tools.versionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-knowledge-articles\n      description: Publish knowledge article versions to configured channels\n      hints:\n        readOnly: false\n        destructive: false\n      call: salesforce-knowledge.publish-knowledge-articles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-knowledge-article\n      description: Delete a knowledge article draft version\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: salesforce-knowledge.delete-knowledge-article\n      with:\n        versionId: tools.versionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-data-category-groups\n      description: List data category groups used to organize knowledge articles\n      hints:\n        readOnly:\
  \ true\n        idempotent: true\n      call: salesforce-knowledge.list-data-category-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-data-categories\n      description: List categories within a data category group\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-knowledge.list-data-categories\n      with:\n        group: tools.group\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce-knowledge-management/refs/heads/main/capabilities/knowledge-management.yaml
tags:
- Salesforce
- Knowledge Management
- Articles
- Support
- CRM
- Customer Service
tools:
- description: List all knowledge articles in the Salesforce org
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-knowledge-articles
- description: Get metadata for a specific knowledge article by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-knowledge-article
- description: Get the full body content and metadata of a knowledge article
  hints:
    idempotent: true
    readOnly: true
  name: get-article-full-content
- description: Search knowledge articles by keywords, channel, and category filters
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: search-knowledge-articles
- description: Get relevant article suggestions based on case subject or description
  hints:
    idempotent: true
    readOnly: true
  name: get-article-suggestions-for-case
- description: Create a new draft knowledge article
  hints:
    destructive: false
    readOnly: false
  name: create-knowledge-article
- description: Update an existing knowledge article draft
  hints:
    idempotent: true
    readOnly: false
  name: update-knowledge-article
- description: Publish knowledge article versions to configured channels
  hints:
    destructive: false
    readOnly: false
  name: publish-knowledge-articles
- description: Delete a knowledge article draft version
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-knowledge-article
- description: List data category groups used to organize knowledge articles
  hints:
    idempotent: true
    readOnly: true
  name: list-data-category-groups
- description: List categories within a data category group
  hints:
    idempotent: true
    readOnly: true
  name: list-data-categories
---
