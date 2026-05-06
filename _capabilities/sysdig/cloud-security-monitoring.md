---
categories: []
consumed_apis: []
description: Unified workflow capability combining Sysdig Monitor and Sysdig Secure for cloud and container security monitoring. Enables security teams to correlate runtime security events with monitoring alerts, manage policies, track vulnerabilities, and maintain compliance across Kubernetes and cloud environments.
layout: capability
name: Sysdig Cloud Security Monitoring
operations:
- description: List all monitoring alerts
  method: GET
  name: list-alerts
  path: /v1/alerts
- description: Create a monitoring alert
  method: POST
  name: create-alert
  path: /v1/alerts
- description: List all monitoring dashboards
  method: GET
  name: list-dashboards
  path: /v1/dashboards
- description: Create a monitoring dashboard
  method: POST
  name: create-dashboard
  path: /v1/dashboards
- description: List monitoring events
  method: GET
  name: list-monitor-events
  path: /v1/events
- description: List runtime security events
  method: GET
  name: list-security-events
  path: /v1/security-events
- description: List vulnerability scanning results
  method: GET
  name: list-vulnerabilities
  path: /v1/vulnerabilities
- description: List scanned container images
  method: GET
  name: list-images
  path: /v1/images
- description: Trigger image vulnerability scan
  method: POST
  name: scan-image
  path: /v1/images
- description: List runtime security policies
  method: GET
  name: list-policies
  path: /v1/policies
- description: Create a runtime security policy
  method: POST
  name: create-policy
  path: /v1/policies
- description: List compliance evaluation tasks
  method: GET
  name: list-compliance-tasks
  path: /v1/compliance
- description: List activity audit entries
  method: GET
  name: list-audit
  path: /v1/audit
- description: List all teams
  method: GET
  name: list-teams
  path: /v1/teams
- description: Search for available metrics
  method: GET
  name: find-metrics
  path: /v1/metrics
