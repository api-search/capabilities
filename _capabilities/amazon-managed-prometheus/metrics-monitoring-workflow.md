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
- list rule groups
- containers
- configure alert manager for prometheus alerting notifications
- list all prometheus workspaces
- create a workspace
- describe prometheus workspace
- DevOps Engineer
- list prometheus workspaces
- amazon
- configure alert manager
- observability
- create prometheus workspace
- prometheus workspaces
- create a new prometheus workspace for storing container metrics
- create prometheus recording and alerting rules namespace
- get workspace details and prometheus remote write endpoint url
- aws
- list workspaces
- prometheus
- create recording rules
- SRE
- alerting
- alert manager configuration
- monitoring
- create workspace
- create alert manager
- list all prometheus rule group namespaces
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
