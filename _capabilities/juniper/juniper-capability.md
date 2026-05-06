---
categories: []
consumed_apis: []
description: Juniper Apstra is an intent-based networking platform for data center automation. The Apstra API provides RESTful access to manage blueprints, design elements, devices, connectivity templates, virtual networks, and intent-based analytics. It supports multivendor environments and enables closed-loop automation from design through deployment and operations.
layout: capability
name: Juniper Networks Juniper Apstra API
operations:
- description: Juniper Networks Authenticate user
  method: POST
  name: login
  path: /aaa/login
- description: Juniper Networks List all blueprints
  method: GET
  name: listblueprints
  path: /blueprints
- description: Juniper Networks Create a blueprint
  method: POST
  name: createblueprint
  path: /blueprints
- description: Juniper Networks Get blueprint details
  method: GET
  name: getblueprint
  path: /blueprints/{blueprint_id}
- description: Juniper Networks Update a blueprint
  method: PUT
  name: updateblueprint
  path: /blueprints/{blueprint_id}
- description: Juniper Networks Delete a blueprint
  method: DELETE
  name: deleteblueprint
  path: /blueprints/{blueprint_id}
- description: Juniper Networks Deploy blueprint
  method: PUT
  name: deployblueprint
  path: /blueprints/{blueprint_id}/deploy
- description: Juniper Networks List blueprint nodes
  method: GET
  name: listblueprintnodes
  path: /blueprints/{blueprint_id}/nodes
- description: Juniper Networks List security zones (routing zones / VRFs)
  method: GET
  name: listsecurityzones
  path: /blueprints/{blueprint_id}/security-zones
- description: Juniper Networks Create security zone
  method: POST
  name: createsecurityzone
  path: /blueprints/{blueprint_id}/security-zones
- description: Juniper Networks List virtual networks
  method: GET
  name: listvirtualnetworks
  path: /blueprints/{blueprint_id}/virtual-networks
- description: Juniper Networks Create virtual network
  method: POST
  name: createvirtualnetwork
  path: /blueprints/{blueprint_id}/virtual-networks
- description: Juniper Networks List connectivity templates
  method: GET
  name: listconnectivitytemplates
  path: /blueprints/{blueprint_id}/connectivity-templates
- description: Juniper Networks List blueprint anomalies
  method: GET
  name: listblueprintanomalies
  path: /blueprints/{blueprint_id}/anomalies
- description: Juniper Networks List IBA dashboards
  method: GET
  name: listibadashboards
  path: /blueprints/{blueprint_id}/iba/dashboards
- description: Juniper Networks List blueprint configlets
  method: GET
  name: listblueprintconfiglets
  path: /blueprints/{blueprint_id}/configlets
- description: Juniper Networks List rack types
  method: GET
  name: listracktypes
  path: /design/rack-types
- description: Juniper Networks Create rack type
  method: POST
  name: createracktype
  path: /design/rack-types
- description: Juniper Networks List design templates
  method: GET
  name: listdesigntemplates
  path: /design/templates
- description: Juniper Networks Create design template
  method: POST
  name: createdesigntemplate
  path: /design/templates
- description: Juniper Networks List logical devices
  method: GET
  name: listlogicaldevices
  path: /design/logical-devices
- description: Juniper Networks List interface maps
  method: GET
  name: listinterfacemaps
  path: /design/interface-maps
- description: Juniper Networks List design configlets
  method: GET
  name: listdesignconfiglets
  path: /design/configlets
- description: Juniper Networks Create design configlet
  method: POST
  name: createdesignconfiglet
  path: /design/configlets
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
- description: Juniper Networks Create IP pool
  method: POST
  name: createippool
  path: /resources/ip-pools
- description: Juniper Networks List VNI pools
  method: GET
  name: listvnipools
  path: /resources/vni-pools
- description: Juniper Networks Create VNI pool
  method: POST
  name: createvnipool
  path: /resources/vni-pools
