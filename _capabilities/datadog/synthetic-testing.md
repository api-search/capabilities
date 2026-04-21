---
consumed_apis:
- dd-synthetics
- dd-monitors
description: Unified workflow for synthetic testing combining synthetics concurrency management and monitors. Used by QA engineers and SREs for managing synthetic test execution capacity and monitoring test results.
layout: capability
name: Datadog Synthetic Testing
operations:
- description: Get the on-demand concurrency cap
  method: GET
  name: GetOnDemandConcurrencyCap
  path: /v1/synthetics/concurrency-cap
- description: Set the on-demand concurrency cap
  method: POST
  name: SetOnDemandConcurrencyCap
  path: /v1/synthetics/concurrency-cap
- description: List monitors
  method: GET
  name: listMonitors
  path: /v1/monitors
- description: Create a monitor
  method: POST
  name: createMonitor
  path: /v1/monitors
- description: Get a monitor
  method: GET
  name: getMonitor
  path: /v1/monitors/{monitor_id}
- description: Update a monitor
  method: PUT
  name: updateMonitor
  path: /v1/monitors/{monitor_id}
- description: Delete a monitor
  method: DELETE
  name: deleteMonitor
  path: /v1/monitors/{monitor_id}
- description: Mute a monitor
  method: POST
  name: muteMonitor
  path: /v1/monitors/{monitor_id}/mute
- description: Validate a monitor
  method: POST
  name: validateMonitor
  path: /v1/monitors/validate
personas: []
provider_name: Datadog
provider_slug: datadog
search_terms:
- muteMonitor
- update a synthetics alert monitor
- validateMonitor
- delete a monitor
- monitor management for synthetic alerts
- create a synthetics alert monitor
- visualizations
- GetOnDemandConcurrencyCap
- deleteMonitor
- analytics
- validate monitor
- mute a monitor
- set a new synthetics on-demand concurrency cap
- synthetics
- updateMonitor
- get monitor
- get concurrency cap
- mute monitor
- unmute a synthetic test monitor
- unmute monitor
- listMonitors
- validate synthetic monitor configurations
- list monitors including synthetic alert monitors
- dashboards
- platform
- t1
- mute synthetic alert monitors
- delete monitor
- synthetic testing
- set concurrency cap
- get the synthetics on-demand concurrency cap
- qa
- synthetics concurrency settings
- create monitor
- getMonitor
- create a monitor
- mute a synthetic test monitor
- validate a monitor
- set the on-demand concurrency cap
- validate a synthetic monitor configuration
- monitoring
- list monitors
- update monitor
- get a monitor
- createMonitor
- update a monitor
- SetOnDemandConcurrencyCap
- get the on-demand concurrency cap
- monitors
- get a monitor by id
- datadog
- individual monitor operations
slug: synthetic-testing
tags:
- Datadog
- Synthetic Testing
- Synthetics
- Monitors
- QA
tools:
- description: Get the synthetics on-demand concurrency cap
  hints:
    readOnly: true
  name: get-concurrency-cap
- description: Set a new synthetics on-demand concurrency cap
  hints: {}
  name: set-concurrency-cap
- description: List monitors including synthetic alert monitors
  hints:
    readOnly: true
  name: list-monitors
- description: Get a monitor by ID
  hints:
    readOnly: true
  name: get-monitor
- description: Create a synthetics alert monitor
  hints: {}
  name: create-monitor
- description: Update a synthetics alert monitor
  hints:
    idempotent: true
  name: update-monitor
- description: Delete a monitor
  hints:
    destructive: true
  name: delete-monitor
- description: Mute a synthetic test monitor
  hints: {}
  name: mute-monitor
- description: Unmute a synthetic test monitor
  hints: {}
  name: unmute-monitor
- description: Validate a synthetic monitor configuration
  hints:
    readOnly: true
  name: validate-monitor
---
