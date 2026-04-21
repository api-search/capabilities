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
- provision new virtual desktops.
- it administration of desktop resources
- list available bundles.
- cloud-based virtual desktop provisioning and management
- virtual desktop
- provision new virtual desktop workspaces for users.
- permanently terminate virtual desktop workspaces.
- IT Administrator
- workspace image management.
- directory management.
- workflow for it administrators to provision and manage amazon workspaces virtual desktops including lifecycle, bundles, directories, and images.
- terminate workspaces
- list registered directories for workspace deployment.
- list virtual desktops.
- describe workspaces
- reboot workspaces
- end user computing
- hardware bundle catalog.
- list workspace images.
- desktop as a service
- describe workspace directories
- reboot virtual desktop workspaces to resolve issues.
- list available hardware configuration bundles.
- describe workspace bundles
- administration
- manages workspaces provisioning, lifecycle, and policy.
- describe workspace images
- list directories.
- create workspaces
- virtual desktop lifecycle management.
- End User Computing Engineer
- aws
- desktop
- list and describe all virtual desktop workspaces.
- remote work and desktop-as-a-service infrastructure
- designs and operates virtual desktop infrastructure.
- list available workspace images for provisioning.
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
