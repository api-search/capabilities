---
categories: []
consumed_apis: []
description: The RabbitMQ Management Plugin provides an HTTP-based API for management and monitoring of RabbitMQ nodes and clusters. It allows management of exchanges, queues, bindings, virtual hosts, users, permissions, policies, and more.
layout: capability
name: RabbitMQ Management HTTP API
operations:
- description: Get cluster overview
  method: GET
  name: getoverview
  path: /overview
- description: Get cluster name
  method: GET
  name: getclustername
  path: /cluster-name
- description: Set cluster name
  method: PUT
  name: setclustername
  path: /cluster-name
- description: List nodes
  method: GET
  name: listnodes
  path: /nodes
- description: Get node details
  method: GET
  name: getnode
  path: /nodes/{name}
- description: List connections
  method: GET
  name: listconnections
  path: /connections
- description: Get connection
  method: GET
  name: getconnection
  path: /connections/{name}
- description: Close connection
  method: DELETE
  name: deleteconnection
  path: /connections/{name}
- description: List channels
  method: GET
  name: listchannels
  path: /channels
- description: List virtual hosts
  method: GET
  name: listvhosts
  path: /vhosts
- description: Get virtual host
  method: GET
  name: getvhost
  path: /vhosts/{vhost}
- description: Create virtual host
  method: PUT
  name: createvhost
  path: /vhosts/{vhost}
- description: Delete virtual host
  method: DELETE
  name: deletevhost
  path: /vhosts/{vhost}
- description: List all exchanges
  method: GET
  name: listexchanges
  path: /exchanges
- description: List exchanges in a virtual host
  method: GET
  name: listexchangesinvhost
  path: /exchanges/{vhost}
- description: Get exchange
  method: GET
  name: getexchange
  path: /exchanges/{vhost}/{exchange}
- description: Create exchange
  method: PUT
  name: createexchange
  path: /exchanges/{vhost}/{exchange}
- description: Delete exchange
  method: DELETE
  name: deleteexchange
  path: /exchanges/{vhost}/{exchange}
- description: Publish message to exchange
  method: POST
  name: publishmessage
  path: /exchanges/{vhost}/{exchange}/publish
- description: List all queues
  method: GET
  name: listqueues
  path: /queues
- description: List queues in virtual host
  method: GET
  name: listqueuesinvhost
  path: /queues/{vhost}
- description: Get queue
  method: GET
  name: getqueue
  path: /queues/{vhost}/{queue}
- description: Create queue
  method: PUT
  name: createqueue
  path: /queues/{vhost}/{queue}
- description: Delete queue
  method: DELETE
  name: deletequeue
  path: /queues/{vhost}/{queue}
- description: Get messages from queue
  method: POST
  name: getmessages
  path: /queues/{vhost}/{queue}/get
- description: Purge queue
  method: DELETE
  name: purgequeue
  path: /queues/{vhost}/{queue}/purge
- description: List all bindings
  method: GET
  name: listbindings
  path: /bindings
- description: List bindings between exchange and queue
  method: GET
  name: listbindingsbetween
  path: /bindings/{vhost}/e/{exchange}/q/{queue}
- description: Create binding
  method: POST
  name: createbinding
  path: /bindings/{vhost}/e/{exchange}/q/{queue}
- description: List users
  method: GET
  name: listusers
  path: /users
- description: Get user
  method: GET
  name: getuser
  path: /users/{user}
- description: Create or update user
  method: PUT
  name: createuser
  path: /users/{user}
- description: Delete user
  method: DELETE
  name: deleteuser
  path: /users/{user}
- description: Get user permissions
  method: GET
  name: getuserpermissions
  path: /permissions/{vhost}/{user}
- description: Set user permissions
  method: PUT
  name: setuserpermissions
  path: /permissions/{vhost}/{user}
- description: Delete user permissions
  method: DELETE
  name: deleteuserpermissions
  path: /permissions/{vhost}/{user}
- description: List policies in vhost
  method: GET
  name: listpolicies
  path: /policies/{vhost}
- description: Get policy
  method: GET
  name: getpolicy
  path: /policies/{vhost}/{policy}
- description: Create or update policy
  method: PUT
  name: createpolicy
  path: /policies/{vhost}/{policy}
- description: Delete policy
  method: DELETE
  name: deletepolicy
  path: /policies/{vhost}/{policy}
