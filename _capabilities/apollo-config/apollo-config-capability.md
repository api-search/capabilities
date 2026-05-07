---
categories: []
consumed_apis: []
description: Apollo Open API for configuration management including app management, namespace management, configuration publishing, and release management. Apollo provides centralized configuration management for distributed systems with real-time push, versioning, and gray release support.
layout: capability
name: Apollo Config Open API
operations:
- description: List all apps
  method: GET
  name: listapps
  path: /openapi/v1/apps
- description: Get app info
  method: GET
  name: getapp
  path: /openapi/v1/apps/{appId}
- description: Get environments and clusters
  method: GET
  name: getenvclusters
  path: /openapi/v1/apps/{appId}/envclusters
- description: Get cluster info
  method: GET
  name: getcluster
  path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}
- description: Create a cluster
  method: POST
  name: createcluster
  path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}
- description: List namespaces
  method: GET
  name: listnamespaces
  path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces
- description: Create a namespace
  method: POST
  name: createnamespace
  path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces
- description: Get namespace info
  method: GET
  name: getnamespace
  path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}
- description: Get namespace lock info
  method: GET
  name: getnamespacelock
  path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/lock
- description: List configuration items
  method: GET
  name: listitems
  path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/items
- description: Create a configuration item
  method: POST
  name: createitem
  path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/items
- description: Get a configuration item
  method: GET
  name: getitem
  path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/items/{key}
- description: Update a configuration item
  method: PUT
  name: updateitem
  path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/items/{key}
- description: Delete a configuration item
  method: DELETE
  name: deleteitem
  path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/items/{key}
- description: Get latest release
  method: GET
  name: getlatestrelease
  path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/releases/latest
- description: Publish a release
  method: POST
  name: createrelease
  path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/releases
- description: Rollback a release
  method: PUT
  name: rollbackrelease
  path: /openapi/v1/envs/{env}/releases/{releaseId}/rollback
- description: Create a gray release
  method: POST
  name: creategrayrelease
  path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/gray-del-releases
