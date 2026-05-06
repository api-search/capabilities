---
categories: []
consumed_apis: []
description: McAfee ePolicy Orchestrator (ePO) REST API for centralized security management, including system management, policy assignment, task scheduling, query execution, and threat event retrieval across managed endpoints.
layout: capability
name: McAfee ePO API
operations:
- description: McAfee List available API commands
  method: GET
  name: corehelp
  path: /core.help
- description: McAfee Search for systems
  method: GET
  name: systemfind
  path: /system.find
- description: McAfee Find systems by tag
  method: GET
  name: systemfindtag
  path: /system.findTag
- description: McAfee Apply a tag to systems
  method: POST
  name: systemapplytag
  path: /system.applyTag
- description: McAfee Remove a tag from systems
  method: POST
  name: systemcleartag
  path: /system.clearTag
- description: McAfee Find system tree groups
  method: GET
  name: epogroupfind
  path: /epogroup.find
- description: McAfee Move a system to a different group
  method: POST
  name: epogroupmovesystem
  path: /epogroup.moveSystem
- description: McAfee Search for policies
  method: GET
  name: policyfind
  path: /policy.find
- description: McAfee Assign a policy to a system
  method: POST
  name: policyassigntosystem
  path: /policy.assignToSystem
- description: McAfee Assign a policy to a group
  method: POST
  name: policyassigntogroup
  path: /policy.assignToGroup
- description: McAfee Search for client tasks
  method: GET
  name: clienttaskfind
  path: /clienttask.find
- description: McAfee Run a client task on systems
  method: POST
  name: clienttaskrun
  path: /clienttask.run
- description: McAfee Execute a saved query
  method: GET
  name: coreexecutequery
  path: /core.executeQuery
- description: McAfee List saved queries
  method: GET
  name: corelistqueries
  path: /core.listQueries
- description: McAfee Find threat events
  method: GET
  name: detectedsystemfind
  path: /detectedsystem.find
- description: McAfee Find software packages
  method: GET
  name: repositoryfindpackages
  path: /repository.findPackages
- description: McAfee List server tasks
  method: GET
  name: schedulerlistservertasks
  path: /scheduler.listServerTasks
- description: McAfee Run a server task
  method: POST
  name: schedulerrunservertask
  path: /scheduler.runServerTask
