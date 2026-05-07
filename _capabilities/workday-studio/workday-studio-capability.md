---
categories: []
consumed_apis: []
description: API for building and deploying custom integrations using Workday Studio, an Eclipse-based IDE that provides a graphical development environment with drag-and-drop reusable components for creating sophisticated integrations with flow control, data transformation, error handling, and scripting. Enables programmatic management of integration systems, events, assemblies, and launch parameters within the Workday platform.
layout: capability
name: Workday Studio Integration API
operations:
- description: Workday Studio List Integration Systems
  method: GET
  name: listintegrationsystems
  path: /integrationSystems
- description: Workday Studio Retrieve a Specific Integration System
  method: GET
  name: getintegrationsystem
  path: /integrationSystems/{ID}
- description: Workday Studio Launch an Integration System
  method: POST
  name: launchintegration
  path: /integrationSystems/{ID}/launch
- description: Workday Studio List Integration Events
  method: GET
  name: listintegrationevents
  path: /integrationEvents
- description: Workday Studio Retrieve a Specific Integration Event
  method: GET
  name: getintegrationevent
  path: /integrationEvents/{ID}
- description: Workday Studio Retrieve Logs for an Integration Event
  method: GET
  name: getintegrationeventlogs
  path: /integrationEvents/{ID}/logs
- description: Workday Studio List Integration Assemblies
  method: GET
  name: listintegrationassemblies
  path: /integrationAssemblies
- description: Workday Studio Retrieve a Specific Integration Assembly
  method: GET
  name: getintegrationassembly
  path: /integrationAssemblies/{ID}
- description: Workday Studio List Integration Templates
  method: GET
  name: listintegrationtemplates
  path: /integrationTemplates
- description: Workday Studio Retrieve a Specific Integration Template
  method: GET
  name: getintegrationtemplate
  path: /integrationTemplates/{ID}
- description: Workday Studio List Available Launch Parameters
  method: GET
  name: listlaunchparameters
  path: /launchParameters
