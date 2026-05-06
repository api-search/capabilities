---
categories: []
consumed_apis: []
description: The Cloud Deploy API provides programmatic access to manage delivery pipelines, targets, releases, and rollouts for continuous delivery workflows on Google Cloud. It supports promoting releases through target environments with approval gates and rollback capabilities.
layout: capability
name: Google Cloud Deploy API
operations:
- description: Google Cloud Deploy List delivery pipelines
  method: GET
  name: listdeliverypipelines
  path: /projects/{projectId}/locations/{location}/deliveryPipelines
- description: Google Cloud Deploy Create a delivery pipeline
  method: POST
  name: createdeliverypipeline
  path: /projects/{projectId}/locations/{location}/deliveryPipelines
- description: Google Cloud Deploy Get a delivery pipeline
  method: GET
  name: getdeliverypipeline
  path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}
- description: Google Cloud Deploy Update a delivery pipeline
  method: PATCH
  name: updatedeliverypipeline
  path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}
- description: Google Cloud Deploy Delete a delivery pipeline
  method: DELETE
  name: deletedeliverypipeline
  path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}
- description: Google Cloud Deploy List targets
  method: GET
  name: listtargets
  path: /projects/{projectId}/locations/{location}/targets
- description: Google Cloud Deploy Create a target
  method: POST
  name: createtarget
  path: /projects/{projectId}/locations/{location}/targets
- description: Google Cloud Deploy List releases
  method: GET
  name: listreleases
  path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}/releases
- description: Google Cloud Deploy Create a release
  method: POST
  name: createrelease
  path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}/releases
- description: Google Cloud Deploy List rollouts
  method: GET
  name: listrollouts
  path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}/releases/{releaseId}/rollouts
- description: Google Cloud Deploy Create a rollout
  method: POST
  name: createrollout
  path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}/releases/{releaseId}/rollouts
- description: Google Cloud Deploy Approve a rollout
  method: POST
  name: approverollout
  path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}/releases/{releaseId}/rollouts/{rolloutId}:approve