- description: Health check - alarms
  method: GET
  name: healthcheckalarms
  path: /health/checks/alarms
- description: Health check - local alarms
  method: GET
  name: healthchecklocalalarms
  path: /health/checks/local-alarms
- description: Get current user
  method: GET
  name: whoami
  path: /whoami
- description: Export definitions
  method: GET
  name: getdefinitions
  path: /definitions
- description: Import definitions
  method: POST
  name: postdefinitions
  path: /definitions
personas: []
provider_name: RabbitMQ
provider_slug: rabbitmq
search_terms:
- createexchange
- get virtual host
- list all exchanges
- list all bindings
- listvhosts
- publish message to exchange
- purgequeue
- list virtual hosts
- getclustername
- getuserpermissions
- message broker
- event streaming
- getoverview
- set cluster name
- export definitions
- delete user
- listqueues
- setuserpermissions
- api
- list channels
- get messages from queue
- getuser
- get policy
- deletepolicy
- health check - local alarms
- publishmessage
- listqueuesinvhost
- deleteuser
- rabbitmq
- createuser
- distributed systems
- list all queues
- listnodes
- getdefinitions
- getnode
- listconnections
- listexchanges
- listchannels
- deletequeue
- getmessages
- messaging
- getvhost
- delete policy
- get cluster name
- listbindingsbetween
- get current user
- close connection
- get user permissions
- listusers
- get connection
- postdefinitions
- list queues in virtual host
- create or update user
- create virtual host
- deletevhost
- listpolicies
- set user permissions
- listexchangesinvhost
- createvhost
- createbinding
- create or update policy
- createqueue
- amqp
- list connections
- listbindings
- list exchanges in a virtual host
- delete exchange
- health check - alarms
- list policies in vhost
- list bindings between exchange and queue
- whoami
- delete user permissions
- queue
- import definitions
- healthcheckalarms
- createpolicy
- deleteuserpermissions
- setclustername
- list nodes
- delete virtual host
- get exchange
- create queue
- get node details
- deleteconnection
- getqueue
- getpolicy
- getconnection
- deleteexchange
- get queue
- healthchecklocalalarms
- get cluster overview
- getexchange
- delete queue
- purge queue
- get user
- create exchange
- list users
- create binding
slug: rabbitmq-capability
source_filename: rabbitmq-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: RabbitMQ Management HTTP API\n  description: The RabbitMQ Management Plugin provides an HTTP-based API for management and monitoring of RabbitMQ nodes and\n    clusters. It allows management of exchanges, queues, bindings, virtual hosts, users, permissions, policies, and more.\n  tags:\n  - Rabbitmq\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: rabbitmq\n    baseUri: http://localhost:15672/api\n    description: RabbitMQ Management HTTP API HTTP API.\n    authentication:\n      type: basic\n      username: '{{RABBITMQ_USERNAME}}'\n      password: '{{RABBITMQ_PASSWORD}}'\n    resources:\n    - name: overview\n      path: /overview\n      operations:\n      - name: getoverview\n        method: GET\n        description: Get cluster overview\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \   - name: cluster-name\n      path: /cluster-name\n      operations:\n      - name: getclustername\n        method: GET\n        description: Get cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setclustername\n        method: PUT\n        description: Set cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nodes\n      path: /nodes\n      operations:\n      - name: listnodes\n        method: GET\n        description: List nodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nodes-name\n      path: /nodes/{name}\n      operations:\n      - name: getnode\n        method: GET\n        description: Get node details\n        inputParameters:\n        - name: name\n          in: path\n        \
  \  type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connections\n      path: /connections\n      operations:\n      - name: listconnections\n        method: GET\n        description: List connections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connections-name\n      path: /connections/{name}\n      operations:\n      - name: getconnection\n        method: GET\n        description: Get connection\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteconnection\n        method: DELETE\n        description: Close connection\n        inputParameters:\n      \
  \  - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: channels\n      path: /channels\n      operations:\n      - name: listchannels\n        method: GET\n        description: List channels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vhosts\n      path: /vhosts\n      operations:\n      - name: listvhosts\n        method: GET\n        description: List virtual hosts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vhosts-vhost\n      path: /vhosts/{vhost}\n      operations:\n      - name: getvhost\n        method: GET\n        description: Get virtual host\n        inputParameters:\n        - name: vhost\n          in: path\n       \
  \   type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvhost\n        method: PUT\n        description: Create virtual host\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletevhost\n        method: DELETE\n        description: Delete virtual host\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: exchanges\n      path: /exchanges\n      operations:\n      - name: listexchanges\n        method: GET\n        description: List all exchanges\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: exchanges-vhost\n      path: /exchanges/{vhost}\n      operations:\n      - name: listexchangesinvhost\n        method: GET\n        description: List exchanges in a virtual host\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: exchanges-vhost-exchange\n      path: /exchanges/{vhost}/{exchange}\n      operations:\n      - name: getexchange\n        method: GET\n        description: Get exchange\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name: exchange\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createexchange\n        method: PUT\n        description: Create exchange\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name: exchange\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteexchange\n        method: DELETE\n        description: Delete exchange\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name: exchange\n          in: path\n          type: string\n          required: true\n        - name: if-unused\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: exchanges-vhost-exchange-publish\n      path: /exchanges/{vhost}/{exchange}/publish\n      operations:\n      - name: publishmessage\n        method: POST\n        description: Publish message to exchange\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name: exchange\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queues\n      path: /queues\n      operations:\n      - name: listqueues\n        method: GET\n        description: List all queues\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queues-vhost\n      path: /queues/{vhost}\n      operations:\n      - name: listqueuesinvhost\n        method: GET\n        description:\
  \ List queues in virtual host\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queues-vhost-queue\n      path: /queues/{vhost}/{queue}\n      operations:\n      - name: getqueue\n        method: GET\n        description: Get queue\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name: queue\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createqueue\n        method: PUT\n        description: Create queue\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name: queue\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletequeue\n        method: DELETE\n        description: Delete queue\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name: queue\n          in: path\n          type: string\n          required: true\n        - name: if-empty\n          in: query\n          type: boolean\n        - name: if-unused\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queues-vhost-queue-get\n      path: /queues/{vhost}/{queue}/get\n      operations:\n      - name: getmessages\n        method: POST\n        description: Get messages from queue\n        inputParameters:\n        - name:\
  \ vhost\n          in: path\n          type: string\n          required: true\n        - name: queue\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queues-vhost-queue-purge\n      path: /queues/{vhost}/{queue}/purge\n      operations:\n      - name: purgequeue\n        method: DELETE\n        description: Purge queue\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name: queue\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bindings\n      path: /bindings\n      operations:\n      - name: listbindings\n        method: GET\n        description: List all bindings\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bindings-vhost-e-exchange-q-queue\n      path: /bindings/{vhost}/e/{exchange}/q/{queue}\n      operations:\n      - name: listbindingsbetween\n        method: GET\n        description: List bindings between exchange and queue\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name: exchange\n          in: path\n          type: string\n          required: true\n        - name: queue\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbinding\n        method: POST\n        description: Create binding\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name:\
  \ exchange\n          in: path\n          type: string\n          required: true\n        - name: queue\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: listusers\n        method: GET\n        description: List users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-user\n      path: /users/{user}\n      operations:\n      - name: getuser\n        method: GET\n        description: Get user\n        inputParameters:\n        - name: user\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: PUT\n\
  \        description: Create or update user\n        inputParameters:\n        - name: user\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Delete user\n        inputParameters:\n        - name: user\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: permissions-vhost-user\n      path: /permissions/{vhost}/{user}\n      operations:\n      - name: getuserpermissions\n        method: GET\n        description: Get user permissions\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name: user\n          in: path\n          type: string\n \
  \         required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setuserpermissions\n        method: PUT\n        description: Set user permissions\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name: user\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuserpermissions\n        method: DELETE\n        description: Delete user permissions\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name: user\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: policies-vhost\n      path: /policies/{vhost}\n      operations:\n      - name: listpolicies\n        method: GET\n        description: List policies in vhost\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies-vhost-policy\n      path: /policies/{vhost}/{policy}\n      operations:\n      - name: getpolicy\n        method: GET\n        description: Get policy\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name: policy\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpolicy\n        method:\
  \ PUT\n        description: Create or update policy\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name: policy\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepolicy\n        method: DELETE\n        description: Delete policy\n        inputParameters:\n        - name: vhost\n          in: path\n          type: string\n          required: true\n        - name: policy\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health-checks-alarms\n      path: /health/checks/alarms\n      operations:\n      - name: healthcheckalarms\n        method: GET\n        description: Health check - alarms\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health-checks-local-alarms\n      path: /health/checks/local-alarms\n      operations:\n      - name: healthchecklocalalarms\n        method: GET\n        description: Health check - local alarms\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: whoami\n      path: /whoami\n      operations:\n      - name: whoami\n        method: GET\n        description: Get current user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: definitions\n      path: /definitions\n      operations:\n      - name: getdefinitions\n        method: GET\n        description: Export definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: postdefinitions\n        method: POST\n        description: Import definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: rabbitmq-rest\n    description: REST adapter for RabbitMQ Management HTTP API.\n    resources:\n    - path: /overview\n      name: getoverview\n      operations:\n      - method: GET\n        name: getoverview\n        description: Get cluster overview\n        call: rabbitmq.getoverview\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cluster-name\n      name: getclustername\n      operations:\n      - method: GET\n        name: getclustername\n        description: Get cluster name\n        call: rabbitmq.getclustername\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cluster-name\n      name: setclustername\n \
  \     operations:\n      - method: PUT\n        name: setclustername\n        description: Set cluster name\n        call: rabbitmq.setclustername\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nodes\n      name: listnodes\n      operations:\n      - method: GET\n        name: listnodes\n        description: List nodes\n        call: rabbitmq.listnodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nodes/{name}\n      name: getnode\n      operations:\n      - method: GET\n        name: getnode\n        description: Get node details\n        call: rabbitmq.getnode\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /connections\n      name: listconnections\n      operations:\n      - method: GET\n        name: listconnections\n        description: List connections\n        call: rabbitmq.listconnections\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /connections/{name}\n      name: getconnection\n      operations:\n      - method: GET\n        name: getconnection\n        description: Get connection\n        call: rabbitmq.getconnection\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /connections/{name}\n      name: deleteconnection\n      operations:\n      - method: DELETE\n        name: deleteconnection\n        description: Close connection\n        call: rabbitmq.deleteconnection\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /channels\n      name: listchannels\n      operations:\n      - method: GET\n        name: listchannels\n        description: List channels\n        call: rabbitmq.listchannels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vhosts\n      name: listvhosts\n\
  \      operations:\n      - method: GET\n        name: listvhosts\n        description: List virtual hosts\n        call: rabbitmq.listvhosts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vhosts/{vhost}\n      name: getvhost\n      operations:\n      - method: GET\n        name: getvhost\n        description: Get virtual host\n        call: rabbitmq.getvhost\n        with:\n          vhost: rest.vhost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vhosts/{vhost}\n      name: createvhost\n      operations:\n      - method: PUT\n        name: createvhost\n        description: Create virtual host\n        call: rabbitmq.createvhost\n        with:\n          vhost: rest.vhost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vhosts/{vhost}\n      name: deletevhost\n      operations:\n      - method: DELETE\n        name: deletevhost\n        description: Delete virtual host\n\
  \        call: rabbitmq.deletevhost\n        with:\n          vhost: rest.vhost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /exchanges\n      name: listexchanges\n      operations:\n      - method: GET\n        name: listexchanges\n        description: List all exchanges\n        call: rabbitmq.listexchanges\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /exchanges/{vhost}\n      name: listexchangesinvhost\n      operations:\n      - method: GET\n        name: listexchangesinvhost\n        description: List exchanges in a virtual host\n        call: rabbitmq.listexchangesinvhost\n        with:\n          vhost: rest.vhost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /exchanges/{vhost}/{exchange}\n      name: getexchange\n      operations:\n      - method: GET\n        name: getexchange\n        description: Get exchange\n        call: rabbitmq.getexchange\n     \
  \   with:\n          vhost: rest.vhost\n          exchange: rest.exchange\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /exchanges/{vhost}/{exchange}\n      name: createexchange\n      operations:\n      - method: PUT\n        name: createexchange\n        description: Create exchange\n        call: rabbitmq.createexchange\n        with:\n          vhost: rest.vhost\n          exchange: rest.exchange\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /exchanges/{vhost}/{exchange}\n      name: deleteexchange\n      operations:\n      - method: DELETE\n        name: deleteexchange\n        description: Delete exchange\n        call: rabbitmq.deleteexchange\n        with:\n          vhost: rest.vhost\n          exchange: rest.exchange\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /exchanges/{vhost}/{exchange}/publish\n      name: publishmessage\n      operations:\n      -\
  \ method: POST\n        name: publishmessage\n        description: Publish message to exchange\n        call: rabbitmq.publishmessage\n        with:\n          vhost: rest.vhost\n          exchange: rest.exchange\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /queues\n      name: listqueues\n      operations:\n      - method: GET\n        name: listqueues\n        description: List all queues\n        call: rabbitmq.listqueues\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /queues/{vhost}\n      name: listqueuesinvhost\n      operations:\n      - method: GET\n        name: listqueuesinvhost\n        description: List queues in virtual host\n        call: rabbitmq.listqueuesinvhost\n        with:\n          vhost: rest.vhost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /queues/{vhost}/{queue}\n      name: getqueue\n      operations:\n      - method: GET\n        name:\
  \ getqueue\n        description: Get queue\n        call: rabbitmq.getqueue\n        with:\n          vhost: rest.vhost\n          queue: rest.queue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /queues/{vhost}/{queue}\n      name: createqueue\n      operations:\n      - method: PUT\n        name: createqueue\n        description: Create queue\n        call: rabbitmq.createqueue\n        with:\n          vhost: rest.vhost\n          queue: rest.queue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /queues/{vhost}/{queue}\n      name: deletequeue\n      operations:\n      - method: DELETE\n        name: deletequeue\n        description: Delete queue\n        call: rabbitmq.deletequeue\n        with:\n          vhost: rest.vhost\n          queue: rest.queue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /queues/{vhost}/{queue}/get\n      name: getmessages\n      operations:\n\
  \      - method: POST\n        name: getmessages\n        description: Get messages from queue\n        call: rabbitmq.getmessages\n        with:\n          vhost: rest.vhost\n          queue: rest.queue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /queues/{vhost}/{queue}/purge\n      name: purgequeue\n      operations:\n      - method: DELETE\n        name: purgequeue\n        description: Purge queue\n        call: rabbitmq.purgequeue\n        with:\n          vhost: rest.vhost\n          queue: rest.queue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bindings\n      name: listbindings\n      operations:\n      - method: GET\n        name: listbindings\n        description: List all bindings\n        call: rabbitmq.listbindings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bindings/{vhost}/e/{exchange}/q/{queue}\n      name: listbindingsbetween\n      operations:\n\
  \      - method: GET\n        name: listbindingsbetween\n        description: List bindings between exchange and queue\n        call: rabbitmq.listbindingsbetween\n        with:\n          vhost: rest.vhost\n          exchange: rest.exchange\n          queue: rest.queue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bindings/{vhost}/e/{exchange}/q/{queue}\n      name: createbinding\n      operations:\n      - method: POST\n        name: createbinding\n        description: Create binding\n        call: rabbitmq.createbinding\n        with:\n          vhost: rest.vhost\n          exchange: rest.exchange\n          queue: rest.queue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: List users\n        call: rabbitmq.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /users/{user}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Get user\n        call: rabbitmq.getuser\n        with:\n          user: rest.user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{user}\n      name: createuser\n      operations:\n      - method: PUT\n        name: createuser\n        description: Create or update user\n        call: rabbitmq.createuser\n        with:\n          user: rest.user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{user}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: Delete user\n        call: rabbitmq.deleteuser\n        with:\n          user: rest.user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /permissions/{vhost}/{user}\n      name: getuserpermissions\n      operations:\n\
  \      - method: GET\n        name: getuserpermissions\n        description: Get user permissions\n        call: rabbitmq.getuserpermissions\n        with:\n          vhost: rest.vhost\n          user: rest.user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /permissions/{vhost}/{user}\n      name: setuserpermissions\n      operations:\n      - method: PUT\n        name: setuserpermissions\n        description: Set user permissions\n        call: rabbitmq.setuserpermissions\n        with:\n          vhost: rest.vhost\n          user: rest.user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /permissions/{vhost}/{user}\n      name: deleteuserpermissions\n      operations:\n      - method: DELETE\n        name: deleteuserpermissions\n        description: Delete user permissions\n        call: rabbitmq.deleteuserpermissions\n        with:\n          vhost: rest.vhost\n          user: rest.user\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /policies/{vhost}\n      name: listpolicies\n      operations:\n      - method: GET\n        name: listpolicies\n        description: List policies in vhost\n        call: rabbitmq.listpolicies\n        with:\n          vhost: rest.vhost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policies/{vhost}/{policy}\n      name: getpolicy\n      operations:\n      - method: GET\n        name: getpolicy\n        description: Get policy\n        call: rabbitmq.getpolicy\n        with:\n          vhost: rest.vhost\n          policy: rest.policy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policies/{vhost}/{policy}\n      name: createpolicy\n      operations:\n      - method: PUT\n        name: createpolicy\n        description: Create or update policy\n        call: rabbitmq.createpolicy\n        with:\n          vhost: rest.vhost\n          policy: rest.policy\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policies/{vhost}/{policy}\n      name: deletepolicy\n      operations:\n      - method: DELETE\n        name: deletepolicy\n        description: Delete policy\n        call: rabbitmq.deletepolicy\n        with:\n          vhost: rest.vhost\n          policy: rest.policy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /health/checks/alarms\n      name: healthcheckalarms\n      operations:\n      - method: GET\n        name: healthcheckalarms\n        description: Health check - alarms\n        call: rabbitmq.healthcheckalarms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /health/checks/local-alarms\n      name: healthchecklocalalarms\n      operations:\n      - method: GET\n        name: healthchecklocalalarms\n        description: Health check - local alarms\n        call: rabbitmq.healthchecklocalalarms\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /whoami\n      name: whoami\n      operations:\n      - method: GET\n        name: whoami\n        description: Get current user\n        call: rabbitmq.whoami\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /definitions\n      name: getdefinitions\n      operations:\n      - method: GET\n        name: getdefinitions\n        description: Export definitions\n        call: rabbitmq.getdefinitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /definitions\n      name: postdefinitions\n      operations:\n      - method: POST\n        name: postdefinitions\n        description: Import definitions\n        call: rabbitmq.postdefinitions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: rabbitmq-mcp\n    transport: http\n    description: MCP adapter for RabbitMQ Management HTTP API for\
  \ AI agent use.\n    tools:\n    - name: getoverview\n      description: Get cluster overview\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: rabbitmq.getoverview\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclustername\n      description: Get cluster name\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: rabbitmq.getclustername\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setclustername\n      description: Set cluster name\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: rabbitmq.setclustername\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnodes\n      description: List nodes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: rabbitmq.listnodes\n\n# ---\
  \ truncated at 32 KB (49 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/rabbitmq/refs/heads/main/capabilities/rabbitmq-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rabbitmq/refs/heads/main/capabilities/rabbitmq-capability.yaml
tags:
- Rabbitmq
- API
tools:
- description: Get cluster overview
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoverview
- description: Get cluster name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclustername
- description: Set cluster name
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setclustername
- description: List nodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnodes
- description: Get node details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnode
- description: List connections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconnections
- description: Get connection
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconnection
- description: Close connection
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteconnection
- description: List channels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchannels
- description: List virtual hosts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvhosts
- description: Get virtual host
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvhost
- description: Create virtual host
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createvhost
- description: Delete virtual host
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletevhost
- description: List all exchanges
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listexchanges
- description: List exchanges in a virtual host
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listexchangesinvhost
- description: Get exchange
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexchange
- description: Create exchange
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createexchange
- description: Delete exchange
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteexchange
- description: Publish message to exchange
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publishmessage
- description: List all queues
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listqueues
- description: List queues in virtual host
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listqueuesinvhost
- description: Get queue
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getqueue
- description: Create queue
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createqueue
- description: Delete queue
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletequeue
- description: Get messages from queue
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getmessages
- description: Purge queue
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: purgequeue
- description: List all bindings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbindings
- description: List bindings between exchange and queue
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbindingsbetween
- description: Create binding
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbinding
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Get user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Create or update user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createuser
- description: Delete user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: Get user permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserpermissions
- description: Set user permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setuserpermissions
- description: Delete user permissions
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuserpermissions
- description: List policies in vhost
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpolicies
- description: Get policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpolicy
- description: Create or update policy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createpolicy
- description: Delete policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepolicy
- description: Health check - alarms
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: healthcheckalarms
- description: Health check - local alarms
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: healthchecklocalalarms
- description: Get current user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: whoami
- description: Export definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdefinitions
- description: Import definitions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postdefinitions
---
