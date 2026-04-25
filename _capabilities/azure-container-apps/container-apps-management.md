---
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
- Platform Engineer
- delete an azure container app
- azure
- DevOps Engineer
- list all container apps
- serverless
- list all container app jobs
- container app management
- managed environment management
- devops
- list jobs
- serverless compute and job execution
- container app deployment and management
- manage containerized applications, environments, and jobs
- delete container app
- create container app
- container app job management
- microservices
- manages the container infrastructure and environments
- dapr
- deploys and manages containerized application workloads
- list container apps
- containers
- list environments
- kubernetes
- list all managed container app environments
- create or update an azure container app
- list all managed environments
- list all azure container apps in a subscription
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
