---
categories: []
consumed_apis: []
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
- get lb vserver
- network administration
- delete lb vserver
- ssl offloading
- list lb vserver stats
- statistics for a specific lb virtual server
- bind a backend service to a load balancing virtual server
- content switching virtual server statistics
- list performance statistics for all lb virtual servers
- web application firewall
- get cs vserver stats
- get ns config
- get lb vserver stats
- delete cs vserver
- update cs vserver
- list statistics for all cs virtual servers
- list all load balancing virtual servers on the netscaler
- get netscaler appliance configuration
- list all content switching virtual servers
- application delivery controller
- service bindings for a load balancing virtual server
- get a content switching virtual server
- get lb vserver service bindings
- single content switching virtual server
- delete a content switching virtual server
- get details of a specific load balancing virtual server
- get details of a specific content switching virtual server
- load balancing virtual servers
- create a new load balancing virtual server
- list cs vservers
- create cs vserver
- update a content switching virtual server
- application security
- get service bindings for an lb virtual server
- get cs vserver
- save ns config
- list lb vservers
- bind a service to an lb virtual server
- save running configuration to disk
- get statistics for an lb virtual server
- netscaler
- single load balancing virtual server
- citrix
- bind service to lb vserver
- update a load balancing virtual server configuration
- unbind a service from a load balancing virtual server
- create a load balancing virtual server
- update a load balancing virtual server
- save the running netscaler configuration to persistent storage
- delete a load balancing virtual server
- api gateway
- get a specific load balancing virtual server
- list cs vserver stats
- create lb vserver
- traffic management
- get all service bindings for a load balancing virtual server
- unbind service from lb vserver
- update lb vserver
- load balancing
- load balancing virtual server statistics
- get performance statistics for a specific lb virtual server
- list all load balancing virtual servers
- content switching virtual servers
- create a content switching virtual server
- list statistics for all lb virtual servers
- list statistics for all content switching virtual servers
- adc management
- get statistics for a specific content switching virtual server
- appliance configuration
- get netscaler configuration
slug: adc-management
source_filename: adc-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Citrix NetScaler ADC Management\n  description: Unified capability for managing Citrix NetScaler application delivery controllers, including load balancing,\n    content switching, configuration management, and monitoring. Used by network administrators and platform engineers.\n  tags:\n  - Citrix\n  - NetScaler\n  - Load Balancing\n  - ADC Management\n  - Network Administration\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    NETSCALER_USERNAME: NETSCALER_USERNAME\n    NETSCALER_PASSWORD: NETSCALER_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: nitro\n    baseUri: https://{nsip}/nitro/v1\n    description: Citrix NetScaler NITRO REST API for ADC management\n    authentication:\n      type: basic\n      username: '{{NETSCALER_USERNAME}}'\n      password: '{{NETSCALER_PASSWORD}}'\n    resources:\n    - name: authentication\n      path: /config\n      description: Session-based\
  \ authentication for the NITRO API\n      operations:\n      - name: login\n        method: POST\n        description: Log in to the NetScaler appliance and obtain session token\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            login:\n              username: '{{tools.username}}'\n              password: '{{tools.password}}'\n      - name: logout\n        method: POST\n        description: Log out from the NetScaler appliance\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            logout: {}\n    - name: ns-config\n      path: /config\n      description: NetScaler appliance configuration management\n      operations:\n      - name: get-ns-config\n    \
  \    method: GET\n        description: Get NetScaler configuration\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-ns-config\n        method: PUT\n        description: Update NetScaler configuration\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            nsconfig: '{{tools.config}}'\n      - name: save-ns-config\n        method: POST\n        description: Save NetScaler configuration to disk\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: clear-ns-config\n        method: POST\n        description: Clear NetScaler configuration\n        inputParameters: []\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            nsconfig: '{{tools.config}}'\n    - name: system-files\n      path: /config\n      description: System file management\n      operations:\n      - name: list-system-files\n        method: GET\n        description: List system files on the appliance\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upload-system-file\n        method: POST\n        description: Upload a system file to the appliance\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            systemfile: '{{tools.file}}'\n      - name: delete-system-file\n        method: DELETE\n\
  \        description: Delete a system file from the appliance\n        inputParameters:\n        - name: filename\n          in: path\n          type: string\n          required: true\n          description: Name of the file to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lb-vservers\n      path: /config\n      description: Load balancing virtual server management\n      operations:\n      - name: list-lb-vservers\n        method: GET\n        description: List all load balancing virtual servers\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-lb-vserver\n        method: POST\n        description: Create a load balancing virtual server\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        body:\n          type: json\n          data:\n            lbvserver: '{{tools.vserver}}'\n      - name: get-lb-vserver\n        method: GET\n        description: Get a specific load balancing virtual server\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the LB virtual server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-lb-vserver\n        method: PUT\n        description: Update a load balancing virtual server\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the LB virtual server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n  \
  \        data:\n            lbvserver: '{{tools.vserver}}'\n      - name: delete-lb-vserver\n        method: DELETE\n        description: Delete a load balancing virtual server\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the LB virtual server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lb-service-bindings\n      path: /config\n      description: Load balancing virtual server service binding management\n      operations:\n      - name: bind-service-to-lb-vserver\n        method: POST\n        description: Bind a service to a load balancing virtual server\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            lbvserver_service_binding:\
  \ '{{tools.binding}}'\n      - name: get-lb-vserver-service-bindings\n        method: GET\n        description: Get service bindings for a load balancing virtual server\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the LB virtual server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unbind-service-from-lb-vserver\n        method: DELETE\n        description: Unbind a service from a load balancing virtual server\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the LB virtual server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cs-vservers\n      path: /config\n      description: Content switching virtual\
  \ server management\n      operations:\n      - name: list-cs-vservers\n        method: GET\n        description: List all content switching virtual servers\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-cs-vserver\n        method: POST\n        description: Create a content switching virtual server\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            csvserver: '{{tools.vserver}}'\n      - name: get-cs-vserver\n        method: GET\n        description: Get a specific content switching virtual server\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the CS virtual server\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-cs-vserver\n        method: PUT\n        description: Update a content switching virtual server\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the CS virtual server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            csvserver: '{{tools.vserver}}'\n      - name: delete-cs-vserver\n        method: DELETE\n        description: Delete a content switching virtual server\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the CS virtual server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n    - name: cs-policy-bindings\n      path: /config\n      description: Content switching policy binding management\n      operations:\n      - name: bind-cs-policy-to-cs-vserver\n        method: POST\n        description: Bind a content switching policy to a CS virtual server\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            csvserver_cspolicy_binding: '{{tools.binding}}'\n      - name: get-cs-vserver-policy-bindings\n        method: GET\n        description: Get policy bindings for a content switching virtual server\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the CS virtual server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n    - name: statistics\n      path: /stat\n      description: Performance and health statistics\n      operations:\n      - name: list-lb-vserver-stats\n        method: GET\n        description: List statistics for all load balancing virtual servers\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-lb-vserver-stats\n        method: GET\n        description: Get statistics for a specific load balancing virtual server\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the LB virtual server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-cs-vserver-stats\n        method: GET\n        description: List statistics for all content switching\
  \ virtual servers\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-cs-vserver-stats\n        method: GET\n        description: Get statistics for a specific content switching virtual server\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the CS virtual server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: adc-management-api\n    description: Unified REST API for Citrix NetScaler ADC management.\n    resources:\n    - path: /v1/lb-vservers\n      name: lb-vservers\n      description: Load balancing virtual servers\n      operations:\n      - method: GET\n        name: list-lb-vservers\n        description: List all load balancing\
  \ virtual servers\n        call: nitro.list-lb-vservers\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-lb-vserver\n        description: Create a load balancing virtual server\n        call: nitro.create-lb-vserver\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lb-vservers/{name}\n      name: lb-vserver\n      description: Single load balancing virtual server\n      operations:\n      - method: GET\n        name: get-lb-vserver\n        description: Get a specific load balancing virtual server\n        call: nitro.get-lb-vserver\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-lb-vserver\n        description: Update a load balancing virtual server\n        call: nitro.update-lb-vserver\n        with:\n          name: rest.name\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n      - method: DELETE\n        name: delete-lb-vserver\n        description: Delete a load balancing virtual server\n        call: nitro.delete-lb-vserver\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lb-vservers/{name}/bindings\n      name: lb-vserver-bindings\n      description: Service bindings for a load balancing virtual server\n      operations:\n      - method: GET\n        name: get-lb-vserver-service-bindings\n        description: Get service bindings for an LB virtual server\n        call: nitro.get-lb-vserver-service-bindings\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: bind-service-to-lb-vserver\n        description: Bind a service to an LB virtual server\n        call: nitro.bind-service-to-lb-vserver\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/cs-vservers\n      name: cs-vservers\n      description: Content switching virtual servers\n      operations:\n      - method: GET\n        name: list-cs-vservers\n        description: List all content switching virtual servers\n        call: nitro.list-cs-vservers\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-cs-vserver\n        description: Create a content switching virtual server\n        call: nitro.create-cs-vserver\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cs-vservers/{name}\n      name: cs-vserver\n      description: Single content switching virtual server\n      operations:\n      - method: GET\n        name: get-cs-vserver\n        description: Get a content switching virtual server\n        call: nitro.get-cs-vserver\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n      \
  \    mapping: $.\n      - method: PUT\n        name: update-cs-vserver\n        description: Update a content switching virtual server\n        call: nitro.update-cs-vserver\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-cs-vserver\n        description: Delete a content switching virtual server\n        call: nitro.delete-cs-vserver\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/config\n      name: config\n      description: Appliance configuration\n      operations:\n      - method: GET\n        name: get-ns-config\n        description: Get NetScaler configuration\n        call: nitro.get-ns-config\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: save-ns-config\n        description: Save running configuration to disk\n       \
  \ call: nitro.save-ns-config\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stats/lb-vservers\n      name: lb-vserver-stats\n      description: Load balancing virtual server statistics\n      operations:\n      - method: GET\n        name: list-lb-vserver-stats\n        description: List statistics for all LB virtual servers\n        call: nitro.list-lb-vserver-stats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stats/lb-vservers/{name}\n      name: lb-vserver-stats-detail\n      description: Statistics for a specific LB virtual server\n      operations:\n      - method: GET\n        name: get-lb-vserver-stats\n        description: Get statistics for an LB virtual server\n        call: nitro.get-lb-vserver-stats\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stats/cs-vservers\n      name: cs-vserver-stats\n      description:\
  \ Content switching virtual server statistics\n      operations:\n      - method: GET\n        name: list-cs-vserver-stats\n        description: List statistics for all CS virtual servers\n        call: nitro.list-cs-vserver-stats\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: adc-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Citrix NetScaler ADC management.\n    tools:\n    - name: list-lb-vservers\n      description: List all load balancing virtual servers on the NetScaler\n      hints:\n        readOnly: true\n        openWorld: true\n      call: nitro.list-lb-vservers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-lb-vserver\n      description: Create a new load balancing virtual server\n      hints:\n        readOnly: false\n      call: nitro.create-lb-vserver\n      with:\n        vserver: tools.vserver\n      outputParameters:\n  \
  \    - type: object\n        mapping: $.\n    - name: get-lb-vserver\n      description: Get details of a specific load balancing virtual server\n      hints:\n        readOnly: true\n        openWorld: true\n      call: nitro.get-lb-vserver\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-lb-vserver\n      description: Update a load balancing virtual server configuration\n      hints:\n        readOnly: false\n        idempotent: true\n      call: nitro.update-lb-vserver\n      with:\n        name: tools.name\n        vserver: tools.vserver\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-lb-vserver\n      description: Delete a load balancing virtual server\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nitro.delete-lb-vserver\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: bind-service-to-lb-vserver\n      description: Bind a backend service to a load balancing virtual server\n      hints:\n        readOnly: false\n      call: nitro.bind-service-to-lb-vserver\n      with:\n        binding: tools.binding\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-lb-vserver-service-bindings\n      description: Get all service bindings for a load balancing virtual server\n      hints:\n        readOnly: true\n        openWorld: true\n      call: nitro.get-lb-vserver-service-bindings\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unbind-service-from-lb-vserver\n      description: Unbind a service from a load balancing virtual server\n      hints:\n        readOnly: false\n        destructive: true\n      call: nitro.unbind-service-from-lb-vserver\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-cs-vservers\n      description: List all content switching virtual servers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: nitro.list-cs-vservers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cs-vserver\n      description: Create a content switching virtual server\n      hints:\n        readOnly: false\n      call: nitro.create-cs-vserver\n      with:\n        vserver: tools.vserver\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cs-vserver\n      description: Get details of a specific content switching virtual server\n      hints:\n        readOnly: true\n        openWorld: true\n      call: nitro.get-cs-vserver\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-cs-vserver\n      description: Update a content switching virtual server\n      hints:\n        readOnly:\
  \ false\n        idempotent: true\n      call: nitro.update-cs-vserver\n      with:\n        name: tools.name\n        vserver: tools.vserver\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-cs-vserver\n      description: Delete a content switching virtual server\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nitro.delete-cs-vserver\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ns-config\n      description: Get NetScaler appliance configuration\n      hints:\n        readOnly: true\n        openWorld: true\n      call: nitro.get-ns-config\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: save-ns-config\n      description: Save the running NetScaler configuration to persistent storage\n      hints:\n        readOnly: false\n      call: nitro.save-ns-config\n      outputParameters:\n \
  \     - type: object\n        mapping: $.\n    - name: list-lb-vserver-stats\n      description: List performance statistics for all LB virtual servers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: nitro.list-lb-vserver-stats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-lb-vserver-stats\n      description: Get performance statistics for a specific LB virtual server\n      hints:\n        readOnly: true\n        openWorld: true\n      call: nitro.get-lb-vserver-stats\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cs-vserver-stats\n      description: List statistics for all content switching virtual servers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: nitro.list-cs-vserver-stats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cs-vserver-stats\n      description: Get statistics\
  \ for a specific content switching virtual server\n      hints:\n        readOnly: true\n        openWorld: true\n      call: nitro.get-cs-vserver-stats\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
