---
categories: []
consumed_apis: []
description: The Cloud Tasks API enables management of distributed task execution. It allows you to create queues, enqueue tasks, and configure retry and rate limiting behavior for tasks targeting App Engine or arbitrary HTTP endpoints.
layout: capability
name: Google Cloud Tasks API
operations:
- description: Google Cloud Tasks List queues
  method: GET
  name: listqueues
  path: /v2/projects/{project}/locations/{location}/queues
- description: Google Cloud Tasks Create a queue
  method: POST
  name: createqueue
  path: /v2/projects/{project}/locations/{location}/queues
- description: Google Cloud Tasks Get a queue
  method: GET
  name: getqueue
  path: /v2/projects/{project}/locations/{location}/queues/{queue}
- description: Google Cloud Tasks Update a queue
  method: PATCH
  name: updatequeue
  path: /v2/projects/{project}/locations/{location}/queues/{queue}
- description: Google Cloud Tasks Delete a queue
  method: DELETE
  name: deletequeue
  path: /v2/projects/{project}/locations/{location}/queues/{queue}
- description: Google Cloud Tasks List tasks
  method: GET
  name: listtasks
  path: /v2/projects/{project}/locations/{location}/queues/{queue}/tasks
- description: Google Cloud Tasks Create a task
  method: POST
  name: createtask
  path: /v2/projects/{project}/locations/{location}/queues/{queue}/tasks
- description: Google Cloud Tasks Get a task
  method: GET
  name: gettask
  path: /v2/projects/{project}/locations/{location}/queues/{queue}/tasks/{task}
- description: Google Cloud Tasks Delete a task
  method: DELETE
  name: deletetask
  path: /v2/projects/{project}/locations/{location}/queues/{queue}/tasks/{task}
- description: Google Cloud Tasks Run a task
  method: POST
  name: runtask
  path: /v2/projects/{project}/locations/{location}/queues/{queue}/tasks/{task}:run
