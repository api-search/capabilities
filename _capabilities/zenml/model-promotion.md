---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Model Promotion
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
slug: model-promotion
source_filename: model-promotion.yaml
source_heading: Capability Spec
source_yaml: "name: ZenML Model Promotion\ndescription: >-\n  Capability for promoting a ZenML model version through stages\n  (none -> staging -> production), recording governance metadata, and\n  triggering downstream deployment pipelines.\napi: zenml\nversion: '1.0.0'\noperations:\n  - id: listModelVersions\n    method: GET\n    path: /model_versions\n    summary: List candidate model versions\n  - id: getModelVersion\n    method: GET\n    path: /model_versions/{model_version_id}\n    summary: Inspect a candidate model version\n  - id: promoteModelVersion\n    method: PUT\n    path: /model_versions/{model_version_id}\n    summary: Update the stage of the model version\n  - id: createDeployment\n    method: POST\n    path: /deployments\n    summary: Create a deployment of the promoted model\nworkflow:\n  - step: listModelVersions\n  - step: getModelVersion\n  - step: promoteModelVersion\n    inputs:\n      stage: production\n  - step: createDeployment\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zenml/refs/heads/main/capabilities/model-promotion.yaml
tags: []
tools: []
---
