---
categories: []
consumed_apis: []
description: Unified workflow capability combining Tufin SecureTrack and SecureChange for end-to-end network security policy lifecycle management. Enables network security engineers and SOC analysts to analyze topology, query firewall rules, assess risk, and automate policy change workflows from a single interface. Ideal for firewall change automation, compliance auditing, and network access troubleshooting.
layout: capability
name: Tufin Network Security Policy Management
operations:
- description: List all network devices in SecureTrack
  method: GET
  name: get-devices
  path: /v1/devices
- description: Get firewall rules for a device
  method: GET
  name: get-device-rules
  path: /v1/devices/{deviceId}/rules
- description: Check if traffic is allowed between network endpoints
  method: GET
  name: check-path
  path: /v1/topology/path
- description: Search for network objects
  method: GET
  name: search-objects
  path: /v1/network-objects
- description: Get risk analysis findings
  method: GET
  name: get-risk
  path: /v1/risk
- description: List security change tickets
  method: GET
  name: get-tickets
  path: /v1/change-tickets
- description: Submit a security change request
  method: POST
  name: create-ticket
  path: /v1/change-tickets
- description: Get a specific change ticket
  method: GET
  name: get-ticket
  path: /v1/change-tickets/{ticketId}
- description: Get a workflow task
  method: GET
  name: get-task
  path: /v1/change-tickets/{ticketId}/tasks/{taskId}
- description: Update a workflow task
  method: PUT
  name: update-task
  path: /v1/change-tickets/{ticketId}/tasks/{taskId}
