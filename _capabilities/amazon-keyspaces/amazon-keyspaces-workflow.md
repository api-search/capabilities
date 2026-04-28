---
categories: []
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
- workflow
- keyspaces list keyspaces
- nosql
- wide column
- amazon keyspaces
- keyspaces create keyspace
- returns the name and the amazon resource name (arn) of a keyspace.
- returns information about the table.
- unified workflow for amazon keyspaces resource management
- aws
- Administrator
- managed database
- tables list tables
- creates a new keyspace.
- returns a list of keyspaces.
- tables create table
- database
- the createtable operation adds a new table to the specified keyspace.
- Developer
- tables get table
- cassandra
- manages resources and configurations
- integrates api into applications
- keyspaces get keyspace
- returns a list of tables for a specified keyspace.
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
