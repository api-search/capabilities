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
- auto-scaling configuration
- list auto-scaling configurations
- list github or bitbucket source code connections
- auto-scaling and observability configuration
- application service lifecycle
- list auto-scaling configurations for capacity management
- trigger a new deployment
- serverless
- Platform Engineer
- update service
- list all app runner services and their status
- network connectivity including custom domains and vpc access
- resume service
- pause a service to save costs during idle periods
- list auto scaling configurations
- deploy, manage, and scale containerized applications with app runner
- deploy a new containerized web application or api
- aws app runner
- describe service
- deploys and manages containerized web applications and apis
- deploy a new containerized application
- start deployment
- update application configuration, image, or code source
- pause service
- trigger a new deployment of the current image or code
- resume a paused service to resume traffic handling
- deployment
- service lifecycle from creation to deletion
- manages app runner infrastructure, scaling, and vpc connectivity
- vpc connectivity management
- list vpc connectors
- list vpc connectors for private backend connectivity
- containers
- delete service
- aws
- list all app runner services
- get detailed status and configuration of an app runner service
- create service
- list services
- Developer
- list connections
- ci/cd
- microservices
- deployment management
- delete an app runner service and all its resources
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
