---
categories: []
consumed_apis: []
description: RESTful API for Juniper Apstra, an intent-based networking platform for automating data center network design, deployment, and operations. Apstra abstracts network infrastructure into design blueprints with logical models, rack types, templates, and connectivity. The platform continuously validates that the network state matches the intended configuration and raises anomalies when deviations occur. The API provides full access to design resources, blueprints, device management, telemetry, and IBA (Intent-Based Analytics) probes. Authentication uses token-based sessions obtained via the login e
layout: capability
name: Juniper Networks Juniper Apstra Intent-Based Networking API
operations:
- description: Juniper Networks Authenticate and obtain token
  method: POST
  name: login
  path: /aaa/login
- description: Juniper Networks Logout and invalidate token
  method: POST
  name: logout
  path: /aaa/logout
- description: Juniper Networks List logical devices
  method: GET
  name: listlogicaldevices
  path: /design/logical-devices
- description: Juniper Networks Create logical device
  method: POST
  name: createlogicaldevice
  path: /design/logical-devices
- description: Juniper Networks List interface maps
  method: GET
  name: listinterfacemaps
  path: /design/interface-maps
- description: Juniper Networks List rack types
  method: GET
  name: listracktypes
  path: /design/rack-types
- description: Juniper Networks Create rack type
  method: POST
  name: createracktype
  path: /design/rack-types
- description: Juniper Networks List templates
  method: GET
  name: listtemplates
  path: /design/templates
- description: Juniper Networks List blueprints
  method: GET
  name: listblueprints
  path: /blueprints
- description: Juniper Networks Create blueprint
  method: POST
  name: createblueprint
  path: /blueprints
- description: Juniper Networks Get blueprint
  method: GET
  name: getblueprint
  path: /blueprints/{blueprint_id}
- description: Juniper Networks Delete blueprint
  method: DELETE
  name: deleteblueprint
  path: /blueprints/{blueprint_id}
- description: Juniper Networks Deploy blueprint
  method: PUT
  name: deployblueprint
  path: /blueprints/{blueprint_id}/deploy
- description: Juniper Networks List blueprint anomalies
  method: GET
  name: listblueprintanomalies
  path: /blueprints/{blueprint_id}/anomalies
- description: Juniper Networks List security zones (VRFs)
  method: GET
  name: listsecurityzones
  path: /blueprints/{blueprint_id}/security-zones
- description: Juniper Networks List virtual networks
  method: GET
  name: listvirtualnetworks
  path: /blueprints/{blueprint_id}/virtual-networks
- description: Juniper Networks List ASN pools
  method: GET
  name: listasnpools
  path: /resources/asn-pools
- description: Juniper Networks Create ASN pool
  method: POST
  name: createasnpool
  path: /resources/asn-pools
- description: Juniper Networks List IP pools
  method: GET
  name: listippools
  path: /resources/ip-pools
- description: Juniper Networks List VNI pools
  method: GET
  name: listvnipools
  path: /resources/vni-pools
- description: Juniper Networks List managed systems
  method: GET
  name: listsystems
  path: /systems
- description: Juniper Networks Get system details
  method: GET
  name: getsystem
  path: /systems/{system_id}
- description: Juniper Networks List IBA probes
  method: GET
  name: listibaprobes
  path: /blueprints/{blueprint_id}/iba/probes
