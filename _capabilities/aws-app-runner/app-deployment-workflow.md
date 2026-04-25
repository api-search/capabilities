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
- service lifecycle from creation to deletion
- deploy a new containerized web application or api
- list github or bitbucket source code connections
- list services
- list all app runner services
- pause a service to save costs during idle periods
- vpc connectivity management
- resume a paused service to resume traffic handling
- microservices
- start deployment
- auto-scaling and observability configuration
- deploys and manages containerized web applications and apis
- list vpc connectors for private backend connectivity
- resume service
- application service lifecycle
- auto-scaling configuration
- describe service
- containers
- Platform Engineer
- update service
- pause service
- create service
- aws app runner
- ci/cd
- network connectivity including custom domains and vpc access
- list vpc connectors
- list auto-scaling configurations for capacity management
- serverless
- deploy, manage, and scale containerized applications with app runner
- deployment management
- Developer
- delete service
- trigger a new deployment
- aws
- trigger a new deployment of the current image or code
- deployment
- get detailed status and configuration of an app runner service
- list connections
- list auto-scaling configurations
- manages app runner infrastructure, scaling, and vpc connectivity
- update application configuration, image, or code source
- deploy a new containerized application
- delete an app runner service and all its resources
- list all app runner services and their status
- list auto scaling configurations
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
