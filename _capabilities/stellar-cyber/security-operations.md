---
categories: []
consumed_apis: []
description: Unified security operations workflow combining Stellar Cyber's Open XDR API capabilities for incident response, threat hunting, case management, and automated playbook execution. Designed for SOC analysts and security engineers who need to investigate alerts, manage cases, monitor sensors, and automate response actions.
layout: capability
name: Stellar Cyber Security Operations
operations:
- description: List security cases with optional status filtering
  method: GET
  name: list-cases
  path: /v1/cases
- description: Create a new security case for investigation
  method: POST
  name: create-case
  path: /v1/cases
- description: Retrieve details of a specific case
  method: GET
  name: get-case
  path: /v1/cases/{id}
- description: Update case status and attributes
  method: PUT
  name: update-case
  path: /v1/cases/{id}
- description: Retrieve security alerts with filtering
  method: GET
  name: list-alerts
  path: /v1/alerts
- description: Ingest security event documents
  method: POST
  name: ingest-events
  path: /v1/events
- description: Retrieve all watchlists
  method: GET
  name: list-watchlists
  path: /v1/watchlists
- description: Create a watchlist for threat tracking
  method: POST
  name: create-watchlist
  path: /v1/watchlists
- description: List all registered sensors
  method: GET
  name: list-sensors
  path: /v1/sensors
- description: List all ATH playbooks
  method: GET
  name: list-playbooks
  path: /v1/playbooks
- description: Create a new automated response playbook
  method: POST
  name: create-playbook
  path: /v1/playbooks
- description: Retrieve available security reports
  method: GET
  name: list-reports
  path: /v1/reports
- description: Generate a new security report
  method: POST
  name: create-report
  path: /v1/reports