personas: []
provider_name: Tufin
provider_slug: tufin
search_terms:
- submit a new firewall rule change request to securechange workflow
- get policy revision history for a network device
- get a workflow task
- get risk findings
- security policy change tickets
- risk analysis and policy compliance findings
- firewall management
- get change ticket
- firewall rules for a network device
- workflow task in a change ticket
- search for network objects
- get risk
- create ticket
- check network path
- get topology map
- search network objects
- get security risk analysis findings including policy violations and unused rules
- list all network devices (firewalls) managed by tufin securetrack
- list security policy change tickets in securechange
- update a workflow task
- policy orchestration
- get firewall rules for a device
- search services
- risk management
- list devices
- get device rules
- get task
- compliance
- network topology path analysis
- submit a security change request
- check path
- search for service definitions across managed devices
- update task
- list change tickets
- create change ticket
- cloud security
- network security
- single security change ticket
- change management
- check if traffic is allowed between source and destination ip addresses
- security policy management
- get ticket
- approve or update a workflow task in a security change ticket
- approve change task
- network objects across managed devices
- list all network devices in securetrack
- workflow automation
- check if traffic is allowed between network endpoints
- search for network objects (ips, ranges, groups) across all managed devices
- zero trust
- get tickets
- get a specific change ticket
- retrieve the full network topology map from securetrack
- get ticket tasks
- network devices managed by securetrack
- list device revisions
- get devices
- get workflow tasks for a change ticket
- network topology
- get details for a specific security change ticket
- tufin
- get risk analysis findings
- list security change tickets
- search objects
- get firewall rules for a specific network device
slug: network-security-policy-management
source_filename: network-security-policy-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tufin Network Security Policy Management\n  description: Unified workflow capability combining Tufin SecureTrack and SecureChange for end-to-end network security policy\n    lifecycle management. Enables network security engineers and SOC analysts to analyze topology, query firewall rules, assess\n    risk, and automate policy change workflows from a single interface. Ideal for firewall change automation, compliance auditing,\n    and network access troubleshooting.\n  tags:\n  - Change Management\n  - Compliance\n  - Firewall Management\n  - Network Security\n  - Policy Orchestration\n  - Risk Management\n  - Tufin\n  - Workflow Automation\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SECURETRACK_USERNAME: SECURETRACK_USERNAME\n    SECURETRACK_PASSWORD: SECURETRACK_PASSWORD\n    SECURECHANGE_USERNAME: SECURECHANGE_USERNAME\n    SECURECHANGE_PASSWORD: SECURECHANGE_PASSWORD\ncapability:\n  consumes:\n\
  \  - type: http\n    namespace: securetrack\n    baseUri: https://{tos_host}/securetrack/api\n    description: Tufin SecureTrack REST API for network security policy management\n    authentication:\n      type: basic\n      username: '{{SECURETRACK_USERNAME}}'\n      password: '{{SECURETRACK_PASSWORD}}'\n    resources:\n    - name: devices\n      path: /devices\n      description: Network devices managed by SecureTrack\n      operations:\n      - name: get-devices\n        method: GET\n        description: Retrieve all network devices managed by SecureTrack\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Filter by device name\n        - name: vendor\n          in: query\n          type: string\n          required: false\n          description: Filter by vendor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: device\n      path: /devices/{deviceId}\n      description: Single network device\n      operations:\n      - name: get-device-by-id\n        method: GET\n        description: Retrieve a specific network device by ID\n        inputParameters:\n        - name: deviceId\n          in: path\n          type: integer\n          required: true\n          description: Device identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: device-revisions\n      path: /devices/{deviceId}/revisions\n      description: Policy revisions for a device\n      operations:\n      - name: get-device-revisions\n        method: GET\n        description: Retrieve policy revision history for a device\n        inputParameters:\n        - name: deviceId\n          in: path\n          type: integer\n          required: true\n          description: Device identifier\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: device-rules\n      path: /devices/{deviceId}/rules\n      description: Firewall rules for a device\n      operations:\n      - name: get-rules-by-device\n        method: GET\n        description: Retrieve all firewall rules for a specific device\n        inputParameters:\n        - name: deviceId\n          in: path\n          type: integer\n          required: true\n          description: Device identifier\n        - name: policy\n          in: query\n          type: string\n          required: false\n          description: Filter by policy name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: topology-path\n      path: /topology/path\n      description: Network path analysis\n      operations:\n      - name: get-topology-path\n        method: GET\n        description: Query network topology to determine if traffic\
  \ is permitted between endpoints\n        inputParameters:\n        - name: src\n          in: query\n          type: string\n          required: true\n          description: Source IP address or CIDR\n        - name: dst\n          in: query\n          type: string\n          required: true\n          description: Destination IP address or CIDR\n        - name: service\n          in: query\n          type: string\n          required: false\n          description: Service (e.g., tcp/443)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: topology-map\n      path: /topology/map\n      description: Full network topology map\n      operations:\n      - name: get-topology-map\n        method: GET\n        description: Retrieve the full network topology map\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: network-objects\n\
  \      path: /network_objects\n      description: Network objects across managed devices\n      operations:\n      - name: get-network-objects\n        method: GET\n        description: Search for network objects across all managed devices\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Filter by object name\n        - name: ip\n          in: query\n          type: string\n          required: false\n          description: Filter by IP address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services\n      path: /services\n      description: Service objects across managed devices\n      operations:\n      - name: get-services\n        method: GET\n        description: Search for service objects across all managed devices\n        inputParameters:\n        - name: name\n          in: query\n          type:\
  \ string\n          required: false\n          description: Filter by service name\n        - name: port\n          in: query\n          type: string\n          required: false\n          description: Filter by port number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: zones\n      path: /zones\n      description: Security zones\n      operations:\n      - name: get-zones\n        method: GET\n        description: Retrieve all security zones\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: risk\n      path: /risk\n      description: Risk analysis findings\n      operations:\n      - name: get-risk-analysis\n        method: GET\n        description: Retrieve risk analysis findings including policy violations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n  - type: http\n    namespace: securechange\n    baseUri: https://{tos_host}/securechangeworkflow/api/securechange\n    description: Tufin SecureChange REST API for security policy change workflows\n    authentication:\n      type: basic\n      username: '{{SECURECHANGE_USERNAME}}'\n      password: '{{SECURECHANGE_PASSWORD}}'\n    resources:\n    - name: tickets\n      path: /tickets\n      description: Security change tickets\n      operations:\n      - name: get-tickets\n        method: GET\n        description: Retrieve security change tickets with optional status filtering\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by ticket status\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Number of tickets to return\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n      - name: create-ticket\n        method: POST\n        description: Submit a new security change ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            subject: '{{tools.subject}}'\n            description: '{{tools.description}}'\n            priority: '{{tools.priority}}'\n            workflow: '{{tools.workflow}}'\n    - name: ticket\n      path: /tickets/{ticketId}\n      description: Single change ticket\n      operations:\n      - name: get-ticket-by-id\n        method: GET\n        description: Retrieve a specific security change ticket\n        inputParameters:\n        - name: ticketId\n          in: path\n          type: integer\n          required: true\n          description: Ticket identifier\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: update-ticket\n        method: PUT\n        description: Update an existing change ticket\n        inputParameters:\n        - name: ticketId\n          in: path\n          type: integer\n          required: true\n          description: Ticket identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            subject: '{{tools.subject}}'\n            description: '{{tools.description}}'\n    - name: ticket-tasks\n      path: /tickets/{ticketId}/tasks\n      description: Workflow tasks for a ticket\n      operations:\n      - name: get-ticket-tasks\n        method: GET\n        description: Retrieve all workflow tasks for a ticket\n        inputParameters:\n        - name: ticketId\n          in: path\n          type: integer\n          required: true\n          description: Ticket identifier\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ticket-task\n      path: /tickets/{ticketId}/tasks/{taskId}\n      description: Single workflow task\n      operations:\n      - name: get-task-by-id\n        method: GET\n        description: Retrieve a specific workflow task\n        inputParameters:\n        - name: ticketId\n          in: path\n          type: integer\n          required: true\n          description: Ticket identifier\n        - name: taskId\n          in: path\n          type: integer\n          required: true\n          description: Task identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-task\n        method: PUT\n        description: Update a workflow task (approve, reject, or provide implementation)\n        inputParameters:\n        - name: ticketId\n          in: path\n\
  \          type: integer\n          required: true\n          description: Ticket identifier\n        - name: taskId\n          in: path\n          type: integer\n          required: true\n          description: Task identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n            comment: '{{tools.comment}}'\n    - name: workflow-definitions\n      path: /workflow_definitions\n      description: Workflow template definitions\n      operations:\n      - name: get-workflow-definitions\n        method: GET\n        description: Retrieve all workflow definitions configured in SecureChange\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: network-policy-api\n    description: Unified\
  \ REST API for Tufin network security policy management.\n    resources:\n    - path: /v1/devices\n      name: devices\n      description: Network devices managed by SecureTrack\n      operations:\n      - method: GET\n        name: get-devices\n        description: List all network devices in SecureTrack\n        call: securetrack.get-devices\n        with:\n          vendor: rest.vendor\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices/{deviceId}/rules\n      name: device-rules\n      description: Firewall rules for a network device\n      operations:\n      - method: GET\n        name: get-device-rules\n        description: Get firewall rules for a device\n        call: securetrack.get-rules-by-device\n        with:\n          deviceId: rest.deviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/topology/path\n      name: topology-path\n      description: Network\
  \ topology path analysis\n      operations:\n      - method: GET\n        name: check-path\n        description: Check if traffic is allowed between network endpoints\n        call: securetrack.get-topology-path\n        with:\n          src: rest.src\n          dst: rest.dst\n          service: rest.service\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/network-objects\n      name: network-objects\n      description: Network objects across managed devices\n      operations:\n      - method: GET\n        name: search-objects\n        description: Search for network objects\n        call: securetrack.get-network-objects\n        with:\n          name: rest.name\n          ip: rest.ip\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/risk\n      name: risk\n      description: Risk analysis and policy compliance findings\n      operations:\n      - method: GET\n        name: get-risk\n        description:\
  \ Get risk analysis findings\n        call: securetrack.get-risk-analysis\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/change-tickets\n      name: change-tickets\n      description: Security policy change tickets\n      operations:\n      - method: GET\n        name: get-tickets\n        description: List security change tickets\n        call: securechange.get-tickets\n        with:\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-ticket\n        description: Submit a security change request\n        call: securechange.create-ticket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/change-tickets/{ticketId}\n      name: change-ticket\n      description: Single security change ticket\n      operations:\n      - method: GET\n        name: get-ticket\n        description: Get a specific change ticket\n  \
  \      call: securechange.get-ticket-by-id\n        with:\n          ticketId: rest.ticketId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/change-tickets/{ticketId}/tasks/{taskId}\n      name: change-ticket-task\n      description: Workflow task in a change ticket\n      operations:\n      - method: GET\n        name: get-task\n        description: Get a workflow task\n        call: securechange.get-task-by-id\n        with:\n          ticketId: rest.ticketId\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-task\n        description: Update a workflow task\n        call: securechange.update-task\n        with:\n          ticketId: rest.ticketId\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: network-policy-mcp\n    transport: http\n    description:\
  \ MCP server for AI-assisted Tufin network security policy management.\n    tools:\n    - name: list-devices\n      description: List all network devices (firewalls) managed by Tufin SecureTrack\n      hints:\n        readOnly: true\n        openWorld: true\n      call: securetrack.get-devices\n      with:\n        vendor: tools.vendor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-device-rules\n      description: Get firewall rules for a specific network device\n      hints:\n        readOnly: true\n        openWorld: false\n      call: securetrack.get-rules-by-device\n      with:\n        deviceId: tools.deviceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-network-path\n      description: Check if traffic is allowed between source and destination IP addresses\n      hints:\n        readOnly: true\n        openWorld: false\n      call: securetrack.get-topology-path\n      with:\n        src: tools.src\n \
  \       dst: tools.dst\n        service: tools.service\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-topology-map\n      description: Retrieve the full network topology map from SecureTrack\n      hints:\n        readOnly: true\n        openWorld: true\n      call: securetrack.get-topology-map\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-network-objects\n      description: Search for network objects (IPs, ranges, groups) across all managed devices\n      hints:\n        readOnly: true\n        openWorld: true\n      call: securetrack.get-network-objects\n      with:\n        name: tools.name\n        ip: tools.ip\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-services\n      description: Search for service definitions across managed devices\n      hints:\n        readOnly: true\n        openWorld: true\n      call: securetrack.get-services\n      with:\n        name:\
  \ tools.name\n        port: tools.port\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-risk-findings\n      description: Get security risk analysis findings including policy violations and unused rules\n      hints:\n        readOnly: true\n        openWorld: true\n      call: securetrack.get-risk-analysis\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-change-tickets\n      description: List security policy change tickets in SecureChange\n      hints:\n        readOnly: true\n        openWorld: true\n      call: securechange.get-tickets\n      with:\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-change-ticket\n      description: Submit a new firewall rule change request to SecureChange workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: securechange.create-ticket\n      with:\n\
  \        subject: tools.subject\n        description: tools.description\n        priority: tools.priority\n        workflow: tools.workflow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-change-ticket\n      description: Get details for a specific security change ticket\n      hints:\n        readOnly: true\n        openWorld: false\n      call: securechange.get-ticket-by-id\n      with:\n        ticketId: tools.ticketId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ticket-tasks\n      description: Get workflow tasks for a change ticket\n      hints:\n        readOnly: true\n        openWorld: false\n      call: securechange.get-ticket-tasks\n      with:\n        ticketId: tools.ticketId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: approve-change-task\n      description: Approve or update a workflow task in a security change ticket\n      hints:\n        readOnly: false\n  \
  \      destructive: false\n        idempotent: false\n      call: securechange.update-task\n      with:\n        ticketId: tools.ticketId\n        taskId: tools.taskId\n        status: tools.status\n        comment: tools.comment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-device-revisions\n      description: Get policy revision history for a network device\n      hints:\n        readOnly: true\n        openWorld: false\n      call: securetrack.get-device-revisions\n      with:\n        deviceId: tools.deviceId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tufin/refs/heads/main/capabilities/network-security-policy-management.yaml
