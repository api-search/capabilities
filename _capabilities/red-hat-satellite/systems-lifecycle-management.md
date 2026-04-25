---
consumed_apis:
- satellite-api
description: Unified workflow for managing the complete lifecycle of physical, virtual, and cloud hosts including provisioning, content management, patching, and subscription management. Used by system administrators and platform engineers.
layout: capability
name: Red Hat Satellite Systems Lifecycle Management
operations:
- description: List all managed hosts.
  method: GET
  name: list-hosts
  path: /v1/hosts
- description: Register a new host.
  method: POST
  name: create-host
  path: /v1/hosts
- description: Get host details.
  method: GET
  name: show-host
  path: /v1/hosts/{id}
- description: Update host attributes.
  method: PUT
  name: update-host
  path: /v1/hosts/{id}
- description: Delete a host.
  method: DELETE
  name: delete-host
  path: /v1/hosts/{id}
- description: List all content views.
  method: GET
  name: list-content-views
  path: /v1/content-views
- description: Create a new content view.
  method: POST
  name: create-content-view
  path: /v1/content-views
- description: Get content view details.
  method: GET
  name: show-content-view
  path: /v1/content-views/{id}
- description: Update a content view.
  method: PUT
  name: update-content-view
  path: /v1/content-views/{id}
- description: Delete a content view.
  method: DELETE
  name: delete-content-view
  path: /v1/content-views/{id}
- description: List lifecycle environments.
  method: GET
  name: list-lifecycle-environments
  path: /v1/lifecycle-environments
- description: Create a lifecycle environment.
  method: POST
  name: create-lifecycle-environment
  path: /v1/lifecycle-environments
- description: List subscriptions.
  method: GET
  name: list-subscriptions
  path: /v1/subscriptions
- description: List organizations.
  method: GET
  name: list-organizations
  path: /v1/organizations
personas: []
provider_name: Red Hat Satellite
provider_slug: red-hat-satellite
search_terms:
- update a content view.
- content management
- get host details.
- update content view
- show organization
- host power action
- create a new content view.
- promote a content view version to a lifecycle environment.
- delete host
- get details for a specific host.
- individual content view management.
- show host
- list all content views.
- execute a power action on a host (start, stop, reboot).
- publish content view
- promote content view version
- organization management.
- create a lifecycle environment.
- host management
- list all managed hosts.
- get details for a content view.
- lifecycle management
- register a new host.
- content view management.
- update host
- create content view
- list subscriptions for an organization.
- list organizations
- get content view details.
- list all organizations.
- update host attributes.
- red hat satellite
- delete a host from satellite.
- show content view
- individual host management.
- list content views
- delete a content view.
- patch management
- list lifecycle environments for an organization.
- list lifecycle environments
- systems management
- list subscriptions.
- list organizations.
- delete a host.
- show details for a specific organization.
- subscription management.
- configuration management
- list hosts
- create a new lifecycle environment.
- create host
- publish a new version of a content view.
- register a new host with satellite.
- create lifecycle environment
- list subscriptions
- host management endpoints.
- list all hosts registered with satellite.
- delete content view
- list lifecycle environments.
- lifecycle environment management.
- subscription management
- list content views in an organization.
slug: systems-lifecycle-management
tags:
- Red Hat Satellite
- Systems Management
- Lifecycle Management
- Host Management
- Content Management
tools:
- description: List all hosts registered with Satellite.
  hints:
    openWorld: true
    readOnly: true
  name: list-hosts
- description: Get details for a specific host.
  hints:
    idempotent: true
    readOnly: true
  name: show-host
- description: Register a new host with Satellite.
  hints:
    readOnly: false
  name: create-host
- description: Update host attributes.
  hints:
    idempotent: true
    readOnly: false
  name: update-host
- description: Delete a host from Satellite.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-host
- description: Execute a power action on a host (start, stop, reboot).
  hints:
    destructive: true
    readOnly: false
  name: host-power-action
- description: List content views in an organization.
  hints:
    readOnly: true
  name: list-content-views
- description: Create a new content view.
  hints:
    readOnly: false
  name: create-content-view
- description: Get details for a content view.
  hints:
    idempotent: true
    readOnly: true
  name: show-content-view
- description: Update a content view.
  hints:
    idempotent: true
    readOnly: false
  name: update-content-view
- description: Delete a content view.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-content-view
- description: Publish a new version of a content view.
  hints:
    readOnly: false
  name: publish-content-view
- description: Promote a content view version to a lifecycle environment.
  hints:
    readOnly: false
  name: promote-content-view-version
- description: List subscriptions for an organization.
  hints:
    readOnly: true
  name: list-subscriptions
- description: List lifecycle environments for an organization.
  hints:
    readOnly: true
  name: list-lifecycle-environments
- description: Create a new lifecycle environment.
  hints:
    readOnly: false
  name: create-lifecycle-environment
- description: List all organizations.
  hints:
    readOnly: true
  name: list-organizations
- description: Show details for a specific organization.
  hints:
    idempotent: true
    readOnly: true
  name: show-organization
---
