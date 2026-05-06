---
categories: []
consumed_apis: []
description: Unified workflow capability for IT asset management using Snow Atlas APIs. Combines software license management and SaaS application visibility to support SAM analysts, IT procurement teams, and FinOps practitioners in managing software spend, license compliance, and SaaS portfolio optimization. Covers license upgrades, policy management, computer license tracking, SaaS application discovery, and spend KPIs.
layout: capability
name: Snow Software IT Asset Management
operations:
- description: Get License Upgrades
  method: GET
  name: get-license-upgrades
  path: /v1/licenses/{id}/upgrades
- description: Get License Policies
  method: GET
  name: get-license-policies
  path: /v1/license-policies
- description: Get Computer License Tracking
  method: GET
  name: get-computer-license-tracking
  path: /v1/licenses/{id}/computer-tracking
- description: Get Applications
  method: GET
  name: get-saas-applications
  path: /v1/saas-applications
- description: Get Application KPIs
  method: GET
  name: get-application-kpis
  path: /v1/saas-applications/{id}/kpis
- description: Get Application Users
  method: GET
  name: get-application-users
  path: /v1/saas-applications/{id}/users
- description: Get Applications Overview KPIs
  method: GET
  name: get-saas-overview
  path: /v1/saas/overview
personas: []
provider_name: Snow Software
provider_slug: snow-software
search_terms:
- get license upgrades
- list configured license policies
- get available upgrade paths for a snow atlas software license
- cloud license management
- get application kpis
- get saas applications
- track which computers are using a license
- organization-wide saas portfolio overview
- get organization-wide saas portfolio kpis, total spend, and application count
- finops
- users with access to a saas application
- get applications overview kpis
- get computer license tracking
- saas management
- get saas portfolio overview
- get computer-level tracking for a specific software license in snow atlas
- list all discovered saas applications
- snow software
- list all saas applications discovered in the snow atlas portfolio
- it asset management
- software asset management
- get key performance indicators for a specific saas application including usage and spend
- get users with access to a specific saas application for license right-sizing
- get upgrade options for a software license
- get application users
- get applications
- get saas application kpis
- get saas application users
- saas application usage kpis
- list all software license policies configured in snow atlas
- get saas overview
- get license policies
- license compliance
slug: it-asset-management
source_filename: it-asset-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Snow Software IT Asset Management\n  description: Unified workflow capability for IT asset management using Snow Atlas APIs. Combines software license management\n    and SaaS application visibility to support SAM analysts, IT procurement teams, and FinOps practitioners in managing software\n    spend, license compliance, and SaaS portfolio optimization. Covers license upgrades, policy management, computer license\n    tracking, SaaS application discovery, and spend KPIs.\n  tags:\n  - FinOps\n  - IT Asset Management\n  - License Compliance\n  - SaaS Management\n  - Snow Software\n  - Software Asset Management\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SNOW_ACCESS_TOKEN: SNOW_ACCESS_TOKEN\n    SNOW_REGION: SNOW_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: snow-licenses\n    baseUri: https://{{SNOW_REGION}}.snowsoftware.io\n    description: Snow Atlas SAM Licenses API for\
  \ software license management\n    authentication:\n      type: bearer\n      token: '{{SNOW_ACCESS_TOKEN}}'\n    resources:\n    - name: license-upgrades\n      path: /api/sam/v1/licenses/{id}/upgrades\n      description: Get upgrade options for a license\n      operations:\n      - name: get-license-upgrades\n        method: GET\n        description: Get License Upgrades\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: License ID\n        - name: page_number\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Maximum items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: license-policies\n      path: /api/sam/v1/licenses/policies\n\
  \      description: List license policies\n      operations:\n      - name: get-license-policies\n        method: GET\n        description: Get License Policies\n        inputParameters:\n        - name: page_number\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: computer-license-tracking\n      path: /api/sam/v1/licenses/{id}/computers/tracking\n      description: Track license usage per computer\n      operations:\n      - name: get-computer-license-tracking\n        method: GET\n        description: Get Computer License Tracking\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n         \
  \ description: License ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snow-saas\n    baseUri: https://{{SNOW_REGION}}.snowsoftware.io\n    description: Snow Atlas SaaS Applications API for SaaS portfolio management\n    authentication:\n      type: bearer\n      token: '{{SNOW_ACCESS_TOKEN}}'\n    resources:\n    - name: saas-applications\n      path: /api/saas/v1/applications\n      description: List and manage SaaS applications\n      operations:\n      - name: get-saas-applications\n        method: GET\n        description: Get Applications\n        inputParameters:\n        - name: page_number\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        - name: filter\n          in:\
  \ query\n          type: string\n          required: false\n          description: Filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: saas-application-kpis\n      path: /api/saas/v1/applications/{id}/kpis\n      description: Application KPIs and usage metrics\n      operations:\n      - name: get-application-kpis\n        method: GET\n        description: Get Application KPIs\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Application ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: saas-application-users\n      path: /api/saas/v1/applications/{id}/users\n      description: Users with access to a SaaS application\n      operations:\n      - name: get-application-users\n        method: GET\n       \
  \ description: Get Application Users\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Application ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: saas-overview-kpis\n      path: /api/saas/v1/applications/overview/kpis\n      description: Organization-wide SaaS overview KPIs\n      operations:\n      - name: get-saas-overview-kpis\n        method: GET\n        description: Get Applications Overview KPIs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: snow-itam-api\n    description: Unified REST API for Snow Software IT asset management and SaaS portfolio visibility.\n    resources:\n    - path: /v1/licenses/{id}/upgrades\n      name: license-upgrades\n      description:\
  \ Get upgrade options for a software license\n      operations:\n      - method: GET\n        name: get-license-upgrades\n        description: Get License Upgrades\n        call: snow-licenses.get-license-upgrades\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/license-policies\n      name: license-policies\n      description: List configured license policies\n      operations:\n      - method: GET\n        name: get-license-policies\n        description: Get License Policies\n        call: snow-licenses.get-license-policies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/licenses/{id}/computer-tracking\n      name: computer-license-tracking\n      description: Track which computers are using a license\n      operations:\n      - method: GET\n        name: get-computer-license-tracking\n        description: Get Computer License Tracking\n        call: snow-licenses.get-computer-license-tracking\n\
  \        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/saas-applications\n      name: saas-applications\n      description: List all discovered SaaS applications\n      operations:\n      - method: GET\n        name: get-saas-applications\n        description: Get Applications\n        call: snow-saas.get-saas-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/saas-applications/{id}/kpis\n      name: saas-application-kpis\n      description: SaaS application usage KPIs\n      operations:\n      - method: GET\n        name: get-application-kpis\n        description: Get Application KPIs\n        call: snow-saas.get-application-kpis\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/saas-applications/{id}/users\n      name: saas-application-users\n      description: Users with access to\
  \ a SaaS application\n      operations:\n      - method: GET\n        name: get-application-users\n        description: Get Application Users\n        call: snow-saas.get-application-users\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/saas/overview\n      name: saas-overview\n      description: Organization-wide SaaS portfolio overview\n      operations:\n      - method: GET\n        name: get-saas-overview\n        description: Get Applications Overview KPIs\n        call: snow-saas.get-saas-overview-kpis\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: snow-itam-mcp\n    transport: http\n    description: MCP server for AI-assisted Snow Software IT asset management and SaaS portfolio analysis.\n    tools:\n    - name: get-license-upgrades\n      description: Get available upgrade paths for a Snow Atlas software license\n      hints:\n\
  \        readOnly: true\n        openWorld: false\n      call: snow-licenses.get-license-upgrades\n      with:\n        id: tools.license_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-license-policies\n      description: List all software license policies configured in Snow Atlas\n      hints:\n        readOnly: true\n        openWorld: false\n      call: snow-licenses.get-license-policies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-computer-license-tracking\n      description: Get computer-level tracking for a specific software license in Snow Atlas\n      hints:\n        readOnly: true\n        openWorld: false\n      call: snow-licenses.get-computer-license-tracking\n      with:\n        id: tools.license_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-saas-applications\n      description: List all SaaS applications discovered in the Snow Atlas portfolio\n     \
  \ hints:\n        readOnly: true\n        openWorld: false\n      call: snow-saas.get-saas-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-saas-application-kpis\n      description: Get key performance indicators for a specific SaaS application including usage and spend\n      hints:\n        readOnly: true\n        openWorld: false\n      call: snow-saas.get-application-kpis\n      with:\n        id: tools.application_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-saas-application-users\n      description: Get users with access to a specific SaaS application for license right-sizing\n      hints:\n        readOnly: true\n        openWorld: false\n      call: snow-saas.get-application-users\n      with:\n        id: tools.application_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-saas-portfolio-overview\n      description: Get organization-wide SaaS portfolio\
  \ KPIs, total spend, and application count\n      hints:\n        readOnly: true\n        openWorld: false\n      call: snow-saas.get-saas-overview-kpis\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snow-software/refs/heads/main/capabilities/it-asset-management.yaml
tags:
- FinOps
- IT Asset Management
- License Compliance
- SaaS Management
- Snow Software
- Software Asset Management
tools:
- description: Get available upgrade paths for a Snow Atlas software license
  hints:
    openWorld: false
    readOnly: true
  name: get-license-upgrades
- description: List all software license policies configured in Snow Atlas
  hints:
    openWorld: false
    readOnly: true
  name: get-license-policies
- description: Get computer-level tracking for a specific software license in Snow Atlas
  hints:
    openWorld: false
    readOnly: true
  name: get-computer-license-tracking
- description: List all SaaS applications discovered in the Snow Atlas portfolio
  hints:
    openWorld: false
    readOnly: true
  name: get-saas-applications
- description: Get key performance indicators for a specific SaaS application including usage and spend
  hints:
    openWorld: false
    readOnly: true
  name: get-saas-application-kpis
- description: Get users with access to a specific SaaS application for license right-sizing
  hints:
    openWorld: false
    readOnly: true
  name: get-saas-application-users
- description: Get organization-wide SaaS portfolio KPIs, total spend, and application count
  hints:
    openWorld: false
    readOnly: true
  name: get-saas-portfolio-overview
---
