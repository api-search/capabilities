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
- amplitude get an experiment
- experiment management api createFlag
- createFlag
- scim provisioning and privacy compliance. for it admins and compliance teams.
- experiment management api listFlags
- amplitude create an experiment
- getFlag
- listDeployments
- amplitude list all flags
- experiment management api updateExperiment
- listFlags
- createExperiment
- runs experiments and feature flags
- manages privacy and compliance
- amplitude list flag and experiment versions
- listExperiments
- amplitude get a flag
- experiment management api listExperiments
- updateFlag
- amplitude get a deployment
- ingests and exports event data
- getExperiment
- export raw event data and manage behavioral cohorts. for data analysts.
- amplitude evaluate variants for a user via get
- getFlags
- data governance
- evaluateVariantsGet
- amplitude
- amplitude list all deployments
- experiment evaluation api evaluateVariantsGet
- experiment management api listDeployments
- manage event schemas and chart annotations. for data governance teams.
- feature flags
- experiment management api getExperiment
- analyzes data and manages cohorts
- experiment management api updateFlag
- amplitude get flag configurations
- evaluateVariants
- updateExperiment
- identity management
- privacy compliance
- amplitude list all experiments
- product analytics
- amplitude update an experiment
- experiment management api createExperiment
- amplitude create a flag
- experiment management api getFlag
- getDeployment
- analytics
- experimentation
- amplitude update a flag
- unified workflow for sending events and identifying users. for data engineers.
- a/b testing
- listVersions
- experiment management api listVersions
- manage and evaluate a/b experiments and feature flags. for product managers.
- amplitude evaluate variants for a user
- experiment evaluation api evaluateVariants
- experiment evaluation api getFlags
- user behavior
- experiment management api getDeployment
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