personas: []
provider_name: McAfee (Trellix)
provider_slug: mcafee
search_terms:
- policyfind
- clienttaskfind
- mcafee run a server task
- systemapplytag
- mcafee find system tree groups
- systemcleartag
- mcafee list saved queries
- mcafee apply a tag to systems
- mcafee move a system to a different group
- systemfindtag
- antivirus
- epogroupfind
- mcafee run a client task on systems
- security
- schedulerrunservertask
- mcafee
- mcafee search for client tasks
- endpoint protection
- mcafee find systems by tag
- clienttaskrun
- coreexecutequery
- mcafee search for systems
- corelistqueries
- systemfind
- api
- policyassigntogroup
- mcafee list available api commands
- mcafee find software packages
- epogroupmovesystem
- repositoryfindpackages
- corehelp
- mcafee find threat events
- policyassigntosystem
- schedulerlistservertasks
- mcafee assign a policy to a group
- detectedsystemfind
- mcafee list server tasks
- cybersecurity
- threat intelligence
- mcafee search for policies
- mcafee execute a saved query
- mcafee remove a tag from systems
- mcafee assign a policy to a system
slug: mcafee-capability
source_filename: mcafee-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: McAfee ePO API\n  description: McAfee ePolicy Orchestrator (ePO) REST API for centralized security management, including system management,\n    policy assignment, task scheduling, query execution, and threat event retrieval across managed endpoints.\n  tags:\n  - Mcafee\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: mcafee\n    baseUri: https://your-epo-server:8443/remote\n    description: McAfee ePO API HTTP API.\n    authentication:\n      type: basic\n      username: '{{MCAFEE_USERNAME}}'\n      password: '{{MCAFEE_PASSWORD}}'\n    resources:\n    - name: core-help\n      path: /core.help\n      operations:\n      - name: corehelp\n        method: GET\n        description: McAfee List available API commands\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-find\n   \
  \   path: /system.find\n      operations:\n      - name: systemfind\n        method: GET\n        description: McAfee Search for systems\n        inputParameters:\n        - name: searchText\n          in: query\n          type: string\n          required: true\n          description: Search string to match against system names, IP addresses, or other properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-findtag\n      path: /system.findTag\n      operations:\n      - name: systemfindtag\n        method: GET\n        description: McAfee Find systems by tag\n        inputParameters:\n        - name: tagName\n          in: query\n          type: string\n          required: true\n          description: Name of the tag to search for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-applytag\n\
  \      path: /system.applyTag\n      operations:\n      - name: systemapplytag\n        method: POST\n        description: McAfee Apply a tag to systems\n        inputParameters:\n        - name: names\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of system names or IDs\n        - name: tagName\n          in: query\n          type: string\n          required: true\n          description: Name of the tag to apply\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-cleartag\n      path: /system.clearTag\n      operations:\n      - name: systemcleartag\n        method: POST\n        description: McAfee Remove a tag from systems\n        inputParameters:\n        - name: names\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of system names or IDs\n        - name:\
  \ tagName\n          in: query\n          type: string\n          required: true\n          description: Name of the tag to remove\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: epogroup-find\n      path: /epogroup.find\n      operations:\n      - name: epogroupfind\n        method: GET\n        description: McAfee Find system tree groups\n        inputParameters:\n        - name: searchText\n          in: query\n          type: string\n          description: Search string to match against group names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: epogroup-movesystem\n      path: /epogroup.moveSystem\n      operations:\n      - name: epogroupmovesystem\n        method: POST\n        description: McAfee Move a system to a different group\n        inputParameters:\n        - name: names\n          in: query\n\
  \          type: string\n          required: true\n          description: Comma-separated list of system names to move\n        - name: parentGroupId\n          in: query\n          type: integer\n          required: true\n          description: ID of the target parent group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policy-find\n      path: /policy.find\n      operations:\n      - name: policyfind\n        method: GET\n        description: McAfee Search for policies\n        inputParameters:\n        - name: searchText\n          in: query\n          type: string\n          description: Search string to match against policy names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policy-assigntosystem\n      path: /policy.assignToSystem\n      operations:\n      - name: policyassigntosystem\n        method:\
  \ POST\n        description: McAfee Assign a policy to a system\n        inputParameters:\n        - name: names\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of system names\n        - name: productId\n          in: query\n          type: string\n          required: true\n          description: Product ID for the policy\n        - name: typeId\n          in: query\n          type: string\n          required: true\n          description: Policy type ID\n        - name: objectId\n          in: query\n          type: integer\n          required: true\n          description: Policy object ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policy-assigntogroup\n      path: /policy.assignToGroup\n      operations:\n      - name: policyassigntogroup\n        method: POST\n        description: McAfee Assign a policy to a group\n    \
  \    inputParameters:\n        - name: groupId\n          in: query\n          type: integer\n          required: true\n          description: Target group ID\n        - name: productId\n          in: query\n          type: string\n          required: true\n          description: Product ID for the policy\n        - name: typeId\n          in: query\n          type: string\n          required: true\n          description: Policy type ID\n        - name: objectId\n          in: query\n          type: integer\n          required: true\n          description: Policy object ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clienttask-find\n      path: /clienttask.find\n      operations:\n      - name: clienttaskfind\n        method: GET\n        description: McAfee Search for client tasks\n        inputParameters:\n        - name: searchText\n          in: query\n          type: string\n          description:\
  \ Search string to match against task names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clienttask-run\n      path: /clienttask.run\n      operations:\n      - name: clienttaskrun\n        method: POST\n        description: McAfee Run a client task on systems\n        inputParameters:\n        - name: names\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of system names\n        - name: productId\n          in: query\n          type: string\n          required: true\n          description: Product ID for the task\n        - name: taskId\n          in: query\n          type: integer\n          required: true\n          description: Client task ID to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: core-executequery\n      path:\
  \ /core.executeQuery\n      operations:\n      - name: coreexecutequery\n        method: GET\n        description: McAfee Execute a saved query\n        inputParameters:\n        - name: queryId\n          in: query\n          type: integer\n          required: true\n          description: ID of the saved query to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: core-listqueries\n      path: /core.listQueries\n      operations:\n      - name: corelistqueries\n        method: GET\n        description: McAfee List saved queries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: detectedsystem-find\n      path: /detectedsystem.find\n      operations:\n      - name: detectedsystemfind\n        method: GET\n        description: McAfee Find threat events\n        inputParameters:\n        - name: searchText\n\
  \          in: query\n          type: string\n          description: Search text to filter threat events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repository-findpackages\n      path: /repository.findPackages\n      operations:\n      - name: repositoryfindpackages\n        method: GET\n        description: McAfee Find software packages\n        inputParameters:\n        - name: searchText\n          in: query\n          type: string\n          description: Search string to filter packages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduler-listservertasks\n      path: /scheduler.listServerTasks\n      operations:\n      - name: schedulerlistservertasks\n        method: GET\n        description: McAfee List server tasks\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: scheduler-runservertask\n      path: /scheduler.runServerTask\n      operations:\n      - name: schedulerrunservertask\n        method: POST\n        description: McAfee Run a server task\n        inputParameters:\n        - name: taskId\n          in: query\n          type: integer\n          required: true\n          description: ID of the server task to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mcafee-rest\n    description: REST adapter for McAfee ePO API.\n    resources:\n    - path: /core.help\n      name: corehelp\n      operations:\n      - method: GET\n        name: corehelp\n        description: McAfee List available API commands\n        call: mcafee.corehelp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system.find\n\
  \      name: systemfind\n      operations:\n      - method: GET\n        name: systemfind\n        description: McAfee Search for systems\n        call: mcafee.systemfind\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system.findTag\n      name: systemfindtag\n      operations:\n      - method: GET\n        name: systemfindtag\n        description: McAfee Find systems by tag\n        call: mcafee.systemfindtag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system.applyTag\n      name: systemapplytag\n      operations:\n      - method: POST\n        name: systemapplytag\n        description: McAfee Apply a tag to systems\n        call: mcafee.systemapplytag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system.clearTag\n      name: systemcleartag\n      operations:\n      - method: POST\n        name: systemcleartag\n        description: McAfee Remove a tag from systems\n\
  \        call: mcafee.systemcleartag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /epogroup.find\n      name: epogroupfind\n      operations:\n      - method: GET\n        name: epogroupfind\n        description: McAfee Find system tree groups\n        call: mcafee.epogroupfind\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /epogroup.moveSystem\n      name: epogroupmovesystem\n      operations:\n      - method: POST\n        name: epogroupmovesystem\n        description: McAfee Move a system to a different group\n        call: mcafee.epogroupmovesystem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policy.find\n      name: policyfind\n      operations:\n      - method: GET\n        name: policyfind\n        description: McAfee Search for policies\n        call: mcafee.policyfind\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /policy.assignToSystem\n      name: policyassigntosystem\n      operations:\n      - method: POST\n        name: policyassigntosystem\n        description: McAfee Assign a policy to a system\n        call: mcafee.policyassigntosystem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policy.assignToGroup\n      name: policyassigntogroup\n      operations:\n      - method: POST\n        name: policyassigntogroup\n        description: McAfee Assign a policy to a group\n        call: mcafee.policyassigntogroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clienttask.find\n      name: clienttaskfind\n      operations:\n      - method: GET\n        name: clienttaskfind\n        description: McAfee Search for client tasks\n        call: mcafee.clienttaskfind\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clienttask.run\n      name: clienttaskrun\n      operations:\n     \
  \ - method: POST\n        name: clienttaskrun\n        description: McAfee Run a client task on systems\n        call: mcafee.clienttaskrun\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /core.executeQuery\n      name: coreexecutequery\n      operations:\n      - method: GET\n        name: coreexecutequery\n        description: McAfee Execute a saved query\n        call: mcafee.coreexecutequery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /core.listQueries\n      name: corelistqueries\n      operations:\n      - method: GET\n        name: corelistqueries\n        description: McAfee List saved queries\n        call: mcafee.corelistqueries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /detectedsystem.find\n      name: detectedsystemfind\n      operations:\n      - method: GET\n        name: detectedsystemfind\n        description: McAfee Find threat events\n       \
  \ call: mcafee.detectedsystemfind\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repository.findPackages\n      name: repositoryfindpackages\n      operations:\n      - method: GET\n        name: repositoryfindpackages\n        description: McAfee Find software packages\n        call: mcafee.repositoryfindpackages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scheduler.listServerTasks\n      name: schedulerlistservertasks\n      operations:\n      - method: GET\n        name: schedulerlistservertasks\n        description: McAfee List server tasks\n        call: mcafee.schedulerlistservertasks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scheduler.runServerTask\n      name: schedulerrunservertask\n      operations:\n      - method: POST\n        name: schedulerrunservertask\n        description: McAfee Run a server task\n        call: mcafee.schedulerrunservertask\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mcafee-mcp\n    transport: http\n    description: MCP adapter for McAfee ePO API for AI agent use.\n    tools:\n    - name: corehelp\n      description: McAfee List available API commands\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mcafee.corehelp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: systemfind\n      description: McAfee Search for systems\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mcafee.systemfind\n      with:\n        searchText: tools.searchText\n      inputParameters:\n      - name: searchText\n        type: string\n        description: Search string to match against system names, IP addresses, or other properties\n        required: true\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: systemfindtag\n      description: McAfee Find systems by tag\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mcafee.systemfindtag\n      with:\n        tagName: tools.tagName\n      inputParameters:\n      - name: tagName\n        type: string\n        description: Name of the tag to search for\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: systemapplytag\n      description: McAfee Apply a tag to systems\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mcafee.systemapplytag\n      with:\n        names: tools.names\n        tagName: tools.tagName\n      inputParameters:\n      - name: names\n        type: string\n        description: Comma-separated list of system names or IDs\n        required: true\n      - name: tagName\n        type: string\n        description: Name of the tag to apply\n      \
  \  required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: systemcleartag\n      description: McAfee Remove a tag from systems\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mcafee.systemcleartag\n      with:\n        names: tools.names\n        tagName: tools.tagName\n      inputParameters:\n      - name: names\n        type: string\n        description: Comma-separated list of system names or IDs\n        required: true\n      - name: tagName\n        type: string\n        description: Name of the tag to remove\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: epogroupfind\n      description: McAfee Find system tree groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mcafee.epogroupfind\n      with:\n        searchText: tools.searchText\n      inputParameters:\n      - name:\
  \ searchText\n        type: string\n        description: Search string to match against group names\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: epogroupmovesystem\n      description: McAfee Move a system to a different group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mcafee.epogroupmovesystem\n      with:\n        names: tools.names\n        parentGroupId: tools.parentGroupId\n      inputParameters:\n      - name: names\n        type: string\n        description: Comma-separated list of system names to move\n        required: true\n      - name: parentGroupId\n        type: integer\n        description: ID of the target parent group\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: policyfind\n      description: McAfee Search for policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n \
  \     call: mcafee.policyfind\n      with:\n        searchText: tools.searchText\n      inputParameters:\n      - name: searchText\n        type: string\n        description: Search string to match against policy names\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: policyassigntosystem\n      description: McAfee Assign a policy to a system\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mcafee.policyassigntosystem\n      with:\n        names: tools.names\n        productId: tools.productId\n        typeId: tools.typeId\n        objectId: tools.objectId\n      inputParameters:\n      - name: names\n        type: string\n        description: Comma-separated list of system names\n        required: true\n      - name: productId\n        type: string\n        description: Product ID for the policy\n        required: true\n      - name: typeId\n        type: string\n        description: Policy type ID\n\
  \        required: true\n      - name: objectId\n        type: integer\n        description: Policy object ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: policyassigntogroup\n      description: McAfee Assign a policy to a group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mcafee.policyassigntogroup\n      with:\n        groupId: tools.groupId\n        productId: tools.productId\n        typeId: tools.typeId\n        objectId: tools.objectId\n      inputParameters:\n      - name: groupId\n        type: integer\n        description: Target group ID\n        required: true\n      - name: productId\n        type: string\n        description: Product ID for the policy\n        required: true\n      - name: typeId\n        type: string\n        description: Policy type ID\n        required: true\n      - name: objectId\n        type: integer\n        description: Policy\
  \ object ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clienttaskfind\n      description: McAfee Search for client tasks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mcafee.clienttaskfind\n      with:\n        searchText: tools.searchText\n      inputParameters:\n      - name: searchText\n        type: string\n        description: Search string to match against task names\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clienttaskrun\n      description: McAfee Run a client task on systems\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mcafee.clienttaskrun\n      with:\n        names: tools.names\n        productId: tools.productId\n        taskId: tools.taskId\n      inputParameters:\n      - name: names\n        type: string\n        description: Comma-separated list of system\
  \ names\n        required: true\n      - name: productId\n        type: string\n        description: Product ID for the task\n        required: true\n      - name: taskId\n        type: integer\n        description: Client task ID to execute\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: coreexecutequery\n      description: McAfee Execute a saved query\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mcafee.coreexecutequery\n      with:\n        queryId: tools.queryId\n      inputParameters:\n      - name: queryId\n        type: integer\n        description: ID of the saved query to execute\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: corelistqueries\n      description: McAfee List saved queries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mcafee.corelistqueries\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: detectedsystemfind\n      description: McAfee Find threat events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mcafee.detectedsystemfind\n      with:\n        searchText: tools.searchText\n      inputParameters:\n      - name: searchText\n        type: string\n        description: Search text to filter threat events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: repositoryfindpackages\n      description: McAfee Find software packages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mcafee.repositoryfindpackages\n      with:\n        searchText: tools.searchText\n      inputParameters:\n      - name: searchText\n        type: string\n        description: Search string to filter packages\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: schedulerlistservertasks\n      description: McAfee List server tasks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mcafee.schedulerlistservertasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: schedulerrunservertask\n      description: McAfee Run a server task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mcafee.schedulerrunservertask\n      with:\n        taskId: tools.taskId\n      inputParameters:\n      - name: taskId\n        type: integer\n        description: ID of the server task to execute\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MCAFEE_USERNAME: MCAFEE_USERNAME\n    MCAFEE_PASSWORD: MCAFEE_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mcafee/refs/heads/main/capabilities/mcafee-capability.yaml
tags:
- Mcafee
- API
tools:
- description: McAfee List available API commands
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: corehelp
- description: McAfee Search for systems
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: systemfind
- description: McAfee Find systems by tag
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: systemfindtag
- description: McAfee Apply a tag to systems
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: systemapplytag
- description: McAfee Remove a tag from systems
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: systemcleartag
- description: McAfee Find system tree groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: epogroupfind
- description: McAfee Move a system to a different group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: epogroupmovesystem
- description: McAfee Search for policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: policyfind
- description: McAfee Assign a policy to a system
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: policyassigntosystem
- description: McAfee Assign a policy to a group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: policyassigntogroup
- description: McAfee Search for client tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: clienttaskfind
- description: McAfee Run a client task on systems
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: clienttaskrun
- description: McAfee Execute a saved query
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: coreexecutequery
- description: McAfee List saved queries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: corelistqueries
- description: McAfee Find threat events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: detectedsystemfind
- description: McAfee Find software packages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: repositoryfindpackages
- description: McAfee List server tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: schedulerlistservertasks
- description: McAfee Run a server task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: schedulerrunservertask
---
