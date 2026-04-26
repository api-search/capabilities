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
- privacy
- get details of a specific clean rooms collaboration by id
- get collaboration details
- join a clean rooms collaboration as a member
- create a configured table from an aws glue table with defined analysis rules for collaboration use
- analytics
- list collaborations
- create configured table
- join a collaboration
- marketing teams measuring campaign effectiveness across publisher and advertiser data
- manage collaboration memberships
- execute and list protected queries
- manage clean rooms collaboration workspaces
- aws
- execute a protected sql query within a clean rooms collaboration without exposing partner raw data
- create a new collaboration
- Marketing Analyst
- privacy-preserving multi-party data analytics
- create membership
- data collaboration
- manage configured tables
- run a protected query
- list all clean rooms memberships in the caller's account
- list protected queries
- list all clean rooms collaborations the caller participates in
- start protected query
- amazon web services
- list memberships
- clean rooms
- get or delete a specific collaboration
- marketing
- create a new secure data collaboration workspace in aws clean rooms
- create collaboration
- list all protected queries run within a collaboration membership
- list configured tables
- analysts running collaborative queries across partner datasets without data exposure
- list all collaborations
- create a configured table
- Data Analyst
- end-to-end workflow for creating and operating secure multi-party data clean rooms
- list configured tables available for use in collaborations
- get collaboration
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
