---
consumed_apis:
- opencue
description: Render farm management workflow using OpenCue for monitoring and managing render jobs, layers, frames, and hosts in a VFX production pipeline. Used by render wranglers and pipeline TDs to monitor and troubleshoot render farm operations.
layout: capability
name: Academy Software Foundation Render Farm Management
operations:
- description: List all active shows in the render farm
  method: GET
  name: list-shows
  path: /v1/shows
- description: List render jobs for a show
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Get details for a specific render job
  method: GET
  name: get-job
  path: /v1/jobs/{job_id}
- description: List all render host machines
  method: GET
  name: list-hosts
  path: /v1/hosts
personas:
- description: Production staff responsible for monitoring and managing render farm operations
  id: render-wrangler
  name: Render Wrangler
- description: Technical director building and maintaining VFX production pipeline tools
  id: pipeline-td
  name: Pipeline TD
provider_name: Academy Software Foundation
provider_slug: academy-software-foundation
search_terms:
- vfx pipeline
- film
- list and manage render shows (productions)
- technical director building and maintaining vfx production pipeline tools
- color management
- get job
- standards
- list render jobs for a specific show with optional state filtering
- production staff responsible for monitoring and managing render farm operations
- monitor and manage render jobs, hosts, and shows using opencue
- get detailed status and frame counts for a specific render job
- list all render host machines
- monitoring and management of distributed render farm resources and jobs
- vfx
- get or kill a specific render job
- academy software foundation
- pipeline td
- get details for a specific render job
- rendering
- list render jobs
- list all active shows (productions) in the render farm
- animation
- render wrangler
- list render jobs for a show
- list shows
- list render hosts
- opencue
- get render job
- open source
- list hosts
- list jobs
- linux foundation
- list all render host machines and their current utilization
- list and manage render hosts
- list all active shows in the render farm
- list and manage render jobs
- render farm
- visual effects
slug: render-farm-management
tags:
- Academy Software Foundation
- Render Farm
- Opencue
- Vfx Pipeline
tools:
- description: List all active shows (productions) in the render farm
  hints:
    openWorld: false
    readOnly: true
  name: list-shows
- description: List render jobs for a specific show with optional state filtering
  hints:
    openWorld: false
    readOnly: true
  name: list-render-jobs
- description: Get detailed status and frame counts for a specific render job
  hints:
    openWorld: false
    readOnly: true
  name: get-render-job
- description: List all render host machines and their current utilization
  hints:
    openWorld: false
    readOnly: true
  name: list-render-hosts
---
