---
categories: []
consumed_apis: []
description: Unified workflow capability for deploying and managing serverless workloads on Scaleway, combining Serverless Containers and Serverless Functions. Used by developers and DevOps teams to deploy event-driven applications with pay-per-use pricing, CRON scheduling, and custom domain support on European cloud infrastructure.
layout: capability
name: Scaleway Serverless
operations:
- description: List serverless container namespaces
  method: GET
  name: list-container-namespaces
  path: /v1/container-namespaces
- description: Create a container namespace
  method: POST
  name: create-container-namespace
  path: /v1/container-namespaces
- description: List serverless containers
  method: GET
  name: list-containers
  path: /v1/containers
- description: Deploy a serverless container
  method: POST
  name: create-container
  path: /v1/containers
- description: Get container details
  method: GET
  name: get-container
  path: /v1/containers/{id}
- description: Delete a serverless container
  method: DELETE
  name: delete-container
  path: /v1/containers/{id}
- description: List container triggers
  method: GET
  name: list-container-triggers
  path: /v1/container-triggers
- description: List function namespaces
  method: GET
  name: list-function-namespaces
  path: /v1/function-namespaces
- description: List serverless functions
  method: GET
  name: list-functions
  path: /v1/functions
- description: Create a serverless function
  method: POST
  name: create-function
  path: /v1/functions
- description: Get function details
  method: GET
  name: get-function
  path: /v1/functions/{id}
- description: Delete a serverless function
  method: DELETE
  name: delete-function
  path: /v1/functions/{id}
- description: List CRON triggers
  method: GET
  name: list-crons
  path: /v1/crons
- description: Create a CRON trigger
  method: POST
  name: create-cron
  path: /v1/crons
