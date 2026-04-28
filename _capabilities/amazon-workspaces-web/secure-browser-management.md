---
categories: []
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
- list all workspaces web secure browser portals.
- secure browser
- list trust stores
- browser policy management.
- portal and resource provisioning
- user settings management.
- administration
- list browser settings.
- workflow for it administrators to manage workspaces web portals and their associated security and network configurations.
- configures browser policies and access controls.
- create a portal.
- list portals
- list network settings
- trust store management.
- list ssl certificate trust stores.
- browser policy and access control enforcement
- virtual desktop
- list user settings.
- network configuration management.
- Security Engineer
- secure remote browser access infrastructure
- list network settings.
- create portal
- end user computing
- list browser policy settings for portals.
- zero trust
- portal management.
- list secure browser portals.
- list network settings for portal connectivity.
- list browser settings
- create a new secure browser portal.
- manages workspaces web portals and configurations.
- IT Administrator
- aws
- list user settings
- list trust stores.
- list user settings configurations for portals.
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
