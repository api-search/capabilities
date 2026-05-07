---
categories: []
consumed_apis: []
description: Workflow capability for sharing distributed in-memory objects across computation engines using Vineyard. Supports data scientists and ML engineers managing zero-copy data sharing, object lifecycle, and Kubernetes cluster operations for big data analytics pipelines.
layout: capability
name: Vineyard Data Sharing Workflow
operations:
- description: Connect to a vineyard in-memory server
  method: POST
  name: connect-to-server
  path: /v1/connect
- description: Store an object in vineyard shared memory
  method: POST
  name: put-object
  path: /v1/objects
- description: Retrieve an in-memory object by its ID
  method: GET
  name: get-object
  path: /v1/objects/{objectId}
- description: Remove an object from vineyard memory
  method: DELETE
  name: delete-object
  path: /v1/objects/{objectId}
- description: Inspect metadata including typename, size, and location
  method: GET
  name: get-object-metadata
  path: /v1/objects/{objectId}/metadata
- description: Persist object for cluster-wide visibility
  method: POST
  name: persist-object
  path: /v1/objects/{objectId}/persist
- description: Register a name for an object
  method: POST
  name: put-name
  path: /v1/names
- description: Resolve a name to its ObjectID
  method: GET
  name: get-by-name
  path: /v1/names/{name}
- description: Allocate a raw memory blob for custom data
  method: POST
  name: create-blob
  path: /v1/blobs
- description: Retrieve a raw memory blob by ID
  method: GET
  name: get-blob
  path: /v1/blobs/{objectId}
