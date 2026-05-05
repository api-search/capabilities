---
categories: []
consumed_apis:
- statsig-http
- statsig-console
description: Unified feature management workflow combining Statsig's HTTP API and Console API. Enables product teams to evaluate feature gates in real-time, manage gate configuration, run A/B experiments, track exposures, and log analytics events from a single integration. Supports the full feature management lifecycle from gate creation through experiment analysis.
layout: capability
name: Statsig Feature Management
operations:
- description: Evaluate a feature gate for a user.
  method: POST
  name: check-gate
  path: /v1/gates/check
- description: Get dynamic config values for a user.
  method: POST
  name: get-config
  path: /v1/configs/get
- description: Get experiment group assignment for a user.
  method: POST
  name: get-experiment
  path: /v1/experiments/evaluate
- description: Log analytics events and exposures.
  method: POST
  name: log-events
  path: /v1/events
- description: List all feature gates.
  method: GET
  name: list-gates
  path: /v1/management/gates
- description: Create a new feature gate.
  method: POST
  name: create-gate
  path: /v1/management/gates
- description: List all experiments.
  method: GET
  name: list-experiments
  path: /v1/management/experiments
- description: Create a new experiment.
  method: POST
  name: create-experiment
  path: /v1/management/experiments
- description: List configuration change audit logs.
  method: GET
  name: list-audit-logs
  path: /v1/management/audit-logs
personas: []
provider_name: statsig
provider_slug: statsig
search_terms:
- dynamic configuration
- initialize all evaluated gates, configs, and experiments for a user (for client sdk use).
- check multiple gates
- list audit log entries showing who changed what in the project configuration.
- list all feature gates.
- analytics event logging.
- product analytics
- list experiments
- list configuration change audit logs.
- evaluate multiple feature gates for a user in a single request.
- initialize sdk
- feature management
- log custom analytics events and experiment exposures to statsig.
- experimentation
- log analytics events
- experiment management.
- get feature gate config
- check gate
- get a user's experiment group assignment and parameter values.
- dynamic configuration retrieval.
- feature flags
- get config
- list audit logs
- delete feature gate
- list gates
- get dynamic config
- list feature gates
- runtime experiment evaluation.
- permanently delete a feature gate from the project.
- start experiment
- log analytics events and exposures.
- gate configuration management.
- list all experiments.
- create a new feature gate with targeting rules.
- create feature gate
- evaluate whether a feature gate passes for a given user, including rule matching and group assignment.
- list all feature gates in the statsig project.
- log events
- fetch dynamic configuration key-value pairs for a user.
- list metrics
- get experiment group assignment for a user.
- create a new experiment.
- a/b testing
- runtime gate evaluation.
- get experiment
- list all metric definitions used in experiment analysis.
- project audit log.
- get the full configuration of a feature gate by name.
- get dynamic config values for a user.
- check feature gate
- create a new feature gate.
- get experiment assignment
- start an experiment to begin allocating users to test groups.
- create a new a/b test experiment with groups and parameter configuration.
- create gate
- list all a/b test experiments in the project.
- evaluate a feature gate for a user.
- create experiment
slug: feature-management
source_filename: feature-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Statsig Feature Management\"\n  description: >-\n    Unified feature management workflow combining Statsig's HTTP API and\n    Console API. Enables product teams to evaluate feature gates in real-time,\n    manage gate configuration, run A/B experiments, track exposures, and\n    log analytics events from a single integration. Supports the full feature\n    management lifecycle from gate creation through experiment analysis.\n  tags:\n    - Feature Flags\n    - Feature Management\n    - A/B Testing\n    - Experimentation\n    - Product Analytics\n    - Dynamic Configuration\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STATSIG_SERVER_SECRET_KEY: STATSIG_SERVER_SECRET_KEY\n      STATSIG_CONSOLE_API_KEY: STATSIG_CONSOLE_API_KEY\n\ncapability:\n  consumes:\n    - import: statsig-http\n      location: ./shared/http-api.yaml\n    - import: statsig-console\n      location: ./shared/console-api.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: statsig-feature-management-api\n      description: \"Unified REST API for Statsig feature management across evaluation and administration.\"\n      resources:\n        - path: /v1/gates/check\n          name: check-gate\n          description: \"Runtime gate evaluation.\"\n          operations:\n            - method: POST\n              name: check-gate\n              description: \"Evaluate a feature gate for a user.\"\n              call: \"statsig-http.check-gate\"\n              with:\n                user: \"rest.user\"\n                gateName: \"rest.gateName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/configs/get\n          name: get-config\n          description: \"Dynamic configuration retrieval.\"\n          operations:\n            - method: POST\n              name: get-config\n              description: \"Get dynamic config values\
  \ for a user.\"\n              call: \"statsig-http.get-config\"\n              with:\n                user: \"rest.user\"\n                configName: \"rest.configName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/experiments/evaluate\n          name: evaluate-experiment\n          description: \"Runtime experiment evaluation.\"\n          operations:\n            - method: POST\n              name: get-experiment\n              description: \"Get experiment group assignment for a user.\"\n              call: \"statsig-http.get-experiment\"\n              with:\n                user: \"rest.user\"\n                experimentName: \"rest.experimentName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events\n          name: events\n          description: \"Analytics event logging.\"\n          operations:\n            - method: POST\n\
  \              name: log-events\n              description: \"Log analytics events and exposures.\"\n              call: \"statsig-http.log-events\"\n              with:\n                events: \"rest.events\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/management/gates\n          name: manage-gates\n          description: \"Gate configuration management.\"\n          operations:\n            - method: GET\n              name: list-gates\n              description: \"List all feature gates.\"\n              call: \"statsig-console.list-gates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-gate\n              description: \"Create a new feature gate.\"\n              call: \"statsig-console.create-gate\"\n              with:\n                name: \"rest.name\"\n                rules: \"rest.rules\"\n\
  \                tags: \"rest.tags\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/management/experiments\n          name: manage-experiments\n          description: \"Experiment management.\"\n          operations:\n            - method: GET\n              name: list-experiments\n              description: \"List all experiments.\"\n              call: \"statsig-console.list-experiments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-experiment\n              description: \"Create a new experiment.\"\n              call: \"statsig-console.create-experiment\"\n              with:\n                name: \"rest.name\"\n                groups: \"rest.groups\"\n                allocation: \"rest.allocation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n\n        - path: /v1/management/audit-logs\n          name: audit-logs\n          description: \"Project audit log.\"\n          operations:\n            - method: GET\n              name: list-audit-logs\n              description: \"List configuration change audit logs.\"\n              call: \"statsig-console.list-audit-logs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: statsig-feature-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Statsig feature management, experimentation, and analytics.\"\n      tools:\n        - name: check-feature-gate\n          description: \"Evaluate whether a feature gate passes for a given user, including rule matching and group assignment.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"statsig-http.check-gate\"\n          with:\n            user: \"tools.user\"\
  \n            gateName: \"tools.gateName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-multiple-gates\n          description: \"Evaluate multiple feature gates for a user in a single request.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"statsig-http.check-gate-multiple\"\n          with:\n            user: \"tools.user\"\n            gateNames: \"tools.gateNames\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-dynamic-config\n          description: \"Fetch dynamic configuration key-value pairs for a user.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"statsig-http.get-config\"\n          with:\n            user: \"tools.user\"\n            configName: \"tools.configName\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n\n        - name: get-experiment-assignment\n          description: \"Get a user's experiment group assignment and parameter values.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"statsig-http.get-experiment\"\n          with:\n            user: \"tools.user\"\n            experimentName: \"tools.experimentName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: initialize-sdk\n          description: \"Initialize all evaluated gates, configs, and experiments for a user (for client SDK use).\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"statsig-http.initialize\"\n          with:\n            user: \"tools.user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: log-analytics-events\n          description: \"Log custom analytics events and experiment exposures to Statsig.\"\
  \n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"statsig-http.log-events\"\n          with:\n            events: \"tools.events\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-feature-gates\n          description: \"List all feature gates in the Statsig project.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"statsig-console.list-gates\"\n          with:\n            limit: \"tools.limit\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-feature-gate\n          description: \"Create a new feature gate with targeting rules.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"statsig-console.create-gate\"\n          with:\n\
  \            name: \"tools.name\"\n            description: \"tools.description\"\n            rules: \"tools.rules\"\n            tags: \"tools.tags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-feature-gate-config\n          description: \"Get the full configuration of a feature gate by name.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"statsig-console.get-gate\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-feature-gate\n          description: \"Permanently delete a feature gate from the project.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"statsig-console.delete-gate\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: list-experiments\n          description: \"List all A/B test experiments in the project.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"statsig-console.list-experiments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-experiment\n          description: \"Create a new A/B test experiment with groups and parameter configuration.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"statsig-console.create-experiment\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n            hypothesis: \"tools.hypothesis\"\n            groups: \"tools.groups\"\n            allocation: \"tools.allocation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-experiment\n\
  \          description: \"Start an experiment to begin allocating users to test groups.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"statsig-console.start-experiment\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-metrics\n          description: \"List all metric definitions used in experiment analysis.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"statsig-console.list-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-audit-logs\n          description: \"List audit log entries showing who changed what in the project configuration.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"statsig-console.list-audit-logs\"\n          with:\n\
  \            limit: \"tools.limit\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/statsig/refs/heads/main/capabilities/feature-management.yaml
