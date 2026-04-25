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
- getFlags
- experiment management api createFlag
- experiment management api listDeployments
- experiment management api getFlag
- analyzes data and manages cohorts
- analytics
- experimentation
- amplitude get flag configurations
- experiment management api updateExperiment
- updateFlag
- amplitude create a flag
- amplitude update a flag
- runs experiments and feature flags
- getExperiment
- data governance
- getDeployment
- amplitude evaluate variants for a user via get
- experiment management api createExperiment
- evaluateVariantsGet
- manages privacy and compliance
- getFlag
- createExperiment
- amplitude get an experiment
- listExperiments
- evaluateVariants
- amplitude list all flags
- amplitude
- listDeployments
- amplitude list all deployments
- listFlags
- amplitude list flag and experiment versions
- experiment management api getDeployment
- manage and evaluate a/b experiments and feature flags. for product managers.
- manage event schemas and chart annotations. for data governance teams.
- product analytics
- experiment management api updateFlag
- scim provisioning and privacy compliance. for it admins and compliance teams.
- ingests and exports event data
- experiment evaluation api evaluateVariantsGet
- experiment management api listVersions
- amplitude list all experiments
- amplitude update an experiment
- experiment evaluation api getFlags
- experiment management api listExperiments
- feature flags
- export raw event data and manage behavioral cohorts. for data analysts.
- identity management
- user behavior
- updateExperiment
- privacy compliance
- unified workflow for sending events and identifying users. for data engineers.
- a/b testing
- createFlag
- experiment management api getExperiment
- amplitude get a deployment
- amplitude get a flag
- amplitude evaluate variants for a user
- experiment evaluation api evaluateVariants
- listVersions
- amplitude create an experiment
- experiment management api listFlags
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
