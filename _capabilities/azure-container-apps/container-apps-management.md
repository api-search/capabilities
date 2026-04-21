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
- kubernetes
- list container apps
- list environments
- Platform Engineer
- list all managed container app environments
- container app management
- managed environment management
- serverless
- create container app
- list jobs
- DevOps Engineer
- delete an azure container app
- list all managed environments
- list all container apps
- dapr
- containers
- azure
- create or update an azure container app
- microservices
- devops
- serverless compute and job execution
- deploys and manages containerized application workloads
- container app job management
- delete container app
- list all container app jobs
- manages the container infrastructure and environments
- container app deployment and management
- manage containerized applications, environments, and jobs
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
