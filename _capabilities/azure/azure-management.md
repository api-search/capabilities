---
consumed_apis:
- azure
description: Workflow capability for managing Microsoft Azure resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Microsoft Azure Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Microsoft Azure
provider_slug: azure
search_terms:
- list
- machine learning
- list provider resources
- databases
- list subscription resources
- cloud
- cloud computing
- platform as a service
- list resources
- list all resources
- management
- list providers
- resource management
- list resource groups
- infrastructure
- storage
- list resourcegroup resources
- azure
- azure resource management
- networking
- list resource resources
- list subscriptions
slug: azure-management
tags:
- Azure
- Cloud
- Management
tools:
- description: List Subscription resources
  hints:
    openWorld: true
    readOnly: true
  name: list-subscriptions
- description: List ResourceGroup resources
  hints:
    openWorld: true
    readOnly: true
  name: list-resource-groups
- description: List Resource resources
  hints:
    openWorld: true
    readOnly: true
  name: list-resources
- description: List Provider resources
  hints:
    openWorld: true
    readOnly: true
  name: list-providers
---
