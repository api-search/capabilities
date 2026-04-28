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
- get lb vserver stats
- single content switching virtual server
- statistics for a specific lb virtual server
- delete a load balancing virtual server
- content switching virtual server statistics
- update a load balancing virtual server configuration
- list performance statistics for all lb virtual servers
- get lb vserver service bindings
- get lb vserver
- get cs vserver
- delete a content switching virtual server
- list cs vserver stats
- ssl offloading
- load balancing
- get service bindings for an lb virtual server
- get netscaler configuration
- update lb vserver
- list all load balancing virtual servers on the netscaler
- bind a backend service to a load balancing virtual server
- get details of a specific content switching virtual server
- service bindings for a load balancing virtual server
- save the running netscaler configuration to persistent storage
- load balancing virtual server statistics
- get statistics for an lb virtual server
- save running configuration to disk
- list statistics for all lb virtual servers
- get netscaler appliance configuration
- traffic management
- create lb vserver
- content switching virtual servers
- delete lb vserver
- list statistics for all cs virtual servers
- get details of a specific load balancing virtual server
- get statistics for a specific content switching virtual server
- single load balancing virtual server
- get a content switching virtual server
- citrix
- web application firewall
- api gateway
- list lb vservers
- get ns config
- adc management
- update a content switching virtual server
- get cs vserver stats
- unbind service from lb vserver
- bind a service to an lb virtual server
- application security
- list statistics for all content switching virtual servers
- create a load balancing virtual server
- network administration
- bind service to lb vserver
- application delivery controller
- get all service bindings for a load balancing virtual server
- get a specific load balancing virtual server
- appliance configuration
- update a load balancing virtual server
- unbind a service from a load balancing virtual server
- netscaler
- create a content switching virtual server
- update cs vserver
- list all load balancing virtual servers
- list all content switching virtual servers
- save ns config
- list cs vservers
- list lb vserver stats
- create a new load balancing virtual server
- create cs vserver
- load balancing virtual servers
- delete cs vserver
- get performance statistics for a specific lb virtual server
slug: adc-management
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
