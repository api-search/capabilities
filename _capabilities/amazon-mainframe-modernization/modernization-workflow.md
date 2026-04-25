---
consumed_apis:
- mainframe-modernization
description: Workflow capability for platform and migration teams to manage mainframe application modernization, including application lifecycle management, environment configuration, and batch job execution on AWS.
layout: capability
name: Amazon Mainframe Modernization - Migration Workflow
operations:
- description: Create a modernization application
  method: POST
  name: create-application
  path: /v1/applications
- description: List modernization applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: Create a runtime environment
  method: POST
  name: create-environment
  path: /v1/environments
- description: List runtime environments
  method: GET
  name: list-environments
  path: /v1/environments
- description: Start a batch job
  method: POST
  name: start-batch-job
  path: /v1/applications/{id}/batch-jobs
- description: List batch jobs
  method: GET
  name: list-batch-jobs
  path: /v1/applications/{id}/batch-jobs
personas: []
provider_name: Amazon Mainframe Modernization
provider_slug: amazon-mainframe-modernization
search_terms:
- create modernization application
- execution of batch jobs migrated from mainframe
- list applications
- modernization
- list all runtime environments available for deployment
- create a runtime environment
- list batch job execution history for an application
- manages runtime environments and deployment infrastructure for modernized mainframe applications
- get application details
- list runtime environments
- develops and deploys modernized cobol/mainframe applications and manages batch job execution
- Platform Engineer
- start a batch job
- batch job executions
- list batch job executions
- environment provisioning for running modernized applications
- create a modernization application
- mainframe
- start a batch job execution for a modernized mainframe application
- get details and status of a modernization application
- list all mainframe applications being modernized
- Mainframe Developer
- create a new mainframe modernization application on aws
- migration
- workflow for managing mainframe application modernization, environments, and batch jobs
- modernization applications
- create application
- start batch job
- batch processing
- cobol
- batch jobs
- create environment
- runtime environments
- create runtime environment
- aws
- create a runtime environment for modernized mainframe applications
- creation and management of modernized mainframe applications
- amazon
- list batch jobs
- list environments
- list modernization applications
slug: modernization-workflow
tags:
- Amazon
- Mainframe
- Migration
- Modernization
- COBOL
- Batch Jobs
tools:
- description: Create a new mainframe modernization application on AWS
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-modernization-application
- description: List all mainframe applications being modernized
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-modernization-applications
- description: Get details and status of a modernization application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-application-details
- description: Create a runtime environment for modernized mainframe applications
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-runtime-environment
- description: List all runtime environments available for deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-runtime-environments
- description: Start a batch job execution for a modernized mainframe application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: start-batch-job
- description: List batch job execution history for an application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-batch-job-executions
---
