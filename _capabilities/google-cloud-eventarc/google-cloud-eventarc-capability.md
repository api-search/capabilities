---
categories: []
consumed_apis: []
description: The Eventarc API enables event-driven architecture by allowing you to create triggers that route events from providers to target destinations such as Cloud Run, Cloud Functions, GKE, and Workflows.
layout: capability
name: Google Cloud Eventarc API
operations:
- description: Google Cloud Eventarc List triggers
  method: GET
  name: listtriggers
  path: /v1/projects/{project}/locations/{location}/triggers
- description: Google Cloud Eventarc Create a trigger
  method: POST
  name: createtrigger
  path: /v1/projects/{project}/locations/{location}/triggers
- description: Google Cloud Eventarc Get a trigger
  method: GET
  name: gettrigger
  path: /v1/projects/{project}/locations/{location}/triggers/{trigger}
- description: Google Cloud Eventarc Update a trigger
  method: PATCH
  name: updatetrigger
  path: /v1/projects/{project}/locations/{location}/triggers/{trigger}
- description: Google Cloud Eventarc Delete a trigger
  method: DELETE
  name: deletetrigger
  path: /v1/projects/{project}/locations/{location}/triggers/{trigger}
- description: Google Cloud Eventarc List channels
  method: GET
  name: listchannels
  path: /v1/projects/{project}/locations/{location}/channels
- description: Google Cloud Eventarc Create a channel
  method: POST
  name: createchannel
  path: /v1/projects/{project}/locations/{location}/channels
- description: Google Cloud Eventarc Get a channel
  method: GET
  name: getchannel
  path: /v1/projects/{project}/locations/{location}/channels/{channel}
- description: Google Cloud Eventarc Delete a channel
  method: DELETE
  name: deletechannel
  path: /v1/projects/{project}/locations/{location}/channels/{channel}
- description: Google Cloud Eventarc List providers
  method: GET
  name: listproviders
  path: /v1/projects/{project}/locations/{location}/providers
