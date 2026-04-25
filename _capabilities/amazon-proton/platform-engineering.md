---
consumed_apis:
- amazon-proton
description: Workflow capability for platform engineering teams using Amazon Proton to publish standardized templates and automate infrastructure provisioning for development teams. Covers template management, environment deployment, and service lifecycle management.
layout: capability
name: Amazon Proton Platform Engineering
operations:
- description: List environment templates
  method: GET
  name: list-environment-templates
  path: /v1/environment-templates
- description: Create an environment template
  method: POST
  name: create-environment-template
  path: /v1/environment-templates
- description: List deployed environments
  method: GET
  name: list-environments
  path: /v1/environments
- description: Create an environment from a template
  method: POST
  name: create-environment
  path: /v1/environments
- description: List service templates
  method: GET
  name: list-service-templates
  path: /v1/service-templates
- description: Create a service template
  method: POST
  name: create-service-template
  path: /v1/service-templates
- description: List deployed services
  method: GET
  name: list-services
  path: /v1/services
- description: Create a service from a template
  method: POST
  name: create-service
  path: /v1/services
personas: []
provider_name: Amazon Proton
provider_slug: amazon-proton
search_terms:
- list services
- deployed service management
- environment template management for platform engineers
- create a service from a template
- infrastructure as code
- list all deployed environments
- devops
- deploy a new environment from a standardized template
- create service template
- creates and manages environment and service templates for standardized deployments
- create a new standardized environment template for developers
- list environment templates for standardized infrastructure
- create an environment template
- deploy a new application service from a service template
- Platform Engineer
- list environments
- deployed environment management
- service template catalog for developers
- create service
- list deployed services
- deploys services using self-service templates provided by platform engineers
- create environment
- ci/cd
- self-service
- amazon
- serverless
- list deployed environments
- create a service template
- list service templates
- templates
- list all deployed services
- aws
- create environment template
- platform engineering template and deployment workflow
- list service templates available for developer self-service
- create an environment from a template
- Application Developer
- platform engineering
- create a new service template for standardized application deployments
- list environment templates
slug: platform-engineering
tags:
- Amazon
- AWS
- DevOps
- Platform Engineering
- Infrastructure as Code
- Self-Service
- Templates
tools:
- description: List environment templates for standardized infrastructure
  hints:
    openWorld: true
    readOnly: true
  name: list-environment-templates
- description: Create a new standardized environment template for developers
  hints:
    destructive: false
    readOnly: false
  name: create-environment-template
- description: List all deployed environments
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
- description: Deploy a new environment from a standardized template
  hints:
    destructive: false
    readOnly: false
  name: create-environment
- description: List service templates available for developer self-service
  hints:
    openWorld: true
    readOnly: true
  name: list-service-templates
- description: Create a new service template for standardized application deployments
  hints:
    destructive: false
    readOnly: false
  name: create-service-template
- description: List all deployed services
  hints:
    openWorld: true
    readOnly: true
  name: list-services
- description: Deploy a new application service from a service template
  hints:
    destructive: false
    readOnly: false
  name: create-service
---
