---
categories:
- container-orchestration
consumed_apis:
- azure-container-apps
description: Workflow capability for managing containerized applications, environments, and jobs in Azure Container Apps. Used by platform engineers and DevOps teams.
layout: capability
name: Azure Container Apps Management
operations:
- description: List all container apps
  method: GET
  name: list-container-apps
  path: /v1/container-apps
- description: List all managed environments
  method: GET
  name: list-environments
  path: /v1/environments
- description: List all container app jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Azure Container Apps
provider_slug: azure-container-apps
search_terms:
- list all container apps
- devops
- container app deployment and management
- delete container app
- deploys and manages containerized application workloads
- create or update an azure container app
- kubernetes
- list all managed container app environments
- azure
- list jobs
- list all azure container apps in a subscription
- DevOps Engineer
- manage containerized applications, environments, and jobs
- manages the container infrastructure and environments
- Platform Engineer
- serverless compute and job execution
- containers
- list environments
- delete an azure container app
- microservices
- serverless
- managed environment management
- dapr
- container app job management
- list all container app jobs
- list all managed environments
- create container app
- container app management
- list container apps
slug: container-apps-management
tags:
- Azure
- Containers
- Microservices
- Serverless
- DevOps
tools:
- description: List all Azure Container Apps in a subscription
  hints:
    openWorld: true
    readOnly: true
  name: list-container-apps
- description: Create or update an Azure Container App
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: create-container-app
- description: Delete an Azure Container App
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-container-app
- description: List all managed container app environments
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
- description: List all container app jobs
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
---
