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
- observability
- developer
- list available metric names
- get application
- query metric data for an application
- send events
- list deployments for an application
- list application hosts
- list available metric names for an application
- update application
- monitoring
- infrastructure
- devops
- get application details
- analytics
- list application metrics
- list applications
- get applications
- create deployment
- get or update an application
- apm
- list deployment records for an application
- query metric data points for an application
- list key transactions
- new relic
- application monitoring
- deployments
- get application hosts
- list all monitored applications
- send custom events for application tracking
- manage deployments
- analysis
- query metric data
- get deployments
- send custom events
- get key transactions
- get application metrics
- list hosts for an application
- platform
- get details of a specific application
- record a new deployment for an application
- get application metrics data
- update application settings
- record a new deployment
- performance
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
