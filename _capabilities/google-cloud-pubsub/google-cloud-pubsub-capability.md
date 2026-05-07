---
categories: []
consumed_apis: []
description: The Cloud Pub/Sub API provides reliable, many-to-many, asynchronous messaging between applications. Publishers send messages to topics, and subscribers receive messages via subscriptions. It supports both push and pull delivery modes.
layout: capability
name: Google Cloud Pub/Sub API
operations:
- description: Google Cloud Pub/Sub List topics
  method: GET
  name: listtopics
  path: /projects/{projectId}/topics
- description: Google Cloud Pub/Sub Get a topic
  method: GET
  name: gettopic
  path: /projects/{projectId}/topics/{topicId}
- description: Google Cloud Pub/Sub Create a topic
  method: PUT
  name: createtopic
  path: /projects/{projectId}/topics/{topicId}
- description: Google Cloud Pub/Sub Delete a topic
  method: DELETE
  name: deletetopic
  path: /projects/{projectId}/topics/{topicId}
- description: Google Cloud Pub/Sub Publish messages
  method: POST
  name: publishmessages
  path: /projects/{projectId}/topics/{topicId}:publish
- description: Google Cloud Pub/Sub List subscriptions
  method: GET
  name: listsubscriptions
  path: /projects/{projectId}/subscriptions
- description: Google Cloud Pub/Sub Get a subscription
  method: GET
  name: getsubscription
  path: /projects/{projectId}/subscriptions/{subscriptionId}
- description: Google Cloud Pub/Sub Create a subscription
  method: PUT
  name: createsubscription
  path: /projects/{projectId}/subscriptions/{subscriptionId}
- description: Google Cloud Pub/Sub Delete a subscription
  method: DELETE
  name: deletesubscription
  path: /projects/{projectId}/subscriptions/{subscriptionId}
- description: Google Cloud Pub/Sub Pull messages
  method: POST
  name: pullmessages
  path: /projects/{projectId}/subscriptions/{subscriptionId}:pull
- description: Google Cloud Pub/Sub Acknowledge messages
  method: POST
  name: acknowledgemessages
  path: /projects/{projectId}/subscriptions/{subscriptionId}:acknowledge
- description: Google Cloud Pub/Sub List schemas
  method: GET
  name: listschemas
  path: /projects/{projectId}/schemas
- description: Google Cloud Pub/Sub Create a schema
  method: POST
  name: createschema
  path: /projects/{projectId}/schemas
