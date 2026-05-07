---
categories: []
consumed_apis: []
description: PTC ThingWorx REST API provides programmatic access to the ThingWorx IoT platform including thing management, property read/write, service execution, event subscription, and mashup data APIs using Application Key or OAuth authentication. ThingWorx is PTC's industrial IoT platform for digital twin and connected factory applications.
layout: capability
name: PTC ThingWorx REST API
operations:
- description: List things
  method: GET
  name: listthings
  path: /Things
- description: Get a thing
  method: GET
  name: getthing
  path: /Things/{thingName}
- description: Get all thing properties
  method: GET
  name: getthingproperties
  path: /Things/{thingName}/Properties
- description: Get a thing property
  method: GET
  name: getthingproperty
  path: /Things/{thingName}/Properties/{propertyName}
- description: Set a thing property
  method: PUT
  name: setthingproperty
  path: /Things/{thingName}/Properties/{propertyName}
- description: Query property history
  method: GET
  name: querypropertyhistory
  path: /Things/{thingName}/Properties/{propertyName}/QueryPropertyHistory
- description: Execute a thing service
  method: POST
  name: executeservice
  path: /Things/{thingName}/Services/{serviceName}
- description: List thing events
  method: GET
  name: getthingevents
  path: /Things/{thingName}/Events
- description: Query event history
  method: GET
  name: geteventhistory
  path: /Things/{thingName}/EventHistory
- description: List thing templates
  method: GET
  name: listthingtemplates
  path: /ThingTemplates
- description: Get a data shape
  method: GET
  name: getdatashape
  path: /DataShapes/{dataShapeName}