personas: []
provider_name: Juniper Networks
provider_slug: juniper-networks
search_terms:
- networking
- createracktype
- getsystem
- listippools
- juniper networks list interface maps
- juniper networks list virtual networks
- listtemplates
- juniper networks list blueprints
- juniper networks authenticate and obtain token
- juniper networks list iba probes
- createblueprint
- listsystems
- cloud
- juniper networks delete blueprint
- juniper networks list vni pools
- juniper networks list templates
- security
- enterprise
- sdn
- listblueprintanomalies
- listibaprobes
- juniper networks list logical devices
- juniper networks list ip pools
- deleteblueprint
- juniper networks get blueprint
- juniper networks list rack types
- juniper networks list blueprint anomalies
- juniper networks list security zones (vrfs)
- deployblueprint
- listvirtualnetworks
- login
- juniper networks list managed systems
- data center
- api
- listlogicaldevices
- listblueprints
- juniper networks create rack type
- createlogicaldevice
- networks
- juniper networks deploy blueprint
- listsecurityzones
- juniper networks get system details
- listracktypes
- juniper networks create logical device
- logout
- listasnpools
- listvnipools
- juniper networks list asn pools
- juniper
- listinterfacemaps
- juniper networks create blueprint
- getblueprint
- createasnpool
- juniper networks create asn pool
- juniper networks logout and invalidate token
- automation
slug: juniper-networks-capability
source_filename: juniper-networks-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Juniper Networks Juniper Apstra Intent-Based Networking API\n  description: RESTful API for Juniper Apstra, an intent-based networking platform for automating data center network design,\n    deployment, and operations. Apstra abstracts network infrastructure into design blueprints with logical models, rack types,\n    templates, and connectivity. The platform continuously validates that the network state matches the intended configuration\n    and raises anomalies when deviations occur. The API provides full access to design resources, blueprints, device management,\n    telemetry, and IBA (Intent-Based Analytics) probes. Authentication uses token-based sessions obtained via the login e\n  tags:\n  - Juniper\n  - Networks\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: juniper-networks\n    baseUri: https://apstra.example.com/api\n    description: Juniper Networks Juniper\
  \ Apstra Intent-Based Networking API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: AuthToken\n      value: '{{JUNIPER_NETWORKS_TOKEN}}'\n    resources:\n    - name: aaa-login\n      path: /aaa/login\n      operations:\n      - name: login\n        method: POST\n        description: Juniper Networks Authenticate and obtain token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: aaa-logout\n      path: /aaa/logout\n      operations:\n      - name: logout\n        method: POST\n        description: Juniper Networks Logout and invalidate token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: design-logical-devices\n      path: /design/logical-devices\n      operations:\n      - name: listlogicaldevices\n        method: GET\n        description: Juniper Networks List logical devices\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlogicaldevice\n        method: POST\n        description: Juniper Networks Create logical device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: design-interface-maps\n      path: /design/interface-maps\n      operations:\n      - name: listinterfacemaps\n        method: GET\n        description: Juniper Networks List interface maps\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: design-rack-types\n      path: /design/rack-types\n      operations:\n      - name: listracktypes\n        method: GET\n        description: Juniper Networks List rack types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n   \
  \       value: $.\n      - name: createracktype\n        method: POST\n        description: Juniper Networks Create rack type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: design-templates\n      path: /design/templates\n      operations:\n      - name: listtemplates\n        method: GET\n        description: Juniper Networks List templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints\n      path: /blueprints\n      operations:\n      - name: listblueprints\n        method: GET\n        description: Juniper Networks List blueprints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createblueprint\n        method: POST\n        description: Juniper Networks Create blueprint\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints-blueprint-id\n      path: /blueprints/{blueprint_id}\n      operations:\n      - name: getblueprint\n        method: GET\n        description: Juniper Networks Get blueprint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteblueprint\n        method: DELETE\n        description: Juniper Networks Delete blueprint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints-blueprint-id-deploy\n      path: /blueprints/{blueprint_id}/deploy\n      operations:\n      - name: deployblueprint\n        method: PUT\n        description: Juniper Networks Deploy blueprint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n    - name: blueprints-blueprint-id-anomalies\n      path: /blueprints/{blueprint_id}/anomalies\n      operations:\n      - name: listblueprintanomalies\n        method: GET\n        description: Juniper Networks List blueprint anomalies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints-blueprint-id-security-zones\n      path: /blueprints/{blueprint_id}/security-zones\n      operations:\n      - name: listsecurityzones\n        method: GET\n        description: Juniper Networks List security zones (VRFs)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints-blueprint-id-virtual-networks\n      path: /blueprints/{blueprint_id}/virtual-networks\n      operations:\n      - name: listvirtualnetworks\n        method: GET\n        description: Juniper Networks List virtual networks\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resources-asn-pools\n      path: /resources/asn-pools\n      operations:\n      - name: listasnpools\n        method: GET\n        description: Juniper Networks List ASN pools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createasnpool\n        method: POST\n        description: Juniper Networks Create ASN pool\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resources-ip-pools\n      path: /resources/ip-pools\n      operations:\n      - name: listippools\n        method: GET\n        description: Juniper Networks List IP pools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ resources-vni-pools\n      path: /resources/vni-pools\n      operations:\n      - name: listvnipools\n        method: GET\n        description: Juniper Networks List VNI pools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: systems\n      path: /systems\n      operations:\n      - name: listsystems\n        method: GET\n        description: Juniper Networks List managed systems\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: systems-system-id\n      path: /systems/{system_id}\n      operations:\n      - name: getsystem\n        method: GET\n        description: Juniper Networks Get system details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints-blueprint-id-iba-probes\n      path: /blueprints/{blueprint_id}/iba/probes\n\
  \      operations:\n      - name: listibaprobes\n        method: GET\n        description: Juniper Networks List IBA probes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: juniper-networks-rest\n    description: REST adapter for Juniper Networks Juniper Apstra Intent-Based Networking API.\n    resources:\n    - path: /aaa/login\n      name: login\n      operations:\n      - method: POST\n        name: login\n        description: Juniper Networks Authenticate and obtain token\n        call: juniper-networks.login\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /aaa/logout\n      name: logout\n      operations:\n      - method: POST\n        name: logout\n        description: Juniper Networks Logout and invalidate token\n        call: juniper-networks.logout\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n    - path: /design/logical-devices\n      name: listlogicaldevices\n      operations:\n      - method: GET\n        name: listlogicaldevices\n        description: Juniper Networks List logical devices\n        call: juniper-networks.listlogicaldevices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /design/logical-devices\n      name: createlogicaldevice\n      operations:\n      - method: POST\n        name: createlogicaldevice\n        description: Juniper Networks Create logical device\n        call: juniper-networks.createlogicaldevice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /design/interface-maps\n      name: listinterfacemaps\n      operations:\n      - method: GET\n        name: listinterfacemaps\n        description: Juniper Networks List interface maps\n        call: juniper-networks.listinterfacemaps\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /design/rack-types\n      name: listracktypes\n      operations:\n      - method: GET\n        name: listracktypes\n        description: Juniper Networks List rack types\n        call: juniper-networks.listracktypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /design/rack-types\n      name: createracktype\n      operations:\n      - method: POST\n        name: createracktype\n        description: Juniper Networks Create rack type\n        call: juniper-networks.createracktype\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /design/templates\n      name: listtemplates\n      operations:\n      - method: GET\n        name: listtemplates\n        description: Juniper Networks List templates\n        call: juniper-networks.listtemplates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints\n      name: listblueprints\n      operations:\n      - method:\
  \ GET\n        name: listblueprints\n        description: Juniper Networks List blueprints\n        call: juniper-networks.listblueprints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints\n      name: createblueprint\n      operations:\n      - method: POST\n        name: createblueprint\n        description: Juniper Networks Create blueprint\n        call: juniper-networks.createblueprint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}\n      name: getblueprint\n      operations:\n      - method: GET\n        name: getblueprint\n        description: Juniper Networks Get blueprint\n        call: juniper-networks.getblueprint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}\n      name: deleteblueprint\n      operations:\n      - method: DELETE\n        name: deleteblueprint\n        description: Juniper Networks\
  \ Delete blueprint\n        call: juniper-networks.deleteblueprint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}/deploy\n      name: deployblueprint\n      operations:\n      - method: PUT\n        name: deployblueprint\n        description: Juniper Networks Deploy blueprint\n        call: juniper-networks.deployblueprint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}/anomalies\n      name: listblueprintanomalies\n      operations:\n      - method: GET\n        name: listblueprintanomalies\n        description: Juniper Networks List blueprint anomalies\n        call: juniper-networks.listblueprintanomalies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}/security-zones\n      name: listsecurityzones\n      operations:\n      - method: GET\n        name: listsecurityzones\n        description:\
  \ Juniper Networks List security zones (VRFs)\n        call: juniper-networks.listsecurityzones\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}/virtual-networks\n      name: listvirtualnetworks\n      operations:\n      - method: GET\n        name: listvirtualnetworks\n        description: Juniper Networks List virtual networks\n        call: juniper-networks.listvirtualnetworks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resources/asn-pools\n      name: listasnpools\n      operations:\n      - method: GET\n        name: listasnpools\n        description: Juniper Networks List ASN pools\n        call: juniper-networks.listasnpools\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resources/asn-pools\n      name: createasnpool\n      operations:\n      - method: POST\n        name: createasnpool\n        description: Juniper Networks Create\
  \ ASN pool\n        call: juniper-networks.createasnpool\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resources/ip-pools\n      name: listippools\n      operations:\n      - method: GET\n        name: listippools\n        description: Juniper Networks List IP pools\n        call: juniper-networks.listippools\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resources/vni-pools\n      name: listvnipools\n      operations:\n      - method: GET\n        name: listvnipools\n        description: Juniper Networks List VNI pools\n        call: juniper-networks.listvnipools\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /systems\n      name: listsystems\n      operations:\n      - method: GET\n        name: listsystems\n        description: Juniper Networks List managed systems\n        call: juniper-networks.listsystems\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /systems/{system_id}\n      name: getsystem\n      operations:\n      - method: GET\n        name: getsystem\n        description: Juniper Networks Get system details\n        call: juniper-networks.getsystem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}/iba/probes\n      name: listibaprobes\n      operations:\n      - method: GET\n        name: listibaprobes\n        description: Juniper Networks List IBA probes\n        call: juniper-networks.listibaprobes\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: juniper-networks-mcp\n    transport: http\n    description: MCP adapter for Juniper Networks Juniper Apstra Intent-Based Networking API for AI agent use.\n    tools:\n    - name: login\n      description: Juniper Networks Authenticate and obtain token\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: juniper-networks.login\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: logout\n      description: Juniper Networks Logout and invalidate token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: juniper-networks.logout\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlogicaldevices\n      description: Juniper Networks List logical devices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper-networks.listlogicaldevices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createlogicaldevice\n      description: Juniper Networks Create logical device\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: juniper-networks.createlogicaldevice\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: listinterfacemaps\n      description: Juniper Networks List interface maps\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper-networks.listinterfacemaps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listracktypes\n      description: Juniper Networks List rack types\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper-networks.listracktypes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createracktype\n      description: Juniper Networks Create rack type\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: juniper-networks.createracktype\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtemplates\n      description: Juniper Networks List templates\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: juniper-networks.listtemplates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listblueprints\n      description: Juniper Networks List blueprints\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper-networks.listblueprints\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createblueprint\n      description: Juniper Networks Create blueprint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: juniper-networks.createblueprint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getblueprint\n      description: Juniper Networks Get blueprint\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper-networks.getblueprint\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: deleteblueprint\n      description: Juniper Networks Delete blueprint\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: juniper-networks.deleteblueprint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployblueprint\n      description: Juniper Networks Deploy blueprint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: juniper-networks.deployblueprint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listblueprintanomalies\n      description: Juniper Networks List blueprint anomalies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper-networks.listblueprintanomalies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsecurityzones\n      description: Juniper Networks List security\
  \ zones (VRFs)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper-networks.listsecurityzones\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvirtualnetworks\n      description: Juniper Networks List virtual networks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper-networks.listvirtualnetworks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listasnpools\n      description: Juniper Networks List ASN pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper-networks.listasnpools\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createasnpool\n      description: Juniper Networks Create ASN pool\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: juniper-networks.createasnpool\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listippools\n      description: Juniper Networks List IP pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper-networks.listippools\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvnipools\n      description: Juniper Networks List VNI pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper-networks.listvnipools\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsystems\n      description: Juniper Networks List managed systems\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper-networks.listsystems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsystem\n      description: Juniper Networks Get system details\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper-networks.getsystem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listibaprobes\n      description: Juniper Networks List IBA probes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper-networks.listibaprobes\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    JUNIPER_NETWORKS_TOKEN: JUNIPER_NETWORKS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/juniper-networks/refs/heads/main/capabilities/juniper-networks-capability.yaml