personas: []
provider_name: Google Cloud Deploy
provider_slug: google-cloud-deploy
search_terms:
- approverollout
- google cloud deploy get a delivery pipeline
- google cloud deploy create a delivery pipeline
- getdeliverypipeline
- deletedeliverypipeline
- updatedeliverypipeline
- devops
- google cloud deploy list rollouts
- cloud
- google cloud deploy list releases
- deployment
- google
- deploy
- createrelease
- kubernetes
- google cloud deploy create a release
- listreleases
- api
- google cloud deploy list targets
- listrollouts
- google cloud deploy create a rollout
- listdeliverypipelines
- release management
- google cloud deploy list delivery pipelines
- createtarget
- google cloud deploy approve a rollout
- createdeliverypipeline
- google cloud deploy delete a delivery pipeline
- google cloud deploy update a delivery pipeline
- pipeline
- continuous delivery
- createrollout
- listtargets
- google cloud deploy create a target
slug: google-cloud-deploy-capability
source_filename: google-cloud-deploy-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Deploy API\n  description: The Cloud Deploy API provides programmatic access to manage delivery pipelines, targets, releases, and rollouts\n    for continuous delivery workflows on Google Cloud. It supports promoting releases through target environments with approval\n    gates and rollback capabilities.\n  tags:\n  - Google\n  - Cloud\n  - Deploy\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-deploy\n    baseUri: https://clouddeploy.googleapis.com/v1\n    description: Google Cloud Deploy API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_DEPLOY_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations-location-deliverypi\n      path: /projects/{projectId}/locations/{location}/deliveryPipelines\n      operations:\n      - name: listdeliverypipelines\n        method: GET\n        description: Google\
  \ Cloud Deploy List delivery pipelines\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdeliverypipeline\n        method: POST\n        description: Google Cloud Deploy Create a delivery pipeline\n        inputParameters:\n        - name: deliveryPipelineId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-deliverypi\n      path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}\n      operations:\n      - name: getdeliverypipeline\n        method: GET\n        description: Google Cloud Deploy Get a delivery pipeline\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedeliverypipeline\n\
  \        method: PATCH\n        description: Google Cloud Deploy Update a delivery pipeline\n        inputParameters:\n        - name: updateMask\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedeliverypipeline\n        method: DELETE\n        description: Google Cloud Deploy Delete a delivery pipeline\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-targets\n      path: /projects/{projectId}/locations/{location}/targets\n      operations:\n      - name: listtargets\n        method: GET\n        description: Google Cloud Deploy List targets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtarget\n        method: POST\n\
  \        description: Google Cloud Deploy Create a target\n        inputParameters:\n        - name: targetId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-deliverypi\n      path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}/releases\n      operations:\n      - name: listreleases\n        method: GET\n        description: Google Cloud Deploy List releases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrelease\n        method: POST\n        description: Google Cloud Deploy Create a release\n        inputParameters:\n        - name: releaseId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-deliverypi\n      path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}/releases/{releaseId}/rollouts\n      operations:\n      - name: listrollouts\n        method: GET\n        description: Google Cloud Deploy List rollouts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrollout\n        method: POST\n        description: Google Cloud Deploy Create a rollout\n        inputParameters:\n        - name: rolloutId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-deliverypi\n      path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}/releases/{releaseId}/rollouts/{rolloutId}:approve\n\
  \      operations:\n      - name: approverollout\n        method: POST\n        description: Google Cloud Deploy Approve a rollout\n        inputParameters:\n        - name: rolloutId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-deploy-rest\n    description: REST adapter for Google Cloud Deploy API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/deliveryPipelines\n      name: listdeliverypipelines\n      operations:\n      - method: GET\n        name: listdeliverypipelines\n        description: Google Cloud Deploy List delivery pipelines\n        call: google-cloud-deploy.listdeliverypipelines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/deliveryPipelines\n\
  \      name: createdeliverypipeline\n      operations:\n      - method: POST\n        name: createdeliverypipeline\n        description: Google Cloud Deploy Create a delivery pipeline\n        call: google-cloud-deploy.createdeliverypipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}\n      name: getdeliverypipeline\n      operations:\n      - method: GET\n        name: getdeliverypipeline\n        description: Google Cloud Deploy Get a delivery pipeline\n        call: google-cloud-deploy.getdeliverypipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}\n      name: updatedeliverypipeline\n      operations:\n      - method: PATCH\n        name: updatedeliverypipeline\n        description: Google Cloud Deploy Update a delivery pipeline\n        call: google-cloud-deploy.updatedeliverypipeline\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}\n      name: deletedeliverypipeline\n      operations:\n      - method: DELETE\n        name: deletedeliverypipeline\n        description: Google Cloud Deploy Delete a delivery pipeline\n        call: google-cloud-deploy.deletedeliverypipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/targets\n      name: listtargets\n      operations:\n      - method: GET\n        name: listtargets\n        description: Google Cloud Deploy List targets\n        call: google-cloud-deploy.listtargets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/targets\n      name: createtarget\n      operations:\n      - method: POST\n        name: createtarget\n        description: Google Cloud\
  \ Deploy Create a target\n        call: google-cloud-deploy.createtarget\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}/releases\n      name: listreleases\n      operations:\n      - method: GET\n        name: listreleases\n        description: Google Cloud Deploy List releases\n        call: google-cloud-deploy.listreleases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}/releases\n      name: createrelease\n      operations:\n      - method: POST\n        name: createrelease\n        description: Google Cloud Deploy Create a release\n        call: google-cloud-deploy.createrelease\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}/releases/{releaseId}/rollouts\n\
  \      name: listrollouts\n      operations:\n      - method: GET\n        name: listrollouts\n        description: Google Cloud Deploy List rollouts\n        call: google-cloud-deploy.listrollouts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}/releases/{releaseId}/rollouts\n      name: createrollout\n      operations:\n      - method: POST\n        name: createrollout\n        description: Google Cloud Deploy Create a rollout\n        call: google-cloud-deploy.createrollout\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/deliveryPipelines/{pipelineId}/releases/{releaseId}/rollouts/{rolloutId}:approve\n      name: approverollout\n      operations:\n      - method: POST\n        name: approverollout\n        description: Google Cloud Deploy Approve a rollout\n        call: google-cloud-deploy.approverollout\n\
  \        with:\n          rolloutId: rest.rolloutId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-deploy-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Deploy API for AI agent use.\n    tools:\n    - name: listdeliverypipelines\n      description: Google Cloud Deploy List delivery pipelines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-deploy.listdeliverypipelines\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdeliverypipeline\n      description: Google Cloud Deploy Create a delivery pipeline\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-deploy.createdeliverypipeline\n      with:\n        deliveryPipelineId: tools.deliveryPipelineId\n      inputParameters:\n      - name: deliveryPipelineId\n\
  \        type: string\n        description: deliveryPipelineId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdeliverypipeline\n      description: Google Cloud Deploy Get a delivery pipeline\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-deploy.getdeliverypipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatedeliverypipeline\n      description: Google Cloud Deploy Update a delivery pipeline\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-deploy.updatedeliverypipeline\n      with:\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: updateMask\n        type: string\n        description: updateMask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedeliverypipeline\n      description: Google\
  \ Cloud Deploy Delete a delivery pipeline\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-deploy.deletedeliverypipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtargets\n      description: Google Cloud Deploy List targets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-deploy.listtargets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtarget\n      description: Google Cloud Deploy Create a target\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-deploy.createtarget\n      with:\n        targetId: tools.targetId\n      inputParameters:\n      - name: targetId\n        type: string\n        description: targetId\n        required: true\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: listreleases\n      description: Google Cloud Deploy List releases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-deploy.listreleases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrelease\n      description: Google Cloud Deploy Create a release\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-deploy.createrelease\n      with:\n        releaseId: tools.releaseId\n      inputParameters:\n      - name: releaseId\n        type: string\n        description: releaseId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrollouts\n      description: Google Cloud Deploy List rollouts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-deploy.listrollouts\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createrollout\n      description: Google Cloud Deploy Create a rollout\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-deploy.createrollout\n      with:\n        rolloutId: tools.rolloutId\n      inputParameters:\n      - name: rolloutId\n        type: string\n        description: rolloutId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: approverollout\n      description: Google Cloud Deploy Approve a rollout\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-deploy.approverollout\n      with:\n        rolloutId: tools.rolloutId\n      inputParameters:\n      - name: rolloutId\n        type: string\n        description: rolloutId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace:\
  \ env\n  keys:\n    GOOGLE_CLOUD_DEPLOY_TOKEN: GOOGLE_CLOUD_DEPLOY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-deploy/refs/heads/main/capabilities/google-cloud-deploy-capability.yaml
tags:
- Google
- Cloud
- Deploy
- API
tools:
- description: Google Cloud Deploy List delivery pipelines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeliverypipelines
- description: Google Cloud Deploy Create a delivery pipeline
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdeliverypipeline
- description: Google Cloud Deploy Get a delivery pipeline
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeliverypipeline
- description: Google Cloud Deploy Update a delivery pipeline
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedeliverypipeline
- description: Google Cloud Deploy Delete a delivery pipeline
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedeliverypipeline
- description: Google Cloud Deploy List targets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtargets
- description: Google Cloud Deploy Create a target
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtarget
- description: Google Cloud Deploy List releases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreleases
- description: Google Cloud Deploy Create a release
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrelease
- description: Google Cloud Deploy List rollouts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrollouts
- description: Google Cloud Deploy Create a rollout
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrollout
- description: Google Cloud Deploy Approve a rollout
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: approverollout
---
