---
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
- aws
- returns information about the deployment.
- workflow
- manages resources and configurations
- lists the deployments that have been created.
- Developer
- sap
- sql server
- deployments create deployment
- deployments list deployments
- deployment
- Administrator
- enterprise applications
- amazon launch wizard
- deployments get deployment
- integrates api into applications
- unified workflow for amazon launch wizard resource management
- creates a deployment for the given workload.
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
