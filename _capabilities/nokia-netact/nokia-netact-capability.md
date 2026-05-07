---
categories: []
consumed_apis: []
description: Nokia NetAct provides network element management APIs for telecom operators. APIs enable network topology discovery, performance monitoring, fault management, and configuration management across RAN, transport, and core network infrastructure. The NBI (Northbound Interface) exposes REST APIs for OSS/BSS integration.
layout: capability
name: Nokia NetAct Network Management Northbound Interface API
operations:
- description: List network elements
  method: GET
  name: listnetworkelements
  path: /topology/network-elements
- description: Get network element details
  method: GET
  name: getnetworkelement
  path: /topology/network-elements/{distinguishedName}
- description: Get child network elements
  method: GET
  name: getnetworkelementchildren
  path: /topology/network-elements/{distinguishedName}/children
- description: List active alarms
  method: GET
  name: listactivealarms
  path: /faults/alarms
- description: Get alarm details
  method: GET
  name: getalarm
  path: /faults/alarms/{alarmId}
- description: Acknowledge an alarm
  method: POST
  name: acknowledgealarm
  path: /faults/alarms/{alarmId}/acknowledge
- description: Get KPI performance counters
  method: GET
  name: getperformancekpis
  path: /performance/kpis
- description: Get managed object attributes
  method: GET
  name: getnetworkelementattributes
  path: /configuration/network-elements/{distinguishedName}/attributes
- description: Modify managed object attributes
  method: PATCH
  name: updatenetworkelementattributes
  path: /configuration/network-elements/{distinguishedName}/attributes
