---
categories: []
consumed_apis: []
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
- get tool usage
- list all configured jobsites with asset counts
- list all tracked assets including tools, batteries, and tags
- get jobsite inventory
- dewalt
- create jobsite
- individual battery health details
- jobsite inventory overview
- hardware
- stanley black and decker
- construction
- get battery diagnostics including charge cycles and temperature
- list all connected dewalt tools with status
- list all dewalt connected tools registered to the account, filterable by jobsite or connectivity status
- create a new dewalt tool connect jobsite for organizing tool and asset tracking by project
- connected tool inventory management
- list tools
- analyze dewalt tool runtime hours, trigger events, and usage patterns over a date range
- list team members
- get tool
- list batteries
- get detailed dewalt battery diagnostics including charge cycles, temperature, and replacement recommendation
- get battery health
- list all configured dewalt tool connect jobsites with asset and user counts
- tool usage and runtime statistics
- manufacturing
- create a new jobsite for tool tracking
- get jobsite with full tool and battery inventory
- jobsite management
- list users
- list dewalt battery fleet with charge levels, health status, and paired tool information
- full asset inventory
- view all tools, batteries, tags, and connectors tracked at a specific jobsite
- get dewalt tool details including model, serial number, firmware version, and warranty information
- list all users in the dewalt tool connect organization with their roles and jobsite assignments
- battery fleet health monitoring
- iot
- get tool usage stats
- register a new dewalt tool, battery, or tag to the account by scanning its qr code or entering the serial number
- register asset
- list jobsites
- get jobsite
- get full dewalt tool and battery inventory for a jobsite including user assignments and asset counts
- get connected tool details
- connected tools
- register a new asset by serial number
- tools
- team and user management
- jobsite project management
- list jobsite assets
- asset tracking
- get battery
- get tool details, firmware, and connectivity status
- get tool operational hours and usage patterns
- list assets
- list all organization users and their roles
- get tool details
- list batteries with charge levels and health status
slug: jobsite-tool-management
source_filename: jobsite-tool-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Stanley Black & Decker Jobsite Tool Management\n  description: Unified capability for jobsite tool and asset management workflows using DEWALT Tool Connect. Enables construction\n    managers, fleet coordinators, and contractors to track connected tools, monitor battery health, manage jobsite inventory,\n    and analyze tool utilization.\n  tags:\n  - Stanley Black And Decker\n  - DEWALT\n  - Connected Tools\n  - Jobsite Management\n  - Asset Tracking\n  - IoT\n  - Construction\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    DEWALT_API_TOKEN: DEWALT_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tool-connect\n    baseUri: https://api.dewalt.com\n    description: DEWALT Tool Connect API for connected tool and asset management\n    authentication:\n      type: bearer\n      token: '{{DEWALT_API_TOKEN}}'\n    resources:\n    - name: tools\n      path: /v1/tools\n      description:\
  \ Connected tool management\n      operations:\n      - name: list-tools\n        method: GET\n        description: List all registered connected tools\n        inputParameters:\n        - name: jobsiteId\n          in: query\n          type: string\n          required: false\n          description: Filter by jobsite\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by connectivity status\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tool\n      path: /v1/tools/{toolId}\n      description: Individual tool details\n      operations:\n      - name: get-tool\n        method: GET\n        description: Get connected tool details and status\n        inputParameters:\n        - name:\
  \ toolId\n          in: path\n          type: string\n          required: true\n          description: Tool identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tool-usage\n      path: /v1/tools/{toolId}/usage\n      description: Tool usage statistics\n      operations:\n      - name: get-tool-usage\n        method: GET\n        description: Get tool runtime and usage statistics\n        inputParameters:\n        - name: toolId\n          in: path\n          type: string\n          required: true\n          description: Tool identifier\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date for usage data\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date for usage data\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n    - name: batteries\n      path: /v1/batteries\n      description: Battery fleet management\n      operations:\n      - name: list-batteries\n        method: GET\n        description: List all registered batteries with charge status\n        inputParameters:\n        - name: jobsiteId\n          in: query\n          type: string\n          required: false\n          description: Filter by jobsite\n        - name: chargeStatus\n          in: query\n          type: string\n          required: false\n          description: Filter by charge status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: battery\n      path: /v1/batteries/{batteryId}\n      description: Individual battery details\n      operations:\n      - name: get-battery\n        method: GET\n        description: Get battery health and charge status\n        inputParameters:\n\
  \        - name: batteryId\n          in: path\n          type: string\n          required: true\n          description: Battery identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets\n      path: /v1/assets\n      description: Asset inventory management\n      operations:\n      - name: list-assets\n        method: GET\n        description: List all tracked assets\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by asset type\n        - name: jobsiteId\n          in: query\n          type: string\n          required: false\n          description: Filter by jobsite\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: register-asset\n        method: POST\n        description: Register a new asset to\
  \ the account\n        body:\n          type: json\n          data:\n            serialNumber: '{{tools.serialNumber}}'\n            type: '{{tools.type}}'\n            jobsiteId: '{{tools.jobsiteId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: asset\n      path: /v1/assets/{assetId}\n      description: Individual asset details\n      operations:\n      - name: get-asset\n        method: GET\n        description: Get asset details and location\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: Asset identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobsites\n      path: /v1/jobsites\n      description: Jobsite management\n      operations:\n      - name: list-jobsites\n        method: GET\n        description:\
  \ List all configured jobsites\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-jobsite\n        method: POST\n        description: Create a new jobsite\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            address: '{{tools.address}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobsite\n      path: /v1/jobsites/{jobsiteId}\n      description: Individual jobsite details\n      operations:\n      - name: get-jobsite\n        method: GET\n        description: Get jobsite details with tool and battery inventory\n        inputParameters:\n        - name: jobsiteId\n          in: path\n          type: string\n          required: true\n          description: Jobsite identifier\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: users\n      path: /v1/users\n      description: User and team management\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users in the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jobsite-tool-management-api\n    description: Unified REST API for DEWALT jobsite tool and asset management.\n    resources:\n    - path: /v1/tools\n      name: tools\n      description: Connected tool inventory management\n      operations:\n      - method: GET\n        name: list-tools\n        description: List all connected DEWALT tools with status\n        call: tool-connect.list-tools\n        with:\n          jobsiteId: rest.jobsiteId\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/tools/{toolId}\n      name: tool\n      description: Get connected tool details\n      operations:\n      - method: GET\n        name: get-tool\n        description: Get tool details, firmware, and connectivity status\n        call: tool-connect.get-tool\n        with:\n          toolId: rest.toolId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tools/{toolId}/usage\n      name: tool-usage\n      description: Tool usage and runtime statistics\n      operations:\n      - method: GET\n        name: get-tool-usage\n        description: Get tool operational hours and usage patterns\n        call: tool-connect.get-tool-usage\n        with:\n          toolId: rest.toolId\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/batteries\n      name: batteries\n      description: Battery fleet health monitoring\n      operations:\n\
  \      - method: GET\n        name: list-batteries\n        description: List batteries with charge levels and health status\n        call: tool-connect.list-batteries\n        with:\n          jobsiteId: rest.jobsiteId\n          chargeStatus: rest.chargeStatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/batteries/{batteryId}\n      name: battery\n      description: Individual battery health details\n      operations:\n      - method: GET\n        name: get-battery\n        description: Get battery diagnostics including charge cycles and temperature\n        call: tool-connect.get-battery\n        with:\n          batteryId: rest.batteryId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets\n      name: assets\n      description: Full asset inventory\n      operations:\n      - method: GET\n        name: list-assets\n        description: List all tracked assets including tools, batteries, and\
  \ tags\n        call: tool-connect.list-assets\n        with:\n          type: rest.type\n          jobsiteId: rest.jobsiteId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: register-asset\n        description: Register a new asset by serial number\n        call: tool-connect.register-asset\n        with:\n          serialNumber: rest.serialNumber\n          type: rest.type\n          jobsiteId: rest.jobsiteId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobsites\n      name: jobsites\n      description: Jobsite project management\n      operations:\n      - method: GET\n        name: list-jobsites\n        description: List all configured jobsites with asset counts\n        call: tool-connect.list-jobsites\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-jobsite\n        description: Create a new jobsite for tool\
  \ tracking\n        call: tool-connect.create-jobsite\n        with:\n          name: rest.name\n          address: rest.address\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobsites/{jobsiteId}\n      name: jobsite\n      description: Jobsite inventory overview\n      operations:\n      - method: GET\n        name: get-jobsite\n        description: Get jobsite with full tool and battery inventory\n        call: tool-connect.get-jobsite\n        with:\n          jobsiteId: rest.jobsiteId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: Team and user management\n      operations:\n      - method: GET\n        name: list-users\n        description: List all organization users and their roles\n        call: tool-connect.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: jobsite-tool-management-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted DEWALT jobsite tool and asset management.\n    tools:\n    - name: list-tools\n      description: List all DEWALT connected tools registered to the account, filterable by jobsite or connectivity status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tool-connect.list-tools\n      with:\n        jobsiteId: tools.jobsiteId\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tool-details\n      description: Get DEWALT tool details including model, serial number, firmware version, and warranty information\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tool-connect.get-tool\n      with:\n        toolId: tools.toolId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tool-usage-stats\n      description: Analyze DEWALT tool runtime hours, trigger events, and usage patterns over\
  \ a date range\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tool-connect.get-tool-usage\n      with:\n        toolId: tools.toolId\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-batteries\n      description: List DEWALT battery fleet with charge levels, health status, and paired tool information\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tool-connect.list-batteries\n      with:\n        jobsiteId: tools.jobsiteId\n        chargeStatus: tools.chargeStatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-battery-health\n      description: Get detailed DEWALT battery diagnostics including charge cycles, temperature, and replacement recommendation\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tool-connect.get-battery\n      with:\n        batteryId: tools.batteryId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobsite-assets\n      description: View all tools, batteries, tags, and connectors tracked at a specific jobsite\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tool-connect.list-assets\n      with:\n        jobsiteId: tools.jobsiteId\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: register-asset\n      description: Register a new DEWALT tool, battery, or tag to the account by scanning its QR code or entering the serial\n        number\n      hints:\n        readOnly: false\n        destructive: false\n      call: tool-connect.register-asset\n      with:\n        serialNumber: tools.serialNumber\n        type: tools.type\n        jobsiteId: tools.jobsiteId\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-jobsite-inventory\n      description: Get full DEWALT\
  \ tool and battery inventory for a jobsite including user assignments and asset counts\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tool-connect.get-jobsite\n      with:\n        jobsiteId: tools.jobsiteId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobsites\n      description: List all configured DEWALT Tool Connect jobsites with asset and user counts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tool-connect.list-jobsites\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-jobsite\n      description: Create a new DEWALT Tool Connect jobsite for organizing tool and asset tracking by project\n      hints:\n        readOnly: false\n        destructive: false\n      call: tool-connect.create-jobsite\n      with:\n        name: tools.name\n        address: tools.address\n        description: tools.description\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-team-members\n      description: List all users in the DEWALT Tool Connect organization with their roles and jobsite assignments\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tool-connect.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
