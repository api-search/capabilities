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
- amplitude update a flag
- amplitude list all deployments
- scim provisioning and privacy compliance. for it admins and compliance teams.
- experiment management api getFlag
- experiment management api getDeployment
- createFlag
- createExperiment
- amplitude update an experiment
- amplitude evaluate variants for a user via get
- updateExperiment
- listDeployments
- amplitude list flag and experiment versions
- experiment management api getExperiment
- updateFlag
- experiment management api listExperiments
- experiment management api updateExperiment
- manage event schemas and chart annotations. for data governance teams.
- listFlags
- amplitude get a deployment
- data governance
- experimentation
- getDeployment
- amplitude get a flag
- analytics
- amplitude list all experiments
- getFlags
- export raw event data and manage behavioral cohorts. for data analysts.
- amplitude get an experiment
- amplitude evaluate variants for a user
- experiment management api createExperiment
- ingests and exports event data
- amplitude get flag configurations
- experiment management api updateFlag
- unified workflow for sending events and identifying users. for data engineers.
- experiment management api listDeployments
- amplitude create a flag
- experiment management api listFlags
- analyzes data and manages cohorts
- user behavior
- amplitude list all flags
- getFlag
- experiment management api listVersions
- experiment evaluation api evaluateVariantsGet
- listVersions
- identity management
- privacy compliance
- a/b testing
- manages privacy and compliance
- runs experiments and feature flags
- listExperiments
- amplitude
- experiment management api createFlag
- evaluateVariantsGet
- product analytics
- experiment evaluation api getFlags
- amplitude create an experiment
- getExperiment
- feature flags
- experiment evaluation api evaluateVariants
- manage and evaluate a/b experiments and feature flags. for product managers.
- evaluateVariants
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
