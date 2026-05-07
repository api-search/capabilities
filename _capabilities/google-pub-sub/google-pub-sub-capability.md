---
categories: []
consumed_apis: []
description: Provides reliable, many-to-many, asynchronous messaging between applications. The Pub/Sub API allows you to create and manage topics and subscriptions, publish messages, and pull or push messages to subscribers.
layout: capability
name: Google Pub/Sub Google Cloud Pub/Sub API
operations:
- description: Google Pub/Sub List topics
  method: GET
  name: listtopics
  path: /v1/projects/{project}/topics
- description: Google Pub/Sub Get a topic
  method: GET
  name: gettopic
  path: /v1/projects/{project}/topics/{topic}
- description: Google Pub/Sub Create a topic
  method: PUT
  name: createtopic
  path: /v1/projects/{project}/topics/{topic}
- description: Google Pub/Sub Delete a topic
  method: DELETE
  name: deletetopic
  path: /v1/projects/{project}/topics/{topic}
- description: Google Pub/Sub Update a topic
  method: PATCH
  name: updatetopic
  path: /v1/{topic}
- description: Google Pub/Sub Publish messages
  method: POST
  name: publish
  path: /v1/{topic}:publish
- description: Google Pub/Sub List subscriptions
  method: GET
  name: listsubscriptions
  path: /v1/projects/{project}/subscriptions
- description: Google Pub/Sub Get a subscription
  method: GET
  name: getsubscription
  path: /v1/projects/{project}/subscriptions/{subscription}
- description: Google Pub/Sub Create a subscription
  method: PUT
  name: createsubscription
  path: /v1/projects/{project}/subscriptions/{subscription}
- description: Google Pub/Sub Delete a subscription
  method: DELETE
  name: deletesubscription
  path: /v1/projects/{project}/subscriptions/{subscription}
- description: Google Pub/Sub Pull messages
  method: POST
  name: pull
  path: /v1/{subscription}:pull
- description: Google Pub/Sub Acknowledge messages
  method: POST
  name: acknowledge
  path: /v1/{subscription}:acknowledge
- description: Google Pub/Sub Modify acknowledgement deadline
  method: POST
  name: modifyackdeadline
  path: /v1/{subscription}:modifyAckDeadline
- description: Google Pub/Sub List snapshots
  method: GET
  name: listsnapshots
  path: /v1/projects/{project}/snapshots
- description: Google Pub/Sub Get a snapshot
  method: GET
  name: getsnapshot
  path: /v1/projects/{project}/snapshots/{snapshot}
- description: Google Pub/Sub Create a snapshot
  method: PUT
  name: createsnapshot
  path: /v1/projects/{project}/snapshots/{snapshot}
- description: Google Pub/Sub Delete a snapshot
  method: DELETE
  name: deletesnapshot
  path: /v1/projects/{project}/snapshots/{snapshot}
- description: Google Pub/Sub List schemas
  method: GET
  name: listschemas
  path: /v1/projects/{project}/schemas
- description: Google Pub/Sub Create a schema
  method: POST
  name: createschema
  path: /v1/projects/{project}/schemas
