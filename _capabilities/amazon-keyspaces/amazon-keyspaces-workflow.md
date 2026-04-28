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
- returns information about the table.
- returns a list of tables for a specified keyspace.
- workflow
- keyspaces list keyspaces
- unified workflow for amazon keyspaces resource management
- the createtable operation adds a new table to the specified keyspace.
- keyspaces get keyspace
- Administrator
- tables create table
- amazon keyspaces
- keyspaces create keyspace
- tables list tables
- cassandra
- creates a new keyspace.
- wide column
- manages resources and configurations
- returns the name and the amazon resource name (arn) of a keyspace.
- Developer
- returns a list of keyspaces.
- nosql
- tables get table
- database
- aws
- managed database
- integrates api into applications
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
