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
- sap
- deployment
- aws
- Developer
- workflow
- amazon launch wizard
- lists the deployments that have been created.
- deployments create deployment
- deployments get deployment
- manages resources and configurations
- enterprise applications
- returns information about the deployment.
- Administrator
- creates a deployment for the given workload.
- unified workflow for amazon launch wizard resource management
- deployments list deployments
- sql server
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
