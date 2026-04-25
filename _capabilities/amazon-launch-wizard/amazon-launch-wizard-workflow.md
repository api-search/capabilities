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
- unified workflow for amazon launch wizard resource management
- Developer
- Administrator
- aws
- workflow
- deployments list deployments
- sql server
- deployment
- manages resources and configurations
- creates a deployment for the given workload.
- amazon launch wizard
- sap
- lists the deployments that have been created.
- deployments get deployment
- returns information about the deployment.
- deployments create deployment
- enterprise applications
- integrates api into applications
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
