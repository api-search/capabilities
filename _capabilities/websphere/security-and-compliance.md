---
categories:
- security
consumed_apis: []
description: Workflow for security vulnerability management, automated patching, compliance reporting, and health monitoring across WebSphere environments for security engineers and compliance teams.
layout: capability
name: WebSphere Security and Compliance
operations:
- description: List known vulnerabilities
  method: GET
  name: list-vulnerabilities
  path: /v1/vulnerabilities
- description: Get vulnerability details
  method: GET
  name: get-vulnerability
  path: /v1/vulnerabilities
- description: List available fixes
  method: GET
  name: list-fixes
  path: /v1/fixes
- description: List compliance reports
  method: GET
  name: list-compliance-reports
  path: /v1/compliance
- description: Get overall health status
  method: GET
  name: get-overall-health
  path: /v1/health
- description: List security users
  method: GET
  name: list-users
  path: /v1/security-users
personas: []
provider_name: IBM WebSphere
provider_slug: websphere
search_terms:
- list vulnerabilities
- health monitoring
- list available security fixes
- list managed servers
- get overall health
- get server health
- list fixes
- middleware
- apply fix
- initiate vulnerability resolution
- j2ee
- cloud native
- get vulnerability
- security user management
- compliance
- fix and patch management
- list users
- compliance reporting
- resolve vulnerability
- get vulnerability details
- get individual server health
- vulnerability tracking and remediation
- list known security vulnerabilities
- list servers managed by websphere automation
- get overall health status
- get overall environment health
- list available fixes
- enterprise java
- list known vulnerabilities
- list compliance reports
- application server
- vulnerability management
- apply a fix to managed servers
- microservices
- security
- ibm websphere
- list security users
slug: security-and-compliance
source_filename: security-and-compliance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WebSphere Security and Compliance\n  description: Workflow for security vulnerability management, automated patching, compliance reporting, and health monitoring\n    across WebSphere environments for security engineers and compliance teams.\n  tags:\n  - IBM WebSphere\n  - Security\n  - Compliance\n  - Vulnerability Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WEBSPHERE_AUTOMATION_TOKEN: WEBSPHERE_AUTOMATION_TOKEN\n    WEBSPHERE_USERNAME: WEBSPHERE_USERNAME\n    WEBSPHERE_PASSWORD: WEBSPHERE_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: automation\n    baseUri: https://automation-api.example.com/v1\n    description: WebSphere Automation REST API for vulnerability and fix management\n    authentication:\n      type: bearer\n      token: '{{WEBSPHERE_AUTOMATION_TOKEN}}'\n    resources:\n    - name: servers\n      path: /servers\n      description: Managed server\
  \ inventory\n      operations:\n      - name: list-managed-servers\n        method: GET\n        description: List managed servers\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by server type\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: register-server\n        method: POST\n        description: Register a server for management\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n      - name: get-managed-server\n        method: GET\n        description: Get\
  \ managed server details\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description: Server identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deregister-server\n        method: DELETE\n        description: Deregister a server\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description: Server identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vulnerabilities\n      path: /vulnerabilities\n      description: Vulnerability tracking\n      operations:\n      - name: list-vulnerabilities\n        method: GET\n        description: List known vulnerabilities\n        inputParameters:\n        - name: severity\n          in:\
  \ query\n          type: string\n          required: false\n          description: Filter by severity\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by remediation status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-vulnerability\n        method: GET\n        description: Get vulnerability details\n        inputParameters:\n        - name: vulnerabilityId\n          in: path\n          type: string\n          required: true\n          description: Vulnerability identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: resolve-vulnerability\n        method: POST\n        description: Initiate vulnerability resolution\n        inputParameters:\n        - name: vulnerabilityId\n          in: path\n          type: string\n\
  \          required: true\n          description: Vulnerability identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fixes\n      path: /fixes\n      description: Fix management\n      operations:\n      - name: list-fixes\n        method: GET\n        description: List available fixes\n        inputParameters:\n        - name: serverId\n          in: query\n          type: string\n          required: false\n          description: Filter by applicable server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-fix\n        method: GET\n        description: Get fix details\n        inputParameters:\n        - name: fixId\n          in: path\n          type: string\n          required: true\n          description: Fix identifier\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: apply-fix\n        method: POST\n        description: Apply a fix to servers\n        inputParameters:\n        - name: fixId\n          in: path\n          type: string\n          required: true\n          description: Fix identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /health\n      description: Health monitoring\n      operations:\n      - name: get-overall-health\n        method: GET\n        description: Get overall health status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-server-health\n        method: GET\n        description: Get server health status\n        inputParameters:\n        - name: serverId\n          in: path\n          type: string\n          required: true\n          description:\
  \ Server identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliance\n      path: /compliance/reports\n      description: Compliance reporting\n      operations:\n      - name: list-compliance-reports\n        method: GET\n        description: List compliance reports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-compliance-report\n        method: GET\n        description: Get compliance report details\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Report identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: admin-rest\n    baseUri: https://localhost:9443/ibm/api\n    description:\
  \ REST API for WebSphere Application Server administration\n    authentication:\n      type: basic\n      username: '{{WEBSPHERE_USERNAME}}'\n      password: '{{WEBSPHERE_PASSWORD}}'\n    resources:\n    - name: applications\n      path: /applications\n      description: Application deployment and lifecycle management\n      operations:\n      - name: list-applications\n        method: GET\n        description: List deployed applications\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by application status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-application\n        method: GET\n        description: Get application details\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deploy-application\n        method: POST\n        description: Deploy a new application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            contextRoot: '{{tools.contextRoot}}'\n            targetServer: '{{tools.targetServer}}'\n      - name: start-application\n        method: POST\n        description: Start a deployed application\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-application\n        method: POST\n\
  \        description: Stop a running application\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uninstall-application\n        method: DELETE\n        description: Uninstall a deployed application\n        inputParameters:\n        - name: appName\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: servers\n      path: /servers\n      description: Server configuration and management\n      operations:\n      - name: list-servers\n        method: GET\n        description: List all servers in the cell\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-server\n        method: GET\n        description: Get server details\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Server name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-server\n        method: POST\n        description: Start a server\n        inputParameters:\n        - name: serverName\n          in: path\n          type: string\n          required: true\n          description: Server name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-server\n        method: POST\n        description: Stop a server\n        inputParameters:\n        - name: serverName\n          in: path\n\
  \          type: string\n          required: true\n          description: Server name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters\n      path: /clusters\n      description: Cluster management operations\n      operations:\n      - name: list-clusters\n        method: GET\n        description: List all clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-cluster\n        method: GET\n        description: Get cluster details\n        inputParameters:\n        - name: clusterName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-cluster\n        method: POST\n        description: Start\
  \ all members of a cluster\n        inputParameters:\n        - name: clusterName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-cluster\n        method: POST\n        description: Stop all members of a cluster\n        inputParameters:\n        - name: clusterName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitoring\n      path: /monitoring\n      description: Performance monitoring and health checks\n      operations:\n      - name: get-performance-data\n        method: GET\n        description: Get performance monitoring data\n        inputParameters:\n        - name: module\n \
  \         in: query\n          type: string\n          required: false\n          description: Performance module name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-health-status\n        method: GET\n        description: Get server health status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration\n      path: /config\n      description: Server configuration management\n      operations:\n      - name: list-config-resources\n        method: GET\n        description: List configuration resource types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-config-resources\n        method: GET\n        description: List resources of a specific type\n        inputParameters:\n        - name: resourceType\n\
  \          in: path\n          type: string\n          required: true\n          description: Configuration resource type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: security-compliance-api\n    description: Unified REST API for WebSphere security and compliance operations.\n    resources:\n    - path: /v1/vulnerabilities\n      name: vulnerabilities\n      description: Vulnerability tracking and remediation\n      operations:\n      - method: GET\n        name: list-vulnerabilities\n        description: List known vulnerabilities\n        call: automation.list-vulnerabilities\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-vulnerability\n        description: Get vulnerability details\n        call: automation.get-vulnerability\n        with:\n          vulnerabilityId: rest.vulnerabilityId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fixes\n      name: fixes\n      description: Fix and patch management\n      operations:\n      - method: GET\n        name: list-fixes\n        description: List available fixes\n        call: automation.list-fixes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/compliance\n      name: compliance\n      description: Compliance reporting\n      operations:\n      - method: GET\n        name: list-compliance-reports\n        description: List compliance reports\n        call: automation.list-compliance-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/health\n      name: health\n      description: Health monitoring\n      operations:\n      - method: GET\n        name: get-overall-health\n        description: Get overall health status\n        call: automation.get-overall-health\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/security-users\n      name: security-users\n      description: Security user management\n      operations:\n      - method: GET\n        name: list-users\n        description: List security users\n        call: admin-rest.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: security-compliance-mcp\n    transport: http\n    description: MCP server for AI-assisted WebSphere security and compliance.\n    tools:\n    - name: list-vulnerabilities\n      description: List known security vulnerabilities\n      hints:\n        readOnly: true\n      call: automation.list-vulnerabilities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vulnerability\n      description: Get vulnerability details\n      hints:\n        readOnly: true\n      call: automation.get-vulnerability\n      with:\n        vulnerabilityId: tools.vulnerabilityId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resolve-vulnerability\n      description: Initiate vulnerability resolution\n      hints:\n        readOnly: false\n      call: automation.resolve-vulnerability\n      with:\n        vulnerabilityId: tools.vulnerabilityId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-fixes\n      description: List available security fixes\n      hints:\n        readOnly: true\n      call: automation.list-fixes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: apply-fix\n      description: Apply a fix to managed servers\n      hints:\n        readOnly: false\n      call: automation.apply-fix\n      with:\n        fixId: tools.fixId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-overall-health\n      description: Get overall environment health\n      hints:\n        readOnly: true\n      call: automation.get-overall-health\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-server-health\n      description: Get individual server health\n      hints:\n        readOnly: true\n      call: automation.get-server-health\n      with:\n        serverId: tools.serverId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-compliance-reports\n      description: List compliance reports\n      hints:\n        readOnly: true\n      call: automation.list-compliance-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-managed-servers\n      description: List servers managed by WebSphere Automation\n      hints:\n        readOnly: true\n      call: automation.list-managed-servers\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/websphere/refs/heads/main/capabilities/security-and-compliance.yaml
tags:
- IBM WebSphere
- Security
- Compliance
- Vulnerability Management
tools:
- description: List known security vulnerabilities
  hints:
    readOnly: true
  name: list-vulnerabilities
- description: Get vulnerability details
  hints:
    readOnly: true
  name: get-vulnerability
- description: Initiate vulnerability resolution
  hints:
    readOnly: false
  name: resolve-vulnerability
- description: List available security fixes
  hints:
    readOnly: true
  name: list-fixes
- description: Apply a fix to managed servers
  hints:
    readOnly: false
  name: apply-fix
- description: Get overall environment health
  hints:
    readOnly: true
  name: get-overall-health
- description: Get individual server health
  hints:
    readOnly: true
  name: get-server-health
- description: List compliance reports
  hints:
    readOnly: true
  name: list-compliance-reports
- description: List servers managed by WebSphere Automation
  hints:
    readOnly: true
  name: list-managed-servers
---