tags:
- Juniper
- Networks
- API
tools:
- description: Juniper Networks Authenticate and obtain token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: login
- description: Juniper Networks Logout and invalidate token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: logout
- description: Juniper Networks List logical devices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlogicaldevices
- description: Juniper Networks Create logical device
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlogicaldevice
- description: Juniper Networks List interface maps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinterfacemaps
- description: Juniper Networks List rack types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listracktypes
- description: Juniper Networks Create rack type
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createracktype
- description: Juniper Networks List templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtemplates
- description: Juniper Networks List blueprints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listblueprints
- description: Juniper Networks Create blueprint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createblueprint
- description: Juniper Networks Get blueprint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getblueprint
- description: Juniper Networks Delete blueprint
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteblueprint
- description: Juniper Networks Deploy blueprint
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: deployblueprint
- description: Juniper Networks List blueprint anomalies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listblueprintanomalies
- description: Juniper Networks List security zones (VRFs)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsecurityzones
- description: Juniper Networks List virtual networks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvirtualnetworks
- description: Juniper Networks List ASN pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listasnpools
- description: Juniper Networks Create ASN pool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasnpool
- description: Juniper Networks List IP pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listippools
- description: Juniper Networks List VNI pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvnipools
- description: Juniper Networks List managed systems
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsystems
- description: Juniper Networks Get system details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsystem
- description: Juniper Networks List IBA probes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listibaprobes
---
