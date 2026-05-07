---
categories: []
consumed_apis: []
description: 'The Drupal JSON:API module is a core component that exposes all Drupal entity types and bundles as a standards-compliant JSON:API interface, requiring no configuration to enable. Each entity bundle receives a unique URL path following the pattern /jsonapi/{entity_type}/{bundle}, and the module supports GET, POST, PATCH, and DELETE operations for full CRUD access. It supports filtering, sorting, pagination, sparse fieldsets, includes for relationship resolution, translations, revisions, and file uploads out of the box. All resource identifiers use entity UUIDs rather than numeric IDs. The JSON:'
layout: capability
name: Drupal JSON:API
operations:
- description: List article nodes
  method: GET
  name: listnodearticles
  path: /node/article
- description: Create an article node
  method: POST
  name: createnodearticle
  path: /node/article
- description: Get an article node
  method: GET
  name: getnodearticle
  path: /node/article/{uuid}
- description: Update an article node
  method: PATCH
  name: updatenodearticle
  path: /node/article/{uuid}
- description: Delete an article node
  method: DELETE
  name: deletenodearticle
  path: /node/article/{uuid}
- description: List basic page nodes
  method: GET
  name: listnodepages
  path: /node/page
- description: Get a basic page node
  method: GET
  name: getnodepage
  path: /node/page/{uuid}
- description: List users
  method: GET
  name: listusers
  path: /user/user
- description: Get a user
  method: GET
  name: getuser
  path: /user/user/{uuid}
- description: Update a user
  method: PATCH
  name: updateuser
  path: /user/user/{uuid}
- description: List taxonomy terms by vocabulary
  method: GET
  name: listtaxonomyterms
  path: /taxonomy_term/{vocabulary}
- description: Get a taxonomy term
  method: GET
  name: gettaxonomyterm
  path: /taxonomy_term/{vocabulary}/{uuid}
- description: List file entities
  method: GET
  name: listfiles
  path: /file/file
- description: Get a file entity
  method: GET
  name: getfile
  path: /file/file/{uuid}
- description: Delete a file entity
  method: DELETE
  name: deletefile
  path: /file/file/{uuid}