tags:
- Change Management
- Compliance
- Firewall Management
- Network Security
- Policy Orchestration
- Risk Management
- Tufin
- Workflow Automation
tools:
- description: List all network devices (firewalls) managed by Tufin SecureTrack
  hints:
    openWorld: true
    readOnly: true
  name: list-devices
- description: Get firewall rules for a specific network device
  hints:
    openWorld: false
    readOnly: true
  name: get-device-rules
- description: Check if traffic is allowed between source and destination IP addresses
  hints:
    openWorld: false
    readOnly: true
  name: check-network-path
- description: Retrieve the full network topology map from SecureTrack
  hints:
    openWorld: true
    readOnly: true
  name: get-topology-map
- description: Search for network objects (IPs, ranges, groups) across all managed devices
  hints:
    openWorld: true
    readOnly: true
  name: search-network-objects
- description: Search for service definitions across managed devices
  hints:
    openWorld: true
    readOnly: true
  name: search-services
- description: Get security risk analysis findings including policy violations and unused rules
  hints:
    openWorld: true
    readOnly: true
  name: get-risk-findings
- description: List security policy change tickets in SecureChange
  hints:
    openWorld: true
    readOnly: true
  name: list-change-tickets
- description: Submit a new firewall rule change request to SecureChange workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-change-ticket
- description: Get details for a specific security change ticket
  hints:
    openWorld: false
    readOnly: true
  name: get-change-ticket
- description: Get workflow tasks for a change ticket
  hints:
    openWorld: false
    readOnly: true
  name: get-ticket-tasks
- description: Approve or update a workflow task in a security change ticket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: approve-change-task
- description: Get policy revision history for a network device
  hints:
    openWorld: false
    readOnly: true
  name: list-device-revisions
---
