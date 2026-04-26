---
consumed_apis:
- rest-api
- event-api
description: Application performance monitoring workflow combining application metrics, deployments, hosts, and custom events for developers tracking application health and release impact.
layout: capability
name: New Relic Application Monitoring
operations:
- description: List all monitored applications
  method: GET
  name: get-applications
  path: /v1/applications
- description: Get application details
  method: GET
  name: get-application
  path: /v1/applications/{id}
- description: Update application settings
  method: PUT
  name: update-application
  path: /v1/applications/{id}
- description: List deployments for an application
  method: GET
  name: get-deployments
  path: /v1/deployments/{applicationId}
- description: Record a new deployment
  method: POST
  name: create-deployment
  path: /v1/deployments/{applicationId}
- description: List hosts for an application
  method: GET
  name: get-application-hosts
  path: /v1/hosts/{applicationId}
- description: List available metric names
  method: GET
  name: get-application-metrics
  path: /v1/metrics/{applicationId}
- description: Query metric data for an application
  method: GET
  name: get-application-metrics-data
  path: /v1/metrics/{applicationId}/data
- description: List key transactions
  method: GET
  name: get-key-transactions
  path: /v1/key-transactions
- description: Send custom events for application tracking
  method: POST
  name: send-events
  path: /v1/events/{accountId}
personas: []
provider_name: New Relic
provider_slug: new-relic
search_terms:
- update application
- apm
- list key transactions
- get application hosts
- analytics
- new relic
- performance
- get or update an application
- list available metric names for an application
- update application settings
- query metric data for an application
- send custom events for application tracking
- get applications
- list deployments for an application
- observability
- application monitoring
- get key transactions
- deployments
- platform
- query metric data
- query metric data points for an application
- developer
- get application
- get deployments
- list hosts for an application
- analysis
- infrastructure
- monitoring
- manage deployments
- get details of a specific application
- list deployment records for an application
- record a new deployment for an application
- record a new deployment
- list all monitored applications
- get application metrics
- devops
- create deployment
- list available metric names
- send events
- list application metrics
- list applications
- get application details
- send custom events
- list application hosts
- get application metrics data
slug: application-monitoring
tags:
- New Relic
- Application Monitoring
- Developer
- APM
- Deployments
tools:
- description: List all monitored applications
  hints:
    openWorld: true
    readOnly: true
  name: get-applications
- description: Get details of a specific application
  hints:
    openWorld: true
    readOnly: true
  name: get-application
- description: Update application settings
  hints:
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-application
- description: List deployment records for an application
  hints:
    openWorld: true
    readOnly: true
  name: get-deployments
- description: Record a new deployment for an application
  hints:
    openWorld: true
    readOnly: false
  name: create-deployment
- description: List hosts for an application
  hints:
    openWorld: true
    readOnly: true
  name: get-application-hosts
- description: List available metric names for an application
  hints:
    openWorld: true
    readOnly: true
  name: get-application-metrics
- description: Query metric data points for an application
  hints:
    openWorld: true
    readOnly: true
  name: get-application-metrics-data
- description: List key transactions
  hints:
    openWorld: true
    readOnly: true
  name: get-key-transactions
- description: Send custom events for application tracking
  hints:
    openWorld: true
    readOnly: false
  name: send-events
---
