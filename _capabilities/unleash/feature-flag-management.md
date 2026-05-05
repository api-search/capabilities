---
categories: []
consumed_apis:
- unleash-admin
description: Workflow capability for managing the complete lifecycle of feature flags using Unleash. Covers creating and configuring flags, toggling environments, managing strategies and segments, tracking events, and administering projects. Used by engineering teams, product managers, and release engineers to safely ship and control features.
layout: capability
name: Unleash Feature Flag Management
operations:
- description: List all projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a new project
  method: POST
  name: create-project
  path: /v1/projects
- description: List all feature flags in a project
  method: GET
  name: list-flags
  path: /v1/projects/{projectId}/flags
- description: Create a new feature flag
  method: POST
  name: create-flag
  path: /v1/projects/{projectId}/flags
- description: Get feature flag details
  method: GET
  name: get-flag
  path: /v1/projects/{projectId}/flags/{flagName}
- description: Enable a feature flag in the specified environment
  method: POST
  name: enable-flag
  path: /v1/projects/{projectId}/flags/{flagName}/environments/{environment}/enable
- description: Disable a feature flag in the specified environment
  method: POST
  name: disable-flag
  path: /v1/projects/{projectId}/flags/{flagName}/environments/{environment}/disable
- description: List all environments
  method: GET
  name: list-environments
  path: /v1/environments
- description: List all segments
  method: GET
  name: list-segments
  path: /v1/segments
- description: Create a targeting segment
  method: POST
  name: create-segment
  path: /v1/segments
- description: List recent events
  method: GET
  name: list-events
  path: /v1/events