personas: []
provider_name: Nokia NetAct
provider_slug: nokia-netact
search_terms:
- list active alarms
- telecom
- getperformancekpis
- updatenetworkelementattributes
- getnetworkelementchildren
- api
- modify managed object attributes
- network management
- listactivealarms
- get network element details
- acknowledge an alarm
- getalarm
- get managed object attributes
- acknowledgealarm
- getnetworkelementattributes
- get child network elements
- snmp
- listnetworkelements
- list network elements
- get alarm details
- netact
- get kpi performance counters
- oss
- getnetworkelement
- nokia
slug: nokia-netact-capability
source_filename: nokia-netact-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Nokia NetAct Network Management Northbound Interface API\n  description: Nokia NetAct provides network element management APIs for telecom operators. APIs enable network topology discovery,\n    performance monitoring, fault management, and configuration management across RAN, transport, and core network infrastructure.\n    The NBI (Northbound Interface) exposes REST APIs for OSS/BSS integration.\n  tags:\n  - Nokia\n  - Netact\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nokia-netact\n    baseUri: https://netact.example.com/api/v1\n    description: Nokia NetAct Network Management Northbound Interface API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{NOKIA_NETACT_TOKEN}}'\n    resources:\n    - name: topology-network-elements\n      path: /topology/network-elements\n      operations:\n      - name: listnetworkelements\n        method: GET\n\
  \        description: List network elements\n        inputParameters:\n        - name: neType\n          in: query\n          type: string\n          description: Network element type (e.g., BTS, NodeB, eNodeB, gNodeB, BSC, RNC, MSC)\n        - name: technology\n          in: query\n          type: string\n        - name: vendor\n          in: query\n          type: string\n          description: Network equipment vendor name\n        - name: operationalState\n          in: query\n          type: string\n        - name: administrativeState\n          in: query\n          type: string\n        - name: alarmState\n          in: query\n          type: string\n        - name: dnFilter\n          in: query\n          type: string\n          description: Distinguished Name prefix filter for topology subtree queries\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: topology-network-elements-distinguishedname\n      path: /topology/network-elements/{distinguishedName}\n      operations:\n      - name: getnetworkelement\n        method: GET\n        description: Get network element details\n        inputParameters:\n        - name: distinguishedName\n          in: path\n          type: string\n          required: true\n          description: DN of the network element (URL-encoded)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: topology-network-elements-distinguishedname-chil\n      path: /topology/network-elements/{distinguishedName}/children\n      operations:\n      - name: getnetworkelementchildren\n        method: GET\n        description: Get child network elements\n        inputParameters:\n        - name: distinguishedName\n          in: path\n     \
  \     type: string\n          required: true\n        - name: childClass\n          in: query\n          type: string\n          description: Filter by specific MO class name (e.g., LNCEL, WCEL, GCELL)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: faults-alarms\n      path: /faults/alarms\n      operations:\n      - name: listactivealarms\n        method: GET\n        description: List active alarms\n        inputParameters:\n        - name: severity\n          in: query\n          type: string\n        - name: neDn\n          in: query\n          type: string\n          description: Distinguished Name of the source NE\n        - name: alarmType\n          in: query\n          type: string\n        - name: fromTime\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: faults-alarms-alarmid\n      path: /faults/alarms/{alarmId}\n      operations:\n      - name: getalarm\n        method: GET\n        description: Get alarm details\n        inputParameters:\n        - name: alarmId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: faults-alarms-alarmid-acknowledge\n      path: /faults/alarms/{alarmId}/acknowledge\n      operations:\n      - name: acknowledgealarm\n        method: POST\n        description: Acknowledge an alarm\n        inputParameters:\n        - name: alarmId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: performance-kpis\n      path: /performance/kpis\n\
  \      operations:\n      - name: getperformancekpis\n        method: GET\n        description: Get KPI performance counters\n        inputParameters:\n        - name: neDn\n          in: query\n          type: string\n          required: true\n          description: DN of the network element or subtree root\n        - name: kpiGroup\n          in: query\n          type: string\n          description: KPI group name (e.g., ACCESSIBILITY, RETAINABILITY, TRAFFIC)\n        - name: granularity\n          in: query\n          type: string\n          description: Measurement granularity (ISO 8601 duration)\n        - name: startTime\n          in: query\n          type: string\n          required: true\n        - name: endTime\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration-network-elements-distinguishedname\n      path:\
  \ /configuration/network-elements/{distinguishedName}/attributes\n      operations:\n      - name: getnetworkelementattributes\n        method: GET\n        description: Get managed object attributes\n        inputParameters:\n        - name: distinguishedName\n          in: path\n          type: string\n          required: true\n        - name: attributes\n          in: query\n          type: string\n          description: Comma-separated list of attribute names to retrieve (all if omitted)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatenetworkelementattributes\n        method: PATCH\n        description: Modify managed object attributes\n        inputParameters:\n        - name: distinguishedName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nokia-netact-rest\n    description: REST adapter for Nokia NetAct Network Management Northbound Interface API.\n    resources:\n    - path: /topology/network-elements\n      name: listnetworkelements\n      operations:\n      - method: GET\n        name: listnetworkelements\n        description: List network elements\n        call: nokia-netact.listnetworkelements\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /topology/network-elements/{distinguishedName}\n      name: getnetworkelement\n      operations:\n      - method: GET\n        name: getnetworkelement\n        description: Get network element details\n        call: nokia-netact.getnetworkelement\n        with:\n          distinguishedName: rest.distinguishedName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /topology/network-elements/{distinguishedName}/children\n      name: getnetworkelementchildren\n\
  \      operations:\n      - method: GET\n        name: getnetworkelementchildren\n        description: Get child network elements\n        call: nokia-netact.getnetworkelementchildren\n        with:\n          distinguishedName: rest.distinguishedName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /faults/alarms\n      name: listactivealarms\n      operations:\n      - method: GET\n        name: listactivealarms\n        description: List active alarms\n        call: nokia-netact.listactivealarms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /faults/alarms/{alarmId}\n      name: getalarm\n      operations:\n      - method: GET\n        name: getalarm\n        description: Get alarm details\n        call: nokia-netact.getalarm\n        with:\n          alarmId: rest.alarmId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /faults/alarms/{alarmId}/acknowledge\n      name:\
  \ acknowledgealarm\n      operations:\n      - method: POST\n        name: acknowledgealarm\n        description: Acknowledge an alarm\n        call: nokia-netact.acknowledgealarm\n        with:\n          alarmId: rest.alarmId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /performance/kpis\n      name: getperformancekpis\n      operations:\n      - method: GET\n        name: getperformancekpis\n        description: Get KPI performance counters\n        call: nokia-netact.getperformancekpis\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /configuration/network-elements/{distinguishedName}/attributes\n      name: getnetworkelementattributes\n      operations:\n      - method: GET\n        name: getnetworkelementattributes\n        description: Get managed object attributes\n        call: nokia-netact.getnetworkelementattributes\n        with:\n          distinguishedName: rest.distinguishedName\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /configuration/network-elements/{distinguishedName}/attributes\n      name: updatenetworkelementattributes\n      operations:\n      - method: PATCH\n        name: updatenetworkelementattributes\n        description: Modify managed object attributes\n        call: nokia-netact.updatenetworkelementattributes\n        with:\n          distinguishedName: rest.distinguishedName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nokia-netact-mcp\n    transport: http\n    description: MCP adapter for Nokia NetAct Network Management Northbound Interface API for AI agent use.\n    tools:\n    - name: listnetworkelements\n      description: List network elements\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nokia-netact.listnetworkelements\n      with:\n        neType: tools.neType\n        technology: tools.technology\n\
  \        vendor: tools.vendor\n        operationalState: tools.operationalState\n        administrativeState: tools.administrativeState\n        alarmState: tools.alarmState\n        dnFilter: tools.dnFilter\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: neType\n        type: string\n        description: Network element type (e.g., BTS, NodeB, eNodeB, gNodeB, BSC, RNC, MSC)\n      - name: technology\n        type: string\n        description: technology\n      - name: vendor\n        type: string\n        description: Network equipment vendor name\n      - name: operationalState\n        type: string\n        description: operationalState\n      - name: administrativeState\n        type: string\n        description: administrativeState\n      - name: alarmState\n        type: string\n        description: alarmState\n      - name: dnFilter\n        type: string\n        description: Distinguished Name prefix filter for topology subtree queries\n\
  \      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnetworkelement\n      description: Get network element details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nokia-netact.getnetworkelement\n      with:\n        distinguishedName: tools.distinguishedName\n      inputParameters:\n      - name: distinguishedName\n        type: string\n        description: DN of the network element (URL-encoded)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnetworkelementchildren\n      description: Get child network elements\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nokia-netact.getnetworkelementchildren\n      with:\n        distinguishedName: tools.distinguishedName\n\
  \        childClass: tools.childClass\n      inputParameters:\n      - name: distinguishedName\n        type: string\n        description: distinguishedName\n        required: true\n      - name: childClass\n        type: string\n        description: Filter by specific MO class name (e.g., LNCEL, WCEL, GCELL)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listactivealarms\n      description: List active alarms\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nokia-netact.listactivealarms\n      with:\n        severity: tools.severity\n        neDn: tools.neDn\n        alarmType: tools.alarmType\n        fromTime: tools.fromTime\n        limit: tools.limit\n      inputParameters:\n      - name: severity\n        type: string\n        description: severity\n      - name: neDn\n        type: string\n        description: Distinguished Name of the source NE\n      - name: alarmType\n        type: string\n\
  \        description: alarmType\n      - name: fromTime\n        type: string\n        description: fromTime\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getalarm\n      description: Get alarm details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nokia-netact.getalarm\n      with:\n        alarmId: tools.alarmId\n      inputParameters:\n      - name: alarmId\n        type: string\n        description: alarmId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: acknowledgealarm\n      description: Acknowledge an alarm\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nokia-netact.acknowledgealarm\n      with:\n        alarmId: tools.alarmId\n      inputParameters:\n      - name: alarmId\n        type: string\n    \
  \    description: alarmId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getperformancekpis\n      description: Get KPI performance counters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nokia-netact.getperformancekpis\n      with:\n        neDn: tools.neDn\n        kpiGroup: tools.kpiGroup\n        granularity: tools.granularity\n        startTime: tools.startTime\n        endTime: tools.endTime\n      inputParameters:\n      - name: neDn\n        type: string\n        description: DN of the network element or subtree root\n        required: true\n      - name: kpiGroup\n        type: string\n        description: KPI group name (e.g., ACCESSIBILITY, RETAINABILITY, TRAFFIC)\n      - name: granularity\n        type: string\n        description: Measurement granularity (ISO 8601 duration)\n      - name: startTime\n        type: string\n        description: startTime\n    \
  \    required: true\n      - name: endTime\n        type: string\n        description: endTime\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnetworkelementattributes\n      description: Get managed object attributes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nokia-netact.getnetworkelementattributes\n      with:\n        distinguishedName: tools.distinguishedName\n        attributes: tools.attributes\n      inputParameters:\n      - name: distinguishedName\n        type: string\n        description: distinguishedName\n        required: true\n      - name: attributes\n        type: string\n        description: Comma-separated list of attribute names to retrieve (all if omitted)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatenetworkelementattributes\n      description: Modify managed object attributes\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: nokia-netact.updatenetworkelementattributes\n      with:\n        distinguishedName: tools.distinguishedName\n      inputParameters:\n      - name: distinguishedName\n        type: string\n        description: distinguishedName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NOKIA_NETACT_TOKEN: NOKIA_NETACT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nokia-netact/refs/heads/main/capabilities/nokia-netact-capability.yaml
tags:
- Nokia
- Netact
- API
tools:
- description: List network elements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnetworkelements
- description: Get network element details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnetworkelement
- description: Get child network elements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnetworkelementchildren
- description: List active alarms
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listactivealarms
- description: Get alarm details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getalarm
- description: Acknowledge an alarm
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: acknowledgealarm
- description: Get KPI performance counters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getperformancekpis
- description: Get managed object attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnetworkelementattributes
- description: Modify managed object attributes
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatenetworkelementattributes
---
