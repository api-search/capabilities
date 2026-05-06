---
categories: []
consumed_apis: []
description: Nected is a low-code workflow automation and decision engine platform. The API enables triggering of rules and workflows, listing and inspecting entities, managing global variables, retrieving audit logs, and checking usage.
layout: capability
name: Nected API
operations:
- description: Trigger a rule
  method: POST
  name: triggerrule
  path: /nected/rule/{ruleId}
- description: Trigger a workflow
  method: POST
  name: triggerworkflow
  path: /nected/workflow/{workflowId}
- description: Check usage
  method: GET
  name: checkusage
  path: /dev/usage
- description: Search audit logs
  method: GET
  name: searchauditlogs
  path: /dev/audit/audit/search
- description: Get audit log detail
  method: GET
  name: getauditlog
  path: /dev/audit/audit/{logId}
- description: List rules or workflows
  method: GET
  name: listentities
  path: /dev/{entityType}
- description: Get rule or workflow detail
  method: GET
  name: getentity
  path: /dev/{entityType}/{entityId}
- description: List global variables
  method: GET
  name: listglobalvariables
  path: /dev/variable
- description: Create a global variable
  method: POST
  name: createglobalvariable
  path: /dev/variable
- description: Get a global variable
  method: GET
  name: getglobalvariable
  path: /dev/variable/{name}
- description: Update a global variable
  method: PATCH
  name: updateglobalvariable
  path: /dev/variable/{name}
- description: Delete a global variable
  method: DELETE
  name: deleteglobalvariable
  path: /dev/variable/{name}
