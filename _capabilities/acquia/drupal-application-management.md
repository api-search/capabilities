---
consumed_apis:
- acquia-cloud
description: Unified workflow for managing Drupal applications on Acquia Cloud, including application discovery, environment management, organization administration, and account operations. Used by Drupal developers, DevOps engineers, and platform administrators to automate Acquia Cloud Platform workflows.
layout: capability
name: Acquia Drupal Application Management
operations:
- description: List all accessible Acquia Cloud applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: Get application details
  method: GET
  name: get-application
  path: /v1/applications
- description: List environments for an application
  method: GET
  name: list-environments
  path: /v1/environments
- description: Get environment details
  method: GET
  name: get-environment
  path: /v1/environments
- description: List all organizations
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: Get current user account details
  method: GET
  name: get-account
  path: /v1/account
personas: []
provider_name: Acquia
provider_slug: acquia
search_terms:
- get current user account details
- get detailed information about a specific acquia cloud environment
- organization management
- list all organizations the current acquia user belongs to
- get detailed information about a specific acquia cloud application
- Drupal Developer
- cloud ide environments and platform notification management
- get the current acquia cloud user account profile and permissions
- list applications
- cloud
- get account
- get application
- devops
- user, team, and organizational access control management
- get environment
- applications
- acquia platform admin managing organizations, teams, and subscriptions
- content
- list environments
- acquia
- list all organizations
- drupal application hosting lifecycle on acquia cloud platform
- application environment operations
- engineer managing ci/cd pipelines, deployments, and environment configuration
- experience
- drupal
- get environment details
- environments
- drupal application lifecycle management
- list all environments (dev, staging, prod) for an acquia cloud application
- developer building and deploying drupal applications on acquia cloud
- list all accessible acquia cloud applications
- Platform Administrator
- DevOps Engineer
- get application details
- list organizations
- list environments for an application
- list all acquia cloud drupal applications the current user can access
- application discovery, environment management, and organization administration
- current user account
slug: drupal-application-management
tags:
- Acquia
- Applications
- Cloud
- DevOps
- Drupal
- Environments
tools:
- description: List all Acquia Cloud Drupal applications the current user can access
  hints:
    openWorld: true
    readOnly: true
  name: list-applications
- description: Get detailed information about a specific Acquia Cloud application
  hints:
    idempotent: true
    readOnly: true
  name: get-application
- description: List all environments (dev, staging, prod) for an Acquia Cloud application
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
- description: Get detailed information about a specific Acquia Cloud environment
  hints:
    idempotent: true
    readOnly: true
  name: get-environment
- description: List all organizations the current Acquia user belongs to
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: Get the current Acquia Cloud user account profile and permissions
  hints:
    idempotent: true
    readOnly: true
  name: get-account
---