tags:
- Feature Flags
- Feature Management
- A/B Testing
- Experimentation
- Product Analytics
- Dynamic Configuration
tools:
- description: Evaluate whether a feature gate passes for a given user, including rule matching and group assignment.
  hints:
    openWorld: false
    readOnly: true
  name: check-feature-gate
- description: Evaluate multiple feature gates for a user in a single request.
  hints:
    openWorld: false
    readOnly: true
  name: check-multiple-gates
- description: Fetch dynamic configuration key-value pairs for a user.
  hints:
    openWorld: false
    readOnly: true
  name: get-dynamic-config
- description: Get a user's experiment group assignment and parameter values.
  hints:
    openWorld: false
    readOnly: true
  name: get-experiment-assignment
- description: Initialize all evaluated gates, configs, and experiments for a user (for client SDK use).
  hints:
    openWorld: false
    readOnly: true
  name: initialize-sdk
- description: Log custom analytics events and experiment exposures to Statsig.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: log-analytics-events
- description: List all feature gates in the Statsig project.
  hints:
    openWorld: true
    readOnly: true
  name: list-feature-gates
- description: Create a new feature gate with targeting rules.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-feature-gate
- description: Get the full configuration of a feature gate by name.
  hints:
    openWorld: false
    readOnly: true
  name: get-feature-gate-config
- description: Permanently delete a feature gate from the project.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-feature-gate
- description: List all A/B test experiments in the project.
  hints:
    openWorld: true
    readOnly: true
  name: list-experiments
- description: Create a new A/B test experiment with groups and parameter configuration.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-experiment
- description: Start an experiment to begin allocating users to test groups.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: start-experiment
- description: List all metric definitions used in experiment analysis.
  hints:
    openWorld: true
    readOnly: true
  name: list-metrics
- description: List audit log entries showing who changed what in the project configuration.
  hints:
    openWorld: true
    readOnly: true
  name: list-audit-logs
---
