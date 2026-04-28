---
categories: []
consumed_apis:
- azure-test-labs
description: Workflow capability for managing Azure DevTest Labs resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure DevTest Labs Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure DevTest Labs
provider_slug: azure-test-labs
search_terms:
- list lab resources
- azure
- labs
- list environments
- list labs
- development
- list virtualmachine resources
- list custom images
- list formula resources
- infrastructure
- list environment resources
- list formulas
- list
- cloud
- testing
- virtual machines
- list all resources
- azure resource management
- resource management
- list virtual machines
- management
- list customimage resources
slug: azure-test-labs-management
tags:
- Azure
- Cloud
- Management
tools:
- description: List Lab resources
  hints:
    openWorld: true
    readOnly: true
  name: list-labs
- description: List VirtualMachine resources
  hints:
    openWorld: true
    readOnly: true
  name: list-virtual-machines
- description: List Environment resources
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
- description: List Formula resources
  hints:
    openWorld: true
    readOnly: true
  name: list-formulas
- description: List CustomImage resources
  hints:
    openWorld: true
    readOnly: true
  name: list-custom-images
---
