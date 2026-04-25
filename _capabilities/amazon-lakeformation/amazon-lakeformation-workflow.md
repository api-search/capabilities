---
consumed_apis:
- lakeformation
description: Unified workflow capability for AWS Lake Formation combining resource management and operations.
layout: capability
name: AWS Lake Formation Workflow
operations: []
personas: []
provider_name: AWS Lake Formation
provider_slug: amazon-lakeformation
search_terms:
- Developer
- Administrator
- aws
- workflow
- creates a new database in the data catalog.
- databases create database
- retrieves the definition of a specified database.
- databases get database
- analytics
- lists all the registered databases in the data catalog.
- aws lake formation
- data lake
- governance
- manages resources and configurations
- databases list databases
- unified workflow for aws lake formation resource management
- integrates api into applications
slug: amazon-lakeformation-workflow
tags:
- AWS Lake Formation
- AWS
- Workflow
tools:
- description: Creates a new database in the Data Catalog.
  hints:
    idempotent: false
    readOnly: false
  name: databases-create-database
- description: Retrieves the definition of a specified database.
  hints:
    idempotent: true
    readOnly: true
  name: databases-get-database
- description: Lists all the registered databases in the Data Catalog.
  hints:
    idempotent: true
    readOnly: true
  name: databases-list-databases
---
