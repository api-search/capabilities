---
categories: []
consumed_apis: []
description: OpenAPI definition for the Hazelcast REST API exposed by cluster members. The REST service is disabled by default and must be enabled in member configuration. Endpoint groups (CLUSTER_READ, CLUSTER_WRITE, DATA, HEALTH_CHECK, PERSISTENCE, WAN, CP) gate access to specific operations.
layout: capability
name: Hazelcast REST API
operations:
- description: Get map entry
  method: GET
  name: getmapentry
  path: /hazelcast/rest/maps/{mapName}/{key}
- description: Put map entry
  method: POST
  name: putmapentry
  path: /hazelcast/rest/maps/{mapName}/{key}
- description: Delete map entry
  method: DELETE
  name: deletemapentry
  path: /hazelcast/rest/maps/{mapName}/{key}
- description: Clear map
  method: DELETE
  name: clearmap
  path: /hazelcast/rest/maps/{mapName}
- description: Offer item to queue
  method: POST
  name: offerqueueitem
  path: /hazelcast/rest/queues/{queueName}
- description: Poll item from queue
  method: DELETE
  name: pollqueueitem
  path: /hazelcast/rest/queues/{queueName}
- description: Get queue size
  method: GET
  name: getqueuesize
  path: /hazelcast/rest/queues/{queueName}/size
- description: Get cluster info
  method: GET
  name: getclusterinfo
  path: /hazelcast/rest/cluster
- description: Get instance name
  method: GET
  name: getinstancename
  path: /hazelcast/rest/instance
- description: Get cluster state
  method: GET
  name: getclusterstate
  path: /hazelcast/rest/management/cluster/state
- description: Change cluster state
  method: POST
  name: changeclusterstate
  path: /hazelcast/rest/management/cluster/state
- description: Get cluster version
  method: GET
  name: getclusterversion
  path: /hazelcast/rest/management/cluster/version
- description: Readiness probe
  method: GET
  name: healthready
  path: /hazelcast/health/ready
- description: Node state
  method: GET
  name: healthnodestate
  path: /hazelcast/health/node-state
- description: Cluster state health
  method: GET
  name: healthclusterstate
  path: /hazelcast/health/cluster-state
- description: Cluster safe
  method: GET
  name: healthclustersafe
  path: /hazelcast/health/cluster-safe
- description: Reload member configuration
  method: POST
  name: reloadconfig
  path: /hazelcast/rest/config/reload
- description: Get TCP-IP member list
  method: GET
  name: gettcpipmemberlist
  path: /hazelcast/rest/config/tcp-ip/member-list
- description: Update TCP-IP member list
  method: POST
  name: updatetcpipmemberlist
  path: /hazelcast/rest/config/tcp-ip/member-list
