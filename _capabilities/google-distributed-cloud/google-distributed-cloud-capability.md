---
categories: []
consumed_apis: []
description: The Distributed Cloud Edge Network API provides programmatic access to manage networking resources for Google Distributed Cloud connected deployments at the edge. It supports creating and managing networks, subnets, routers, and interconnect attachments for edge locations.
layout: capability
name: Google Distributed Cloud Edge Network API
operations:
- description: Google Distributed Cloud List zones
  method: GET
  name: listzones
  path: /projects/{projectId}/locations/{location}/zones
- description: Google Distributed Cloud List networks
  method: GET
  name: listnetworks
  path: /projects/{projectId}/locations/{location}/zones/{zone}/networks
- description: Google Distributed Cloud Create a network
  method: POST
  name: createnetwork
  path: /projects/{projectId}/locations/{location}/zones/{zone}/networks
- description: Google Distributed Cloud List subnets
  method: GET
  name: listsubnets
  path: /projects/{projectId}/locations/{location}/zones/{zone}/subnets
- description: Google Distributed Cloud Create a subnet
  method: POST
  name: createsubnet
  path: /projects/{projectId}/locations/{location}/zones/{zone}/subnets
- description: Google Distributed Cloud List routers
  method: GET
  name: listrouters
  path: /projects/{projectId}/locations/{location}/zones/{zone}/routers
- description: Google Distributed Cloud Create a router
  method: POST
  name: createrouter
  path: /projects/{projectId}/locations/{location}/zones/{zone}/routers
