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
- azure resource management
- list resource groups
- azure
- resource management
- list all resources
- list
- list provider resources
- management
- list resources
- cloud computing
- machine learning
- cloud
- list resourcegroup resources
- databases
- list providers
- networking
- storage
- list resource resources
- platform as a service
- infrastructure
- list subscriptions
- list subscription resources
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
