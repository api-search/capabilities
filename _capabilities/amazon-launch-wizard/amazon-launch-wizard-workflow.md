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
- integrates api into applications
- deployments list deployments
- deployments create deployment
- deployment
- aws
- workflow
- unified workflow for amazon launch wizard resource management
- lists the deployments that have been created.
- sql server
- returns information about the deployment.
- enterprise applications
- Developer
- deployments get deployment
- creates a deployment for the given workload.
- manages resources and configurations
- sap
- amazon launch wizard
- Administrator
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