personas: []
provider_name: Google Distributed Cloud
provider_slug: google-distributed-cloud
search_terms:
- listsubnets
- google distributed cloud list subnets
- distributed
- hardware
- on-premises
- listnetworks
- google distributed cloud create a router
- google distributed cloud list networks
- api
- listzones
- edge computing
- google distributed cloud create a subnet
- createnetwork
- google
- google distributed cloud list routers
- kubernetes
- createsubnet
- listrouters
- cloud
- createrouter
- hybrid cloud
- distributed infrastructure
- google distributed cloud list zones
- google distributed cloud create a network
slug: google-distributed-cloud-capability
source_filename: google-distributed-cloud-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Distributed Cloud Edge Network API\n  description: The Distributed Cloud Edge Network API provides programmatic access to manage networking resources for Google\n    Distributed Cloud connected deployments at the edge. It supports creating and managing networks, subnets, routers, and\n    interconnect attachments for edge locations.\n  tags:\n  - Google\n  - Distributed\n  - Cloud\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-distributed-cloud\n    baseUri: https://edgenetwork.googleapis.com/v1\n    description: Google Distributed Cloud Edge Network API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_DISTRIBUTED_CLOUD_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations-location-zones\n      path: /projects/{projectId}/locations/{location}/zones\n      operations:\n      - name: listzones\n        method: GET\n\
  \        description: Google Distributed Cloud List zones\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-zones-zone\n      path: /projects/{projectId}/locations/{location}/zones/{zone}/networks\n      operations:\n      - name: listnetworks\n        method: GET\n        description: Google Distributed Cloud List networks\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: zone\n          in: path\n          type: string\n          required: true\n        - name:\
  \ pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnetwork\n        method: POST\n        description: Google Distributed Cloud Create a network\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: zone\n          in: path\n          type: string\n          required: true\n        - name: networkId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-zones-zone\n      path: /projects/{projectId}/locations/{location}/zones/{zone}/subnets\n\
  \      operations:\n      - name: listsubnets\n        method: GET\n        description: Google Distributed Cloud List subnets\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: zone\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsubnet\n        method: POST\n        description: Google Distributed Cloud Create a subnet\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: zone\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-zones-zone\n      path: /projects/{projectId}/locations/{location}/zones/{zone}/routers\n      operations:\n      - name: listrouters\n        method: GET\n        description: Google Distributed Cloud List routers\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: zone\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrouter\n        method: POST\n        description: Google Distributed Cloud Create a router\n        inputParameters:\n        - name: projectId\n          in: path\n     \
  \     type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: zone\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-distributed-cloud-rest\n    description: REST adapter for Google Distributed Cloud Edge Network API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/zones\n      name: listzones\n      operations:\n      - method: GET\n        name: listzones\n        description: Google Distributed Cloud List zones\n        call: google-distributed-cloud.listzones\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/zones/{zone}/networks\n\
  \      name: listnetworks\n      operations:\n      - method: GET\n        name: listnetworks\n        description: Google Distributed Cloud List networks\n        call: google-distributed-cloud.listnetworks\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          zone: rest.zone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/zones/{zone}/networks\n      name: createnetwork\n      operations:\n      - method: POST\n        name: createnetwork\n        description: Google Distributed Cloud Create a network\n        call: google-distributed-cloud.createnetwork\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          zone: rest.zone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/zones/{zone}/subnets\n      name: listsubnets\n      operations:\n\
  \      - method: GET\n        name: listsubnets\n        description: Google Distributed Cloud List subnets\n        call: google-distributed-cloud.listsubnets\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          zone: rest.zone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/zones/{zone}/subnets\n      name: createsubnet\n      operations:\n      - method: POST\n        name: createsubnet\n        description: Google Distributed Cloud Create a subnet\n        call: google-distributed-cloud.createsubnet\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          zone: rest.zone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/zones/{zone}/routers\n      name: listrouters\n      operations:\n      - method: GET\n        name: listrouters\n     \
  \   description: Google Distributed Cloud List routers\n        call: google-distributed-cloud.listrouters\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          zone: rest.zone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/zones/{zone}/routers\n      name: createrouter\n      operations:\n      - method: POST\n        name: createrouter\n        description: Google Distributed Cloud Create a router\n        call: google-distributed-cloud.createrouter\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          zone: rest.zone\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-distributed-cloud-mcp\n    transport: http\n    description: MCP adapter for Google Distributed Cloud Edge Network API for AI agent use.\n    tools:\n    - name: listzones\n \
  \     description: Google Distributed Cloud List zones\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-distributed-cloud.listzones\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnetworks\n      description: Google Distributed Cloud List networks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-distributed-cloud.listnetworks\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        zone: tools.zone\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n\
  \      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: zone\n        type: string\n        description: zone\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnetwork\n      description: Google Distributed Cloud Create a network\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-distributed-cloud.createnetwork\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        zone: tools.zone\n        networkId: tools.networkId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n\
  \        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: zone\n        type: string\n        description: zone\n        required: true\n      - name: networkId\n        type: string\n        description: networkId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsubnets\n      description: Google Distributed Cloud List subnets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-distributed-cloud.listsubnets\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        zone: tools.zone\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: zone\n        type: string\n     \
  \   description: zone\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsubnet\n      description: Google Distributed Cloud Create a subnet\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-distributed-cloud.createsubnet\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        zone: tools.zone\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: zone\n        type: string\n        description: zone\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrouters\n      description: Google Distributed Cloud List routers\n      hints:\n        readOnly: true\n        destructive: false\n     \
  \   idempotent: true\n      call: google-distributed-cloud.listrouters\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        zone: tools.zone\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: zone\n        type: string\n        description: zone\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrouter\n      description: Google Distributed Cloud Create a router\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-distributed-cloud.createrouter\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        zone: tools.zone\n      inputParameters:\n      - name: projectId\n        type: string\n        description:\
  \ projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: zone\n        type: string\n        description: zone\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_DISTRIBUTED_CLOUD_TOKEN: GOOGLE_DISTRIBUTED_CLOUD_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-distributed-cloud/refs/heads/main/capabilities/google-distributed-cloud-capability.yaml
tags:
- Google
- Distributed
- Cloud
- API
tools:
- description: Google Distributed Cloud List zones
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listzones
- description: Google Distributed Cloud List networks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnetworks
- description: Google Distributed Cloud Create a network
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnetwork
- description: Google Distributed Cloud List subnets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsubnets
- description: Google Distributed Cloud Create a subnet
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsubnet
- description: Google Distributed Cloud List routers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrouters
- description: Google Distributed Cloud Create a router
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrouter
---
