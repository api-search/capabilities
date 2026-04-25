---
consumed_apis:
- codepipeline
description: Unified workflow for DevOps and release engineering teams to create and manage delivery pipelines, trigger pipeline executions, monitor pipeline status, and manage pipeline artifacts using Amazon CodePipeline.
layout: capability
name: Amazon CodePipeline Release Pipeline Automation
operations: []
personas: []
provider_name: Amazon CodePipeline
provider_slug: amazon-codepipeline
search_terms:
- put approval result
- list action executions for a pipeline
- get pipeline execution
- retry stage execution
- stop pipeline execution
- delete pipeline
- start pipeline execution
- devops
- stop an in-progress pipeline execution
- retry all failed actions in a pipeline stage
- update pipeline
- start a pipeline execution
- Release Manager
- create a new delivery pipeline
- list pipeline executions
- get the current state of each stage in a pipeline
- Platform Engineer
- update the structure of a pipeline
- get details about a pipeline execution
- list pipelines in the account
- list pipeline webhooks
- ci/cd
- create pipeline
- release manager persona.
- unified workflow for devops and release engineering teams to create and manage delivery pipelines, t
- amazon
- list action executions
- list webhooks
- platform engineer persona.
- pipeline
- get the structure and details of a pipeline
- aws
- delete a pipeline
- submit approval or rejection for a manual approval action
- list pipelines
- get pipeline
- DevOps Engineer
- devops engineer persona.
- continuous delivery
- unified workflow for devops and release engineering teams to create and manage delivery pipelines, trigger pipeline executions, monitor pipeline statu
- list executions for a pipeline
- get pipeline state
- release automation
slug: amazon-codepipeline-release-pipeline
tags:
- Amazon
- AWS
- CI/CD
- Continuous Delivery
- DevOps
- Pipeline
- Release Automation
tools:
- description: List pipelines in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-pipelines
- description: Get the structure and details of a pipeline
  hints:
    openWorld: true
    readOnly: true
  name: get-pipeline
- description: Create a new delivery pipeline
  hints:
    openWorld: true
    readOnly: false
  name: create-pipeline
- description: Update the structure of a pipeline
  hints:
    openWorld: true
    readOnly: false
  name: update-pipeline
- description: Delete a pipeline
  hints:
    openWorld: true
    readOnly: false
  name: delete-pipeline
- description: Start a pipeline execution
  hints:
    openWorld: true
    readOnly: false
  name: start-pipeline-execution
- description: Stop an in-progress pipeline execution
  hints:
    openWorld: true
    readOnly: false
  name: stop-pipeline-execution
- description: Get details about a pipeline execution
  hints:
    openWorld: true
    readOnly: true
  name: get-pipeline-execution
- description: List executions for a pipeline
  hints:
    openWorld: true
    readOnly: true
  name: list-pipeline-executions
- description: Get the current state of each stage in a pipeline
  hints:
    openWorld: true
    readOnly: true
  name: get-pipeline-state
- description: List action executions for a pipeline
  hints:
    openWorld: true
    readOnly: true
  name: list-action-executions
- description: Submit approval or rejection for a manual approval action
  hints:
    openWorld: true
    readOnly: false
  name: put-approval-result
- description: Retry all failed actions in a pipeline stage
  hints:
    openWorld: true
    readOnly: false
  name: retry-stage-execution
- description: List pipeline webhooks
  hints:
    openWorld: true
    readOnly: true
  name: list-webhooks
---
