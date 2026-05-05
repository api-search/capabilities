---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Pipeline Lifecycle
operations: []
personas: []
provider_name: ZenML
provider_slug: zenml
search_terms:
- mlops
- pipelines
- python
- machine learning
- llmops
- ai
- open source
slug: pipeline-lifecycle
source_filename: pipeline-lifecycle.yaml
source_heading: Capability Spec
source_yaml: "name: ZenML Pipeline Lifecycle\ndescription: >-\n  End-to-end capability composition covering the lifecycle of a ZenML\n  pipeline: registering a pipeline, configuring a stack, triggering a run,\n  monitoring its status, and inspecting produced artifacts and model versions.\napi: zenml\nversion: '1.0.0'\noperations:\n  - id: registerPipeline\n    method: POST\n    path: /pipelines\n    summary: Register a new pipeline definition\n  - id: configureStack\n    method: POST\n    path: /stacks\n    summary: Create or update the execution stack\n  - id: triggerRun\n    method: POST\n    path: /runs\n    summary: Trigger a pipeline run on the configured stack\n  - id: monitorRun\n    method: GET\n    path: /runs/{run_id}\n    summary: Poll the status of a pipeline run\n  - id: listArtifacts\n    method: GET\n    path: /artifacts\n    summary: List artifacts produced by the run\n  - id: registerModelVersion\n    method: POST\n    path: /model_versions\n    summary: Register a new model\
  \ version produced by the run\nworkflow:\n  - step: registerPipeline\n  - step: configureStack\n  - step: triggerRun\n  - step: monitorRun\n    until:\n      status: completed\n  - step: listArtifacts\n  - step: registerModelVersion\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zenml/refs/heads/main/capabilities/pipeline-lifecycle.yaml
tags: []
tools: []
---
