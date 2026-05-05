---
api_specs:
- filename: split-admin-api-openapi.yml
  format: yaml
  label: split-admin
  slug: split-admin
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/split/refs/heads/main/openapi/split-admin-api-openapi.yml
- filename: split-feature-flag-api-openapi.yml
  format: yaml
  label: split-flags
  slug: split-flags
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/split/refs/heads/main/openapi/split-feature-flag-api-openapi.yml
- filename: split-evaluator-api-openapi.yml
  format: yaml
  label: split-evaluator
  slug: split-evaluator
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/split/refs/heads/main/openapi/split-evaluator-api-openapi.yml
categories: []
consumed_apis:
- split-admin
- split-flags
- split-evaluator
description: 'Unified capability for managing Split feature flags across the full lifecycle: creating and configuring flags, managing targeting rules and segments, controlling environments, administering users and groups, and evaluating flag treatments. Combines the Split Admin, Feature Flag, and Evaluator APIs into a single workflow for feature release engineers and platform administrators.'
layout: capability
name: Split Feature Flag Management
operations:
- description: List all accessible Split workspaces.
  method: GET
  name: list-workspaces
  path: /v1/workspaces
- description: List all environments in a workspace.
  method: GET
  name: list-environments
  path: /v1/environments
- description: List all feature flags in a workspace.
  method: GET
  name: list-feature-flags
  path: /v1/feature-flags
- description: Get a feature flag's targeting definition in an environment.
  method: GET
  name: get-feature-flag-definition
  path: /v1/feature-flag-definitions
- description: List all segments in a workspace.
  method: GET
  name: list-segments
  path: /v1/segments
- description: Evaluate a feature flag treatment for a customer key.
  method: GET
  name: get-treatment
  path: /v1/treatments
- description: List all users in the account.
  method: GET
  name: list-users
  path: /v1/users
- description: List change requests for feature flag modifications.
  method: GET
  name: list-change-requests
  path: /v1/change-requests
