---
categories: []
consumed_apis: []
description: 'The Knative Eventing API extends Kubernetes with custom resources for building event-driven architectures. It provides two main patterns: Broker and Trigger for cloud-native event routing with filtering, and Channel and Subscription for pub/sub messaging. Event sources such as ApiServerSource, PingSource, and SinkBinding connect external event producers to the eventing mesh. All events conform to the CloudEvents specification. Resources are served through the Kubernetes API server under the eventing.knative.dev and messaging.knative.dev API groups.'
layout: capability
name: Knative Eventing API
operations:
- description: Knative List Brokers
  method: GET
  name: listbrokers
  path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/brokers
- description: Knative Create a Broker
  method: POST
  name: createbroker
  path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/brokers
- description: Knative Get a Broker
  method: GET
  name: getbroker
  path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/brokers/{name}
- description: Knative Delete a Broker
  method: DELETE
  name: deletebroker
  path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/brokers/{name}
- description: Knative List Triggers
  method: GET
  name: listtriggers
  path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/triggers
- description: Knative Create a Trigger
  method: POST
  name: createtrigger
  path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/triggers
- description: Knative Get a Trigger
  method: GET
  name: gettrigger
  path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/triggers/{name}
- description: Knative Delete a Trigger
  method: DELETE
  name: deletetrigger
  path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/triggers/{name}
- description: Knative List Channels
  method: GET
  name: listchannels
  path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/channels
- description: Knative Create a Channel
  method: POST
  name: createchannel
  path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/channels
- description: Knative Get a Channel
  method: GET
  name: getchannel
  path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/channels/{name}
- description: Knative Delete a Channel
  method: DELETE
  name: deletechannel
  path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/channels/{name}
- description: Knative List Subscriptions
  method: GET
  name: listsubscriptions
  path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/subscriptions
- description: Knative Create a Subscription
  method: POST
  name: createsubscription
  path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/subscriptions
- description: Knative Get a Subscription
  method: GET
  name: getsubscription
  path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/subscriptions/{name}
- description: Knative Delete a Subscription
  method: DELETE
  name: deletesubscription
  path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/subscriptions/{name}
- description: Knative List ApiServerSources
  method: GET
  name: listapiserversources
  path: /apis/sources.knative.dev/v1/namespaces/{namespace}/apiserversources
- description: Knative Create an ApiServerSource
  method: POST
  name: createapiserversource
  path: /apis/sources.knative.dev/v1/namespaces/{namespace}/apiserversources
- description: Knative List PingSources
  method: GET
  name: listpingsources
  path: /apis/sources.knative.dev/v1/namespaces/{namespace}/pingsources
- description: Knative Create a PingSource
  method: POST
  name: createpingsource
  path: /apis/sources.knative.dev/v1/namespaces/{namespace}/pingsources
- description: Knative List SinkBindings
  method: GET
  name: listsinkbindings
  path: /apis/sources.knative.dev/v1/namespaces/{namespace}/sinkbindings
- description: Knative Create a SinkBinding
  method: POST
  name: createsinkbinding
  path: /apis/sources.knative.dev/v1/namespaces/{namespace}/sinkbindings
- description: Knative List EventTypes
  method: GET
  name: listeventtypes
  path: /apis/eventing.knative.dev/v1beta2/namespaces/{namespace}/eventtypes
- description: Knative Create an EventType
  method: POST
  name: createeventtype
  path: /apis/eventing.knative.dev/v1beta2/namespaces/{namespace}/eventtypes
