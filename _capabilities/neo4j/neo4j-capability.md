---
categories: []
consumed_apis: []
description: 'The Neo4j Aura API provides programmatic access to manage Neo4j AuraDB cloud database instances. It supports operations across three primary resources: instances, tenants, and snapshots. Developers authenticate using OAuth2 bearer tokens obtained through client credentials, and can automate the provisioning, configuration, and management of their cloud-hosted Neo4j graph databases. The API is accessible through the api.neo4j.io platform and is available to Aura Enterprise customers.'
layout: capability
name: Neo4j Aura API
operations:
- description: Obtain an OAuth2 access token
  method: POST
  name: getaccesstoken
  path: /oauth/token
- description: List all instances
  method: GET
  name: listinstances
  path: /instances
- description: Create a new instance
  method: POST
  name: createinstance
  path: /instances
- description: Get instance details
  method: GET
  name: getinstance
  path: /instances/{instanceId}
- description: Update an instance
  method: PATCH
  name: updateinstance
  path: /instances/{instanceId}
- description: Delete an instance
  method: DELETE
  name: deleteinstance
  path: /instances/{instanceId}
- description: Pause an instance
  method: POST
  name: pauseinstance
  path: /instances/{instanceId}/pause
- description: Resume a paused instance
  method: POST
  name: resumeinstance
  path: /instances/{instanceId}/resume
- description: Overwrite an instance from a snapshot
  method: POST
  name: overwriteinstance
  path: /instances/{instanceId}/overwrite
- description: List all tenants
  method: GET
  name: listtenants
  path: /tenants
- description: Get tenant details
  method: GET
  name: gettenant
  path: /tenants/{tenantId}
- description: List snapshots for an instance
  method: GET
  name: listsnapshots
  path: /instances/{instanceId}/snapshots
- description: Create a snapshot
  method: POST
  name: createsnapshot
  path: /instances/{instanceId}/snapshots
- description: Get snapshot details
  method: GET
  name: getsnapshot
  path: /instances/{instanceId}/snapshots/{snapshotId}
- description: Restore a snapshot to a new instance
  method: POST
  name: restoresnapshot
  path: /instances/{instanceId}/snapshots/{snapshotId}/restore
