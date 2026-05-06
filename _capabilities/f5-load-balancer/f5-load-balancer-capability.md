---
categories: []
consumed_apis: []
description: The Application Services 3 Extension (AS3) provides a declarative API for managing application-specific configurations on BIG-IP systems. AS3 uses JSON declarations to describe the desired state of Layer 4-7 application services, enabling infrastructure-as-code workflows for load balancing, SSL offloading, and traffic management. Rather than issuing imperative commands, users submit a complete declaration and AS3 configures the BIG-IP to match the declared state.
layout: capability
name: F5 Load Balancer F5 BIG-IP Application Services 3 Extension (AS3) API
operations:
- description: F5 Load Balancer Submit an AS3 declaration
  method: POST
  name: submitdeclaration
  path: /declare
- description: F5 Load Balancer Retrieve the current AS3 declaration
  method: GET
  name: getdeclaration
  path: /declare
- description: F5 Load Balancer Remove the AS3 declaration
  method: DELETE
  name: deletedeclaration
  path: /declare
- description: F5 Load Balancer Partially update the AS3 declaration
  method: PATCH
  name: patchdeclaration
  path: /declare
- description: F5 Load Balancer Retrieve declaration for a specific tenant
  method: GET
  name: gettenantdeclaration
  path: /declare/{tenantName}
- description: F5 Load Balancer Remove a specific tenant declaration
  method: DELETE
  name: deletetenantdeclaration
  path: /declare/{tenantName}
- description: F5 Load Balancer List all AS3 tasks
  method: GET
  name: listtasks
  path: /task
- description: F5 Load Balancer Get status of a specific task
  method: GET
  name: gettask
  path: /task/{taskId}
- description: F5 Load Balancer Get AS3 extension information
  method: GET
  name: getinfo
  path: /info
