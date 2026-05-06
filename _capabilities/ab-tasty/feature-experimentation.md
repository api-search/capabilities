---
categories: []
consumed_apis: []
description: Unified workflow for server-side feature experimentation, A/B testing, and feature flag management. Enables developers and product teams to evaluate campaigns, retrieve flag values, and track activations for controlled rollouts and experiments.
layout: capability
name: AB Tasty Feature Experimentation
operations:
- description: Evaluate visitor context and retrieve all matching campaign assignments
  method: POST
  name: get-campaigns
  path: /v1/campaigns
- description: Get assignment for a specific campaign by ID
  method: POST
  name: get-campaign
  path: /v1/campaigns/{campaignId}
- description: Retrieve feature flag values and metadata for a visitor
  method: POST
  name: get-flags
  path: /v1/flags
- description: Manually activate a campaign variation for a visitor
  method: POST
  name: activate-campaign
  path: /v1/activate
personas: []
provider_name: AB Tasty
provider_slug: ab-tasty
search_terms:
- get campaigns
- retrieve a specific campaign assignment for a visitor, useful for targeted experiment evaluation
- server side
- get visitor flags
- get visitor campaigns
- a/b testing
- manually activate a campaign variation assignment, used when auto-activation is disabled via trigger_hit=false
- activate experiment
- quality assurance engineer using remote control api to test experiments
- retrieve feature flag values and metadata for a visitor, used to implement feature toggles and progressive rollouts
- Developer
- experimentation
- manually activate a campaign variation for a visitor
- conversion tracking and experiment measurement
- ab tasty
- product manager monitoring experiment assignments and flag rollouts
- activate campaign
- unified workflow for server-side feature experimentation, a/b testing, and feature flag management
- retrieve feature flag values and metadata for a visitor
- get campaign
- Product Manager
- backend or frontend developer implementing server-side experiments and feature flags
- feature flag evaluation operations
- a/b testing, multivariate testing, and experiment management
- evaluate visitor context and retrieve all matching campaign assignments
- get flags
- evaluate a visitor's context and retrieve all active campaign and variation assignments for server-side rendering
- get assignment for a specific campaign by id
- retrieve a specific campaign assignment for a visitor
- feature flags
- aggregation
- progressive feature releases and feature toggles
- manual campaign activation
- retrieve campaign assignments for a visitor based on context
- get visitor campaign
- personalization
slug: feature-experimentation
source_filename: feature-experimentation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AB Tasty Feature Experimentation\n  description: Unified workflow for server-side feature experimentation, A/B testing, and feature flag management. Enables\n    developers and product teams to evaluate campaigns, retrieve flag values, and track activations for controlled rollouts\n    and experiments.\n  tags:\n  - AB Tasty\n  - Experimentation\n  - Feature Flags\n  - A/B Testing\n  - Server Side\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AB_TASTY_API_KEY: AB_TASTY_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: decision-api\n    baseUri: https://decision.flagship.io/v2\n    description: AB Tasty Decision API for server-side experimentation and feature flagging\n    authentication:\n      type: apikey\n      key: x-api-key\n      value: '{{AB_TASTY_API_KEY}}'\n      placement: header\n    resources:\n    - name: campaigns\n      path: /{environmentId}/campaigns\n      description:\
  \ Campaign assignment operations for all campaigns\n      operations:\n      - name: get-campaigns\n        method: POST\n        description: Retrieve all campaign assignments for a visitor\n        inputParameters:\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: mode\n          in: query\n          type: string\n          required: false\n          description: Response format mode (normal, simple, full)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaign\n      path: /{environmentId}/campaigns/{campaignId}\n      description: Single campaign assignment operations\n      operations:\n      - name: get-campaign\n        method: POST\n        description: Retrieve a specific campaign assignment for a visitor\n        inputParameters:\n        - name: environmentId\n         \
  \ in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: campaignId\n          in: path\n          type: string\n          required: true\n          description: Campaign identifier or slug\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flags\n      path: /{environmentId}/flags\n      description: Feature flag operations\n      operations:\n      - name: get-flags\n        method: POST\n        description: Retrieve feature flags with values and metadata for a visitor\n        inputParameters:\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: exposeAllKeys\n          in: query\n          type: boolean\n          required: false\n          description: If true, returns all flag keys including null values\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activate\n      path: /activate\n      description: Manual campaign activation operations\n      operations:\n      - name: activate-campaign\n        method: POST\n        description: Manually activate a campaign variation for a visitor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: feature-experimentation-api\n    description: Unified REST API for AB Tasty server-side feature experimentation and campaign management.\n    resources:\n    - path: /v1/campaigns\n      name: campaigns\n      description: Retrieve campaign assignments for a visitor based on context\n      operations:\n      - method: POST\n        name: get-campaigns\n        description: Evaluate visitor context and retrieve all matching campaign assignments\n        call:\
  \ decision-api.get-campaigns\n        with:\n          environmentId: rest.environmentId\n          mode: rest.mode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns/{campaignId}\n      name: campaign\n      description: Retrieve a specific campaign assignment for a visitor\n      operations:\n      - method: POST\n        name: get-campaign\n        description: Get assignment for a specific campaign by ID\n        call: decision-api.get-campaign\n        with:\n          environmentId: rest.environmentId\n          campaignId: rest.campaignId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flags\n      name: flags\n      description: Feature flag evaluation operations\n      operations:\n      - method: POST\n        name: get-flags\n        description: Retrieve feature flag values and metadata for a visitor\n        call: decision-api.get-flags\n        with:\n          environmentId: rest.environmentId\n\
  \          exposeAllKeys: rest.exposeAllKeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/activate\n      name: activate\n      description: Manual campaign activation\n      operations:\n      - method: POST\n        name: activate-campaign\n        description: Manually activate a campaign variation for a visitor\n        call: decision-api.activate-campaign\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: feature-experimentation-mcp\n    transport: http\n    description: MCP server for AI-assisted feature experimentation and A/B test management.\n    tools:\n    - name: get-visitor-campaigns\n      description: Evaluate a visitor's context and retrieve all active campaign and variation assignments for server-side\n        rendering\n      hints:\n        readOnly: true\n        openWorld: false\n      call: decision-api.get-campaigns\n      with:\n        environmentId:\
  \ tools.environmentId\n        mode: tools.mode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-visitor-campaign\n      description: Retrieve a specific campaign assignment for a visitor, useful for targeted experiment evaluation\n      hints:\n        readOnly: true\n        openWorld: false\n      call: decision-api.get-campaign\n      with:\n        environmentId: tools.environmentId\n        campaignId: tools.campaignId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-visitor-flags\n      description: Retrieve feature flag values and metadata for a visitor, used to implement feature toggles and progressive\n        rollouts\n      hints:\n        readOnly: true\n        openWorld: false\n      call: decision-api.get-flags\n      with:\n        environmentId: tools.environmentId\n        exposeAllKeys: tools.exposeAllKeys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: activate-experiment\n\
  \      description: Manually activate a campaign variation assignment, used when auto-activation is disabled via trigger_hit=false\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: decision-api.activate-campaign\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ab-tasty/refs/heads/main/capabilities/feature-experimentation.yaml
tags:
- AB Tasty
- Experimentation
- Feature Flags
- A/B Testing
- Server Side
tools:
- description: Evaluate a visitor's context and retrieve all active campaign and variation assignments for server-side rendering
  hints:
    openWorld: false
    readOnly: true
  name: get-visitor-campaigns
- description: Retrieve a specific campaign assignment for a visitor, useful for targeted experiment evaluation
  hints:
    openWorld: false
    readOnly: true
  name: get-visitor-campaign
- description: Retrieve feature flag values and metadata for a visitor, used to implement feature toggles and progressive rollouts
  hints:
    openWorld: false
    readOnly: true
  name: get-visitor-flags
- description: Manually activate a campaign variation assignment, used when auto-activation is disabled via trigger_hit=false
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: activate-experiment
---