personas: []
provider_name: Unleash
provider_slug: unleash
search_terms:
- list all segments
- enable feature flag
- list recent events
- create feature flag
- enable flag
- release management
- create flag
- get flag
- segment management for targeting groups
- list flags
- list feature flags
- open source
- list events
- event log for audit and observability
- feature management
- create segment
- unleash
- list all feature flags in a project
- list all unleash projects
- list all configured environments in unleash
- enable a feature flag in the specified environment
- enable a flag in an environment
- create a new project
- list recent audit events for a project or globally
- feature flags
- list segments
- feature flag management within a project
- environment management
- developer tools
- single flag operations
- list projects
- create a targeting segment
- list all environments
- disable feature flag
- create a targeting segment for feature flag strategies
- create a new unleash project for organizing feature flags
- list all projects
- disable a flag in an environment
- disable flag
- list environments
- project management
- get details of a feature flag including environments and strategies
- progressive delivery
- create a new feature flag in a project
- a/b testing
- list all targeting segments
- disable a feature flag in the specified environment
- create a new feature flag
- get feature flag
- create project
- get feature flag details
slug: feature-flag-management
source_filename: feature-flag-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Unleash Feature Flag Management\n  description: >-\n    Workflow capability for managing the complete lifecycle of feature flags using Unleash.\n    Covers creating and configuring flags, toggling environments, managing strategies and\n    segments, tracking events, and administering projects. Used by engineering teams,\n    product managers, and release engineers to safely ship and control features.\n  tags:\n    - Unleash\n    - Feature Flags\n    - Feature Management\n    - Release Management\n    - Progressive Delivery\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNLEASH_API_TOKEN: UNLEASH_API_TOKEN\n      UNLEASH_BASE_URL: UNLEASH_BASE_URL\n\ncapability:\n  consumes:\n    - import: unleash-admin\n      location: ./shared/unleash-admin.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: unleash-feature-management-api\n      description: Unified REST\
  \ API for Unleash feature flag lifecycle management.\n      resources:\n        - path: /v1/projects\n          name: projects\n          description: Project management\n          operations:\n            - method: GET\n              name: list-projects\n              description: List all projects\n              call: \"unleash-admin.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: Create a new project\n              call: \"unleash-admin.create-project\"\n              with:\n                id: \"rest.id\"\n                name: \"rest.name\"\n                description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/flags\n          name: flags\n          description: Feature flag management within a project\n\
  \          operations:\n            - method: GET\n              name: list-flags\n              description: List all feature flags in a project\n              call: \"unleash-admin.list-features\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-flag\n              description: Create a new feature flag\n              call: \"unleash-admin.create-feature\"\n              with:\n                projectId: \"rest.projectId\"\n                name: \"rest.name\"\n                description: \"rest.description\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/flags/{flagName}\n          name: flag\n          description: Single flag operations\n          operations:\n            - method:\
  \ GET\n              name: get-flag\n              description: Get feature flag details\n              call: \"unleash-admin.get-feature\"\n              with:\n                projectId: \"rest.projectId\"\n                featureName: \"rest.flagName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/flags/{flagName}/environments/{environment}/enable\n          name: flag-enable\n          description: Enable a flag in an environment\n          operations:\n            - method: POST\n              name: enable-flag\n              description: Enable a feature flag in the specified environment\n              call: \"unleash-admin.enable-feature\"\n              with:\n                projectId: \"rest.projectId\"\n                featureName: \"rest.flagName\"\n                environment: \"rest.environment\"\n              outputParameters:\n                - type: object\n             \
  \     mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}/flags/{flagName}/environments/{environment}/disable\n          name: flag-disable\n          description: Disable a flag in an environment\n          operations:\n            - method: POST\n              name: disable-flag\n              description: Disable a feature flag in the specified environment\n              call: \"unleash-admin.disable-feature\"\n              with:\n                projectId: \"rest.projectId\"\n                featureName: \"rest.flagName\"\n                environment: \"rest.environment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/environments\n          name: environments\n          description: Environment management\n          operations:\n            - method: GET\n              name: list-environments\n              description: List all environments\n              call: \"unleash-admin.list-environments\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/segments\n          name: segments\n          description: Segment management for targeting groups\n          operations:\n            - method: GET\n              name: list-segments\n              description: List all segments\n              call: \"unleash-admin.list-segments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-segment\n              description: Create a targeting segment\n              call: \"unleash-admin.create-segment\"\n              with:\n                name: \"rest.name\"\n                description: \"rest.description\"\n                constraints: \"rest.constraints\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events\n          name: events\n    \
  \      description: Event log for audit and observability\n          operations:\n            - method: GET\n              name: list-events\n              description: List recent events\n              call: \"unleash-admin.list-events\"\n              with:\n                project: \"rest.project\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: unleash-feature-management-mcp\n      transport: http\n      description: MCP server for AI-assisted feature flag management with Unleash.\n      tools:\n        - name: list-projects\n          description: List all Unleash projects\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unleash-admin.list-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-project\n          description:\
  \ Create a new Unleash project for organizing feature flags\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"unleash-admin.create-project\"\n          with:\n            id: \"tools.id\"\n            name: \"tools.name\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-feature-flags\n          description: List all feature flags in a project\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unleash-admin.list-features\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-feature-flag\n          description: Create a new feature flag in a project\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"unleash-admin.create-feature\"\
  \n          with:\n            projectId: \"tools.projectId\"\n            name: \"tools.name\"\n            description: \"tools.description\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-feature-flag\n          description: Get details of a feature flag including environments and strategies\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unleash-admin.get-feature\"\n          with:\n            projectId: \"tools.projectId\"\n            featureName: \"tools.featureName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enable-feature-flag\n          description: Enable a feature flag in the specified environment\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"unleash-admin.enable-feature\"\n          with:\n\
  \            projectId: \"tools.projectId\"\n            featureName: \"tools.featureName\"\n            environment: \"tools.environment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: disable-feature-flag\n          description: Disable a feature flag in the specified environment\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"unleash-admin.disable-feature\"\n          with:\n            projectId: \"tools.projectId\"\n            featureName: \"tools.featureName\"\n            environment: \"tools.environment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-environments\n          description: List all configured environments in Unleash\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unleash-admin.list-environments\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-segments\n          description: List all targeting segments\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unleash-admin.list-segments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-segment\n          description: Create a targeting segment for feature flag strategies\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"unleash-admin.create-segment\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n            constraints: \"tools.constraints\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-events\n          description: List recent audit events for a project or globally\n          hints:\n            readOnly: true\n            openWorld:\
  \ false\n          call: \"unleash-admin.list-events\"\n          with:\n            project: \"tools.project\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unleash/refs/heads/main/capabilities/feature-flag-management.yaml
tags:
- Unleash
- Feature Flags
- Feature Management
- Release Management
- Progressive Delivery
tools:
- description: List all Unleash projects
  hints:
    openWorld: false
    readOnly: true
  name: list-projects
- description: Create a new Unleash project for organizing feature flags
  hints:
    destructive: false
    readOnly: false
  name: create-project
- description: List all feature flags in a project
  hints:
    openWorld: false
    readOnly: true
  name: list-feature-flags
- description: Create a new feature flag in a project
  hints:
    destructive: false
    readOnly: false
  name: create-feature-flag
- description: Get details of a feature flag including environments and strategies
  hints:
    openWorld: false
    readOnly: true
  name: get-feature-flag
- description: Enable a feature flag in the specified environment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: enable-feature-flag
- description: Disable a feature flag in the specified environment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: disable-feature-flag
- description: List all configured environments in Unleash
  hints:
    openWorld: false
    readOnly: true
  name: list-environments
- description: List all targeting segments
  hints:
    openWorld: false
    readOnly: true
  name: list-segments
- description: Create a targeting segment for feature flag strategies
  hints:
    destructive: false
    readOnly: false
  name: create-segment
- description: List recent audit events for a project or globally
  hints:
    openWorld: false
    readOnly: true
  name: list-events
---
