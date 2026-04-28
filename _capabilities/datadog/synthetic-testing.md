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
- get the on-demand concurrency cap
- individual monitor operations
- get a monitor by id
- set a new synthetics on-demand concurrency cap
- qa
- validate monitor
- update a monitor
- createMonitor
- updateMonitor
- deleteMonitor
- datadog
- mute synthetic alert monitors
- mute a monitor
- visualizations
- getMonitor
- create monitor
- delete monitor
- get concurrency cap
- validateMonitor
- unmute monitor
- mute a synthetic test monitor
- unmute a synthetic test monitor
- list monitors
- muteMonitor
- validate synthetic monitor configurations
- set concurrency cap
- validate a monitor
- GetOnDemandConcurrencyCap
- update a synthetics alert monitor
- monitor management for synthetic alerts
- get a monitor
- delete a monitor
- monitoring
- get the synthetics on-demand concurrency cap
- update monitor
- mute monitor
- validate a synthetic monitor configuration
- set the on-demand concurrency cap
- analytics
- monitors
- synthetics
- listMonitors
- t1
- create a monitor
- dashboards
- create a synthetics alert monitor
- platform
- get monitor
- synthetics concurrency settings
- list monitors including synthetic alert monitors
- SetOnDemandConcurrencyCap
- synthetic testing
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
