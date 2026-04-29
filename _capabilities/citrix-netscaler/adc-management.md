---
categories: []
consumed_apis:
- nitro
description: Unified capability for managing Citrix NetScaler application delivery controllers, including load balancing, content switching, configuration management, and monitoring. Used by network administrators and platform engineers.
layout: capability
name: Citrix NetScaler ADC Management
operations:
- description: List all load balancing virtual servers
  method: GET
  name: list-lb-vservers
  path: /v1/lb-vservers
- description: Create a load balancing virtual server
  method: POST
  name: create-lb-vserver
  path: /v1/lb-vservers
- description: Get a specific load balancing virtual server
  method: GET
  name: get-lb-vserver
  path: /v1/lb-vservers/{name}
- description: Update a load balancing virtual server
  method: PUT
  name: update-lb-vserver
  path: /v1/lb-vservers/{name}
- description: Delete a load balancing virtual server
  method: DELETE
  name: delete-lb-vserver
  path: /v1/lb-vservers/{name}
- description: Get service bindings for an LB virtual server
  method: GET
  name: get-lb-vserver-service-bindings
  path: /v1/lb-vservers/{name}/bindings
- description: Bind a service to an LB virtual server
  method: POST
  name: bind-service-to-lb-vserver
  path: /v1/lb-vservers/{name}/bindings
- description: List all content switching virtual servers
  method: GET
  name: list-cs-vservers
  path: /v1/cs-vservers
- description: Create a content switching virtual server
  method: POST
  name: create-cs-vserver
  path: /v1/cs-vservers
- description: Get a content switching virtual server
  method: GET
  name: get-cs-vserver
  path: /v1/cs-vservers/{name}
- description: Update a content switching virtual server
  method: PUT
  name: update-cs-vserver
  path: /v1/cs-vservers/{name}
- description: Delete a content switching virtual server
  method: DELETE
  name: delete-cs-vserver
  path: /v1/cs-vservers/{name}
- description: Get NetScaler configuration
  method: GET
  name: get-ns-config
  path: /v1/config
- description: Save running configuration to disk
  method: POST
  name: save-ns-config
  path: /v1/config
- description: List statistics for all LB virtual servers
  method: GET
  name: list-lb-vserver-stats
  path: /v1/stats/lb-vservers
- description: Get statistics for an LB virtual server
  method: GET
  name: get-lb-vserver-stats
  path: /v1/stats/lb-vservers/{name}
- description: List statistics for all CS virtual servers
  method: GET
  name: list-cs-vserver-stats
  path: /v1/stats/cs-vservers
