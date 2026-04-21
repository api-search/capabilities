---
consumed_apis:
- keyspaces
description: Unified workflow capability for Amazon Keyspaces combining resource management and operations.
layout: capability
name: Amazon Keyspaces Workflow
operations: []
personas: []
provider_name: Amazon Keyspaces
provider_slug: amazon-keyspaces
search_terms:
- nosql
- database
- returns information about the table.
- unified workflow for amazon keyspaces resource management
- cassandra
- the createtable operation adds a new table to the specified keyspace.
- tables create table
- workflow
- integrates api into applications
- returns the name and the amazon resource name (arn) of a keyspace.
- keyspaces get keyspace
- creates a new keyspace.
- returns a list of tables for a specified keyspace.
- keyspaces list keyspaces
- aws
- manages resources and configurations
- tables list tables
- tables get table
- keyspaces create keyspace
- Administrator
- wide column
- amazon keyspaces
- returns a list of keyspaces.
- Developer
- managed database
slug: amazon-keyspaces-workflow
tags:
- Amazon Keyspaces
- AWS
- Workflow
tools:
- description: Creates a new keyspace.
  hints:
    idempotent: false
    readOnly: false
  name: keyspaces-create-keyspace
- description: Returns a list of keyspaces.
  hints:
    idempotent: true
    readOnly: true
  name: keyspaces-list-keyspaces
- description: Returns the name and the Amazon Resource Name (ARN) of a keyspace.
  hints:
    idempotent: true
    readOnly: true
  name: keyspaces-get-keyspace
- description: The CreateTable operation adds a new table to the specified keyspace.
  hints:
    idempotent: false
    readOnly: false
  name: tables-create-table
- description: Returns a list of tables for a specified keyspace.
  hints:
    idempotent: true
    readOnly: true
  name: tables-list-tables
- description: Returns information about the table.
  hints:
    idempotent: true
    readOnly: true
  name: tables-get-table
---