personas: []
provider_name: Hazelcast
provider_slug: hazelcast
search_terms:
- poll item from queue
- putmapentry
- getqueuesize
- real-time
- node state
- rest
- getinstancename
- data caching
- deletemapentry
- getclusterinfo
- cluster safe
- healthclusterstate
- gettcpipmemberlist
- updatetcpipmemberlist
- get cluster info
- getclusterstate
- get cluster state
- put map entry
- changeclusterstate
- readiness probe
- reloadconfig
- offer item to queue
- get tcp-ip member list
- clearmap
- hazelcast
- api
- clear map
- in-memory computing
- distributed computing
- pollqueueitem
- change cluster state
- healthnodestate
- update tcp-ip member list
- healthclustersafe
- getmapentry
- get map entry
- delete map entry
- get cluster version
- offerqueueitem
- healthready
- getclusterversion
- cluster state health
- reload member configuration
- get instance name
- get queue size
slug: hazelcast-capability
source_filename: hazelcast-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Hazelcast REST API\n  description: OpenAPI definition for the Hazelcast REST API exposed by cluster members. The REST service is disabled by default\n    and must be enabled in member configuration. Endpoint groups (CLUSTER_READ, CLUSTER_WRITE, DATA, HEALTH_CHECK, PERSISTENCE,\n    WAN, CP) gate access to specific operations.\n  tags:\n  - Hazelcast\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hazelcast\n    baseUri: http://localhost:5701\n    description: Hazelcast REST API HTTP API.\n    resources:\n    - name: hazelcast-rest-maps-mapname-key\n      path: /hazelcast/rest/maps/{mapName}/{key}\n      operations:\n      - name: getmapentry\n        method: GET\n        description: Get map entry\n        inputParameters:\n        - name: mapName\n          in: path\n          type: string\n          required: true\n        - name: key\n          in: path\n        \
  \  type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putmapentry\n        method: POST\n        description: Put map entry\n        inputParameters:\n        - name: mapName\n          in: path\n          type: string\n          required: true\n        - name: key\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemapentry\n        method: DELETE\n        description: Delete map entry\n        inputParameters:\n        - name: mapName\n          in: path\n          type: string\n          required: true\n        - name: key\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: hazelcast-rest-maps-mapname\n      path: /hazelcast/rest/maps/{mapName}\n      operations:\n      - name: clearmap\n        method: DELETE\n        description: Clear map\n        inputParameters:\n        - name: mapName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hazelcast-rest-queues-queuename\n      path: /hazelcast/rest/queues/{queueName}\n      operations:\n      - name: offerqueueitem\n        method: POST\n        description: Offer item to queue\n        inputParameters:\n        - name: queueName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: pollqueueitem\n        method: DELETE\n        description: Poll item from queue\n\
  \        inputParameters:\n        - name: queueName\n          in: path\n          type: string\n          required: true\n        - name: timeout\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hazelcast-rest-queues-queuename-size\n      path: /hazelcast/rest/queues/{queueName}/size\n      operations:\n      - name: getqueuesize\n        method: GET\n        description: Get queue size\n        inputParameters:\n        - name: queueName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hazelcast-rest-cluster\n      path: /hazelcast/rest/cluster\n      operations:\n      - name: getclusterinfo\n        method: GET\n        description: Get cluster info\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hazelcast-rest-instance\n      path: /hazelcast/rest/instance\n      operations:\n      - name: getinstancename\n        method: GET\n        description: Get instance name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hazelcast-rest-management-cluster-state\n      path: /hazelcast/rest/management/cluster/state\n      operations:\n      - name: getclusterstate\n        method: GET\n        description: Get cluster state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: changeclusterstate\n        method: POST\n        description: Change cluster state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hazelcast-rest-management-cluster-version\n\
  \      path: /hazelcast/rest/management/cluster/version\n      operations:\n      - name: getclusterversion\n        method: GET\n        description: Get cluster version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hazelcast-health-ready\n      path: /hazelcast/health/ready\n      operations:\n      - name: healthready\n        method: GET\n        description: Readiness probe\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hazelcast-health-node-state\n      path: /hazelcast/health/node-state\n      operations:\n      - name: healthnodestate\n        method: GET\n        description: Node state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hazelcast-health-cluster-state\n      path: /hazelcast/health/cluster-state\n\
  \      operations:\n      - name: healthclusterstate\n        method: GET\n        description: Cluster state health\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hazelcast-health-cluster-safe\n      path: /hazelcast/health/cluster-safe\n      operations:\n      - name: healthclustersafe\n        method: GET\n        description: Cluster safe\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hazelcast-rest-config-reload\n      path: /hazelcast/rest/config/reload\n      operations:\n      - name: reloadconfig\n        method: POST\n        description: Reload member configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hazelcast-rest-config-tcp-ip-member-list\n      path: /hazelcast/rest/config/tcp-ip/member-list\n\
  \      operations:\n      - name: gettcpipmemberlist\n        method: GET\n        description: Get TCP-IP member list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetcpipmemberlist\n        method: POST\n        description: Update TCP-IP member list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hazelcast-rest\n    description: REST adapter for Hazelcast REST API.\n    resources:\n    - path: /hazelcast/rest/maps/{mapName}/{key}\n      name: getmapentry\n      operations:\n      - method: GET\n        name: getmapentry\n        description: Get map entry\n        call: hazelcast.getmapentry\n        with:\n          mapName: rest.mapName\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /hazelcast/rest/maps/{mapName}/{key}\n      name: putmapentry\n      operations:\n      - method: POST\n        name: putmapentry\n        description: Put map entry\n        call: hazelcast.putmapentry\n        with:\n          mapName: rest.mapName\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazelcast/rest/maps/{mapName}/{key}\n      name: deletemapentry\n      operations:\n      - method: DELETE\n        name: deletemapentry\n        description: Delete map entry\n        call: hazelcast.deletemapentry\n        with:\n          mapName: rest.mapName\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazelcast/rest/maps/{mapName}\n      name: clearmap\n      operations:\n      - method: DELETE\n        name: clearmap\n        description: Clear map\n        call: hazelcast.clearmap\n        with:\n          mapName: rest.mapName\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /hazelcast/rest/queues/{queueName}\n      name: offerqueueitem\n      operations:\n      - method: POST\n        name: offerqueueitem\n        description: Offer item to queue\n        call: hazelcast.offerqueueitem\n        with:\n          queueName: rest.queueName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazelcast/rest/queues/{queueName}\n      name: pollqueueitem\n      operations:\n      - method: DELETE\n        name: pollqueueitem\n        description: Poll item from queue\n        call: hazelcast.pollqueueitem\n        with:\n          queueName: rest.queueName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazelcast/rest/queues/{queueName}/size\n      name: getqueuesize\n      operations:\n      - method: GET\n        name: getqueuesize\n        description: Get queue size\n        call: hazelcast.getqueuesize\n        with:\n    \
  \      queueName: rest.queueName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazelcast/rest/cluster\n      name: getclusterinfo\n      operations:\n      - method: GET\n        name: getclusterinfo\n        description: Get cluster info\n        call: hazelcast.getclusterinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazelcast/rest/instance\n      name: getinstancename\n      operations:\n      - method: GET\n        name: getinstancename\n        description: Get instance name\n        call: hazelcast.getinstancename\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazelcast/rest/management/cluster/state\n      name: getclusterstate\n      operations:\n      - method: GET\n        name: getclusterstate\n        description: Get cluster state\n        call: hazelcast.getclusterstate\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /hazelcast/rest/management/cluster/state\n      name: changeclusterstate\n      operations:\n      - method: POST\n        name: changeclusterstate\n        description: Change cluster state\n        call: hazelcast.changeclusterstate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazelcast/rest/management/cluster/version\n      name: getclusterversion\n      operations:\n      - method: GET\n        name: getclusterversion\n        description: Get cluster version\n        call: hazelcast.getclusterversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazelcast/health/ready\n      name: healthready\n      operations:\n      - method: GET\n        name: healthready\n        description: Readiness probe\n        call: hazelcast.healthready\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazelcast/health/node-state\n      name: healthnodestate\n      operations:\n\
  \      - method: GET\n        name: healthnodestate\n        description: Node state\n        call: hazelcast.healthnodestate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazelcast/health/cluster-state\n      name: healthclusterstate\n      operations:\n      - method: GET\n        name: healthclusterstate\n        description: Cluster state health\n        call: hazelcast.healthclusterstate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazelcast/health/cluster-safe\n      name: healthclustersafe\n      operations:\n      - method: GET\n        name: healthclustersafe\n        description: Cluster safe\n        call: hazelcast.healthclustersafe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazelcast/rest/config/reload\n      name: reloadconfig\n      operations:\n      - method: POST\n        name: reloadconfig\n        description: Reload member configuration\n\
  \        call: hazelcast.reloadconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazelcast/rest/config/tcp-ip/member-list\n      name: gettcpipmemberlist\n      operations:\n      - method: GET\n        name: gettcpipmemberlist\n        description: Get TCP-IP member list\n        call: hazelcast.gettcpipmemberlist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazelcast/rest/config/tcp-ip/member-list\n      name: updatetcpipmemberlist\n      operations:\n      - method: POST\n        name: updatetcpipmemberlist\n        description: Update TCP-IP member list\n        call: hazelcast.updatetcpipmemberlist\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hazelcast-mcp\n    transport: http\n    description: MCP adapter for Hazelcast REST API for AI agent use.\n    tools:\n    - name: getmapentry\n      description: Get map entry\n \
  \     hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hazelcast.getmapentry\n      with:\n        mapName: tools.mapName\n        key: tools.key\n      inputParameters:\n      - name: mapName\n        type: string\n        description: mapName\n        required: true\n      - name: key\n        type: string\n        description: key\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putmapentry\n      description: Put map entry\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hazelcast.putmapentry\n      with:\n        mapName: tools.mapName\n        key: tools.key\n      inputParameters:\n      - name: mapName\n        type: string\n        description: mapName\n        required: true\n      - name: key\n        type: string\n        description: key\n        required: true\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: deletemapentry\n      description: Delete map entry\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hazelcast.deletemapentry\n      with:\n        mapName: tools.mapName\n        key: tools.key\n      inputParameters:\n      - name: mapName\n        type: string\n        description: mapName\n        required: true\n      - name: key\n        type: string\n        description: key\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clearmap\n      description: Clear map\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hazelcast.clearmap\n      with:\n        mapName: tools.mapName\n      inputParameters:\n      - name: mapName\n        type: string\n        description: mapName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: offerqueueitem\n\
  \      description: Offer item to queue\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hazelcast.offerqueueitem\n      with:\n        queueName: tools.queueName\n      inputParameters:\n      - name: queueName\n        type: string\n        description: queueName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pollqueueitem\n      description: Poll item from queue\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hazelcast.pollqueueitem\n      with:\n        queueName: tools.queueName\n        timeout: tools.timeout\n      inputParameters:\n      - name: queueName\n        type: string\n        description: queueName\n        required: true\n      - name: timeout\n        type: integer\n        description: timeout\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getqueuesize\n      description:\
  \ Get queue size\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hazelcast.getqueuesize\n      with:\n        queueName: tools.queueName\n      inputParameters:\n      - name: queueName\n        type: string\n        description: queueName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclusterinfo\n      description: Get cluster info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hazelcast.getclusterinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinstancename\n      description: Get instance name\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hazelcast.getinstancename\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclusterstate\n      description: Get cluster state\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hazelcast.getclusterstate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: changeclusterstate\n      description: Change cluster state\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hazelcast.changeclusterstate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclusterversion\n      description: Get cluster version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hazelcast.getclusterversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: healthready\n      description: Readiness probe\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hazelcast.healthready\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ healthnodestate\n      description: Node state\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hazelcast.healthnodestate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: healthclusterstate\n      description: Cluster state health\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hazelcast.healthclusterstate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: healthclustersafe\n      description: Cluster safe\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hazelcast.healthclustersafe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reloadconfig\n      description: Reload member configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hazelcast.reloadconfig\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: gettcpipmemberlist\n      description: Get TCP-IP member list\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hazelcast.gettcpipmemberlist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatetcpipmemberlist\n      description: Update TCP-IP member list\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hazelcast.updatetcpipmemberlist\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hazelcast/refs/heads/main/capabilities/hazelcast-capability.yaml
tags:
- Hazelcast
- API
tools:
- description: Get map entry
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmapentry
- description: Put map entry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: putmapentry
- description: Delete map entry
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemapentry
- description: Clear map
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: clearmap
- description: Offer item to queue
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: offerqueueitem
- description: Poll item from queue
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: pollqueueitem
- description: Get queue size
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getqueuesize
- description: Get cluster info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclusterinfo
- description: Get instance name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstancename
- description: Get cluster state
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclusterstate
- description: Change cluster state
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: changeclusterstate
- description: Get cluster version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclusterversion
- description: Readiness probe
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: healthready
- description: Node state
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: healthnodestate
- description: Cluster state health
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: healthclusterstate
- description: Cluster safe
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: healthclustersafe
- description: Reload member configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: reloadconfig
- description: Get TCP-IP member list
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettcpipmemberlist
- description: Update TCP-IP member list
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatetcpipmemberlist
---
