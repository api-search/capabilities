---
categories: []
consumed_apis: []
description: API for endpoint detection and response, threat and vulnerability management, and automated investigation and remediation. Provides programmatic access to alerts, machines, and vulnerabilities managed by Microsoft Defender for Endpoint.
layout: capability
name: Microsoft Defender for Endpoint API
operations:
- description: Microsoft Defender List alerts
  method: GET
  name: listalerts
  path: /alerts
- description: Microsoft Defender Get alert by ID
  method: GET
  name: getalert
  path: /alerts/{alertId}
- description: Microsoft Defender Update alert
  method: PATCH
  name: updatealert
  path: /alerts/{alertId}
- description: Microsoft Defender List machines
  method: GET
  name: listmachines
  path: /machines
- description: Microsoft Defender Get machine by ID
  method: GET
  name: getmachine
  path: /machines/{machineId}
- description: Microsoft Defender List alerts for a machine
  method: GET
  name: listmachinealerts
  path: /machines/{machineId}/alerts
- description: Microsoft Defender List vulnerabilities for a machine
  method: GET
  name: listmachinevulnerabilities
  path: /machines/{machineId}/vulnerabilities
- description: Microsoft Defender List all vulnerabilities
  method: GET
  name: listvulnerabilities
  path: /vulnerabilities
- description: Microsoft Defender Get vulnerability by ID
  method: GET
  name: getvulnerability
  path: /vulnerabilities/{vulnerabilityId}
- description: Microsoft Defender List machines affected by a vulnerability
  method: GET
  name: listvulnerabilitymachinereferences
  path: /vulnerabilities/{vulnerabilityId}/machineReferences
