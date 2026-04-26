---
consumed_apis:
- app-runner
description: Workflow for developers and platform engineers to deploy, manage, and monitor containerized web applications and APIs using AWS App Runner. Covers service lifecycle, deployments, auto-scaling, and VPC connectivity.
layout: capability
name: AWS App Runner Application Deployment Workflow
operations:
- description: List all App Runner services
  method: GET
  name: list-services
  path: /v1/services
- description: Deploy a new containerized application
  method: POST
  name: create-service
  path: /v1/services
- description: Trigger a new deployment
  method: POST
  name: start-deployment
  path: /v1/services/{serviceArn}/deployments
- description: List auto-scaling configurations
  method: GET
  name: list-auto-scaling-configurations
  path: /v1/auto-scaling-configurations
- description: List VPC connectors
  method: GET
  name: list-vpc-connectors
  path: /v1/vpc-connectors
personas: []
provider_name: AWS App Runner
provider_slug: aws-app-runner
search_terms:
- create service
- list vpc connectors
- list auto-scaling configurations for capacity management
- deploy a new containerized application
- delete service
- pause a service to save costs during idle periods
- describe service
- resume a paused service to resume traffic handling
- deploys and manages containerized web applications and apis
- delete an app runner service and all its resources
- serverless
- list all app runner services and their status
- update service
- aws app runner
- aws
- service lifecycle from creation to deletion
- trigger a new deployment of the current image or code
- list github or bitbucket source code connections
- list auto scaling configurations
- get detailed status and configuration of an app runner service
- auto-scaling and observability configuration
- resume service
- trigger a new deployment
- vpc connectivity management
- list services
- containers
- list vpc connectors for private backend connectivity
- pause service
- network connectivity including custom domains and vpc access
- deployment management
- deploy, manage, and scale containerized applications with app runner
- Platform Engineer
- microservices
- start deployment
- manages app runner infrastructure, scaling, and vpc connectivity
- Developer
- list connections
- update application configuration, image, or code source
- list auto-scaling configurations
- auto-scaling configuration
- deployment
- deploy a new containerized web application or api
- ci/cd
- application service lifecycle
- list all app runner services
slug: app-deployment-workflow
tags:
- AWS App Runner
- AWS
- Containers
- Deployment
- Serverless
- CI/CD
tools:
- description: List all App Runner services and their status
  hints:
    openWorld: true
    readOnly: true
  name: list-services
- description: Deploy a new containerized web application or API
  hints:
    readOnly: false
  name: create-service
- description: Get detailed status and configuration of an App Runner service
  hints:
    readOnly: true
  name: describe-service
- description: Update application configuration, image, or code source
  hints:
    readOnly: false
  name: update-service
- description: Delete an App Runner service and all its resources
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-service
- description: Trigger a new deployment of the current image or code
  hints:
    readOnly: false
  name: start-deployment
- description: Pause a service to save costs during idle periods
  hints:
    readOnly: false
  name: pause-service
- description: Resume a paused service to resume traffic handling
  hints:
    readOnly: false
  name: resume-service
- description: List GitHub or Bitbucket source code connections
  hints:
    readOnly: true
  name: list-connections
- description: List auto-scaling configurations for capacity management
  hints:
    readOnly: true
  name: list-auto-scaling-configurations
- description: List VPC connectors for private backend connectivity
  hints:
    readOnly: true
  name: list-vpc-connectors
---
