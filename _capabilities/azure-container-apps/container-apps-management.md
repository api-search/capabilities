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
- create or update an azure container app
- list container apps
- container app deployment and management
- manage containerized applications, environments, and jobs
- create container app
- serverless
- manages the container infrastructure and environments
- deploys and manages containerized application workloads
- list all managed environments
- serverless compute and job execution
- container app management
- DevOps Engineer
- list all managed container app environments
- list environments
- managed environment management
- kubernetes
- containers
- devops
- delete an azure container app
- list all azure container apps in a subscription
- list all container apps
- container app job management
- azure
- list jobs
- dapr
- delete container app
- list all container app jobs
- microservices
- Platform Engineer
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