personas: []
provider_name: Workday Studio
provider_slug: workday-studio
search_terms:
- getintegrationtemplate
- launchintegration
- listintegrationassemblies
- getintegrationeventlogs
- api
- workday studio list integration templates
- getintegrationevent
- workday
- workday studio retrieve a specific integration assembly
- getintegrationassembly
- workday studio retrieve a specific integration system
- workday studio list available launch parameters
- listintegrationevents
- workday studio list integration events
- integration
- hr
- ide
- finance
- listintegrationsystems
- workday studio retrieve a specific integration event
- enterprise
- getintegrationsystem
- studio
- development
- cloud
- workday studio retrieve logs for an integration event
- workday studio launch an integration system
- workday studio retrieve a specific integration template
- workday studio list integration assemblies
- workday studio list integration systems
- listintegrationtemplates
- listlaunchparameters
slug: workday-studio-capability
source_filename: workday-studio-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Studio Integration API\n  description: API for building and deploying custom integrations using Workday Studio, an Eclipse-based IDE that provides\n    a graphical development environment with drag-and-drop reusable components for creating sophisticated integrations with\n    flow control, data transformation, error handling, and scripting. Enables programmatic management of integration systems,\n    events, assemblies, and launch parameters within the Workday platform.\n  tags:\n  - Workday\n  - Studio\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: workday-studio\n    baseUri: https://wd2-impl-services1.workday.com/ccx/service/tenant\n    description: Workday Studio Integration API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_STUDIO_TOKEN}}'\n    resources:\n    - name: integrationsystems\n      path: /integrationSystems\n   \
  \   operations:\n      - name: listintegrationsystems\n        method: GET\n        description: Workday Studio List Integration Systems\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrationsystems-id\n      path: /integrationSystems/{ID}\n      operations:\n      - name: getintegrationsystem\n        method: GET\n        description: Workday Studio Retrieve a Specific Integration System\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrationsystems-id-launch\n      path: /integrationSystems/{ID}/launch\n      operations:\n      - name: launchintegration\n        method: POST\n        description: Workday Studio Launch an Integration System\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrationevents\n\
  \      path: /integrationEvents\n      operations:\n      - name: listintegrationevents\n        method: GET\n        description: Workday Studio List Integration Events\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter events by execution status\n        - name: fromDate\n          in: query\n          type: string\n          description: Filter events starting from this date\n        - name: toDate\n          in: query\n          type: string\n          description: Filter events up to this date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrationevents-id\n      path: /integrationEvents/{ID}\n      operations:\n      - name: getintegrationevent\n        method: GET\n        description: Workday Studio Retrieve a Specific Integration Event\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: integrationevents-id-logs\n      path: /integrationEvents/{ID}/logs\n      operations:\n      - name: getintegrationeventlogs\n        method: GET\n        description: Workday Studio Retrieve Logs for an Integration Event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrationassemblies\n      path: /integrationAssemblies\n      operations:\n      - name: listintegrationassemblies\n        method: GET\n        description: Workday Studio List Integration Assemblies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrationassemblies-id\n      path: /integrationAssemblies/{ID}\n      operations:\n      - name: getintegrationassembly\n        method: GET\n        description: Workday Studio Retrieve a Specific Integration Assembly\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrationtemplates\n      path: /integrationTemplates\n      operations:\n      - name: listintegrationtemplates\n        method: GET\n        description: Workday Studio List Integration Templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrationtemplates-id\n      path: /integrationTemplates/{ID}\n      operations:\n      - name: getintegrationtemplate\n        method: GET\n        description: Workday Studio Retrieve a Specific Integration Template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: launchparameters\n      path: /launchParameters\n      operations:\n      - name: listlaunchparameters\n        method: GET\n        description: Workday Studio List\
  \ Available Launch Parameters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workday-studio-rest\n    description: REST adapter for Workday Studio Integration API.\n    resources:\n    - path: /integrationSystems\n      name: listintegrationsystems\n      operations:\n      - method: GET\n        name: listintegrationsystems\n        description: Workday Studio List Integration Systems\n        call: workday-studio.listintegrationsystems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integrationSystems/{ID}\n      name: getintegrationsystem\n      operations:\n      - method: GET\n        name: getintegrationsystem\n        description: Workday Studio Retrieve a Specific Integration System\n        call: workday-studio.getintegrationsystem\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /integrationSystems/{ID}/launch\n      name: launchintegration\n      operations:\n      - method: POST\n        name: launchintegration\n        description: Workday Studio Launch an Integration System\n        call: workday-studio.launchintegration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integrationEvents\n      name: listintegrationevents\n      operations:\n      - method: GET\n        name: listintegrationevents\n        description: Workday Studio List Integration Events\n        call: workday-studio.listintegrationevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integrationEvents/{ID}\n      name: getintegrationevent\n      operations:\n      - method: GET\n        name: getintegrationevent\n        description: Workday Studio Retrieve a Specific Integration Event\n        call: workday-studio.getintegrationevent\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n    - path: /integrationEvents/{ID}/logs\n      name: getintegrationeventlogs\n      operations:\n      - method: GET\n        name: getintegrationeventlogs\n        description: Workday Studio Retrieve Logs for an Integration Event\n        call: workday-studio.getintegrationeventlogs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integrationAssemblies\n      name: listintegrationassemblies\n      operations:\n      - method: GET\n        name: listintegrationassemblies\n        description: Workday Studio List Integration Assemblies\n        call: workday-studio.listintegrationassemblies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integrationAssemblies/{ID}\n      name: getintegrationassembly\n      operations:\n      - method: GET\n        name: getintegrationassembly\n        description: Workday Studio Retrieve a Specific Integration Assembly\n        call: workday-studio.getintegrationassembly\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integrationTemplates\n      name: listintegrationtemplates\n      operations:\n      - method: GET\n        name: listintegrationtemplates\n        description: Workday Studio List Integration Templates\n        call: workday-studio.listintegrationtemplates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integrationTemplates/{ID}\n      name: getintegrationtemplate\n      operations:\n      - method: GET\n        name: getintegrationtemplate\n        description: Workday Studio Retrieve a Specific Integration Template\n        call: workday-studio.getintegrationtemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /launchParameters\n      name: listlaunchparameters\n      operations:\n      - method: GET\n        name: listlaunchparameters\n        description: Workday Studio List Available Launch Parameters\n        call:\
  \ workday-studio.listlaunchparameters\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: workday-studio-mcp\n    transport: http\n    description: MCP adapter for Workday Studio Integration API for AI agent use.\n    tools:\n    - name: listintegrationsystems\n      description: Workday Studio List Integration Systems\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-studio.listintegrationsystems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getintegrationsystem\n      description: Workday Studio Retrieve a Specific Integration System\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-studio.getintegrationsystem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: launchintegration\n      description: Workday Studio Launch an Integration\
  \ System\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: workday-studio.launchintegration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listintegrationevents\n      description: Workday Studio List Integration Events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-studio.listintegrationevents\n      with:\n        status: tools.status\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter events by execution status\n      - name: fromDate\n        type: string\n        description: Filter events starting from this date\n      - name: toDate\n        type: string\n        description: Filter events up to this date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getintegrationevent\n      description:\
  \ Workday Studio Retrieve a Specific Integration Event\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-studio.getintegrationevent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getintegrationeventlogs\n      description: Workday Studio Retrieve Logs for an Integration Event\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-studio.getintegrationeventlogs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listintegrationassemblies\n      description: Workday Studio List Integration Assemblies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-studio.listintegrationassemblies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getintegrationassembly\n      description: Workday Studio Retrieve a Specific Integration\
  \ Assembly\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-studio.getintegrationassembly\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listintegrationtemplates\n      description: Workday Studio List Integration Templates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-studio.listintegrationtemplates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getintegrationtemplate\n      description: Workday Studio Retrieve a Specific Integration Template\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-studio.getintegrationtemplate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlaunchparameters\n      description: Workday Studio List Available Launch Parameters\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: workday-studio.listlaunchparameters\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_STUDIO_TOKEN: WORKDAY_STUDIO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-studio/refs/heads/main/capabilities/workday-studio-capability.yaml
tags:
- Workday
- Studio
- API
tools:
- description: Workday Studio List Integration Systems
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listintegrationsystems
- description: Workday Studio Retrieve a Specific Integration System
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getintegrationsystem
- description: Workday Studio Launch an Integration System
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: launchintegration
- description: Workday Studio List Integration Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listintegrationevents
- description: Workday Studio Retrieve a Specific Integration Event
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getintegrationevent
- description: Workday Studio Retrieve Logs for an Integration Event
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getintegrationeventlogs
- description: Workday Studio List Integration Assemblies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listintegrationassemblies
- description: Workday Studio Retrieve a Specific Integration Assembly
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getintegrationassembly
- description: Workday Studio List Integration Templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listintegrationtemplates
- description: Workday Studio Retrieve a Specific Integration Template
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getintegrationtemplate
- description: Workday Studio List Available Launch Parameters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlaunchparameters
---
