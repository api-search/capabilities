---
categories: []
consumed_apis: []
description: The Document360 API provides programmatic access to manage knowledge base projects, articles, categories, drives, files, users, and teams. It enables integrating Document360 documentation workflows into CI/CD pipelines and external applications.
layout: capability
name: Document360 API
operations:
- description: List Project Versions
  method: GET
  name: listprojectversions
  path: /ProjectVersions
- description: List Articles
  method: GET
  name: listarticles
  path: /Articles
- description: Create Article
  method: POST
  name: createarticle
  path: /Articles
- description: Get Article
  method: GET
  name: getarticle
  path: /Articles/{id}
- description: Update Article
  method: PUT
  name: updatearticle
  path: /Articles/{id}
- description: Delete Article
  method: DELETE
  name: deletearticle
  path: /Articles/{id}
- description: List Categories
  method: GET
  name: listcategories
  path: /Categories
- description: Create Category
  method: POST
  name: createcategory
  path: /Categories
- description: Get Category
  method: GET
  name: getcategory
  path: /Categories/{id}
- description: Update Category
  method: PUT
  name: updatecategory
  path: /Categories/{id}
- description: Delete Category
  method: DELETE
  name: deletecategory
  path: /Categories/{id}
- description: List Drive Folders
  method: GET
  name: listdrivefolders
  path: /Drive/Folders
- description: List Drive Files
  method: GET
  name: listdrivefiles
  path: /Drive/Files
- description: List Users
  method: GET
  name: listusers
  path: /Users
- description: List Teams
  method: GET
  name: listteams
  path: /Teams