personas: []
provider_name: Citrix NetScaler
provider_slug: citrix-netscaler
search_terms:
- get a content switching virtual server
- web application firewall
- get service bindings for an lb virtual server
- get cs vserver stats
- application delivery controller
- get cs vserver
- ssl offloading
- adc management
- update a content switching virtual server
- create lb vserver
- update lb vserver
- unbind a service from a load balancing virtual server
- delete cs vserver
- single load balancing virtual server
- list cs vservers
- get details of a specific content switching virtual server
- bind a backend service to a load balancing virtual server
- appliance configuration
- get performance statistics for a specific lb virtual server
- list statistics for all cs virtual servers
- load balancing virtual servers
- single content switching virtual server
- netscaler
- load balancing
- get netscaler configuration
- unbind service from lb vserver
- list all content switching virtual servers
- save ns config
- list lb vservers
- get ns config
- content switching virtual servers
- citrix
- network administration
- delete a content switching virtual server
- content switching virtual server statistics
- list statistics for all content switching virtual servers
- get lb vserver
- get lb vserver stats
- get netscaler appliance configuration
- service bindings for a load balancing virtual server
- get statistics for a specific content switching virtual server
- delete lb vserver
- bind service to lb vserver
- list performance statistics for all lb virtual servers
- create cs vserver
- application security
- delete a load balancing virtual server
- create a load balancing virtual server
- get a specific load balancing virtual server
- list statistics for all lb virtual servers
- create a content switching virtual server
- load balancing virtual server statistics
- statistics for a specific lb virtual server
- get details of a specific load balancing virtual server
- update a load balancing virtual server
- list all load balancing virtual servers on the netscaler
- bind a service to an lb virtual server
- list all load balancing virtual servers
- save running configuration to disk
- api gateway
- list lb vserver stats
- update a load balancing virtual server configuration
- get all service bindings for a load balancing virtual server
- traffic management
- create a new load balancing virtual server
- get statistics for an lb virtual server
- get lb vserver service bindings
- update cs vserver
- save the running netscaler configuration to persistent storage
- list cs vserver stats
slug: adc-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Citrix NetScaler ADC Management\"\n  description: \"Unified capability for managing Citrix NetScaler application delivery controllers, including load balancing, content switching, configuration management, and monitoring. Used by network administrators and platform engineers.\"\n  tags:\n    - Citrix\n    - NetScaler\n    - Load Balancing\n    - ADC Management\n    - Network Administration\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      NETSCALER_USERNAME: NETSCALER_USERNAME\n      NETSCALER_PASSWORD: NETSCALER_PASSWORD\n\ncapability:\n  consumes:\n    - import: nitro\n      location: ./shared/nitro.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: adc-management-api\n      description: \"Unified REST API for Citrix NetScaler ADC management.\"\n      resources:\n        - path: /v1/lb-vservers\n          name: lb-vservers\n          description: \"Load\
  \ balancing virtual servers\"\n          operations:\n            - method: GET\n              name: list-lb-vservers\n              description: \"List all load balancing virtual servers\"\n              call: \"nitro.list-lb-vservers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-lb-vserver\n              description: \"Create a load balancing virtual server\"\n              call: \"nitro.create-lb-vserver\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/lb-vservers/{name}\n          name: lb-vserver\n          description: \"Single load balancing virtual server\"\n          operations:\n            - method: GET\n              name: get-lb-vserver\n              description: \"Get a specific load balancing virtual server\"\n              call: \"nitro.get-lb-vserver\"\n              with:\n          \
  \      name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-lb-vserver\n              description: \"Update a load balancing virtual server\"\n              call: \"nitro.update-lb-vserver\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-lb-vserver\n              description: \"Delete a load balancing virtual server\"\n              call: \"nitro.delete-lb-vserver\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/lb-vservers/{name}/bindings\n          name: lb-vserver-bindings\n          description: \"Service bindings for a load balancing virtual server\"\n          operations:\n\
  \            - method: GET\n              name: get-lb-vserver-service-bindings\n              description: \"Get service bindings for an LB virtual server\"\n              call: \"nitro.get-lb-vserver-service-bindings\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: bind-service-to-lb-vserver\n              description: \"Bind a service to an LB virtual server\"\n              call: \"nitro.bind-service-to-lb-vserver\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cs-vservers\n          name: cs-vservers\n          description: \"Content switching virtual servers\"\n          operations:\n            - method: GET\n              name: list-cs-vservers\n              description: \"List all content switching virtual servers\"\n              call: \"nitro.list-cs-vservers\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-cs-vserver\n              description: \"Create a content switching virtual server\"\n              call: \"nitro.create-cs-vserver\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cs-vservers/{name}\n          name: cs-vserver\n          description: \"Single content switching virtual server\"\n          operations:\n            - method: GET\n              name: get-cs-vserver\n              description: \"Get a content switching virtual server\"\n              call: \"nitro.get-cs-vserver\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-cs-vserver\n              description: \"Update a content\
  \ switching virtual server\"\n              call: \"nitro.update-cs-vserver\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-cs-vserver\n              description: \"Delete a content switching virtual server\"\n              call: \"nitro.delete-cs-vserver\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/config\n          name: config\n          description: \"Appliance configuration\"\n          operations:\n            - method: GET\n              name: get-ns-config\n              description: \"Get NetScaler configuration\"\n              call: \"nitro.get-ns-config\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method:\
  \ POST\n              name: save-ns-config\n              description: \"Save running configuration to disk\"\n              call: \"nitro.save-ns-config\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stats/lb-vservers\n          name: lb-vserver-stats\n          description: \"Load balancing virtual server statistics\"\n          operations:\n            - method: GET\n              name: list-lb-vserver-stats\n              description: \"List statistics for all LB virtual servers\"\n              call: \"nitro.list-lb-vserver-stats\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stats/lb-vservers/{name}\n          name: lb-vserver-stats-detail\n          description: \"Statistics for a specific LB virtual server\"\n          operations:\n            - method: GET\n              name: get-lb-vserver-stats\n              description: \"\
  Get statistics for an LB virtual server\"\n              call: \"nitro.get-lb-vserver-stats\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stats/cs-vservers\n          name: cs-vserver-stats\n          description: \"Content switching virtual server statistics\"\n          operations:\n            - method: GET\n              name: list-cs-vserver-stats\n              description: \"List statistics for all CS virtual servers\"\n              call: \"nitro.list-cs-vserver-stats\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: adc-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Citrix NetScaler ADC management.\"\n      tools:\n        - name: list-lb-vservers\n          description: \"List all load balancing virtual\
  \ servers on the NetScaler\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"nitro.list-lb-vservers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-lb-vserver\n          description: \"Create a new load balancing virtual server\"\n          hints:\n            readOnly: false\n          call: \"nitro.create-lb-vserver\"\n          with:\n            vserver: \"tools.vserver\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-lb-vserver\n          description: \"Get details of a specific load balancing virtual server\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"nitro.get-lb-vserver\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-lb-vserver\n          description:\
  \ \"Update a load balancing virtual server configuration\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"nitro.update-lb-vserver\"\n          with:\n            name: \"tools.name\"\n            vserver: \"tools.vserver\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-lb-vserver\n          description: \"Delete a load balancing virtual server\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"nitro.delete-lb-vserver\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: bind-service-to-lb-vserver\n          description: \"Bind a backend service to a load balancing virtual server\"\n          hints:\n            readOnly: false\n          call: \"nitro.bind-service-to-lb-vserver\"\n          with:\n\
  \            binding: \"tools.binding\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-lb-vserver-service-bindings\n          description: \"Get all service bindings for a load balancing virtual server\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"nitro.get-lb-vserver-service-bindings\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: unbind-service-from-lb-vserver\n          description: \"Unbind a service from a load balancing virtual server\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"nitro.unbind-service-from-lb-vserver\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-cs-vservers\n          description:\
  \ \"List all content switching virtual servers\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"nitro.list-cs-vservers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-cs-vserver\n          description: \"Create a content switching virtual server\"\n          hints:\n            readOnly: false\n          call: \"nitro.create-cs-vserver\"\n          with:\n            vserver: \"tools.vserver\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cs-vserver\n          description: \"Get details of a specific content switching virtual server\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"nitro.get-cs-vserver\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-cs-vserver\n\
  \          description: \"Update a content switching virtual server\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"nitro.update-cs-vserver\"\n          with:\n            name: \"tools.name\"\n            vserver: \"tools.vserver\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-cs-vserver\n          description: \"Delete a content switching virtual server\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"nitro.delete-cs-vserver\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-ns-config\n          description: \"Get NetScaler appliance configuration\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"nitro.get-ns-config\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: save-ns-config\n          description: \"Save the running NetScaler configuration to persistent storage\"\n          hints:\n            readOnly: false\n          call: \"nitro.save-ns-config\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-lb-vserver-stats\n          description: \"List performance statistics for all LB virtual servers\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"nitro.list-lb-vserver-stats\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-lb-vserver-stats\n          description: \"Get performance statistics for a specific LB virtual server\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"nitro.get-lb-vserver-stats\"\n          with:\n            name: \"tools.name\"\n     \
  \     outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-cs-vserver-stats\n          description: \"List statistics for all content switching virtual servers\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"nitro.list-cs-vserver-stats\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cs-vserver-stats\n          description: \"Get statistics for a specific content switching virtual server\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"nitro.get-cs-vserver-stats\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/citrix-netscaler/refs/heads/main/capabilities/adc-management.yaml