personas: []
provider_name: Nected
provider_slug: nected
search_terms:
- low-code
- decision engine
- getentity
- updateglobalvariable
- update a global variable
- deleteglobalvariable
- getauditlog
- check usage
- listentities
- trigger a rule
- createglobalvariable
- triggerworkflow
- get audit log detail
- list rules or workflows
- search audit logs
- get rule or workflow detail
- api
- workflow automation
- get a global variable
- checkusage
- triggerrule
- create a global variable
- list global variables
- trigger a workflow
- nected
- getglobalvariable
- listglobalvariables
- delete a global variable
- searchauditlogs
- business rules
slug: nected-capability
source_filename: nected-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Nected API\n  description: Nected is a low-code workflow automation and decision engine platform. The API enables triggering of rules\n    and workflows, listing and inspecting entities, managing global variables, retrieving audit logs, and checking usage.\n  tags:\n  - Nected\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nected\n    baseUri: https://api.nected.ai\n    description: Nected API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: nected-api-key\n      value: '{{NECTED_TOKEN}}'\n    resources:\n    - name: nected-rule-ruleid\n      path: /nected/rule/{ruleId}\n      operations:\n      - name: triggerrule\n        method: POST\n        description: Trigger a rule\n        inputParameters:\n        - name: ruleId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: nected-workflow-workflowid\n      path: /nected/workflow/{workflowId}\n      operations:\n      - name: triggerworkflow\n        method: POST\n        description: Trigger a workflow\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dev-usage\n      path: /dev/usage\n      operations:\n      - name: checkusage\n        method: GET\n        description: Check usage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dev-audit-audit-search\n      path: /dev/audit/audit/search\n      operations:\n      - name: searchauditlogs\n        method: GET\n        description: Search audit logs\n        inputParameters:\n\
  \        - name: pageNo\n          in: query\n          type: integer\n        - name: pageSize\n          in: query\n          type: integer\n        - name: search\n          in: query\n          type: string\n        - name: type\n          in: query\n          type: string\n        - name: event\n          in: query\n          type: string\n        - name: status\n          in: query\n          type: string\n        - name: startDate\n          in: query\n          type: string\n        - name: endDate\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dev-audit-audit-logid\n      path: /dev/audit/audit/{logId}\n      operations:\n      - name: getauditlog\n        method: GET\n        description: Get audit log detail\n        inputParameters:\n        - name: logId\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dev-entitytype\n      path: /dev/{entityType}\n      operations:\n      - name: listentities\n        method: GET\n        description: List rules or workflows\n        inputParameters:\n        - name: entityType\n          in: path\n          type: string\n          required: true\n        - name: page\n          in: query\n          type: integer\n        - name: perPage\n          in: query\n          type: integer\n        - name: sortBy\n          in: query\n          type: string\n        - name: sortDir\n          in: query\n          type: string\n        - name: status\n          in: query\n          type: string\n        - name: name\n          in: query\n          type: string\n        - name: type\n          in: query\n          type: string\n        - name: q\n          in: query\n          type: string\n        - name: tags\n          in: query\n          type:\
  \ string\n        - name: createdAtFrom\n          in: query\n          type: string\n        - name: createdAtTo\n          in: query\n          type: string\n        - name: updatedAtFrom\n          in: query\n          type: string\n        - name: updatedAtTo\n          in: query\n          type: string\n        - name: createdBy\n          in: query\n          type: string\n        - name: updatedBy\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dev-entitytype-entityid\n      path: /dev/{entityType}/{entityId}\n      operations:\n      - name: getentity\n        method: GET\n        description: Get rule or workflow detail\n        inputParameters:\n        - name: entityType\n          in: path\n          type: string\n          required: true\n        - name: entityId\n          in: path\n          type: string\n          required: true\n    \
  \    - name: view\n          in: query\n          type: string\n        - name: include\n          in: query\n          type: string\n        - name: version\n          in: query\n          type: string\n        - name: expand\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dev-variable\n      path: /dev/variable\n      operations:\n      - name: listglobalvariables\n        method: GET\n        description: List global variables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createglobalvariable\n        method: POST\n        description: Create a global variable\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dev-variable-name\n      path: /dev/variable/{name}\n   \
  \   operations:\n      - name: getglobalvariable\n        method: GET\n        description: Get a global variable\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateglobalvariable\n        method: PATCH\n        description: Update a global variable\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: checksum\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteglobalvariable\n        method: DELETE\n        description: Delete a global variable\n        inputParameters:\n        - name: name\n          in: path\n          type:\
  \ string\n          required: true\n        - name: checksum\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nected-rest\n    description: REST adapter for Nected API.\n    resources:\n    - path: /nected/rule/{ruleId}\n      name: triggerrule\n      operations:\n      - method: POST\n        name: triggerrule\n        description: Trigger a rule\n        call: nected.triggerrule\n        with:\n          ruleId: rest.ruleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nected/workflow/{workflowId}\n      name: triggerworkflow\n      operations:\n      - method: POST\n        name: triggerworkflow\n        description: Trigger a workflow\n        call: nected.triggerworkflow\n        with:\n          workflowId: rest.workflowId\n       \
  \ outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dev/usage\n      name: checkusage\n      operations:\n      - method: GET\n        name: checkusage\n        description: Check usage\n        call: nected.checkusage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dev/audit/audit/search\n      name: searchauditlogs\n      operations:\n      - method: GET\n        name: searchauditlogs\n        description: Search audit logs\n        call: nected.searchauditlogs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dev/audit/audit/{logId}\n      name: getauditlog\n      operations:\n      - method: GET\n        name: getauditlog\n        description: Get audit log detail\n        call: nected.getauditlog\n        with:\n          logId: rest.logId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dev/{entityType}\n      name: listentities\n     \
  \ operations:\n      - method: GET\n        name: listentities\n        description: List rules or workflows\n        call: nected.listentities\n        with:\n          entityType: rest.entityType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dev/{entityType}/{entityId}\n      name: getentity\n      operations:\n      - method: GET\n        name: getentity\n        description: Get rule or workflow detail\n        call: nected.getentity\n        with:\n          entityType: rest.entityType\n          entityId: rest.entityId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dev/variable\n      name: listglobalvariables\n      operations:\n      - method: GET\n        name: listglobalvariables\n        description: List global variables\n        call: nected.listglobalvariables\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dev/variable\n      name: createglobalvariable\n\
  \      operations:\n      - method: POST\n        name: createglobalvariable\n        description: Create a global variable\n        call: nected.createglobalvariable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dev/variable/{name}\n      name: getglobalvariable\n      operations:\n      - method: GET\n        name: getglobalvariable\n        description: Get a global variable\n        call: nected.getglobalvariable\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dev/variable/{name}\n      name: updateglobalvariable\n      operations:\n      - method: PATCH\n        name: updateglobalvariable\n        description: Update a global variable\n        call: nected.updateglobalvariable\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dev/variable/{name}\n      name: deleteglobalvariable\n\
  \      operations:\n      - method: DELETE\n        name: deleteglobalvariable\n        description: Delete a global variable\n        call: nected.deleteglobalvariable\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nected-mcp\n    transport: http\n    description: MCP adapter for Nected API for AI agent use.\n    tools:\n    - name: triggerrule\n      description: Trigger a rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nected.triggerrule\n      with:\n        ruleId: tools.ruleId\n      inputParameters:\n      - name: ruleId\n        type: string\n        description: ruleId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: triggerworkflow\n      description: Trigger a workflow\n      hints:\n        readOnly: false\n        destructive: false\n      \
  \  idempotent: false\n      call: nected.triggerworkflow\n      with:\n        workflowId: tools.workflowId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: workflowId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: checkusage\n      description: Check usage\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nected.checkusage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchauditlogs\n      description: Search audit logs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nected.searchauditlogs\n      with:\n        pageNo: tools.pageNo\n        pageSize: tools.pageSize\n        search: tools.search\n        type: tools.type\n        event: tools.event\n        status: tools.status\n        startDate: tools.startDate\n        endDate: tools.endDate\n\
  \      inputParameters:\n      - name: pageNo\n        type: integer\n        description: pageNo\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: search\n        type: string\n        description: search\n      - name: type\n        type: string\n        description: type\n      - name: event\n        type: string\n        description: event\n      - name: status\n        type: string\n        description: status\n      - name: startDate\n        type: string\n        description: startDate\n      - name: endDate\n        type: string\n        description: endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getauditlog\n      description: Get audit log detail\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nected.getauditlog\n      with:\n        logId: tools.logId\n      inputParameters:\n      - name: logId\n        type: string\n        description:\
  \ logId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listentities\n      description: List rules or workflows\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nected.listentities\n      with:\n        entityType: tools.entityType\n        page: tools.page\n        perPage: tools.perPage\n        sortBy: tools.sortBy\n        sortDir: tools.sortDir\n        status: tools.status\n        name: tools.name\n        type: tools.type\n        q: tools.q\n        tags: tools.tags\n        createdAtFrom: tools.createdAtFrom\n        createdAtTo: tools.createdAtTo\n        updatedAtFrom: tools.updatedAtFrom\n        updatedAtTo: tools.updatedAtTo\n        createdBy: tools.createdBy\n        updatedBy: tools.updatedBy\n      inputParameters:\n      - name: entityType\n        type: string\n        description: entityType\n        required: true\n      - name: page\n        type: integer\n\
  \        description: page\n      - name: perPage\n        type: integer\n        description: perPage\n      - name: sortBy\n        type: string\n        description: sortBy\n      - name: sortDir\n        type: string\n        description: sortDir\n      - name: status\n        type: string\n        description: status\n      - name: name\n        type: string\n        description: name\n      - name: type\n        type: string\n        description: type\n      - name: q\n        type: string\n        description: q\n      - name: tags\n        type: string\n        description: tags\n      - name: createdAtFrom\n        type: string\n        description: createdAtFrom\n      - name: createdAtTo\n        type: string\n        description: createdAtTo\n      - name: updatedAtFrom\n        type: string\n        description: updatedAtFrom\n      - name: updatedAtTo\n        type: string\n        description: updatedAtTo\n      - name: createdBy\n        type: string\n        description:\
  \ createdBy\n      - name: updatedBy\n        type: string\n        description: updatedBy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getentity\n      description: Get rule or workflow detail\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nected.getentity\n      with:\n        entityType: tools.entityType\n        entityId: tools.entityId\n        view: tools.view\n        include: tools.include\n        version: tools.version\n        expand: tools.expand\n      inputParameters:\n      - name: entityType\n        type: string\n        description: entityType\n        required: true\n      - name: entityId\n        type: string\n        description: entityId\n        required: true\n      - name: view\n        type: string\n        description: view\n      - name: include\n        type: string\n        description: include\n      - name: version\n        type: string\n        description: version\n\
  \      - name: expand\n        type: string\n        description: expand\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listglobalvariables\n      description: List global variables\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nected.listglobalvariables\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createglobalvariable\n      description: Create a global variable\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nected.createglobalvariable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getglobalvariable\n      description: Get a global variable\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nected.getglobalvariable\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n\
  \        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateglobalvariable\n      description: Update a global variable\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nected.updateglobalvariable\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteglobalvariable\n      description: Delete a global variable\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nected.deleteglobalvariable\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n\
  - namespace: env\n  keys:\n    NECTED_TOKEN: NECTED_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nected/refs/heads/main/capabilities/nected-capability.yaml
tags:
- Nected
- API
tools:
- description: Trigger a rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: triggerrule
- description: Trigger a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: triggerworkflow
- description: Check usage
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: checkusage
- description: Search audit logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchauditlogs
- description: Get audit log detail
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauditlog
- description: List rules or workflows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listentities
- description: Get rule or workflow detail
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getentity
- description: List global variables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listglobalvariables
- description: Create a global variable
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createglobalvariable
- description: Get a global variable
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getglobalvariable
- description: Update a global variable
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateglobalvariable
- description: Delete a global variable
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteglobalvariable
---
