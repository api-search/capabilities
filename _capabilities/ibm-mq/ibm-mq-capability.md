---
categories: []
consumed_apis: []
description: REST API for administering and monitoring IBM MQ queue managers, queues, topics, subscriptions, and channels. Provides programmatic access to manage MQ objects and retrieve status information.
layout: capability
name: IBM MQ Administration REST API
operations:
- description: IBM MQ List queue managers
  method: GET
  name: listqueuemanagers
  path: /admin/qmgr
- description: IBM MQ Get queue manager details
  method: GET
  name: getqueuemanager
  path: /admin/qmgr/{qmgrName}
- description: IBM MQ List queues
  method: GET
  name: listqueues
  path: /admin/qmgr/{qmgrName}/queue
- description: IBM MQ Create a queue
  method: POST
  name: createqueue
  path: /admin/qmgr/{qmgrName}/queue
- description: IBM MQ Get queue details
  method: GET
  name: getqueue
  path: /admin/qmgr/{qmgrName}/queue/{queueName}
- description: IBM MQ Update a queue
  method: PATCH
  name: updatequeue
  path: /admin/qmgr/{qmgrName}/queue/{queueName}
- description: IBM MQ Delete a queue
  method: DELETE
  name: deletequeue
  path: /admin/qmgr/{qmgrName}/queue/{queueName}
- description: IBM MQ List topics
  method: GET
  name: listtopics
  path: /admin/qmgr/{qmgrName}/topic
- description: IBM MQ Create a topic
  method: POST
  name: createtopic
  path: /admin/qmgr/{qmgrName}/topic
- description: IBM MQ Get topic details
  method: GET
  name: gettopic
  path: /admin/qmgr/{qmgrName}/topic/{topicName}
- description: IBM MQ Update a topic
  method: PATCH
  name: updatetopic
  path: /admin/qmgr/{qmgrName}/topic/{topicName}
- description: IBM MQ Delete a topic
  method: DELETE
  name: deletetopic
  path: /admin/qmgr/{qmgrName}/topic/{topicName}
- description: IBM MQ List subscriptions
  method: GET
  name: listsubscriptions
  path: /admin/qmgr/{qmgrName}/subscription
- description: IBM MQ Create a subscription
  method: POST
  name: createsubscription
  path: /admin/qmgr/{qmgrName}/subscription
- description: IBM MQ Get subscription details
  method: GET
  name: getsubscription
  path: /admin/qmgr/{qmgrName}/subscription/{subscriptionId}
- description: IBM MQ Delete a subscription
  method: DELETE
  name: deletesubscription
  path: /admin/qmgr/{qmgrName}/subscription/{subscriptionId}
- description: IBM MQ List channels
  method: GET
  name: listchannels
  path: /admin/qmgr/{qmgrName}/channel
- description: IBM MQ Create a channel
  method: POST
  name: createchannel
  path: /admin/qmgr/{qmgrName}/channel
- description: IBM MQ Get channel details
  method: GET
  name: getchannel
  path: /admin/qmgr/{qmgrName}/channel/{channelName}
- description: IBM MQ Update a channel
  method: PATCH
  name: updatechannel
  path: /admin/qmgr/{qmgrName}/channel/{channelName}
- description: IBM MQ Delete a channel
  method: DELETE
  name: deletechannel
  path: /admin/qmgr/{qmgrName}/channel/{channelName}
- description: IBM MQ List MQ installations
  method: GET
  name: listinstallations
  path: /admin/installation