personas: []
provider_name: Google Cloud Tasks
provider_slug: google-cloud-tasks
search_terms:
- listtasks
- getqueue
- google cloud tasks delete a task
- distributed systems
- background jobs
- api
- google cloud tasks get a queue
- gettask
- deletequeue
- google cloud tasks update a queue
- google
- google cloud tasks get a task
- tasks
- google cloud tasks delete a queue
- updatequeue
- google cloud tasks create a task
- google cloud tasks run a task
- google cloud tasks list queues
- cloud
- asynchronous
- runtask
- deletetask
- queues
- google cloud tasks create a queue
- google cloud tasks list tasks
- listqueues
- google cloud
- createtask
- createqueue
slug: google-cloud-tasks-capability
source_filename: google-cloud-tasks-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Tasks API\n  description: The Cloud Tasks API enables management of distributed task execution. It allows you to create queues, enqueue\n    tasks, and configure retry and rate limiting behavior for tasks targeting App Engine or arbitrary HTTP endpoints.\n  tags:\n  - Google\n  - Cloud\n  - Tasks\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-tasks\n    baseUri: https://cloudtasks.googleapis.com\n    description: Google Cloud Tasks API HTTP API.\n    resources:\n    - name: v2-projects-project-locations-location-queues\n      path: /v2/projects/{project}/locations/{location}/queues\n      operations:\n      - name: listqueues\n        method: GET\n        description: Google Cloud Tasks List queues\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createqueue\n        method: POST\n        description: Google Cloud Tasks Create a queue\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-projects-project-locations-location-queues-qu\n      path: /v2/projects/{project}/locations/{location}/queues/{queue}\n      operations:\n      - name: getqueue\n        method: GET\n        description: Google Cloud Tasks Get a queue\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n      \
  \    required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: queue\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatequeue\n        method: PATCH\n        description: Google Cloud Tasks Update a queue\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: queue\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletequeue\n        method: DELETE\n        description: Google Cloud Tasks Delete a queue\n        inputParameters:\n\
  \        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: queue\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-projects-project-locations-location-queues-qu\n      path: /v2/projects/{project}/locations/{location}/queues/{queue}/tasks\n      operations:\n      - name: listtasks\n        method: GET\n        description: Google Cloud Tasks List tasks\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: queue\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtask\n        method: POST\n        description: Google Cloud Tasks Create a task\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: queue\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-projects-project-locations-location-queues-qu\n      path: /v2/projects/{project}/locations/{location}/queues/{queue}/tasks/{task}\n      operations:\n      - name: gettask\n        method: GET\n        description: Google Cloud Tasks Get a task\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n\
  \          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: queue\n          in: path\n          type: string\n          required: true\n        - name: task\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetask\n        method: DELETE\n        description: Google Cloud Tasks Delete a task\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: queue\n          in: path\n          type: string\n          required: true\n        - name: task\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v2-projects-project-locations-location-queues-qu\n      path: /v2/projects/{project}/locations/{location}/queues/{queue}/tasks/{task}:run\n      operations:\n      - name: runtask\n        method: POST\n        description: Google Cloud Tasks Run a task\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: queue\n          in: path\n          type: string\n          required: true\n        - name: task\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-tasks-rest\n    description: REST adapter for Google Cloud Tasks\
  \ API.\n    resources:\n    - path: /v2/projects/{project}/locations/{location}/queues\n      name: listqueues\n      operations:\n      - method: GET\n        name: listqueues\n        description: Google Cloud Tasks List queues\n        call: google-cloud-tasks.listqueues\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/projects/{project}/locations/{location}/queues\n      name: createqueue\n      operations:\n      - method: POST\n        name: createqueue\n        description: Google Cloud Tasks Create a queue\n        call: google-cloud-tasks.createqueue\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/projects/{project}/locations/{location}/queues/{queue}\n      name: getqueue\n      operations:\n      - method: GET\n        name: getqueue\n\
  \        description: Google Cloud Tasks Get a queue\n        call: google-cloud-tasks.getqueue\n        with:\n          project: rest.project\n          location: rest.location\n          queue: rest.queue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/projects/{project}/locations/{location}/queues/{queue}\n      name: updatequeue\n      operations:\n      - method: PATCH\n        name: updatequeue\n        description: Google Cloud Tasks Update a queue\n        call: google-cloud-tasks.updatequeue\n        with:\n          project: rest.project\n          location: rest.location\n          queue: rest.queue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/projects/{project}/locations/{location}/queues/{queue}\n      name: deletequeue\n      operations:\n      - method: DELETE\n        name: deletequeue\n        description: Google Cloud Tasks Delete a queue\n        call: google-cloud-tasks.deletequeue\n\
  \        with:\n          project: rest.project\n          location: rest.location\n          queue: rest.queue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/projects/{project}/locations/{location}/queues/{queue}/tasks\n      name: listtasks\n      operations:\n      - method: GET\n        name: listtasks\n        description: Google Cloud Tasks List tasks\n        call: google-cloud-tasks.listtasks\n        with:\n          project: rest.project\n          location: rest.location\n          queue: rest.queue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/projects/{project}/locations/{location}/queues/{queue}/tasks\n      name: createtask\n      operations:\n      - method: POST\n        name: createtask\n        description: Google Cloud Tasks Create a task\n        call: google-cloud-tasks.createtask\n        with:\n          project: rest.project\n          location: rest.location\n          queue:\
  \ rest.queue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/projects/{project}/locations/{location}/queues/{queue}/tasks/{task}\n      name: gettask\n      operations:\n      - method: GET\n        name: gettask\n        description: Google Cloud Tasks Get a task\n        call: google-cloud-tasks.gettask\n        with:\n          project: rest.project\n          location: rest.location\n          queue: rest.queue\n          task: rest.task\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/projects/{project}/locations/{location}/queues/{queue}/tasks/{task}\n      name: deletetask\n      operations:\n      - method: DELETE\n        name: deletetask\n        description: Google Cloud Tasks Delete a task\n        call: google-cloud-tasks.deletetask\n        with:\n          project: rest.project\n          location: rest.location\n          queue: rest.queue\n          task: rest.task\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v2/projects/{project}/locations/{location}/queues/{queue}/tasks/{task}:run\n      name: runtask\n      operations:\n      - method: POST\n        name: runtask\n        description: Google Cloud Tasks Run a task\n        call: google-cloud-tasks.runtask\n        with:\n          project: rest.project\n          location: rest.location\n          queue: rest.queue\n          task: rest.task\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-tasks-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Tasks API for AI agent use.\n    tools:\n    - name: listqueues\n      description: Google Cloud Tasks List queues\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-tasks.listqueues\n      with:\n        project: tools.project\n        location: tools.location\n   \
  \   inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createqueue\n      description: Google Cloud Tasks Create a queue\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-tasks.createqueue\n      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getqueue\n      description: Google Cloud Tasks Get a queue\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: google-cloud-tasks.getqueue\n      with:\n        project: tools.project\n        location: tools.location\n        queue: tools.queue\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: queue\n        type: string\n        description: queue\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatequeue\n      description: Google Cloud Tasks Update a queue\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-tasks.updatequeue\n      with:\n        project: tools.project\n        location: tools.location\n        queue: tools.queue\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n      \
  \  required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: queue\n        type: string\n        description: queue\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletequeue\n      description: Google Cloud Tasks Delete a queue\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-tasks.deletequeue\n      with:\n        project: tools.project\n        location: tools.location\n        queue: tools.queue\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: queue\n        type: string\n        description: queue\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ listtasks\n      description: Google Cloud Tasks List tasks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-tasks.listtasks\n      with:\n        project: tools.project\n        location: tools.location\n        queue: tools.queue\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: queue\n        type: string\n        description: queue\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtask\n      description: Google Cloud Tasks Create a task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-tasks.createtask\n      with:\n        project: tools.project\n        location: tools.location\n        queue: tools.queue\n\
  \      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: queue\n        type: string\n        description: queue\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettask\n      description: Google Cloud Tasks Get a task\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-tasks.gettask\n      with:\n        project: tools.project\n        location: tools.location\n        queue: tools.queue\n        task: tools.task\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: queue\n        type: string\n        description:\
  \ queue\n        required: true\n      - name: task\n        type: string\n        description: task\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetask\n      description: Google Cloud Tasks Delete a task\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-tasks.deletetask\n      with:\n        project: tools.project\n        location: tools.location\n        queue: tools.queue\n        task: tools.task\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: queue\n        type: string\n        description: queue\n        required: true\n      - name: task\n        type: string\n        description: task\n        required: true\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: runtask\n      description: Google Cloud Tasks Run a task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-tasks.runtask\n      with:\n        project: tools.project\n        location: tools.location\n        queue: tools.queue\n        task: tools.task\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: queue\n        type: string\n        description: queue\n        required: true\n      - name: task\n        type: string\n        description: task\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-tasks/refs/heads/main/capabilities/google-cloud-tasks-capability.yaml
tags:
- Google
- Cloud
- Tasks
- API
tools:
- description: Google Cloud Tasks List queues
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listqueues
- description: Google Cloud Tasks Create a queue
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createqueue
- description: Google Cloud Tasks Get a queue
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getqueue
- description: Google Cloud Tasks Update a queue
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatequeue
- description: Google Cloud Tasks Delete a queue
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletequeue
- description: Google Cloud Tasks List tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtasks
- description: Google Cloud Tasks Create a task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtask
- description: Google Cloud Tasks Get a task
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettask
- description: Google Cloud Tasks Delete a task
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetask
- description: Google Cloud Tasks Run a task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runtask
---
