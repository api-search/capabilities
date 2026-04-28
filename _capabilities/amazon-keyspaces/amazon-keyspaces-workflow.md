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
- keyspaces get keyspace
- keyspaces list keyspaces
- returns a list of tables for a specified keyspace.
- unified workflow for amazon keyspaces resource management
- tables get table
- returns information about the table.
- Developer
- Administrator
- database
- managed database
- cassandra
- nosql
- amazon keyspaces
- tables list tables
- returns the name and the amazon resource name (arn) of a keyspace.
- returns a list of keyspaces.
- the createtable operation adds a new table to the specified keyspace.
- integrates api into applications
- creates a new keyspace.
- aws
- workflow
- wide column
- tables create table
- manages resources and configurations
- keyspaces create keyspace
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
