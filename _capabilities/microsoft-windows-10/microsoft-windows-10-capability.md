---
categories: []
consumed_apis: []
description: API for running code in the background when an application is suspended or not running. Based on the Windows.ApplicationModel.Background namespace, it supports time-triggered, system-triggered, and maintenance-triggered background tasks. Key classes include BackgroundTaskBuilder, BackgroundTaskRegistration, SystemTrigger, TimeTrigger, and BackgroundTaskCompletedEventArgs.
layout: capability
name: Microsoft Windows 10 Windows Background Tasks API
operations:
- description: Microsoft Windows 10 List registered background tasks
  method: GET
  name: listbackgroundtasks
  path: /background-tasks
- description: Microsoft Windows 10 Register a background task
  method: POST
  name: registerbackgroundtask
  path: /background-tasks
- description: Microsoft Windows 10 Get background task details
  method: GET
  name: getbackgroundtask
  path: /background-tasks/{taskId}
- description: Microsoft Windows 10 Unregister a background task
  method: DELETE
  name: unregisterbackgroundtask
  path: /background-tasks/{taskId}
- description: Microsoft Windows 10 Get background access status
  method: GET
  name: getbackgroundaccessstatus
  path: /background-tasks/access
- description: Microsoft Windows 10 Request background access
  method: POST
  name: requestbackgroundaccess
  path: /background-tasks/access
- description: Microsoft Windows 10 List available trigger types
  method: GET
  name: listtriggertypes
  path: /background-tasks/triggers
