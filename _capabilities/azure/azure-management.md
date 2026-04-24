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
- list provider resources
- list all resources
- cloud
- list providers
- platform as a service
- list subscription resources
- list subscriptions
- networking
- azure resource management
- list resource resources
- list resource groups
- machine learning
- list resourcegroup resources
- resource management
- management
- list
- cloud computing
- list resources
- azure
- storage
- infrastructure
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
