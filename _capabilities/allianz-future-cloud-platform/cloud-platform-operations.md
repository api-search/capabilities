---
categories:
- monitoring
consumed_apis:
- allianz-platform-services
description: Workflow capability for platform engineering and DevOps teams operating the Allianz Future Cloud Platform, combining service management, deployment automation, observability, and infrastructure provisioning.
layout: capability
name: Allianz Cloud Platform Operations
operations:
- description: List all platform services
  method: GET
  name: list-services
  path: /v1/services
- description: Register a new microservice
  method: POST
  name: register-service
  path: /v1/services
- description: List deployment history
  method: GET
  name: list-deployments
  path: /v1/services/{service_id}/deployments
- description: Trigger a deployment
  method: POST
  name: deploy-service
  path: /v1/services/{service_id}/deployments
- description: Get platform metrics
  method: GET
  name: get-metrics
  path: /v1/observability/metrics
- description: Provision infrastructure resource
  method: POST
  name: provision-resource
  path: /v1/infrastructure/resources
personas: []
provider_name: Allianz Future Cloud Platform
provider_slug: allianz-future-cloud-platform
search_terms:
- get platform metrics
- platform engineering
- list platform namespaces
- devops
- list deployment history
- provision redis, rds, msk, or s3 resources for insurance microservices
- metrics, monitoring, and alerting for platform health
- insurance
- register a new insurance microservice on the kubernetes platform
- microservice lifecycle management
- cloud platform
- list platform services
- kubernetes
- gitops-based deployment pipelines for microservice updates
- list deployment history for a platform service including version and status
- enterprise
- deploy platform service
- register a new microservice
- get metrics
- trigger a rolling, blue-green, or canary deployment for a microservice
- registration and lifecycle management of insurance microservices
- list services
- get cpu, memory, request rate, error rate, and latency metrics for a service
- list kubernetes namespaces and their team ownership on the platform
- DevOps Engineer
- register service
- deployment management for services
- list deployments
- Insurance Product Developer
- infrastructure provisioning
- Platform Engineer
- developer building insurance microservices on the allianz future cloud platform
- get service metrics
- trigger a deployment
- list all platform services
- deploy service
- provision infrastructure resource
- financial services
- get details and status of a specific platform service
- cloud resource provisioning for microservice dependencies
- observability
- list service deployments
- platform observability metrics
- register platform service
- end-to-end platform operations for devops teams
- engineer responsible for maintaining and evolving the allianz future cloud platform
- engineer deploying and operating insurance microservices on the platform
- list all microservices registered on the allianz future cloud platform
- get platform service
- provision resource
slug: cloud-platform-operations
tags:
- Cloud Platform
- DevOps
- Platform Engineering
- Kubernetes
- Observability
tools:
- description: List all microservices registered on the Allianz Future Cloud Platform
  hints:
    openWorld: false
    readOnly: true
  name: list-platform-services
- description: Register a new insurance microservice on the Kubernetes platform
  hints:
    openWorld: false
    readOnly: false
  name: register-platform-service
- description: Get details and status of a specific platform service
  hints:
    openWorld: false
    readOnly: true
  name: get-platform-service
- description: List deployment history for a platform service including version and status
  hints:
    openWorld: false
    readOnly: true
  name: list-service-deployments
- description: Trigger a rolling, blue-green, or canary deployment for a microservice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deploy-platform-service
- description: List Kubernetes namespaces and their team ownership on the platform
  hints:
    openWorld: false
    readOnly: true
  name: list-platform-namespaces
- description: Get CPU, memory, request rate, error rate, and latency metrics for a service
  hints:
    openWorld: false
    readOnly: true
  name: get-service-metrics
- description: Provision Redis, RDS, MSK, or S3 resources for insurance microservices
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: provision-infrastructure-resource
---
