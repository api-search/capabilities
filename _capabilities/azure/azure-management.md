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
- databases
- management
- list subscription resources
- azure resource management
- azure
- platform as a service
- list provider resources
- resource management
- machine learning
- list subscriptions
- networking
- list providers
- list resourcegroup resources
- list resource groups
- list resource resources
- list resources
- list
- list all resources
- infrastructure
- cloud
- storage
- cloud computing
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