personas: []
provider_name: ptc-thingworx
provider_slug: ptc-thingworx
search_terms:
- query event history
- list things
- getdatashape
- getthingproperties
- listthings
- api
- execute a thing service
- ptc
- geteventhistory
- getthing
- get a thing
- listthingtemplates
- get all thing properties
- get a thing property
- executeservice
- thingworx
- set a thing property
- getthingproperty
- query property history
- getthingevents
- setthingproperty
- list thing events
- querypropertyhistory
- list thing templates
- get a data shape
slug: ptc-thingworx-capability
source_filename: ptc-thingworx-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PTC ThingWorx REST API\n  description: PTC ThingWorx REST API provides programmatic access to the ThingWorx IoT platform including thing management,\n    property read/write, service execution, event subscription, and mashup data APIs using Application Key or OAuth authentication.\n    ThingWorx is PTC's industrial IoT platform for digital twin and connected factory applications.\n  tags:\n  - Ptc\n  - Thingworx\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ptc-thingworx\n    baseUri: https://thingworx.example.com/Thingworx\n    description: PTC ThingWorx REST API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: appKey\n      value: '{{PTC_THINGWORX_TOKEN}}'\n    resources:\n    - name: things\n      path: /Things\n      operations:\n      - name: listthings\n        method: GET\n        description: List things\n        inputParameters:\n\
  \        - name: maxItems\n          in: query\n          type: integer\n          description: Maximum number of things to return\n        - name: nameMask\n          in: query\n          type: string\n          description: Name filter using % as wildcard\n        - name: tags\n          in: query\n          type: string\n          description: Tag-based filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: things-thingname\n      path: /Things/{thingName}\n      operations:\n      - name: getthing\n        method: GET\n        description: Get a thing\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: things-thingname-properties\n      path: /Things/{thingName}/Properties\n      operations:\n      - name: getthingproperties\n        method: GET\n        description: Get all thing properties\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: things-thingname-properties-propertyname\n      path: /Things/{thingName}/Properties/{propertyName}\n      operations:\n      - name: getthingproperty\n        method: GET\n        description: Get a thing property\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setthingproperty\n        method: PUT\n        description: Set a thing property\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: things-thingname-properties-propertyname-querypr\n      path: /Things/{thingName}/Properties/{propertyName}/QueryPropertyHistory\n      operations:\n      - name: querypropertyhistory\n        method: GET\n        description: Query property history\n        inputParameters:\n        - name: startDate\n \
  \         in: query\n          type: integer\n          description: Start of time range (epoch milliseconds)\n        - name: endDate\n          in: query\n          type: integer\n          description: End of time range (epoch milliseconds)\n        - name: maxItems\n          in: query\n          type: integer\n        - name: query\n          in: query\n          type: string\n          description: JSON query expression for filtering\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: things-thingname-services-servicename\n      path: /Things/{thingName}/Services/{serviceName}\n      operations:\n      - name: executeservice\n        method: POST\n        description: Execute a thing service\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: things-thingname-events\n      path: /Things/{thingName}/Events\n      operations:\n      - name: getthingevents\n        method: GET\n        description: List thing events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: things-thingname-eventhistory\n      path: /Things/{thingName}/EventHistory\n      operations:\n      - name: geteventhistory\n        method: GET\n        description: Query event history\n        inputParameters:\n        - name: startDate\n          in: query\n          type: integer\n        - name: endDate\n          in: query\n          type: integer\n        - name: maxItems\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: thingtemplates\n      path: /ThingTemplates\n\
  \      operations:\n      - name: listthingtemplates\n        method: GET\n        description: List thing templates\n        inputParameters:\n        - name: maxItems\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datashapes-datashapename\n      path: /DataShapes/{dataShapeName}\n      operations:\n      - name: getdatashape\n        method: GET\n        description: Get a data shape\n        inputParameters:\n        - name: dataShapeName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ptc-thingworx-rest\n    description: REST adapter for PTC ThingWorx REST API.\n    resources:\n    - path: /Things\n      name: listthings\n      operations:\n\
  \      - method: GET\n        name: listthings\n        description: List things\n        call: ptc-thingworx.listthings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Things/{thingName}\n      name: getthing\n      operations:\n      - method: GET\n        name: getthing\n        description: Get a thing\n        call: ptc-thingworx.getthing\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Things/{thingName}/Properties\n      name: getthingproperties\n      operations:\n      - method: GET\n        name: getthingproperties\n        description: Get all thing properties\n        call: ptc-thingworx.getthingproperties\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Things/{thingName}/Properties/{propertyName}\n      name: getthingproperty\n      operations:\n      - method: GET\n        name: getthingproperty\n        description: Get a thing property\n        call: ptc-thingworx.getthingproperty\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Things/{thingName}/Properties/{propertyName}\n      name: setthingproperty\n      operations:\n      - method: PUT\n        name: setthingproperty\n        description: Set a thing property\n        call: ptc-thingworx.setthingproperty\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Things/{thingName}/Properties/{propertyName}/QueryPropertyHistory\n      name: querypropertyhistory\n      operations:\n      - method: GET\n        name: querypropertyhistory\n        description: Query property history\n        call: ptc-thingworx.querypropertyhistory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Things/{thingName}/Services/{serviceName}\n      name: executeservice\n      operations:\n      - method: POST\n        name: executeservice\n        description: Execute a thing service\n        call: ptc-thingworx.executeservice\n\
  \        with:\n          serviceName: rest.serviceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Things/{thingName}/Events\n      name: getthingevents\n      operations:\n      - method: GET\n        name: getthingevents\n        description: List thing events\n        call: ptc-thingworx.getthingevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Things/{thingName}/EventHistory\n      name: geteventhistory\n      operations:\n      - method: GET\n        name: geteventhistory\n        description: Query event history\n        call: ptc-thingworx.geteventhistory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ThingTemplates\n      name: listthingtemplates\n      operations:\n      - method: GET\n        name: listthingtemplates\n        description: List thing templates\n        call: ptc-thingworx.listthingtemplates\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /DataShapes/{dataShapeName}\n      name: getdatashape\n      operations:\n      - method: GET\n        name: getdatashape\n        description: Get a data shape\n        call: ptc-thingworx.getdatashape\n        with:\n          dataShapeName: rest.dataShapeName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ptc-thingworx-mcp\n    transport: http\n    description: MCP adapter for PTC ThingWorx REST API for AI agent use.\n    tools:\n    - name: listthings\n      description: List things\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ptc-thingworx.listthings\n      with:\n        maxItems: tools.maxItems\n        nameMask: tools.nameMask\n        tags: tools.tags\n      inputParameters:\n      - name: maxItems\n        type: integer\n        description: Maximum number of things to return\n      - name: nameMask\n\
  \        type: string\n        description: Name filter using % as wildcard\n      - name: tags\n        type: string\n        description: Tag-based filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getthing\n      description: Get a thing\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ptc-thingworx.getthing\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getthingproperties\n      description: Get all thing properties\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ptc-thingworx.getthingproperties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getthingproperty\n      description: Get a thing property\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ptc-thingworx.getthingproperty\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: setthingproperty\n      description: Set a thing property\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: ptc-thingworx.setthingproperty\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: querypropertyhistory\n      description: Query property history\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ptc-thingworx.querypropertyhistory\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n        maxItems: tools.maxItems\n        query: tools.query\n      inputParameters:\n      - name: startDate\n        type: integer\n        description: Start of time range (epoch milliseconds)\n      - name: endDate\n        type: integer\n        description: End of time range (epoch milliseconds)\n      - name: maxItems\n        type: integer\n        description: maxItems\n      - name:\
  \ query\n        type: string\n        description: JSON query expression for filtering\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: executeservice\n      description: Execute a thing service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ptc-thingworx.executeservice\n      with:\n        serviceName: tools.serviceName\n      inputParameters:\n      - name: serviceName\n        type: string\n        description: Service name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getthingevents\n      description: List thing events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ptc-thingworx.getthingevents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: geteventhistory\n      description: Query event history\n      hints:\n        readOnly: true\n      \
  \  destructive: false\n        idempotent: true\n      call: ptc-thingworx.geteventhistory\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n        maxItems: tools.maxItems\n      inputParameters:\n      - name: startDate\n        type: integer\n        description: startDate\n      - name: endDate\n        type: integer\n        description: endDate\n      - name: maxItems\n        type: integer\n        description: maxItems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listthingtemplates\n      description: List thing templates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ptc-thingworx.listthingtemplates\n      with:\n        maxItems: tools.maxItems\n      inputParameters:\n      - name: maxItems\n        type: integer\n        description: maxItems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdatashape\n      description:\
  \ Get a data shape\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ptc-thingworx.getdatashape\n      with:\n        dataShapeName: tools.dataShapeName\n      inputParameters:\n      - name: dataShapeName\n        type: string\n        description: dataShapeName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PTC_THINGWORX_TOKEN: PTC_THINGWORX_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ptc-thingworx/refs/heads/main/capabilities/ptc-thingworx-capability.yaml
tags:
- Ptc
- Thingworx
- API
tools:
- description: List things
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listthings
- description: Get a thing
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getthing
- description: Get all thing properties
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getthingproperties
- description: Get a thing property
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getthingproperty
- description: Set a thing property
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setthingproperty
- description: Query property history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: querypropertyhistory
- description: Execute a thing service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executeservice
- description: List thing events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getthingevents
- description: Query event history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteventhistory
- description: List thing templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listthingtemplates
- description: Get a data shape
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatashape
---
