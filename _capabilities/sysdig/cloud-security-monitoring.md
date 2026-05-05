---
api_specs:
- filename: sysdig-monitor-openapi.yml
  format: yaml
  label: sysdig-monitor
  slug: sysdig-monitor
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sysdig/refs/heads/main/openapi/sysdig-monitor-openapi.yml
- filename: sysdig-secure-openapi.yml
  format: yaml
  label: sysdig-secure
  slug: sysdig-secure
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sysdig/refs/heads/main/openapi/sysdig-secure-openapi.yml
categories: []
consumed_apis:
- sysdig-monitor
- sysdig-secure
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
- containers
- trigger image vulnerability scan
- list sysdig monitor events within a time range
- list activity audit entries
- get compliance results
- cloud security
- get alert
- create a monitoring alert
- list all falco security detection rules
- cspm
- monitor alerts for cloud-native infrastructure
- list sysdig monitor dashboards
- trigger a vulnerability scan for a container image
- list sysdig secure runtime security events triggered by policy violations
- runtime security events from policy violations
- list alerts
- scanned container images
- create dashboard
- list monitoring events
- list all monitoring alerts
- create alert
- compliance evaluation tasks and results
- get vulnerability findings for a specific container image
- get details of a specific sysdig monitor alert
- list activity audit
- scan image
- list sysdig secure runtime security policies
- search for available sysdig metrics by name pattern
- list scanned container images
- list audit
- create a monitoring dashboard
- create a new runtime security policy
- observability
- get image vulnerabilities
- list dashboards
- vulnerability scanning results
- search for available metrics
- list vulnerabilities
- vulnerability management
- runtime security policies
- list monitor events
- list all teams
- get details of a specific runtime security policy
- list runtime security policies
- get image sbom
- security
- list security events
- list sysdig monitor alerts for cloud-native infrastructure
- create a runtime security policy
- monitoring dashboards
- monitoring events
- runtime security
- monitoring
- activity audit trail
- team management
- compliance
- list images
- create policy
- list policies
- get compliance check results for a specific task
- list compliance evaluation tasks (pci-dss, gdpr, nist)
- create a new monitoring alert for cloud infrastructure
- get the software bill of materials (sbom) for a container image
- get policy
- create a custom falco detection rule
- list vulnerability scanning results
- list all monitoring dashboards
- list compliance tasks
- list all container images that have been scanned
- list all sysdig teams and their configurations
- list scanned images
- sysdig
- list the activity audit trail for forensic investigation
- search available metrics
- list compliance evaluation tasks
- list container and host vulnerability scanning results
- list teams
- list runtime security events
- create falco rule
- kubernetes
- list falco rules
- find metrics
slug: cloud-security-monitoring
source_filename: cloud-security-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sysdig Cloud Security Monitoring\"\n  description: >-\n    Unified workflow capability combining Sysdig Monitor and Sysdig Secure for\n    cloud and container security monitoring. Enables security teams to correlate\n    runtime security events with monitoring alerts, manage policies, track\n    vulnerabilities, and maintain compliance across Kubernetes and cloud environments.\n  tags:\n    - Sysdig\n    - Cloud Security\n    - Monitoring\n    - Containers\n    - Kubernetes\n    - Runtime Security\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      SYSDIG_API_TOKEN: SYSDIG_API_TOKEN\n\ncapability:\n  consumes:\n    - import: sysdig-monitor\n      location: ./shared/sysdig-monitor.yaml\n    - import: sysdig-secure\n      location: ./shared/sysdig-secure.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sysdig-security-api\n      description: \"Unified REST\
  \ API for Sysdig cloud security and monitoring workflows.\"\n      resources:\n        - path: /v1/alerts\n          name: alerts\n          description: \"Monitor alerts for cloud-native infrastructure\"\n          operations:\n            - method: GET\n              name: list-alerts\n              description: \"List all monitoring alerts\"\n              call: \"sysdig-monitor.list-alerts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-alert\n              description: \"Create a monitoring alert\"\n              call: \"sysdig-monitor.create-alert\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/dashboards\n          name: dashboards\n          description: \"Monitoring dashboards\"\n          operations:\n            - method: GET\n              name: list-dashboards\n              description: \"\
  List all monitoring dashboards\"\n              call: \"sysdig-monitor.list-dashboards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-dashboard\n              description: \"Create a monitoring dashboard\"\n              call: \"sysdig-monitor.create-dashboard\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events\n          name: monitor-events\n          description: \"Monitoring events\"\n          operations:\n            - method: GET\n              name: list-monitor-events\n              description: \"List monitoring events\"\n              call: \"sysdig-monitor.list-events\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/security-events\n          name: security-events\n          description: \"Runtime security events\
  \ from policy violations\"\n          operations:\n            - method: GET\n              name: list-security-events\n              description: \"List runtime security events\"\n              call: \"sysdig-secure.list-secure-events\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/vulnerabilities\n          name: vulnerabilities\n          description: \"Vulnerability scanning results\"\n          operations:\n            - method: GET\n              name: list-vulnerabilities\n              description: \"List vulnerability scanning results\"\n              call: \"sysdig-secure.list-vulnerability-results\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/images\n          name: images\n          description: \"Scanned container images\"\n          operations:\n            - method: GET\n              name: list-images\n             \
  \ description: \"List scanned container images\"\n              call: \"sysdig-secure.list-scanned-images\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: scan-image\n              description: \"Trigger image vulnerability scan\"\n              call: \"sysdig-secure.scan-image\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/policies\n          name: policies\n          description: \"Runtime security policies\"\n          operations:\n            - method: GET\n              name: list-policies\n              description: \"List runtime security policies\"\n              call: \"sysdig-secure.list-policies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-policy\n              description: \"Create a runtime\
  \ security policy\"\n              call: \"sysdig-secure.create-policy\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/compliance\n          name: compliance\n          description: \"Compliance evaluation tasks and results\"\n          operations:\n            - method: GET\n              name: list-compliance-tasks\n              description: \"List compliance evaluation tasks\"\n              call: \"sysdig-secure.list-compliance-tasks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/audit\n          name: audit\n          description: \"Activity audit trail\"\n          operations:\n            - method: GET\n              name: list-audit\n              description: \"List activity audit entries\"\n              call: \"sysdig-secure.list-activity-audit\"\n              outputParameters:\n                - type: object\n         \
  \         mapping: \"$.\"\n\n        - path: /v1/teams\n          name: teams\n          description: \"Team management\"\n          operations:\n            - method: GET\n              name: list-teams\n              description: \"List all teams\"\n              call: \"sysdig-monitor.list-teams\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/metrics\n          name: metrics\n          description: \"Search available metrics\"\n          operations:\n            - method: GET\n              name: find-metrics\n              description: \"Search for available metrics\"\n              call: \"sysdig-monitor.find-metrics\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sysdig-security-mcp\n      transport: http\n      description: \"MCP server for\
  \ AI-assisted Sysdig cloud security monitoring and incident response.\"\n      tools:\n        - name: list-alerts\n          description: \"List Sysdig Monitor alerts for cloud-native infrastructure\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-monitor.list-alerts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-alert\n          description: \"Get details of a specific Sysdig Monitor alert\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-monitor.get-alert\"\n          with:\n            alertId: \"tools.alertId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-alert\n          description: \"Create a new monitoring alert for cloud infrastructure\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent:\
  \ false\n          call: \"sysdig-monitor.create-alert\"\n          with:\n            alert: \"tools.alert\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-dashboards\n          description: \"List Sysdig Monitor dashboards\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-monitor.list-dashboards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-monitor-events\n          description: \"List Sysdig Monitor events within a time range\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-monitor.list-events\"\n          with:\n            from: \"tools.from\"\n            to: \"tools.to\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-security-events\n         \
  \ description: \"List Sysdig Secure runtime security events triggered by policy violations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-secure.list-secure-events\"\n          with:\n            from: \"tools.from\"\n            to: \"tools.to\"\n            filter: \"tools.filter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-vulnerabilities\n          description: \"List container and host vulnerability scanning results\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-secure.list-vulnerability-results\"\n          with:\n            filter: \"tools.filter\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-image-vulnerabilities\n          description: \"Get vulnerability findings for a specific container image\"\n\
  \          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-secure.get-image-vulnerabilities\"\n          with:\n            imageId: \"tools.imageId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-image-sbom\n          description: \"Get the Software Bill of Materials (SBOM) for a container image\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-secure.get-image-sbom\"\n          with:\n            imageId: \"tools.imageId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: scan-image\n          description: \"Trigger a vulnerability scan for a container image\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sysdig-secure.scan-image\"\n          with:\n            tag: \"tools.tag\"\n       \
  \   outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-scanned-images\n          description: \"List all container images that have been scanned\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-secure.list-scanned-images\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-policies\n          description: \"List Sysdig Secure runtime security policies\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-secure.list-policies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-policy\n          description: \"Get details of a specific runtime security policy\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-secure.get-policy\"\n          with:\n            policyId:\
  \ \"tools.policyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-policy\n          description: \"Create a new runtime security policy\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sysdig-secure.create-policy\"\n          with:\n            policy: \"tools.policy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-falco-rules\n          description: \"List all Falco security detection rules\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-secure.list-falco-rules\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-falco-rule\n          description: \"Create a custom Falco detection rule\"\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n            idempotent: false\n          call: \"sysdig-secure.create-falco-rule\"\n          with:\n            rule: \"tools.rule\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-compliance-tasks\n          description: \"List compliance evaluation tasks (PCI-DSS, GDPR, NIST)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-secure.list-compliance-tasks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-compliance-results\n          description: \"Get compliance check results for a specific task\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-secure.get-compliance-results\"\n          with:\n            taskId: \"tools.taskId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-activity-audit\n\
  \          description: \"List the activity audit trail for forensic investigation\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-secure.list-activity-audit\"\n          with:\n            from: \"tools.from\"\n            to: \"tools.to\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-teams\n          description: \"List all Sysdig teams and their configurations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-monitor.list-teams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-metrics\n          description: \"Search for available Sysdig metrics by name pattern\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sysdig-monitor.find-metrics\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
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
