---
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
- monitor running instances
- hpc
- researcher running reproducible computational experiments in containers
- system administrator managing container infrastructure on hpc clusters
- managing container images for hpc workloads
- containers
- research
- run scientific workload
- pull hpc image
- starts an apptainer container instance to run a scientific computing workload
- pulls a container image for hpc workloads from docker or oci registry
- lists apptainer container images optimized for hpc workloads
- monitors currently running apptainer container instances
- pull images and run reproducible scientific computing workloads
- list hpc images
- apptainer
- starting and monitoring container instances for scientific computation
- linux foundation
- open source
- scientific computing
slug: hpc-container-management
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
