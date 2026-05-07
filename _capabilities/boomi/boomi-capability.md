---
categories: []
consumed_apis: []
description: 'The Boomi DataHub REST API provides programmatic access to master data management operations. It consists of two layers: the Platform API for managing repositories, models, sources, and domains; and the Repository API for querying and manipulating golden records and staged entities. The Platform API uses Basic Authentication while the Repository API supports JWT authentication. Requests are subject to usage limits based on licensed connectors (1,000 times the number of connectors per 24 hours).'
layout: capability
name: Boomi DataHub API
operations:
- description: Boomi List repositories
  method: GET
  name: listrepositories
  path: /repositories
- description: Boomi Create a repository
  method: POST
  name: createrepository
  path: /repositories
- description: Boomi Get a repository
  method: GET
  name: getrepository
  path: /repositories/{repositoryId}
- description: Boomi Delete a repository
  method: DELETE
  name: deleterepository
  path: /repositories/{repositoryId}
- description: Boomi List models
  method: GET
  name: listmodels
  path: /repositories/{repositoryId}/models
- description: Boomi Create a model
  method: POST
  name: createmodel
  path: /repositories/{repositoryId}/models
- description: Boomi Get a model
  method: GET
  name: getmodel
  path: /repositories/{repositoryId}/models/{modelId}
- description: Boomi Delete a model
  method: DELETE
  name: deletemodel
  path: /repositories/{repositoryId}/models/{modelId}
- description: Boomi Publish a model
  method: POST
  name: publishmodel
  path: /repositories/{repositoryId}/models/{modelId}/publish
- description: Boomi List sources
  method: GET
  name: listsources
  path: /repositories/{repositoryId}/sources
- description: Boomi Create a source
  method: POST
  name: createsource
  path: /repositories/{repositoryId}/sources
- description: Boomi List golden records
  method: GET
  name: listgoldenrecords
  path: /repositories/{repositoryId}/universes/{universeId}/records
- description: Boomi List quarantine entries
  method: GET
  name: listquarantineentries
  path: /repositories/{repositoryId}/universes/{universeId}/quarantine