- description: Juniper Networks List system agents
  method: GET
  name: listsystemagents
  path: /system-agents
- description: Juniper Networks Create system agent
  method: POST
  name: createsystemagent
  path: /system-agents
- description: Juniper Networks List managed systems
  method: GET
  name: listsystems
  path: /systems
personas: []
provider_name: Juniper Networks
provider_slug: juniper
search_terms:
- networking
- createracktype
- listconnectivitytemplates
- updateblueprint
- juniper networks list design templates
- createdesignconfiglet
- listippools
- listsystemagents
- listdesigntemplates
- juniper networks list interface maps
- juniper networks list virtual networks
- juniper networks list connectivity templates
- listdesignconfiglets
- listblueprintnodes
- juniper networks authenticate user
- juniper networks list security zones (routing zones / vrfs)
- listibadashboards
- juniper networks update a blueprint
- createblueprint
- juniper networks create security zone
- juniper networks list design configlets
- listsystems
- cloud
- juniper networks create ip pool
- juniper networks list vni pools
- juniper networks create virtual network
- security
- enterprise
- sdn
- createsecurityzone
- juniper networks list system agents
- listblueprintanomalies
- juniper networks list managed systems
- ai
- juniper networks list logical devices
- juniper networks list ip pools
- juniper networks list all blueprints
- createsystemagent
- deleteblueprint
- juniper networks list blueprint anomalies
- listvirtualnetworks
- juniper networks list iba dashboards
- juniper networks list blueprint nodes
- juniper networks delete a blueprint
- deployblueprint
- login
- juniper networks list blueprint configlets
- juniper networks list rack types
- api
- createdesigntemplate
- listblueprints
- listlogicaldevices
- juniper networks create rack type
- listblueprintconfiglets
- juniper networks create system agent
- createippool
- juniper networks deploy blueprint
- listsecurityzones
- juniper networks create a blueprint
- createvirtualnetwork
- listracktypes
- juniper networks create design configlet
- listvnipools
- juniper networks get blueprint details
- listasnpools
- juniper networks list asn pools
- juniper
- listinterfacemaps
- createasnpool
- getblueprint
- juniper networks create design template
- juniper networks create asn pool
- juniper networks create vni pool
- createvnipool
- automation
slug: juniper-capability
source_filename: juniper-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Juniper Networks Juniper Apstra API\n  description: Juniper Apstra is an intent-based networking platform for data center automation. The Apstra API provides RESTful\n    access to manage blueprints, design elements, devices, connectivity templates, virtual networks, and intent-based analytics.\n    It supports multivendor environments and enables closed-loop automation from design through deployment and operations.\n  tags:\n  - Juniper\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: juniper\n    baseUri: https://apstra.example.com/api\n    description: Juniper Networks Juniper Apstra API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: AuthToken\n      value: '{{JUNIPER_TOKEN}}'\n    resources:\n    - name: aaa-login\n      path: /aaa/login\n      operations:\n      - name: login\n        method: POST\n        description: Juniper Networks\
  \ Authenticate user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints\n      path: /blueprints\n      operations:\n      - name: listblueprints\n        method: GET\n        description: Juniper Networks List all blueprints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createblueprint\n        method: POST\n        description: Juniper Networks Create a blueprint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints-blueprint-id\n      path: /blueprints/{blueprint_id}\n      operations:\n      - name: getblueprint\n        method: GET\n        description: Juniper Networks Get blueprint details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: updateblueprint\n        method: PUT\n        description: Juniper Networks Update a blueprint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteblueprint\n        method: DELETE\n        description: Juniper Networks Delete a blueprint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints-blueprint-id-deploy\n      path: /blueprints/{blueprint_id}/deploy\n      operations:\n      - name: deployblueprint\n        method: PUT\n        description: Juniper Networks Deploy blueprint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints-blueprint-id-nodes\n      path: /blueprints/{blueprint_id}/nodes\n      operations:\n      - name: listblueprintnodes\n        method:\
  \ GET\n        description: Juniper Networks List blueprint nodes\n        inputParameters:\n        - name: node_type\n          in: query\n          type: string\n          description: Filter by node type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints-blueprint-id-security-zones\n      path: /blueprints/{blueprint_id}/security-zones\n      operations:\n      - name: listsecurityzones\n        method: GET\n        description: Juniper Networks List security zones (routing zones / VRFs)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsecurityzone\n        method: POST\n        description: Juniper Networks Create security zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints-blueprint-id-virtual-networks\n\
  \      path: /blueprints/{blueprint_id}/virtual-networks\n      operations:\n      - name: listvirtualnetworks\n        method: GET\n        description: Juniper Networks List virtual networks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvirtualnetwork\n        method: POST\n        description: Juniper Networks Create virtual network\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints-blueprint-id-connectivity-templates\n      path: /blueprints/{blueprint_id}/connectivity-templates\n      operations:\n      - name: listconnectivitytemplates\n        method: GET\n        description: Juniper Networks List connectivity templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints-blueprint-id-anomalies\n\
  \      path: /blueprints/{blueprint_id}/anomalies\n      operations:\n      - name: listblueprintanomalies\n        method: GET\n        description: Juniper Networks List blueprint anomalies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints-blueprint-id-iba-dashboards\n      path: /blueprints/{blueprint_id}/iba/dashboards\n      operations:\n      - name: listibadashboards\n        method: GET\n        description: Juniper Networks List IBA dashboards\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blueprints-blueprint-id-configlets\n      path: /blueprints/{blueprint_id}/configlets\n      operations:\n      - name: listblueprintconfiglets\n        method: GET\n        description: Juniper Networks List blueprint configlets\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: design-rack-types\n      path: /design/rack-types\n      operations:\n      - name: listracktypes\n        method: GET\n        description: Juniper Networks List rack types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createracktype\n        method: POST\n        description: Juniper Networks Create rack type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: design-templates\n      path: /design/templates\n      operations:\n      - name: listdesigntemplates\n        method: GET\n        description: Juniper Networks List design templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdesigntemplate\n        method: POST\n        description:\
  \ Juniper Networks Create design template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: design-logical-devices\n      path: /design/logical-devices\n      operations:\n      - name: listlogicaldevices\n        method: GET\n        description: Juniper Networks List logical devices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: design-interface-maps\n      path: /design/interface-maps\n      operations:\n      - name: listinterfacemaps\n        method: GET\n        description: Juniper Networks List interface maps\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: design-configlets\n      path: /design/configlets\n      operations:\n      - name: listdesignconfiglets\n        method: GET\n        description: Juniper\
  \ Networks List design configlets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdesignconfiglet\n        method: POST\n        description: Juniper Networks Create design configlet\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resources-asn-pools\n      path: /resources/asn-pools\n      operations:\n      - name: listasnpools\n        method: GET\n        description: Juniper Networks List ASN pools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createasnpool\n        method: POST\n        description: Juniper Networks Create ASN pool\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resources-ip-pools\n      path:\
  \ /resources/ip-pools\n      operations:\n      - name: listippools\n        method: GET\n        description: Juniper Networks List IP pools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createippool\n        method: POST\n        description: Juniper Networks Create IP pool\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resources-vni-pools\n      path: /resources/vni-pools\n      operations:\n      - name: listvnipools\n        method: GET\n        description: Juniper Networks List VNI pools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvnipool\n        method: POST\n        description: Juniper Networks Create VNI pool\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: system-agents\n      path: /system-agents\n      operations:\n      - name: listsystemagents\n        method: GET\n        description: Juniper Networks List system agents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsystemagent\n        method: POST\n        description: Juniper Networks Create system agent\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: systems\n      path: /systems\n      operations:\n      - name: listsystems\n        method: GET\n        description: Juniper Networks List managed systems\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: juniper-rest\n    description: REST adapter for\
  \ Juniper Networks Juniper Apstra API.\n    resources:\n    - path: /aaa/login\n      name: login\n      operations:\n      - method: POST\n        name: login\n        description: Juniper Networks Authenticate user\n        call: juniper.login\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints\n      name: listblueprints\n      operations:\n      - method: GET\n        name: listblueprints\n        description: Juniper Networks List all blueprints\n        call: juniper.listblueprints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints\n      name: createblueprint\n      operations:\n      - method: POST\n        name: createblueprint\n        description: Juniper Networks Create a blueprint\n        call: juniper.createblueprint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}\n      name: getblueprint\n      operations:\n  \
  \    - method: GET\n        name: getblueprint\n        description: Juniper Networks Get blueprint details\n        call: juniper.getblueprint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}\n      name: updateblueprint\n      operations:\n      - method: PUT\n        name: updateblueprint\n        description: Juniper Networks Update a blueprint\n        call: juniper.updateblueprint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}\n      name: deleteblueprint\n      operations:\n      - method: DELETE\n        name: deleteblueprint\n        description: Juniper Networks Delete a blueprint\n        call: juniper.deleteblueprint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}/deploy\n      name: deployblueprint\n      operations:\n      - method: PUT\n        name: deployblueprint\n        description:\
  \ Juniper Networks Deploy blueprint\n        call: juniper.deployblueprint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}/nodes\n      name: listblueprintnodes\n      operations:\n      - method: GET\n        name: listblueprintnodes\n        description: Juniper Networks List blueprint nodes\n        call: juniper.listblueprintnodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}/security-zones\n      name: listsecurityzones\n      operations:\n      - method: GET\n        name: listsecurityzones\n        description: Juniper Networks List security zones (routing zones / VRFs)\n        call: juniper.listsecurityzones\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}/security-zones\n      name: createsecurityzone\n      operations:\n      - method: POST\n        name: createsecurityzone\n   \
  \     description: Juniper Networks Create security zone\n        call: juniper.createsecurityzone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}/virtual-networks\n      name: listvirtualnetworks\n      operations:\n      - method: GET\n        name: listvirtualnetworks\n        description: Juniper Networks List virtual networks\n        call: juniper.listvirtualnetworks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}/virtual-networks\n      name: createvirtualnetwork\n      operations:\n      - method: POST\n        name: createvirtualnetwork\n        description: Juniper Networks Create virtual network\n        call: juniper.createvirtualnetwork\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}/connectivity-templates\n      name: listconnectivitytemplates\n      operations:\n      - method:\
  \ GET\n        name: listconnectivitytemplates\n        description: Juniper Networks List connectivity templates\n        call: juniper.listconnectivitytemplates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}/anomalies\n      name: listblueprintanomalies\n      operations:\n      - method: GET\n        name: listblueprintanomalies\n        description: Juniper Networks List blueprint anomalies\n        call: juniper.listblueprintanomalies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}/iba/dashboards\n      name: listibadashboards\n      operations:\n      - method: GET\n        name: listibadashboards\n        description: Juniper Networks List IBA dashboards\n        call: juniper.listibadashboards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blueprints/{blueprint_id}/configlets\n      name: listblueprintconfiglets\n\
  \      operations:\n      - method: GET\n        name: listblueprintconfiglets\n        description: Juniper Networks List blueprint configlets\n        call: juniper.listblueprintconfiglets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /design/rack-types\n      name: listracktypes\n      operations:\n      - method: GET\n        name: listracktypes\n        description: Juniper Networks List rack types\n        call: juniper.listracktypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /design/rack-types\n      name: createracktype\n      operations:\n      - method: POST\n        name: createracktype\n        description: Juniper Networks Create rack type\n        call: juniper.createracktype\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /design/templates\n      name: listdesigntemplates\n      operations:\n      - method: GET\n        name: listdesigntemplates\n \
  \       description: Juniper Networks List design templates\n        call: juniper.listdesigntemplates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /design/templates\n      name: createdesigntemplate\n      operations:\n      - method: POST\n        name: createdesigntemplate\n        description: Juniper Networks Create design template\n        call: juniper.createdesigntemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /design/logical-devices\n      name: listlogicaldevices\n      operations:\n      - method: GET\n        name: listlogicaldevices\n        description: Juniper Networks List logical devices\n        call: juniper.listlogicaldevices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /design/interface-maps\n      name: listinterfacemaps\n      operations:\n      - method: GET\n        name: listinterfacemaps\n        description: Juniper Networks List\
  \ interface maps\n        call: juniper.listinterfacemaps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /design/configlets\n      name: listdesignconfiglets\n      operations:\n      - method: GET\n        name: listdesignconfiglets\n        description: Juniper Networks List design configlets\n        call: juniper.listdesignconfiglets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /design/configlets\n      name: createdesignconfiglet\n      operations:\n      - method: POST\n        name: createdesignconfiglet\n        description: Juniper Networks Create design configlet\n        call: juniper.createdesignconfiglet\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resources/asn-pools\n      name: listasnpools\n      operations:\n      - method: GET\n        name: listasnpools\n        description: Juniper Networks List ASN pools\n        call: juniper.listasnpools\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resources/asn-pools\n      name: createasnpool\n      operations:\n      - method: POST\n        name: createasnpool\n        description: Juniper Networks Create ASN pool\n        call: juniper.createasnpool\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resources/ip-pools\n      name: listippools\n      operations:\n      - method: GET\n        name: listippools\n        description: Juniper Networks List IP pools\n        call: juniper.listippools\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resources/ip-pools\n      name: createippool\n      operations:\n      - method: POST\n        name: createippool\n        description: Juniper Networks Create IP pool\n        call: juniper.createippool\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resources/vni-pools\n      name: listvnipools\n\
  \      operations:\n      - method: GET\n        name: listvnipools\n        description: Juniper Networks List VNI pools\n        call: juniper.listvnipools\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resources/vni-pools\n      name: createvnipool\n      operations:\n      - method: POST\n        name: createvnipool\n        description: Juniper Networks Create VNI pool\n        call: juniper.createvnipool\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system-agents\n      name: listsystemagents\n      operations:\n      - method: GET\n        name: listsystemagents\n        description: Juniper Networks List system agents\n        call: juniper.listsystemagents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system-agents\n      name: createsystemagent\n      operations:\n      - method: POST\n        name: createsystemagent\n        description: Juniper Networks\
  \ Create system agent\n        call: juniper.createsystemagent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /systems\n      name: listsystems\n      operations:\n      - method: GET\n        name: listsystems\n        description: Juniper Networks List managed systems\n        call: juniper.listsystems\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: juniper-mcp\n    transport: http\n    description: MCP adapter for Juniper Networks Juniper Apstra API for AI agent use.\n    tools:\n    - name: login\n      description: Juniper Networks Authenticate user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: juniper.login\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listblueprints\n      description: Juniper Networks List all blueprints\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: juniper.listblueprints\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createblueprint\n      description: Juniper Networks Create a blueprint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: juniper.createblueprint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getblueprint\n      description: Juniper Networks Get blueprint details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.getblueprint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateblueprint\n      description: Juniper Networks Update a blueprint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: juniper.updateblueprint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteblueprint\n\
  \      description: Juniper Networks Delete a blueprint\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: juniper.deleteblueprint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployblueprint\n      description: Juniper Networks Deploy blueprint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: juniper.deployblueprint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listblueprintnodes\n      description: Juniper Networks List blueprint nodes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.listblueprintnodes\n      with:\n        node_type: tools.node_type\n      inputParameters:\n      - name: node_type\n        type: string\n        description: Filter by node type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsecurityzones\n\
  \      description: Juniper Networks List security zones (routing zones / VRFs)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.listsecurityzones\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsecurityzone\n      description: Juniper Networks Create security zone\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: juniper.createsecurityzone\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvirtualnetworks\n      description: Juniper Networks List virtual networks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.listvirtualnetworks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createvirtualnetwork\n      description: Juniper Networks Create virtual network\n      hints:\n        readOnly: false\n \
  \       destructive: false\n        idempotent: false\n      call: juniper.createvirtualnetwork\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listconnectivitytemplates\n      description: Juniper Networks List connectivity templates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.listconnectivitytemplates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listblueprintanomalies\n      description: Juniper Networks List blueprint anomalies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.listblueprintanomalies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listibadashboards\n      description: Juniper Networks List IBA dashboards\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.listibadashboards\n  \
  \    outputParameters:\n      - type: object\n        mapping: $.\n    - name: listblueprintconfiglets\n      description: Juniper Networks List blueprint configlets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.listblueprintconfiglets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listracktypes\n      description: Juniper Networks List rack types\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.listracktypes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createracktype\n      description: Juniper Networks Create rack type\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: juniper.createracktype\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdesigntemplates\n      description: Juniper Networks List\
  \ design templates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.listdesigntemplates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdesigntemplate\n      description: Juniper Networks Create design template\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: juniper.createdesigntemplate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlogicaldevices\n      description: Juniper Networks List logical devices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.listlogicaldevices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinterfacemaps\n      description: Juniper Networks List interface maps\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ juniper.listinterfacemaps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdesignconfiglets\n      description: Juniper Networks List design configlets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.listdesignconfiglets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdesignconfiglet\n      description: Juniper Networks Create design configlet\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: juniper.createdesignconfiglet\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listasnpools\n      description: Juniper Networks List ASN pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.listasnpools\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createasnpool\n      description:\
  \ Juniper Networks Create ASN pool\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: juniper.createasnpool\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listippools\n      description: Juniper Networks List IP pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.listippools\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createippool\n      description: Juniper Networks Create IP pool\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: juniper.createippool\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvnipools\n      description: Juniper Networks List VNI pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.listvnipools\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createvnipool\n      description: Juniper Networks Create VNI pool\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: juniper.createvnipool\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsystemagents\n      description: Juniper Networks List system agents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: juniper.listsystemagents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsystemagent\n      description: Juniper Networks Create system agent\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: juniper.createsystemagent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsystems\n      description: Juniper Networks List managed systems\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: juniper.listsystems\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    JUNIPER_TOKEN: JUNIPER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/juniper/refs/heads/main/capabilities/juniper-capability.yaml
