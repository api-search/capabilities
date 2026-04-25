---
consumed_apis:
- lake-formation
description: Unified workflow capability for Amazon Lake Formation combining resource management and operations.
layout: capability
name: Amazon Lake Formation Workflow
operations: []
personas: []
provider_name: Amazon Lake Formation
provider_slug: amazon-lake-formation
search_terms:
- Administrator
- resources describe resource
- access control
- manages resources and configurations
- integrates api into applications
- s3
- lists the resources registered as managed by lake formation.
- amazon lake formation
- resources list resources
- registers an amazon s3 path as a data lake location managed by lake formation.
- workflow
- retrieves the current data access role for the given resource registered in lake formation.
- data governance
- data lake
- unified workflow for amazon lake formation resource management
- resources register resource
- Developer
- aws
- analytics
slug: amazon-lake-formation-workflow
tags:
- Amazon Lake Formation
- AWS
- Workflow
tools:
- description: Registers an Amazon S3 path as a data lake location managed by Lake Formation.
  hints:
    idempotent: false
    readOnly: false
  name: resources-register-resource
- description: Lists the resources registered as managed by Lake Formation.
  hints:
    idempotent: true
    readOnly: true
  name: resources-list-resources
- description: Retrieves the current data access role for the given resource registered in Lake Formation.
  hints:
    idempotent: true
    readOnly: true
  name: resources-describe-resource
---