personas: []
provider_name: Boomi
provider_slug: boomi
search_terms:
- integrations
- boomi
- ai agents
- automation
- boomi delete a repository
- api
- createrepository
- platform
- b2b
- listrepositories
- edi
- deleterepository
- listsources
- boomi list golden records
- createmodel
- listquarantineentries
- boomi list quarantine entries
- deletemodel
- boomi list models
- getmodel
- boomi get a repository
- boomi publish a model
- listgoldenrecords
- listmodels
- management
- mft
- boomi list repositories
- boomi list sources
- boomi create a model
- boomi get a model
- boomi delete a model
- publishmodel
- workflows
- data integration
- createsource
- getrepository
- boomi create a source
- boomi create a repository
slug: boomi-capability
source_filename: boomi-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Boomi DataHub API\n  description: 'The Boomi DataHub REST API provides programmatic access to master data management operations. It consists\n    of two layers: the Platform API for managing repositories, models, sources, and domains; and the Repository API for querying\n    and manipulating golden records and staged entities. The Platform API uses Basic Authentication while the Repository API\n    supports JWT authentication. Requests are subject to usage limits based on licensed connectors (1,000 times the number\n    of connectors per 24 hours).'\n  tags:\n  - Boomi\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: boomi\n    baseUri: https://mdh.boomi.com/mdh\n    description: Boomi DataHub API HTTP API.\n    authentication:\n      type: basic\n      username: '{{BOOMI_USERNAME}}'\n      password: '{{BOOMI_PASSWORD}}'\n    resources:\n    - name: repositories\n   \
  \   path: /repositories\n      operations:\n      - name: listrepositories\n        method: GET\n        description: Boomi List repositories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrepository\n        method: POST\n        description: Boomi Create a repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repositoryid\n      path: /repositories/{repositoryId}\n      operations:\n      - name: getrepository\n        method: GET\n        description: Boomi Get a repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterepository\n        method: DELETE\n        description: Boomi Delete a repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: repositories-repositoryid-models\n      path: /repositories/{repositoryId}/models\n      operations:\n      - name: listmodels\n        method: GET\n        description: Boomi List models\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmodel\n        method: POST\n        description: Boomi Create a model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repositoryid-models-modelid\n      path: /repositories/{repositoryId}/models/{modelId}\n      operations:\n      - name: getmodel\n        method: GET\n        description: Boomi Get a model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemodel\n        method: DELETE\n        description:\
  \ Boomi Delete a model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repositoryid-models-modelid-publish\n      path: /repositories/{repositoryId}/models/{modelId}/publish\n      operations:\n      - name: publishmodel\n        method: POST\n        description: Boomi Publish a model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repositoryid-sources\n      path: /repositories/{repositoryId}/sources\n      operations:\n      - name: listsources\n        method: GET\n        description: Boomi List sources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsource\n        method: POST\n        description: Boomi Create a source\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: repositories-repositoryid-universes-universeid-r\n      path: /repositories/{repositoryId}/universes/{universeId}/records\n      operations:\n      - name: listgoldenrecords\n        method: GET\n        description: Boomi List golden records\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          description: Number of records per page.\n        - name: pageToken\n          in: query\n          type: string\n          description: Pagination token from a previous response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repositoryid-universes-universeid-q\n      path: /repositories/{repositoryId}/universes/{universeId}/quarantine\n      operations:\n      - name: listquarantineentries\n        method: GET\n        description: Boomi List quarantine\
  \ entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: boomi-rest\n    description: REST adapter for Boomi DataHub API.\n    resources:\n    - path: /repositories\n      name: listrepositories\n      operations:\n      - method: GET\n        name: listrepositories\n        description: Boomi List repositories\n        call: boomi.listrepositories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories\n      name: createrepository\n      operations:\n      - method: POST\n        name: createrepository\n        description: Boomi Create a repository\n        call: boomi.createrepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryId}\n      name: getrepository\n      operations:\n      - method: GET\n        name: getrepository\n     \
  \   description: Boomi Get a repository\n        call: boomi.getrepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryId}\n      name: deleterepository\n      operations:\n      - method: DELETE\n        name: deleterepository\n        description: Boomi Delete a repository\n        call: boomi.deleterepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryId}/models\n      name: listmodels\n      operations:\n      - method: GET\n        name: listmodels\n        description: Boomi List models\n        call: boomi.listmodels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryId}/models\n      name: createmodel\n      operations:\n      - method: POST\n        name: createmodel\n        description: Boomi Create a model\n        call: boomi.createmodel\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /repositories/{repositoryId}/models/{modelId}\n      name: getmodel\n      operations:\n      - method: GET\n        name: getmodel\n        description: Boomi Get a model\n        call: boomi.getmodel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryId}/models/{modelId}\n      name: deletemodel\n      operations:\n      - method: DELETE\n        name: deletemodel\n        description: Boomi Delete a model\n        call: boomi.deletemodel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryId}/models/{modelId}/publish\n      name: publishmodel\n      operations:\n      - method: POST\n        name: publishmodel\n        description: Boomi Publish a model\n        call: boomi.publishmodel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryId}/sources\n      name:\
  \ listsources\n      operations:\n      - method: GET\n        name: listsources\n        description: Boomi List sources\n        call: boomi.listsources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryId}/sources\n      name: createsource\n      operations:\n      - method: POST\n        name: createsource\n        description: Boomi Create a source\n        call: boomi.createsource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryId}/universes/{universeId}/records\n      name: listgoldenrecords\n      operations:\n      - method: GET\n        name: listgoldenrecords\n        description: Boomi List golden records\n        call: boomi.listgoldenrecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryId}/universes/{universeId}/quarantine\n      name: listquarantineentries\n      operations:\n    \
  \  - method: GET\n        name: listquarantineentries\n        description: Boomi List quarantine entries\n        call: boomi.listquarantineentries\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: boomi-mcp\n    transport: http\n    description: MCP adapter for Boomi DataHub API for AI agent use.\n    tools:\n    - name: listrepositories\n      description: Boomi List repositories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: boomi.listrepositories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrepository\n      description: Boomi Create a repository\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: boomi.createrepository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrepository\n      description: Boomi Get a repository\n \
  \     hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: boomi.getrepository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterepository\n      description: Boomi Delete a repository\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: boomi.deleterepository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmodels\n      description: Boomi List models\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: boomi.listmodels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmodel\n      description: Boomi Create a model\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: boomi.createmodel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmodel\n \
  \     description: Boomi Get a model\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: boomi.getmodel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletemodel\n      description: Boomi Delete a model\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: boomi.deletemodel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publishmodel\n      description: Boomi Publish a model\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: boomi.publishmodel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsources\n      description: Boomi List sources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: boomi.listsources\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: createsource\n      description: Boomi Create a source\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: boomi.createsource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgoldenrecords\n      description: Boomi List golden records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: boomi.listgoldenrecords\n      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: Number of records per page.\n      - name: pageToken\n        type: string\n        description: Pagination token from a previous response.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listquarantineentries\n      description: Boomi List quarantine entries\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: boomi.listquarantineentries\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BOOMI_USERNAME: BOOMI_USERNAME\n    BOOMI_PASSWORD: BOOMI_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/boomi/refs/heads/main/capabilities/boomi-capability.yaml
tags:
- Boomi
- API
tools:
- description: Boomi List repositories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrepositories
- description: Boomi Create a repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrepository
- description: Boomi Get a repository
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrepository
- description: Boomi Delete a repository
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterepository
- description: Boomi List models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmodels
- description: Boomi Create a model
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmodel
- description: Boomi Get a model
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmodel
- description: Boomi Delete a model
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemodel
- description: Boomi Publish a model
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publishmodel
- description: Boomi List sources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsources
- description: Boomi Create a source
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsource
- description: Boomi List golden records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgoldenrecords
- description: Boomi List quarantine entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listquarantineentries
---
