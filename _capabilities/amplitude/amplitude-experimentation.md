---
categories: []
consumed_apis: []
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
- amplitude list flag and experiment versions
- analytics
- experiment management api createFlag
- feature flags
- evaluateVariantsGet
- updateExperiment
- amplitude get a flag
- unified workflow for sending events and identifying users. for data engineers.
- updateFlag
- amplitude create an experiment
- experimentation
- amplitude create a flag
- amplitude update an experiment
- manage event schemas and chart annotations. for data governance teams.
- runs experiments and feature flags
- manages privacy and compliance
- ingests and exports event data
- identity management
- experiment management api listFlags
- product analytics
- getExperiment
- analyzes data and manages cohorts
- experiment management api getFlag
- privacy compliance
- evaluateVariants
- getDeployment
- listExperiments
- amplitude
- experiment management api updateFlag
- amplitude evaluate variants for a user via get
- listDeployments
- experiment management api listExperiments
- amplitude list all experiments
- experiment management api updateExperiment
- manage and evaluate a/b experiments and feature flags. for product managers.
- scim provisioning and privacy compliance. for it admins and compliance teams.
- amplitude update a flag
- experiment evaluation api getFlags
- createFlag
- amplitude evaluate variants for a user
- listVersions
- amplitude list all flags
- getFlag
- amplitude get an experiment
- amplitude get a deployment
- a/b testing
- experiment evaluation api evaluateVariantsGet
- experiment management api listVersions
- getFlags
- experiment evaluation api evaluateVariants
- experiment management api createExperiment
- listFlags
- createExperiment
- experiment management api listDeployments
- export raw event data and manage behavioral cohorts. for data analysts.
- data governance
- experiment management api getDeployment
- user behavior
- amplitude list all deployments
- amplitude get flag configurations
- experiment management api getExperiment
slug: amplitude-experimentation
source_filename: amplitude-experimentation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amplitude Experimentation\n  description: Manage and evaluate A/B experiments and feature flags. For product managers.\n  tags:\n  - Amplitude\n  - Experimentation\n  - Feature Flags\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AMPLITUDE_API_KEY: AMPLITUDE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: experiment-evaluation-api\n    baseUri: https://api.lab.amplitude.com\n    description: The Amplitude Experiment Evaluation API retrieves variant assignment data for users through remote evaluation.\n      When called, it evaluates targeting rules and returns the assigned variant for each active experiment or feature flag.\n      The API also tracks assignment events automatically in Amplitude Analytics. It is used by server-side applications that\n      need to determine which experiment variant or feature flag value to serve to a given user in real time.\n    resources:\n\
  \    - name: evaluation\n      path: /evaluation\n      description: Evaluation operations\n      operations:\n      - name: evaluateVariantsGet\n        method: GET\n        description: Amplitude Evaluate Variants for a User via GET\n        inputParameters:\n        - name: user_id\n          in: query\n          type: string\n          required: false\n          description: The user ID to evaluate variants for.\n        - name: device_id\n          in: query\n          type: string\n          required: false\n          description: The device ID to evaluate variants for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: evaluateVariants\n        method: POST\n        description: Amplitude Evaluate Variants for a User\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flags\n\
  \      path: /flags\n      description: Flags operations\n      operations:\n      - name: getFlags\n        method: GET\n        description: Amplitude Get Flag Configurations\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AMPLITUDE_API_KEY}}'\n      placement: header\n  - type: http\n    namespace: experiment-management-api\n    baseUri: https://experiment.amplitude.com\n    description: The Amplitude Experiment Management API provides programmatic control over feature flags and experiments.\n      It supports creating, updating, activating, and archiving experiments and flags, as well as managing deployments, variants,\n      holdout groups, and mutual exclusion groups. This API enables teams to integrate experiment lifecycle management into\n      their CI/CD pipelines, automate flag rollouts,\
  \ and manage experimentation workflows without using the Amplitude UI.\n    resources:\n    - name: flags\n      path: /flags\n      description: Flags operations\n      operations:\n      - name: listFlags\n        method: GET\n        description: Amplitude List All Flags\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of flags to return.\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: A cursor for pagination returned from a previous request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createFlag\n        method: POST\n        description: Amplitude Create a Flag\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n      - name: getFlag\n        method: GET\n        description: Amplitude Get a Flag\n        inputParameters:\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateFlag\n        method: PATCH\n        description: Amplitude Update a Flag\n        inputParameters:\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: experiments\n      path: /experiments\n      description: Experiments operations\n      operations:\n      - name: listExperiments\n        method: GET\n        description: Amplitude List All Experiments\n        inputParameters:\n     \
  \   - name: limit\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of experiments to return.\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: A cursor for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createExperiment\n        method: POST\n        description: Amplitude Create an Experiment\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getExperiment\n        method: GET\n        description: Amplitude Get an Experiment\n        inputParameters:\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: updateExperiment\n        method: PATCH\n        description: Amplitude Update an Experiment\n        inputParameters:\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /deployments\n      description: Deployments operations\n      operations:\n      - name: listDeployments\n        method: GET\n        description: Amplitude List All Deployments\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getDeployment\n        method: GET\n        description: Amplitude Get a Deployment\n        inputParameters:\n        - name: id\n          in: path\n       \
  \   type: string\n          required: true\n          description: The unique identifier of the deployment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: versions\n      path: /versions\n      description: Versions operations\n      operations:\n      - name: listVersions\n        method: GET\n        description: Amplitude List Flag and Experiment Versions\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of versions to return.\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: A cursor for pagination.\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: The start date for filtering versions.\n        - name: end\n          in: query\n          type:\
  \ string\n          required: false\n          description: The end date for filtering versions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    authentication:\n      type: bearer\n      token: '{{AMPLITUDE_API_KEY}}'\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: amplitude-experimentation-api\n    description: REST API for Amplitude Experimentation\n    resources:\n    - path: /v1/evaluation\n      name: evaluation\n      operations:\n      - method: GET\n        name: evaluateVariantsGet\n        description: Amplitude Evaluate Variants for a User via GET\n        call: experiment-evaluation-api.evaluateVariantsGet\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/evaluation\n      name: evaluation\n      operations:\n      - method: POST\n        name: evaluateVariants\n        description: Amplitude Evaluate Variants for a User\n\
  \        call: experiment-evaluation-api.evaluateVariants\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flags\n      name: flags\n      operations:\n      - method: GET\n        name: getFlags\n        description: Amplitude Get Flag Configurations\n        call: experiment-evaluation-api.getFlags\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flags\n      name: flags\n      operations:\n      - method: GET\n        name: listFlags\n        description: Amplitude List All Flags\n        call: experiment-management-api.listFlags\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flags\n      name: flags\n      operations:\n      - method: POST\n        name: createFlag\n        description: Amplitude Create a Flag\n        call: experiment-management-api.createFlag\n        with: {}\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/flags\n      name: flags\n      operations:\n      - method: GET\n        name: getFlag\n        description: Amplitude Get a Flag\n        call: experiment-management-api.getFlag\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flags\n      name: flags\n      operations:\n      - method: PATCH\n        name: updateFlag\n        description: Amplitude Update a Flag\n        call: experiment-management-api.updateFlag\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/experiments\n      name: experiments\n      operations:\n      - method: GET\n        name: listExperiments\n        description: Amplitude List All Experiments\n        call: experiment-management-api.listExperiments\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/experiments\n      name:\
  \ experiments\n      operations:\n      - method: POST\n        name: createExperiment\n        description: Amplitude Create an Experiment\n        call: experiment-management-api.createExperiment\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/experiments\n      name: experiments\n      operations:\n      - method: GET\n        name: getExperiment\n        description: Amplitude Get an Experiment\n        call: experiment-management-api.getExperiment\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/experiments\n      name: experiments\n      operations:\n      - method: PATCH\n        name: updateExperiment\n        description: Amplitude Update an Experiment\n        call: experiment-management-api.updateExperiment\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments\n      name: deployments\n   \
  \   operations:\n      - method: GET\n        name: listDeployments\n        description: Amplitude List All Deployments\n        call: experiment-management-api.listDeployments\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments\n      name: deployments\n      operations:\n      - method: GET\n        name: getDeployment\n        description: Amplitude Get a Deployment\n        call: experiment-management-api.getDeployment\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/versions\n      name: versions\n      operations:\n      - method: GET\n        name: listVersions\n        description: Amplitude List Flag and Experiment Versions\n        call: experiment-management-api.listVersions\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: amplitude-experimentation-mcp\n    transport:\
  \ http\n    description: MCP for Amplitude Experimentation\n    tools:\n    - name: experiment-evaluation-api-evaluateVariantsGet\n      description: Amplitude Evaluate Variants for a User via GET\n      hints:\n        readOnly: true\n      call: experiment-evaluation-api.evaluateVariantsGet\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-evaluation-api-evaluateVariants\n      description: Amplitude Evaluate Variants for a User\n      hints:\n        readOnly: false\n      call: experiment-evaluation-api.evaluateVariants\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-evaluation-api-getFlags\n      description: Amplitude Get Flag Configurations\n      hints:\n        readOnly: true\n      call: experiment-evaluation-api.getFlags\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-listFlags\n     \
  \ description: Amplitude List All Flags\n      hints:\n        readOnly: true\n      call: experiment-management-api.listFlags\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-createFlag\n      description: Amplitude Create a Flag\n      hints:\n        readOnly: false\n      call: experiment-management-api.createFlag\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-getFlag\n      description: Amplitude Get a Flag\n      hints:\n        readOnly: true\n      call: experiment-management-api.getFlag\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-updateFlag\n      description: Amplitude Update a Flag\n      hints:\n        readOnly: false\n      call: experiment-management-api.updateFlag\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: experiment-management-api-listExperiments\n      description: Amplitude List All Experiments\n      hints:\n        readOnly: true\n      call: experiment-management-api.listExperiments\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-createExperiment\n      description: Amplitude Create an Experiment\n      hints:\n        readOnly: false\n      call: experiment-management-api.createExperiment\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-getExperiment\n      description: Amplitude Get an Experiment\n      hints:\n        readOnly: true\n      call: experiment-management-api.getExperiment\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-updateExperiment\n      description: Amplitude Update an Experiment\n      hints:\n        readOnly: false\n      call:\
  \ experiment-management-api.updateExperiment\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-listDeployments\n      description: Amplitude List All Deployments\n      hints:\n        readOnly: true\n      call: experiment-management-api.listDeployments\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-getDeployment\n      description: Amplitude Get a Deployment\n      hints:\n        readOnly: true\n      call: experiment-management-api.getDeployment\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: experiment-management-api-listVersions\n      description: Amplitude List Flag and Experiment Versions\n      hints:\n        readOnly: true\n      call: experiment-management-api.listVersions\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
