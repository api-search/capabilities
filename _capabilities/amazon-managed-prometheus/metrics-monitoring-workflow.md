---
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
- create prometheus recording and alerting rules namespace
- DevOps Engineer
- create a new prometheus workspace for storing container metrics
- monitoring
- prometheus workspaces
- containers
- list all prometheus workspaces
- list prometheus workspaces
- alerting
- list workspaces
- prometheus
- create recording rules
- create workspace
- list rule groups
- alert manager configuration
- describe prometheus workspace
- observability
- create a workspace
- aws
- SRE
- create alert manager
- get workspace details and prometheus remote write endpoint url
- amazon
- list all prometheus rule group namespaces
- configure alert manager for prometheus alerting notifications
- configure alert manager
slug: metrics-monitoring-workflow
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