personas: []
provider_name: Neo4j
provider_slug: neo4j
search_terms:
- get tenant details
- graph database
- get instance details
- resumeinstance
- listtenants
- listsnapshots
- deleteinstance
- getaccesstoken
- apis
- createsnapshot
- cloud
- update an instance
- restore a snapshot to a new instance
- graphql
- pauseinstance
- createinstance
- updateinstance
- getinstance
- list all tenants
- resume a paused instance
- restoresnapshot
- neo4j
- delete an instance
- pause an instance
- gettenant
- api
- drivers
- obtain an oauth2 access token
- overwrite an instance from a snapshot
- list snapshots for an instance
- listinstances
- get snapshot details
- getsnapshot
- create a snapshot
- list all instances
- overwriteinstance
- cypher
- create a new instance
slug: neo4j-capability
source_filename: neo4j-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Neo4j Aura API\n  description: 'The Neo4j Aura API provides programmatic access to manage Neo4j AuraDB cloud database instances. It supports\n    operations across three primary resources: instances, tenants, and snapshots. Developers authenticate using OAuth2 bearer\n    tokens obtained through client credentials, and can automate the provisioning, configuration, and management of their\n    cloud-hosted Neo4j graph databases. The API is accessible through the api.neo4j.io platform and is available to Aura Enterprise\n    customers.'\n  tags:\n  - Neo4j\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: neo4j\n    baseUri: https://api.neo4j.io/v1\n    description: Neo4j Aura API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{NEO4J_TOKEN}}'\n    resources:\n    - name: oauth-token\n      path: /oauth/token\n      operations:\n      - name: getaccesstoken\n\
  \        method: POST\n        description: Obtain an OAuth2 access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instances\n      path: /instances\n      operations:\n      - name: listinstances\n        method: GET\n        description: List all instances\n        inputParameters:\n        - name: tenantId\n          in: query\n          type: string\n          description: Filter instances by tenant ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createinstance\n        method: POST\n        description: Create a new instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instances-instanceid\n      path: /instances/{instanceId}\n      operations:\n      - name: getinstance\n        method: GET\n \
  \       description: Get instance details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateinstance\n        method: PATCH\n        description: Update an instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteinstance\n        method: DELETE\n        description: Delete an instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instances-instanceid-pause\n      path: /instances/{instanceId}/pause\n      operations:\n      - name: pauseinstance\n        method: POST\n        description: Pause an instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instances-instanceid-resume\n      path: /instances/{instanceId}/resume\n\
  \      operations:\n      - name: resumeinstance\n        method: POST\n        description: Resume a paused instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instances-instanceid-overwrite\n      path: /instances/{instanceId}/overwrite\n      operations:\n      - name: overwriteinstance\n        method: POST\n        description: Overwrite an instance from a snapshot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tenants\n      path: /tenants\n      operations:\n      - name: listtenants\n        method: GET\n        description: List all tenants\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tenants-tenantid\n      path: /tenants/{tenantId}\n      operations:\n      - name: gettenant\n        method: GET\n\
  \        description: Get tenant details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instances-instanceid-snapshots\n      path: /instances/{instanceId}/snapshots\n      operations:\n      - name: listsnapshots\n        method: GET\n        description: List snapshots for an instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsnapshot\n        method: POST\n        description: Create a snapshot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instances-instanceid-snapshots-snapshotid\n      path: /instances/{instanceId}/snapshots/{snapshotId}\n      operations:\n      - name: getsnapshot\n        method: GET\n        description: Get snapshot details\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: instances-instanceid-snapshots-snapshotid-restor\n      path: /instances/{instanceId}/snapshots/{snapshotId}/restore\n      operations:\n      - name: restoresnapshot\n        method: POST\n        description: Restore a snapshot to a new instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: neo4j-rest\n    description: REST adapter for Neo4j Aura API.\n    resources:\n    - path: /oauth/token\n      name: getaccesstoken\n      operations:\n      - method: POST\n        name: getaccesstoken\n        description: Obtain an OAuth2 access token\n        call: neo4j.getaccesstoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances\n      name: listinstances\n      operations:\n      - method: GET\n        name: listinstances\n\
  \        description: List all instances\n        call: neo4j.listinstances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances\n      name: createinstance\n      operations:\n      - method: POST\n        name: createinstance\n        description: Create a new instance\n        call: neo4j.createinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances/{instanceId}\n      name: getinstance\n      operations:\n      - method: GET\n        name: getinstance\n        description: Get instance details\n        call: neo4j.getinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances/{instanceId}\n      name: updateinstance\n      operations:\n      - method: PATCH\n        name: updateinstance\n        description: Update an instance\n        call: neo4j.updateinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /instances/{instanceId}\n      name: deleteinstance\n      operations:\n      - method: DELETE\n        name: deleteinstance\n        description: Delete an instance\n        call: neo4j.deleteinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances/{instanceId}/pause\n      name: pauseinstance\n      operations:\n      - method: POST\n        name: pauseinstance\n        description: Pause an instance\n        call: neo4j.pauseinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances/{instanceId}/resume\n      name: resumeinstance\n      operations:\n      - method: POST\n        name: resumeinstance\n        description: Resume a paused instance\n        call: neo4j.resumeinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances/{instanceId}/overwrite\n      name: overwriteinstance\n      operations:\n      - method: POST\n      \
  \  name: overwriteinstance\n        description: Overwrite an instance from a snapshot\n        call: neo4j.overwriteinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tenants\n      name: listtenants\n      operations:\n      - method: GET\n        name: listtenants\n        description: List all tenants\n        call: neo4j.listtenants\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tenants/{tenantId}\n      name: gettenant\n      operations:\n      - method: GET\n        name: gettenant\n        description: Get tenant details\n        call: neo4j.gettenant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances/{instanceId}/snapshots\n      name: listsnapshots\n      operations:\n      - method: GET\n        name: listsnapshots\n        description: List snapshots for an instance\n        call: neo4j.listsnapshots\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /instances/{instanceId}/snapshots\n      name: createsnapshot\n      operations:\n      - method: POST\n        name: createsnapshot\n        description: Create a snapshot\n        call: neo4j.createsnapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances/{instanceId}/snapshots/{snapshotId}\n      name: getsnapshot\n      operations:\n      - method: GET\n        name: getsnapshot\n        description: Get snapshot details\n        call: neo4j.getsnapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances/{instanceId}/snapshots/{snapshotId}/restore\n      name: restoresnapshot\n      operations:\n      - method: POST\n        name: restoresnapshot\n        description: Restore a snapshot to a new instance\n        call: neo4j.restoresnapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n\
  \    namespace: neo4j-mcp\n    transport: http\n    description: MCP adapter for Neo4j Aura API for AI agent use.\n    tools:\n    - name: getaccesstoken\n      description: Obtain an OAuth2 access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: neo4j.getaccesstoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinstances\n      description: List all instances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neo4j.listinstances\n      with:\n        tenantId: tools.tenantId\n      inputParameters:\n      - name: tenantId\n        type: string\n        description: Filter instances by tenant ID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createinstance\n      description: Create a new instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ neo4j.createinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinstance\n      description: Get instance details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neo4j.getinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateinstance\n      description: Update an instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: neo4j.updateinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteinstance\n      description: Delete an instance\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: neo4j.deleteinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pauseinstance\n      description: Pause an instance\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: neo4j.pauseinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resumeinstance\n      description: Resume a paused instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: neo4j.resumeinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: overwriteinstance\n      description: Overwrite an instance from a snapshot\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: neo4j.overwriteinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtenants\n      description: List all tenants\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neo4j.listtenants\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettenant\n      description: Get tenant details\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neo4j.gettenant\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsnapshots\n      description: List snapshots for an instance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neo4j.listsnapshots\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsnapshot\n      description: Create a snapshot\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: neo4j.createsnapshot\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsnapshot\n      description: Get snapshot details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: neo4j.getsnapshot\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restoresnapshot\n\
  \      description: Restore a snapshot to a new instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: neo4j.restoresnapshot\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NEO4J_TOKEN: NEO4J_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/neo4j/refs/heads/main/capabilities/neo4j-capability.yaml
tags:
- Neo4j
- API
tools:
- description: Obtain an OAuth2 access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getaccesstoken
- description: List all instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstances
- description: Create a new instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinstance
- description: Get instance details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstance
- description: Update an instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateinstance
- description: Delete an instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteinstance
- description: Pause an instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pauseinstance
- description: Resume a paused instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resumeinstance
- description: Overwrite an instance from a snapshot
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: overwriteinstance
- description: List all tenants
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtenants
- description: Get tenant details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettenant
- description: List snapshots for an instance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsnapshots
- description: Create a snapshot
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsnapshot
- description: Get snapshot details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsnapshot
- description: Restore a snapshot to a new instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restoresnapshot
---
