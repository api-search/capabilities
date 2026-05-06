---
categories: []
consumed_apis: []
description: Quorum Land Management API provides access to land records, lease management, tract data, division order information, and document management for upstream oil and gas exploration and production companies. Quorum is a leading provider of software solutions for the upstream oil and gas industry.
layout: capability
name: Quorum Land Management API
operations:
- description: List leases
  method: GET
  name: listleases
  path: /leases
- description: Create a lease
  method: POST
  name: createlease
  path: /leases
- description: Get a lease
  method: GET
  name: getlease
  path: /leases/{leaseId}
- description: Update a lease
  method: PUT
  name: updatelease
  path: /leases/{leaseId}
- description: List tracts
  method: GET
  name: listtracts
  path: /tracts
- description: List division orders
  method: GET
  name: listdivisionorders
  path: /division-orders
- description: List wells
  method: GET
  name: listwells
  path: /wells
- description: Get a well
  method: GET
  name: getwell
  path: /wells/{wellId}
- description: List mineral interest owners
  method: GET
  name: listowners
  path: /owners
personas: []
provider_name: Quorum Software
provider_slug: quorum
search_terms:
- create a lease
- royalty accounting
- list mineral interest owners
- list wells
- list leases
- update a lease
- get a well
- updatelease
- list division orders
- oil & gas
- getlease
- quorum
- getwell
- get a lease
- api
- listdivisionorders
- listleases
- energy
- listtracts
- land management
- production reporting
- createlease
- upstream
- listwells
- listowners
- list tracts
slug: quorum-capability
source_filename: quorum-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Quorum Land Management API\n  description: Quorum Land Management API provides access to land records, lease management, tract data, division order information,\n    and document management for upstream oil and gas exploration and production companies. Quorum is a leading provider of\n    software solutions for the upstream oil and gas industry.\n  tags:\n  - Quorum\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: quorum\n    baseUri: https://api.quorumsoftware.com/v1\n    description: Quorum Land Management API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{QUORUM_TOKEN}}'\n    resources:\n    - name: leases\n      path: /leases\n      operations:\n      - name: listleases\n        method: GET\n        description: List leases\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter\
  \ by lease status\n        - name: county\n          in: query\n          type: string\n          description: Filter by county name\n        - name: state\n          in: query\n          type: string\n          description: Filter by state (2-letter abbreviation)\n        - name: updatedSince\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlease\n        method: POST\n        description: Create a lease\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: leases-leaseid\n      path: /leases/{leaseId}\n      operations:\n      - name: getlease\n        method: GET\n        description: Get a lease\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelease\n        method: PUT\n        description: Update a lease\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tracts\n      path: /tracts\n      operations:\n      - name: listtracts\n        method: GET\n        description: List tracts\n        inputParameters:\n        - name: leaseId\n          in: query\n          type: string\n          description: Filter by associated lease\n        - name: state\n          in: query\n          type: string\n        - name: county\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: division-orders\n      path: /division-orders\n      operations:\n      - name: listdivisionorders\n        method: GET\n        description: List division orders\n        inputParameters:\n        - name: wellId\n          in: query\n          type: string\n          description: Filter by well\n        - name: ownerId\n          in: query\n          type: string\n          description: Filter by owner\n        - name: status\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wells\n      path: /wells\n      operations:\n      - name: listwells\n        method: GET\n        description: List wells\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n      \
  \  - name: state\n          in: query\n          type: string\n        - name: county\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wells-wellid\n      path: /wells/{wellId}\n      operations:\n      - name: getwell\n        method: GET\n        description: Get a well\n        inputParameters:\n        - name: wellId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: owners\n      path: /owners\n      operations:\n      - name: listowners\n        method: GET\n        description: List mineral interest owners\n        inputParameters:\n        - name: ownerType\n\
  \          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: quorum-rest\n    description: REST adapter for Quorum Land Management API.\n    resources:\n    - path: /leases\n      name: listleases\n      operations:\n      - method: GET\n        name: listleases\n        description: List leases\n        call: quorum.listleases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /leases\n      name: createlease\n      operations:\n      - method: POST\n        name: createlease\n        description: Create a lease\n        call: quorum.createlease\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /leases/{leaseId}\n\
  \      name: getlease\n      operations:\n      - method: GET\n        name: getlease\n        description: Get a lease\n        call: quorum.getlease\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /leases/{leaseId}\n      name: updatelease\n      operations:\n      - method: PUT\n        name: updatelease\n        description: Update a lease\n        call: quorum.updatelease\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tracts\n      name: listtracts\n      operations:\n      - method: GET\n        name: listtracts\n        description: List tracts\n        call: quorum.listtracts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /division-orders\n      name: listdivisionorders\n      operations:\n      - method: GET\n        name: listdivisionorders\n        description: List division orders\n        call: quorum.listdivisionorders\n        outputParameters:\n      \
  \  - type: object\n          mapping: $.\n    - path: /wells\n      name: listwells\n      operations:\n      - method: GET\n        name: listwells\n        description: List wells\n        call: quorum.listwells\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wells/{wellId}\n      name: getwell\n      operations:\n      - method: GET\n        name: getwell\n        description: Get a well\n        call: quorum.getwell\n        with:\n          wellId: rest.wellId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /owners\n      name: listowners\n      operations:\n      - method: GET\n        name: listowners\n        description: List mineral interest owners\n        call: quorum.listowners\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: quorum-mcp\n    transport: http\n    description: MCP adapter for Quorum Land Management API for AI\
  \ agent use.\n    tools:\n    - name: listleases\n      description: List leases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quorum.listleases\n      with:\n        status: tools.status\n        county: tools.county\n        state: tools.state\n        updatedSince: tools.updatedSince\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by lease status\n      - name: county\n        type: string\n        description: Filter by county name\n      - name: state\n        type: string\n        description: Filter by state (2-letter abbreviation)\n      - name: updatedSince\n        type: string\n        description: updatedSince\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: createlease\n      description: Create a lease\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: quorum.createlease\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlease\n      description: Get a lease\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quorum.getlease\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatelease\n      description: Update a lease\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: quorum.updatelease\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtracts\n      description: List tracts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quorum.listtracts\n      with:\n        leaseId: tools.leaseId\n        state: tools.state\n\
  \        county: tools.county\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: leaseId\n        type: string\n        description: Filter by associated lease\n      - name: state\n        type: string\n        description: state\n      - name: county\n        type: string\n        description: county\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdivisionorders\n      description: List division orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quorum.listdivisionorders\n      with:\n        wellId: tools.wellId\n        ownerId: tools.ownerId\n        status: tools.status\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: wellId\n        type: string\n\
  \        description: Filter by well\n      - name: ownerId\n        type: string\n        description: Filter by owner\n      - name: status\n        type: string\n        description: status\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listwells\n      description: List wells\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quorum.listwells\n      with:\n        status: tools.status\n        state: tools.state\n        county: tools.county\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: status\n        type: string\n        description: status\n      - name: state\n        type: string\n        description: state\n      - name: county\n        type: string\n        description: county\n      - name: offset\n\
  \        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getwell\n      description: Get a well\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quorum.getwell\n      with:\n        wellId: tools.wellId\n      inputParameters:\n      - name: wellId\n        type: string\n        description: wellId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listowners\n      description: List mineral interest owners\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quorum.listowners\n      with:\n        ownerType: tools.ownerType\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: ownerType\n        type: string\n        description: ownerType\n\
  \      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    QUORUM_TOKEN: QUORUM_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/quorum/refs/heads/main/capabilities/quorum-capability.yaml
tags:
- Quorum
- API
tools:
- description: List leases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listleases
- description: Create a lease
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlease
- description: Get a lease
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlease
- description: Update a lease
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatelease
- description: List tracts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtracts
- description: List division orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdivisionorders
- description: List wells
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwells
- description: Get a well
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwell
- description: List mineral interest owners
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listowners
---
