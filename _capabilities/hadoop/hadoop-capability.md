---
categories: []
consumed_apis: []
description: Aggregated OpenAPI definition for the public REST APIs exposed by Apache Hadoop. Includes WebHDFS for filesystem operations and the YARN ResourceManager for cluster, application, and node management.
layout: capability
name: Apache Hadoop REST APIs
operations:
- description: WebHDFS GET operations
  method: GET
  name: webhdfsget
  path: /webhdfs/v1/{path}
- description: WebHDFS PUT operations
  method: PUT
  name: webhdfsput
  path: /webhdfs/v1/{path}
- description: WebHDFS POST operations
  method: POST
  name: webhdfspost
  path: /webhdfs/v1/{path}
- description: WebHDFS DELETE
  method: DELETE
  name: webhdfsdelete
  path: /webhdfs/v1/{path}
- description: Cluster info
  method: GET
  name: getclusterinfo
  path: /ws/v1/cluster/info
- description: Cluster metrics
  method: GET
  name: getclustermetrics
  path: /ws/v1/cluster/metrics
- description: Scheduler info
  method: GET
  name: getscheduler
  path: /ws/v1/cluster/scheduler
- description: List applications
  method: GET
  name: listapps
  path: /ws/v1/cluster/apps
- description: Submit a new application
  method: POST
  name: submitapp
  path: /ws/v1/cluster/apps
- description: Application details
  method: GET
  name: getapp
  path: /ws/v1/cluster/apps/{appid}
- description: Update application state
  method: PUT
  name: updateappstate
  path: /ws/v1/cluster/apps/{appid}/state
- description: Move application to a different queue
  method: PUT
  name: updateappqueue
  path: /ws/v1/cluster/apps/{appid}/queue
- description: Update application priority
  method: PUT
  name: updateapppriority
  path: /ws/v1/cluster/apps/{appid}/priority
- description: List application attempts
  method: GET
  name: listappattempts
  path: /ws/v1/cluster/apps/{appid}/appattempts
- description: List nodes
  method: GET
  name: listnodes
  path: /ws/v1/cluster/nodes
- description: Node details
  method: GET
  name: getnode
  path: /ws/v1/cluster/nodes/{nodeid}
- description: Application statistics
  method: GET
  name: getappstatistics
  path: /ws/v1/cluster/appstatistics
