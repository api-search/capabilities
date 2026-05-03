---
api_specs:
- filename: trino-client-api-openapi.yml
  format: yaml
  label: trino-client
  slug: trino-client
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/trino/refs/heads/main/openapi/trino-client-api-openapi.yml
categories: []
consumed_apis:
- trino-client
description: Workflow capability for submitting distributed SQL queries to Trino, monitoring query execution, retrieving results, and managing the Trino cluster. Designed for data engineers, analysts, and data platform operators who need programmatic access to Trino's big data SQL engine across data lakes and databases.
layout: capability
name: Trino SQL Analytics
operations:
- description: Submit an SQL query to Trino for distributed execution
  method: POST
  name: submit-query
  path: /v1/queries
- description: List active and recently completed queries
  method: GET
  name: list-queries
  path: /v1/queries
- description: Get the next page of results for a running query
  method: GET
  name: get-query-results
  path: /v1/queries/{queryId}/{token}
- description: Cancel a running query
  method: DELETE
  name: cancel-query
  path: /v1/queries/{queryId}/{token}
- description: Get Trino cluster version, environment, and startup state
  method: GET
  name: get-cluster-info
  path: /v1/cluster/info
- description: List all active worker nodes in the cluster
  method: GET
  name: list-nodes
  path: /v1/cluster/nodes
personas: []
provider_name: Trino
provider_slug: trino
search_terms:
- list active and recently completed queries
- list active queries
- big data
- submit sql queries and list query history
- distributed sql
- list queries
- retrieve paginated results or cancel a query
- cancel query
- analytics
- worker node listing and status
- retrieve trino cluster metadata including version, environment name, and whether the coordinator is still starting. use for health checks.
- list all active worker nodes in the trino cluster with their node ids, uris, heartbeat times, and resource utilization.
- get trino cluster version, environment, and startup state
- data engineering
- retrieve the next page of results for a running or recently completed query. follow the nexturi from a previous query response.
- list nodes
- list all active worker nodes in the cluster
- cancel a running trino query by its queryid and current token.
- mysql
- list currently running and recently completed queries on the trino cluster. filter by state (running, finished, failed) or limit the result count.
- sql
- submit an sql query to trino for distributed execution across data lakes and databases. returns initial results and a nexturi for polling more data.
- nosql
- submit query
- list cluster nodes
- queries
- get cluster info
- get the next page of results for a running query
- cancel a running query
- submit sql query
- submit an sql query to trino for distributed execution
- get query results
- trino cluster health and version information
slug: sql-analytics
source_filename: sql-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Trino SQL Analytics\"\n  description: >-\n    Workflow capability for submitting distributed SQL queries to Trino, monitoring\n    query execution, retrieving results, and managing the Trino cluster. Designed\n    for data engineers, analysts, and data platform operators who need programmatic\n    access to Trino's big data SQL engine across data lakes and databases.\n  tags:\n    - Analytics\n    - Big Data\n    - Data Engineering\n    - Distributed SQL\n    - Queries\n    - SQL\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRINO_HOST: TRINO_HOST\n      TRINO_USER: TRINO_USER\n\ncapability:\n  consumes:\n    - import: trino-client\n      location: ./shared/trino-client-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: trino-analytics-api\n      description: \"Unified REST API for submitting and managing Trino SQL queries.\"\n      resources:\n\
  \        - path: /v1/queries\n          name: queries\n          description: \"Submit SQL queries and list query history\"\n          operations:\n            - method: POST\n              name: submit-query\n              description: \"Submit an SQL query to Trino for distributed execution\"\n              call: \"trino-client.submit-statement\"\n              with:\n                sql_query: \"rest.body.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-queries\n              description: \"List active and recently completed queries\"\n              call: \"trino-client.list-queries\"\n              with:\n                state: \"rest.state\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/queries/{queryId}/{token}\n          name: query-results\n          description:\
  \ \"Retrieve paginated results or cancel a query\"\n          operations:\n            - method: GET\n              name: get-query-results\n              description: \"Get the next page of results for a running query\"\n              call: \"trino-client.get-query-results\"\n              with:\n                queryId: \"rest.queryId\"\n                token: \"rest.token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: cancel-query\n              description: \"Cancel a running query\"\n              call: \"trino-client.cancel-query\"\n              with:\n                queryId: \"rest.queryId\"\n                token: \"rest.token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cluster/info\n          name: cluster-info\n          description: \"Trino cluster health and version information\"\n        \
  \  operations:\n            - method: GET\n              name: get-cluster-info\n              description: \"Get Trino cluster version, environment, and startup state\"\n              call: \"trino-client.get-cluster-info\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cluster/nodes\n          name: nodes\n          description: \"Worker node listing and status\"\n          operations:\n            - method: GET\n              name: list-nodes\n              description: \"List all active worker nodes in the cluster\"\n              call: \"trino-client.list-nodes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: trino-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SQL analytics with Trino distributed query engine.\"\n      tools:\n        - name: submit-sql-query\n \
  \         description: >-\n            Submit an SQL query to Trino for distributed execution across data lakes\n            and databases. Returns initial results and a nextUri for polling more data.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trino-client.submit-statement\"\n          with:\n            sql_query: \"tools.sql_query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-query-results\n          description: >-\n            Retrieve the next page of results for a running or recently completed query.\n            Follow the nextUri from a previous query response.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trino-client.get-query-results\"\n          with:\n            queryId: \"tools.queryId\"\n            token: \"tools.token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n        - name: cancel-query\n          description: \"Cancel a running Trino query by its queryId and current token.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"trino-client.cancel-query\"\n          with:\n            queryId: \"tools.queryId\"\n            token: \"tools.token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-active-queries\n          description: >-\n            List currently running and recently completed queries on the Trino cluster.\n            Filter by state (RUNNING, FINISHED, FAILED) or limit the result count.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trino-client.list-queries\"\n          with:\n            state: \"tools.state\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n   \
  \     - name: get-cluster-info\n          description: >-\n            Retrieve Trino cluster metadata including version, environment name,\n            and whether the coordinator is still starting. Use for health checks.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trino-client.get-cluster-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-cluster-nodes\n          description: >-\n            List all active worker nodes in the Trino cluster with their node IDs,\n            URIs, heartbeat times, and resource utilization.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trino-client.list-nodes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trino/refs/heads/main/capabilities/sql-analytics.yaml
tags:
- Analytics
- Big Data
- Data Engineering
- Distributed SQL
- Queries
- SQL
tools:
- description: Submit an SQL query to Trino for distributed execution across data lakes and databases. Returns initial results and a nextUri for polling more data.
  hints:
    openWorld: true
    readOnly: true
  name: submit-sql-query
- description: Retrieve the next page of results for a running or recently completed query. Follow the nextUri from a previous query response.
  hints:
    openWorld: false
    readOnly: true
  name: get-query-results
- description: Cancel a running Trino query by its queryId and current token.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-query
- description: List currently running and recently completed queries on the Trino cluster. Filter by state (RUNNING, FINISHED, FAILED) or limit the result count.
  hints:
    openWorld: false
    readOnly: true
  name: list-active-queries
- description: Retrieve Trino cluster metadata including version, environment name, and whether the coordinator is still starting. Use for health checks.
  hints:
    openWorld: false
    readOnly: true
  name: get-cluster-info
- description: List all active worker nodes in the Trino cluster with their node IDs, URIs, heartbeat times, and resource utilization.
  hints:
    openWorld: false
    readOnly: true
  name: list-cluster-nodes
---