personas: []
provider_name: F5 Load Balancer
provider_slug: f5-load-balancer
search_terms:
- networking
- balancer
- f5
- submitdeclaration
- f5 load balancer partially update the as3 declaration
- gettask
- deletetenantdeclaration
- application delivery
- getdeclaration
- f5 load balancer retrieve declaration for a specific tenant
- getinfo
- f5 load balancer remove a specific tenant declaration
- f5 load balancer retrieve the current as3 declaration
- f5 load balancer get status of a specific task
- big-ip
- api
- listtasks
- f5 load balancer list all as3 tasks
- load balancer
- load
- patchdeclaration
- gettenantdeclaration
- traffic management
- f5 load balancer submit an as3 declaration
- f5 load balancer remove the as3 declaration
- deletedeclaration
- f5 load balancer get as3 extension information
slug: f5-load-balancer-capability
source_filename: f5-load-balancer-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: F5 Load Balancer F5 BIG-IP Application Services 3 Extension (AS3) API\n  description: The Application Services 3 Extension (AS3) provides a declarative API for managing application-specific configurations\n    on BIG-IP systems. AS3 uses JSON declarations to describe the desired state of Layer 4-7 application services, enabling\n    infrastructure-as-code workflows for load balancing, SSL offloading, and traffic management. Rather than issuing imperative\n    commands, users submit a complete declaration and AS3 configures the BIG-IP to match the declared state.\n  tags:\n  - F5\n  - Load\n  - Balancer\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: f5-load-balancer\n    baseUri: https://192.168.1.245/mgmt/shared/appsvcs\n    description: F5 Load Balancer F5 BIG-IP Application Services 3 Extension (AS3) API HTTP API.\n    authentication:\n      type: basic\n      username:\
  \ '{{F5_LOAD_BALANCER_USERNAME}}'\n      password: '{{F5_LOAD_BALANCER_PASSWORD}}'\n    resources:\n    - name: declare\n      path: /declare\n      operations:\n      - name: submitdeclaration\n        method: POST\n        description: F5 Load Balancer Submit an AS3 declaration\n        inputParameters:\n        - name: async\n          in: query\n          type: boolean\n          description: When true, returns immediately with a task ID for asynchronous processing. Recommended for large declarations.\n        - name: show\n          in: query\n          type: string\n          description: Controls the level of detail in the response. Use full to include all configuration details, or base\n            for a summary.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getdeclaration\n        method: GET\n        description: F5 Load Balancer Retrieve the current AS3 declaration\n        inputParameters:\n\
  \        - name: show\n          in: query\n          type: string\n          description: Controls the level of detail in the response.\n        - name: age\n          in: query\n          type: integer\n          description: Retrieve a previous declaration by age. Use 0 for the most recent, 1 for the previous, and so on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedeclaration\n        method: DELETE\n        description: F5 Load Balancer Remove the AS3 declaration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchdeclaration\n        method: PATCH\n        description: F5 Load Balancer Partially update the AS3 declaration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: declare-tenantname\n     \
  \ path: /declare/{tenantName}\n      operations:\n      - name: gettenantdeclaration\n        method: GET\n        description: F5 Load Balancer Retrieve declaration for a specific tenant\n        inputParameters:\n        - name: show\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetenantdeclaration\n        method: DELETE\n        description: F5 Load Balancer Remove a specific tenant declaration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task\n      path: /task\n      operations:\n      - name: listtasks\n        method: GET\n        description: F5 Load Balancer List all AS3 tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task-taskid\n      path: /task/{taskId}\n\
  \      operations:\n      - name: gettask\n        method: GET\n        description: F5 Load Balancer Get status of a specific task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: info\n      path: /info\n      operations:\n      - name: getinfo\n        method: GET\n        description: F5 Load Balancer Get AS3 extension information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: f5-load-balancer-rest\n    description: REST adapter for F5 Load Balancer F5 BIG-IP Application Services 3 Extension (AS3) API.\n    resources:\n    - path: /declare\n      name: submitdeclaration\n      operations:\n      - method: POST\n        name: submitdeclaration\n        description: F5 Load Balancer Submit an AS3 declaration\n        call: f5-load-balancer.submitdeclaration\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /declare\n      name: getdeclaration\n      operations:\n      - method: GET\n        name: getdeclaration\n        description: F5 Load Balancer Retrieve the current AS3 declaration\n        call: f5-load-balancer.getdeclaration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /declare\n      name: deletedeclaration\n      operations:\n      - method: DELETE\n        name: deletedeclaration\n        description: F5 Load Balancer Remove the AS3 declaration\n        call: f5-load-balancer.deletedeclaration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /declare\n      name: patchdeclaration\n      operations:\n      - method: PATCH\n        name: patchdeclaration\n        description: F5 Load Balancer Partially update the AS3 declaration\n        call: f5-load-balancer.patchdeclaration\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /declare/{tenantName}\n      name: gettenantdeclaration\n      operations:\n      - method: GET\n        name: gettenantdeclaration\n        description: F5 Load Balancer Retrieve declaration for a specific tenant\n        call: f5-load-balancer.gettenantdeclaration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /declare/{tenantName}\n      name: deletetenantdeclaration\n      operations:\n      - method: DELETE\n        name: deletetenantdeclaration\n        description: F5 Load Balancer Remove a specific tenant declaration\n        call: f5-load-balancer.deletetenantdeclaration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /task\n      name: listtasks\n      operations:\n      - method: GET\n        name: listtasks\n        description: F5 Load Balancer List all AS3 tasks\n        call: f5-load-balancer.listtasks\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /task/{taskId}\n      name: gettask\n      operations:\n      - method: GET\n        name: gettask\n        description: F5 Load Balancer Get status of a specific task\n        call: f5-load-balancer.gettask\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /info\n      name: getinfo\n      operations:\n      - method: GET\n        name: getinfo\n        description: F5 Load Balancer Get AS3 extension information\n        call: f5-load-balancer.getinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: f5-load-balancer-mcp\n    transport: http\n    description: MCP adapter for F5 Load Balancer F5 BIG-IP Application Services 3 Extension (AS3) API for AI agent use.\n    tools:\n    - name: submitdeclaration\n      description: F5 Load Balancer Submit an AS3 declaration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: f5-load-balancer.submitdeclaration\n      with:\n        async: tools.async\n        show: tools.show\n      inputParameters:\n      - name: async\n        type: boolean\n        description: When true, returns immediately with a task ID for asynchronous processing. Recommended for large declarations.\n      - name: show\n        type: string\n        description: Controls the level of detail in the response. Use full to include all configuration details, or base\n          for a summary.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdeclaration\n      description: F5 Load Balancer Retrieve the current AS3 declaration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: f5-load-balancer.getdeclaration\n      with:\n        show: tools.show\n        age: tools.age\n      inputParameters:\n      - name: show\n        type: string\n        description: Controls the level of detail\
  \ in the response.\n      - name: age\n        type: integer\n        description: Retrieve a previous declaration by age. Use 0 for the most recent, 1 for the previous, and so on.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedeclaration\n      description: F5 Load Balancer Remove the AS3 declaration\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: f5-load-balancer.deletedeclaration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchdeclaration\n      description: F5 Load Balancer Partially update the AS3 declaration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: f5-load-balancer.patchdeclaration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettenantdeclaration\n      description: F5 Load Balancer Retrieve declaration for a specific tenant\n      hints:\n     \
  \   readOnly: true\n        destructive: false\n        idempotent: true\n      call: f5-load-balancer.gettenantdeclaration\n      with:\n        show: tools.show\n      inputParameters:\n      - name: show\n        type: string\n        description: show\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetenantdeclaration\n      description: F5 Load Balancer Remove a specific tenant declaration\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: f5-load-balancer.deletetenantdeclaration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtasks\n      description: F5 Load Balancer List all AS3 tasks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: f5-load-balancer.listtasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettask\n      description: F5 Load Balancer Get status of\
  \ a specific task\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: f5-load-balancer.gettask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinfo\n      description: F5 Load Balancer Get AS3 extension information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: f5-load-balancer.getinfo\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    F5_LOAD_BALANCER_USERNAME: F5_LOAD_BALANCER_USERNAME\n    F5_LOAD_BALANCER_PASSWORD: F5_LOAD_BALANCER_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/f5-load-balancer/refs/heads/main/capabilities/f5-load-balancer-capability.yaml
tags:
- F5
- Load
- Balancer
- API
tools:
- description: F5 Load Balancer Submit an AS3 declaration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitdeclaration
- description: F5 Load Balancer Retrieve the current AS3 declaration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeclaration
- description: F5 Load Balancer Remove the AS3 declaration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedeclaration
- description: F5 Load Balancer Partially update the AS3 declaration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchdeclaration
- description: F5 Load Balancer Retrieve declaration for a specific tenant
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettenantdeclaration
- description: F5 Load Balancer Remove a specific tenant declaration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetenantdeclaration
- description: F5 Load Balancer List all AS3 tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtasks
- description: F5 Load Balancer Get status of a specific task
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettask
- description: F5 Load Balancer Get AS3 extension information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinfo
---
