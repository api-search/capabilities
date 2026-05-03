---
categories:
- monitoring
consumed_apis:
- managed-prometheus
description: Workflow capability for DevOps and SRE teams to manage Prometheus workspaces, configure alerting, and define recording rules for container metrics monitoring.
layout: capability
name: Amazon Managed Service for Prometheus - Metrics Monitoring Workflow
operations:
- description: List workspaces
  method: GET
  name: list-workspaces
  path: /v1/workspaces
- description: Create a workspace
  method: POST
  name: create-workspace
  path: /v1/workspaces
- description: Create alert manager
  method: POST
  name: create-alert-manager
  path: /v1/workspaces/{id}/alert-manager
personas: []
provider_name: Amazon Managed Service for Prometheus
provider_slug: amazon-managed-prometheus
search_terms:
- create prometheus workspace
- prometheus workspaces
- create prometheus recording and alerting rules namespace
- monitoring
- list all prometheus workspaces
- SRE
- create recording rules
- create alert manager
- list all prometheus rule group namespaces
- alert manager configuration
- configure alert manager
- list prometheus workspaces
- create a workspace
- alerting
- get workspace details and prometheus remote write endpoint url
- amazon
- list rule groups
- containers
- configure alert manager for prometheus alerting notifications
- list workspaces
- create a new prometheus workspace for storing container metrics
- describe prometheus workspace
- observability
- prometheus
- create workspace
- DevOps Engineer
slug: metrics-monitoring-workflow
source_filename: metrics-monitoring-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"Amazon Managed Service for Prometheus - Metrics Monitoring Workflow\"\n  description: \"Workflow capability for DevOps and SRE teams to manage Prometheus workspaces, configure alerting, and define recording rules for container metrics monitoring.\"\n  tags:\n    - Amazon\n    - Prometheus\n    - Monitoring\n    - Observability\n    - Containers\n    - Alerting\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n    - import: managed-prometheus\n      location: ./shared/managed-prometheus.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: prometheus-monitoring-api\n      description: \"Unified REST API for Prometheus metrics monitoring workflows.\"\n      resources:\n        - path: /v1/workspaces\n          name: workspaces\n\
  \          description: \"Prometheus workspaces\"\n          operations:\n            - method: GET\n              name: list-workspaces\n              description: \"List workspaces\"\n              call: \"managed-prometheus.list-workspaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-workspace\n              description: \"Create a workspace\"\n              call: \"managed-prometheus.create-workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workspaces/{id}/alert-manager\n          name: alert-manager\n          description: \"Alert manager configuration\"\n          operations:\n            - method: POST\n              name: create-alert-manager\n              description: \"Create alert manager\"\n              call: \"managed-prometheus.create-alert-manager-definition\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: prometheus-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Prometheus metrics monitoring.\"\n      tools:\n        - name: list-prometheus-workspaces\n          description: \"List all Prometheus workspaces\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"managed-prometheus.list-workspaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-prometheus-workspace\n          description: \"Create a new Prometheus workspace for storing container metrics\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"managed-prometheus.create-workspace\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: describe-prometheus-workspace\n          description: \"Get workspace details and Prometheus remote write endpoint URL\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"managed-prometheus.describe-workspace\"\n          with:\n            workspaceId: \"tools.workspaceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: configure-alert-manager\n          description: \"Configure alert manager for Prometheus alerting notifications\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"managed-prometheus.create-alert-manager-definition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-recording-rules\n          description: \"Create Prometheus recording and alerting rules namespace\"\n     \
  \     hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"managed-prometheus.create-rule-groups-namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-rule-groups\n          description: \"List all Prometheus rule group namespaces\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"managed-prometheus.list-rule-groups-namespaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-managed-prometheus/refs/heads/main/capabilities/metrics-monitoring-workflow.yaml
tags:
- Amazon
- Prometheus
- Monitoring
- Observability
- Containers
- Alerting
tools:
- description: List all Prometheus workspaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-prometheus-workspaces
- description: Create a new Prometheus workspace for storing container metrics
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-prometheus-workspace
- description: Get workspace details and Prometheus remote write endpoint URL
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describe-prometheus-workspace
- description: Configure alert manager for Prometheus alerting notifications
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: configure-alert-manager
- description: Create Prometheus recording and alerting rules namespace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-recording-rules
- description: List all Prometheus rule group namespaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-rule-groups
---
