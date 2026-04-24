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
- list all container apps
- serverless
- Platform Engineer
- container app job management
- deploys and manages containerized application workloads
- devops
- list container apps
- create container app
- list all container app jobs
- manages the container infrastructure and environments
- delete an azure container app
- list environments
- serverless compute and job execution
- create or update an azure container app
- list jobs
- manage containerized applications, environments, and jobs
- list all azure container apps in a subscription
- managed environment management
- delete container app
- container app deployment and management
- containers
- container app management
- dapr
- list all managed environments
- azure
- kubernetes
- list all managed container app environments
- microservices
- DevOps Engineer
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
