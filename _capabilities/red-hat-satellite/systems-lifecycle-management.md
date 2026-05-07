---
categories:
- content-management
consumed_apis: []
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
- host power action
- list organizations.
- subscription management
- content view management.
- subscription management.
- delete content view
- list content views
- list all hosts registered with satellite.
- individual host management.
- list lifecycle environments for an organization.
- list all content views.
- get details for a content view.
- create a lifecycle environment.
- delete a host.
- register a new host with satellite.
- list all managed hosts.
- create host
- show content view
- execute a power action on a host (start, stop, reboot).
- list content views in an organization.
- show organization
- systems management
- delete a host from satellite.
- update host attributes.
- promote content view version
- update content view
- create lifecycle environment
- host management
- organization management.
- show details for a specific organization.
- configuration management
- lifecycle management
- register a new host.
- red hat satellite
- list lifecycle environments
- create a new content view.
- get details for a specific host.
- delete host
- list subscriptions
- patch management
- list organizations
- create content view
- host management endpoints.
- list hosts
- list lifecycle environments.
- publish a new version of a content view.
- get host details.
- create a new lifecycle environment.
- update host
- content management
- get content view details.
- update a content view.
- list subscriptions for an organization.
- promote a content view version to a lifecycle environment.
- publish content view
- show host
- lifecycle environment management.
- delete a content view.
- individual content view management.
- list subscriptions.
- list all organizations.
slug: systems-lifecycle-management
source_filename: systems-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Red Hat Satellite Systems Lifecycle Management\n  description: Unified workflow for managing the complete lifecycle of physical, virtual, and cloud hosts including provisioning,\n    content management, patching, and subscription management. Used by system administrators and platform engineers.\n  tags:\n  - Red Hat Satellite\n  - Systems Management\n  - Lifecycle Management\n  - Host Management\n  - Content Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SATELLITE_USERNAME: SATELLITE_USERNAME\n    SATELLITE_PASSWORD: SATELLITE_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: satellite-api\n    baseUri: https://satellite.example.com\n    description: Red Hat Satellite REST API for systems lifecycle management.\n    authentication:\n      type: basic\n      username: '{{SATELLITE_USERNAME}}'\n      password: '{{SATELLITE_PASSWORD}}'\n    resources:\n    - name: hosts\n\
  \      path: /api/v2/hosts\n      description: Manage hosts registered with Satellite.\n      operations:\n      - name: list-hosts\n        method: GET\n        description: List all hosts registered with the Satellite server.\n        inputParameters:\n        - name: organization_id\n          in: query\n          type: integer\n          required: false\n          description: Filter by organization ID.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search query filter.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-host\n        method: POST\n\
  \        description: Register a new host with the Satellite server.\n        inputParameters:\n        - name: organization_id\n          in: query\n          type: integer\n          required: false\n          description: Organization ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            host: '{{tools.host}}'\n    - name: host-details\n      path: /api/v2/hosts/{id}\n      description: Manage individual host details.\n      operations:\n      - name: show-host\n        method: GET\n        description: Retrieve details for a specific host.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Host identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-host\n\
  \        method: PUT\n        description: Update the attributes of an existing host.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Host identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            host: '{{tools.host}}'\n      - name: delete-host\n        method: DELETE\n        description: Delete a host from the Satellite server.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Host identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: host-power\n      path: /api/v2/hosts/{id}/power\n      description: Manage host power state.\n      operations:\n      - name: host-power-action\n\
  \        method: PUT\n        description: Execute a power action on a host.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Host identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            power_action: '{{tools.power_action}}'\n    - name: content-views\n      path: /katello/api/v2/content_views\n      description: Manage content views.\n      operations:\n      - name: list-content-views\n        method: GET\n        description: List all content views in an organization.\n        inputParameters:\n        - name: organization_id\n          in: query\n          type: integer\n          required: true\n          description: Organization ID.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description:\
  \ Search query.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-content-view\n        method: POST\n        description: Create a new content view.\n        inputParameters:\n        - name: organization_id\n          in: query\n          type: integer\n          required: true\n          description: Organization ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n    - name: content-view-details\n      path: /katello/api/v2/content_views/{id}\n      description: Manage individual content view.\n      operations:\n      - name: show-content-view\n        method: GET\n        description: Retrieve details for a content view.\n        inputParameters:\n        - name: id\n\
  \          in: path\n          type: integer\n          required: true\n          description: Content view ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-content-view\n        method: PUT\n        description: Update a content view.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Content view ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-content-view\n        method: DELETE\n        description: Delete a content view.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Content view ID.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-view-publish\n      path: /katello/api/v2/content_views/{id}/publish\n      description: Publish a content view version.\n      operations:\n      - name: publish-content-view\n        method: POST\n        description: Publish a new version of a content view.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Content view ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-view-promote\n      path: /katello/api/v2/content_view_versions/{id}/promote\n      description: Promote a content view version.\n      operations:\n      - name: promote-content-view-version\n        method: POST\n        description: Promote a content view version to an environment.\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Content view version ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            environment_id: '{{tools.environment_id}}'\n    - name: subscriptions\n      path: /katello/api/v2/organizations/{organization_id}/subscriptions\n      description: Manage subscriptions.\n      operations:\n      - name: list-subscriptions\n        method: GET\n        description: List subscriptions for an organization.\n        inputParameters:\n        - name: organization_id\n          in: path\n          type: integer\n          required: true\n          description: Organization ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upload-subscription-manifest\n\
  \        method: POST\n        description: Upload a subscription manifest.\n        inputParameters:\n        - name: organization_id\n          in: path\n          type: integer\n          required: true\n          description: Organization ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-subscription-manifest\n        method: POST\n        description: Delete a subscription manifest.\n        inputParameters:\n        - name: organization_id\n          in: path\n          type: integer\n          required: true\n          description: Organization ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: refresh-subscription-manifest\n        method: PUT\n        description: Refresh a subscription manifest.\n        inputParameters:\n        - name: organization_id\n          in: path\n      \
  \    type: integer\n          required: true\n          description: Organization ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lifecycle-environments\n      path: /katello/api/v2/organizations/{organization_id}/environments\n      description: Manage lifecycle environments.\n      operations:\n      - name: list-lifecycle-environments\n        method: GET\n        description: List lifecycle environments for an organization.\n        inputParameters:\n        - name: organization_id\n          in: path\n          type: integer\n          required: true\n          description: Organization ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-lifecycle-environment\n        method: POST\n        description: Create a new lifecycle environment.\n        inputParameters:\n        - name: organization_id\n\
  \          in: path\n          type: integer\n          required: true\n          description: Organization ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            prior_id: '{{tools.prior_id}}'\n    - name: organizations\n      path: /api/v2/organizations\n      description: Manage organizations.\n      operations:\n      - name: list-organizations\n        method: GET\n        description: List all organizations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: show-organization\n        method: GET\n        description: Show details for a specific organization.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Organization ID.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: satellite-lifecycle-api\n    description: Unified REST API for Red Hat Satellite systems lifecycle management.\n    resources:\n    - path: /v1/hosts\n      name: hosts\n      description: Host management endpoints.\n      operations:\n      - method: GET\n        name: list-hosts\n        description: List all managed hosts.\n        call: satellite-api.list-hosts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-host\n        description: Register a new host.\n        call: satellite-api.create-host\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hosts/{id}\n      name: host-details\n      description: Individual host management.\n      operations:\n      - method: GET\n        name: show-host\n\
  \        description: Get host details.\n        call: satellite-api.show-host\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-host\n        description: Update host attributes.\n        call: satellite-api.update-host\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-host\n        description: Delete a host.\n        call: satellite-api.delete-host\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content-views\n      name: content-views\n      description: Content view management.\n      operations:\n      - method: GET\n        name: list-content-views\n        description: List all content views.\n        call: satellite-api.list-content-views\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: POST\n        name: create-content-view\n        description: Create a new content view.\n        call: satellite-api.create-content-view\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content-views/{id}\n      name: content-view-details\n      description: Individual content view management.\n      operations:\n      - method: GET\n        name: show-content-view\n        description: Get content view details.\n        call: satellite-api.show-content-view\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-content-view\n        description: Update a content view.\n        call: satellite-api.update-content-view\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-content-view\n        description:\
  \ Delete a content view.\n        call: satellite-api.delete-content-view\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lifecycle-environments\n      name: lifecycle-environments\n      description: Lifecycle environment management.\n      operations:\n      - method: GET\n        name: list-lifecycle-environments\n        description: List lifecycle environments.\n        call: satellite-api.list-lifecycle-environments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-lifecycle-environment\n        description: Create a lifecycle environment.\n        call: satellite-api.create-lifecycle-environment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscriptions\n      name: subscriptions\n      description: Subscription management.\n      operations:\n      - method: GET\n        name: list-subscriptions\n\
  \        description: List subscriptions.\n        call: satellite-api.list-subscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations\n      name: organizations\n      description: Organization management.\n      operations:\n      - method: GET\n        name: list-organizations\n        description: List organizations.\n        call: satellite-api.list-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: satellite-lifecycle-mcp\n    transport: http\n    description: MCP server for AI-assisted Red Hat Satellite systems lifecycle management.\n    tools:\n    - name: list-hosts\n      description: List all hosts registered with Satellite.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: satellite-api.list-hosts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: show-host\n      description:\
  \ Get details for a specific host.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: satellite-api.show-host\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-host\n      description: Register a new host with Satellite.\n      hints:\n        readOnly: false\n      call: satellite-api.create-host\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-host\n      description: Update host attributes.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: satellite-api.update-host\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-host\n      description: Delete a host from Satellite.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: satellite-api.delete-host\n      with:\n        id: tools.id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: host-power-action\n      description: Execute a power action on a host (start, stop, reboot).\n      hints:\n        readOnly: false\n        destructive: true\n      call: satellite-api.host-power-action\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-content-views\n      description: List content views in an organization.\n      hints:\n        readOnly: true\n      call: satellite-api.list-content-views\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-content-view\n      description: Create a new content view.\n      hints:\n        readOnly: false\n      call: satellite-api.create-content-view\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: show-content-view\n      description: Get details for a content view.\n      hints:\n        readOnly: true\n        idempotent: true\n      call:\
  \ satellite-api.show-content-view\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-content-view\n      description: Update a content view.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: satellite-api.update-content-view\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-content-view\n      description: Delete a content view.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: satellite-api.delete-content-view\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-content-view\n      description: Publish a new version of a content view.\n      hints:\n        readOnly: false\n      call: satellite-api.publish-content-view\n      with:\n        id: tools.id\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: promote-content-view-version\n      description: Promote a content view version to a lifecycle environment.\n      hints:\n        readOnly: false\n      call: satellite-api.promote-content-view-version\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-subscriptions\n      description: List subscriptions for an organization.\n      hints:\n        readOnly: true\n      call: satellite-api.list-subscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-lifecycle-environments\n      description: List lifecycle environments for an organization.\n      hints:\n        readOnly: true\n      call: satellite-api.list-lifecycle-environments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-lifecycle-environment\n      description: Create a new lifecycle environment.\n      hints:\n        readOnly: false\n\
  \      call: satellite-api.create-lifecycle-environment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-organizations\n      description: List all organizations.\n      hints:\n        readOnly: true\n      call: satellite-api.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: show-organization\n      description: Show details for a specific organization.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: satellite-api.show-organization\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
