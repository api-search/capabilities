---
categories: []
consumed_apis:
- varonis-datalert
description: Unified workflow capability for SOC analysts performing threat detection, alert triage, and incident response using the Varonis DatAlert API. Combines alert management, forensic event investigation, and threat model reference into a single AI-accessible interface.
layout: capability
name: Varonis Threat Detection and Response
operations:
- description: Retrieve security alerts with filtering by threat model, severity, status, and time range.
  method: POST
  name: get-alerts
  path: /v1/alerts
- description: Update an alert status to Open or Under Investigation.
  method: PUT
  name: update-alert-status
  path: /v1/alerts/{alertId}/status
- description: Close an alert with a specified resolution reason.
  method: POST
  name: close-alert
  path: /v1/alerts/{alertId}/close
- description: Add an investigation note to an alert.
  method: POST
  name: add-alert-note
  path: /v1/alerts/{alertId}/notes
- description: Retrieve forensic events associated with an alert for investigation.
  method: GET
  name: get-alerted-events
  path: /v1/alerts/{alertId}/events
- description: List threat models configured in Varonis DatAlert.
  method: GET
  name: get-threat-models
  path: /v1/threat-models
personas: []
provider_name: Varonis
provider_slug: varonis
search_terms:
- soc
- alert status management.
- security operations center analyst who monitors alerts, investigates incidents, and manages alert lifecycle.
- incident response
- investigation notes on alerts.
- SOC Analyst
- unified workflow for soc analysts to retrieve alerts, investigate events, manage alert lifecycle, and reference threat models.
- protecting enterprise data from unauthorized access, exfiltration, and misuse.
- retrieve forensic events associated with an alert for investigation.
- update an alert status to open or under investigation.
- close a security alert with resolution reason.
- add alert note
- list threat models configured in varonis datalert.
- close a varonis datalert alert with a resolution reason such as resolved, legitimate activity, or misconfiguration.
- get alerts
- update the status of a varonis datalert alert to open or under investigation, with optional investigation note.
- retrieve varonis datalert security alerts with filtering by threat model, severity, status, and time range.
- add an investigation note to a varonis datalert alert to document findings and remediation steps.
- threat model definitions used to generate alerts.
- retrieve forensic events associated with a varonis alert for threat hunting and incident investigation.
- data analytics
- processes for detecting, investigating, and resolving security incidents.
- compliance
- close an alert with a specified resolution reason.
- close alert
- get alerted events
- cloud security
- list varonis datalert threat model definitions including category, severity, and mitre att&ck alignment.
- varonis
- data governance
- update alert status
- get threat models
- data security
- threat detection
- retrieve security alerts with filtering by threat model, severity, status, and time range.
- security operations
- forensic events associated with a security alert.
- security alerts from varonis datalert threat detection.
- add an investigation note to an alert.
slug: threat-detection-response
source_filename: threat-detection-response.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Varonis Threat Detection and Response\"\n  description: \"Unified workflow capability for SOC analysts performing threat detection, alert triage, and incident response using the Varonis DatAlert API. Combines alert management, forensic event investigation, and threat model reference into a single AI-accessible interface.\"\n  tags:\n    - Varonis\n    - Data Security\n    - Threat Detection\n    - Incident Response\n    - Security Operations\n    - SOC\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VARONIS_API_KEY: VARONIS_API_KEY\n\ncapability:\n  consumes:\n    - import: varonis-datalert\n      location: ./shared/datalert.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: varonis-threat-response-api\n      description: \"Unified REST API for Varonis threat detection and incident response workflows.\"\n      resources:\n        - path: /v1/alerts\n \
  \         name: alerts\n          description: \"Security alerts from Varonis DatAlert threat detection.\"\n          operations:\n            - method: POST\n              name: get-alerts\n              description: \"Retrieve security alerts with filtering by threat model, severity, status, and time range.\"\n              call: \"varonis-datalert.get-alerts\"\n              with:\n                maxResults: \"rest.maxResults\"\n                offset: \"rest.offset\"\n                alertStatus: \"rest.alertStatus\"\n                alertSeverity: \"rest.alertSeverity\"\n                lastDays: \"rest.lastDays\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/alerts/{alertId}/status\n          name: alert-status\n          description: \"Alert status management.\"\n          operations:\n            - method: PUT\n              name: update-alert-status\n              description: \"Update an alert status\
  \ to Open or Under Investigation.\"\n              call: \"varonis-datalert.update-alert-status\"\n              with:\n                alertId: \"rest.alertId\"\n                status: \"rest.status\"\n                note: \"rest.note\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/alerts/{alertId}/close\n          name: alert-close\n          description: \"Close a security alert with resolution reason.\"\n          operations:\n            - method: POST\n              name: close-alert\n              description: \"Close an alert with a specified resolution reason.\"\n              call: \"varonis-datalert.close-alert\"\n              with:\n                alertId: \"rest.alertId\"\n                closeReason: \"rest.closeReason\"\n                note: \"rest.note\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/alerts/{alertId}/notes\n\
  \          name: alert-notes\n          description: \"Investigation notes on alerts.\"\n          operations:\n            - method: POST\n              name: add-alert-note\n              description: \"Add an investigation note to an alert.\"\n              call: \"varonis-datalert.add-alert-note\"\n              with:\n                alertId: \"rest.alertId\"\n                note: \"rest.note\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/alerts/{alertId}/events\n          name: alert-events\n          description: \"Forensic events associated with a security alert.\"\n          operations:\n            - method: GET\n              name: get-alerted-events\n              description: \"Retrieve forensic events associated with an alert for investigation.\"\n              call: \"varonis-datalert.get-alerted-events\"\n              with:\n                alertId: \"rest.alertId\"\n                lastDays:\
  \ \"rest.lastDays\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/threat-models\n          name: threat-models\n          description: \"Threat model definitions used to generate alerts.\"\n          operations:\n            - method: GET\n              name: get-threat-models\n              description: \"List threat models configured in Varonis DatAlert.\"\n              call: \"varonis-datalert.get-threat-models\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: varonis-threat-response-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Varonis threat detection and incident response workflows.\"\n      tools:\n        - name: get-alerts\n          description: \"Retrieve Varonis DatAlert security alerts with filtering by threat\
  \ model, severity, status, and time range.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"varonis-datalert.get-alerts\"\n          with:\n            maxResults: \"tools.maxResults\"\n            offset: \"tools.offset\"\n            alertStatus: \"tools.alertStatus\"\n            alertSeverity: \"tools.alertSeverity\"\n            lastDays: \"tools.lastDays\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-alert-status\n          description: \"Update the status of a Varonis DatAlert alert to Open or Under Investigation, with optional investigation note.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"varonis-datalert.update-alert-status\"\n          with:\n            alertId: \"tools.alertId\"\n            status: \"tools.status\"\n            note: \"tools.note\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: close-alert\n          description: \"Close a Varonis DatAlert alert with a resolution reason such as Resolved, Legitimate activity, or Misconfiguration.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"varonis-datalert.close-alert\"\n          with:\n            alertId: \"tools.alertId\"\n            closeReason: \"tools.closeReason\"\n            note: \"tools.note\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: add-alert-note\n          description: \"Add an investigation note to a Varonis DatAlert alert to document findings and remediation steps.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"varonis-datalert.add-alert-note\"\n          with:\n            alertId: \"tools.alertId\"\n            note: \"tools.note\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: get-alerted-events\n          description: \"Retrieve forensic events associated with a Varonis alert for threat hunting and incident investigation.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"varonis-datalert.get-alerted-events\"\n          with:\n            alertId: \"tools.alertId\"\n            lastDays: \"tools.lastDays\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-threat-models\n          description: \"List Varonis DatAlert threat model definitions including category, severity, and MITRE ATT&CK alignment.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"varonis-datalert.get-threat-models\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/varonis/refs/heads/main/capabilities/threat-detection-response.yaml
tags:
- Varonis
- Data Security
- Threat Detection
- Incident Response
- Security Operations
- SOC
tools:
- description: Retrieve Varonis DatAlert security alerts with filtering by threat model, severity, status, and time range.
  hints:
    openWorld: false
    readOnly: true
  name: get-alerts
- description: Update the status of a Varonis DatAlert alert to Open or Under Investigation, with optional investigation note.
  hints:
    idempotent: true
    readOnly: false
  name: update-alert-status
- description: Close a Varonis DatAlert alert with a resolution reason such as Resolved, Legitimate activity, or Misconfiguration.
  hints:
    idempotent: false
    readOnly: false
  name: close-alert
- description: Add an investigation note to a Varonis DatAlert alert to document findings and remediation steps.
  hints:
    idempotent: false
    readOnly: false
  name: add-alert-note
- description: Retrieve forensic events associated with a Varonis alert for threat hunting and incident investigation.
  hints:
    openWorld: true
    readOnly: true
  name: get-alerted-events
- description: List Varonis DatAlert threat model definitions including category, severity, and MITRE ATT&CK alignment.
  hints:
    openWorld: false
    readOnly: true
  name: get-threat-models
---