tags:
- Citrix
- NetScaler
- Load Balancing
- ADC Management
- Network Administration
tools:
- description: List all load balancing virtual servers on the NetScaler
  hints:
    openWorld: true
    readOnly: true
  name: list-lb-vservers
- description: Create a new load balancing virtual server
  hints:
    readOnly: false
  name: create-lb-vserver
- description: Get details of a specific load balancing virtual server
  hints:
    openWorld: true
    readOnly: true
  name: get-lb-vserver
- description: Update a load balancing virtual server configuration
  hints:
    idempotent: true
    readOnly: false
  name: update-lb-vserver
- description: Delete a load balancing virtual server
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-lb-vserver
- description: Bind a backend service to a load balancing virtual server
  hints:
    readOnly: false
  name: bind-service-to-lb-vserver
- description: Get all service bindings for a load balancing virtual server
  hints:
    openWorld: true
    readOnly: true
  name: get-lb-vserver-service-bindings
- description: Unbind a service from a load balancing virtual server
  hints:
    destructive: true
    readOnly: false
  name: unbind-service-from-lb-vserver
- description: List all content switching virtual servers
  hints:
    openWorld: true
    readOnly: true
  name: list-cs-vservers
- description: Create a content switching virtual server
  hints:
    readOnly: false
  name: create-cs-vserver
- description: Get details of a specific content switching virtual server
  hints:
    openWorld: true
    readOnly: true
  name: get-cs-vserver
- description: Update a content switching virtual server
  hints:
    idempotent: true
    readOnly: false
  name: update-cs-vserver
- description: Delete a content switching virtual server
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-cs-vserver
- description: Get NetScaler appliance configuration
  hints:
    openWorld: true
    readOnly: true
  name: get-ns-config
- description: Save the running NetScaler configuration to persistent storage
  hints:
    readOnly: false
  name: save-ns-config
- description: List performance statistics for all LB virtual servers
  hints:
    openWorld: true
    readOnly: true
  name: list-lb-vserver-stats
- description: Get performance statistics for a specific LB virtual server
  hints:
    openWorld: true
    readOnly: true
  name: get-lb-vserver-stats
- description: List statistics for all content switching virtual servers
  hints:
    openWorld: true
    readOnly: true
  name: list-cs-vserver-stats
- description: Get statistics for a specific content switching virtual server
  hints:
    openWorld: true
    readOnly: true
  name: get-cs-vserver-stats
---
