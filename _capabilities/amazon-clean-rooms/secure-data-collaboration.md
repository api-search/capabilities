---
consumed_apis:
- cleanrooms
description: Workflow for establishing and operating secure multi-party data clean rooms on AWS, enabling data analysts and marketing teams to run collaborative analytics without sharing raw data.
layout: capability
name: Amazon Clean Rooms Secure Data Collaboration
operations:
- description: List all collaborations
  method: GET
  name: list-collaborations
  path: /v1/collaborations
- description: Create a new collaboration
  method: POST
  name: create-collaboration
  path: /v1/collaborations
- description: Get collaboration details
  method: GET
  name: get-collaboration
  path: /v1/collaborations/{collaborationId}
- description: List memberships
  method: GET
  name: list-memberships
  path: /v1/memberships
- description: Join a collaboration
  method: POST
  name: create-membership
  path: /v1/memberships
- description: List protected queries
  method: GET
  name: list-protected-queries
  path: /v1/memberships/{membershipId}/queries
- description: Run a protected query
  method: POST
  name: start-protected-query
  path: /v1/memberships/{membershipId}/queries
- description: List configured tables
  method: GET
  name: list-configured-tables
  path: /v1/configured-tables
- description: Create a configured table
  method: POST
  name: create-configured-table
  path: /v1/configured-tables
personas: []
provider_name: Amazon Clean Rooms
provider_slug: amazon-clean-rooms
search_terms:
- create membership
- analysts running collaborative queries across partner datasets without data exposure
- privacy-preserving multi-party data analytics
- list configured tables available for use in collaborations
- analytics
- amazon web services
- manage collaboration memberships
- start protected query
- list memberships
- list all clean rooms memberships in the caller's account
- list all protected queries run within a collaboration membership
- manage configured tables
- list protected queries
- aws
- privacy
- create a new collaboration
- get collaboration
- execute and list protected queries
- get details of a specific clean rooms collaboration by id
- data collaboration
- manage clean rooms collaboration workspaces
- get or delete a specific collaboration
- get collaboration details
- run a protected query
- create a configured table
- Data Analyst
- create configured table
- Marketing Analyst
- list collaborations
- create collaboration
- create a configured table from an aws glue table with defined analysis rules for collaboration use
- list configured tables
- clean rooms
- list all collaborations
- join a clean rooms collaboration as a member
- join a collaboration
- execute a protected sql query within a clean rooms collaboration without exposing partner raw data
- create a new secure data collaboration workspace in aws clean rooms
- marketing
- list all clean rooms collaborations the caller participates in
- marketing teams measuring campaign effectiveness across publisher and advertiser data
- end-to-end workflow for creating and operating secure multi-party data clean rooms
slug: secure-data-collaboration
tags:
- Amazon Web Services
- Clean Rooms
- Data Collaboration
- Privacy
- Analytics
- Marketing
tools:
- description: List all Clean Rooms collaborations the caller participates in
  hints:
    idempotent: true
    readOnly: true
  name: list-collaborations
- description: Create a new secure data collaboration workspace in AWS Clean Rooms
  hints:
    idempotent: false
    readOnly: false
  name: create-collaboration
- description: Get details of a specific Clean Rooms collaboration by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-collaboration
- description: List all Clean Rooms memberships in the caller's account
  hints:
    idempotent: true
    readOnly: true
  name: list-memberships
- description: Join a Clean Rooms collaboration as a member
  hints:
    idempotent: false
    readOnly: false
  name: create-membership
- description: Execute a protected SQL query within a Clean Rooms collaboration without exposing partner raw data
  hints:
    idempotent: false
    readOnly: false
  name: start-protected-query
- description: List all protected queries run within a collaboration membership
  hints:
    idempotent: true
    readOnly: true
  name: list-protected-queries
- description: List configured tables available for use in collaborations
  hints:
    idempotent: true
    readOnly: true
  name: list-configured-tables
- description: Create a configured table from an AWS Glue table with defined analysis rules for collaboration use
  hints:
    idempotent: false
    readOnly: false
  name: create-configured-table
---
