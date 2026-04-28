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
- labs
- management
- list lab resources
- azure resource management
- list virtual machines
- testing
- list
- list all resources
- list environments
- development
- list custom images
- list environment resources
- list labs
- list virtualmachine resources
- list formula resources
- azure
- infrastructure
- resource management
- list customimage resources
- virtual machines
- cloud
- list formulas
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