personas: []
provider_name: Microsoft Defender
provider_slug: microsoft-defender
search_terms:
- microsoft defender list machines affected by a vulnerability
- getmachine
- microsoft defender update alert
- microsoft defender list vulnerabilities for a machine
- getvulnerability
- api
- listvulnerabilitymachinereferences
- listvulnerabilities
- listalerts
- getalert
- microsoft
- listmachinealerts
- microsoft defender get alert by id
- updatealert
- microsoft defender list machines
- microsoft defender list all vulnerabilities
- microsoft defender list alerts
- listmachines
- microsoft defender get vulnerability by id
- defender
- listmachinevulnerabilities
- microsoft defender list alerts for a machine
- microsoft defender get machine by id
slug: microsoft-defender-capability
source_filename: microsoft-defender-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Defender for Endpoint API\n  description: API for endpoint detection and response, threat and vulnerability management, and automated investigation and\n    remediation. Provides programmatic access to alerts, machines, and vulnerabilities managed by Microsoft Defender for Endpoint.\n  tags:\n  - Microsoft\n  - Defender\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-defender\n    baseUri: https://api.security.microsoft.com/api\n    description: Microsoft Defender for Endpoint API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_DEFENDER_TOKEN}}'\n    resources:\n    - name: alerts\n      path: /alerts\n      operations:\n      - name: listalerts\n        method: GET\n        description: Microsoft Defender List alerts\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n   \
  \       description: OData filter expression. Filterable properties include alertCreationTime, lastUpdateTime, incidentId,\n            investigationId, id, assignedTo, detectionSource, lastEven\n        - name: $top\n          in: query\n          type: integer\n          description: Maximum number of results to return (max 10,000).\n        - name: $skip\n          in: query\n          type: integer\n          description: Number of results to skip for pagination.\n        - name: $expand\n          in: query\n          type: string\n          description: Expand related entities. Supports expanding evidence.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts-alertid\n      path: /alerts/{alertId}\n      operations:\n      - name: getalert\n        method: GET\n        description: Microsoft Defender Get alert by ID\n        inputParameters:\n        - name: alertId\n          in: path\n\
  \          type: string\n          required: true\n          description: The unique identifier of the alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatealert\n        method: PATCH\n        description: Microsoft Defender Update alert\n        inputParameters:\n        - name: alertId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the alert to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: machines\n      path: /machines\n      operations:\n      - name: listmachines\n        method: GET\n        description: Microsoft Defender List machines\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n          description: OData filter expression. Filterable properties include\
  \ computerDnsName, id, version, deviceValue, aadDeviceId,\n            machineTags, lastSeen, exposureLevel, onboardingS\n        - name: $top\n          in: query\n          type: integer\n          description: Maximum number of results to return (max 10,000).\n        - name: $skip\n          in: query\n          type: integer\n          description: Number of results to skip for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: machines-machineid\n      path: /machines/{machineId}\n      operations:\n      - name: getmachine\n        method: GET\n        description: Microsoft Defender Get machine by ID\n        inputParameters:\n        - name: machineId\n          in: path\n          type: string\n          required: true\n          description: The device ID or computer name of the machine.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n    - name: machines-machineid-alerts\n      path: /machines/{machineId}/alerts\n      operations:\n      - name: listmachinealerts\n        method: GET\n        description: Microsoft Defender List alerts for a machine\n        inputParameters:\n        - name: machineId\n          in: path\n          type: string\n          required: true\n          description: The device ID of the machine.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: machines-machineid-vulnerabilities\n      path: /machines/{machineId}/vulnerabilities\n      operations:\n      - name: listmachinevulnerabilities\n        method: GET\n        description: Microsoft Defender List vulnerabilities for a machine\n        inputParameters:\n        - name: machineId\n          in: path\n          type: string\n          required: true\n          description: The device ID of the machine.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vulnerabilities\n      path: /vulnerabilities\n      operations:\n      - name: listvulnerabilities\n        method: GET\n        description: Microsoft Defender List all vulnerabilities\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n          description: OData filter expression. Filterable properties include id, name, description, cvssV3, publishedOn,\n            severity, and updatedOn.\n        - name: $top\n          in: query\n          type: integer\n          description: Maximum number of results to return (max 8,000).\n        - name: $skip\n          in: query\n          type: integer\n          description: Number of results to skip for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ vulnerabilities-vulnerabilityid\n      path: /vulnerabilities/{vulnerabilityId}\n      operations:\n      - name: getvulnerability\n        method: GET\n        description: Microsoft Defender Get vulnerability by ID\n        inputParameters:\n        - name: vulnerabilityId\n          in: path\n          type: string\n          required: true\n          description: The CVE identifier of the vulnerability.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vulnerabilities-vulnerabilityid-machinereference\n      path: /vulnerabilities/{vulnerabilityId}/machineReferences\n      operations:\n      - name: listvulnerabilitymachinereferences\n        method: GET\n        description: Microsoft Defender List machines affected by a vulnerability\n        inputParameters:\n        - name: vulnerabilityId\n          in: path\n          type: string\n          required: true\n          description: The CVE\
  \ identifier of the vulnerability.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-defender-rest\n    description: REST adapter for Microsoft Defender for Endpoint API.\n    resources:\n    - path: /alerts\n      name: listalerts\n      operations:\n      - method: GET\n        name: listalerts\n        description: Microsoft Defender List alerts\n        call: microsoft-defender.listalerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerts/{alertId}\n      name: getalert\n      operations:\n      - method: GET\n        name: getalert\n        description: Microsoft Defender Get alert by ID\n        call: microsoft-defender.getalert\n        with:\n          alertId: rest.alertId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerts/{alertId}\n      name:\
  \ updatealert\n      operations:\n      - method: PATCH\n        name: updatealert\n        description: Microsoft Defender Update alert\n        call: microsoft-defender.updatealert\n        with:\n          alertId: rest.alertId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /machines\n      name: listmachines\n      operations:\n      - method: GET\n        name: listmachines\n        description: Microsoft Defender List machines\n        call: microsoft-defender.listmachines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /machines/{machineId}\n      name: getmachine\n      operations:\n      - method: GET\n        name: getmachine\n        description: Microsoft Defender Get machine by ID\n        call: microsoft-defender.getmachine\n        with:\n          machineId: rest.machineId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /machines/{machineId}/alerts\n   \
  \   name: listmachinealerts\n      operations:\n      - method: GET\n        name: listmachinealerts\n        description: Microsoft Defender List alerts for a machine\n        call: microsoft-defender.listmachinealerts\n        with:\n          machineId: rest.machineId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /machines/{machineId}/vulnerabilities\n      name: listmachinevulnerabilities\n      operations:\n      - method: GET\n        name: listmachinevulnerabilities\n        description: Microsoft Defender List vulnerabilities for a machine\n        call: microsoft-defender.listmachinevulnerabilities\n        with:\n          machineId: rest.machineId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vulnerabilities\n      name: listvulnerabilities\n      operations:\n      - method: GET\n        name: listvulnerabilities\n        description: Microsoft Defender List all vulnerabilities\n        call:\
  \ microsoft-defender.listvulnerabilities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vulnerabilities/{vulnerabilityId}\n      name: getvulnerability\n      operations:\n      - method: GET\n        name: getvulnerability\n        description: Microsoft Defender Get vulnerability by ID\n        call: microsoft-defender.getvulnerability\n        with:\n          vulnerabilityId: rest.vulnerabilityId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vulnerabilities/{vulnerabilityId}/machineReferences\n      name: listvulnerabilitymachinereferences\n      operations:\n      - method: GET\n        name: listvulnerabilitymachinereferences\n        description: Microsoft Defender List machines affected by a vulnerability\n        call: microsoft-defender.listvulnerabilitymachinereferences\n        with:\n          vulnerabilityId: rest.vulnerabilityId\n        outputParameters:\n        - type: object\n        \
  \  mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-defender-mcp\n    transport: http\n    description: MCP adapter for Microsoft Defender for Endpoint API for AI agent use.\n    tools:\n    - name: listalerts\n      description: Microsoft Defender List alerts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-defender.listalerts\n      with:\n        $filter: tools.$filter\n        $top: tools.$top\n        $skip: tools.$skip\n        $expand: tools.$expand\n      inputParameters:\n      - name: $filter\n        type: string\n        description: OData filter expression. Filterable properties include alertCreationTime, lastUpdateTime, incidentId,\n          investigationId, id, assignedTo, detectionSource, lastEven\n      - name: $top\n        type: integer\n        description: Maximum number of results to return (max 10,000).\n      - name: $skip\n        type: integer\n        description: Number of\
  \ results to skip for pagination.\n      - name: $expand\n        type: string\n        description: Expand related entities. Supports expanding evidence.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getalert\n      description: Microsoft Defender Get alert by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-defender.getalert\n      with:\n        alertId: tools.alertId\n      inputParameters:\n      - name: alertId\n        type: string\n        description: The unique identifier of the alert.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatealert\n      description: Microsoft Defender Update alert\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-defender.updatealert\n      with:\n        alertId: tools.alertId\n      inputParameters:\n      - name: alertId\n\
  \        type: string\n        description: The unique identifier of the alert to update.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmachines\n      description: Microsoft Defender List machines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-defender.listmachines\n      with:\n        $filter: tools.$filter\n        $top: tools.$top\n        $skip: tools.$skip\n      inputParameters:\n      - name: $filter\n        type: string\n        description: OData filter expression. Filterable properties include computerDnsName, id, version, deviceValue, aadDeviceId,\n          machineTags, lastSeen, exposureLevel, onboardingS\n      - name: $top\n        type: integer\n        description: Maximum number of results to return (max 10,000).\n      - name: $skip\n        type: integer\n        description: Number of results to skip for pagination.\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getmachine\n      description: Microsoft Defender Get machine by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-defender.getmachine\n      with:\n        machineId: tools.machineId\n      inputParameters:\n      - name: machineId\n        type: string\n        description: The device ID or computer name of the machine.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmachinealerts\n      description: Microsoft Defender List alerts for a machine\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-defender.listmachinealerts\n      with:\n        machineId: tools.machineId\n      inputParameters:\n      - name: machineId\n        type: string\n        description: The device ID of the machine.\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listmachinevulnerabilities\n      description: Microsoft Defender List vulnerabilities for a machine\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-defender.listmachinevulnerabilities\n      with:\n        machineId: tools.machineId\n      inputParameters:\n      - name: machineId\n        type: string\n        description: The device ID of the machine.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvulnerabilities\n      description: Microsoft Defender List all vulnerabilities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-defender.listvulnerabilities\n      with:\n        $filter: tools.$filter\n        $top: tools.$top\n        $skip: tools.$skip\n      inputParameters:\n      - name: $filter\n        type: string\n        description:\
  \ OData filter expression. Filterable properties include id, name, description, cvssV3, publishedOn, severity,\n          and updatedOn.\n      - name: $top\n        type: integer\n        description: Maximum number of results to return (max 8,000).\n      - name: $skip\n        type: integer\n        description: Number of results to skip for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvulnerability\n      description: Microsoft Defender Get vulnerability by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-defender.getvulnerability\n      with:\n        vulnerabilityId: tools.vulnerabilityId\n      inputParameters:\n      - name: vulnerabilityId\n        type: string\n        description: The CVE identifier of the vulnerability.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvulnerabilitymachinereferences\n\
  \      description: Microsoft Defender List machines affected by a vulnerability\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-defender.listvulnerabilitymachinereferences\n      with:\n        vulnerabilityId: tools.vulnerabilityId\n      inputParameters:\n      - name: vulnerabilityId\n        type: string\n        description: The CVE identifier of the vulnerability.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_DEFENDER_TOKEN: MICROSOFT_DEFENDER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-defender/refs/heads/main/capabilities/microsoft-defender-capability.yaml
tags:
- Microsoft
- Defender
- API
tools:
- description: Microsoft Defender List alerts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listalerts
- description: Microsoft Defender Get alert by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getalert
- description: Microsoft Defender Update alert
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatealert
- description: Microsoft Defender List machines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmachines
- description: Microsoft Defender Get machine by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmachine
- description: Microsoft Defender List alerts for a machine
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmachinealerts
- description: Microsoft Defender List vulnerabilities for a machine
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmachinevulnerabilities
- description: Microsoft Defender List all vulnerabilities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvulnerabilities
- description: Microsoft Defender Get vulnerability by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvulnerability
- description: Microsoft Defender List machines affected by a vulnerability
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvulnerabilitymachinereferences
---