personas: []
provider_name: Vineyard
provider_slug: vineyard
search_terms:
- retrieve an in-memory object by its id
- put name
- retrieve object
- object metadata inspection
- distributed systems
- connect to vineyard
- delete object
- store object
- lookup object by name
- data engineering
- retrieve a raw memory blob by id
- register object name
- allocate a raw memory blob in vineyard for low-level data operations
- delete a vineyard object from shared memory
- human-readable names for objects
- get object
- object access by id
- distributed in-memory object storage
- cloud native
- name-to-id resolution
- get by name
- store a python object in vineyard shared memory for zero-copy sharing
- create blob
- inspect metadata for a vineyard object including type, size, and cluster location
- metadata management
- persist object for cluster-wide visibility
- associate a human-readable name with a vineyard objectid for discovery
- inspect metadata including typename, size, and location
- connect to a vineyard in-memory server
- get object metadata
- machine learning
- retrieve blob
- blob retrieval
- allocate blob
- big data
- remove object
- kubernetes
- object persistence across cluster instances
- persist object
- register a name for an object
- remove an object from vineyard memory
- resolve a name to its objectid
- retrieve a distributed in-memory object by its objectid
- python
- allocate a raw memory blob for custom data
- zero-copy
- get blob
- make a vineyard object visible across all cluster instances
- cncf
- inspect object metadata
- connect to server
- store an object in vineyard shared memory
- server connection management
- put object
- persist object globally
- resolve a named vineyard object to its objectid
- raw memory blob management
- retrieve a raw memory blob from vineyard storage
- in-memory storage
- connect to a vineyard in-memory data manager server via ipc or tcp
slug: data-sharing-workflow
source_filename: data-sharing-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vineyard Data Sharing Workflow\n  description: Workflow capability for sharing distributed in-memory objects across computation engines using Vineyard. Supports\n    data scientists and ML engineers managing zero-copy data sharing, object lifecycle, and Kubernetes cluster operations\n    for big data analytics pipelines.\n  tags:\n  - Big Data\n  - CNCF\n  - Cloud Native\n  - Data Engineering\n  - Distributed Systems\n  - In-Memory Storage\n  - Machine Learning\n  - Python\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VINEYARD_IPC_SOCKET: VINEYARD_IPC_SOCKET\ncapability:\n  consumes:\n  - type: http\n    namespace: vineyard-client\n    baseUri: http://localhost:9600\n    description: Vineyard in-memory data manager REST interface\n    resources:\n    - name: connection\n      path: /connect\n      description: Connect to the vineyard server\n      operations:\n      - name: connect-to-server\n\
  \        method: POST\n        description: Establish IPC or RPC connection to vineyard\n        inputParameters:\n        - name: socket\n          in: body\n          type: string\n          required: false\n          description: UNIX domain socket path\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: objects\n      path: /objects\n      description: Store and retrieve in-memory objects\n      operations:\n      - name: put-object\n        method: POST\n        description: Store a Python object in vineyard\n        inputParameters:\n        - name: persist\n          in: body\n          type: boolean\n          required: false\n          description: Whether to persist globally\n        - name: name\n          in: body\n          type: string\n          required: false\n          description: Optional name to associate\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: get-object\n        method: GET\n        description: Retrieve an object by ObjectID\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n          description: The vineyard ObjectID\n        - name: fetch\n          in: query\n          type: boolean\n          required: false\n          description: Fetch remote objects via RPC\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-object\n        method: DELETE\n        description: Delete an object from vineyard\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n          description: The ObjectID to delete\n        - name: force\n          in: query\n          type: boolean\n          required: false\n          description: Force deletion\n\
  \        - name: deep\n          in: query\n          type: boolean\n          required: false\n          description: Recursively delete members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata\n      path: /objects/{objectId}/metadata\n      description: Inspect object metadata\n      operations:\n      - name: get-object-metadata\n        method: GET\n        description: Fetch metadata for a vineyard object\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n          description: The ObjectID to inspect\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: persistence\n      path: /objects/{objectId}/persist\n      description: Persist objects for cluster-wide visibility\n      operations:\n      - name: persist-object\n       \
  \ method: POST\n        description: Make an object persistent across vineyard instances\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n          description: The ObjectID to persist\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: names\n      path: /names\n      description: Associate names with objects\n      operations:\n      - name: put-name\n        method: POST\n        description: Associate a human-readable name with an ObjectID\n        inputParameters:\n        - name: object_id\n          in: body\n          type: string\n          required: true\n          description: The ObjectID to name\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: The name string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n      - name: get-by-name\n        method: GET\n        description: Retrieve an ObjectID by name\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name to resolve\n        - name: wait\n          in: query\n          type: boolean\n          required: false\n          description: Block until name is available\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blobs\n      path: /blobs\n      description: Low-level blob operations\n      operations:\n      - name: create-blob\n        method: POST\n        description: Allocate a raw memory blob\n        inputParameters:\n        - name: size\n          in: body\n          type: integer\n          required: true\n          description: Bytes to allocate\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n      - name: get-blob\n        method: GET\n        description: Retrieve a raw memory blob\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n          description: The blob ObjectID\n        - name: remote\n          in: query\n          type: boolean\n          required: false\n          description: Retrieve from remote instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vineyard-data-sharing-api\n    description: Unified REST API for vineyard data sharing and object lifecycle management.\n    resources:\n    - path: /v1/connect\n      name: connection\n      description: Server connection management\n      operations:\n      - method: POST\n        name: connect-to-server\n        description: Connect\
  \ to a vineyard in-memory server\n        call: vineyard-client.connect-to-server\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/objects\n      name: objects\n      description: Distributed in-memory object storage\n      operations:\n      - method: POST\n        name: put-object\n        description: Store an object in vineyard shared memory\n        call: vineyard-client.put-object\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/objects/{objectId}\n      name: object-by-id\n      description: Object access by ID\n      operations:\n      - method: GET\n        name: get-object\n        description: Retrieve an in-memory object by its ID\n        call: vineyard-client.get-object\n        with:\n          objectId: rest.objectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-object\n        description: Remove an object from vineyard\
  \ memory\n        call: vineyard-client.delete-object\n        with:\n          objectId: rest.objectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/objects/{objectId}/metadata\n      name: object-metadata\n      description: Object metadata inspection\n      operations:\n      - method: GET\n        name: get-object-metadata\n        description: Inspect metadata including typename, size, and location\n        call: vineyard-client.get-object-metadata\n        with:\n          objectId: rest.objectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/objects/{objectId}/persist\n      name: object-persistence\n      description: Object persistence across cluster instances\n      operations:\n      - method: POST\n        name: persist-object\n        description: Persist object for cluster-wide visibility\n        call: vineyard-client.persist-object\n        with:\n          objectId: rest.objectId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/names\n      name: names\n      description: Human-readable names for objects\n      operations:\n      - method: POST\n        name: put-name\n        description: Register a name for an object\n        call: vineyard-client.put-name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/names/{name}\n      name: name-lookup\n      description: Name-to-ID resolution\n      operations:\n      - method: GET\n        name: get-by-name\n        description: Resolve a name to its ObjectID\n        call: vineyard-client.get-by-name\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/blobs\n      name: blobs\n      description: Raw memory blob management\n      operations:\n      - method: POST\n        name: create-blob\n        description: Allocate a raw memory blob for custom data\n\
  \        call: vineyard-client.create-blob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/blobs/{objectId}\n      name: blob-by-id\n      description: Blob retrieval\n      operations:\n      - method: GET\n        name: get-blob\n        description: Retrieve a raw memory blob by ID\n        call: vineyard-client.get-blob\n        with:\n          objectId: rest.objectId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vineyard-data-sharing-mcp\n    transport: http\n    description: MCP server for AI-assisted vineyard data sharing and object lifecycle management.\n    tools:\n    - name: connect-to-vineyard\n      description: Connect to a vineyard in-memory data manager server via IPC or TCP\n      hints:\n        readOnly: false\n        idempotent: true\n      call: vineyard-client.connect-to-server\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: store-object\n      description: Store a Python object in vineyard shared memory for zero-copy sharing\n      hints:\n        readOnly: false\n        idempotent: false\n      call: vineyard-client.put-object\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieve-object\n      description: Retrieve a distributed in-memory object by its ObjectID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vineyard-client.get-object\n      with:\n        objectId: tools.objectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inspect-object-metadata\n      description: Inspect metadata for a vineyard object including type, size, and cluster location\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vineyard-client.get-object-metadata\n      with:\n        objectId: tools.objectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-object\n\
  \      description: Delete a vineyard object from shared memory\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: vineyard-client.delete-object\n      with:\n        objectId: tools.objectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: persist-object-globally\n      description: Make a vineyard object visible across all cluster instances\n      hints:\n        readOnly: false\n        idempotent: true\n      call: vineyard-client.persist-object\n      with:\n        objectId: tools.objectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: register-object-name\n      description: Associate a human-readable name with a vineyard ObjectID for discovery\n      hints:\n        readOnly: false\n        idempotent: false\n      call: vineyard-client.put-name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-object-by-name\n      description:\
  \ Resolve a named vineyard object to its ObjectID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vineyard-client.get-by-name\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: allocate-blob\n      description: Allocate a raw memory blob in vineyard for low-level data operations\n      hints:\n        readOnly: false\n        idempotent: false\n      call: vineyard-client.create-blob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieve-blob\n      description: Retrieve a raw memory blob from vineyard storage\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vineyard-client.get-blob\n      with:\n        objectId: tools.objectId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vineyard/refs/heads/main/capabilities/data-sharing-workflow.yaml