personas: []
provider_name: drupal
provider_slug: drupal
search_terms:
- listnodepages
- updatenodearticle
- delete an article node
- listtaxonomyterms
- get a file entity
- getnodepage
- api
- getfile
- delete a file entity
- listnodearticles
- getuser
- deletenodearticle
- get a user
- list users
- get a basic page node
- getnodearticle
- get a taxonomy term
- update an article node
- updateuser
- list file entities
- deletefile
- createnodearticle
- list basic page nodes
- listusers
- list article nodes
- drupal
- update a user
- list taxonomy terms by vocabulary
- listfiles
- gettaxonomyterm
- get an article node
- create an article node
slug: drupal-capability
source_filename: drupal-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Drupal JSON:API\n  description: 'The Drupal JSON:API module is a core component that exposes all Drupal entity types and bundles as a standards-compliant\n    JSON:API interface, requiring no configuration to enable. Each entity bundle receives a unique URL path following the\n    pattern /jsonapi/{entity_type}/{bundle}, and the module supports GET, POST, PATCH, and DELETE operations for full CRUD\n    access. It supports filtering, sorting, pagination, sparse fieldsets, includes for relationship resolution, translations,\n    revisions, and file uploads out of the box. All resource identifiers use entity UUIDs rather than numeric IDs. The JSON:'\n  tags:\n  - Drupal\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: drupal\n    baseUri: https://example.com/jsonapi\n    description: Drupal JSON:API HTTP API.\n    authentication:\n      type: basic\n      username: '{{DRUPAL_USERNAME}}'\n\
  \      password: '{{DRUPAL_PASSWORD}}'\n    resources:\n    - name: node-article\n      path: /node/article\n      operations:\n      - name: listnodearticles\n        method: GET\n        description: List article nodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnodearticle\n        method: POST\n        description: Create an article node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-article-uuid\n      path: /node/article/{uuid}\n      operations:\n      - name: getnodearticle\n        method: GET\n        description: Get an article node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatenodearticle\n        method: PATCH\n        description: Update an article node\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenodearticle\n        method: DELETE\n        description: Delete an article node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-page\n      path: /node/page\n      operations:\n      - name: listnodepages\n        method: GET\n        description: List basic page nodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-page-uuid\n      path: /node/page/{uuid}\n      operations:\n      - name: getnodepage\n        method: GET\n        description: Get a basic page node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-user\n      path: /user/user\n      operations:\n      - name: listusers\n\
  \        method: GET\n        description: List users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-user-uuid\n      path: /user/user/{uuid}\n      operations:\n      - name: getuser\n        method: GET\n        description: Get a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PATCH\n        description: Update a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: taxonomy-term-vocabulary\n      path: /taxonomy_term/{vocabulary}\n      operations:\n      - name: listtaxonomyterms\n        method: GET\n        description: List taxonomy terms by vocabulary\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n    - name: taxonomy-term-vocabulary-uuid\n      path: /taxonomy_term/{vocabulary}/{uuid}\n      operations:\n      - name: gettaxonomyterm\n        method: GET\n        description: Get a taxonomy term\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: file-file\n      path: /file/file\n      operations:\n      - name: listfiles\n        method: GET\n        description: List file entities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: file-file-uuid\n      path: /file/file/{uuid}\n      operations:\n      - name: getfile\n        method: GET\n        description: Get a file entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefile\n        method: DELETE\n        description: Delete a file entity\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: drupal-rest\n    description: REST adapter for Drupal JSON:API.\n    resources:\n    - path: /node/article\n      name: listnodearticles\n      operations:\n      - method: GET\n        name: listnodearticles\n        description: List article nodes\n        call: drupal.listnodearticles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/article\n      name: createnodearticle\n      operations:\n      - method: POST\n        name: createnodearticle\n        description: Create an article node\n        call: drupal.createnodearticle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/article/{uuid}\n      name: getnodearticle\n      operations:\n      - method: GET\n        name: getnodearticle\n        description: Get an\
  \ article node\n        call: drupal.getnodearticle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/article/{uuid}\n      name: updatenodearticle\n      operations:\n      - method: PATCH\n        name: updatenodearticle\n        description: Update an article node\n        call: drupal.updatenodearticle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/article/{uuid}\n      name: deletenodearticle\n      operations:\n      - method: DELETE\n        name: deletenodearticle\n        description: Delete an article node\n        call: drupal.deletenodearticle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/page\n      name: listnodepages\n      operations:\n      - method: GET\n        name: listnodepages\n        description: List basic page nodes\n        call: drupal.listnodepages\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /node/page/{uuid}\n      name: getnodepage\n      operations:\n      - method: GET\n        name: getnodepage\n        description: Get a basic page node\n        call: drupal.getnodepage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user/user\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: List users\n        call: drupal.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user/user/{uuid}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Get a user\n        call: drupal.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user/user/{uuid}\n      name: updateuser\n      operations:\n      - method: PATCH\n        name: updateuser\n        description: Update a user\n        call: drupal.updateuser\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n    - path: /taxonomy_term/{vocabulary}\n      name: listtaxonomyterms\n      operations:\n      - method: GET\n        name: listtaxonomyterms\n        description: List taxonomy terms by vocabulary\n        call: drupal.listtaxonomyterms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /taxonomy_term/{vocabulary}/{uuid}\n      name: gettaxonomyterm\n      operations:\n      - method: GET\n        name: gettaxonomyterm\n        description: Get a taxonomy term\n        call: drupal.gettaxonomyterm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /file/file\n      name: listfiles\n      operations:\n      - method: GET\n        name: listfiles\n        description: List file entities\n        call: drupal.listfiles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /file/file/{uuid}\n      name: getfile\n      operations:\n     \
  \ - method: GET\n        name: getfile\n        description: Get a file entity\n        call: drupal.getfile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /file/file/{uuid}\n      name: deletefile\n      operations:\n      - method: DELETE\n        name: deletefile\n        description: Delete a file entity\n        call: drupal.deletefile\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: drupal-mcp\n    transport: http\n    description: MCP adapter for Drupal JSON:API for AI agent use.\n    tools:\n    - name: listnodearticles\n      description: List article nodes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: drupal.listnodearticles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnodearticle\n      description: Create an article node\n      hints:\n        readOnly: false\n   \
  \     destructive: false\n        idempotent: false\n      call: drupal.createnodearticle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnodearticle\n      description: Get an article node\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: drupal.getnodearticle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatenodearticle\n      description: Update an article node\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: drupal.updatenodearticle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenodearticle\n      description: Delete an article node\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: drupal.deletenodearticle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnodepages\n    \
  \  description: List basic page nodes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: drupal.listnodepages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnodepage\n      description: Get a basic page node\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: drupal.getnodepage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: drupal.listusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: Get a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: drupal.getuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateuser\n\
  \      description: Update a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: drupal.updateuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtaxonomyterms\n      description: List taxonomy terms by vocabulary\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: drupal.listtaxonomyterms\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettaxonomyterm\n      description: Get a taxonomy term\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: drupal.gettaxonomyterm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfiles\n      description: List file entities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: drupal.listfiles\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getfile\n      description: Get a file entity\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: drupal.getfile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletefile\n      description: Delete a file entity\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: drupal.deletefile\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    DRUPAL_USERNAME: DRUPAL_USERNAME\n    DRUPAL_PASSWORD: DRUPAL_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/drupal/refs/heads/main/capabilities/drupal-capability.yaml
tags:
- Drupal
- API
tools:
- description: List article nodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnodearticles
- description: Create an article node
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnodearticle
- description: Get an article node
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnodearticle
- description: Update an article node
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatenodearticle
- description: Delete an article node
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenodearticle
- description: List basic page nodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnodepages
- description: Get a basic page node
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnodepage
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Get a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Update a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateuser
- description: List taxonomy terms by vocabulary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtaxonomyterms
- description: Get a taxonomy term
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettaxonomyterm
- description: List file entities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfiles
- description: Get a file entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfile
- description: Delete a file entity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefile
---
