---
categories: []
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
- update a monitor
- create a synthetics alert monitor
- monitors
- dashboards
- get concurrency cap
- set a new synthetics on-demand concurrency cap
- validateMonitor
- validate monitor
- visualizations
- delete monitor
- update a synthetics alert monitor
- get the on-demand concurrency cap
- analytics
- mute monitor
- platform
- validate a synthetic monitor configuration
- create monitor
- qa
- synthetic testing
- get a monitor by id
- validate synthetic monitor configurations
- monitor management for synthetic alerts
- get the synthetics on-demand concurrency cap
- set concurrency cap
- set the on-demand concurrency cap
- create a monitor
- mute synthetic alert monitors
- validate a monitor
- unmute monitor
- datadog
- updateMonitor
- individual monitor operations
- monitoring
- synthetics
- unmute a synthetic test monitor
- list monitors
- deleteMonitor
- list monitors including synthetic alert monitors
- delete a monitor
- update monitor
- t1
- createMonitor
- mute a monitor
- listMonitors
- muteMonitor
- GetOnDemandConcurrencyCap
- get a monitor
- get monitor
- synthetics concurrency settings
- getMonitor
- SetOnDemandConcurrencyCap
- mute a synthetic test monitor
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
