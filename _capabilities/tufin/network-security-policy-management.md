---
categories: []
consumed_apis:
- securetrack
- securechange
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
- approve change task
- check path
- risk analysis and policy compliance findings
- list all network devices (firewalls) managed by tufin securetrack
- get tickets
- check network path
- list all network devices in securetrack
- search network objects
- create change ticket
- get details for a specific security change ticket
- submit a security change request
- cloud security
- submit a new firewall rule change request to securechange workflow
- firewall rules for a network device
- update task
- risk management
- update a workflow task
- get risk
- get change ticket
- list security policy change tickets in securechange
- create ticket
- list devices
- get firewall rules for a device
- search for network objects (ips, ranges, groups) across all managed devices
- tufin
- get risk analysis findings
- get a specific change ticket
- check if traffic is allowed between network endpoints
- get firewall rules for a specific network device
- check if traffic is allowed between source and destination ip addresses
- get ticket tasks
- network topology path analysis
- approve or update a workflow task in a security change ticket
- list security change tickets
- get devices
- get ticket
- search services
- get risk findings
- single security change ticket
- list device revisions
- search for network objects
- network security
- zero trust
- security policy management
- get device rules
- change management
- search for service definitions across managed devices
- list change tickets
- network devices managed by securetrack
- firewall management
- get task
- compliance
- get topology map
- get workflow tasks for a change ticket
- get security risk analysis findings including policy violations and unused rules
- get policy revision history for a network device
- workflow task in a change ticket
- policy orchestration
- network topology
- search objects
- workflow automation
- security policy change tickets
- retrieve the full network topology map from securetrack
- get a workflow task
- network objects across managed devices
slug: network-security-policy-management
source_filename: network-security-policy-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tufin Network Security Policy Management\"\n  description: >-\n    Unified workflow capability combining Tufin SecureTrack and SecureChange for\n    end-to-end network security policy lifecycle management. Enables network security\n    engineers and SOC analysts to analyze topology, query firewall rules, assess risk,\n    and automate policy change workflows from a single interface. Ideal for firewall\n    change automation, compliance auditing, and network access troubleshooting.\n  tags:\n    - Change Management\n    - Compliance\n    - Firewall Management\n    - Network Security\n    - Policy Orchestration\n    - Risk Management\n    - Tufin\n    - Workflow Automation\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      SECURETRACK_USERNAME: SECURETRACK_USERNAME\n      SECURETRACK_PASSWORD: SECURETRACK_PASSWORD\n      SECURECHANGE_USERNAME: SECURECHANGE_USERNAME\n      SECURECHANGE_PASSWORD:\
  \ SECURECHANGE_PASSWORD\n\ncapability:\n  consumes:\n    - import: securetrack\n      location: ./shared/securetrack.yaml\n    - import: securechange\n      location: ./shared/securechange.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: network-policy-api\n      description: \"Unified REST API for Tufin network security policy management.\"\n      resources:\n        - path: /v1/devices\n          name: devices\n          description: \"Network devices managed by SecureTrack\"\n          operations:\n            - method: GET\n              name: get-devices\n              description: \"List all network devices in SecureTrack\"\n              call: \"securetrack.get-devices\"\n              with:\n                vendor: \"rest.vendor\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/devices/{deviceId}/rules\n          name: device-rules\n          description:\
  \ \"Firewall rules for a network device\"\n          operations:\n            - method: GET\n              name: get-device-rules\n              description: \"Get firewall rules for a device\"\n              call: \"securetrack.get-rules-by-device\"\n              with:\n                deviceId: \"rest.deviceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/topology/path\n          name: topology-path\n          description: \"Network topology path analysis\"\n          operations:\n            - method: GET\n              name: check-path\n              description: \"Check if traffic is allowed between network endpoints\"\n              call: \"securetrack.get-topology-path\"\n              with:\n                src: \"rest.src\"\n                dst: \"rest.dst\"\n                service: \"rest.service\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n\n        - path: /v1/network-objects\n          name: network-objects\n          description: \"Network objects across managed devices\"\n          operations:\n            - method: GET\n              name: search-objects\n              description: \"Search for network objects\"\n              call: \"securetrack.get-network-objects\"\n              with:\n                name: \"rest.name\"\n                ip: \"rest.ip\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/risk\n          name: risk\n          description: \"Risk analysis and policy compliance findings\"\n          operations:\n            - method: GET\n              name: get-risk\n              description: \"Get risk analysis findings\"\n              call: \"securetrack.get-risk-analysis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/change-tickets\n          name:\
  \ change-tickets\n          description: \"Security policy change tickets\"\n          operations:\n            - method: GET\n              name: get-tickets\n              description: \"List security change tickets\"\n              call: \"securechange.get-tickets\"\n              with:\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-ticket\n              description: \"Submit a security change request\"\n              call: \"securechange.create-ticket\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/change-tickets/{ticketId}\n          name: change-ticket\n          description: \"Single security change ticket\"\n          operations:\n            - method: GET\n              name: get-ticket\n              description: \"Get a specific change ticket\"\n     \
  \         call: \"securechange.get-ticket-by-id\"\n              with:\n                ticketId: \"rest.ticketId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/change-tickets/{ticketId}/tasks/{taskId}\n          name: change-ticket-task\n          description: \"Workflow task in a change ticket\"\n          operations:\n            - method: GET\n              name: get-task\n              description: \"Get a workflow task\"\n              call: \"securechange.get-task-by-id\"\n              with:\n                ticketId: \"rest.ticketId\"\n                taskId: \"rest.taskId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-task\n              description: \"Update a workflow task\"\n              call: \"securechange.update-task\"\n              with:\n                ticketId: \"rest.ticketId\"\n\
  \                taskId: \"rest.taskId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: network-policy-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Tufin network security policy management.\"\n      tools:\n        - name: list-devices\n          description: \"List all network devices (firewalls) managed by Tufin SecureTrack\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"securetrack.get-devices\"\n          with:\n            vendor: \"tools.vendor\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-device-rules\n          description: \"Get firewall rules for a specific network device\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"securetrack.get-rules-by-device\"\n          with:\n       \
  \     deviceId: \"tools.deviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-network-path\n          description: \"Check if traffic is allowed between source and destination IP addresses\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"securetrack.get-topology-path\"\n          with:\n            src: \"tools.src\"\n            dst: \"tools.dst\"\n            service: \"tools.service\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-topology-map\n          description: \"Retrieve the full network topology map from SecureTrack\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"securetrack.get-topology-map\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-network-objects\n          description: \"Search\
  \ for network objects (IPs, ranges, groups) across all managed devices\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"securetrack.get-network-objects\"\n          with:\n            name: \"tools.name\"\n            ip: \"tools.ip\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-services\n          description: \"Search for service definitions across managed devices\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"securetrack.get-services\"\n          with:\n            name: \"tools.name\"\n            port: \"tools.port\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-risk-findings\n          description: \"Get security risk analysis findings including policy violations and unused rules\"\n          hints:\n            readOnly: true\n            openWorld: true\n\
  \          call: \"securetrack.get-risk-analysis\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-change-tickets\n          description: \"List security policy change tickets in SecureChange\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"securechange.get-tickets\"\n          with:\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-change-ticket\n          description: \"Submit a new firewall rule change request to SecureChange workflow\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"securechange.create-ticket\"\n          with:\n            subject: \"tools.subject\"\n            description: \"tools.description\"\n            priority: \"tools.priority\"\n            workflow: \"tools.workflow\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-change-ticket\n          description: \"Get details for a specific security change ticket\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"securechange.get-ticket-by-id\"\n          with:\n            ticketId: \"tools.ticketId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-ticket-tasks\n          description: \"Get workflow tasks for a change ticket\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"securechange.get-ticket-tasks\"\n          with:\n            ticketId: \"tools.ticketId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: approve-change-task\n          description: \"Approve or update a workflow task in a security change ticket\"\n          hints:\n\
  \            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"securechange.update-task\"\n          with:\n            ticketId: \"tools.ticketId\"\n            taskId: \"tools.taskId\"\n            status: \"tools.status\"\n            comment: \"tools.comment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-device-revisions\n          description: \"Get policy revision history for a network device\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"securetrack.get-device-revisions\"\n          with:\n            deviceId: \"tools.deviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
