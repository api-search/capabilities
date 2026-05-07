---
categories: []
consumed_apis: []
description: The Google Cloud Memorystore for Redis API provides programmatic management of fully managed Redis instances on Google Cloud. It enables creating, configuring, scaling, and monitoring Redis instances for use as in-memory data stores and caches, with support for high availability, automatic failover, and data persistence.
layout: capability
name: Google Cloud Memorystore for Redis API
operations:
- description: Google Cloud Memorystore List instances
  method: GET
  name: listinstances
  path: /projects/{project}/locations/{location}/instances
- description: Google Cloud Memorystore Create an instance
  method: POST
  name: createinstance
  path: /projects/{project}/locations/{location}/instances
- description: Google Cloud Memorystore Get an instance
  method: GET
  name: getinstance
  path: /projects/{project}/locations/{location}/instances/{instance}
- description: Google Cloud Memorystore Update an instance
  method: PATCH
  name: updateinstance
  path: /projects/{project}/locations/{location}/instances/{instance}
- description: Google Cloud Memorystore Delete an instance
  method: DELETE
  name: deleteinstance
  path: /projects/{project}/locations/{location}/instances/{instance}
- description: Google Cloud Memorystore Upgrade an instance
  method: POST
  name: upgradeinstance
  path: /projects/{project}/locations/{location}/instances/{instance}:upgrade
- description: Google Cloud Memorystore Failover an instance
  method: POST
  name: failoverinstance
  path: /projects/{project}/locations/{location}/instances/{instance}:failover
