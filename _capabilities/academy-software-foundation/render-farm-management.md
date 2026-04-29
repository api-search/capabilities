---
categories: []
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
- render farm
- standards
- list and manage render jobs
- list all active shows in the render farm
- get detailed status and frame counts for a specific render job
- list and manage render shows (productions)
- get details for a specific render job
- list render jobs for a specific show with optional state filtering
- list all active shows (productions) in the render farm
- technical director building and maintaining vfx production pipeline tools
- linux foundation
- list jobs
- list all render host machines and their current utilization
- rendering
- vfx pipeline
- pipeline td
- color management
- get or kill a specific render job
- animation
- film
- list and manage render hosts
- list hosts
- monitor and manage render jobs, hosts, and shows using opencue
- render wrangler
- get render job
- academy software foundation
- list render hosts
- visual effects
- vfx
- list render jobs
- get job
- monitoring and management of distributed render farm resources and jobs
- production staff responsible for monitoring and managing render farm operations
- opencue
- list shows
- list all render host machines
- list render jobs for a show
- open source
slug: render-farm-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Academy Software Foundation Render Farm Management\"\n  description: \"Render farm management workflow using OpenCue for monitoring and managing render jobs, layers, frames, and hosts in a VFX production pipeline. Used by render wranglers and pipeline TDs to monitor and troubleshoot render farm operations.\"\n  tags:\n    - Academy Software Foundation\n    - Render Farm\n    - Opencue\n    - Vfx Pipeline\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      OPENCUE_HOST: OPENCUE_HOST\n\ncapability:\n  consumes:\n    - import: opencue\n      location: ./shared/opencue.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: render-farm-api\n      description: \"Unified REST API for VFX render farm management.\"\n      resources:\n        - path: /v1/shows\n          name: shows\n          description: \"List and manage render shows (productions)\"\n          operations:\n\
  \            - method: GET\n              name: list-shows\n              description: \"List all active shows in the render farm\"\n              call: \"opencue.listShows\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs\n          name: jobs\n          description: \"List and manage render jobs\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List render jobs for a show\"\n              call: \"opencue.listJobs\"\n              with:\n                show_id: \"rest.show_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs/{job_id}\n          name: job\n          description: \"Get or kill a specific render job\"\n          operations:\n            - method: GET\n              name: get-job\n              description: \"Get details for a specific render job\"\n     \
  \         call: \"opencue.getJob\"\n              with:\n                job_id: \"rest.job_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/hosts\n          name: hosts\n          description: \"List and manage render hosts\"\n          operations:\n            - method: GET\n              name: list-hosts\n              description: \"List all render host machines\"\n              call: \"opencue.listHosts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: render-farm-mcp\n      transport: http\n      description: \"MCP server for AI-assisted render farm monitoring and management.\"\n      tools:\n        - name: list-shows\n          description: \"List all active shows (productions) in the render farm\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"opencue.listShows\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-render-jobs\n          description: \"List render jobs for a specific show with optional state filtering\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"opencue.listJobs\"\n          with:\n            show_id: \"tools.show_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-render-job\n          description: \"Get detailed status and frame counts for a specific render job\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"opencue.getJob\"\n          with:\n            job_id: \"tools.job_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-render-hosts\n          description: \"List all render host machines and their current utilization\"\n          hints:\n  \
  \          readOnly: true\n            openWorld: false\n          call: \"opencue.listHosts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/academy-software-foundation/refs/heads/main/capabilities/render-farm-management.yaml
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