personas: []
provider_name: Scaleway
provider_slug: scaleway
search_terms:
- delete a serverless function
- get function details
- list function namespaces
- manage a specific serverless container
- list serverless containers
- storage
- cron schedule management
- list cron triggers for serverless functions
- infrastructure
- list crons
- create a cron schedule for a serverless function
- create function
- delete function
- manage a specific function
- serverless
- serverless function management
- list serverless container namespaces
- list container namespaces
- get details of a serverless function
- european cloud
- containers
- serverless container management
- function namespace management
- create a container namespace
- create a cron trigger
- list containers
- cloud computing
- container trigger management
- list deployed serverless containers
- ai
- kubernetes
- get container details
- list serverless functions
- database
- functions
- deploy a serverless container
- faas
- get container
- list triggers for serverless containers
- deploy a new serverless container
- event-driven
- scaleway
- list functions
- create cron
- list cron triggers
- list container triggers
- get function
- delete a serverless container
- delete container
- create container namespace
- create a serverless function
- create a new serverless function
- list serverless function namespaces
- get details of a serverless container
- container namespace management
- create container
slug: serverless
source_filename: serverless.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Scaleway Serverless\n  description: Unified workflow capability for deploying and managing serverless workloads on Scaleway, combining Serverless\n    Containers and Serverless Functions. Used by developers and DevOps teams to deploy event-driven applications with pay-per-use\n    pricing, CRON scheduling, and custom domain support on European cloud infrastructure.\n  tags:\n  - Cloud Computing\n  - Containers\n  - Event-Driven\n  - FaaS\n  - Functions\n  - Scaleway\n  - Serverless\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SCALEWAY_API_KEY: SCALEWAY_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: scaleway-containers\n    baseUri: https://api.scaleway.com\n    description: Scaleway Serverless Containers API\n    authentication:\n      type: apikey\n      key: X-Auth-Token\n      value: '{{SCALEWAY_API_KEY}}'\n      placement: header\n    resources:\n    - name: namespaces\n\
  \      path: /containers/v1/regions/{region}/namespaces\n      description: Container namespace management\n      operations:\n      - name: list-container-namespaces\n        method: GET\n        description: List Container Namespaces\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-container-namespace\n        method: POST\n        description: Create a Container Namespace\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: containers\n      path: /containers/v1/regions/{region}/containers\n\
  \      description: Container management\n      operations:\n      - name: list-containers\n        method: GET\n        description: List Containers\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: namespace_id\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-container\n        method: POST\n        description: Create a Container\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            namespace_id: '{{tools.namespace_id}}'\n            registry_image:\
  \ '{{tools.registry_image}}'\n    - name: container\n      path: /containers/v1/regions/{region}/containers/{container_id}\n      description: Manage a specific container\n      operations:\n      - name: get-container\n        method: GET\n        description: Get Container details\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: container_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-container\n        method: DELETE\n        description: Delete a Container\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: container_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: triggers\n      path: /containers/v1/regions/{region}/triggers\n      description: Container trigger management\n      operations:\n      - name: list-container-triggers\n        method: GET\n        description: List Container Triggers\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: scaleway-functions\n    baseUri: https://api.scaleway.com\n    description: Scaleway Serverless Functions API\n    authentication:\n      type: apikey\n      key: X-Auth-Token\n      value: '{{SCALEWAY_API_KEY}}'\n      placement: header\n    resources:\n    - name: function-namespaces\n      path: /functions/v1beta1/regions/{region}/namespaces\n      description: Function namespace management\n   \
  \   operations:\n      - name: list-function-namespaces\n        method: GET\n        description: List Function Namespaces\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-function-namespace\n        method: POST\n        description: Create a Function Namespace\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: functions\n      path: /functions/v1beta1/regions/{region}/functions\n      description: Function management\n      operations:\n      - name: list-functions\n      \
  \  method: GET\n        description: List Functions\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: namespace_id\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-function\n        method: POST\n        description: Create a Function\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            namespace_id: '{{tools.namespace_id}}'\n            runtime: '{{tools.runtime}}'\n    - name: function\n      path: /functions/v1beta1/regions/{region}/functions/{function_id}\n\
  \      description: Manage a specific function\n      operations:\n      - name: get-function\n        method: GET\n        description: Get Function details\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: function_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-function\n        method: DELETE\n        description: Delete a Function\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: function_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crons\n      path: /functions/v1beta1/regions/{region}/crons\n\
  \      description: CRON trigger management\n      operations:\n      - name: list-crons\n        method: GET\n        description: List CRON Triggers\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-cron\n        method: POST\n        description: Create a CRON Trigger\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            function_id: '{{tools.function_id}}'\n            schedule: '{{tools.schedule}}'\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: scaleway-serverless-api\n    description: Unified REST\
  \ API for Scaleway serverless workload management.\n    resources:\n    - path: /v1/container-namespaces\n      name: container-namespaces\n      description: Container namespace management\n      operations:\n      - method: GET\n        name: list-container-namespaces\n        description: List serverless container namespaces\n        call: scaleway-containers.list-container-namespaces\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-container-namespace\n        description: Create a container namespace\n        call: scaleway-containers.create-container-namespace\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/containers\n      name: containers\n      description: Serverless container management\n      operations:\n      - method: GET\n        name: list-containers\n        description:\
  \ List serverless containers\n        call: scaleway-containers.list-containers\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-container\n        description: Deploy a serverless container\n        call: scaleway-containers.create-container\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/containers/{id}\n      name: container\n      description: Manage a specific serverless container\n      operations:\n      - method: GET\n        name: get-container\n        description: Get container details\n        call: scaleway-containers.get-container\n        with:\n          region: rest.region\n          container_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-container\n        description: Delete a serverless\
  \ container\n        call: scaleway-containers.delete-container\n        with:\n          region: rest.region\n          container_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/container-triggers\n      name: container-triggers\n      description: Container trigger management\n      operations:\n      - method: GET\n        name: list-container-triggers\n        description: List container triggers\n        call: scaleway-containers.list-container-triggers\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/function-namespaces\n      name: function-namespaces\n      description: Function namespace management\n      operations:\n      - method: GET\n        name: list-function-namespaces\n        description: List function namespaces\n        call: scaleway-functions.list-function-namespaces\n        with:\n          region: rest.region\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/functions\n      name: functions\n      description: Serverless function management\n      operations:\n      - method: GET\n        name: list-functions\n        description: List serverless functions\n        call: scaleway-functions.list-functions\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-function\n        description: Create a serverless function\n        call: scaleway-functions.create-function\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/functions/{id}\n      name: function\n      description: Manage a specific function\n      operations:\n      - method: GET\n        name: get-function\n        description: Get function details\n        call: scaleway-functions.get-function\n        with:\n          region:\
  \ rest.region\n          function_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-function\n        description: Delete a serverless function\n        call: scaleway-functions.delete-function\n        with:\n          region: rest.region\n          function_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/crons\n      name: crons\n      description: CRON schedule management\n      operations:\n      - method: GET\n        name: list-crons\n        description: List CRON triggers\n        call: scaleway-functions.list-crons\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-cron\n        description: Create a CRON trigger\n        call: scaleway-functions.create-cron\n        with:\n          region: rest.region\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: scaleway-serverless-mcp\n    transport: http\n    description: MCP server for AI-assisted Scaleway serverless workload management.\n    tools:\n    - name: list-container-namespaces\n      description: List serverless container namespaces\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-containers.list-container-namespaces\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-containers\n      description: List deployed serverless containers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-containers.list-containers\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-container\n      description: Deploy a new serverless container\n      hints:\n        readOnly: false\n \
  \       destructive: false\n        idempotent: false\n      call: scaleway-containers.create-container\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-container\n      description: Get details of a serverless container\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scaleway-containers.get-container\n      with:\n        region: tools.region\n        container_id: tools.container_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-container\n      description: Delete a serverless container\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: scaleway-containers.delete-container\n      with:\n        region: tools.region\n        container_id: tools.container_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-container-triggers\n      description: List\
  \ triggers for serverless containers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-containers.list-container-triggers\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-function-namespaces\n      description: List serverless function namespaces\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-functions.list-function-namespaces\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-functions\n      description: List serverless functions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-functions.list-functions\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-function\n      description: Create a new serverless function\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: scaleway-functions.create-function\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-function\n      description: Get details of a serverless function\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scaleway-functions.get-function\n      with:\n        region: tools.region\n        function_id: tools.function_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-function\n      description: Delete a serverless function\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: scaleway-functions.delete-function\n      with:\n        region: tools.region\n        function_id: tools.function_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-crons\n      description: List CRON triggers for\
  \ serverless functions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-functions.list-crons\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cron\n      description: Create a CRON schedule for a serverless function\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scaleway-functions.create-cron\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/scaleway/refs/heads/main/capabilities/serverless.yaml
tags:
- Cloud Computing
- Containers
- Event-Driven
- FaaS
- Functions
- Scaleway
- Serverless
tools:
- description: List serverless container namespaces
  hints:
    openWorld: true
    readOnly: true
  name: list-container-namespaces
- description: List deployed serverless containers
  hints:
    openWorld: true
    readOnly: true
  name: list-containers
- description: Deploy a new serverless container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-container
- description: Get details of a serverless container
  hints:
    openWorld: false
    readOnly: true
  name: get-container
- description: Delete a serverless container
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-container
- description: List triggers for serverless containers
  hints:
    openWorld: true
    readOnly: true
  name: list-container-triggers
- description: List serverless function namespaces
  hints:
    openWorld: true
    readOnly: true
  name: list-function-namespaces
- description: List serverless functions
  hints:
    openWorld: true
    readOnly: true
  name: list-functions
- description: Create a new serverless function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-function
- description: Get details of a serverless function
  hints:
    openWorld: false
    readOnly: true
  name: get-function
- description: Delete a serverless function
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-function
- description: List CRON triggers for serverless functions
  hints:
    openWorld: true
    readOnly: true
  name: list-crons
- description: Create a CRON schedule for a serverless function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-cron
---
