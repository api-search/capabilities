---
categories: []
consumed_apis:
- experiment-evaluation-api
- experiment-management-api
description: Manage and evaluate A/B experiments and feature flags. For product managers.
layout: capability
name: Amplitude Experimentation
operations:
- description: Amplitude Evaluate Variants for a User via GET
  method: GET
  name: evaluateVariantsGet
  path: /v1/evaluation
- description: Amplitude Evaluate Variants for a User
  method: POST
  name: evaluateVariants
  path: /v1/evaluation
- description: Amplitude Get Flag Configurations
  method: GET
  name: getFlags
  path: /v1/flags
- description: Amplitude List All Flags
  method: GET
  name: listFlags
  path: /v1/flags
- description: Amplitude Create a Flag
  method: POST
  name: createFlag
  path: /v1/flags
- description: Amplitude Get a Flag
  method: GET
  name: getFlag
  path: /v1/flags
- description: Amplitude Update a Flag
  method: PATCH
  name: updateFlag
  path: /v1/flags
- description: Amplitude List All Experiments
  method: GET
  name: listExperiments
  path: /v1/experiments
- description: Amplitude Create an Experiment
  method: POST
  name: createExperiment
  path: /v1/experiments
- description: Amplitude Get an Experiment
  method: GET
  name: getExperiment
  path: /v1/experiments
- description: Amplitude Update an Experiment
  method: PATCH
  name: updateExperiment
  path: /v1/experiments
- description: Amplitude List All Deployments
  method: GET
  name: listDeployments
  path: /v1/deployments
- description: Amplitude Get a Deployment
  method: GET
  name: getDeployment
  path: /v1/deployments
- description: Amplitude List Flag and Experiment Versions
  method: GET
  name: listVersions
  path: /v1/versions
