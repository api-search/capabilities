---
categories: []
consumed_apis:
- iis-administration
description: Unified workflow for IT administrators to manage IIS web sites, applications, and application pools for enterprise web hosting on Windows Server.
layout: capability
name: Windows Server Web Management
operations:
- description: List all web sites
  method: GET
  name: list-websites
  path: /v1/websites
- description: Create a web site
  method: POST
  name: create-website
  path: /v1/websites
- description: Get web site details
  method: GET
  name: get-website
  path: /v1/websites/{id}
- description: Update a web site
  method: PATCH
  name: update-website
  path: /v1/websites/{id}
- description: Delete a web site
  method: DELETE
  name: delete-website
  path: /v1/websites/{id}
- description: List all applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: Create an application
  method: POST
  name: create-application
  path: /v1/applications
- description: List all application pools
  method: GET
  name: list-application-pools
  path: /v1/application-pools
- description: Create an application pool
  method: POST
  name: create-application-pool
  path: /v1/application-pools
personas: []
provider_name: Microsoft Windows Server
provider_slug: microsoft-windows-server
search_terms:
- create an iis application pool
- update an iis web site configuration
- create application
- get application
- create a new web application
- get web application details
- get application pool details
- create an application
- list application pools
- delete website
- single web site operations
- delete an iis web site
- get website
- list all iis application pools
- update application
- get web site details
- operating system
- list websites
- list all web sites
- windows server
- list all application pools
- enterprise
- update an application pool configuration
- create website
- datacenter
- microsoft
- list all applications
- infrastructure
- update a web site
- server management
- iis
- delete an application pool
- web application management
- create application pool
- update application pool
- list all iis web sites on the server
- update a web application
- list applications
- create a new iis web site
- list all web applications
- get application pool
- create a web site
- delete a web application
- delete application
- create an application pool
- delete application pool
- web server
- application pool management
- windows server 2025
- web site management
- get details for a specific web site
- update website
- delete a web site
slug: web-server-management
source_filename: web-server-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Windows Server Web Management\"\n  description: \"Unified workflow for IT administrators to manage IIS web sites, applications, and application pools for enterprise web hosting on Windows Server.\"\n  tags:\n    - Microsoft\n    - Windows Server\n    - IIS\n    - Web Server\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      IIS_ACCESS_TOKEN: IIS_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: iis-administration\n      location: ./shared/iis-administration.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: web-server-api\n      description: \"Unified REST API for IIS web server management.\"\n      resources:\n        - path: /v1/websites\n          name: websites\n          description: \"Web site management\"\n          operations:\n            - method: GET\n              name: list-websites\n              description: \"List all web sites\"\n \
  \             call: \"iis-administration.list-websites\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-website\n              description: \"Create a web site\"\n              call: \"iis-administration.create-website\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/websites/{id}\n          name: website-detail\n          description: \"Single web site operations\"\n          operations:\n            - method: GET\n              name: get-website\n              description: \"Get web site details\"\n              call: \"iis-administration.get-website\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-website\n              description: \"Update\
  \ a web site\"\n              call: \"iis-administration.update-website\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-website\n              description: \"Delete a web site\"\n              call: \"iis-administration.delete-website\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications\n          name: applications\n          description: \"Web application management\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List all applications\"\n              call: \"iis-administration.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method:\
  \ POST\n              name: create-application\n              description: \"Create an application\"\n              call: \"iis-administration.create-application\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/application-pools\n          name: application-pools\n          description: \"Application pool management\"\n          operations:\n            - method: GET\n              name: list-application-pools\n              description: \"List all application pools\"\n              call: \"iis-administration.list-application-pools\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-application-pool\n              description: \"Create an application pool\"\n              call: \"iis-administration.create-application-pool\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: web-server-mcp\n      transport: http\n      description: \"MCP server for AI-assisted IIS web server management.\"\n      tools:\n        - name: list-websites\n          description: \"List all IIS web sites on the server\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iis-administration.list-websites\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-website\n          description: \"Create a new IIS web site\"\n          hints:\n            readOnly: false\n          call: \"iis-administration.create-website\"\n          with:\n            name: \"tools.name\"\n            physical_path: \"tools.physical_path\"\n            bindings: \"tools.bindings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-website\n          description: \"Get details for a\
  \ specific web site\"\n          hints:\n            readOnly: true\n          call: \"iis-administration.get-website\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-website\n          description: \"Update an IIS web site configuration\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"iis-administration.update-website\"\n          with:\n            id: \"tools.id\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-website\n          description: \"Delete an IIS web site\"\n          hints:\n            destructive: true\n          call: \"iis-administration.delete-website\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-applications\n\
  \          description: \"List all web applications\"\n          hints:\n            readOnly: true\n          call: \"iis-administration.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-application\n          description: \"Create a new web application\"\n          hints:\n            readOnly: false\n          call: \"iis-administration.create-application\"\n          with:\n            path: \"tools.path\"\n            physical_path: \"tools.physical_path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application\n          description: \"Get web application details\"\n          hints:\n            readOnly: true\n          call: \"iis-administration.get-application\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-application\n\
  \          description: \"Update a web application\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"iis-administration.update-application\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-application\n          description: \"Delete a web application\"\n          hints:\n            destructive: true\n          call: \"iis-administration.delete-application\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-application-pools\n          description: \"List all IIS application pools\"\n          hints:\n            readOnly: true\n          call: \"iis-administration.list-application-pools\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-application-pool\n     \
  \     description: \"Create an IIS application pool\"\n          hints:\n            readOnly: false\n          call: \"iis-administration.create-application-pool\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application-pool\n          description: \"Get application pool details\"\n          hints:\n            readOnly: true\n          call: \"iis-administration.get-application-pool\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-application-pool\n          description: \"Update an application pool configuration\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"iis-administration.update-application-pool\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n  \
  \            mapping: \"$.\"\n        - name: delete-application-pool\n          description: \"Delete an application pool\"\n          hints:\n            destructive: true\n          call: \"iis-administration.delete-application-pool\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-windows-server/refs/heads/main/capabilities/web-server-management.yaml
tags:
- Microsoft
- Windows Server
- IIS
- Web Server
tools:
- description: List all IIS web sites on the server
  hints:
    openWorld: true
    readOnly: true
  name: list-websites
- description: Create a new IIS web site
  hints:
    readOnly: false
  name: create-website
- description: Get details for a specific web site
  hints:
    readOnly: true
  name: get-website
- description: Update an IIS web site configuration
  hints:
    idempotent: true
    readOnly: false
  name: update-website
- description: Delete an IIS web site
  hints:
    destructive: true
  name: delete-website
- description: List all web applications
  hints:
    readOnly: true
  name: list-applications
- description: Create a new web application
  hints:
    readOnly: false
  name: create-application
- description: Get web application details
  hints:
    readOnly: true
  name: get-application
- description: Update a web application
  hints:
    idempotent: true
    readOnly: false
  name: update-application
- description: Delete a web application
  hints:
    destructive: true
  name: delete-application
- description: List all IIS application pools
  hints:
    readOnly: true
  name: list-application-pools
- description: Create an IIS application pool
  hints:
    readOnly: false
  name: create-application-pool
- description: Get application pool details
  hints:
    readOnly: true
  name: get-application-pool
- description: Update an application pool configuration
  hints:
    idempotent: true
    readOnly: false
  name: update-application-pool
- description: Delete an application pool
  hints:
    destructive: true
  name: delete-application-pool
---