personas: []
provider_name: Microsoft Windows 10
provider_slug: microsoft-windows-10
search_terms:
- listtriggertypes
- microsoft windows 10 register a background task
- getbackgroundtask
- api
- microsoft windows 10 list available trigger types
- '10'
- microsoft windows 10 get background task details
- listbackgroundtasks
- unregisterbackgroundtask
- microsoft windows 10 request background access
- microsoft
- requestbackgroundaccess
- uwp
- operating system
- win32
- microsoft windows 10 list registered background tasks
- microsoft windows 10 unregister a background task
- registerbackgroundtask
- desktop
- microsoft windows 10 get background access status
- getbackgroundaccessstatus
- windows
slug: microsoft-windows-10-capability
source_filename: microsoft-windows-10-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Windows 10 Windows Background Tasks API\n  description: API for running code in the background when an application is suspended or not running. Based on the Windows.ApplicationModel.Background\n    namespace, it supports time-triggered, system-triggered, and maintenance-triggered background tasks. Key classes include\n    BackgroundTaskBuilder, BackgroundTaskRegistration, SystemTrigger, TimeTrigger, and BackgroundTaskCompletedEventArgs.\n  tags:\n  - Microsoft\n  - Windows\n  - '10'\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-windows-10\n    baseUri: https://api.windows.com\n    description: Microsoft Windows 10 Windows Background Tasks API HTTP API.\n    resources:\n    - name: background-tasks\n      path: /background-tasks\n      operations:\n      - name: listbackgroundtasks\n        method: GET\n        description: Microsoft Windows 10 List\
  \ registered background tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: registerbackgroundtask\n        method: POST\n        description: Microsoft Windows 10 Register a background task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: background-tasks-taskid\n      path: /background-tasks/{taskId}\n      operations:\n      - name: getbackgroundtask\n        method: GET\n        description: Microsoft Windows 10 Get background task details\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n          description: Background task registration ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unregisterbackgroundtask\n        method: DELETE\n\
  \        description: Microsoft Windows 10 Unregister a background task\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n          description: Background task registration ID\n        - name: cancelRunningTask\n          in: query\n          type: boolean\n          description: Whether to cancel a running instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: background-tasks-access\n      path: /background-tasks/access\n      operations:\n      - name: getbackgroundaccessstatus\n        method: GET\n        description: Microsoft Windows 10 Get background access status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: requestbackgroundaccess\n        method: POST\n        description: Microsoft Windows 10 Request background access\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: background-tasks-triggers\n      path: /background-tasks/triggers\n      operations:\n      - name: listtriggertypes\n        method: GET\n        description: Microsoft Windows 10 List available trigger types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-windows-10-rest\n    description: REST adapter for Microsoft Windows 10 Windows Background Tasks API.\n    resources:\n    - path: /background-tasks\n      name: listbackgroundtasks\n      operations:\n      - method: GET\n        name: listbackgroundtasks\n        description: Microsoft Windows 10 List registered background tasks\n        call: microsoft-windows-10.listbackgroundtasks\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /background-tasks\n      name: registerbackgroundtask\n      operations:\n      - method: POST\n        name: registerbackgroundtask\n        description: Microsoft Windows 10 Register a background task\n        call: microsoft-windows-10.registerbackgroundtask\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /background-tasks/{taskId}\n      name: getbackgroundtask\n      operations:\n      - method: GET\n        name: getbackgroundtask\n        description: Microsoft Windows 10 Get background task details\n        call: microsoft-windows-10.getbackgroundtask\n        with:\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /background-tasks/{taskId}\n      name: unregisterbackgroundtask\n      operations:\n      - method: DELETE\n        name: unregisterbackgroundtask\n        description: Microsoft Windows 10 Unregister a background task\n        call: microsoft-windows-10.unregisterbackgroundtask\n\
  \        with:\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /background-tasks/access\n      name: getbackgroundaccessstatus\n      operations:\n      - method: GET\n        name: getbackgroundaccessstatus\n        description: Microsoft Windows 10 Get background access status\n        call: microsoft-windows-10.getbackgroundaccessstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /background-tasks/access\n      name: requestbackgroundaccess\n      operations:\n      - method: POST\n        name: requestbackgroundaccess\n        description: Microsoft Windows 10 Request background access\n        call: microsoft-windows-10.requestbackgroundaccess\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /background-tasks/triggers\n      name: listtriggertypes\n      operations:\n      - method: GET\n        name: listtriggertypes\n        description:\
  \ Microsoft Windows 10 List available trigger types\n        call: microsoft-windows-10.listtriggertypes\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-windows-10-mcp\n    transport: http\n    description: MCP adapter for Microsoft Windows 10 Windows Background Tasks API for AI agent use.\n    tools:\n    - name: listbackgroundtasks\n      description: Microsoft Windows 10 List registered background tasks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-windows-10.listbackgroundtasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: registerbackgroundtask\n      description: Microsoft Windows 10 Register a background task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-windows-10.registerbackgroundtask\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: getbackgroundtask\n      description: Microsoft Windows 10 Get background task details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-windows-10.getbackgroundtask\n      with:\n        taskId: tools.taskId\n      inputParameters:\n      - name: taskId\n        type: string\n        description: Background task registration ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unregisterbackgroundtask\n      description: Microsoft Windows 10 Unregister a background task\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-windows-10.unregisterbackgroundtask\n      with:\n        taskId: tools.taskId\n        cancelRunningTask: tools.cancelRunningTask\n      inputParameters:\n      - name: taskId\n        type: string\n        description: Background task registration\
  \ ID\n        required: true\n      - name: cancelRunningTask\n        type: boolean\n        description: Whether to cancel a running instance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbackgroundaccessstatus\n      description: Microsoft Windows 10 Get background access status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-windows-10.getbackgroundaccessstatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: requestbackgroundaccess\n      description: Microsoft Windows 10 Request background access\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-windows-10.requestbackgroundaccess\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtriggertypes\n      description: Microsoft Windows 10 List available trigger types\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: microsoft-windows-10.listtriggertypes\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-windows-10/refs/heads/main/capabilities/microsoft-windows-10-capability.yaml
tags:
- Microsoft
- Windows
- '10'
- API
tools:
- description: Microsoft Windows 10 List registered background tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbackgroundtasks
- description: Microsoft Windows 10 Register a background task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: registerbackgroundtask
- description: Microsoft Windows 10 Get background task details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbackgroundtask
- description: Microsoft Windows 10 Unregister a background task
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: unregisterbackgroundtask
- description: Microsoft Windows 10 Get background access status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbackgroundaccessstatus
- description: Microsoft Windows 10 Request background access
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: requestbackgroundaccess
- description: Microsoft Windows 10 List available trigger types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtriggertypes
---