personas: []
provider_name: Split
provider_slug: split
search_terms:
- evaluate a feature flag treatment for a customer key.
- list pending change requests for feature flag modifications requiring approval.
- rollouts
- list users
- restore feature flag
- get treatments
- list all segments in a workspace.
- list all users in the account.
- feature flags within a workspace.
- list feature flags
- split workspaces (projects).
- account users.
- feature management
- get treatment
- experimentation
- evaluate multiple feature flags for a customer key in a single request.
- list all split workspaces accessible to the admin api key.
- list all accessible split workspaces.
- restore a previously killed feature flag to normal targeting rule evaluation.
- kill feature flag
- feature flags
- list segments
- administration
- get a feature flag's targeting definition in an environment.
- change request approval workflows.
- list all deployment environments within a split workspace.
- get feature flag definition
- list change requests for feature flag modifications.
- targeting segments within a workspace.
- list environments
- track event
- list workspaces
- list all feature flags in a workspace.
- kill a feature flag in an environment, forcing all traffic to receive the default treatment. use as an emergency shut-off.
- list all users in the split account.
- list all environments in a workspace.
- environments within a split workspace.
- retrieve the full targeting definition of a feature flag in a specific environment, including treatments and rules.
- list all targeting segments in a split workspace.
- evaluate a feature flag for a customer key and return the treatment value.
- feature flag treatment evaluations.
- list change requests
- feature flag targeting definitions per environment.
- record a custom event for experimentation and metrics measurement.
- sdks
- list all feature flags in a split workspace, optionally filtered by tag.
slug: feature-flag-management
source_filename: feature-flag-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Split Feature Flag Management\"\n  description: >-\n    Unified capability for managing Split feature flags across the full lifecycle:\n    creating and configuring flags, managing targeting rules and segments, controlling\n    environments, administering users and groups, and evaluating flag treatments.\n    Combines the Split Admin, Feature Flag, and Evaluator APIs into a single\n    workflow for feature release engineers and platform administrators.\n  tags:\n    - Feature Flags\n    - Feature Management\n    - Experimentation\n    - Rollouts\n    - Administration\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPLIT_ADMIN_API_KEY: SPLIT_ADMIN_API_KEY\n      SPLIT_EVALUATOR_HOST: SPLIT_EVALUATOR_HOST\n\ncapability:\n  consumes:\n    - import: split-admin\n      location: ./shared/split-admin-api.yaml\n    - import: split-flags\n      location: ./shared/split-feature-flag-api.yaml\n\
  \    - import: split-evaluator\n      location: ./shared/split-evaluator-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: split-feature-flag-management-api\n      description: \"Unified REST API for Split feature flag lifecycle management.\"\n      resources:\n        - path: /v1/workspaces\n          name: workspaces\n          description: \"Split workspaces (projects).\"\n          operations:\n            - method: GET\n              name: list-workspaces\n              description: \"List all accessible Split workspaces.\"\n              call: \"split-admin.list-workspaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/environments\n          name: environments\n          description: \"Environments within a Split workspace.\"\n          operations:\n            - method: GET\n              name: list-environments\n              description: \"List all environments in a workspace.\"\
  \n              call: \"split-admin.list-environments\"\n              with:\n                workspaceId: \"rest.workspaceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/feature-flags\n          name: feature-flags\n          description: \"Feature flags within a workspace.\"\n          operations:\n            - method: GET\n              name: list-feature-flags\n              description: \"List all feature flags in a workspace.\"\n              call: \"split-flags.list-feature-flags\"\n              with:\n                workspaceId: \"rest.workspaceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/feature-flag-definitions\n          name: feature-flag-definitions\n          description: \"Feature flag targeting definitions per environment.\"\n          operations:\n            - method: GET\n              name: get-feature-flag-definition\n\
  \              description: \"Get a feature flag's targeting definition in an environment.\"\n              call: \"split-flags.get-feature-flag-definition\"\n              with:\n                workspaceId: \"rest.workspaceId\"\n                featureFlagName: \"rest.featureFlagName\"\n                environmentId: \"rest.environmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/segments\n          name: segments\n          description: \"Targeting segments within a workspace.\"\n          operations:\n            - method: GET\n              name: list-segments\n              description: \"List all segments in a workspace.\"\n              call: \"split-admin.list-segments\"\n              with:\n                workspaceId: \"rest.workspaceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/treatments\n          name: treatments\n\
  \          description: \"Feature flag treatment evaluations.\"\n          operations:\n            - method: GET\n              name: get-treatment\n              description: \"Evaluate a feature flag treatment for a customer key.\"\n              call: \"split-evaluator.get-treatment\"\n              with:\n                key: \"rest.key\"\n                split-name: \"rest.flagName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: \"Account users.\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all users in the account.\"\n              call: \"split-admin.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/change-requests\n          name: change-requests\n          description: \"Change request approval\
  \ workflows.\"\n          operations:\n            - method: GET\n              name: list-change-requests\n              description: \"List change requests for feature flag modifications.\"\n              call: \"split-admin.list-change-requests\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: split-feature-flag-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Split feature flag lifecycle management.\"\n      tools:\n        - name: list-workspaces\n          description: \"List all Split workspaces accessible to the Admin API key.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"split-admin.list-workspaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-environments\n          description: \"List all deployment environments within\
  \ a Split workspace.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"split-admin.list-environments\"\n          with:\n            workspaceId: \"tools.workspaceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-feature-flags\n          description: \"List all feature flags in a Split workspace, optionally filtered by tag.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"split-flags.list-feature-flags\"\n          with:\n            workspaceId: \"tools.workspaceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-feature-flag-definition\n          description: \"Retrieve the full targeting definition of a feature flag in a specific environment, including treatments and rules.\"\n          hints:\n            readOnly: true\n            idempotent: true\n        \
  \  call: \"split-flags.get-feature-flag-definition\"\n          with:\n            workspaceId: \"tools.workspaceId\"\n            featureFlagName: \"tools.featureFlagName\"\n            environmentId: \"tools.environmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: kill-feature-flag\n          description: \"Kill a feature flag in an environment, forcing all traffic to receive the default treatment. Use as an emergency shut-off.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"split-flags.kill-feature-flag\"\n          with:\n            workspaceId: \"tools.workspaceId\"\n            featureFlagName: \"tools.featureFlagName\"\n            environmentId: \"tools.environmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: restore-feature-flag\n          description: \"Restore a previously\
  \ killed feature flag to normal targeting rule evaluation.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"split-flags.restore-feature-flag\"\n          with:\n            workspaceId: \"tools.workspaceId\"\n            featureFlagName: \"tools.featureFlagName\"\n            environmentId: \"tools.environmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-segments\n          description: \"List all targeting segments in a Split workspace.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"split-admin.list-segments\"\n          with:\n            workspaceId: \"tools.workspaceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-treatment\n          description: \"Evaluate a feature flag for a customer key and return the treatment value.\"\
  \n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"split-evaluator.get-treatment\"\n          with:\n            key: \"tools.key\"\n            split-name: \"tools.flagName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-treatments\n          description: \"Evaluate multiple feature flags for a customer key in a single request.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"split-evaluator.get-treatments\"\n          with:\n            key: \"tools.key\"\n            split-names: \"tools.flagNames\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: track-event\n          description: \"Record a custom event for experimentation and metrics measurement.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"split-evaluator.track-event\"\
  \n          with:\n            key: \"tools.key\"\n            traffic-type: \"tools.trafficType\"\n            event-type: \"tools.eventType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-users\n          description: \"List all users in the Split account.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"split-admin.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-change-requests\n          description: \"List pending change requests for feature flag modifications requiring approval.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"split-admin.list-change-requests\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/split/refs/heads/main/capabilities/feature-flag-management.yaml
tags:
- Feature Flags
- Feature Management
- Experimentation
- Rollouts
- Administration
tools:
- description: List all Split workspaces accessible to the Admin API key.
  hints:
    idempotent: true
    readOnly: true
  name: list-workspaces
- description: List all deployment environments within a Split workspace.
  hints:
    idempotent: true
    readOnly: true
  name: list-environments
- description: List all feature flags in a Split workspace, optionally filtered by tag.
  hints:
    idempotent: true
    readOnly: true
  name: list-feature-flags
- description: Retrieve the full targeting definition of a feature flag in a specific environment, including treatments and rules.
  hints:
    idempotent: true
    readOnly: true
  name: get-feature-flag-definition
- description: Kill a feature flag in an environment, forcing all traffic to receive the default treatment. Use as an emergency shut-off.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: kill-feature-flag
- description: Restore a previously killed feature flag to normal targeting rule evaluation.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: restore-feature-flag
- description: List all targeting segments in a Split workspace.
  hints:
    idempotent: true
    readOnly: true
  name: list-segments
- description: Evaluate a feature flag for a customer key and return the treatment value.
  hints:
    idempotent: true
    readOnly: true
  name: get-treatment
- description: Evaluate multiple feature flags for a customer key in a single request.
  hints:
    idempotent: true
    readOnly: true
  name: get-treatments
- description: Record a custom event for experimentation and metrics measurement.
  hints:
    idempotent: false
    readOnly: false
  name: track-event
- description: List all users in the Split account.
  hints:
    idempotent: true
    readOnly: true
  name: list-users
- description: List pending change requests for feature flag modifications requiring approval.
  hints:
    idempotent: true
    readOnly: true
  name: list-change-requests
---
