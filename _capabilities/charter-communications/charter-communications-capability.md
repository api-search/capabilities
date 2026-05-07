---
categories: []
consumed_apis: []
description: Bryte IQ is a Network-as-a-Service (NaaS) API platform launched by Charter Communications and CableLabs, providing secure API access to network capabilities based on the CAMARA project.
layout: capability
name: Charter Communications Bryte IQ API
operations:
- description: Get Connected Devices
  method: GET
  name: getconnecteddevices
  path: /network/devices
- description: Get Network Status
  method: GET
  name: getnetworkstatus
  path: /network/status
personas: []
provider_name: Charter Communications
provider_slug: charter-communications
search_terms:
- get network status
- camara
- spectrum
- charter
- get connected devices
- getnetworkstatus
- broadband
- cable
- enterprise
- network as a service
- ticketing
- api
- telecommunications
- naas
- getconnecteddevices
- communications
slug: charter-communications-capability
source_filename: charter-communications-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Charter Communications Bryte IQ API\n  description: Bryte IQ is a Network-as-a-Service (NaaS) API platform launched by Charter Communications and CableLabs, providing\n    secure API access to network capabilities based on the CAMARA project.\n  tags:\n  - Charter\n  - Communications\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: charter-communications\n    baseUri: https://api.charter.com\n    description: Charter Communications Bryte IQ API HTTP API.\n    resources:\n    - name: network-devices\n      path: /network/devices\n      operations:\n      - name: getconnecteddevices\n        method: GET\n        description: Get Connected Devices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: network-status\n      path: /network/status\n      operations:\n      - name: getnetworkstatus\n\
  \        method: GET\n        description: Get Network Status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: charter-communications-rest\n    description: REST adapter for Charter Communications Bryte IQ API.\n    resources:\n    - path: /network/devices\n      name: getconnecteddevices\n      operations:\n      - method: GET\n        name: getconnecteddevices\n        description: Get Connected Devices\n        call: charter-communications.getconnecteddevices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /network/status\n      name: getnetworkstatus\n      operations:\n      - method: GET\n        name: getnetworkstatus\n        description: Get Network Status\n        call: charter-communications.getnetworkstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n   \
  \ port: 9090\n    namespace: charter-communications-mcp\n    transport: http\n    description: MCP adapter for Charter Communications Bryte IQ API for AI agent use.\n    tools:\n    - name: getconnecteddevices\n      description: Get Connected Devices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charter-communications.getconnecteddevices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnetworkstatus\n      description: Get Network Status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charter-communications.getnetworkstatus\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/charter-communications/refs/heads/main/capabilities/charter-communications-capability.yaml
tags:
- Charter
- Communications
- API
tools:
- description: Get Connected Devices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconnecteddevices
- description: Get Network Status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnetworkstatus
---