personas: []
provider_name: Google Pub/Sub
provider_slug: google-pub-sub
search_terms:
- deletetopic
- event-driven
- gettopic
- createtopic
- google pub/sub list subscriptions
- streaming
- google pub/sub create a snapshot
- updatetopic
- listsnapshots
- api
- createsubscription
- listsubscriptions
- google pub/sub get a subscription
- getsnapshot
- google pub/sub create a schema
- google pub/sub list topics
- google
- google pub/sub update a topic
- getsubscription
- deletesubscription
- createschema
- deletesnapshot
- listschemas
- google pub/sub delete a subscription
- pull
- google pub/sub list schemas
- google pub/sub delete a topic
- google pub/sub list snapshots
- pub/sub
- cloud
- google pub/sub get a topic
- google pub/sub pull messages
- google pub/sub publish messages
- pub
- google pub/sub create a topic
- listtopics
- acknowledge
- modifyackdeadline
- google cloud
- messaging
- google pub/sub create a subscription
- publish
- createsnapshot
- google pub/sub acknowledge messages
- google pub/sub modify acknowledgement deadline
- google pub/sub delete a snapshot
- google pub/sub get a snapshot
- sub
slug: google-pub-sub-capability
source_filename: google-pub-sub-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Pub/Sub Google Cloud Pub/Sub API\n  description: Provides reliable, many-to-many, asynchronous messaging between applications. The Pub/Sub API allows you to\n    create and manage topics and subscriptions, publish messages, and pull or push messages to subscribers.\n  tags:\n  - Google\n  - Pub\n  - Sub\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-pub-sub\n    baseUri: https://pubsub.googleapis.com\n    description: Google Pub/Sub Google Cloud Pub/Sub API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_PUB_SUB_TOKEN}}'\n    resources:\n    - name: v1-projects-project-topics\n      path: /v1/projects/{project}/topics\n      operations:\n      - name: listtopics\n        method: GET\n        description: Google Pub/Sub List topics\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n\
  \          required: true\n          description: The project ID (e.g., projects/my-project).\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of topics to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: Token for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-topics-topic\n      path: /v1/projects/{project}/topics/{topic}\n      operations:\n      - name: gettopic\n        method: GET\n        description: Google Pub/Sub Get a topic\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: topic\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: createtopic\n        method: PUT\n        description: Google Pub/Sub Create a topic\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: topic\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetopic\n        method: DELETE\n        description: Google Pub/Sub Delete a topic\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: topic\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-topic\n      path: /v1/{topic}\n      operations:\n      - name: updatetopic\n\
  \        method: PATCH\n        description: Google Pub/Sub Update a topic\n        inputParameters:\n        - name: topic\n          in: path\n          type: string\n          required: true\n          description: The name of the topic (e.g., projects/my-project/topics/my-topic).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-topic-publish\n      path: /v1/{topic}:publish\n      operations:\n      - name: publish\n        method: POST\n        description: Google Pub/Sub Publish messages\n        inputParameters:\n        - name: topic\n          in: path\n          type: string\n          required: true\n          description: The topic name (e.g., projects/my-project/topics/my-topic).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-subscriptions\n      path: /v1/projects/{project}/subscriptions\n\
  \      operations:\n      - name: listsubscriptions\n        method: GET\n        description: Google Pub/Sub List subscriptions\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-subscriptions-subscription\n      path: /v1/projects/{project}/subscriptions/{subscription}\n      operations:\n      - name: getsubscription\n        method: GET\n        description: Google Pub/Sub Get a subscription\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: subscription\n          in: path\n          type: string\n          required: true\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsubscription\n        method: PUT\n        description: Google Pub/Sub Create a subscription\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: subscription\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesubscription\n        method: DELETE\n        description: Google Pub/Sub Delete a subscription\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: subscription\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: v1-subscription-pull\n      path: /v1/{subscription}:pull\n      operations:\n      - name: pull\n        method: POST\n        description: Google Pub/Sub Pull messages\n        inputParameters:\n        - name: subscription\n          in: path\n          type: string\n          required: true\n          description: The subscription name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-subscription-acknowledge\n      path: /v1/{subscription}:acknowledge\n      operations:\n      - name: acknowledge\n        method: POST\n        description: Google Pub/Sub Acknowledge messages\n        inputParameters:\n        - name: subscription\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ v1-subscription-modifyackdeadline\n      path: /v1/{subscription}:modifyAckDeadline\n      operations:\n      - name: modifyackdeadline\n        method: POST\n        description: Google Pub/Sub Modify acknowledgement deadline\n        inputParameters:\n        - name: subscription\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-snapshots\n      path: /v1/projects/{project}/snapshots\n      operations:\n      - name: listsnapshots\n        method: GET\n        description: Google Pub/Sub List snapshots\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-snapshots-snapshot\n      path: /v1/projects/{project}/snapshots/{snapshot}\n      operations:\n      - name: getsnapshot\n        method: GET\n        description: Google Pub/Sub Get a snapshot\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: snapshot\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsnapshot\n        method: PUT\n        description: Google Pub/Sub Create a snapshot\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: snapshot\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesnapshot\n        method: DELETE\n        description: Google Pub/Sub Delete a snapshot\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: snapshot\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-schemas\n      path: /v1/projects/{project}/schemas\n      operations:\n      - name: listschemas\n        method: GET\n        description: Google Pub/Sub List schemas\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n         \
  \ type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createschema\n        method: POST\n        description: Google Pub/Sub Create a schema\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: schemaId\n          in: query\n          type: string\n          description: The ID to use for the schema.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-pub-sub-rest\n    description: REST adapter for Google Pub/Sub Google Cloud Pub/Sub API.\n    resources:\n    - path: /v1/projects/{project}/topics\n      name: listtopics\n      operations:\n      - method: GET\n        name: listtopics\n        description: Google Pub/Sub List topics\n        call: google-pub-sub.listtopics\n\
  \        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/topics/{topic}\n      name: gettopic\n      operations:\n      - method: GET\n        name: gettopic\n        description: Google Pub/Sub Get a topic\n        call: google-pub-sub.gettopic\n        with:\n          project: rest.project\n          topic: rest.topic\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/topics/{topic}\n      name: createtopic\n      operations:\n      - method: PUT\n        name: createtopic\n        description: Google Pub/Sub Create a topic\n        call: google-pub-sub.createtopic\n        with:\n          project: rest.project\n          topic: rest.topic\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/topics/{topic}\n      name: deletetopic\n      operations:\n      - method: DELETE\n\
  \        name: deletetopic\n        description: Google Pub/Sub Delete a topic\n        call: google-pub-sub.deletetopic\n        with:\n          project: rest.project\n          topic: rest.topic\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{topic}\n      name: updatetopic\n      operations:\n      - method: PATCH\n        name: updatetopic\n        description: Google Pub/Sub Update a topic\n        call: google-pub-sub.updatetopic\n        with:\n          topic: rest.topic\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{topic}:publish\n      name: publish\n      operations:\n      - method: POST\n        name: publish\n        description: Google Pub/Sub Publish messages\n        call: google-pub-sub.publish\n        with:\n          topic: rest.topic\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/subscriptions\n      name: listsubscriptions\n\
  \      operations:\n      - method: GET\n        name: listsubscriptions\n        description: Google Pub/Sub List subscriptions\n        call: google-pub-sub.listsubscriptions\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/subscriptions/{subscription}\n      name: getsubscription\n      operations:\n      - method: GET\n        name: getsubscription\n        description: Google Pub/Sub Get a subscription\n        call: google-pub-sub.getsubscription\n        with:\n          project: rest.project\n          subscription: rest.subscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/subscriptions/{subscription}\n      name: createsubscription\n      operations:\n      - method: PUT\n        name: createsubscription\n        description: Google Pub/Sub Create a subscription\n        call: google-pub-sub.createsubscription\n\
  \        with:\n          project: rest.project\n          subscription: rest.subscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/subscriptions/{subscription}\n      name: deletesubscription\n      operations:\n      - method: DELETE\n        name: deletesubscription\n        description: Google Pub/Sub Delete a subscription\n        call: google-pub-sub.deletesubscription\n        with:\n          project: rest.project\n          subscription: rest.subscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{subscription}:pull\n      name: pull\n      operations:\n      - method: POST\n        name: pull\n        description: Google Pub/Sub Pull messages\n        call: google-pub-sub.pull\n        with:\n          subscription: rest.subscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{subscription}:acknowledge\n      name:\
  \ acknowledge\n      operations:\n      - method: POST\n        name: acknowledge\n        description: Google Pub/Sub Acknowledge messages\n        call: google-pub-sub.acknowledge\n        with:\n          subscription: rest.subscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/{subscription}:modifyAckDeadline\n      name: modifyackdeadline\n      operations:\n      - method: POST\n        name: modifyackdeadline\n        description: Google Pub/Sub Modify acknowledgement deadline\n        call: google-pub-sub.modifyackdeadline\n        with:\n          subscription: rest.subscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/snapshots\n      name: listsnapshots\n      operations:\n      - method: GET\n        name: listsnapshots\n        description: Google Pub/Sub List snapshots\n        call: google-pub-sub.listsnapshots\n        with:\n          project: rest.project\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/snapshots/{snapshot}\n      name: getsnapshot\n      operations:\n      - method: GET\n        name: getsnapshot\n        description: Google Pub/Sub Get a snapshot\n        call: google-pub-sub.getsnapshot\n        with:\n          project: rest.project\n          snapshot: rest.snapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/snapshots/{snapshot}\n      name: createsnapshot\n      operations:\n      - method: PUT\n        name: createsnapshot\n        description: Google Pub/Sub Create a snapshot\n        call: google-pub-sub.createsnapshot\n        with:\n          project: rest.project\n          snapshot: rest.snapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/snapshots/{snapshot}\n      name: deletesnapshot\n      operations:\n      - method:\
  \ DELETE\n        name: deletesnapshot\n        description: Google Pub/Sub Delete a snapshot\n        call: google-pub-sub.deletesnapshot\n        with:\n          project: rest.project\n          snapshot: rest.snapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/schemas\n      name: listschemas\n      operations:\n      - method: GET\n        name: listschemas\n        description: Google Pub/Sub List schemas\n        call: google-pub-sub.listschemas\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/schemas\n      name: createschema\n      operations:\n      - method: POST\n        name: createschema\n        description: Google Pub/Sub Create a schema\n        call: google-pub-sub.createschema\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n  - type: mcp\n    port: 9090\n    namespace: google-pub-sub-mcp\n    transport: http\n    description: MCP adapter for Google Pub/Sub Google Cloud Pub/Sub API for AI agent use.\n    tools:\n    - name: listtopics\n      description: Google Pub/Sub List topics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-pub-sub.listtopics\n      with:\n        project: tools.project\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: project\n        type: string\n        description: The project ID (e.g., projects/my-project).\n        required: true\n      - name: pageSize\n        type: integer\n        description: Maximum number of topics to return.\n      - name: pageToken\n        type: string\n        description: Token for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettopic\n      description: Google Pub/Sub Get a topic\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-pub-sub.gettopic\n      with:\n        project: tools.project\n        topic: tools.topic\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: topic\n        type: string\n        description: topic\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtopic\n      description: Google Pub/Sub Create a topic\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-pub-sub.createtopic\n      with:\n        project: tools.project\n        topic: tools.topic\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: topic\n        type: string\n        description: topic\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: deletetopic\n      description: Google Pub/Sub Delete a topic\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-pub-sub.deletetopic\n      with:\n        project: tools.project\n        topic: tools.topic\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: topic\n        type: string\n        description: topic\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatetopic\n      description: Google Pub/Sub Update a topic\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-pub-sub.updatetopic\n      with:\n        topic: tools.topic\n      inputParameters:\n      - name: topic\n        type: string\n        description: The name of the topic (e.g., projects/my-project/topics/my-topic).\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish\n      description: Google Pub/Sub Publish messages\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-pub-sub.publish\n      with:\n        topic: tools.topic\n      inputParameters:\n      - name: topic\n        type: string\n        description: The topic name (e.g., projects/my-project/topics/my-topic).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsubscriptions\n      description: Google Pub/Sub List subscriptions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-pub-sub.listsubscriptions\n      with:\n        project: tools.project\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: project\n        type: string\n        description:\
  \ project\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsubscription\n      description: Google Pub/Sub Get a subscription\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-pub-sub.getsubscription\n      with:\n        project: tools.project\n        subscription: tools.subscription\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: subscription\n        type: string\n        description: subscription\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsubscription\n      description: Google Pub/Sub Create a subscription\n      hints:\n        readOnly: false\n     \
  \   destructive: false\n        idempotent: true\n      call: google-pub-sub.createsubscription\n      with:\n        project: tools.project\n        subscription: tools.subscription\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: subscription\n        type: string\n        description: subscription\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesubscription\n      description: Google Pub/Sub Delete a subscription\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-pub-sub.deletesubscription\n      with:\n        project: tools.project\n        subscription: tools.subscription\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: subscription\n        type: string\n        description: subscription\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pull\n      description: Google Pub/Sub Pull messages\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-pub-sub.pull\n      with:\n        subscription: tools.subscription\n      inputParameters:\n      - name: subscription\n        type: string\n        description: The subscription name.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: acknowledge\n      description: Google Pub/Sub Acknowledge messages\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-pub-sub.acknowledge\n      with:\n        subscription: tools.subscription\n      inputParameters:\n      - name: subscription\n        type: string\n        description: subscription\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: modifyackdeadline\n      description: Google Pub/Sub Modify acknowledgement deadline\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-pub-sub.modifyackdeadline\n      with:\n        subscription: tools.subscription\n      inputParameters:\n      - name: subscription\n        type: string\n        description: subscription\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsnapshots\n      description: Google Pub/Sub List snapshots\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-pub-sub.listsnapshots\n      with:\n        project: tools.project\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: pageSize\n        type:\
  \ integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsnapshot\n      description: Google Pub/Sub Get a snapshot\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-pub-sub.getsnapshot\n      with:\n        project: tools.project\n        snapshot: tools.snapshot\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: snapshot\n        type: string\n        description: snapshot\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsnapshot\n      description: Google Pub/Sub Create a snapshot\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-pub-sub.createsnapshot\n      with:\n  \
  \      project: tools.project\n        snapshot: tools.snapshot\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: snapshot\n        type: string\n        description: snapshot\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesnapshot\n      description: Google Pub/Sub Delete a snapshot\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-pub-sub.deletesnapshot\n      with:\n        project: tools.project\n        snapshot: tools.snapshot\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: snapshot\n        type: string\n        description: snapshot\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listschemas\n      description: Google Pub/Sub\
  \ List schemas\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-pub-sub.listschemas\n      with:\n        project: tools.project\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createschema\n      description: Google Pub/Sub Create a schema\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-pub-sub.createschema\n      with:\n        project: tools.project\n        schemaId: tools.schemaId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n\
  \        required: true\n      - name: schemaId\n        type: string\n        description: The ID to use for the schema.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_PUB_SUB_TOKEN: GOOGLE_PUB_SUB_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-pub-sub/refs/heads/main/capabilities/google-pub-sub-capability.yaml
tags:
- Google
- Pub
- Sub
- API
tools:
- description: Google Pub/Sub List topics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtopics
- description: Google Pub/Sub Get a topic
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettopic
- description: Google Pub/Sub Create a topic
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createtopic
- description: Google Pub/Sub Delete a topic
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetopic
- description: Google Pub/Sub Update a topic
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatetopic
- description: Google Pub/Sub Publish messages
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publish
- description: Google Pub/Sub List subscriptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsubscriptions
- description: Google Pub/Sub Get a subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubscription
- description: Google Pub/Sub Create a subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createsubscription
- description: Google Pub/Sub Delete a subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesubscription
- description: Google Pub/Sub Pull messages
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pull
- description: Google Pub/Sub Acknowledge messages
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: acknowledge
- description: Google Pub/Sub Modify acknowledgement deadline
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: modifyackdeadline
- description: Google Pub/Sub List snapshots
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsnapshots
- description: Google Pub/Sub Get a snapshot
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsnapshot
- description: Google Pub/Sub Create a snapshot
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createsnapshot
- description: Google Pub/Sub Delete a snapshot
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesnapshot
- description: Google Pub/Sub List schemas
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschemas
- description: Google Pub/Sub Create a schema
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createschema
---
