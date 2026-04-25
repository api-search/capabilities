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
- analytics
- Administrator
- data lake
- lists the resources registered as managed by lake formation.
- resources describe resource
- data governance
- amazon lake formation
- workflow
- registers an amazon s3 path as a data lake location managed by lake formation.
- resources register resource
- integrates api into applications
- manages resources and configurations
- access control
- aws
- resources list resources
- unified workflow for amazon lake formation resource management
- s3
- retrieves the current data access role for the given resource registered in lake formation.
- Developer
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