personas: []
provider_name: Knative
provider_slug: knative
search_terms:
- listapiserversources
- listbrokers
- knative get a trigger
- knative delete a channel
- listtriggers
- event-driven
- getbroker
- createeventtype
- createpingsource
- api
- auto-scaling
- createsubscription
- listsubscriptions
- cloud native
- knative get a channel
- knative create a broker
- createbroker
- deletetrigger
- knative delete a trigger
- knative create a sinkbinding
- createapiserversource
- knative
- graduated
- knative delete a subscription
- knative create a trigger
- knative create a channel
- getsubscription
- serverless
- deletesubscription
- kubernetes
- knative list subscriptions
- listpingsources
- knative list pingsources
- gettrigger
- knative list sinkbindings
- getchannel
- knative create an apiserversource
- knative delete a broker
- knative list apiserversources
- knative create a pingsource
- listsinkbindings
- knative list eventtypes
- knative create an eventtype
- createtrigger
- knative list triggers
- knative get a subscription
- knative list brokers
- listeventtypes
- knative get a broker
- deletebroker
- knative create a subscription
- knative list channels
- createchannel
- createsinkbinding
- deletechannel
- listchannels
slug: knative-capability
source_filename: knative-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Knative Eventing API\n  description: 'The Knative Eventing API extends Kubernetes with custom resources for building event-driven architectures.\n    It provides two main patterns: Broker and Trigger for cloud-native event routing with filtering, and Channel and Subscription\n    for pub/sub messaging. Event sources such as ApiServerSource, PingSource, and SinkBinding connect external event producers\n    to the eventing mesh. All events conform to the CloudEvents specification. Resources are served through the Kubernetes\n    API server under the eventing.knative.dev and messaging.knative.dev API groups.'\n  tags:\n  - Knative\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: knative\n    baseUri: https://kubernetes.default.svc\n    description: Knative Eventing API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{KNATIVE_TOKEN}}'\n    resources:\n\
  \    - name: apis-eventing-knative-dev-v1-namespaces-namespac\n      path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/brokers\n      operations:\n      - name: listbrokers\n        method: GET\n        description: Knative List Brokers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbroker\n        method: POST\n        description: Knative Create a Broker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-eventing-knative-dev-v1-namespaces-namespac\n      path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/brokers/{name}\n      operations:\n      - name: getbroker\n        method: GET\n        description: Knative Get a Broker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebroker\n\
  \        method: DELETE\n        description: Knative Delete a Broker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-eventing-knative-dev-v1-namespaces-namespac\n      path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/triggers\n      operations:\n      - name: listtriggers\n        method: GET\n        description: Knative List Triggers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtrigger\n        method: POST\n        description: Knative Create a Trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-eventing-knative-dev-v1-namespaces-namespac\n      path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/triggers/{name}\n      operations:\n      - name: gettrigger\n        method:\
  \ GET\n        description: Knative Get a Trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetrigger\n        method: DELETE\n        description: Knative Delete a Trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-messaging-knative-dev-v1-namespaces-namespa\n      path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/channels\n      operations:\n      - name: listchannels\n        method: GET\n        description: Knative List Channels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createchannel\n        method: POST\n        description: Knative Create a Channel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: apis-messaging-knative-dev-v1-namespaces-namespa\n      path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/channels/{name}\n      operations:\n      - name: getchannel\n        method: GET\n        description: Knative Get a Channel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletechannel\n        method: DELETE\n        description: Knative Delete a Channel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-messaging-knative-dev-v1-namespaces-namespa\n      path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/subscriptions\n      operations:\n      - name: listsubscriptions\n        method: GET\n        description: Knative List Subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: createsubscription\n        method: POST\n        description: Knative Create a Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-messaging-knative-dev-v1-namespaces-namespa\n      path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/subscriptions/{name}\n      operations:\n      - name: getsubscription\n        method: GET\n        description: Knative Get a Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesubscription\n        method: DELETE\n        description: Knative Delete a Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-sources-knative-dev-v1-namespaces-namespace\n      path: /apis/sources.knative.dev/v1/namespaces/{namespace}/apiserversources\n\
  \      operations:\n      - name: listapiserversources\n        method: GET\n        description: Knative List ApiServerSources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapiserversource\n        method: POST\n        description: Knative Create an ApiServerSource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-sources-knative-dev-v1-namespaces-namespace\n      path: /apis/sources.knative.dev/v1/namespaces/{namespace}/pingsources\n      operations:\n      - name: listpingsources\n        method: GET\n        description: Knative List PingSources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpingsource\n        method: POST\n        description: Knative Create a PingSource\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-sources-knative-dev-v1-namespaces-namespace\n      path: /apis/sources.knative.dev/v1/namespaces/{namespace}/sinkbindings\n      operations:\n      - name: listsinkbindings\n        method: GET\n        description: Knative List SinkBindings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsinkbinding\n        method: POST\n        description: Knative Create a SinkBinding\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-eventing-knative-dev-v1beta2-namespaces-nam\n      path: /apis/eventing.knative.dev/v1beta2/namespaces/{namespace}/eventtypes\n      operations:\n      - name: listeventtypes\n        method: GET\n        description: Knative List EventTypes\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createeventtype\n        method: POST\n        description: Knative Create an EventType\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: knative-rest\n    description: REST adapter for Knative Eventing API.\n    resources:\n    - path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/brokers\n      name: listbrokers\n      operations:\n      - method: GET\n        name: listbrokers\n        description: Knative List Brokers\n        call: knative.listbrokers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/brokers\n      name: createbroker\n      operations:\n      - method: POST\n        name: createbroker\n        description: Knative Create\
  \ a Broker\n        call: knative.createbroker\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/brokers/{name}\n      name: getbroker\n      operations:\n      - method: GET\n        name: getbroker\n        description: Knative Get a Broker\n        call: knative.getbroker\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/brokers/{name}\n      name: deletebroker\n      operations:\n      - method: DELETE\n        name: deletebroker\n        description: Knative Delete a Broker\n        call: knative.deletebroker\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/triggers\n      name: listtriggers\n      operations:\n      - method: GET\n        name: listtriggers\n        description: Knative List Triggers\n        call:\
  \ knative.listtriggers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/triggers\n      name: createtrigger\n      operations:\n      - method: POST\n        name: createtrigger\n        description: Knative Create a Trigger\n        call: knative.createtrigger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/triggers/{name}\n      name: gettrigger\n      operations:\n      - method: GET\n        name: gettrigger\n        description: Knative Get a Trigger\n        call: knative.gettrigger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/eventing.knative.dev/v1/namespaces/{namespace}/triggers/{name}\n      name: deletetrigger\n      operations:\n      - method: DELETE\n        name: deletetrigger\n        description: Knative Delete a Trigger\n        call: knative.deletetrigger\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/channels\n      name: listchannels\n      operations:\n      - method: GET\n        name: listchannels\n        description: Knative List Channels\n        call: knative.listchannels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/channels\n      name: createchannel\n      operations:\n      - method: POST\n        name: createchannel\n        description: Knative Create a Channel\n        call: knative.createchannel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/channels/{name}\n      name: getchannel\n      operations:\n      - method: GET\n        name: getchannel\n        description: Knative Get a Channel\n        call: knative.getchannel\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/channels/{name}\n      name: deletechannel\n      operations:\n      - method: DELETE\n        name: deletechannel\n        description: Knative Delete a Channel\n        call: knative.deletechannel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/subscriptions\n      name: listsubscriptions\n      operations:\n      - method: GET\n        name: listsubscriptions\n        description: Knative List Subscriptions\n        call: knative.listsubscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/subscriptions\n      name: createsubscription\n      operations:\n      - method: POST\n        name: createsubscription\n        description: Knative Create a Subscription\n        call: knative.createsubscription\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/subscriptions/{name}\n      name: getsubscription\n      operations:\n      - method: GET\n        name: getsubscription\n        description: Knative Get a Subscription\n        call: knative.getsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/messaging.knative.dev/v1/namespaces/{namespace}/subscriptions/{name}\n      name: deletesubscription\n      operations:\n      - method: DELETE\n        name: deletesubscription\n        description: Knative Delete a Subscription\n        call: knative.deletesubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/sources.knative.dev/v1/namespaces/{namespace}/apiserversources\n      name: listapiserversources\n      operations:\n      - method: GET\n        name: listapiserversources\n        description:\
  \ Knative List ApiServerSources\n        call: knative.listapiserversources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/sources.knative.dev/v1/namespaces/{namespace}/apiserversources\n      name: createapiserversource\n      operations:\n      - method: POST\n        name: createapiserversource\n        description: Knative Create an ApiServerSource\n        call: knative.createapiserversource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/sources.knative.dev/v1/namespaces/{namespace}/pingsources\n      name: listpingsources\n      operations:\n      - method: GET\n        name: listpingsources\n        description: Knative List PingSources\n        call: knative.listpingsources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/sources.knative.dev/v1/namespaces/{namespace}/pingsources\n      name: createpingsource\n      operations:\n      - method:\
  \ POST\n        name: createpingsource\n        description: Knative Create a PingSource\n        call: knative.createpingsource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/sources.knative.dev/v1/namespaces/{namespace}/sinkbindings\n      name: listsinkbindings\n      operations:\n      - method: GET\n        name: listsinkbindings\n        description: Knative List SinkBindings\n        call: knative.listsinkbindings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/sources.knative.dev/v1/namespaces/{namespace}/sinkbindings\n      name: createsinkbinding\n      operations:\n      - method: POST\n        name: createsinkbinding\n        description: Knative Create a SinkBinding\n        call: knative.createsinkbinding\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/eventing.knative.dev/v1beta2/namespaces/{namespace}/eventtypes\n      name: listeventtypes\n\
  \      operations:\n      - method: GET\n        name: listeventtypes\n        description: Knative List EventTypes\n        call: knative.listeventtypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/eventing.knative.dev/v1beta2/namespaces/{namespace}/eventtypes\n      name: createeventtype\n      operations:\n      - method: POST\n        name: createeventtype\n        description: Knative Create an EventType\n        call: knative.createeventtype\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: knative-mcp\n    transport: http\n    description: MCP adapter for Knative Eventing API for AI agent use.\n    tools:\n    - name: listbrokers\n      description: Knative List Brokers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knative.listbrokers\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: createbroker\n      description: Knative Create a Broker\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: knative.createbroker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbroker\n      description: Knative Get a Broker\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knative.getbroker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletebroker\n      description: Knative Delete a Broker\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: knative.deletebroker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtriggers\n      description: Knative List Triggers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knative.listtriggers\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createtrigger\n      description: Knative Create a Trigger\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: knative.createtrigger\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettrigger\n      description: Knative Get a Trigger\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knative.gettrigger\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetrigger\n      description: Knative Delete a Trigger\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: knative.deletetrigger\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listchannels\n      description: Knative List Channels\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n \
  \     call: knative.listchannels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createchannel\n      description: Knative Create a Channel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: knative.createchannel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getchannel\n      description: Knative Get a Channel\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knative.getchannel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletechannel\n      description: Knative Delete a Channel\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: knative.deletechannel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsubscriptions\n      description: Knative List Subscriptions\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: knative.listsubscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsubscription\n      description: Knative Create a Subscription\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: knative.createsubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsubscription\n      description: Knative Get a Subscription\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knative.getsubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesubscription\n      description: Knative Delete a Subscription\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: knative.deletesubscription\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: listapiserversources\n      description: Knative List ApiServerSources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knative.listapiserversources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapiserversource\n      description: Knative Create an ApiServerSource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: knative.createapiserversource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpingsources\n      description: Knative List PingSources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knative.listpingsources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpingsource\n      description: Knative Create a PingSource\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: knative.createpingsource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsinkbindings\n      description: Knative List SinkBindings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knative.listsinkbindings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsinkbinding\n      description: Knative Create a SinkBinding\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: knative.createsinkbinding\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listeventtypes\n      description: Knative List EventTypes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knative.listeventtypes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createeventtype\n      description:\
  \ Knative Create an EventType\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: knative.createeventtype\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    KNATIVE_TOKEN: KNATIVE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/knative/refs/heads/main/capabilities/knative-capability.yaml
tags:
- Knative
- API
tools:
- description: Knative List Brokers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbrokers
- description: Knative Create a Broker
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbroker
- description: Knative Get a Broker
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbroker
- description: Knative Delete a Broker
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebroker
- description: Knative List Triggers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtriggers
- description: Knative Create a Trigger
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtrigger
- description: Knative Get a Trigger
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettrigger
- description: Knative Delete a Trigger
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetrigger
- description: Knative List Channels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchannels
- description: Knative Create a Channel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchannel
- description: Knative Get a Channel
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchannel
- description: Knative Delete a Channel
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletechannel
- description: Knative List Subscriptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsubscriptions
- description: Knative Create a Subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsubscription
- description: Knative Get a Subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubscription
- description: Knative Delete a Subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesubscription
- description: Knative List ApiServerSources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapiserversources
- description: Knative Create an ApiServerSource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapiserversource
- description: Knative List PingSources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpingsources
- description: Knative Create a PingSource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpingsource
- description: Knative List SinkBindings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsinkbindings
- description: Knative Create a SinkBinding
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsinkbinding
- description: Knative List EventTypes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listeventtypes
- description: Knative Create an EventType
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createeventtype
---
