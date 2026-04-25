---
consumed_apis:
- workspaces
description: Unified workflow for IT administrators and end user computing teams to provision, manage, and maintain Amazon WorkSpaces virtual desktops at scale, including workspace lifecycle, bundle management, directory integration, and image management.
layout: capability
name: Amazon WorkSpaces Virtual Desktop Management
operations:
- description: List virtual desktops.
  method: GET
  name: describe-workspaces
  path: /v1/workspaces
- description: Provision new virtual desktops.
  method: POST
  name: create-workspaces
  path: /v1/workspaces
- description: List available bundles.
  method: GET
  name: describe-workspace-bundles
  path: /v1/bundles
- description: List directories.
  method: GET
  name: describe-workspace-directories
  path: /v1/directories
- description: List workspace images.
  method: GET
  name: describe-workspace-images
  path: /v1/images
personas: []
provider_name: Amazon WorkSpaces
provider_slug: amazon-workspaces
search_terms:
- cloud-based virtual desktop provisioning and management
- permanently terminate virtual desktop workspaces.
- list available workspace images for provisioning.
- directory management.
- list workspace images.
- list available hardware configuration bundles.
- reboot virtual desktop workspaces to resolve issues.
- administration
- desktop
- describe workspaces
- workspace image management.
- provision new virtual desktops.
- terminate workspaces
- workflow for it administrators to provision and manage amazon workspaces virtual desktops including lifecycle, bundles, directories, and images.
- create workspaces
- End User Computing Engineer
- list available bundles.
- describe workspace directories
- list registered directories for workspace deployment.
- remote work and desktop-as-a-service infrastructure
- it administration of desktop resources
- describe workspace images
- manages workspaces provisioning, lifecycle, and policy.
- virtual desktop lifecycle management.
- reboot workspaces
- list virtual desktops.
- IT Administrator
- describe workspace bundles
- list directories.
- virtual desktop
- end user computing
- desktop as a service
- aws
- hardware bundle catalog.
- list and describe all virtual desktop workspaces.
- designs and operates virtual desktop infrastructure.
- provision new virtual desktop workspaces for users.
slug: virtual-desktop-management
tags:
- AWS
- Virtual Desktop
- End User Computing
- Desktop as a Service
- Administration
tools:
- description: List and describe all virtual desktop workspaces.
  hints:
    openWorld: true
    readOnly: true
  name: describe-workspaces
- description: Provision new virtual desktop workspaces for users.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-workspaces
- description: Permanently terminate virtual desktop workspaces.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: terminate-workspaces
- description: Reboot virtual desktop workspaces to resolve issues.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: reboot-workspaces
- description: List available hardware configuration bundles.
  hints:
    openWorld: true
    readOnly: true
  name: describe-workspace-bundles
- description: List registered directories for workspace deployment.
  hints:
    openWorld: true
    readOnly: true
  name: describe-workspace-directories
- description: List available workspace images for provisioning.
  hints:
    openWorld: true
    readOnly: true
  name: describe-workspace-images
---
