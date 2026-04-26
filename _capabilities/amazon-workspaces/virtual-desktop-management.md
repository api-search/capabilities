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
- provision new virtual desktop workspaces for users.
- list registered directories for workspace deployment.
- end user computing
- desktop
- list workspace images.
- desktop as a service
- provision new virtual desktops.
- list available workspace images for provisioning.
- virtual desktop lifecycle management.
- virtual desktop
- create workspaces
- remote work and desktop-as-a-service infrastructure
- aws
- describe workspace directories
- administration
- directory management.
- IT Administrator
- list directories.
- hardware bundle catalog.
- list available bundles.
- reboot virtual desktop workspaces to resolve issues.
- cloud-based virtual desktop provisioning and management
- permanently terminate virtual desktop workspaces.
- list available hardware configuration bundles.
- list and describe all virtual desktop workspaces.
- describe workspaces
- terminate workspaces
- describe workspace images
- workflow for it administrators to provision and manage amazon workspaces virtual desktops including lifecycle, bundles, directories, and images.
- list virtual desktops.
- describe workspace bundles
- it administration of desktop resources
- manages workspaces provisioning, lifecycle, and policy.
- workspace image management.
- reboot workspaces
- End User Computing Engineer
- designs and operates virtual desktop infrastructure.
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
