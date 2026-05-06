---
categories: []
consumed_apis: []
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
- retrieve the full targeting definition of a feature flag in a specific environment, including treatments and rules.
- list all users in the account.
- restore feature flag
- list all feature flags in a split workspace, optionally filtered by tag.
- restore a previously killed feature flag to normal targeting rule evaluation.
- list environments
- feature flag treatment evaluations.
- split workspaces (projects).
- feature management
- sdks
- experimentation
- kill a feature flag in an environment, forcing all traffic to receive the default treatment. use as an emergency shut-off.
- list feature flags
- list segments
- rollouts
- list pending change requests for feature flag modifications requiring approval.
- environments within a split workspace.
- list all targeting segments in a split workspace.
- evaluate multiple feature flags for a customer key in a single request.
- list all accessible split workspaces.
- list all users in the split account.
- list all deployment environments within a split workspace.
- list change requests
- list change requests for feature flag modifications.
- list all feature flags in a workspace.
- get a feature flag's targeting definition in an environment.
- list all environments in a workspace.
- record a custom event for experimentation and metrics measurement.
- targeting segments within a workspace.
- kill feature flag
- change request approval workflows.
- list workspaces
- administration
- get treatment
- feature flags
- get feature flag definition
- evaluate a feature flag treatment for a customer key.
- feature flag targeting definitions per environment.
- list users
- feature flags within a workspace.
- evaluate a feature flag for a customer key and return the treatment value.
- track event
- account users.
- list all segments in a workspace.
- list all split workspaces accessible to the admin api key.
- get treatments
slug: feature-flag-management
source_filename: feature-flag-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Split Feature Flag Management\n  description: 'Unified capability for managing Split feature flags across the full lifecycle: creating and configuring flags,\n    managing targeting rules and segments, controlling environments, administering users and groups, and evaluating flag treatments.\n    Combines the Split Admin, Feature Flag, and Evaluator APIs into a single workflow for feature release engineers and platform\n    administrators.'\n  tags:\n  - Feature Flags\n  - Feature Management\n  - Experimentation\n  - Rollouts\n  - Administration\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPLIT_ADMIN_API_KEY: SPLIT_ADMIN_API_KEY\n    SPLIT_EVALUATOR_HOST: SPLIT_EVALUATOR_HOST\ncapability:\n  consumes:\n  - type: http\n    namespace: split-admin\n    baseUri: https://api.split.io/internal/api/v2\n    description: Split Admin API for managing workspaces, environments, and users.\n    authentication:\n\
  \      type: bearer\n      token: '{{SPLIT_ADMIN_API_KEY}}'\n    resources:\n    - name: workspaces\n      path: /workspaces\n      description: Manage workspaces (projects).\n      operations:\n      - name: list-workspaces\n        method: GET\n        description: Retrieve all workspaces accessible to the authenticated Admin API key.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Number of results to skip.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments\n      path: /environments/ws/{workspaceId}\n      description: Manage environments within a workspace.\n      operations:\n      - name: list-environments\n        method: GET\n\
  \        description: Retrieve all environments within the specified workspace.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workspace.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-environment\n        method: POST\n        description: Create a new environment within the specified workspace.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workspace.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            production: '{{tools.production}}'\n    - name: users\n\
  \      path: /users\n      description: Manage users within the account.\n      operations:\n      - name: list-users\n        method: GET\n        description: Retrieve all users the Admin API key has access to.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Number of results to skip.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: 'Filter by status: ACTIVE, DEACTIVATED, PENDING.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invite-user\n        method: POST\n        description: Invite a new user to the account.\n        inputParameters: []\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n    - name: groups\n      path: /groups\n      description: Manage groups for organizing users.\n      operations:\n      - name: list-groups\n        method: GET\n        description: Retrieve all active groups in the account.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create a new group.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n    - name: segments\n      path: /segments/ws/{workspaceId}\n\
  \      description: Manage segments within a workspace.\n      operations:\n      - name: list-segments\n        method: GET\n        description: Retrieve all segments in the specified workspace.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workspace.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: change-requests\n      path: /changeRequests\n      description: Manage change request approval workflows.\n      operations:\n      - name: list-change-requests\n        method: GET\n        description: Retrieve all change requests.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: 'Filter by status: OPEN, APPROVED, DECLINED, APPLIED, CANCELLED.'\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: split-flags\n    baseUri: https://api.split.io/internal/api/v2\n    description: Split Feature Flag API for managing feature flags and definitions.\n    authentication:\n      type: bearer\n      token: '{{SPLIT_ADMIN_API_KEY}}'\n    resources:\n    - name: feature-flags\n      path: /splits/ws/{workspaceId}\n      description: Manage feature flags within a workspace.\n      operations:\n      - name: list-feature-flags\n        method: GET\n        description: Retrieve all feature flags within the specified workspace.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workspace.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results.\n        -\
  \ name: offset\n          in: query\n          type: integer\n          required: false\n          description: Number of results to skip.\n        - name: tags\n          in: query\n          type: string\n          required: false\n          description: Filter by tag names (comma-separated).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-feature-flag\n        method: POST\n        description: Create a new feature flag within the specified workspace.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workspace.\n        - name: trafficTypeId\n          in: path\n          type: string\n          required: true\n          description: The traffic type identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n    - name: feature-flag-definitions\n      path: /splits/ws/{workspaceId}/{featureFlagName}/environments/{environmentId}\n      description: Manage feature flag definitions in specific environments.\n      operations:\n      - name: get-feature-flag-definition\n        method: GET\n        description: Retrieve the full definition of a feature flag in a specific environment.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workspace.\n        - name: featureFlagName\n          in: path\n          type: string\n          required: true\n          description: The name of the feature flag.\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n \
  \         description: The unique identifier or name of the environment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: kill-feature-flag\n        method: PUT\n        description: Kill a feature flag in the specified environment, forcing the default treatment.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workspace.\n        - name: featureFlagName\n          in: path\n          type: string\n          required: true\n          description: The name of the feature flag.\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier or name of the environment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: restore-feature-flag\n        method: PUT\n        description: Restore a previously killed feature flag in the specified environment.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workspace.\n        - name: featureFlagName\n          in: path\n          type: string\n          required: true\n          description: The name of the feature flag.\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier or name of the environment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: split-evaluator\n    baseUri: http://{{SPLIT_EVALUATOR_HOST}}:7548\n    description: Split Evaluator service for feature flag treatment evaluation.\n    resources:\n\
  \    - name: health\n      path: /admin\n      description: Service health and admin endpoints.\n      operations:\n      - name: health-check\n        method: GET\n        description: Check that the Split Evaluator is connected and ready.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: evaluation\n      path: /client\n      description: Feature flag evaluation endpoints.\n      operations:\n      - name: get-treatment\n        method: GET\n        description: Evaluate a single feature flag for the given key.\n        inputParameters:\n        - name: key\n          in: query\n          type: string\n          required: true\n          description: The customer key to evaluate against.\n        - name: split-name\n          in: query\n          type: string\n          required: true\n          description: The feature flag name to evaluate.\n        - name: attributes\n\
  \          in: query\n          type: string\n          required: false\n          description: JSON string of attributes for targeting.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-treatments\n        method: GET\n        description: Evaluate multiple feature flags for the given key.\n        inputParameters:\n        - name: key\n          in: query\n          type: string\n          required: true\n          description: The customer key.\n        - name: split-names\n          in: query\n          type: string\n          required: true\n          description: Comma-separated feature flag names.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: track-event\n        method: GET\n        description: Record a custom event for a given key and event type.\n        inputParameters:\n        - name:\
  \ key\n          in: query\n          type: string\n          required: true\n          description: The customer key.\n        - name: traffic-type\n          in: query\n          type: string\n          required: true\n          description: The traffic type for the event.\n        - name: event-type\n          in: query\n          type: string\n          required: true\n          description: The type of event (e.g., purchase, click).\n        - name: value\n          in: query\n          type: number\n          required: false\n          description: Optional numeric value.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: split-feature-flag-management-api\n    description: Unified REST API for Split feature flag lifecycle management.\n    resources:\n    - path: /v1/workspaces\n      name: workspaces\n      description: Split workspaces (projects).\n\
  \      operations:\n      - method: GET\n        name: list-workspaces\n        description: List all accessible Split workspaces.\n        call: split-admin.list-workspaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/environments\n      name: environments\n      description: Environments within a Split workspace.\n      operations:\n      - method: GET\n        name: list-environments\n        description: List all environments in a workspace.\n        call: split-admin.list-environments\n        with:\n          workspaceId: rest.workspaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/feature-flags\n      name: feature-flags\n      description: Feature flags within a workspace.\n      operations:\n      - method: GET\n        name: list-feature-flags\n        description: List all feature flags in a workspace.\n        call: split-flags.list-feature-flags\n        with:\n          workspaceId:\
  \ rest.workspaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/feature-flag-definitions\n      name: feature-flag-definitions\n      description: Feature flag targeting definitions per environment.\n      operations:\n      - method: GET\n        name: get-feature-flag-definition\n        description: Get a feature flag's targeting definition in an environment.\n        call: split-flags.get-feature-flag-definition\n        with:\n          workspaceId: rest.workspaceId\n          featureFlagName: rest.featureFlagName\n          environmentId: rest.environmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/segments\n      name: segments\n      description: Targeting segments within a workspace.\n      operations:\n      - method: GET\n        name: list-segments\n        description: List all segments in a workspace.\n        call: split-admin.list-segments\n        with:\n          workspaceId:\
  \ rest.workspaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/treatments\n      name: treatments\n      description: Feature flag treatment evaluations.\n      operations:\n      - method: GET\n        name: get-treatment\n        description: Evaluate a feature flag treatment for a customer key.\n        call: split-evaluator.get-treatment\n        with:\n          key: rest.key\n          split-name: rest.flagName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: Account users.\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users in the account.\n        call: split-admin.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/change-requests\n      name: change-requests\n      description: Change request approval workflows.\n      operations:\n      - method:\
  \ GET\n        name: list-change-requests\n        description: List change requests for feature flag modifications.\n        call: split-admin.list-change-requests\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: split-feature-flag-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Split feature flag lifecycle management.\n    tools:\n    - name: list-workspaces\n      description: List all Split workspaces accessible to the Admin API key.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: split-admin.list-workspaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-environments\n      description: List all deployment environments within a Split workspace.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: split-admin.list-environments\n      with:\n        workspaceId: tools.workspaceId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-feature-flags\n      description: List all feature flags in a Split workspace, optionally filtered by tag.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: split-flags.list-feature-flags\n      with:\n        workspaceId: tools.workspaceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-feature-flag-definition\n      description: Retrieve the full targeting definition of a feature flag in a specific environment, including treatments\n        and rules.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: split-flags.get-feature-flag-definition\n      with:\n        workspaceId: tools.workspaceId\n        featureFlagName: tools.featureFlagName\n        environmentId: tools.environmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: kill-feature-flag\n      description: Kill a feature flag in an environment,\
  \ forcing all traffic to receive the default treatment. Use as an\n        emergency shut-off.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: split-flags.kill-feature-flag\n      with:\n        workspaceId: tools.workspaceId\n        featureFlagName: tools.featureFlagName\n        environmentId: tools.environmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restore-feature-flag\n      description: Restore a previously killed feature flag to normal targeting rule evaluation.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: split-flags.restore-feature-flag\n      with:\n        workspaceId: tools.workspaceId\n        featureFlagName: tools.featureFlagName\n        environmentId: tools.environmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-segments\n      description: List all targeting segments\
  \ in a Split workspace.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: split-admin.list-segments\n      with:\n        workspaceId: tools.workspaceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-treatment\n      description: Evaluate a feature flag for a customer key and return the treatment value.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: split-evaluator.get-treatment\n      with:\n        key: tools.key\n        split-name: tools.flagName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-treatments\n      description: Evaluate multiple feature flags for a customer key in a single request.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: split-evaluator.get-treatments\n      with:\n        key: tools.key\n        split-names: tools.flagNames\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ track-event\n      description: Record a custom event for experimentation and metrics measurement.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: split-evaluator.track-event\n      with:\n        key: tools.key\n        traffic-type: tools.trafficType\n        event-type: tools.eventType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List all users in the Split account.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: split-admin.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-change-requests\n      description: List pending change requests for feature flag modifications requiring approval.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: split-admin.list-change-requests\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