personas: []
provider_name: Apollo Config
provider_slug: apollo-config
search_terms:
- updateitem
- get namespace lock info
- distributed systems
- listitems
- getcluster
- getnamespace
- api
- createcluster
- get environments and clusters
- java
- create a namespace
- open source
- ctrip
- getlatestrelease
- create a configuration item
- publish a release
- delete a configuration item
- config
- get app info
- creategrayrelease
- apollo
- get a configuration item
- rollbackrelease
- getitem
- configuration management
- list all apps
- create a cluster
- get namespace info
- create a gray release
- update a configuration item
- deleteitem
- createnamespace
- list namespaces
- getapp
- real-time configuration
- createitem
- list configuration items
- apache 2.0
- createrelease
- rollback a release
- listapps
- listnamespaces
- microservices
- get latest release
- getenvclusters
- getnamespacelock
- get cluster info
slug: apollo-config-capability
source_filename: apollo-config-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apollo Config Open API\n  description: Apollo Open API for configuration management including app management, namespace management, configuration\n    publishing, and release management. Apollo provides centralized configuration management for distributed systems with\n    real-time push, versioning, and gray release support.\n  tags:\n  - Apollo\n  - Config\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: apollo-config\n    baseUri: http://localhost:8070\n    description: Apollo Config Open API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{APOLLO_CONFIG_TOKEN}}'\n    resources:\n    - name: openapi-v1-apps\n      path: /openapi/v1/apps\n      operations:\n      - name: listapps\n        method: GET\n        description: List all apps\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: openapi-v1-apps-appid\n      path: /openapi/v1/apps/{appId}\n      operations:\n      - name: getapp\n        method: GET\n        description: Get app info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: openapi-v1-apps-appid-envclusters\n      path: /openapi/v1/apps/{appId}/envclusters\n      operations:\n      - name: getenvclusters\n        method: GET\n        description: Get environments and clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: openapi-v1-envs-env-apps-appid-clusters-clustern\n      path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}\n      operations:\n      - name: getcluster\n        method: GET\n        description: Get cluster info\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createcluster\n        method: POST\n        description: Create a cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: openapi-v1-envs-env-apps-appid-clusters-clustern\n      path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces\n      operations:\n      - name: listnamespaces\n        method: GET\n        description: List namespaces\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespace\n        method: POST\n        description: Create a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: openapi-v1-envs-env-apps-appid-clusters-clustern\n      path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}\n\
  \      operations:\n      - name: getnamespace\n        method: GET\n        description: Get namespace info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: openapi-v1-envs-env-apps-appid-clusters-clustern\n      path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/lock\n      operations:\n      - name: getnamespacelock\n        method: GET\n        description: Get namespace lock info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: openapi-v1-envs-env-apps-appid-clusters-clustern\n      path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/items\n      operations:\n      - name: listitems\n        method: GET\n        description: List configuration items\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: createitem\n        method: POST\n        description: Create a configuration item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: openapi-v1-envs-env-apps-appid-clusters-clustern\n      path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/items/{key}\n      operations:\n      - name: getitem\n        method: GET\n        description: Get a configuration item\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateitem\n        method: PUT\n        description: Update a configuration item\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n    \
  \      required: true\n        - name: createIfNotExists\n          in: query\n          type: boolean\n          description: Create item if it does not exist\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteitem\n        method: DELETE\n        description: Delete a configuration item\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n        - name: operator\n          in: query\n          type: string\n          required: true\n          description: Operator (user) performing the delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: openapi-v1-envs-env-apps-appid-clusters-clustern\n      path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/releases/latest\n      operations:\n      - name:\
  \ getlatestrelease\n        method: GET\n        description: Get latest release\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: openapi-v1-envs-env-apps-appid-clusters-clustern\n      path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/releases\n      operations:\n      - name: createrelease\n        method: POST\n        description: Publish a release\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: openapi-v1-envs-env-releases-releaseid-rollback\n      path: /openapi/v1/envs/{env}/releases/{releaseId}/rollback\n      operations:\n      - name: rollbackrelease\n        method: PUT\n        description: Rollback a release\n        inputParameters:\n        - name: releaseId\n          in: path\n          type: integer\n          required: true\n        - name: operator\n\
  \          in: query\n          type: string\n          required: true\n          description: Operator performing the rollback\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: openapi-v1-envs-env-apps-appid-clusters-clustern\n      path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/gray-del-releases\n      operations:\n      - name: creategrayrelease\n        method: POST\n        description: Create a gray release\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: apollo-config-rest\n    description: REST adapter for Apollo Config Open API.\n    resources:\n    - path: /openapi/v1/apps\n      name: listapps\n      operations:\n      - method: GET\n        name: listapps\n        description: List all apps\n        call:\
  \ apollo-config.listapps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /openapi/v1/apps/{appId}\n      name: getapp\n      operations:\n      - method: GET\n        name: getapp\n        description: Get app info\n        call: apollo-config.getapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /openapi/v1/apps/{appId}/envclusters\n      name: getenvclusters\n      operations:\n      - method: GET\n        name: getenvclusters\n        description: Get environments and clusters\n        call: apollo-config.getenvclusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}\n      name: getcluster\n      operations:\n      - method: GET\n        name: getcluster\n        description: Get cluster info\n        call: apollo-config.getcluster\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}\n      name: createcluster\n      operations:\n      - method: POST\n        name: createcluster\n        description: Create a cluster\n        call: apollo-config.createcluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces\n      name: listnamespaces\n      operations:\n      - method: GET\n        name: listnamespaces\n        description: List namespaces\n        call: apollo-config.listnamespaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces\n      name: createnamespace\n      operations:\n      - method: POST\n        name: createnamespace\n        description: Create a namespace\n        call: apollo-config.createnamespace\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}\n      name: getnamespace\n      operations:\n      - method: GET\n        name: getnamespace\n        description: Get namespace info\n        call: apollo-config.getnamespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/lock\n      name: getnamespacelock\n      operations:\n      - method: GET\n        name: getnamespacelock\n        description: Get namespace lock info\n        call: apollo-config.getnamespacelock\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/items\n      name: listitems\n      operations:\n      - method: GET\n        name: listitems\n        description: List configuration items\n        call: apollo-config.listitems\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/items\n      name: createitem\n      operations:\n      - method: POST\n        name: createitem\n        description: Create a configuration item\n        call: apollo-config.createitem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/items/{key}\n      name: getitem\n      operations:\n      - method: GET\n        name: getitem\n        description: Get a configuration item\n        call: apollo-config.getitem\n        with:\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/items/{key}\n      name: updateitem\n      operations:\n      - method: PUT\n\
  \        name: updateitem\n        description: Update a configuration item\n        call: apollo-config.updateitem\n        with:\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/items/{key}\n      name: deleteitem\n      operations:\n      - method: DELETE\n        name: deleteitem\n        description: Delete a configuration item\n        call: apollo-config.deleteitem\n        with:\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/releases/latest\n      name: getlatestrelease\n      operations:\n      - method: GET\n        name: getlatestrelease\n        description: Get latest release\n        call: apollo-config.getlatestrelease\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n    - path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/releases\n      name: createrelease\n      operations:\n      - method: POST\n        name: createrelease\n        description: Publish a release\n        call: apollo-config.createrelease\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /openapi/v1/envs/{env}/releases/{releaseId}/rollback\n      name: rollbackrelease\n      operations:\n      - method: PUT\n        name: rollbackrelease\n        description: Rollback a release\n        call: apollo-config.rollbackrelease\n        with:\n          releaseId: rest.releaseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /openapi/v1/envs/{env}/apps/{appId}/clusters/{clusterName}/namespaces/{namespaceName}/gray-del-releases\n      name: creategrayrelease\n      operations:\n      - method: POST\n        name: creategrayrelease\n        description:\
  \ Create a gray release\n        call: apollo-config.creategrayrelease\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: apollo-config-mcp\n    transport: http\n    description: MCP adapter for Apollo Config Open API for AI agent use.\n    tools:\n    - name: listapps\n      description: List all apps\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apollo-config.listapps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapp\n      description: Get app info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apollo-config.getapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getenvclusters\n      description: Get environments and clusters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ apollo-config.getenvclusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcluster\n      description: Get cluster info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apollo-config.getcluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcluster\n      description: Create a cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apollo-config.createcluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnamespaces\n      description: List namespaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apollo-config.listnamespaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespace\n      description: Create a namespace\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: apollo-config.createnamespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnamespace\n      description: Get namespace info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apollo-config.getnamespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnamespacelock\n      description: Get namespace lock info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apollo-config.getnamespacelock\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listitems\n      description: List configuration items\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apollo-config.listitems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createitem\n\
  \      description: Create a configuration item\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apollo-config.createitem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getitem\n      description: Get a configuration item\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apollo-config.getitem\n      with:\n        key: tools.key\n      inputParameters:\n      - name: key\n        type: string\n        description: key\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateitem\n      description: Update a configuration item\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: apollo-config.updateitem\n      with:\n        key: tools.key\n        createIfNotExists: tools.createIfNotExists\n      inputParameters:\n      - name: key\n  \
  \      type: string\n        description: key\n        required: true\n      - name: createIfNotExists\n        type: boolean\n        description: Create item if it does not exist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteitem\n      description: Delete a configuration item\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: apollo-config.deleteitem\n      with:\n        key: tools.key\n        operator: tools.operator\n      inputParameters:\n      - name: key\n        type: string\n        description: key\n        required: true\n      - name: operator\n        type: string\n        description: Operator (user) performing the delete\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlatestrelease\n      description: Get latest release\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n  \
  \    call: apollo-config.getlatestrelease\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrelease\n      description: Publish a release\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apollo-config.createrelease\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: rollbackrelease\n      description: Rollback a release\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: apollo-config.rollbackrelease\n      with:\n        releaseId: tools.releaseId\n        operator: tools.operator\n      inputParameters:\n      - name: releaseId\n        type: integer\n        description: releaseId\n        required: true\n      - name: operator\n        type: string\n        description: Operator performing the rollback\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategrayrelease\n\
  \      description: Create a gray release\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: apollo-config.creategrayrelease\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    APOLLO_CONFIG_TOKEN: APOLLO_CONFIG_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apollo-config/refs/heads/main/capabilities/apollo-config-capability.yaml
tags:
- Apollo
- Config
- API
tools:
- description: List all apps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapps
- description: Get app info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapp
- description: Get environments and clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvclusters
- description: Get cluster info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcluster
- description: Create a cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcluster
- description: List namespaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespaces
- description: Create a namespace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespace
- description: Get namespace info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnamespace
- description: Get namespace lock info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnamespacelock
- description: List configuration items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listitems
- description: Create a configuration item
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createitem
- description: Get a configuration item
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getitem
- description: Update a configuration item
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateitem
- description: Delete a configuration item
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteitem
- description: Get latest release
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlatestrelease
- description: Publish a release
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrelease
- description: Rollback a release
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: rollbackrelease
- description: Create a gray release
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategrayrelease
---
