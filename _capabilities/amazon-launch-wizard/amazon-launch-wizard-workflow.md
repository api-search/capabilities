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
- manages resources and configurations
- deployment
- amazon launch wizard
- deployments list deployments
- deployments get deployment
- integrates api into applications
- enterprise applications
- sql server
- lists the deployments that have been created.
- Developer
- Administrator
- sap
- creates a deployment for the given workload.
- aws
- unified workflow for amazon launch wizard resource management
- deployments create deployment
- returns information about the deployment.
- workflow
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
