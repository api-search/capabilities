---
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
- list formula resources
- list virtualmachine resources
- cloud
- list custom images
- list all resources
- management
- list customimage resources
- resource management
- list labs
- list environment resources
- list environments
- infrastructure
- testing
- development
- list lab resources
- azure
- azure resource management
- list virtual machines
- list formulas
- labs
- virtual machines
- list
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
