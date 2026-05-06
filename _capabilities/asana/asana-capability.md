---
categories: []
consumed_apis: []
description: The Asana Allocations API allows users to manage and allocate resources within their Asana project management system. An allocation object represents how much of a resource (e.g. person, team) is dedicated to a specific work object (e.g. project, portfolio) over a specific period of time. The effort value can be a percentage or number of hours.
layout: capability
name: Asana Allocations API
operations:
- description: Asana Get an allocation
  method: GET
  name: getallocation
  path: /allocations/{allocation_gid}
- description: Asana Update an allocation
  method: PUT
  name: updateallocation
  path: /allocations/{allocation_gid}
- description: Asana Delete an allocation
  method: DELETE
  name: deleteallocation
  path: /allocations/{allocation_gid}
- description: Asana Get multiple allocations
  method: GET
  name: getallocations
  path: /allocations
- description: Asana Create an allocation
  method: POST
  name: createallocation
  path: /allocations
personas: []
provider_name: Asana
provider_slug: asana
search_terms:
- updateallocation
- tasks
- workflow
- projects
- asana delete an allocation
- asana create an allocation
- project management
- productivity
- asana get an allocation
- task management
- api
- deleteallocation
- asana update an allocation
- createallocation
- asana
- getallocations
- collaboration
- getallocation
- asana get multiple allocations
slug: asana-capability
source_filename: asana-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Asana Allocations API\n  description: The Asana Allocations API allows users to manage and allocate resources within their Asana project management\n    system. An allocation object represents how much of a resource (e.g. person, team) is dedicated to a specific work object\n    (e.g. project, portfolio) over a specific period of time. The effort value can be a percentage or number of hours.\n  tags:\n  - Asana\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: asana\n    baseUri: https://app.asana.com/api/1.0\n    description: Asana Allocations API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ASANA_TOKEN}}'\n    resources:\n    - name: allocations-allocation-gid\n      path: /allocations/{allocation_gid}\n      operations:\n      - name: getallocation\n        method: GET\n        description: Asana Get an allocation\n        inputParameters:\n \
  \       - name: allocation_gid\n          in: path\n          type: string\n          required: true\n          description: Globally unique identifier for the allocation.\n        - name: opt_fields\n          in: query\n          type: array\n          description: Comma-separated list of optional fields to include.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateallocation\n        method: PUT\n        description: Asana Update an allocation\n        inputParameters:\n        - name: allocation_gid\n          in: path\n          type: string\n          required: true\n          description: Globally unique identifier for the allocation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteallocation\n        method: DELETE\n        description: Asana Delete an allocation\n        inputParameters:\n\
  \        - name: allocation_gid\n          in: path\n          type: string\n          required: true\n          description: Globally unique identifier for the allocation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allocations\n      path: /allocations\n      operations:\n      - name: getallocations\n        method: GET\n        description: Asana Get multiple allocations\n        inputParameters:\n        - name: parent\n          in: query\n          type: string\n          required: true\n          description: Globally unique identifier for the project to filter allocations.\n        - name: assignee\n          in: query\n          type: string\n          description: Globally unique identifier for the user to filter allocations.\n        - name: workspace\n          in: query\n          type: string\n          description: Globally unique identifier for the workspace.\n        - name:\
  \ limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createallocation\n        method: POST\n        description: Asana Create an allocation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: asana-rest\n    description: REST adapter for Asana Allocations API.\n    resources:\n    - path: /allocations/{allocation_gid}\n      name: getallocation\n      operations:\n      - method: GET\n        name: getallocation\n        description: Asana Get an allocation\n        call: asana.getallocation\n        with:\n          allocation_gid: rest.allocation_gid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /allocations/{allocation_gid}\n\
  \      name: updateallocation\n      operations:\n      - method: PUT\n        name: updateallocation\n        description: Asana Update an allocation\n        call: asana.updateallocation\n        with:\n          allocation_gid: rest.allocation_gid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /allocations/{allocation_gid}\n      name: deleteallocation\n      operations:\n      - method: DELETE\n        name: deleteallocation\n        description: Asana Delete an allocation\n        call: asana.deleteallocation\n        with:\n          allocation_gid: rest.allocation_gid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /allocations\n      name: getallocations\n      operations:\n      - method: GET\n        name: getallocations\n        description: Asana Get multiple allocations\n        call: asana.getallocations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /allocations\n\
  \      name: createallocation\n      operations:\n      - method: POST\n        name: createallocation\n        description: Asana Create an allocation\n        call: asana.createallocation\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: asana-mcp\n    transport: http\n    description: MCP adapter for Asana Allocations API for AI agent use.\n    tools:\n    - name: getallocation\n      description: Asana Get an allocation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: asana.getallocation\n      with:\n        allocation_gid: tools.allocation_gid\n        opt_fields: tools.opt_fields\n      inputParameters:\n      - name: allocation_gid\n        type: string\n        description: Globally unique identifier for the allocation.\n        required: true\n      - name: opt_fields\n        type: array\n        description: Comma-separated list of optional fields to\
  \ include.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateallocation\n      description: Asana Update an allocation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: asana.updateallocation\n      with:\n        allocation_gid: tools.allocation_gid\n      inputParameters:\n      - name: allocation_gid\n        type: string\n        description: Globally unique identifier for the allocation.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteallocation\n      description: Asana Delete an allocation\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: asana.deleteallocation\n      with:\n        allocation_gid: tools.allocation_gid\n      inputParameters:\n      - name: allocation_gid\n        type: string\n        description: Globally unique identifier for the allocation.\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getallocations\n      description: Asana Get multiple allocations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: asana.getallocations\n      with:\n        parent: tools.parent\n        assignee: tools.assignee\n        workspace: tools.workspace\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: parent\n        type: string\n        description: Globally unique identifier for the project to filter allocations.\n        required: true\n      - name: assignee\n        type: string\n        description: Globally unique identifier for the user to filter allocations.\n      - name: workspace\n        type: string\n        description: Globally unique identifier for the workspace.\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: string\n     \
  \   description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createallocation\n      description: Asana Create an allocation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: asana.createallocation\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ASANA_TOKEN: ASANA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/asana/refs/heads/main/capabilities/asana-capability.yaml
tags:
- Asana
- API
tools:
- description: Asana Get an allocation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallocation
- description: Asana Update an allocation
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateallocation
- description: Asana Delete an allocation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteallocation
- description: Asana Get multiple allocations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallocations
- description: Asana Create an allocation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createallocation
---