personas: []
provider_name: Stellar Cyber
provider_slug: stellar-cyber
search_terms:
- create a new watchlist for tracking threat indicators such as malicious ips, domains, or file hashes.
- soc
- incident response
- retrieve all automated response playbooks. use to review available automation workflows for threat response.
- create case
- retrieve security cases from stellar cyber. use for investigating ongoing incidents and tracking case status.
- list all registered sensors
- retrieve details of a specific case
- ai
- ingest custom security event documents into stellar cyber for analysis and correlation.
- create report
- list all ath playbooks
- list reports
- get detailed information about a specific security case by id.
- security case management operations
- security alert management
- create a watchlist for threat tracking
- automated response playbooks
- retrieve available security reports
- create a new security case in stellar cyber. use when an alert or event requires formal investigation and tracking.
- list available security reports. use for compliance reporting and security posture reviews.
- threat watchlist management
- list sensors
- update a security case status, priority, or other attributes. use to progress cases through investigation workflows.
- security sensor monitoring
- individual case operations
- update case status and attributes
- generate a new security report
- security reporting
- xdr
- create a new ath playbook response action for automated threat response.
- list cases
- get case
- retrieve security alerts with filtering
- list alerts
- list all sensors registered with stellar cyber. use to check sensor health and coverage across the environment.
- ingest events
- soar
- threat hunting
- security event ingestion
- ingest security event documents
- generate a new security report for compliance or executive reporting.
- stellar cyber
- create watchlist
- cybersecurity
- retrieve all watchlists
- list security cases with optional status filtering
- create playbook
- create a new security case for investigation
- list watchlists
- security
- list playbooks
- create a new automated response playbook
- retrieve security alerts from stellar cyber open xdr. use for alert triage and identifying threats requiring investigation.
- siem
- retrieve all threat watchlists. use to check what indicators and entities are currently being monitored.
- update case
slug: security-operations
source_filename: security-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Stellar Cyber Security Operations\n  description: Unified security operations workflow combining Stellar Cyber's Open XDR API capabilities for incident response,\n    threat hunting, case management, and automated playbook execution. Designed for SOC analysts and security engineers who\n    need to investigate alerts, manage cases, monitor sensors, and automate response actions.\n  tags:\n  - Stellar Cyber\n  - Cybersecurity\n  - SOC\n  - Incident Response\n  - Threat Hunting\n  - SOAR\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STELLAR_CYBER_JWT_TOKEN: STELLAR_CYBER_JWT_TOKEN\n    STELLAR_CYBER_HOSTNAME: STELLAR_CYBER_HOSTNAME\ncapability:\n  consumes:\n  - type: http\n    namespace: stellar-cyber\n    baseUri: https://{{env.STELLAR_CYBER_HOSTNAME}}/connect/api/v1\n    description: Stellar Cyber Open XDR platform REST API\n    authentication:\n      type: bearer\n      token: '{{env.STELLAR_CYBER_JWT_TOKEN}}'\n\
  \    resources:\n    - name: authentication\n      path: /access_token\n      description: JWT token generation from API key\n      operations:\n      - name: get-access-token\n        method: POST\n        description: Generate a JWT access token using an API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases\n      path: /cases\n      description: Security case management\n      operations:\n      - name: list-cases\n        method: GET\n        description: Retrieve a list of security cases\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of cases to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: status\n          in: query\n          type: string\n          required:\
  \ false\n          description: Filter by status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-case\n        method: POST\n        description: Create a new security case\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            priority: '{{tools.priority}}'\n    - name: case\n      path: /cases/{caseId}\n      description: Individual case management\n      operations:\n      - name: get-case\n        method: GET\n        description: Retrieve details of a specific case\n        inputParameters:\n        - name: caseId\n          in: path\n          type: string\n          required: true\n          description: Unique case identifier\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-case\n        method: PUT\n        description: Update case status and attributes\n        inputParameters:\n        - name: caseId\n          in: path\n          type: string\n          required: true\n          description: Unique case identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n            priority: '{{tools.priority}}'\n    - name: tenants\n      path: /tenants\n      description: Multi-tenant administration\n      operations:\n      - name: list-tenants\n        method: GET\n        description: Retrieve all tenants\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-tenant\n        method:\
  \ POST\n        description: Create a new tenant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n    - name: connectors\n      path: /connectors\n      description: Data connector management\n      operations:\n      - name: list-connectors\n        method: GET\n        description: Retrieve all configured connectors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-connector\n        method: POST\n        description: Create a new data connector\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n           \
  \ type: '{{tools.type}}'\n    - name: alerts\n      path: /alerts\n      description: Alert management\n      operations:\n      - name: list-alerts\n        method: GET\n        description: Retrieve security alerts\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of alerts to return\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by alert status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events\n      description: Security event ingestion\n      operations:\n      - name: ingest-events\n        method: POST\n        description: Ingest security event documents into the platform\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            events: '{{tools.events}}'\n    - name: watchlists\n      path: /watchlists\n      description: Watchlist management\n      operations:\n      - name: list-watchlists\n        method: GET\n        description: Retrieve all watchlists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-watchlist\n        method: POST\n        description: Create a new watchlist\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            entries: '{{tools.entries}}'\n    - name: sensors\n      path: /sensors\n      description: Sensor monitoring\n      operations:\n      - name: list-sensors\n        method: GET\n        description: Retrieve all registered\
  \ sensors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /reports\n      description: Security report management\n      operations:\n      - name: list-reports\n        method: GET\n        description: Retrieve available security reports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-report\n        method: POST\n        description: Generate a new security report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n    - name: playbooks\n      path: /playbooks\n      description: ATH Playbook response actions\n      operations:\n      - name: list-playbooks\n        method:\
  \ GET\n        description: Retrieve all playbooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-playbook\n        method: POST\n        description: Create a new ATH Playbook response action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            trigger: '{{tools.trigger}}'\n            actions: '{{tools.actions}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: security-operations-api\n    description: Unified REST API for Stellar Cyber security operations workflows.\n    resources:\n    - path: /v1/cases\n      name: cases\n      description: Security case management operations\n      operations:\n      - method: GET\n        name: list-cases\n        description: List security cases with optional\
  \ status filtering\n        call: stellar-cyber.list-cases\n        with:\n          limit: rest.limit\n          offset: rest.offset\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-case\n        description: Create a new security case for investigation\n        call: stellar-cyber.create-case\n        with:\n          name: rest.name\n          description: rest.description\n          priority: rest.priority\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cases/{id}\n      name: case\n      description: Individual case operations\n      operations:\n      - method: GET\n        name: get-case\n        description: Retrieve details of a specific case\n        call: stellar-cyber.get-case\n        with:\n          caseId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-case\n\
  \        description: Update case status and attributes\n        call: stellar-cyber.update-case\n        with:\n          caseId: rest.id\n          status: rest.status\n          priority: rest.priority\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alerts\n      name: alerts\n      description: Security alert management\n      operations:\n      - method: GET\n        name: list-alerts\n        description: Retrieve security alerts with filtering\n        call: stellar-cyber.list-alerts\n        with:\n          limit: rest.limit\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Security event ingestion\n      operations:\n      - method: POST\n        name: ingest-events\n        description: Ingest security event documents\n        call: stellar-cyber.ingest-events\n        with:\n          events: rest.events\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/watchlists\n      name: watchlists\n      description: Threat watchlist management\n      operations:\n      - method: GET\n        name: list-watchlists\n        description: Retrieve all watchlists\n        call: stellar-cyber.list-watchlists\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-watchlist\n        description: Create a watchlist for threat tracking\n        call: stellar-cyber.create-watchlist\n        with:\n          name: rest.name\n          entries: rest.entries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sensors\n      name: sensors\n      description: Security sensor monitoring\n      operations:\n      - method: GET\n        name: list-sensors\n        description: List all registered sensors\n        call: stellar-cyber.list-sensors\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /v1/playbooks\n      name: playbooks\n      description: Automated response playbooks\n      operations:\n      - method: GET\n        name: list-playbooks\n        description: List all ATH playbooks\n        call: stellar-cyber.list-playbooks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-playbook\n        description: Create a new automated response playbook\n        call: stellar-cyber.create-playbook\n        with:\n          name: rest.name\n          trigger: rest.trigger\n          actions: rest.actions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: Security reporting\n      operations:\n      - method: GET\n        name: list-reports\n        description: Retrieve available security reports\n        call: stellar-cyber.list-reports\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: POST\n        name: create-report\n        description: Generate a new security report\n        call: stellar-cyber.create-report\n        with:\n          name: rest.name\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: security-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted security operations on Stellar Cyber Open XDR.\n    tools:\n    - name: list-cases\n      description: Retrieve security cases from Stellar Cyber. Use for investigating ongoing incidents and tracking case status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stellar-cyber.list-cases\n      with:\n        limit: tools.limit\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-case\n      description: Create a new security case in Stellar Cyber. Use when\
  \ an alert or event requires formal investigation and\n        tracking.\n      hints:\n        readOnly: false\n        destructive: false\n      call: stellar-cyber.create-case\n      with:\n        name: tools.name\n        description: tools.description\n        priority: tools.priority\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-case\n      description: Get detailed information about a specific security case by ID.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stellar-cyber.get-case\n      with:\n        caseId: tools.caseId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-case\n      description: Update a security case status, priority, or other attributes. Use to progress cases through investigation\n        workflows.\n      hints:\n        readOnly: false\n        destructive: false\n      call: stellar-cyber.update-case\n      with:\n        caseId: tools.caseId\n   \
  \     status: tools.status\n        priority: tools.priority\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-alerts\n      description: Retrieve security alerts from Stellar Cyber Open XDR. Use for alert triage and identifying threats requiring\n        investigation.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stellar-cyber.list-alerts\n      with:\n        limit: tools.limit\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ingest-events\n      description: Ingest custom security event documents into Stellar Cyber for analysis and correlation.\n      hints:\n        readOnly: false\n        destructive: false\n      call: stellar-cyber.ingest-events\n      with:\n        events: tools.events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-watchlists\n      description: Retrieve all threat watchlists. Use to check what\
  \ indicators and entities are currently being monitored.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stellar-cyber.list-watchlists\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-watchlist\n      description: Create a new watchlist for tracking threat indicators such as malicious IPs, domains, or file hashes.\n      hints:\n        readOnly: false\n        destructive: false\n      call: stellar-cyber.create-watchlist\n      with:\n        name: tools.name\n        entries: tools.entries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sensors\n      description: List all sensors registered with Stellar Cyber. Use to check sensor health and coverage across the environment.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stellar-cyber.list-sensors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-playbooks\n      description:\
  \ Retrieve all automated response playbooks. Use to review available automation workflows for threat response.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stellar-cyber.list-playbooks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-playbook\n      description: Create a new ATH Playbook response action for automated threat response.\n      hints:\n        readOnly: false\n        destructive: false\n      call: stellar-cyber.create-playbook\n      with:\n        name: tools.name\n        trigger: tools.trigger\n        actions: tools.actions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reports\n      description: List available security reports. Use for compliance reporting and security posture reviews.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stellar-cyber.list-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n  \
  \  - name: create-report\n      description: Generate a new security report for compliance or executive reporting.\n      hints:\n        readOnly: false\n        destructive: false\n      call: stellar-cyber.create-report\n      with:\n        name: tools.name\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stellar-cyber/refs/heads/main/capabilities/security-operations.yaml
tags:
- Stellar Cyber
- Cybersecurity
- SOC
- Incident Response
- Threat Hunting
- SOAR
tools:
- description: Retrieve security cases from Stellar Cyber. Use for investigating ongoing incidents and tracking case status.
  hints:
    openWorld: true
    readOnly: true
  name: list-cases
- description: Create a new security case in Stellar Cyber. Use when an alert or event requires formal investigation and tracking.
  hints:
    destructive: false
    readOnly: false
  name: create-case
- description: Get detailed information about a specific security case by ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-case
- description: Update a security case status, priority, or other attributes. Use to progress cases through investigation workflows.
  hints:
    destructive: false
    readOnly: false
  name: update-case
- description: Retrieve security alerts from Stellar Cyber Open XDR. Use for alert triage and identifying threats requiring investigation.
  hints:
    openWorld: true
    readOnly: true
  name: list-alerts
- description: Ingest custom security event documents into Stellar Cyber for analysis and correlation.
  hints:
    destructive: false
    readOnly: false
  name: ingest-events
- description: Retrieve all threat watchlists. Use to check what indicators and entities are currently being monitored.
  hints:
    openWorld: true
    readOnly: true
  name: list-watchlists
- description: Create a new watchlist for tracking threat indicators such as malicious IPs, domains, or file hashes.
  hints:
    destructive: false
    readOnly: false
  name: create-watchlist
- description: List all sensors registered with Stellar Cyber. Use to check sensor health and coverage across the environment.
  hints:
    openWorld: true
    readOnly: true
  name: list-sensors
- description: Retrieve all automated response playbooks. Use to review available automation workflows for threat response.
  hints:
    openWorld: true
    readOnly: true
  name: list-playbooks
- description: Create a new ATH Playbook response action for automated threat response.
  hints:
    destructive: false
    readOnly: false
  name: create-playbook
- description: List available security reports. Use for compliance reporting and security posture reviews.
  hints:
    openWorld: true
    readOnly: true
  name: list-reports
- description: Generate a new security report for compliance or executive reporting.
  hints:
    destructive: false
    readOnly: false
  name: create-report
---