personas: []
provider_name: Amplitude
provider_slug: amplitude
search_terms:
- amplitude evaluate variants for a user via get
- experiment management api createExperiment
- createFlag
- createExperiment
- amplitude get a deployment
- experiment management api getFlag
- experiment evaluation api getFlags
- experiment management api listExperiments
- a/b testing
- experiment management api updateFlag
- updateExperiment
- feature flags
- getFlags
- amplitude update an experiment
- data governance
- experiment management api listDeployments
- experiment evaluation api evaluateVariants
- user behavior
- experimentation
- getFlag
- experiment management api createFlag
- getDeployment
- amplitude list all deployments
- listFlags
- experiment management api getDeployment
- updateFlag
- amplitude create an experiment
- product analytics
- manages privacy and compliance
- amplitude get a flag
- evaluateVariants
- scim provisioning and privacy compliance. for it admins and compliance teams.
- amplitude update a flag
- runs experiments and feature flags
- experiment management api getExperiment
- amplitude get flag configurations
- manage and evaluate a/b experiments and feature flags. for product managers.
- amplitude create a flag
- experiment management api listFlags
- experiment management api listVersions
- amplitude list flag and experiment versions
- experiment management api updateExperiment
- analyzes data and manages cohorts
- privacy compliance
- analytics
- export raw event data and manage behavioral cohorts. for data analysts.
- experiment evaluation api evaluateVariantsGet
- manage event schemas and chart annotations. for data governance teams.
- listExperiments
- identity management
- amplitude evaluate variants for a user
- evaluateVariantsGet
- unified workflow for sending events and identifying users. for data engineers.
- amplitude get an experiment
- getExperiment
- amplitude list all flags
- amplitude list all experiments
- listVersions
- listDeployments
- amplitude
- ingests and exports event data
slug: amplitude-experimentation
source_filename: amplitude-experimentation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amplitude Experimentation\n  description: Manage and evaluate A/B experiments and feature flags. For product managers.\n  tags:\n  - Amplitude\n  - Experimentation\n  - Feature Flags\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AMPLITUDE_API_KEY: AMPLITUDE_API_KEY\ncapability:\n  consumes:\n  - import: experiment-evaluation-api\n    location: ./shared/experiment-evaluation-api.yaml\n  - import: experiment-management-api\n    location: ./shared/experiment-management-api.yaml\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: amplitude-experimentation-api\n    description: REST API for Amplitude Experimentation\n    resources:\n    - path: /v1/evaluation\n      name: evaluation\n      operations:\n      - method: GET\n        name: evaluateVariantsGet\n        description: Amplitude Evaluate Variants for a User via GET\n        call: experiment-evaluation-api.evaluateVariantsGet\n  \
  \      with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/evaluation\n      name: evaluation\n      operations:\n      - method: POST\n        name: evaluateVariants\n        description: Amplitude Evaluate Variants for a User\n        call: experiment-evaluation-api.evaluateVariants\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flags\n      name: flags\n      operations:\n      - method: GET\n        name: getFlags\n        description: Amplitude Get Flag Configurations\n        call: experiment-evaluation-api.getFlags\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flags\n      name: flags\n      operations:\n      - method: GET\n        name: listFlags\n        description: Amplitude List All Flags\n        call: experiment-management-api.listFlags\n        with: {}\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/flags\n      name: flags\n      operations:\n      - method: POST\n        name: createFlag\n        description: Amplitude Create a Flag\n        call: experiment-management-api.createFlag\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flags\n      name: flags\n      operations:\n      - method: GET\n        name: getFlag\n        description: Amplitude Get a Flag\n        call: experiment-management-api.getFlag\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flags\n      name: flags\n      operations:\n      - method: PATCH\n        name: updateFlag\n        description: Amplitude Update a Flag\n        call: experiment-management-api.updateFlag\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/experiments\n      name: experiments\n      operations:\n      - method:\
  \ GET\n        name: listExperiments\n        description: Amplitude List All Experiments\n        call: experiment-management-api.listExperiments\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/experiments\n      name: experiments\n      operations:\n      - method: POST\n        name: createExperiment\n        description: Amplitude Create an Experiment\n        call: experiment-management-api.createExperiment\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/experiments\n      name: experiments\n      operations:\n      - method: GET\n        name: getExperiment\n        description: Amplitude Get an Experiment\n        call: experiment-management-api.getExperiment\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/experiments\n      name: experiments\n      operations:\n      - method: PATCH\n        name:\
  \ updateExperiment\n        description: Amplitude Update an Experiment\n        call: experiment-management-api.updateExperiment\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments\n      name: deployments\n      operations:\n      - method: GET\n        name: listDeployments\n        description: Amplitude List All Deployments\n        call: experiment-management-api.listDeployments\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments\n      name: deployments\n      operations:\n      - method: GET\n        name: getDeployment\n        description: Amplitude Get a Deployment\n        call: experiment-management-api.getDeployment\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/versions\n      name: versions\n      operations:\n      - method: GET\n        name: listVersions\n        description:\
  \ Amplitude List Flag and Experiment Versions\n        call: experiment-management-api.listVersions\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: amplitude-experimentation-mcp\n    transport: http\n    description: MCP for Amplitude Experimentation\n    tools:\n    - name: experiment-evaluation-api-evaluateVariantsGet\n      description: Amplitude Evaluate Variants for a User via GET\n      hints:\n        readOnly: true\n      call: experiment-evaluation-api.evaluateVariantsGet\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-evaluation-api-evaluateVariants\n      description: Amplitude Evaluate Variants for a User\n      hints:\n        readOnly: false\n      call: experiment-evaluation-api.evaluateVariants\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-evaluation-api-getFlags\n\
  \      description: Amplitude Get Flag Configurations\n      hints:\n        readOnly: true\n      call: experiment-evaluation-api.getFlags\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-listFlags\n      description: Amplitude List All Flags\n      hints:\n        readOnly: true\n      call: experiment-management-api.listFlags\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-createFlag\n      description: Amplitude Create a Flag\n      hints:\n        readOnly: false\n      call: experiment-management-api.createFlag\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-getFlag\n      description: Amplitude Get a Flag\n      hints:\n        readOnly: true\n      call: experiment-management-api.getFlag\n      with: {}\n      outputParameters:\n      - type: object\n      \
  \  mapping: $.\n    - name: experiment-management-api-updateFlag\n      description: Amplitude Update a Flag\n      hints:\n        readOnly: false\n      call: experiment-management-api.updateFlag\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-listExperiments\n      description: Amplitude List All Experiments\n      hints:\n        readOnly: true\n      call: experiment-management-api.listExperiments\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-createExperiment\n      description: Amplitude Create an Experiment\n      hints:\n        readOnly: false\n      call: experiment-management-api.createExperiment\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-getExperiment\n      description: Amplitude Get an Experiment\n      hints:\n        readOnly: true\n      call:\
  \ experiment-management-api.getExperiment\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-updateExperiment\n      description: Amplitude Update an Experiment\n      hints:\n        readOnly: false\n      call: experiment-management-api.updateExperiment\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-listDeployments\n      description: Amplitude List All Deployments\n      hints:\n        readOnly: true\n      call: experiment-management-api.listDeployments\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-getDeployment\n      description: Amplitude Get a Deployment\n      hints:\n        readOnly: true\n      call: experiment-management-api.getDeployment\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-listVersions\n\
  \      description: Amplitude List Flag and Experiment Versions\n      hints:\n        readOnly: true\n      call: experiment-management-api.listVersions\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amplitude/refs/heads/main/capabilities/amplitude-experimentation.yaml
tags:
- Amplitude
- Experimentation
- Feature Flags
tools:
- description: Amplitude Evaluate Variants for a User via GET
  hints:
    readOnly: true
  name: experiment-evaluation-api-evaluateVariantsGet
- description: Amplitude Evaluate Variants for a User
  hints:
    readOnly: false
  name: experiment-evaluation-api-evaluateVariants
- description: Amplitude Get Flag Configurations
  hints:
    readOnly: true
  name: experiment-evaluation-api-getFlags
- description: Amplitude List All Flags
  hints:
    readOnly: true
  name: experiment-management-api-listFlags
- description: Amplitude Create a Flag
  hints:
    readOnly: false
  name: experiment-management-api-createFlag
- description: Amplitude Get a Flag
  hints:
    readOnly: true
  name: experiment-management-api-getFlag
- description: Amplitude Update a Flag
  hints:
    readOnly: false
  name: experiment-management-api-updateFlag
- description: Amplitude List All Experiments
  hints:
    readOnly: true
  name: experiment-management-api-listExperiments
- description: Amplitude Create an Experiment
  hints:
    readOnly: false
  name: experiment-management-api-createExperiment
- description: Amplitude Get an Experiment
  hints:
    readOnly: true
  name: experiment-management-api-getExperiment
- description: Amplitude Update an Experiment
  hints:
    readOnly: false
  name: experiment-management-api-updateExperiment
- description: Amplitude List All Deployments
  hints:
    readOnly: true
  name: experiment-management-api-listDeployments
- description: Amplitude Get a Deployment
  hints:
    readOnly: true
  name: experiment-management-api-getDeployment
- description: Amplitude List Flag and Experiment Versions
  hints:
    readOnly: true
  name: experiment-management-api-listVersions
---
