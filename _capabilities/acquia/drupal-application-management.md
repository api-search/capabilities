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
- list applications
- cloud ide environments and platform notification management
- acquia
- developer building and deploying drupal applications on acquia cloud
- environments
- organization management
- list all organizations
- applications
- engineer managing ci/cd pipelines, deployments, and environment configuration
- list environments for an application
- DevOps Engineer
- get application details
- list all environments (dev, staging, prod) for an acquia cloud application
- devops
- get the current acquia cloud user account profile and permissions
- list all organizations the current acquia user belongs to
- get detailed information about a specific acquia cloud application
- drupal
- get current user account details
- list all acquia cloud drupal applications the current user can access
- get account
- list organizations
- acquia platform admin managing organizations, teams, and subscriptions
- Platform Administrator
- Drupal Developer
- get environment details
- drupal application hosting lifecycle on acquia cloud platform
- drupal application lifecycle management
- experience
- application environment operations
- content
- get application
- get detailed information about a specific acquia cloud environment
- get environment
- current user account
- cloud
- application discovery, environment management, and organization administration
- user, team, and organizational access control management
- list environments
- list all accessible acquia cloud applications
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