personas: []
provider_name: IBM MQ
provider_slug: ibm-mq
search_terms:
- deletesubscription
- ibm mq list mq installations
- ibm mq list queue managers
- integration
- listqueuemanagers
- updatechannel
- ibm mq update a queue
- getchannel
- getqueuemanager
- updatequeue
- ibm mq get subscription details
- middleware
- ibm mq update a channel
- ibm mq delete a subscription
- ibm mq list subscriptions
- ibm mq create a channel
- getsubscription
- ibm mq list topics
- listchannels
- createsubscription
- enterprise
- ibm mq list channels
- getqueue
- deletechannel
- ibm mq delete a channel
- deletequeue
- ibm mq get queue manager details
- gettopic
- createchannel
- listinstallations
- async
- ibm mq delete a topic
- listqueues
- messaging
- ibm mq update a topic
- updatetopic
- ibm mq get queue details
- mq
- api
- createtopic
- ibm mq get topic details
- ibm mq delete a queue
- ibm mq create a queue
- createqueue
- listsubscriptions
- ibm mq create a subscription
- listtopics
- ibm mq get channel details
- ibm
- deletetopic
- ibm mq create a topic
- queue
- ibm mq list queues
slug: ibm-mq-capability
source_filename: ibm-mq-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: IBM MQ Administration REST API\n  description: REST API for administering and monitoring IBM MQ queue managers, queues, topics, subscriptions, and channels.\n    Provides programmatic access to manage MQ objects and retrieve status information.\n  tags:\n  - Ibm\n  - Mq\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ibm-mq\n    baseUri: https://localhost:9443/ibmmq/rest/v2\n    description: IBM MQ Administration REST API HTTP API.\n    authentication:\n      type: basic\n      username: '{{IBM_MQ_USERNAME}}'\n      password: '{{IBM_MQ_PASSWORD}}'\n    resources:\n    - name: admin-qmgr\n      path: /admin/qmgr\n      operations:\n      - name: listqueuemanagers\n        method: GET\n        description: IBM MQ List queue managers\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter queue managers\
  \ by name (supports wildcard *)\n        - name: attributes\n          in: query\n          type: string\n          description: Comma-separated list of attributes to return\n        - name: status\n          in: query\n          type: string\n          description: Comma-separated list of status attributes to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-qmgr-qmgrname\n      path: /admin/qmgr/{qmgrName}\n      operations:\n      - name: getqueuemanager\n        method: GET\n        description: IBM MQ Get queue manager details\n        inputParameters:\n        - name: attributes\n          in: query\n          type: string\n          description: Comma-separated list of attributes to return\n        - name: status\n          in: query\n          type: string\n          description: Comma-separated list of status attributes to return\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: admin-qmgr-qmgrname-queue\n      path: /admin/qmgr/{qmgrName}/queue\n      operations:\n      - name: listqueues\n        method: GET\n        description: IBM MQ List queues\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter queues by name (supports wildcard *)\n        - name: type\n          in: query\n          type: string\n          description: Filter by queue type\n        - name: attributes\n          in: query\n          type: string\n          description: Comma-separated list of attributes to return\n        - name: status\n          in: query\n          type: string\n          description: Comma-separated list of status attributes to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createqueue\n        method: POST\n     \
  \   description: IBM MQ Create a queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-qmgr-qmgrname-queue-queuename\n      path: /admin/qmgr/{qmgrName}/queue/{queueName}\n      operations:\n      - name: getqueue\n        method: GET\n        description: IBM MQ Get queue details\n        inputParameters:\n        - name: attributes\n          in: query\n          type: string\n          description: Comma-separated list of attributes to return\n        - name: status\n          in: query\n          type: string\n          description: Comma-separated list of status attributes to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatequeue\n        method: PATCH\n        description: IBM MQ Update a queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n      - name: deletequeue\n        method: DELETE\n        description: IBM MQ Delete a queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-qmgr-qmgrname-topic\n      path: /admin/qmgr/{qmgrName}/topic\n      operations:\n      - name: listtopics\n        method: GET\n        description: IBM MQ List topics\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter topics by name (supports wildcard *)\n        - name: attributes\n          in: query\n          type: string\n          description: Comma-separated list of attributes to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtopic\n        method: POST\n        description: IBM MQ Create a topic\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-qmgr-qmgrname-topic-topicname\n      path: /admin/qmgr/{qmgrName}/topic/{topicName}\n      operations:\n      - name: gettopic\n        method: GET\n        description: IBM MQ Get topic details\n        inputParameters:\n        - name: attributes\n          in: query\n          type: string\n          description: Comma-separated list of attributes to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetopic\n        method: PATCH\n        description: IBM MQ Update a topic\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetopic\n        method: DELETE\n        description: IBM MQ Delete a topic\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: admin-qmgr-qmgrname-subscription\n      path: /admin/qmgr/{qmgrName}/subscription\n      operations:\n      - name: listsubscriptions\n        method: GET\n        description: IBM MQ List subscriptions\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter subscriptions by name (supports wildcard *)\n        - name: attributes\n          in: query\n          type: string\n          description: Comma-separated list of attributes to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsubscription\n        method: POST\n        description: IBM MQ Create a subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-qmgr-qmgrname-subscription-subscriptionid\n\
  \      path: /admin/qmgr/{qmgrName}/subscription/{subscriptionId}\n      operations:\n      - name: getsubscription\n        method: GET\n        description: IBM MQ Get subscription details\n        inputParameters:\n        - name: attributes\n          in: query\n          type: string\n          description: Comma-separated list of attributes to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesubscription\n        method: DELETE\n        description: IBM MQ Delete a subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-qmgr-qmgrname-channel\n      path: /admin/qmgr/{qmgrName}/channel\n      operations:\n      - name: listchannels\n        method: GET\n        description: IBM MQ List channels\n        inputParameters:\n        - name: name\n          in: query\n          type:\
  \ string\n          description: Filter channels by name (supports wildcard *)\n        - name: type\n          in: query\n          type: string\n          description: Filter by channel type\n        - name: attributes\n          in: query\n          type: string\n          description: Comma-separated list of attributes to return\n        - name: status\n          in: query\n          type: string\n          description: Comma-separated list of status attributes to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createchannel\n        method: POST\n        description: IBM MQ Create a channel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-qmgr-qmgrname-channel-channelname\n      path: /admin/qmgr/{qmgrName}/channel/{channelName}\n      operations:\n      - name: getchannel\n        method:\
  \ GET\n        description: IBM MQ Get channel details\n        inputParameters:\n        - name: attributes\n          in: query\n          type: string\n          description: Comma-separated list of attributes to return\n        - name: status\n          in: query\n          type: string\n          description: Comma-separated list of status attributes to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatechannel\n        method: PATCH\n        description: IBM MQ Update a channel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletechannel\n        method: DELETE\n        description: IBM MQ Delete a channel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-installation\n      path: /admin/installation\n\
  \      operations:\n      - name: listinstallations\n        method: GET\n        description: IBM MQ List MQ installations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ibm-mq-rest\n    description: REST adapter for IBM MQ Administration REST API.\n    resources:\n    - path: /admin/qmgr\n      name: listqueuemanagers\n      operations:\n      - method: GET\n        name: listqueuemanagers\n        description: IBM MQ List queue managers\n        call: ibm-mq.listqueuemanagers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}\n      name: getqueuemanager\n      operations:\n      - method: GET\n        name: getqueuemanager\n        description: IBM MQ Get queue manager details\n        call: ibm-mq.getqueuemanager\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /admin/qmgr/{qmgrName}/queue\n      name: listqueues\n      operations:\n      - method: GET\n        name: listqueues\n        description: IBM MQ List queues\n        call: ibm-mq.listqueues\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/queue\n      name: createqueue\n      operations:\n      - method: POST\n        name: createqueue\n        description: IBM MQ Create a queue\n        call: ibm-mq.createqueue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/queue/{queueName}\n      name: getqueue\n      operations:\n      - method: GET\n        name: getqueue\n        description: IBM MQ Get queue details\n        call: ibm-mq.getqueue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/queue/{queueName}\n      name: updatequeue\n      operations:\n      - method: PATCH\n        name: updatequeue\n\
  \        description: IBM MQ Update a queue\n        call: ibm-mq.updatequeue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/queue/{queueName}\n      name: deletequeue\n      operations:\n      - method: DELETE\n        name: deletequeue\n        description: IBM MQ Delete a queue\n        call: ibm-mq.deletequeue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/topic\n      name: listtopics\n      operations:\n      - method: GET\n        name: listtopics\n        description: IBM MQ List topics\n        call: ibm-mq.listtopics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/topic\n      name: createtopic\n      operations:\n      - method: POST\n        name: createtopic\n        description: IBM MQ Create a topic\n        call: ibm-mq.createtopic\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /admin/qmgr/{qmgrName}/topic/{topicName}\n      name: gettopic\n      operations:\n      - method: GET\n        name: gettopic\n        description: IBM MQ Get topic details\n        call: ibm-mq.gettopic\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/topic/{topicName}\n      name: updatetopic\n      operations:\n      - method: PATCH\n        name: updatetopic\n        description: IBM MQ Update a topic\n        call: ibm-mq.updatetopic\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/topic/{topicName}\n      name: deletetopic\n      operations:\n      - method: DELETE\n        name: deletetopic\n        description: IBM MQ Delete a topic\n        call: ibm-mq.deletetopic\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/subscription\n      name: listsubscriptions\n   \
  \   operations:\n      - method: GET\n        name: listsubscriptions\n        description: IBM MQ List subscriptions\n        call: ibm-mq.listsubscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/subscription\n      name: createsubscription\n      operations:\n      - method: POST\n        name: createsubscription\n        description: IBM MQ Create a subscription\n        call: ibm-mq.createsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/subscription/{subscriptionId}\n      name: getsubscription\n      operations:\n      - method: GET\n        name: getsubscription\n        description: IBM MQ Get subscription details\n        call: ibm-mq.getsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/subscription/{subscriptionId}\n      name: deletesubscription\n      operations:\n\
  \      - method: DELETE\n        name: deletesubscription\n        description: IBM MQ Delete a subscription\n        call: ibm-mq.deletesubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/channel\n      name: listchannels\n      operations:\n      - method: GET\n        name: listchannels\n        description: IBM MQ List channels\n        call: ibm-mq.listchannels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/channel\n      name: createchannel\n      operations:\n      - method: POST\n        name: createchannel\n        description: IBM MQ Create a channel\n        call: ibm-mq.createchannel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/channel/{channelName}\n      name: getchannel\n      operations:\n      - method: GET\n        name: getchannel\n        description: IBM MQ Get channel\
  \ details\n        call: ibm-mq.getchannel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/channel/{channelName}\n      name: updatechannel\n      operations:\n      - method: PATCH\n        name: updatechannel\n        description: IBM MQ Update a channel\n        call: ibm-mq.updatechannel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/qmgr/{qmgrName}/channel/{channelName}\n      name: deletechannel\n      operations:\n      - method: DELETE\n        name: deletechannel\n        description: IBM MQ Delete a channel\n        call: ibm-mq.deletechannel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/installation\n      name: listinstallations\n      operations:\n      - method: GET\n        name: listinstallations\n        description: IBM MQ List MQ installations\n        call: ibm-mq.listinstallations\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ibm-mq-mcp\n    transport: http\n    description: MCP adapter for IBM MQ Administration REST API for AI agent use.\n    tools:\n    - name: listqueuemanagers\n      description: IBM MQ List queue managers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm-mq.listqueuemanagers\n      with:\n        name: tools.name\n        attributes: tools.attributes\n        status: tools.status\n      inputParameters:\n      - name: name\n        type: string\n        description: Filter queue managers by name (supports wildcard *)\n      - name: attributes\n        type: string\n        description: Comma-separated list of attributes to return\n      - name: status\n        type: string\n        description: Comma-separated list of status attributes to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getqueuemanager\n\
  \      description: IBM MQ Get queue manager details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm-mq.getqueuemanager\n      with:\n        attributes: tools.attributes\n        status: tools.status\n      inputParameters:\n      - name: attributes\n        type: string\n        description: Comma-separated list of attributes to return\n      - name: status\n        type: string\n        description: Comma-separated list of status attributes to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listqueues\n      description: IBM MQ List queues\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm-mq.listqueues\n      with:\n        name: tools.name\n        type: tools.type\n        attributes: tools.attributes\n        status: tools.status\n      inputParameters:\n      - name: name\n        type: string\n        description: Filter\
  \ queues by name (supports wildcard *)\n      - name: type\n        type: string\n        description: Filter by queue type\n      - name: attributes\n        type: string\n        description: Comma-separated list of attributes to return\n      - name: status\n        type: string\n        description: Comma-separated list of status attributes to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createqueue\n      description: IBM MQ Create a queue\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibm-mq.createqueue\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getqueue\n      description: IBM MQ Get queue details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm-mq.getqueue\n      with:\n        attributes: tools.attributes\n        status: tools.status\n      inputParameters:\n      - name: attributes\n\
  \        type: string\n        description: Comma-separated list of attributes to return\n      - name: status\n        type: string\n        description: Comma-separated list of status attributes to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatequeue\n      description: IBM MQ Update a queue\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibm-mq.updatequeue\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletequeue\n      description: IBM MQ Delete a queue\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ibm-mq.deletequeue\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtopics\n      description: IBM MQ List topics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm-mq.listtopics\n      with:\n    \
  \    name: tools.name\n        attributes: tools.attributes\n      inputParameters:\n      - name: name\n        type: string\n        description: Filter topics by name (supports wildcard *)\n      - name: attributes\n        type: string\n        description: Comma-separated list of attributes to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtopic\n      description: IBM MQ Create a topic\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibm-mq.createtopic\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettopic\n      description: IBM MQ Get topic details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm-mq.gettopic\n      with:\n        attributes: tools.attributes\n      inputParameters:\n      - name: attributes\n        type: string\n        description: Comma-separated list of attributes\
  \ to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatetopic\n      description: IBM MQ Update a topic\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibm-mq.updatetopic\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetopic\n      description: IBM MQ Delete a topic\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ibm-mq.deletetopic\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsubscriptions\n      description: IBM MQ List subscriptions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm-mq.listsubscriptions\n      with:\n        name: tools.name\n        attributes: tools.attributes\n      inputParameters:\n      - name: name\n        type: string\n        description: Filter subscriptions by name\
  \ (supports wildcard *)\n      - name: attributes\n        type: string\n        description: Comma-separated list of attributes to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsubscription\n      description: IBM MQ Create a subscription\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibm-mq.createsubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsubscription\n      description: IBM MQ Get subscription details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm-mq.getsubscription\n      with:\n        attributes: tools.attributes\n      inputParameters:\n      - name: attributes\n        type: string\n        description: Comma-separated list of attributes to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesubscription\n      description:\
  \ IBM MQ Delete a subscription\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ibm-mq.deletesubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listchannels\n      description: IBM MQ List channels\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm-mq.listchannels\n      with:\n        name: tools.name\n        type: tools.type\n        attributes: tools.attributes\n        status: tools.status\n      inputParameters:\n      - name: name\n        type: string\n        description: Filter channels by name (supports wildcard *)\n      - name: type\n        type: string\n        description: Filter by channel type\n      - name: attributes\n        type: string\n        description: Comma-separated list of attributes to return\n      - name: status\n        type: string\n        description: Comma-separated list of status attributes to\
  \ return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createchannel\n      description: IBM MQ Create a channel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibm-mq.createchannel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getchannel\n      description: IBM MQ Get channel details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm-mq.getchannel\n      with:\n        attributes: tools.attributes\n        status: tools.status\n      inputParameters:\n      - name: attributes\n        type: string\n        description: Comma-separated list of attributes to return\n      - name: status\n        type: string\n        description: Comma-separated list of status attributes to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatechannel\n      description: IBM MQ Update\
  \ a channel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibm-mq.updatechannel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletechannel\n      description: IBM MQ Delete a channel\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ibm-mq.deletechannel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinstallations\n      description: IBM MQ List MQ installations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm-mq.listinstallations\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    IBM_MQ_USERNAME: IBM_MQ_USERNAME\n    IBM_MQ_PASSWORD: IBM_MQ_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ibm-mq/refs/heads/main/capabilities/ibm-mq-capability.yaml
tags:
- Ibm
- Mq
- API
tools:
- description: IBM MQ List queue managers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listqueuemanagers
- description: IBM MQ Get queue manager details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getqueuemanager
- description: IBM MQ List queues
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listqueues
- description: IBM MQ Create a queue
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createqueue
- description: IBM MQ Get queue details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getqueue
- description: IBM MQ Update a queue
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatequeue
- description: IBM MQ Delete a queue
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletequeue
- description: IBM MQ List topics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtopics
- description: IBM MQ Create a topic
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtopic
- description: IBM MQ Get topic details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettopic
- description: IBM MQ Update a topic
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatetopic
- description: IBM MQ Delete a topic
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetopic
- description: IBM MQ List subscriptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsubscriptions
- description: IBM MQ Create a subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsubscription
- description: IBM MQ Get subscription details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubscription
- description: IBM MQ Delete a subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesubscription
- description: IBM MQ List channels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchannels
- description: IBM MQ Create a channel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchannel
- description: IBM MQ Get channel details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchannel
- description: IBM MQ Update a channel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatechannel
- description: IBM MQ Delete a channel
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletechannel
- description: IBM MQ List MQ installations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstallations
---