personas: []
provider_name: Google Cloud Memorystore
provider_slug: google-cloud-memorystore
search_terms:
- google cloud memorystore get an instance
- updateinstance
- createinstance
- api
- deleteinstance
- google
- getinstance
- google cloud memorystore list instances
- cache
- memorystore
- failoverinstance
- in-memory
- redis
- google cloud memorystore update an instance
- upgradeinstance
- cloud
- memcached
- google cloud memorystore create an instance
- google cloud memorystore delete an instance
- google cloud memorystore upgrade an instance
- google cloud
- listinstances
- google cloud memorystore failover an instance
slug: google-cloud-memorystore-capability
source_filename: google-cloud-memorystore-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Memorystore for Redis API\n  description: The Google Cloud Memorystore for Redis API provides programmatic management of fully managed Redis instances\n    on Google Cloud. It enables creating, configuring, scaling, and monitoring Redis instances for use as in-memory data stores\n    and caches, with support for high availability, automatic failover, and data persistence.\n  tags:\n  - Google\n  - Cloud\n  - Memorystore\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-memorystore\n    baseUri: https://redis.googleapis.com/v1\n    description: Google Cloud Memorystore for Redis API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_MEMORYSTORE_TOKEN}}'\n    resources:\n    - name: projects-project-locations-location-instances\n      path: /projects/{project}/locations/{location}/instances\n      operations:\n    \
  \  - name: listinstances\n        method: GET\n        description: Google Cloud Memorystore List instances\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n          description: Use '-' for all locations.\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createinstance\n        method: POST\n        description: Google Cloud Memorystore Create an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: instanceId\n\
  \          in: query\n          type: string\n          required: true\n          description: The logical name of the Redis instance.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-locations-location-instances-in\n      path: /projects/{project}/locations/{location}/instances/{instance}\n      operations:\n      - name: getinstance\n        method: GET\n        description: Google Cloud Memorystore Get an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateinstance\n\
  \        method: PATCH\n        description: Google Cloud Memorystore Update an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        - name: updateMask\n          in: query\n          type: string\n          required: true\n          description: Fields to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteinstance\n        method: DELETE\n        description: Google Cloud Memorystore Delete an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required:\
  \ true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-locations-location-instances-in\n      path: /projects/{project}/locations/{location}/instances/{instance}:upgrade\n      operations:\n      - name: upgradeinstance\n        method: POST\n        description: Google Cloud Memorystore Upgrade an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-locations-location-instances-in\n\
  \      path: /projects/{project}/locations/{location}/instances/{instance}:failover\n      operations:\n      - name: failoverinstance\n        method: POST\n        description: Google Cloud Memorystore Failover an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-memorystore-rest\n    description: REST adapter for Google Cloud Memorystore for Redis API.\n    resources:\n    - path: /projects/{project}/locations/{location}/instances\n      name: listinstances\n      operations:\n      - method: GET\n        name: listinstances\n\
  \        description: Google Cloud Memorystore List instances\n        call: google-cloud-memorystore.listinstances\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/instances\n      name: createinstance\n      operations:\n      - method: POST\n        name: createinstance\n        description: Google Cloud Memorystore Create an instance\n        call: google-cloud-memorystore.createinstance\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/instances/{instance}\n      name: getinstance\n      operations:\n      - method: GET\n        name: getinstance\n        description: Google Cloud Memorystore Get an instance\n        call: google-cloud-memorystore.getinstance\n  \
  \      with:\n          project: rest.project\n          location: rest.location\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/instances/{instance}\n      name: updateinstance\n      operations:\n      - method: PATCH\n        name: updateinstance\n        description: Google Cloud Memorystore Update an instance\n        call: google-cloud-memorystore.updateinstance\n        with:\n          project: rest.project\n          location: rest.location\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/instances/{instance}\n      name: deleteinstance\n      operations:\n      - method: DELETE\n        name: deleteinstance\n        description: Google Cloud Memorystore Delete an instance\n        call: google-cloud-memorystore.deleteinstance\n        with:\n        \
  \  project: rest.project\n          location: rest.location\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/instances/{instance}:upgrade\n      name: upgradeinstance\n      operations:\n      - method: POST\n        name: upgradeinstance\n        description: Google Cloud Memorystore Upgrade an instance\n        call: google-cloud-memorystore.upgradeinstance\n        with:\n          project: rest.project\n          location: rest.location\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/instances/{instance}:failover\n      name: failoverinstance\n      operations:\n      - method: POST\n        name: failoverinstance\n        description: Google Cloud Memorystore Failover an instance\n        call: google-cloud-memorystore.failoverinstance\n        with:\n   \
  \       project: rest.project\n          location: rest.location\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-memorystore-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Memorystore for Redis API for AI agent use.\n    tools:\n    - name: listinstances\n      description: Google Cloud Memorystore List instances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-memorystore.listinstances\n      with:\n        project: tools.project\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: Use '-' for all locations.\n        required: true\n  \
  \    - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createinstance\n      description: Google Cloud Memorystore Create an instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-memorystore.createinstance\n      with:\n        project: tools.project\n        location: tools.location\n        instanceId: tools.instanceId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: instanceId\n        type: string\n        description: The logical name of the Redis instance.\n        required: true\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getinstance\n      description: Google Cloud Memorystore Get an instance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-memorystore.getinstance\n      with:\n        project: tools.project\n        location: tools.location\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateinstance\n      description: Google Cloud Memorystore Update an instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-memorystore.updateinstance\n      with:\n       \
  \ project: tools.project\n        location: tools.location\n        instance: tools.instance\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      - name: updateMask\n        type: string\n        description: Fields to update.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteinstance\n      description: Google Cloud Memorystore Delete an instance\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-memorystore.deleteinstance\n      with:\n        project: tools.project\n        location: tools.location\n        instance: tools.instance\n      inputParameters:\n\
  \      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upgradeinstance\n      description: Google Cloud Memorystore Upgrade an instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-memorystore.upgradeinstance\n      with:\n        project: tools.project\n        location: tools.location\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: instance\n        type: string\n    \
  \    description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: failoverinstance\n      description: Google Cloud Memorystore Failover an instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-memorystore.failoverinstance\n      with:\n        project: tools.project\n        location: tools.location\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_MEMORYSTORE_TOKEN: GOOGLE_CLOUD_MEMORYSTORE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-memorystore/refs/heads/main/capabilities/google-cloud-memorystore-capability.yaml
tags:
- Google
- Cloud
- Memorystore
- API
tools:
- description: Google Cloud Memorystore List instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstances
- description: Google Cloud Memorystore Create an instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinstance
- description: Google Cloud Memorystore Get an instance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstance
- description: Google Cloud Memorystore Update an instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateinstance
- description: Google Cloud Memorystore Delete an instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteinstance
- description: Google Cloud Memorystore Upgrade an instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: upgradeinstance
- description: Google Cloud Memorystore Failover an instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: failoverinstance
---
