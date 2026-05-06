---
categories: []
consumed_apis: []
description: The OpenStreetMap main API v0.6 provides CRUD operations for map data editing including nodes, ways, relations, changesets, and notes. Requires OAuth 2.0 authentication for write operations. Maximum bounding box query area is 0.25 square degrees. Returns XML or JSON. Intended for editing, not high-volume read access.
layout: capability
name: OpenStreetMap API v0.6
operations:
- description: Get map data for a bounding box
  method: GET
  name: getmapdata
  path: /map
- description: Get node by ID
  method: GET
  name: getnode
  path: /node/{id}
- description: Update a node
  method: PUT
  name: updatenode
  path: /node/{id}
- description: Delete a node
  method: DELETE
  name: deletenode
  path: /node/{id}
- description: Create a new node
  method: PUT
  name: createnode
  path: /node/create
- description: Get a specific version of a node
  method: GET
  name: getnodeversion
  path: /node/{id}/{version}
- description: Get way by ID
  method: GET
  name: getway
  path: /way/{id}
- description: Get relation by ID
  method: GET
  name: getrelation
  path: /relation/{id}
- description: Create a changeset
  method: PUT
  name: createchangeset
  path: /changeset/create
- description: Get changeset details
  method: GET
  name: getchangeset
  path: /changeset/{id}
- description: Update changeset tags
  method: PUT
  name: updatechangeset
  path: /changeset/{id}
- description: Close a changeset
  method: PUT
  name: closechangeset
  path: /changeset/{id}/close
- description: Upload an OsmChange document
  method: POST
  name: uploadchangeset
  path: /changeset/{id}/upload
- description: Search notes
  method: GET
  name: searchnotes
  path: /notes
- description: Create a note
  method: POST
  name: createnote
  path: /notes
- description: Get a note
  method: GET
  name: getnote
  path: /notes/{id}
- description: Get authenticated user details
  method: GET
  name: getuserdetails
  path: /user/details
- description: Get API capabilities and limits
  method: GET
  name: getcapabilities
  path: /capabilities