personas: []
provider_name: Google Cloud Pub/Sub
provider_slug: google-cloud-pubsub
search_terms:
- deletetopic
- google cloud pub/sub delete a subscription
- gettopic
- createtopic
- event-driven
- api
- createsubscription
- listsubscriptions
- google cloud pub/sub list schemas
- google
- pubsub
- getsubscription
- google cloud pub/sub publish messages
- deletesubscription
- acknowledgemessages
- createschema
- pullmessages
- publishmessages
- listschemas
- google cloud pub/sub get a subscription
- google cloud pub/sub delete a topic
- google cloud pub/sub create a subscription
- google cloud pub/sub create a schema
- google cloud pub/sub pull messages
- cloud
- pub/sub
- google cloud pub/sub list subscriptions
- google cloud pub/sub get a topic
- google cloud pub/sub create a topic
- google cloud pub/sub acknowledge messages
- google cloud pub/sub list topics
- listtopics
- google cloud
- messaging
slug: google-cloud-pubsub-capability
source_filename: google-cloud-pubsub-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Pub/Sub API\n  description: The Cloud Pub/Sub API provides reliable, many-to-many, asynchronous messaging between applications. Publishers\n    send messages to topics, and subscribers receive messages via subscriptions. It supports both push and pull delivery modes.\n  tags:\n  - Google\n  - Cloud\n  - Pubsub\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-pubsub\n    baseUri: https://pubsub.googleapis.com/v1\n    description: Google Cloud Pub/Sub API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_PUBSUB_TOKEN}}'\n    resources:\n    - name: projects-projectid-topics\n      path: /projects/{projectId}/topics\n      operations:\n      - name: listtopics\n        method: GET\n        description: Google Cloud Pub/Sub List topics\n        inputParameters:\n        - name: projectId\n          in: path\n      \
  \    type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-topics-topicid\n      path: /projects/{projectId}/topics/{topicId}\n      operations:\n      - name: gettopic\n        method: GET\n        description: Google Cloud Pub/Sub Get a topic\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: topicId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtopic\n        method: PUT\n        description: Google Cloud Pub/Sub Create a topic\n        inputParameters:\n\
  \        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: topicId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetopic\n        method: DELETE\n        description: Google Cloud Pub/Sub Delete a topic\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: topicId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-topics-topicid-publish\n      path: /projects/{projectId}/topics/{topicId}:publish\n      operations:\n      - name: publishmessages\n        method: POST\n        description: Google Cloud Pub/Sub\
  \ Publish messages\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: topicId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-subscriptions\n      path: /projects/{projectId}/subscriptions\n      operations:\n      - name: listsubscriptions\n        method: GET\n        description: Google Cloud Pub/Sub List subscriptions\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ projects-projectid-subscriptions-subscriptionid\n      path: /projects/{projectId}/subscriptions/{subscriptionId}\n      operations:\n      - name: getsubscription\n        method: GET\n        description: Google Cloud Pub/Sub Get a subscription\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsubscription\n        method: PUT\n        description: Google Cloud Pub/Sub Create a subscription\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deletesubscription\n        method: DELETE\n        description: Google Cloud Pub/Sub Delete a subscription\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-subscriptions-subscriptionid-\n      path: /projects/{projectId}/subscriptions/{subscriptionId}:pull\n      operations:\n      - name: pullmessages\n        method: POST\n        description: Google Cloud Pub/Sub Pull messages\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: subscriptionId\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-subscriptions-subscriptionid-\n      path: /projects/{projectId}/subscriptions/{subscriptionId}:acknowledge\n      operations:\n      - name: acknowledgemessages\n        method: POST\n        description: Google Cloud Pub/Sub Acknowledge messages\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-schemas\n      path: /projects/{projectId}/schemas\n      operations:\n      - name: listschemas\n        method: GET\n        description: Google Cloud Pub/Sub List schemas\n       \
  \ inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createschema\n        method: POST\n        description: Google Cloud Pub/Sub Create a schema\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: schemaId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-pubsub-rest\n    description: REST adapter for Google Cloud Pub/Sub API.\n    resources:\n    - path: /projects/{projectId}/topics\n\
  \      name: listtopics\n      operations:\n      - method: GET\n        name: listtopics\n        description: Google Cloud Pub/Sub List topics\n        call: google-cloud-pubsub.listtopics\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/topics/{topicId}\n      name: gettopic\n      operations:\n      - method: GET\n        name: gettopic\n        description: Google Cloud Pub/Sub Get a topic\n        call: google-cloud-pubsub.gettopic\n        with:\n          projectId: rest.projectId\n          topicId: rest.topicId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/topics/{topicId}\n      name: createtopic\n      operations:\n      - method: PUT\n        name: createtopic\n        description: Google Cloud Pub/Sub Create a topic\n        call: google-cloud-pubsub.createtopic\n        with:\n          projectId: rest.projectId\n\
  \          topicId: rest.topicId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/topics/{topicId}\n      name: deletetopic\n      operations:\n      - method: DELETE\n        name: deletetopic\n        description: Google Cloud Pub/Sub Delete a topic\n        call: google-cloud-pubsub.deletetopic\n        with:\n          projectId: rest.projectId\n          topicId: rest.topicId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/topics/{topicId}:publish\n      name: publishmessages\n      operations:\n      - method: POST\n        name: publishmessages\n        description: Google Cloud Pub/Sub Publish messages\n        call: google-cloud-pubsub.publishmessages\n        with:\n          projectId: rest.projectId\n          topicId: rest.topicId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/subscriptions\n\
  \      name: listsubscriptions\n      operations:\n      - method: GET\n        name: listsubscriptions\n        description: Google Cloud Pub/Sub List subscriptions\n        call: google-cloud-pubsub.listsubscriptions\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/subscriptions/{subscriptionId}\n      name: getsubscription\n      operations:\n      - method: GET\n        name: getsubscription\n        description: Google Cloud Pub/Sub Get a subscription\n        call: google-cloud-pubsub.getsubscription\n        with:\n          projectId: rest.projectId\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/subscriptions/{subscriptionId}\n      name: createsubscription\n      operations:\n      - method: PUT\n        name: createsubscription\n        description: Google Cloud\
  \ Pub/Sub Create a subscription\n        call: google-cloud-pubsub.createsubscription\n        with:\n          projectId: rest.projectId\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/subscriptions/{subscriptionId}\n      name: deletesubscription\n      operations:\n      - method: DELETE\n        name: deletesubscription\n        description: Google Cloud Pub/Sub Delete a subscription\n        call: google-cloud-pubsub.deletesubscription\n        with:\n          projectId: rest.projectId\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/subscriptions/{subscriptionId}:pull\n      name: pullmessages\n      operations:\n      - method: POST\n        name: pullmessages\n        description: Google Cloud Pub/Sub Pull messages\n        call: google-cloud-pubsub.pullmessages\n \
  \       with:\n          projectId: rest.projectId\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/subscriptions/{subscriptionId}:acknowledge\n      name: acknowledgemessages\n      operations:\n      - method: POST\n        name: acknowledgemessages\n        description: Google Cloud Pub/Sub Acknowledge messages\n        call: google-cloud-pubsub.acknowledgemessages\n        with:\n          projectId: rest.projectId\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/schemas\n      name: listschemas\n      operations:\n      - method: GET\n        name: listschemas\n        description: Google Cloud Pub/Sub List schemas\n        call: google-cloud-pubsub.listschemas\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n      \
  \    mapping: $.\n    - path: /projects/{projectId}/schemas\n      name: createschema\n      operations:\n      - method: POST\n        name: createschema\n        description: Google Cloud Pub/Sub Create a schema\n        call: google-cloud-pubsub.createschema\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-pubsub-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Pub/Sub API for AI agent use.\n    tools:\n    - name: listtopics\n      description: Google Cloud Pub/Sub List topics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-pubsub.listtopics\n      with:\n        projectId: tools.projectId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n\
  \        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettopic\n      description: Google Cloud Pub/Sub Get a topic\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-pubsub.gettopic\n      with:\n        projectId: tools.projectId\n        topicId: tools.topicId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: topicId\n        type: string\n        description: topicId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtopic\n      description: Google Cloud Pub/Sub Create a topic\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ true\n      call: google-cloud-pubsub.createtopic\n      with:\n        projectId: tools.projectId\n        topicId: tools.topicId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: topicId\n        type: string\n        description: topicId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetopic\n      description: Google Cloud Pub/Sub Delete a topic\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-pubsub.deletetopic\n      with:\n        projectId: tools.projectId\n        topicId: tools.topicId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: topicId\n        type: string\n        description: topicId\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: publishmessages\n      description: Google Cloud Pub/Sub Publish messages\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-pubsub.publishmessages\n      with:\n        projectId: tools.projectId\n        topicId: tools.topicId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: topicId\n        type: string\n        description: topicId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsubscriptions\n      description: Google Cloud Pub/Sub List subscriptions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-pubsub.listsubscriptions\n      with:\n        projectId: tools.projectId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n\
  \      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsubscription\n      description: Google Cloud Pub/Sub Get a subscription\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-pubsub.getsubscription\n      with:\n        projectId: tools.projectId\n        subscriptionId: tools.subscriptionId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: subscriptionId\n        type: string\n        description: subscriptionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsubscription\n     \
  \ description: Google Cloud Pub/Sub Create a subscription\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-cloud-pubsub.createsubscription\n      with:\n        projectId: tools.projectId\n        subscriptionId: tools.subscriptionId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: subscriptionId\n        type: string\n        description: subscriptionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesubscription\n      description: Google Cloud Pub/Sub Delete a subscription\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-pubsub.deletesubscription\n      with:\n        projectId: tools.projectId\n        subscriptionId: tools.subscriptionId\n      inputParameters:\n      - name: projectId\n        type:\
  \ string\n        description: projectId\n        required: true\n      - name: subscriptionId\n        type: string\n        description: subscriptionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pullmessages\n      description: Google Cloud Pub/Sub Pull messages\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-pubsub.pullmessages\n      with:\n        projectId: tools.projectId\n        subscriptionId: tools.subscriptionId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: subscriptionId\n        type: string\n        description: subscriptionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: acknowledgemessages\n      description: Google Cloud Pub/Sub Acknowledge messages\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: google-cloud-pubsub.acknowledgemessages\n      with:\n        projectId: tools.projectId\n        subscriptionId: tools.subscriptionId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: subscriptionId\n        type: string\n        description: subscriptionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listschemas\n      description: Google Cloud Pub/Sub List schemas\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-pubsub.listschemas\n      with:\n        projectId: tools.projectId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: pageSize\n \
  \       type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createschema\n      description: Google Cloud Pub/Sub Create a schema\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-pubsub.createschema\n      with:\n        projectId: tools.projectId\n        schemaId: tools.schemaId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: schemaId\n        type: string\n        description: schemaId\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_PUBSUB_TOKEN: GOOGLE_CLOUD_PUBSUB_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-pubsub/refs/heads/main/capabilities/google-cloud-pubsub-capability.yaml
tags:
- Google
- Cloud
- Pubsub
- API
tools:
- description: Google Cloud Pub/Sub List topics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtopics
- description: Google Cloud Pub/Sub Get a topic
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettopic
- description: Google Cloud Pub/Sub Create a topic
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createtopic
- description: Google Cloud Pub/Sub Delete a topic
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetopic
- description: Google Cloud Pub/Sub Publish messages
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publishmessages
- description: Google Cloud Pub/Sub List subscriptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsubscriptions
- description: Google Cloud Pub/Sub Get a subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubscription
- description: Google Cloud Pub/Sub Create a subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createsubscription
- description: Google Cloud Pub/Sub Delete a subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesubscription
- description: Google Cloud Pub/Sub Pull messages
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pullmessages
- description: Google Cloud Pub/Sub Acknowledge messages
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: acknowledgemessages
- description: Google Cloud Pub/Sub List schemas
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschemas
- description: Google Cloud Pub/Sub Create a schema
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createschema
---