tags:
- Juniper
- API
tools:
- description: Juniper Networks Authenticate user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: login
- description: Juniper Networks List all blueprints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listblueprints
- description: Juniper Networks Create a blueprint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createblueprint
- description: Juniper Networks Get blueprint details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getblueprint
- description: Juniper Networks Update a blueprint
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateblueprint
- description: Juniper Networks Delete a blueprint
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
- description: Juniper Networks List blueprint nodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listblueprintnodes
- description: Juniper Networks List security zones (routing zones / VRFs)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsecurityzones
- description: Juniper Networks Create security zone
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsecurityzone
- description: Juniper Networks List virtual networks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvirtualnetworks
- description: Juniper Networks Create virtual network
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvirtualnetwork
- description: Juniper Networks List connectivity templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconnectivitytemplates
- description: Juniper Networks List blueprint anomalies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listblueprintanomalies
- description: Juniper Networks List IBA dashboards
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listibadashboards
- description: Juniper Networks List blueprint configlets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listblueprintconfiglets
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
- description: Juniper Networks List design templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdesigntemplates
- description: Juniper Networks Create design template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdesigntemplate
- description: Juniper Networks List logical devices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlogicaldevices
- description: Juniper Networks List interface maps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinterfacemaps
- description: Juniper Networks List design configlets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdesignconfiglets
- description: Juniper Networks Create design configlet
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdesignconfiglet
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
- description: Juniper Networks Create IP pool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createippool
- description: Juniper Networks List VNI pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvnipools
- description: Juniper Networks Create VNI pool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvnipool
- description: Juniper Networks List system agents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsystemagents
- description: Juniper Networks Create system agent
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsystemagent
- description: Juniper Networks List managed systems
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsystems
---