personas: []
provider_name: OpenStreetMap
provider_slug: openstreetmap
search_terms:
- mapping
- getway
- openstreetmap
- geocoding
- searchnotes
- createnote
- geospatial
- getuserdetails
- updatenode
- update a node
- create a changeset
- updatechangeset
- getnode
- getmapdata
- get map data for a bounding box
- get relation by id
- getchangeset
- closechangeset
- uploadchangeset
- getcapabilities
- create a new node
- delete a node
- create a note
- upload an osmchange document
- search notes
- editing
- api
- getnodeversion
- get api capabilities and limits
- createchangeset
- get authenticated user details
- get changeset details
- createnode
- close a changeset
- deletenode
- get a note
- get node by id
- update changeset tags
- getrelation
- getnote
- get a specific version of a node
- get way by id
- open data
slug: openstreetmap-capability
source_filename: openstreetmap-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenStreetMap API v0.6\n  description: The OpenStreetMap main API v0.6 provides CRUD operations for map data editing including nodes, ways, relations,\n    changesets, and notes. Requires OAuth 2.0 authentication for write operations. Maximum bounding box query area is 0.25\n    square degrees. Returns XML or JSON. Intended for editing, not high-volume read access.\n  tags:\n  - Openstreetmap\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: openstreetmap\n    baseUri: https://api.openstreetmap.org/api/0.6\n    description: OpenStreetMap API v0.6 HTTP API.\n    authentication:\n      type: bearer\n      token: '{{OPENSTREETMAP_TOKEN}}'\n    resources:\n    - name: map\n      path: /map\n      operations:\n      - name: getmapdata\n        method: GET\n        description: Get map data for a bounding box\n        inputParameters:\n        - name: bbox\n          in: query\n\
  \          type: string\n          required: true\n          description: Bounding box as min_lon,min_lat,max_lon,max_lat (e.g., -0.489,51.28,0.236,51.686)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-id\n      path: /node/{id}\n      operations:\n      - name: getnode\n        method: GET\n        description: Get node by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatenode\n        method: PUT\n        description: Update a node\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: deletenode\n        method: DELETE\n        description: Delete a node\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-create\n      path: /node/create\n      operations:\n      - name: createnode\n        method: PUT\n        description: Create a new node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-id-version\n      path: /node/{id}/{version}\n      operations:\n      - name: getnodeversion\n        method: GET\n        description: Get a specific version of a node\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        - name: version\n          in: path\n          type: integer\n         \
  \ required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: way-id\n      path: /way/{id}\n      operations:\n      - name: getway\n        method: GET\n        description: Get way by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: relation-id\n      path: /relation/{id}\n      operations:\n      - name: getrelation\n        method: GET\n        description: Get relation by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: changeset-create\n      path: /changeset/create\n   \
  \   operations:\n      - name: createchangeset\n        method: PUT\n        description: Create a changeset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: changeset-id\n      path: /changeset/{id}\n      operations:\n      - name: getchangeset\n        method: GET\n        description: Get changeset details\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        - name: include_discussion\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatechangeset\n        method: PUT\n        description: Update changeset tags\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: changeset-id-close\n      path: /changeset/{id}/close\n      operations:\n      - name: closechangeset\n        method: PUT\n        description: Close a changeset\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: changeset-id-upload\n      path: /changeset/{id}/upload\n      operations:\n      - name: uploadchangeset\n        method: POST\n        description: Upload an OsmChange document\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notes\n      path: /notes\n      operations:\n      - name: searchnotes\n\
  \        method: GET\n        description: Search notes\n        inputParameters:\n        - name: bbox\n          in: query\n          type: string\n          description: Bounding box (min_lon,min_lat,max_lon,max_lat)\n        - name: q\n          in: query\n          type: string\n          description: Free text search\n        - name: status\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        - name: closed\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnote\n        method: POST\n        description: Create a note\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notes-id\n      path: /notes/{id}\n      operations:\n      - name: getnote\n        method: GET\n        description:\
  \ Get a note\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-details\n      path: /user/details\n      operations:\n      - name: getuserdetails\n        method: GET\n        description: Get authenticated user details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: capabilities\n      path: /capabilities\n      operations:\n      - name: getcapabilities\n        method: GET\n        description: Get API capabilities and limits\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: openstreetmap-rest\n    description: REST adapter for OpenStreetMap API v0.6.\n\
  \    resources:\n    - path: /map\n      name: getmapdata\n      operations:\n      - method: GET\n        name: getmapdata\n        description: Get map data for a bounding box\n        call: openstreetmap.getmapdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/{id}\n      name: getnode\n      operations:\n      - method: GET\n        name: getnode\n        description: Get node by ID\n        call: openstreetmap.getnode\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/{id}\n      name: updatenode\n      operations:\n      - method: PUT\n        name: updatenode\n        description: Update a node\n        call: openstreetmap.updatenode\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/{id}\n      name: deletenode\n      operations:\n      - method: DELETE\n        name: deletenode\n\
  \        description: Delete a node\n        call: openstreetmap.deletenode\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/create\n      name: createnode\n      operations:\n      - method: PUT\n        name: createnode\n        description: Create a new node\n        call: openstreetmap.createnode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/{id}/{version}\n      name: getnodeversion\n      operations:\n      - method: GET\n        name: getnodeversion\n        description: Get a specific version of a node\n        call: openstreetmap.getnodeversion\n        with:\n          id: rest.id\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /way/{id}\n      name: getway\n      operations:\n      - method: GET\n        name: getway\n        description: Get way by ID\n        call: openstreetmap.getway\n\
  \        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /relation/{id}\n      name: getrelation\n      operations:\n      - method: GET\n        name: getrelation\n        description: Get relation by ID\n        call: openstreetmap.getrelation\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /changeset/create\n      name: createchangeset\n      operations:\n      - method: PUT\n        name: createchangeset\n        description: Create a changeset\n        call: openstreetmap.createchangeset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /changeset/{id}\n      name: getchangeset\n      operations:\n      - method: GET\n        name: getchangeset\n        description: Get changeset details\n        call: openstreetmap.getchangeset\n        with:\n          id: rest.id\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n    - path: /changeset/{id}\n      name: updatechangeset\n      operations:\n      - method: PUT\n        name: updatechangeset\n        description: Update changeset tags\n        call: openstreetmap.updatechangeset\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /changeset/{id}/close\n      name: closechangeset\n      operations:\n      - method: PUT\n        name: closechangeset\n        description: Close a changeset\n        call: openstreetmap.closechangeset\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /changeset/{id}/upload\n      name: uploadchangeset\n      operations:\n      - method: POST\n        name: uploadchangeset\n        description: Upload an OsmChange document\n        call: openstreetmap.uploadchangeset\n        with:\n          id: rest.id\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n    - path: /notes\n      name: searchnotes\n      operations:\n      - method: GET\n        name: searchnotes\n        description: Search notes\n        call: openstreetmap.searchnotes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /notes\n      name: createnote\n      operations:\n      - method: POST\n        name: createnote\n        description: Create a note\n        call: openstreetmap.createnote\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /notes/{id}\n      name: getnote\n      operations:\n      - method: GET\n        name: getnote\n        description: Get a note\n        call: openstreetmap.getnote\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user/details\n      name: getuserdetails\n      operations:\n      - method: GET\n        name: getuserdetails\n        description:\
  \ Get authenticated user details\n        call: openstreetmap.getuserdetails\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /capabilities\n      name: getcapabilities\n      operations:\n      - method: GET\n        name: getcapabilities\n        description: Get API capabilities and limits\n        call: openstreetmap.getcapabilities\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: openstreetmap-mcp\n    transport: http\n    description: MCP adapter for OpenStreetMap API v0.6 for AI agent use.\n    tools:\n    - name: getmapdata\n      description: Get map data for a bounding box\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstreetmap.getmapdata\n      with:\n        bbox: tools.bbox\n      inputParameters:\n      - name: bbox\n        type: string\n        description: Bounding box as min_lon,min_lat,max_lon,max_lat\
  \ (e.g., -0.489,51.28,0.236,51.686)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnode\n      description: Get node by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstreetmap.getnode\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatenode\n      description: Update a node\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: openstreetmap.updatenode\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenode\n      description: Delete a node\n      hints:\n\
  \        readOnly: false\n        destructive: true\n        idempotent: true\n      call: openstreetmap.deletenode\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnode\n      description: Create a new node\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: openstreetmap.createnode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnodeversion\n      description: Get a specific version of a node\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstreetmap.getnodeversion\n      with:\n        id: tools.id\n        version: tools.version\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      - name:\
  \ version\n        type: integer\n        description: version\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getway\n      description: Get way by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstreetmap.getway\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrelation\n      description: Get relation by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstreetmap.getrelation\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createchangeset\n     \
  \ description: Create a changeset\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: openstreetmap.createchangeset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getchangeset\n      description: Get changeset details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstreetmap.getchangeset\n      with:\n        id: tools.id\n        include_discussion: tools.include_discussion\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      - name: include_discussion\n        type: boolean\n        description: include_discussion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatechangeset\n      description: Update changeset tags\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: openstreetmap.updatechangeset\n\
  \      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: closechangeset\n      description: Close a changeset\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: openstreetmap.closechangeset\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploadchangeset\n      description: Upload an OsmChange document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openstreetmap.uploadchangeset\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchnotes\n      description: Search notes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstreetmap.searchnotes\n      with:\n        bbox: tools.bbox\n        q: tools.q\n        status: tools.status\n        limit: tools.limit\n        closed: tools.closed\n      inputParameters:\n      - name: bbox\n        type: string\n        description: Bounding box (min_lon,min_lat,max_lon,max_lat)\n      - name: q\n        type: string\n        description: Free text search\n      - name: status\n        type: string\n        description: status\n      - name: limit\n        type: integer\n        description: limit\n      - name: closed\n        type: integer\n        description: closed\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnote\n      description: Create a note\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: openstreetmap.createnote\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnote\n      description: Get a note\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstreetmap.getnote\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuserdetails\n      description: Get authenticated user details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openstreetmap.getuserdetails\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcapabilities\n      description: Get API capabilities and limits\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: openstreetmap.getcapabilities\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OPENSTREETMAP_TOKEN: OPENSTREETMAP_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/openstreetmap/refs/heads/main/capabilities/openstreetmap-capability.yaml
tags:
- Openstreetmap
- API
tools:
- description: Get map data for a bounding box
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmapdata
- description: Get node by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnode
- description: Update a node
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatenode
- description: Delete a node
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenode
- description: Create a new node
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createnode
- description: Get a specific version of a node
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnodeversion
- description: Get way by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getway
- description: Get relation by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrelation
- description: Create a changeset
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createchangeset
- description: Get changeset details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchangeset
- description: Update changeset tags
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatechangeset
- description: Close a changeset
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: closechangeset
- description: Upload an OsmChange document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadchangeset
- description: Search notes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchnotes
- description: Create a note
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnote
- description: Get a note
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnote
- description: Get authenticated user details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserdetails
- description: Get API capabilities and limits
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcapabilities
---
