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
- Platform Engineer
- runtime environments
- create a runtime environment
- list batch job executions
- list applications
- Mainframe Developer
- modernization applications
- cobol
- batch processing
- list runtime environments
- batch jobs
- aws
- create a modernization application
- create modernization application
- start a batch job execution for a modernized mainframe application
- start a batch job
- environment provisioning for running modernized applications
- migration
- list batch job execution history for an application
- workflow for managing mainframe application modernization, environments, and batch jobs
- batch job executions
- get details and status of a modernization application
- list modernization applications
- mainframe
- list environments
- develops and deploys modernized cobol/mainframe applications and manages batch job execution
- amazon
- create a runtime environment for modernized mainframe applications
- list all mainframe applications being modernized
- start batch job
- get application details
- list all runtime environments available for deployment
- execution of batch jobs migrated from mainframe
- create application
- create runtime environment
- modernization
- list batch jobs
- create a new mainframe modernization application on aws
- create environment
- creation and management of modernized mainframe applications
- manages runtime environments and deployment infrastructure for modernized mainframe applications
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
