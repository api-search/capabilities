---
categories: []
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
- mainframe
- cobol
- batch processing
- create a new mainframe modernization application on aws
- creation and management of modernized mainframe applications
- environment provisioning for running modernized applications
- get details and status of a modernization application
- start batch job
- batch jobs
- create a runtime environment
- list modernization applications
- get application details
- create a runtime environment for modernized mainframe applications
- list batch jobs
- list batch job execution history for an application
- list environments
- runtime environments
- workflow for managing mainframe application modernization, environments, and batch jobs
- manages runtime environments and deployment infrastructure for modernized mainframe applications
- start a batch job
- list runtime environments
- modernization applications
- start a batch job execution for a modernized mainframe application
- list applications
- batch job executions
- develops and deploys modernized cobol/mainframe applications and manages batch job execution
- execution of batch jobs migrated from mainframe
- create application
- create environment
- migration
- create modernization application
- create runtime environment
- list batch job executions
- Mainframe Developer
- aws
- modernization
- create a modernization application
- list all runtime environments available for deployment
- amazon
- list all mainframe applications being modernized
- Platform Engineer
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
