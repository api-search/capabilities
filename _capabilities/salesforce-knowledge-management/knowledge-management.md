---
categories: []
consumed_apis:
- salesforce-knowledge
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
- knowledge article search
- create a knowledge article draft
- full article content
- get full article content
- publish article versions
- list all knowledge articles in the salesforce org
- article suggestions for cases
- get a knowledge article
- get article detail
- get suggestions
- list knowledge articles
- list data categories
- list categories within a data category group
- update knowledge article
- individual article operations
- search articles
- get article suggestions
- create a new draft knowledge article
- delete a knowledge article draft version
- search knowledge articles by keywords, channel, and category filters
- get knowledge article
- publish articles
- list categories
- salesforce
- articles
- publish knowledge article versions to configured channels
- support
- update an existing knowledge article draft
- crm
- get the full body content and metadata of a knowledge article
- knowledge management
- get article full content
- list data category groups used to organize knowledge articles
- knowledge article management
- documentation
- list data category groups
- publish knowledge articles
- get relevant article suggestions based on case subject or description
- delete knowledge article
- data category management
- get metadata for a specific knowledge article by id
- get article suggestions for case
- customer service
- create knowledge article
- search knowledge articles
- list all knowledge articles
slug: knowledge-management
source_filename: knowledge-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce Knowledge Management\"\n  description: >-\n    Unified workflow capability for managing Salesforce Knowledge articles across\n    the full article lifecycle: creation, editing, categorization, publishing,\n    and surfacing relevant articles for case deflection and agent assistance.\n  tags:\n    - Salesforce\n    - Knowledge Management\n    - Articles\n    - Support\n    - CRM\n    - Customer Service\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: salesforce-knowledge\n      location: ./shared/knowledge-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: knowledge-management-api\n      description: \"Unified REST API for Salesforce Knowledge Management.\"\n      resources:\n        - path: /v1/articles\n          name: articles\n          description:\
  \ \"Knowledge article management\"\n          operations:\n            - method: GET\n              name: list-knowledge-articles\n              description: \"List all knowledge articles\"\n              call: \"salesforce-knowledge.list-knowledge-articles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-knowledge-article\n              description: \"Create a knowledge article draft\"\n              call: \"salesforce-knowledge.create-knowledge-article\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/articles/{articleId}\n          name: article\n          description: \"Individual article operations\"\n          operations:\n            - method: GET\n              name: get-knowledge-article\n              description: \"Get a knowledge article\"\n              call: \"salesforce-knowledge.get-knowledge-article\"\
  \n              with:\n                articleId: \"rest.articleId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/articles/{articleId}/detail\n          name: article-detail\n          description: \"Full article content\"\n          operations:\n            - method: GET\n              name: get-article-detail\n              description: \"Get full article content\"\n              call: \"salesforce-knowledge.get-knowledge-article-detail\"\n              with:\n                articleId: \"rest.articleId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/articles/publish\n          name: publish-articles\n          description: \"Publish article versions\"\n          operations:\n            - method: POST\n              name: publish-articles\n              description: \"Publish knowledge articles\"\n              call: \"salesforce-knowledge.publish-knowledge-articles\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search\n          name: search\n          description: \"Knowledge article search\"\n          operations:\n            - method: GET\n              name: search-articles\n              description: \"Search knowledge articles\"\n              call: \"salesforce-knowledge.search-knowledge-articles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/suggestions\n          name: suggestions\n          description: \"Article suggestions for cases\"\n          operations:\n            - method: GET\n              name: get-suggestions\n              description: \"Get article suggestions\"\n              call: \"salesforce-knowledge.get-suggested-articles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/categories\n          name:\
  \ categories\n          description: \"Data category management\"\n          operations:\n            - method: GET\n              name: list-categories\n              description: \"List data category groups\"\n              call: \"salesforce-knowledge.list-data-category-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: knowledge-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Salesforce Knowledge Management.\"\n      tools:\n        - name: list-knowledge-articles\n          description: \"List all knowledge articles in the Salesforce org\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"salesforce-knowledge.list-knowledge-articles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-knowledge-article\n\
  \          description: \"Get metadata for a specific knowledge article by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-knowledge.get-knowledge-article\"\n          with:\n            articleId: \"tools.articleId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-article-full-content\n          description: \"Get the full body content and metadata of a knowledge article\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-knowledge.get-knowledge-article-detail\"\n          with:\n            articleId: \"tools.articleId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-knowledge-articles\n          description: \"Search knowledge articles by keywords, channel, and category filters\"\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n            openWorld: true\n          call: \"salesforce-knowledge.search-knowledge-articles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-article-suggestions-for-case\n          description: \"Get relevant article suggestions based on case subject or description\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-knowledge.get-suggested-articles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-knowledge-article\n          description: \"Create a new draft knowledge article\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-knowledge.create-knowledge-article\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-knowledge-article\n          description: \"Update an existing knowledge\
  \ article draft\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"salesforce-knowledge.update-knowledge-article\"\n          with:\n            versionId: \"tools.versionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-knowledge-articles\n          description: \"Publish knowledge article versions to configured channels\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-knowledge.publish-knowledge-articles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-knowledge-article\n          description: \"Delete a knowledge article draft version\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"salesforce-knowledge.delete-knowledge-article\"\n          with:\n            versionId:\
  \ \"tools.versionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-data-category-groups\n          description: \"List data category groups used to organize knowledge articles\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-knowledge.list-data-category-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-data-categories\n          description: \"List categories within a data category group\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-knowledge.list-data-categories\"\n          with:\n            group: \"tools.group\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
