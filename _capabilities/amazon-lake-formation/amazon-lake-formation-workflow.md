---
categories: []
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
- workflow
- registers an amazon s3 path as a data lake location managed by lake formation.
- amazon lake formation
- retrieves the current data access role for the given resource registered in lake formation.
- data lake
- aws
- resources register resource
- resources describe resource
- data governance
- Developer
- s3
- analytics
- access control
- lists the resources registered as managed by lake formation.
- unified workflow for amazon lake formation resource management
- resources list resources
- manages resources and configurations
- integrates api into applications
- Administrator
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