personas: []
provider_name: Document360
provider_slug: document360
search_terms:
- create category
- listarticles
- getarticle
- update article
- listcategories
- get article
- api
- document360
- getcategory
- updatecategory
- list drive folders
- saas
- list project versions
- documentation
- list teams
- list categories
- deletearticle
- knowledge base
- listprojectversions
- createarticle
- list users
- update category
- listdrivefolders
- list articles
- updatearticle
- get category
- create article
- listteams
- deletecategory
- list drive files
- delete category
- listusers
- delete article
- createcategory
- listdrivefiles
slug: document360-capability
source_filename: document360-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Document360 API\n  description: The Document360 API provides programmatic access to manage knowledge base projects, articles, categories, drives,\n    files, users, and teams. It enables integrating Document360 documentation workflows into CI/CD pipelines and external\n    applications.\n  tags:\n  - Document360\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: document360\n    baseUri: https://apihub.document360.io/v2\n    description: Document360 API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: api_token\n      value: '{{DOCUMENT360_TOKEN}}'\n    resources:\n    - name: projectversions\n      path: /ProjectVersions\n      operations:\n      - name: listprojectversions\n        method: GET\n        description: List Project Versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: articles\n      path: /Articles\n      operations:\n      - name: listarticles\n        method: GET\n        description: List Articles\n        inputParameters:\n        - name: projectVersionId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createarticle\n        method: POST\n        description: Create Article\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: articles-id\n      path: /Articles/{id}\n      operations:\n      - name: getarticle\n        method: GET\n        description: Get Article\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n      - name: updatearticle\n        method: PUT\n        description: Update Article\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletearticle\n        method: DELETE\n        description: Delete Article\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories\n      path: /Categories\n      operations:\n      - name: listcategories\n        method: GET\n        description: List Categories\n        inputParameters:\n        - name: projectVersionId\n          in: query\n          type: string\n          required: true\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcategory\n        method: POST\n        description: Create Category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories-id\n      path: /Categories/{id}\n      operations:\n      - name: getcategory\n        method: GET\n        description: Get Category\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecategory\n        method: PUT\n        description: Update Category\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deletecategory\n        method: DELETE\n        description: Delete Category\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: drive-folders\n      path: /Drive/Folders\n      operations:\n      - name: listdrivefolders\n        method: GET\n        description: List Drive Folders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: drive-files\n      path: /Drive/Files\n      operations:\n      - name: listdrivefiles\n        method: GET\n        description: List Drive Files\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n\
  \      path: /Users\n      operations:\n      - name: listusers\n        method: GET\n        description: List Users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /Teams\n      operations:\n      - name: listteams\n        method: GET\n        description: List Teams\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: document360-rest\n    description: REST adapter for Document360 API.\n    resources:\n    - path: /ProjectVersions\n      name: listprojectversions\n      operations:\n      - method: GET\n        name: listprojectversions\n        description: List Project Versions\n        call: document360.listprojectversions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Articles\n      name: listarticles\n\
  \      operations:\n      - method: GET\n        name: listarticles\n        description: List Articles\n        call: document360.listarticles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Articles\n      name: createarticle\n      operations:\n      - method: POST\n        name: createarticle\n        description: Create Article\n        call: document360.createarticle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Articles/{id}\n      name: getarticle\n      operations:\n      - method: GET\n        name: getarticle\n        description: Get Article\n        call: document360.getarticle\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Articles/{id}\n      name: updatearticle\n      operations:\n      - method: PUT\n        name: updatearticle\n        description: Update Article\n        call: document360.updatearticle\n    \
  \    with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Articles/{id}\n      name: deletearticle\n      operations:\n      - method: DELETE\n        name: deletearticle\n        description: Delete Article\n        call: document360.deletearticle\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Categories\n      name: listcategories\n      operations:\n      - method: GET\n        name: listcategories\n        description: List Categories\n        call: document360.listcategories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Categories\n      name: createcategory\n      operations:\n      - method: POST\n        name: createcategory\n        description: Create Category\n        call: document360.createcategory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Categories/{id}\n\
  \      name: getcategory\n      operations:\n      - method: GET\n        name: getcategory\n        description: Get Category\n        call: document360.getcategory\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Categories/{id}\n      name: updatecategory\n      operations:\n      - method: PUT\n        name: updatecategory\n        description: Update Category\n        call: document360.updatecategory\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Categories/{id}\n      name: deletecategory\n      operations:\n      - method: DELETE\n        name: deletecategory\n        description: Delete Category\n        call: document360.deletecategory\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Drive/Folders\n      name: listdrivefolders\n      operations:\n\
  \      - method: GET\n        name: listdrivefolders\n        description: List Drive Folders\n        call: document360.listdrivefolders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Drive/Files\n      name: listdrivefiles\n      operations:\n      - method: GET\n        name: listdrivefiles\n        description: List Drive Files\n        call: document360.listdrivefiles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: List Users\n        call: document360.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Teams\n      name: listteams\n      operations:\n      - method: GET\n        name: listteams\n        description: List Teams\n        call: document360.listteams\n        outputParameters:\n        - type: object\n          mapping: $.\n  -\
  \ type: mcp\n    port: 9090\n    namespace: document360-mcp\n    transport: http\n    description: MCP adapter for Document360 API for AI agent use.\n    tools:\n    - name: listprojectversions\n      description: List Project Versions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: document360.listprojectversions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listarticles\n      description: List Articles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: document360.listarticles\n      with:\n        projectVersionId: tools.projectVersionId\n      inputParameters:\n      - name: projectVersionId\n        type: string\n        description: projectVersionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createarticle\n      description: Create Article\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: document360.createarticle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getarticle\n      description: Get Article\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: document360.getarticle\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatearticle\n      description: Update Article\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: document360.updatearticle\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletearticle\n\
  \      description: Delete Article\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: document360.deletearticle\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcategories\n      description: List Categories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: document360.listcategories\n      with:\n        projectVersionId: tools.projectVersionId\n      inputParameters:\n      - name: projectVersionId\n        type: string\n        description: projectVersionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcategory\n      description: Create Category\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: document360.createcategory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcategory\n      description: Get Category\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: document360.getcategory\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecategory\n      description: Update Category\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: document360.updatecategory\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecategory\n      description: Delete Category\n  \
  \    hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: document360.deletecategory\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdrivefolders\n      description: List Drive Folders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: document360.listdrivefolders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdrivefiles\n      description: List Drive Files\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: document360.listdrivefiles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: List Users\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: document360.listusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listteams\n      description: List Teams\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: document360.listteams\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    DOCUMENT360_TOKEN: DOCUMENT360_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/document360/refs/heads/main/capabilities/document360-capability.yaml
tags:
- Document360
- API
tools:
- description: List Project Versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojectversions
- description: List Articles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listarticles
- description: Create Article
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createarticle
- description: Get Article
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getarticle
- description: Update Article
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatearticle
- description: Delete Article
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletearticle
- description: List Categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcategories
- description: Create Category
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcategory
- description: Get Category
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcategory
- description: Update Category
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecategory
- description: Delete Category
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecategory
- description: List Drive Folders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdrivefolders
- description: List Drive Files
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdrivefiles
- description: List Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: List Teams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listteams
---
