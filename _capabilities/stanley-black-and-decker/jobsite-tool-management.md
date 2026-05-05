---
categories: []
consumed_apis:
- tool-connect
description: Unified capability for jobsite tool and asset management workflows using DEWALT Tool Connect. Enables construction managers, fleet coordinators, and contractors to track connected tools, monitor battery health, manage jobsite inventory, and analyze tool utilization.
layout: capability
name: Stanley Black & Decker Jobsite Tool Management
operations:
- description: List all connected DEWALT tools with status
  method: GET
  name: list-tools
  path: /v1/tools
- description: Get tool details, firmware, and connectivity status
  method: GET
  name: get-tool
  path: /v1/tools/{toolId}
- description: Get tool operational hours and usage patterns
  method: GET
  name: get-tool-usage
  path: /v1/tools/{toolId}/usage
- description: List batteries with charge levels and health status
  method: GET
  name: list-batteries
  path: /v1/batteries
- description: Get battery diagnostics including charge cycles and temperature
  method: GET
  name: get-battery
  path: /v1/batteries/{batteryId}
- description: List all tracked assets including tools, batteries, and tags
  method: GET
  name: list-assets
  path: /v1/assets
- description: Register a new asset by serial number
  method: POST
  name: register-asset
  path: /v1/assets
- description: List all configured jobsites with asset counts
  method: GET
  name: list-jobsites
  path: /v1/jobsites
- description: Create a new jobsite for tool tracking
  method: POST
  name: create-jobsite
  path: /v1/jobsites
- description: Get jobsite with full tool and battery inventory
  method: GET
  name: get-jobsite
  path: /v1/jobsites/{jobsiteId}
- description: List all organization users and their roles
  method: GET
  name: list-users
  path: /v1/users
