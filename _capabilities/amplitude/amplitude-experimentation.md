---
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
- amplitude evaluate variants for a user
- updateExperiment
- experiment management api listVersions
- export raw event data and manage behavioral cohorts. for data analysts.
- scim provisioning and privacy compliance. for it admins and compliance teams.
- experiment management api listExperiments
- experiment management api createFlag
- amplitude list all flags
- amplitude get an experiment
- analytics
- amplitude
- data governance
- experiment evaluation api getFlags
- amplitude get flag configurations
- amplitude create an experiment
- a/b testing
- getExperiment
- experiment management api getExperiment
- analyzes data and manages cohorts
- getFlag
- amplitude get a flag
- experiment management api updateExperiment
- manages privacy and compliance
- manage and evaluate a/b experiments and feature flags. for product managers.
- experimentation
- experiment management api createExperiment
- listFlags
- feature flags
- amplitude get a deployment
- listDeployments
- experiment management api listDeployments
- experiment evaluation api evaluateVariants
- evaluateVariants
- getFlags
- createExperiment
- createFlag
- updateFlag
- unified workflow for sending events and identifying users. for data engineers.
- listVersions
- amplitude update an experiment
- experiment evaluation api evaluateVariantsGet
- ingests and exports event data
- experiment management api updateFlag
- listExperiments
- user behavior
- manage event schemas and chart annotations. for data governance teams.
- amplitude list all experiments
- amplitude evaluate variants for a user via get
- experiment management api getDeployment
- amplitude list flag and experiment versions
- amplitude update a flag
- runs experiments and feature flags
- amplitude list all deployments
- experiment management api listFlags
- experiment management api getFlag
- evaluateVariantsGet
- amplitude create a flag
- getDeployment
- identity management
- product analytics
- privacy compliance
slug: amplitude-experimentation
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
