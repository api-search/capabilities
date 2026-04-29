---
categories:
- container-orchestration
consumed_apis:
- apptainer
description: Workflow capability for managing HPC containers using Apptainer for scientific computing and research workloads. Supports researchers pulling container images and running reproducible computational experiments.
layout: capability
name: Apptainer HPC Container Management
operations: []
personas: []
provider_name: Apptainer
provider_slug: apptainer
search_terms:
- linux foundation
- run scientific workload
- open source
- starting and monitoring container instances for scientific computation
- monitor running instances
- monitors currently running apptainer container instances
- managing container images for hpc workloads
- pull hpc image
- hpc
- researcher running reproducible computational experiments in containers
- lists apptainer container images optimized for hpc workloads
- scientific computing
- pull images and run reproducible scientific computing workloads
- apptainer
- list hpc images
- pulls a container image for hpc workloads from docker or oci registry
- system administrator managing container infrastructure on hpc clusters
- containers
- research
- starts an apptainer container instance to run a scientific computing workload
slug: hpc-container-management
source_filename: hpc-container-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Apptainer HPC Container Management\n  description: >-\n    Workflow capability for managing HPC containers using Apptainer for scientific\n    computing and research workloads. Supports researchers pulling container images\n    and running reproducible computational experiments.\n  tags:\n    - Apptainer\n    - HPC\n    - Scientific Computing\n    - Containers\n    - Research\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      APPTAINER_API_TOKEN: APPTAINER_API_TOKEN\n\ncapability:\n  consumes:\n    - import: apptainer\n      location: ./shared/apptainer-api.yaml\n\n  exposes:\n    - type: mcp\n      port: 9090\n      namespace: hpc-containers-mcp\n      transport: http\n      description: MCP server for AI-assisted HPC container management with Apptainer.\n      tools:\n        - name: list-hpc-images\n          description: Lists Apptainer container images optimized for HPC workloads\n\
  \          hints:\n            readOnly: true\n            idempotent: true\n          call: \"apptainer.list-images\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: pull-hpc-image\n          description: Pulls a container image for HPC workloads from Docker or OCI registry\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"apptainer.pull-image\"\n          with:\n            source: \"tools.source\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: run-scientific-workload\n          description: Starts an Apptainer container instance to run a scientific computing workload\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"apptainer.start-instance\"\n          with:\n            imageId: \"tools.imageId\"\n            name: \"tools.name\"\n    \
  \        command: \"tools.command\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: monitor-running-instances\n          description: Monitors currently running Apptainer container instances\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"apptainer.list-instances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apptainer/refs/heads/main/capabilities/hpc-container-management.yaml
tags:
- Apptainer
- HPC
- Scientific Computing
- Containers
- Research
tools:
- description: Lists Apptainer container images optimized for HPC workloads
  hints:
    idempotent: true
    readOnly: true
  name: list-hpc-images
- description: Pulls a container image for HPC workloads from Docker or OCI registry
  hints:
    destructive: false
    readOnly: false
  name: pull-hpc-image
- description: Starts an Apptainer container instance to run a scientific computing workload
  hints:
    destructive: false
    readOnly: false
  name: run-scientific-workload
- description: Monitors currently running Apptainer container instances
  hints:
    idempotent: true
    readOnly: true
  name: monitor-running-instances
---