personas: []
provider_name: Apache Hadoop
provider_slug: hadoop
search_terms:
- scheduler info
- hadoop
- getclusterinfo
- node details
- updateappstate
- getscheduler
- api
- update application priority
- webhdfs delete
- webhdfs get operations
- application details
- getclustermetrics
- open source
- getappstatistics
- listnodes
- cluster metrics
- big data
- webhdfspost
- updateappqueue
- webhdfsdelete
- data processing
- cluster info
- update application state
- getnode
- hdfs
- submit a new application
- webhdfsput
- getapp
- webhdfsget
- list applications
- application statistics
- mapreduce
- submitapp
- webhdfs post operations
- listappattempts
- move application to a different queue
- list nodes
- listapps
- webhdfs put operations
- updateapppriority
- distributed computing
- list application attempts
slug: hadoop-capability
source_filename: hadoop-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Hadoop REST APIs\n  description: Aggregated OpenAPI definition for the public REST APIs exposed by Apache Hadoop. Includes WebHDFS for filesystem\n    operations and the YARN ResourceManager for cluster, application, and node management.\n  tags:\n  - Hadoop\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hadoop\n    baseUri: http://localhost:50070\n    description: Apache Hadoop REST APIs HTTP API.\n    resources:\n    - name: webhdfs-v1-path\n      path: /webhdfs/v1/{path}\n      operations:\n      - name: webhdfsget\n        method: GET\n        description: WebHDFS GET operations\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        - name: op\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: webhdfsput\n        method: PUT\n        description: WebHDFS PUT operations\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        - name: op\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: webhdfspost\n        method: POST\n        description: WebHDFS POST operations\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        - name: op\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: webhdfsdelete\n        method: DELETE\n        description: WebHDFS DELETE\n\
  \        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n        - name: op\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ws-v1-cluster-info\n      path: /ws/v1/cluster/info\n      operations:\n      - name: getclusterinfo\n        method: GET\n        description: Cluster info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ws-v1-cluster-metrics\n      path: /ws/v1/cluster/metrics\n      operations:\n      - name: getclustermetrics\n        method: GET\n        description: Cluster metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ws-v1-cluster-scheduler\n      path: /ws/v1/cluster/scheduler\n\
  \      operations:\n      - name: getscheduler\n        method: GET\n        description: Scheduler info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ws-v1-cluster-apps\n      path: /ws/v1/cluster/apps\n      operations:\n      - name: listapps\n        method: GET\n        description: List applications\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n        - name: user\n          in: query\n          type: string\n        - name: queue\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submitapp\n        method: POST\n        description: Submit a new application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ws-v1-cluster-apps-appid\n\
  \      path: /ws/v1/cluster/apps/{appid}\n      operations:\n      - name: getapp\n        method: GET\n        description: Application details\n        inputParameters:\n        - name: appid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ws-v1-cluster-apps-appid-state\n      path: /ws/v1/cluster/apps/{appid}/state\n      operations:\n      - name: updateappstate\n        method: PUT\n        description: Update application state\n        inputParameters:\n        - name: appid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ws-v1-cluster-apps-appid-queue\n      path: /ws/v1/cluster/apps/{appid}/queue\n      operations:\n      - name: updateappqueue\n        method:\
  \ PUT\n        description: Move application to a different queue\n        inputParameters:\n        - name: appid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ws-v1-cluster-apps-appid-priority\n      path: /ws/v1/cluster/apps/{appid}/priority\n      operations:\n      - name: updateapppriority\n        method: PUT\n        description: Update application priority\n        inputParameters:\n        - name: appid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ws-v1-cluster-apps-appid-appattempts\n      path: /ws/v1/cluster/apps/{appid}/appattempts\n      operations:\n      - name: listappattempts\n        method: GET\n        description: List application attempts\n\
  \        inputParameters:\n        - name: appid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ws-v1-cluster-nodes\n      path: /ws/v1/cluster/nodes\n      operations:\n      - name: listnodes\n        method: GET\n        description: List nodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ws-v1-cluster-nodes-nodeid\n      path: /ws/v1/cluster/nodes/{nodeid}\n      operations:\n      - name: getnode\n        method: GET\n        description: Node details\n        inputParameters:\n        - name: nodeid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ws-v1-cluster-appstatistics\n\
  \      path: /ws/v1/cluster/appstatistics\n      operations:\n      - name: getappstatistics\n        method: GET\n        description: Application statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hadoop-rest\n    description: REST adapter for Apache Hadoop REST APIs.\n    resources:\n    - path: /webhdfs/v1/{path}\n      name: webhdfsget\n      operations:\n      - method: GET\n        name: webhdfsget\n        description: WebHDFS GET operations\n        call: hadoop.webhdfsget\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhdfs/v1/{path}\n      name: webhdfsput\n      operations:\n      - method: PUT\n        name: webhdfsput\n        description: WebHDFS PUT operations\n        call: hadoop.webhdfsput\n        with:\n          path: rest.path\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhdfs/v1/{path}\n      name: webhdfspost\n      operations:\n      - method: POST\n        name: webhdfspost\n        description: WebHDFS POST operations\n        call: hadoop.webhdfspost\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhdfs/v1/{path}\n      name: webhdfsdelete\n      operations:\n      - method: DELETE\n        name: webhdfsdelete\n        description: WebHDFS DELETE\n        call: hadoop.webhdfsdelete\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ws/v1/cluster/info\n      name: getclusterinfo\n      operations:\n      - method: GET\n        name: getclusterinfo\n        description: Cluster info\n        call: hadoop.getclusterinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ws/v1/cluster/metrics\n\
  \      name: getclustermetrics\n      operations:\n      - method: GET\n        name: getclustermetrics\n        description: Cluster metrics\n        call: hadoop.getclustermetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ws/v1/cluster/scheduler\n      name: getscheduler\n      operations:\n      - method: GET\n        name: getscheduler\n        description: Scheduler info\n        call: hadoop.getscheduler\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ws/v1/cluster/apps\n      name: listapps\n      operations:\n      - method: GET\n        name: listapps\n        description: List applications\n        call: hadoop.listapps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ws/v1/cluster/apps\n      name: submitapp\n      operations:\n      - method: POST\n        name: submitapp\n        description: Submit a new application\n        call: hadoop.submitapp\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ws/v1/cluster/apps/{appid}\n      name: getapp\n      operations:\n      - method: GET\n        name: getapp\n        description: Application details\n        call: hadoop.getapp\n        with:\n          appid: rest.appid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ws/v1/cluster/apps/{appid}/state\n      name: updateappstate\n      operations:\n      - method: PUT\n        name: updateappstate\n        description: Update application state\n        call: hadoop.updateappstate\n        with:\n          appid: rest.appid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ws/v1/cluster/apps/{appid}/queue\n      name: updateappqueue\n      operations:\n      - method: PUT\n        name: updateappqueue\n        description: Move application to a different queue\n        call: hadoop.updateappqueue\n        with:\n        \
  \  appid: rest.appid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ws/v1/cluster/apps/{appid}/priority\n      name: updateapppriority\n      operations:\n      - method: PUT\n        name: updateapppriority\n        description: Update application priority\n        call: hadoop.updateapppriority\n        with:\n          appid: rest.appid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ws/v1/cluster/apps/{appid}/appattempts\n      name: listappattempts\n      operations:\n      - method: GET\n        name: listappattempts\n        description: List application attempts\n        call: hadoop.listappattempts\n        with:\n          appid: rest.appid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ws/v1/cluster/nodes\n      name: listnodes\n      operations:\n      - method: GET\n        name: listnodes\n        description: List nodes\n        call: hadoop.listnodes\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ws/v1/cluster/nodes/{nodeid}\n      name: getnode\n      operations:\n      - method: GET\n        name: getnode\n        description: Node details\n        call: hadoop.getnode\n        with:\n          nodeid: rest.nodeid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ws/v1/cluster/appstatistics\n      name: getappstatistics\n      operations:\n      - method: GET\n        name: getappstatistics\n        description: Application statistics\n        call: hadoop.getappstatistics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hadoop-mcp\n    transport: http\n    description: MCP adapter for Apache Hadoop REST APIs for AI agent use.\n    tools:\n    - name: webhdfsget\n      description: WebHDFS GET operations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: hadoop.webhdfsget\n      with:\n        path: tools.path\n        op: tools.op\n      inputParameters:\n      - name: path\n        type: string\n        description: path\n        required: true\n      - name: op\n        type: string\n        description: op\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: webhdfsput\n      description: WebHDFS PUT operations\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: hadoop.webhdfsput\n      with:\n        path: tools.path\n        op: tools.op\n      inputParameters:\n      - name: path\n        type: string\n        description: path\n        required: true\n      - name: op\n        type: string\n        description: op\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: webhdfspost\n      description: WebHDFS POST operations\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: hadoop.webhdfspost\n      with:\n        path: tools.path\n        op: tools.op\n      inputParameters:\n      - name: path\n        type: string\n        description: path\n        required: true\n      - name: op\n        type: string\n        description: op\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: webhdfsdelete\n      description: WebHDFS DELETE\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hadoop.webhdfsdelete\n      with:\n        path: tools.path\n        op: tools.op\n      inputParameters:\n      - name: path\n        type: string\n        description: path\n        required: true\n      - name: op\n        type: string\n        description: op\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclusterinfo\n      description:\
  \ Cluster info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hadoop.getclusterinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclustermetrics\n      description: Cluster metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hadoop.getclustermetrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getscheduler\n      description: Scheduler info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hadoop.getscheduler\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapps\n      description: List applications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hadoop.listapps\n      with:\n        state: tools.state\n        user: tools.user\n        queue: tools.queue\n\
  \      inputParameters:\n      - name: state\n        type: string\n        description: state\n      - name: user\n        type: string\n        description: user\n      - name: queue\n        type: string\n        description: queue\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submitapp\n      description: Submit a new application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hadoop.submitapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapp\n      description: Application details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hadoop.getapp\n      with:\n        appid: tools.appid\n      inputParameters:\n      - name: appid\n        type: string\n        description: appid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateappstate\n\
  \      description: Update application state\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: hadoop.updateappstate\n      with:\n        appid: tools.appid\n      inputParameters:\n      - name: appid\n        type: string\n        description: appid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateappqueue\n      description: Move application to a different queue\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: hadoop.updateappqueue\n      with:\n        appid: tools.appid\n      inputParameters:\n      - name: appid\n        type: string\n        description: appid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateapppriority\n      description: Update application priority\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ true\n      call: hadoop.updateapppriority\n      with:\n        appid: tools.appid\n      inputParameters:\n      - name: appid\n        type: string\n        description: appid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listappattempts\n      description: List application attempts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hadoop.listappattempts\n      with:\n        appid: tools.appid\n      inputParameters:\n      - name: appid\n        type: string\n        description: appid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnodes\n      description: List nodes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hadoop.listnodes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnode\n      description: Node details\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hadoop.getnode\n      with:\n        nodeid: tools.nodeid\n      inputParameters:\n      - name: nodeid\n        type: string\n        description: nodeid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getappstatistics\n      description: Application statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hadoop.getappstatistics\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hadoop/refs/heads/main/capabilities/hadoop-capability.yaml
tags:
- Hadoop
- API
tools:
- description: WebHDFS GET operations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: webhdfsget
- description: WebHDFS PUT operations
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: webhdfsput
- description: WebHDFS POST operations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: webhdfspost
- description: WebHDFS DELETE
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: webhdfsdelete
- description: Cluster info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclusterinfo
- description: Cluster metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclustermetrics
- description: Scheduler info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getscheduler
- description: List applications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapps
- description: Submit a new application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitapp
- description: Application details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapp
- description: Update application state
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateappstate
- description: Move application to a different queue
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateappqueue
- description: Update application priority
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateapppriority
- description: List application attempts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listappattempts
- description: List nodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnodes
- description: Node details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnode
- description: Application statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getappstatistics
---
