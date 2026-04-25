---
consumed_apis:
- workspaces-web
description: Unified workflow for IT administrators to manage Amazon WorkSpaces Web portals, user settings, browser policies, network configurations, and trust stores for enterprise secure browser deployments.
layout: capability
name: Amazon WorkSpaces Web Secure Browser Management
operations:
- description: List secure browser portals.
  method: GET
  name: list-portals
  path: /v1/portals
- description: Create a portal.
  method: POST
  name: create-portal
  path: /v1/portals
- description: List user settings.
  method: GET
  name: list-user-settings
  path: /v1/user-settings
- description: List browser settings.
  method: GET
  name: list-browser-settings
  path: /v1/browser-settings
- description: List network settings.
  method: GET
  name: list-network-settings
  path: /v1/network-settings
- description: List trust stores.
  method: GET
  name: list-trust-stores
  path: /v1/trust-stores
personas: []
provider_name: Amazon WorkSpaces Web
provider_slug: amazon-workspaces-web
search_terms:
- secure browser
- portal management.
- create a portal.
- browser policy management.
- workflow for it administrators to manage workspaces web portals and their associated security and network configurations.
- zero trust
- create a new secure browser portal.
- list network settings
- manages workspaces web portals and configurations.
- Security Engineer
- list user settings configurations for portals.
- list portals
- browser policy and access control enforcement
- IT Administrator
- configures browser policies and access controls.
- create portal
- secure remote browser access infrastructure
- list ssl certificate trust stores.
- trust store management.
- end user computing
- network configuration management.
- list user settings
- list browser settings.
- user settings management.
- list all workspaces web secure browser portals.
- list user settings.
- aws
- administration
- list network settings.
- list secure browser portals.
- list browser settings
- virtual desktop
- list trust stores.
- list network settings for portal connectivity.
- list trust stores
- portal and resource provisioning
- list browser policy settings for portals.
slug: secure-browser-management
tags:
- AWS
- Secure Browser
- End User Computing
- Administration
tools:
- description: List all WorkSpaces Web secure browser portals.
  hints:
    openWorld: true
    readOnly: true
  name: list-portals
- description: Create a new secure browser portal.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-portal
- description: List user settings configurations for portals.
  hints:
    openWorld: true
    readOnly: true
  name: list-user-settings
- description: List browser policy settings for portals.
  hints:
    openWorld: true
    readOnly: true
  name: list-browser-settings
- description: List network settings for portal connectivity.
  hints:
    openWorld: true
    readOnly: true
  name: list-network-settings
- description: List SSL certificate trust stores.
  hints:
    openWorld: true
    readOnly: true
  name: list-trust-stores
---