personas: []
provider_name: Google Cloud Eventarc
provider_slug: google-cloud-eventarc
search_terms:
- event-driven
- listtriggers
- google cloud eventarc create a channel
- api
- listchannels
- listproviders
- google cloud eventarc get a channel
- google cloud eventarc update a trigger
- deletetrigger
- google cloud eventarc list providers
- google
- google cloud eventarc delete a trigger
- triggers
- serverless
- events
- google cloud eventarc get a trigger
- google cloud eventarc delete a channel
- google cloud eventarc list triggers
- gettrigger
- getchannel
- eventarc
- cloud
- createtrigger
- google cloud eventarc create a trigger
- google cloud
- updatetrigger
- messaging
- createchannel
- deletechannel
- google cloud eventarc list channels
slug: google-cloud-eventarc-capability
source_filename: google-cloud-eventarc-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Eventarc API\n  description: The Eventarc API enables event-driven architecture by allowing you to create triggers that route events from\n    providers to target destinations such as Cloud Run, Cloud Functions, GKE, and Workflows.\n  tags:\n  - Google\n  - Cloud\n  - Eventarc\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-eventarc\n    baseUri: https://eventarc.googleapis.com\n    description: Google Cloud Eventarc API HTTP API.\n    resources:\n    - name: v1-projects-project-locations-location-triggers\n      path: /v1/projects/{project}/locations/{location}/triggers\n      operations:\n      - name: listtriggers\n        method: GET\n        description: Google Cloud Eventarc List triggers\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtrigger\n        method: POST\n        description: Google Cloud Eventarc Create a trigger\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: triggerId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-location-triggers-\n      path: /v1/projects/{project}/locations/{location}/triggers/{trigger}\n      operations:\n      - name: gettrigger\n        method: GET\n        description: Google Cloud Eventarc Get a trigger\n        inputParameters:\n\
  \        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: trigger\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetrigger\n        method: PATCH\n        description: Google Cloud Eventarc Update a trigger\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: trigger\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetrigger\n    \
  \    method: DELETE\n        description: Google Cloud Eventarc Delete a trigger\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: trigger\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-location-channels\n      path: /v1/projects/{project}/locations/{location}/channels\n      operations:\n      - name: listchannels\n        method: GET\n        description: Google Cloud Eventarc List channels\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createchannel\n        method: POST\n        description: Google Cloud Eventarc Create a channel\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: channelId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-location-channels-\n      path: /v1/projects/{project}/locations/{location}/channels/{channel}\n      operations:\n      - name: getchannel\n        method: GET\n        description: Google Cloud Eventarc Get a channel\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required:\
  \ true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: channel\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletechannel\n        method: DELETE\n        description: Google Cloud Eventarc Delete a channel\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: channel\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-location-providers\n      path: /v1/projects/{project}/locations/{location}/providers\n\
  \      operations:\n      - name: listproviders\n        method: GET\n        description: Google Cloud Eventarc List providers\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-eventarc-rest\n    description: REST adapter for Google Cloud Eventarc API.\n    resources:\n    - path: /v1/projects/{project}/locations/{location}/triggers\n      name: listtriggers\n      operations:\n      - method: GET\n        name: listtriggers\n        description: Google Cloud Eventarc List triggers\n        call: google-cloud-eventarc.listtriggers\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/triggers\n      name: createtrigger\n      operations:\n      - method: POST\n        name: createtrigger\n        description: Google Cloud Eventarc Create a trigger\n        call: google-cloud-eventarc.createtrigger\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/triggers/{trigger}\n      name: gettrigger\n      operations:\n      - method: GET\n        name: gettrigger\n        description: Google Cloud Eventarc Get a trigger\n        call: google-cloud-eventarc.gettrigger\n        with:\n          project: rest.project\n          location: rest.location\n          trigger: rest.trigger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/triggers/{trigger}\n\
  \      name: updatetrigger\n      operations:\n      - method: PATCH\n        name: updatetrigger\n        description: Google Cloud Eventarc Update a trigger\n        call: google-cloud-eventarc.updatetrigger\n        with:\n          project: rest.project\n          location: rest.location\n          trigger: rest.trigger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/triggers/{trigger}\n      name: deletetrigger\n      operations:\n      - method: DELETE\n        name: deletetrigger\n        description: Google Cloud Eventarc Delete a trigger\n        call: google-cloud-eventarc.deletetrigger\n        with:\n          project: rest.project\n          location: rest.location\n          trigger: rest.trigger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/channels\n      name: listchannels\n      operations:\n      - method:\
  \ GET\n        name: listchannels\n        description: Google Cloud Eventarc List channels\n        call: google-cloud-eventarc.listchannels\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/channels\n      name: createchannel\n      operations:\n      - method: POST\n        name: createchannel\n        description: Google Cloud Eventarc Create a channel\n        call: google-cloud-eventarc.createchannel\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/channels/{channel}\n      name: getchannel\n      operations:\n      - method: GET\n        name: getchannel\n        description: Google Cloud Eventarc Get a channel\n        call: google-cloud-eventarc.getchannel\n\
  \        with:\n          project: rest.project\n          location: rest.location\n          channel: rest.channel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/channels/{channel}\n      name: deletechannel\n      operations:\n      - method: DELETE\n        name: deletechannel\n        description: Google Cloud Eventarc Delete a channel\n        call: google-cloud-eventarc.deletechannel\n        with:\n          project: rest.project\n          location: rest.location\n          channel: rest.channel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/providers\n      name: listproviders\n      operations:\n      - method: GET\n        name: listproviders\n        description: Google Cloud Eventarc List providers\n        call: google-cloud-eventarc.listproviders\n        with:\n          project: rest.project\n          location:\
  \ rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-eventarc-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Eventarc API for AI agent use.\n    tools:\n    - name: listtriggers\n      description: Google Cloud Eventarc List triggers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-eventarc.listtriggers\n      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtrigger\n      description: Google Cloud Eventarc Create a trigger\n      hints:\n        readOnly: false\n      \
  \  destructive: false\n        idempotent: false\n      call: google-cloud-eventarc.createtrigger\n      with:\n        project: tools.project\n        location: tools.location\n        triggerId: tools.triggerId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: triggerId\n        type: string\n        description: triggerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettrigger\n      description: Google Cloud Eventarc Get a trigger\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-eventarc.gettrigger\n      with:\n        project: tools.project\n        location: tools.location\n        trigger: tools.trigger\n      inputParameters:\n      - name: project\n        type: string\n        description:\
  \ project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: trigger\n        type: string\n        description: trigger\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatetrigger\n      description: Google Cloud Eventarc Update a trigger\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-eventarc.updatetrigger\n      with:\n        project: tools.project\n        location: tools.location\n        trigger: tools.trigger\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: trigger\n        type: string\n        description: trigger\n        required: true\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: deletetrigger\n      description: Google Cloud Eventarc Delete a trigger\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-eventarc.deletetrigger\n      with:\n        project: tools.project\n        location: tools.location\n        trigger: tools.trigger\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: trigger\n        type: string\n        description: trigger\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listchannels\n      description: Google Cloud Eventarc List channels\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-eventarc.listchannels\n      with:\n    \
  \    project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createchannel\n      description: Google Cloud Eventarc Create a channel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-eventarc.createchannel\n      with:\n        project: tools.project\n        location: tools.location\n        channelId: tools.channelId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: channelId\n        type: string\n        description: channelId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getchannel\n      description: Google Cloud Eventarc Get a channel\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-eventarc.getchannel\n      with:\n        project: tools.project\n        location: tools.location\n        channel: tools.channel\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: channel\n        type: string\n        description: channel\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletechannel\n      description: Google Cloud Eventarc Delete a channel\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-eventarc.deletechannel\n\
  \      with:\n        project: tools.project\n        location: tools.location\n        channel: tools.channel\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: channel\n        type: string\n        description: channel\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listproviders\n      description: Google Cloud Eventarc List providers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-eventarc.listproviders\n      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-eventarc/refs/heads/main/capabilities/google-cloud-eventarc-capability.yaml
tags:
- Google
- Cloud
- Eventarc
- API
tools:
- description: Google Cloud Eventarc List triggers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtriggers
- description: Google Cloud Eventarc Create a trigger
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtrigger
- description: Google Cloud Eventarc Get a trigger
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettrigger
- description: Google Cloud Eventarc Update a trigger
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatetrigger
- description: Google Cloud Eventarc Delete a trigger
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetrigger
- description: Google Cloud Eventarc List channels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchannels
- description: Google Cloud Eventarc Create a channel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchannel
- description: Google Cloud Eventarc Get a channel
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchannel
- description: Google Cloud Eventarc Delete a channel
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletechannel
- description: Google Cloud Eventarc List providers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproviders
---