personas: []
provider_name: Sysdig
provider_slug: sysdig
search_terms:
- create a monitoring dashboard
- create a monitoring alert
- scanned container images
- search for available sysdig metrics by name pattern
- list vulnerabilities
- team management
- list all monitoring dashboards
- list teams
- find metrics
- security
- get image sbom
- cloud security
- get image vulnerabilities
- create a runtime security policy
- create a custom falco detection rule
- observability
- list sysdig secure runtime security events triggered by policy violations
- get compliance results
- get policy
- list runtime security events
- sysdig
- create a new runtime security policy
- list policies
- list all sysdig teams and their configurations
- scan image
- list falco rules
- list runtime security policies
- create a new monitoring alert for cloud infrastructure
- search for available metrics
- trigger image vulnerability scan
- runtime security policies
- runtime security events from policy violations
- list container and host vulnerability scanning results
- monitoring
- create dashboard
- kubernetes
- monitor alerts for cloud-native infrastructure
- list monitor events
- monitoring dashboards
- list compliance evaluation tasks (pci-dss, gdpr, nist)
- get details of a specific sysdig monitor alert
- list all container images that have been scanned
- get alert
- list activity audit
- get compliance check results for a specific task
- compliance evaluation tasks and results
- list monitoring events
- get vulnerability findings for a specific container image
- compliance
- vulnerability scanning results
- list compliance evaluation tasks
- list security events
- list scanned container images
- list all teams
- list the activity audit trail for forensic investigation
- list dashboards
- monitoring events
- list all falco security detection rules
- cspm
- list alerts
- list images
- list vulnerability scanning results
- list sysdig monitor dashboards
- list activity audit entries
- trigger a vulnerability scan for a container image
- list sysdig secure runtime security policies
- vulnerability management
- list audit
- get the software bill of materials (sbom) for a container image
- get details of a specific runtime security policy
- list all monitoring alerts
- containers
- search available metrics
- activity audit trail
- create falco rule
- create policy
- list scanned images
- create alert
- list compliance tasks
- list sysdig monitor alerts for cloud-native infrastructure
- list sysdig monitor events within a time range
- runtime security
slug: cloud-security-monitoring
source_filename: cloud-security-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sysdig Cloud Security Monitoring\n  description: Unified workflow capability combining Sysdig Monitor and Sysdig Secure for cloud and container security monitoring.\n    Enables security teams to correlate runtime security events with monitoring alerts, manage policies, track vulnerabilities,\n    and maintain compliance across Kubernetes and cloud environments.\n  tags:\n  - Sysdig\n  - Cloud Security\n  - Monitoring\n  - Containers\n  - Kubernetes\n  - Runtime Security\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SYSDIG_API_TOKEN: SYSDIG_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: sysdig-monitor\n    baseUri: https://api.us1.sysdig.com\n    description: Sysdig Monitor REST API for observability and alerting.\n    authentication:\n      type: bearer\n      token: '{{SYSDIG_API_TOKEN}}'\n    resources:\n    - name: alerts\n      path: /api/v2/alerts\n      description:\
  \ Manage monitoring alerts\n      operations:\n      - name: list-alerts\n        method: GET\n        description: Retrieve all monitoring alerts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-alert\n        method: POST\n        description: Create a new monitoring alert\n        body:\n          type: json\n          data:\n            alert: '{{tools.alert}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alert-by-id\n      path: /api/v2/alerts/{alertId}\n      description: Manage a specific alert\n      operations:\n      - name: get-alert\n        method: GET\n        description: Retrieve a specific alert by ID\n        inputParameters:\n        - name: alertId\n          in: path\n          type: integer\n          required: true\n          description: Alert unique identifier\n       \
  \ outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-alert\n        method: PUT\n        description: Update an existing monitoring alert\n        inputParameters:\n        - name: alertId\n          in: path\n          type: integer\n          required: true\n          description: Alert unique identifier\n        body:\n          type: json\n          data:\n            alert: '{{tools.alert}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-alert\n        method: DELETE\n        description: Delete a monitoring alert\n        inputParameters:\n        - name: alertId\n          in: path\n          type: integer\n          required: true\n          description: Alert unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n    - name: dashboards\n      path: /api/v3/dashboards\n      description: Manage monitoring dashboards\n      operations:\n      - name: list-dashboards\n        method: GET\n        description: Retrieve all monitoring dashboards\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-dashboard\n        method: POST\n        description: Create a new monitoring dashboard\n        body:\n          type: json\n          data:\n            dashboard: '{{tools.dashboard}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboard-by-id\n      path: /api/v3/dashboards/{dashboardId}\n      description: Manage a specific dashboard\n      operations:\n      - name: get-dashboard\n        method: GET\n        description: Retrieve a specific dashboard by ID\n        inputParameters:\n        - name:\
  \ dashboardId\n          in: path\n          type: integer\n          required: true\n          description: Dashboard unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-dashboard\n        method: PUT\n        description: Update an existing dashboard\n        inputParameters:\n        - name: dashboardId\n          in: path\n          type: integer\n          required: true\n          description: Dashboard unique identifier\n        body:\n          type: json\n          data:\n            dashboard: '{{tools.dashboard}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-dashboard\n        method: DELETE\n        description: Delete a dashboard\n        inputParameters:\n        - name: dashboardId\n          in: path\n          type: integer\n          required: true\n  \
  \        description: Dashboard unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /api/v2/events\n      description: Manage monitoring events\n      operations:\n      - name: list-events\n        method: GET\n        description: Retrieve monitoring events\n        inputParameters:\n        - name: from\n          in: query\n          type: integer\n          required: false\n          description: Start time (Unix epoch microseconds)\n        - name: to\n          in: query\n          type: integer\n          required: false\n          description: End time (Unix epoch microseconds)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n     \
  \ - name: create-event\n        method: POST\n        description: Create a custom event\n        body:\n          type: json\n          data:\n            event: '{{tools.event}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notification-channels\n      path: /api/notificationChannels\n      description: Manage alert notification channels\n      operations:\n      - name: list-notification-channels\n        method: GET\n        description: Retrieve all notification channels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-notification-channel\n        method: POST\n        description: Create a new notification channel\n        body:\n          type: json\n          data:\n            notificationChannel: '{{tools.notificationChannel}}'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /api/v2/teams\n      description: Manage Sysdig teams\n      operations:\n      - name: list-teams\n        method: GET\n        description: Retrieve all teams\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-team\n        method: POST\n        description: Create a new team\n        body:\n          type: json\n          data:\n            team: '{{tools.team}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics-find\n      path: /api/v2/metrics/find\n      description: Search available metrics\n      operations:\n      - name: find-metrics\n        method: GET\n        description: Search for metrics by name pattern\n        inputParameters:\n        - name: name\n          in: query\n    \
  \      type: string\n          required: false\n          description: Metric name pattern\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: sysdig-secure\n    baseUri: https://api.us1.sysdig.com\n    description: Sysdig Secure REST API for cloud and container security.\n    authentication:\n      type: bearer\n      token: '{{SYSDIG_API_TOKEN}}'\n    resources:\n    - name: vulnerabilities\n      path: /api/scanning/v1/resultsDirect\n      description: Vulnerability scanning results\n      operations:\n      - name: list-vulnerability-results\n        method: GET\n        description: List vulnerability scanning results\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        - name: cursor\n          in: query\n          type: string\n          required:\
  \ false\n          description: Pagination cursor\n        - name: filter\n          in: query\n          type: string\n          required: false\n          description: Filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: image-vulnerabilities\n      path: /api/scanning/v1/images/{imageId}/vulnDirect\n      description: Image-specific vulnerabilities\n      operations:\n      - name: get-image-vulnerabilities\n        method: GET\n        description: Get vulnerabilities for a specific image\n        inputParameters:\n        - name: imageId\n          in: path\n          type: string\n          required: true\n          description: Container image identifier\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: image-sbom\n      path: /api/scanning/v1/images/{imageId}/sbom\n      description: Image SBOM\n      operations:\n      - name: get-image-sbom\n        method: GET\n        description: Get SBOM for a container image\n        inputParameters:\n        - name: imageId\n          in: path\n          type: string\n          required: true\n          description: Container image identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies\n      path: /api/policies/v2\n      description: Runtime security policies\n      operations:\n      - name: list-policies\n        method: GET\n        description: List all runtime security policies\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Policy type filter\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-policy\n        method: POST\n        description: Create a new runtime security policy\n        body:\n          type: json\n          data:\n            policy: '{{tools.policy}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policy-by-id\n      path: /api/policies/v2/{policyId}\n      description: Manage a specific policy\n      operations:\n      - name: get-policy\n        method: GET\n        description: Get a specific runtime policy\n        inputParameters:\n        - name: policyId\n          in: path\n          type: integer\n          required: true\n          description: Policy unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-policy\n        method: PUT\n\
  \        description: Update a runtime security policy\n        inputParameters:\n        - name: policyId\n          in: path\n          type: integer\n          required: true\n          description: Policy unique identifier\n        body:\n          type: json\n          data:\n            policy: '{{tools.policy}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-policy\n        method: DELETE\n        description: Delete a runtime security policy\n        inputParameters:\n        - name: policyId\n          in: path\n          type: integer\n          required: true\n          description: Policy unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: falco-rules\n      path: /api/secure/falco/v2/rules\n      description: Falco security rules\n      operations:\n      - name: list-falco-rules\n\
  \        method: GET\n        description: List all Falco rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-falco-rule\n        method: POST\n        description: Create a custom Falco rule\n        body:\n          type: json\n          data:\n            rule: '{{tools.rule}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliance-tasks\n      path: /api/compliance/v2/tasks\n      description: Compliance evaluation tasks\n      operations:\n      - name: list-compliance-tasks\n        method: GET\n        description: List all compliance tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliance-results\n      path: /api/compliance/v2/tasks/{taskId}/results\n      description: Compliance check\
  \ results\n      operations:\n      - name: get-compliance-results\n        method: GET\n        description: Get compliance results for a task\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n          description: Compliance task identifier\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secure-events\n      path: /api/v1/secureEvents\n      description: Runtime security events\n      operations:\n      - name: list-secure-events\n        method: GET\n        description: List runtime security events\n        inputParameters:\n        - name: from\n          in: query\n          type: integer\n          required: false\n          description: Start time (Unix epoch seconds)\n   \
  \     - name: to\n          in: query\n          type: integer\n          required: false\n          description: End time (Unix epoch seconds)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        - name: filter\n          in: query\n          type: string\n          required: false\n          description: Filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activity-audit\n      path: /api/v1/activityAudit\n      description: Activity audit trail\n      operations:\n      - name: list-activity-audit\n        method: GET\n        description: List activity audit entries\n        inputParameters:\n        - name: from\n          in: query\n          type: integer\n          required: false\n          description: Start time\n        - name: to\n          in: query\n          type: integer\n\
  \          required: false\n          description: End time\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: image-scan\n      path: /api/scanning/v1/image\n      description: Trigger image scanning\n      operations:\n      - name: scan-image\n        method: POST\n        description: Trigger vulnerability scan for a container image\n        body:\n          type: json\n          data:\n            tag: '{{tools.tag}}'\n            digest: '{{tools.digest}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scanned-images\n      path: /api/scanning/v1/images\n      description: Scanned images inventory\n      operations:\n      - name: list-scanned-images\n     \
  \   method: GET\n        description: List all scanned container images\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sysdig-security-api\n    description: Unified REST API for Sysdig cloud security and monitoring workflows.\n    resources:\n    - path: /v1/alerts\n      name: alerts\n      description: Monitor alerts for cloud-native infrastructure\n      operations:\n      - method: GET\n        name: list-alerts\n        description: List all monitoring alerts\n        call: sysdig-monitor.list-alerts\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n      - method: POST\n        name: create-alert\n        description: Create a monitoring alert\n        call: sysdig-monitor.create-alert\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dashboards\n      name: dashboards\n      description: Monitoring dashboards\n      operations:\n      - method: GET\n        name: list-dashboards\n        description: List all monitoring dashboards\n        call: sysdig-monitor.list-dashboards\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-dashboard\n        description: Create a monitoring dashboard\n        call: sysdig-monitor.create-dashboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: monitor-events\n      description: Monitoring events\n      operations:\n      - method: GET\n        name: list-monitor-events\n        description: List\
  \ monitoring events\n        call: sysdig-monitor.list-events\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/security-events\n      name: security-events\n      description: Runtime security events from policy violations\n      operations:\n      - method: GET\n        name: list-security-events\n        description: List runtime security events\n        call: sysdig-secure.list-secure-events\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vulnerabilities\n      name: vulnerabilities\n      description: Vulnerability scanning results\n      operations:\n      - method: GET\n        name: list-vulnerabilities\n        description: List vulnerability scanning results\n        call: sysdig-secure.list-vulnerability-results\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/images\n      name: images\n      description: Scanned container images\n      operations:\n\
  \      - method: GET\n        name: list-images\n        description: List scanned container images\n        call: sysdig-secure.list-scanned-images\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: scan-image\n        description: Trigger image vulnerability scan\n        call: sysdig-secure.scan-image\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies\n      name: policies\n      description: Runtime security policies\n      operations:\n      - method: GET\n        name: list-policies\n        description: List runtime security policies\n        call: sysdig-secure.list-policies\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-policy\n        description: Create a runtime security policy\n        call: sysdig-secure.create-policy\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /v1/compliance\n      name: compliance\n      description: Compliance evaluation tasks and results\n      operations:\n      - method: GET\n        name: list-compliance-tasks\n        description: List compliance evaluation tasks\n        call: sysdig-secure.list-compliance-tasks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audit\n      name: audit\n      description: Activity audit trail\n      operations:\n      - method: GET\n        name: list-audit\n        description: List activity audit entries\n        call: sysdig-secure.list-activity-audit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams\n      name: teams\n      description: Team management\n      operations:\n      - method: GET\n        name: list-teams\n        description: List all teams\n        call: sysdig-monitor.list-teams\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics\n\
  \      name: metrics\n      description: Search available metrics\n      operations:\n      - method: GET\n        name: find-metrics\n        description: Search for available metrics\n        call: sysdig-monitor.find-metrics\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sysdig-security-mcp\n    transport: http\n    description: MCP server for AI-assisted Sysdig cloud security monitoring and incident response.\n    tools:\n    - name: list-alerts\n      description: List Sysdig Monitor alerts for cloud-native infrastructure\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sysdig-monitor.list-alerts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-alert\n      description: Get details of a specific Sysdig Monitor alert\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sysdig-monitor.get-alert\n\
  \      with:\n        alertId: tools.alertId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-alert\n      description: Create a new monitoring alert for cloud infrastructure\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sysdig-monitor.create-alert\n      with:\n        alert: tools.alert\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dashboards\n      description: List Sysdig Monitor dashboards\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sysdig-monitor.list-dashboards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-monitor-events\n      description: List Sysdig Monitor events within a time range\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sysdig-monitor.list-events\n      with:\n        from: tools.from\n        to: tools.to\n        limit: tools.limit\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-security-events\n      description: List Sysdig Secure runtime security events triggered by policy violations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sysdig-secure.list-secure-events\n      with:\n        from: tools.from\n        to: tools.to\n        filter: tools.filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vulnerabilities\n      description: List container and host vulnerability scanning results\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sysdig-secure.list-vulnerability-results\n      with:\n        filter: tools.filter\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-image-vulnerabilities\n      description: Get vulnerability findings for a specific container image\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: sysdig-secure.get-image-vulnerabilities\n      with:\n        imageId: tools.imageId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-image-sbom\n      description: Get the Software Bill of Materials (SBOM) for a container image\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sysdig-secure.get-image-sbom\n      with:\n        imageId: tools.imageId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scan-image\n      description: Trigger a vulnerability scan for a container image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sysdig-secure.scan-image\n      with:\n        tag: tools.tag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-scanned-images\n      description: List all container images that have been scanned\n      hints:\n        readOnly: true\n        openWorld: true\n\
  \      call: sysdig-secure.list-scanned-images\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-policies\n      description: List Sysdig Secure runtime security policies\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sysdig-secure.list-policies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-policy\n      description: Get details of a specific runtime security policy\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sysdig-secure.get-policy\n      with:\n        policyId: tools.policyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-policy\n      description: Create a new runtime security policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sysdig-secure.create-policy\n      with:\n        policy: tools.policy\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-falco-rules\n      description: List all Falco security detection rules\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sysdig-secure.list-falco-rules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-falco-rule\n      description: Create a custom Falco detection rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sysdig-secure.create-falco-rule\n      with:\n        rule: tools.rule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-compliance-tasks\n      description: List compliance evaluation tasks (PCI-DSS, GDPR, NIST)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sysdig-secure.list-compliance-tasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-compliance-results\n      description: Get compliance check results for a\
  \ specific task\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sysdig-secure.get-compliance-results\n      with:\n        taskId: tools.taskId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-activity-audit\n      description: List the activity audit trail for forensic investigation\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sysdig-secure.list-activity-audit\n      with:\n        from: tools.from\n        to: tools.to\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-teams\n      description: List all Sysdig teams and their configurations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sysdig-monitor.list-teams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-metrics\n      description: Search for available Sysdig metrics by name pattern\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: sysdig-monitor.find-metrics\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sysdig/refs/heads/main/capabilities/cloud-security-monitoring.yaml
tags:
- Sysdig
- Cloud Security
- Monitoring
- Containers
- Kubernetes
- Runtime Security
tools:
- description: List Sysdig Monitor alerts for cloud-native infrastructure
  hints:
    openWorld: true
    readOnly: true
  name: list-alerts
- description: Get details of a specific Sysdig Monitor alert
  hints:
    openWorld: true
    readOnly: true
  name: get-alert
- description: Create a new monitoring alert for cloud infrastructure
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-alert
- description: List Sysdig Monitor dashboards
  hints:
    openWorld: true
    readOnly: true
  name: list-dashboards
- description: List Sysdig Monitor events within a time range
  hints:
    openWorld: true
    readOnly: true
  name: list-monitor-events
- description: List Sysdig Secure runtime security events triggered by policy violations
  hints:
    openWorld: true
    readOnly: true
  name: list-security-events
- description: List container and host vulnerability scanning results
  hints:
    openWorld: true
    readOnly: true
  name: list-vulnerabilities
- description: Get vulnerability findings for a specific container image
  hints:
    openWorld: true
    readOnly: true
  name: get-image-vulnerabilities
- description: Get the Software Bill of Materials (SBOM) for a container image
  hints:
    openWorld: true
    readOnly: true
  name: get-image-sbom
- description: Trigger a vulnerability scan for a container image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: scan-image
- description: List all container images that have been scanned
  hints:
    openWorld: true
    readOnly: true
  name: list-scanned-images
- description: List Sysdig Secure runtime security policies
  hints:
    openWorld: true
    readOnly: true
  name: list-policies
- description: Get details of a specific runtime security policy
  hints:
    openWorld: true
    readOnly: true
  name: get-policy
- description: Create a new runtime security policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-policy
- description: List all Falco security detection rules
  hints:
    openWorld: true
    readOnly: true
  name: list-falco-rules
- description: Create a custom Falco detection rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-falco-rule
- description: List compliance evaluation tasks (PCI-DSS, GDPR, NIST)
  hints:
    openWorld: true
    readOnly: true
  name: list-compliance-tasks
- description: Get compliance check results for a specific task
  hints:
    openWorld: true
    readOnly: true
  name: get-compliance-results
- description: List the activity audit trail for forensic investigation
  hints:
    openWorld: true
    readOnly: true
  name: list-activity-audit
- description: List all Sysdig teams and their configurations
  hints:
    openWorld: true
    readOnly: true
  name: list-teams
- description: Search for available Sysdig metrics by name pattern
  hints:
    openWorld: true
    readOnly: true
  name: find-metrics
---