tags:
- Big Data
- CNCF
- Cloud Native
- Data Engineering
- Distributed Systems
- In-Memory Storage
- Machine Learning
- Python
tools:
- description: Connect to a vineyard in-memory data manager server via IPC or TCP
  hints:
    idempotent: true
    readOnly: false
  name: connect-to-vineyard
- description: Store a Python object in vineyard shared memory for zero-copy sharing
  hints:
    idempotent: false
    readOnly: false
  name: store-object
- description: Retrieve a distributed in-memory object by its ObjectID
  hints:
    idempotent: true
    readOnly: true
  name: retrieve-object
- description: Inspect metadata for a vineyard object including type, size, and cluster location
  hints:
    idempotent: true
    readOnly: true
  name: inspect-object-metadata
- description: Delete a vineyard object from shared memory
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-object
- description: Make a vineyard object visible across all cluster instances
  hints:
    idempotent: true
    readOnly: false
  name: persist-object-globally
- description: Associate a human-readable name with a vineyard ObjectID for discovery
  hints:
    idempotent: false
    readOnly: false
  name: register-object-name
- description: Resolve a named vineyard object to its ObjectID
  hints:
    idempotent: true
    readOnly: true
  name: lookup-object-by-name
- description: Allocate a raw memory blob in vineyard for low-level data operations
  hints:
    idempotent: false
    readOnly: false
  name: allocate-blob
- description: Retrieve a raw memory blob from vineyard storage
  hints:
    idempotent: true
    readOnly: true
  name: retrieve-blob
---
