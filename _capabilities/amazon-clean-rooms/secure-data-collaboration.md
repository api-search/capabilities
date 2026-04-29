---
categories:
- analytics
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
- list all collaborations
- Marketing Analyst
- analysts running collaborative queries across partner datasets without data exposure
- analytics
- clean rooms
- list all protected queries run within a collaboration membership
- create a new collaboration
- manage clean rooms collaboration workspaces
- list memberships
- data collaboration
- list configured tables available for use in collaborations
- get collaboration details
- get details of a specific clean rooms collaboration by id
- start protected query
- create membership
- create a configured table
- create configured table
- get collaboration
- list all clean rooms memberships in the caller's account
- get or delete a specific collaboration
- marketing
- amazon web services
- run a protected query
- list all clean rooms collaborations the caller participates in
- list collaborations
- Data Analyst
- list configured tables
- create a configured table from an aws glue table with defined analysis rules for collaboration use
- marketing teams measuring campaign effectiveness across publisher and advertiser data
- privacy
- manage collaboration memberships
- join a collaboration
- create collaboration
- list protected queries
- join a clean rooms collaboration as a member
- privacy-preserving multi-party data analytics
- create a new secure data collaboration workspace in aws clean rooms
- execute and list protected queries
- execute a protected sql query within a clean rooms collaboration without exposing partner raw data
- aws
- end-to-end workflow for creating and operating secure multi-party data clean rooms
- manage configured tables
slug: secure-data-collaboration
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Clean Rooms Secure Data Collaboration\"\n  description: \"Workflow for establishing and operating secure multi-party data clean rooms on AWS, enabling data analysts and marketing teams to run collaborative analytics without sharing raw data.\"\n  tags:\n    - Amazon Web Services\n    - Clean Rooms\n    - Data Collaboration\n    - Privacy\n    - Analytics\n    - Marketing\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: cleanrooms\n      location: ./shared/clean-rooms.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: secure-collaboration-api\n      description: \"Unified REST API for secure multi-party data collaboration using AWS Clean Rooms.\"\n      resources:\n        - path: /v1/collaborations\n\
  \          name: collaborations\n          description: \"Manage Clean Rooms collaboration workspaces\"\n          operations:\n            - method: GET\n              name: list-collaborations\n              description: \"List all collaborations\"\n              call: \"cleanrooms.list-collaborations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-collaboration\n              description: \"Create a new collaboration\"\n              call: \"cleanrooms.create-collaboration\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/collaborations/{collaborationId}\n          name: collaboration\n          description: \"Get or delete a specific collaboration\"\n          operations:\n            - method: GET\n              name: get-collaboration\n              description: \"Get collaboration details\"\n    \
  \          call: \"cleanrooms.get-collaboration\"\n              with:\n                collaborationIdentifier: \"rest.collaborationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/memberships\n          name: memberships\n          description: \"Manage collaboration memberships\"\n          operations:\n            - method: GET\n              name: list-memberships\n              description: \"List memberships\"\n              call: \"cleanrooms.list-memberships\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-membership\n              description: \"Join a collaboration\"\n              call: \"cleanrooms.create-membership\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/memberships/{membershipId}/queries\n          name:\
  \ protected-queries\n          description: \"Execute and list protected queries\"\n          operations:\n            - method: GET\n              name: list-protected-queries\n              description: \"List protected queries\"\n              call: \"cleanrooms.list-protected-queries\"\n              with:\n                membershipIdentifier: \"rest.membershipId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: start-protected-query\n              description: \"Run a protected query\"\n              call: \"cleanrooms.start-protected-query\"\n              with:\n                membershipIdentifier: \"rest.membershipId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/configured-tables\n          name: configured-tables\n          description: \"Manage configured tables\"\n          operations:\n        \
  \    - method: GET\n              name: list-configured-tables\n              description: \"List configured tables\"\n              call: \"cleanrooms.list-configured-tables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-configured-table\n              description: \"Create a configured table\"\n              call: \"cleanrooms.create-configured-table\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: secure-collaboration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted secure data collaboration using AWS Clean Rooms.\"\n      tools:\n        - name: list-collaborations\n          description: \"List all Clean Rooms collaborations the caller participates in\"\n          hints:\n            readOnly: true\n            idempotent: true\n         \
  \ call: \"cleanrooms.list-collaborations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-collaboration\n          description: \"Create a new secure data collaboration workspace in AWS Clean Rooms\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"cleanrooms.create-collaboration\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-collaboration\n          description: \"Get details of a specific Clean Rooms collaboration by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cleanrooms.get-collaboration\"\n          with:\n            collaborationIdentifier: \"tools.collaboration_id\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n\n        - name: list-memberships\n          description: \"List all Clean Rooms memberships in the caller's account\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cleanrooms.list-memberships\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-membership\n          description: \"Join a Clean Rooms collaboration as a member\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"cleanrooms.create-membership\"\n          with:\n            collaborationIdentifier: \"tools.collaboration_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-protected-query\n          description: \"Execute a protected SQL query within a Clean Rooms collaboration without exposing partner raw data\"\n          hints:\n            readOnly: false\n            idempotent: false\n     \
  \     call: \"cleanrooms.start-protected-query\"\n          with:\n            membershipIdentifier: \"tools.membership_id\"\n            queryString: \"tools.query_string\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-protected-queries\n          description: \"List all protected queries run within a collaboration membership\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cleanrooms.list-protected-queries\"\n          with:\n            membershipIdentifier: \"tools.membership_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-configured-tables\n          description: \"List configured tables available for use in collaborations\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cleanrooms.list-configured-tables\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n\n        - name: create-configured-table\n          description: \"Create a configured table from an AWS Glue table with defined analysis rules for collaboration use\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"cleanrooms.create-configured-table\"\n          with:\n            name: \"tools.name\"\n            analysisMethod: \"DIRECT_QUERY\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-clean-rooms/refs/heads/main/capabilities/secure-data-collaboration.yaml
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