personas: []
provider_name: Stanley Black & Decker
provider_slug: stanley-black-and-decker
search_terms:
- get battery health
- list all tracked assets including tools, batteries, and tags
- view all tools, batteries, tags, and connectors tracked at a specific jobsite
- analyze dewalt tool runtime hours, trigger events, and usage patterns over a date range
- get detailed dewalt battery diagnostics including charge cycles, temperature, and replacement recommendation
- list users
- list team members
- list jobsite assets
- list jobsites
- tools
- get tool usage stats
- list tools
- construction
- list assets
- get tool details, firmware, and connectivity status
- get connected tool details
- jobsite management
- team and user management
- individual battery health details
- list all configured jobsites with asset counts
- list all configured dewalt tool connect jobsites with asset and user counts
- get tool details
- get jobsite
- list all users in the dewalt tool connect organization with their roles and jobsite assignments
- register a new dewalt tool, battery, or tag to the account by scanning its qr code or entering the serial number
- list batteries
- connected tool inventory management
- list batteries with charge levels and health status
- list all connected dewalt tools with status
- create jobsite
- stanley black and decker
- get battery diagnostics including charge cycles and temperature
- list dewalt battery fleet with charge levels, health status, and paired tool information
- register asset
- asset tracking
- get tool
- create a new jobsite for tool tracking
- get jobsite with full tool and battery inventory
- full asset inventory
- get battery
- manufacturing
- list all organization users and their roles
- get full dewalt tool and battery inventory for a jobsite including user assignments and asset counts
- get tool operational hours and usage patterns
- register a new asset by serial number
- jobsite project management
- get tool usage
- dewalt
- jobsite inventory overview
- list all dewalt connected tools registered to the account, filterable by jobsite or connectivity status
- get dewalt tool details including model, serial number, firmware version, and warranty information
- iot
- create a new dewalt tool connect jobsite for organizing tool and asset tracking by project
- get jobsite inventory
- connected tools
- battery fleet health monitoring
- hardware
- tool usage and runtime statistics
slug: jobsite-tool-management
source_filename: jobsite-tool-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Stanley Black & Decker Jobsite Tool Management\"\n  description: >-\n    Unified capability for jobsite tool and asset management workflows using DEWALT Tool Connect. Enables construction managers, fleet coordinators, and contractors to track connected tools, monitor battery health, manage jobsite inventory, and analyze tool utilization.\n  tags:\n    - Stanley Black And Decker\n    - DEWALT\n    - Connected Tools\n    - Jobsite Management\n    - Asset Tracking\n    - IoT\n    - Construction\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      DEWALT_API_TOKEN: DEWALT_API_TOKEN\n\ncapability:\n  consumes:\n    - import: tool-connect\n      location: ./shared/tool-connect-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: jobsite-tool-management-api\n      description: \"Unified REST API for DEWALT jobsite tool and asset management.\"\n      resources:\n\
  \        - path: /v1/tools\n          name: tools\n          description: Connected tool inventory management\n          operations:\n            - method: GET\n              name: list-tools\n              description: List all connected DEWALT tools with status\n              call: \"tool-connect.list-tools\"\n              with:\n                jobsiteId: \"rest.jobsiteId\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tools/{toolId}\n          name: tool\n          description: Get connected tool details\n          operations:\n            - method: GET\n              name: get-tool\n              description: Get tool details, firmware, and connectivity status\n              call: \"tool-connect.get-tool\"\n              with:\n                toolId: \"rest.toolId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n\n        - path: /v1/tools/{toolId}/usage\n          name: tool-usage\n          description: Tool usage and runtime statistics\n          operations:\n            - method: GET\n              name: get-tool-usage\n              description: Get tool operational hours and usage patterns\n              call: \"tool-connect.get-tool-usage\"\n              with:\n                toolId: \"rest.toolId\"\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/batteries\n          name: batteries\n          description: Battery fleet health monitoring\n          operations:\n            - method: GET\n              name: list-batteries\n              description: List batteries with charge levels and health status\n              call: \"tool-connect.list-batteries\"\n              with:\n                jobsiteId: \"rest.jobsiteId\"\n\
  \                chargeStatus: \"rest.chargeStatus\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/batteries/{batteryId}\n          name: battery\n          description: Individual battery health details\n          operations:\n            - method: GET\n              name: get-battery\n              description: Get battery diagnostics including charge cycles and temperature\n              call: \"tool-connect.get-battery\"\n              with:\n                batteryId: \"rest.batteryId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/assets\n          name: assets\n          description: Full asset inventory\n          operations:\n            - method: GET\n              name: list-assets\n              description: List all tracked assets including tools, batteries, and tags\n              call: \"tool-connect.list-assets\"\n   \
  \           with:\n                type: \"rest.type\"\n                jobsiteId: \"rest.jobsiteId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: register-asset\n              description: Register a new asset by serial number\n              call: \"tool-connect.register-asset\"\n              with:\n                serialNumber: \"rest.serialNumber\"\n                type: \"rest.type\"\n                jobsiteId: \"rest.jobsiteId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobsites\n          name: jobsites\n          description: Jobsite project management\n          operations:\n            - method: GET\n              name: list-jobsites\n              description: List all configured jobsites with asset counts\n              call: \"tool-connect.list-jobsites\"\n              outputParameters:\n \
  \               - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-jobsite\n              description: Create a new jobsite for tool tracking\n              call: \"tool-connect.create-jobsite\"\n              with:\n                name: \"rest.name\"\n                address: \"rest.address\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobsites/{jobsiteId}\n          name: jobsite\n          description: Jobsite inventory overview\n          operations:\n            - method: GET\n              name: get-jobsite\n              description: Get jobsite with full tool and battery inventory\n              call: \"tool-connect.get-jobsite\"\n              with:\n                jobsiteId: \"rest.jobsiteId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n\
  \          description: Team and user management\n          operations:\n            - method: GET\n              name: list-users\n              description: List all organization users and their roles\n              call: \"tool-connect.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: jobsite-tool-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted DEWALT jobsite tool and asset management.\"\n      tools:\n        - name: list-tools\n          description: List all DEWALT connected tools registered to the account, filterable by jobsite or connectivity status\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tool-connect.list-tools\"\n          with:\n            jobsiteId: \"tools.jobsiteId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n \
  \             mapping: \"$.\"\n\n        - name: get-tool-details\n          description: Get DEWALT tool details including model, serial number, firmware version, and warranty information\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tool-connect.get-tool\"\n          with:\n            toolId: \"tools.toolId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-tool-usage-stats\n          description: Analyze DEWALT tool runtime hours, trigger events, and usage patterns over a date range\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tool-connect.get-tool-usage\"\n          with:\n            toolId: \"tools.toolId\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-batteries\n         \
  \ description: List DEWALT battery fleet with charge levels, health status, and paired tool information\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tool-connect.list-batteries\"\n          with:\n            jobsiteId: \"tools.jobsiteId\"\n            chargeStatus: \"tools.chargeStatus\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-battery-health\n          description: Get detailed DEWALT battery diagnostics including charge cycles, temperature, and replacement recommendation\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tool-connect.get-battery\"\n          with:\n            batteryId: \"tools.batteryId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-jobsite-assets\n          description: View all tools, batteries, tags, and connectors tracked at a specific\
  \ jobsite\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tool-connect.list-assets\"\n          with:\n            jobsiteId: \"tools.jobsiteId\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: register-asset\n          description: Register a new DEWALT tool, battery, or tag to the account by scanning its QR code or entering the serial number\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"tool-connect.register-asset\"\n          with:\n            serialNumber: \"tools.serialNumber\"\n            type: \"tools.type\"\n            jobsiteId: \"tools.jobsiteId\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-jobsite-inventory\n          description: Get full DEWALT tool and battery inventory for a jobsite\
  \ including user assignments and asset counts\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tool-connect.get-jobsite\"\n          with:\n            jobsiteId: \"tools.jobsiteId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-jobsites\n          description: List all configured DEWALT Tool Connect jobsites with asset and user counts\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tool-connect.list-jobsites\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-jobsite\n          description: Create a new DEWALT Tool Connect jobsite for organizing tool and asset tracking by project\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"tool-connect.create-jobsite\"\n          with:\n            name: \"tools.name\"\n         \
  \   address: \"tools.address\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-team-members\n          description: List all users in the DEWALT Tool Connect organization with their roles and jobsite assignments\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tool-connect.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stanley-black-and-decker/refs/heads/main/capabilities/jobsite-tool-management.yaml
