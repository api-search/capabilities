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
- s3
- unified workflow for amazon lake formation resource management
- data governance
- Developer
- Administrator
- resources list resources
- analytics
- registers an amazon s3 path as a data lake location managed by lake formation.
- resources describe resource
- access control
- amazon lake formation
- resources register resource
- integrates api into applications
- retrieves the current data access role for the given resource registered in lake formation.
- aws
- workflow
- lists the resources registered as managed by lake formation.
- manages resources and configurations
- data lake
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
