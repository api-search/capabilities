---
categories:
- content-management
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
- update host attributes.
- list all managed hosts.
- delete host
- delete content view
- subscription management.
- list subscriptions.
- promote a content view version to a lifecycle environment.
- create a lifecycle environment.
- show organization
- list lifecycle environments
- list subscriptions for an organization.
- red hat satellite
- list lifecycle environments for an organization.
- show content view
- subscription management
- list all hosts registered with satellite.
- host management endpoints.
- list organizations
- individual content view management.
- update a content view.
- create a new content view.
- list lifecycle environments.
- update content view
- publish content view
- list organizations.
- publish a new version of a content view.
- get details for a specific host.
- delete a host.
- configuration management
- register a new host with satellite.
- promote content view version
- execute a power action on a host (start, stop, reboot).
- individual host management.
- delete a content view.
- organization management.
- list subscriptions
- content view management.
- show host
- register a new host.
- get details for a content view.
- content management
- get host details.
- host power action
- list content views in an organization.
- create lifecycle environment
- list hosts
- delete a host from satellite.
- list content views
- lifecycle management
- create a new lifecycle environment.
- create host
- list all content views.
- patch management
- lifecycle environment management.
- update host
- list all organizations.
- get content view details.
- host management
- show details for a specific organization.
- systems management
- create content view
slug: systems-lifecycle-management
source_filename: systems-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Red Hat Satellite Systems Lifecycle Management\"\n  description: \"Unified workflow for managing the complete lifecycle of physical, virtual, and cloud hosts including provisioning, content management, patching, and subscription management. Used by system administrators and platform engineers.\"\n  tags:\n    - Red Hat Satellite\n    - Systems Management\n    - Lifecycle Management\n    - Host Management\n    - Content Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SATELLITE_USERNAME: SATELLITE_USERNAME\n      SATELLITE_PASSWORD: SATELLITE_PASSWORD\n\ncapability:\n  consumes:\n    - import: satellite-api\n      location: ./shared/satellite-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: satellite-lifecycle-api\n      description: \"Unified REST API for Red Hat Satellite systems lifecycle management.\"\n      resources:\n        - path:\
  \ /v1/hosts\n          name: hosts\n          description: \"Host management endpoints.\"\n          operations:\n            - method: GET\n              name: list-hosts\n              description: \"List all managed hosts.\"\n              call: \"satellite-api.list-hosts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-host\n              description: \"Register a new host.\"\n              call: \"satellite-api.create-host\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/hosts/{id}\n          name: host-details\n          description: \"Individual host management.\"\n          operations:\n            - method: GET\n              name: show-host\n              description: \"Get host details.\"\n              call: \"satellite-api.show-host\"\n              with:\n                id: \"rest.id\"\n   \
  \           outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-host\n              description: \"Update host attributes.\"\n              call: \"satellite-api.update-host\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-host\n              description: \"Delete a host.\"\n              call: \"satellite-api.delete-host\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content-views\n          name: content-views\n          description: \"Content view management.\"\n          operations:\n            - method: GET\n              name: list-content-views\n              description: \"List all content views.\"\n\
  \              call: \"satellite-api.list-content-views\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-content-view\n              description: \"Create a new content view.\"\n              call: \"satellite-api.create-content-view\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content-views/{id}\n          name: content-view-details\n          description: \"Individual content view management.\"\n          operations:\n            - method: GET\n              name: show-content-view\n              description: \"Get content view details.\"\n              call: \"satellite-api.show-content-view\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-content-view\n\
  \              description: \"Update a content view.\"\n              call: \"satellite-api.update-content-view\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-content-view\n              description: \"Delete a content view.\"\n              call: \"satellite-api.delete-content-view\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/lifecycle-environments\n          name: lifecycle-environments\n          description: \"Lifecycle environment management.\"\n          operations:\n            - method: GET\n              name: list-lifecycle-environments\n              description: \"List lifecycle environments.\"\n              call: \"satellite-api.list-lifecycle-environments\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-lifecycle-environment\n              description: \"Create a lifecycle environment.\"\n              call: \"satellite-api.create-lifecycle-environment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: \"Subscription management.\"\n          operations:\n            - method: GET\n              name: list-subscriptions\n              description: \"List subscriptions.\"\n              call: \"satellite-api.list-subscriptions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations\n          name: organizations\n          description: \"Organization management.\"\n          operations:\n            - method: GET\n              name: list-organizations\n\
  \              description: \"List organizations.\"\n              call: \"satellite-api.list-organizations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: satellite-lifecycle-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Red Hat Satellite systems lifecycle management.\"\n      tools:\n        - name: list-hosts\n          description: \"List all hosts registered with Satellite.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"satellite-api.list-hosts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: show-host\n          description: \"Get details for a specific host.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"satellite-api.show-host\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: create-host\n          description: \"Register a new host with Satellite.\"\n          hints:\n            readOnly: false\n          call: \"satellite-api.create-host\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-host\n          description: \"Update host attributes.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"satellite-api.update-host\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-host\n          description: \"Delete a host from Satellite.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"satellite-api.delete-host\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n      \
  \      - type: object\n              mapping: \"$.\"\n        - name: host-power-action\n          description: \"Execute a power action on a host (start, stop, reboot).\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"satellite-api.host-power-action\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-content-views\n          description: \"List content views in an organization.\"\n          hints:\n            readOnly: true\n          call: \"satellite-api.list-content-views\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-content-view\n          description: \"Create a new content view.\"\n          hints:\n            readOnly: false\n          call: \"satellite-api.create-content-view\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: show-content-view\n          description: \"Get details for a content view.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"satellite-api.show-content-view\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-content-view\n          description: \"Update a content view.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"satellite-api.update-content-view\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-content-view\n          description: \"Delete a content view.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"satellite-api.delete-content-view\"\n          with:\n       \
  \     id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-content-view\n          description: \"Publish a new version of a content view.\"\n          hints:\n            readOnly: false\n          call: \"satellite-api.publish-content-view\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: promote-content-view-version\n          description: \"Promote a content view version to a lifecycle environment.\"\n          hints:\n            readOnly: false\n          call: \"satellite-api.promote-content-view-version\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-subscriptions\n          description: \"List subscriptions for an organization.\"\n          hints:\n            readOnly: true\n          call:\
  \ \"satellite-api.list-subscriptions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-lifecycle-environments\n          description: \"List lifecycle environments for an organization.\"\n          hints:\n            readOnly: true\n          call: \"satellite-api.list-lifecycle-environments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-lifecycle-environment\n          description: \"Create a new lifecycle environment.\"\n          hints:\n            readOnly: false\n          call: \"satellite-api.create-lifecycle-environment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-organizations\n          description: \"List all organizations.\"\n          hints:\n            readOnly: true\n          call: \"satellite-api.list-organizations\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: show-organization\n          description: \"Show details for a specific organization.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"satellite-api.show-organization\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/red-hat-satellite/refs/heads/main/capabilities/systems-lifecycle-management.yaml
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