tags:
- Stanley Black And Decker
- DEWALT
- Connected Tools
- Jobsite Management
- Asset Tracking
- IoT
- Construction
tools:
- description: List all DEWALT connected tools registered to the account, filterable by jobsite or connectivity status
  hints:
    openWorld: true
    readOnly: true
  name: list-tools
- description: Get DEWALT tool details including model, serial number, firmware version, and warranty information
  hints:
    idempotent: true
    readOnly: true
  name: get-tool-details
- description: Analyze DEWALT tool runtime hours, trigger events, and usage patterns over a date range
  hints:
    idempotent: true
    readOnly: true
  name: get-tool-usage-stats
- description: List DEWALT battery fleet with charge levels, health status, and paired tool information
  hints:
    openWorld: true
    readOnly: true
  name: list-batteries
- description: Get detailed DEWALT battery diagnostics including charge cycles, temperature, and replacement recommendation
  hints:
    idempotent: true
    readOnly: true
  name: get-battery-health
- description: View all tools, batteries, tags, and connectors tracked at a specific jobsite
  hints:
    idempotent: true
    readOnly: true
  name: list-jobsite-assets
- description: Register a new DEWALT tool, battery, or tag to the account by scanning its QR code or entering the serial number
  hints:
    destructive: false
    readOnly: false
  name: register-asset
- description: Get full DEWALT tool and battery inventory for a jobsite including user assignments and asset counts
  hints:
    idempotent: true
    readOnly: true
  name: get-jobsite-inventory
- description: List all configured DEWALT Tool Connect jobsites with asset and user counts
  hints:
    openWorld: true
    readOnly: true
  name: list-jobsites
- description: Create a new DEWALT Tool Connect jobsite for organizing tool and asset tracking by project
  hints:
    destructive: false
    readOnly: false
  name: create-jobsite
- description: List all users in the DEWALT Tool Connect organization with their roles and jobsite assignments
  hints:
    idempotent: true
    readOnly: true
  name: list-team-members
---
