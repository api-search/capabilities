---
categories: []
consumed_apis:
- launch-wizard
description: Unified workflow capability for Amazon Launch Wizard combining resource management and operations.
layout: capability
name: Amazon Launch Wizard Workflow
operations: []
personas: []
provider_name: Amazon Launch Wizard
provider_slug: amazon-launch-wizard
search_terms:
- creates a deployment for the given workload.
- deployment
- amazon launch wizard
- workflow
- sap
- aws
- lists the deployments that have been created.
- Administrator
- deployments list deployments
- enterprise applications
- sql server
- manages resources and configurations
- integrates api into applications
- returns information about the deployment.
- Developer
- unified workflow for amazon launch wizard resource management
- deployments get deployment
- deployments create deployment
slug: amazon-launch-wizard-workflow
tags:
- Amazon Launch Wizard
- AWS
- Workflow
tools:
- description: Creates a deployment for the given workload.
  hints:
    idempotent: false
    readOnly: false
  name: deployments-create-deployment
- description: Lists the deployments that have been created.
  hints:
    idempotent: true
    readOnly: true
  name: deployments-list-deployments
- description: Returns information about the deployment.
  hints:
    idempotent: true
    readOnly: true
  name: deployments-get-deployment
---
