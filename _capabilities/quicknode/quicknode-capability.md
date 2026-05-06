---
categories: []
consumed_apis: []
description: The QuickNode IPFS REST API provides programmatic access to QuickNode's managed IPFS pinning, gateway, and account services. Developers can pin files and CIDs to keep them persistently available on the InterPlanetary File System, manage dedicated gateways for retrieval, and inspect account usage including bandwidth and storage. Authentication is performed using an API key issued from the QuickNode dashboard.
layout: capability
name: QuickNode IPFS REST API
operations:
- description: Upload and pin a file
  method: POST
  name: putobject
  path: /v1/s3/put-object
- description: List pinned objects
  method: GET
  name: listpins
  path: /v1/pinning
- description: Pin an existing CID
  method: POST
  name: pinbycid
  path: /v1/pinning
- description: Get a pin by request id
  method: GET
  name: getpin
  path: /v1/pinning/{requestId}
- description: Unpin an object
  method: DELETE
  name: deletepin
  path: /v1/pinning/{requestId}
- description: List gateways
  method: GET
  name: listgateways
  path: /v1/gateways
- description: Create gateway
  method: POST
  name: creategateway
  path: /v1/gateways
- description: Get account usage
  method: GET
  name: getaccountusage
  path: /v1/account/usage
personas: []
provider_name: QuickNode
provider_slug: quicknode
search_terms:
- webhooks
- getpin
- web3
- ipfs
- pinbycid
- pin an existing cid
- blockchain
- infrastructure
- deletepin
- putobject
- key-value store
- getaccountusage
- rpc
- listgateways
- list gateways
- listpins
- get account usage
- api
- get a pin by request id
- list pinned objects
- creategateway
- create gateway
- quicknode
- unpin an object
- upload and pin a file
- streaming data
slug: quicknode-capability
source_filename: quicknode-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: QuickNode IPFS REST API\n  description: The QuickNode IPFS REST API provides programmatic access to QuickNode's managed IPFS pinning, gateway, and\n    account services. Developers can pin files and CIDs to keep them persistently available on the InterPlanetary File System,\n    manage dedicated gateways for retrieval, and inspect account usage including bandwidth and storage. Authentication is\n    performed using an API key issued from the QuickNode dashboard.\n  tags:\n  - Quicknode\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: quicknode\n    baseUri: https://api.quicknode.com/ipfs/rest\n    description: QuickNode IPFS REST API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{QUICKNODE_TOKEN}}'\n    resources:\n    - name: v1-s3-put-object\n      path: /v1/s3/put-object\n      operations:\n      - name:\
  \ putobject\n        method: POST\n        description: Upload and pin a file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-pinning\n      path: /v1/pinning\n      operations:\n      - name: listpins\n        method: GET\n        description: List pinned objects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: pinbycid\n        method: POST\n        description: Pin an existing CID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-pinning-requestid\n      path: /v1/pinning/{requestId}\n      operations:\n      - name: getpin\n        method: GET\n        description: Get a pin by request id\n        inputParameters:\n        - name: requestId\n          in: path\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepin\n        method: DELETE\n        description: Unpin an object\n        inputParameters:\n        - name: requestId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-gateways\n      path: /v1/gateways\n      operations:\n      - name: listgateways\n        method: GET\n        description: List gateways\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategateway\n        method: POST\n        description: Create gateway\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-account-usage\n      path:\
  \ /v1/account/usage\n      operations:\n      - name: getaccountusage\n        method: GET\n        description: Get account usage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: quicknode-rest\n    description: REST adapter for QuickNode IPFS REST API.\n    resources:\n    - path: /v1/s3/put-object\n      name: putobject\n      operations:\n      - method: POST\n        name: putobject\n        description: Upload and pin a file\n        call: quicknode.putobject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pinning\n      name: listpins\n      operations:\n      - method: GET\n        name: listpins\n        description: List pinned objects\n        call: quicknode.listpins\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pinning\n      name: pinbycid\n      operations:\n\
  \      - method: POST\n        name: pinbycid\n        description: Pin an existing CID\n        call: quicknode.pinbycid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pinning/{requestId}\n      name: getpin\n      operations:\n      - method: GET\n        name: getpin\n        description: Get a pin by request id\n        call: quicknode.getpin\n        with:\n          requestId: rest.requestId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pinning/{requestId}\n      name: deletepin\n      operations:\n      - method: DELETE\n        name: deletepin\n        description: Unpin an object\n        call: quicknode.deletepin\n        with:\n          requestId: rest.requestId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gateways\n      name: listgateways\n      operations:\n      - method: GET\n        name: listgateways\n        description: List gateways\n\
  \        call: quicknode.listgateways\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gateways\n      name: creategateway\n      operations:\n      - method: POST\n        name: creategateway\n        description: Create gateway\n        call: quicknode.creategateway\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/account/usage\n      name: getaccountusage\n      operations:\n      - method: GET\n        name: getaccountusage\n        description: Get account usage\n        call: quicknode.getaccountusage\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: quicknode-mcp\n    transport: http\n    description: MCP adapter for QuickNode IPFS REST API for AI agent use.\n    tools:\n    - name: putobject\n      description: Upload and pin a file\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: quicknode.putobject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpins\n      description: List pinned objects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quicknode.listpins\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pinbycid\n      description: Pin an existing CID\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: quicknode.pinbycid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpin\n      description: Get a pin by request id\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quicknode.getpin\n      with:\n        requestId: tools.requestId\n      inputParameters:\n      - name: requestId\n        type: string\n        description: requestId\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: deletepin\n      description: Unpin an object\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: quicknode.deletepin\n      with:\n        requestId: tools.requestId\n      inputParameters:\n      - name: requestId\n        type: string\n        description: requestId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgateways\n      description: List gateways\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quicknode.listgateways\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategateway\n      description: Create gateway\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: quicknode.creategateway\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ getaccountusage\n      description: Get account usage\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quicknode.getaccountusage\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    QUICKNODE_TOKEN: QUICKNODE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/quicknode/refs/heads/main/capabilities/quicknode-capability.yaml
tags:
- Quicknode
- API
tools:
- description: Upload and pin a file
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: putobject
- description: List pinned objects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpins
- description: Pin an existing CID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pinbycid
- description: Get a pin by request id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpin
- description: Unpin an object
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepin
- description: List gateways
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgateways
- description: Create gateway
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategateway
- description: Get account usage
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountusage
---
