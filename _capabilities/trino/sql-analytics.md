---
categories: []
consumed_apis: []
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
- analytics
- retrieve the next page of results for a running or recently completed query. follow the nexturi from a previous query response.
- cancel a running trino query by its queryid and current token.
- list cluster nodes
- submit sql queries and list query history
- data engineering
- submit an sql query to trino for distributed execution
- retrieve paginated results or cancel a query
- list all active worker nodes in the cluster
- queries
- worker node listing and status
- submit an sql query to trino for distributed execution across data lakes and databases. returns initial results and a nexturi for polling more data.
- list all active worker nodes in the trino cluster with their node ids, uris, heartbeat times, and resource utilization.
- distributed sql
- list currently running and recently completed queries on the trino cluster. filter by state (running, finished, failed) or limit the result count.
- sql
- big data
- cancel a running query
- trino cluster health and version information
- list active and recently completed queries
- get the next page of results for a running query
- get trino cluster version, environment, and startup state
- submit sql query
- get query results
- cancel query
- mysql
- submit query
- nosql
- list nodes
- retrieve trino cluster metadata including version, environment name, and whether the coordinator is still starting. use for health checks.
- list queries
- list active queries
- get cluster info
slug: sql-analytics
source_filename: sql-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Trino SQL Analytics\n  description: Workflow capability for submitting distributed SQL queries to Trino, monitoring query execution, retrieving\n    results, and managing the Trino cluster. Designed for data engineers, analysts, and data platform operators who need programmatic\n    access to Trino's big data SQL engine across data lakes and databases.\n  tags:\n  - Analytics\n  - Big Data\n  - Data Engineering\n  - Distributed SQL\n  - Queries\n  - SQL\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRINO_HOST: TRINO_HOST\n    TRINO_USER: TRINO_USER\ncapability:\n  consumes:\n  - type: http\n    namespace: trino-client\n    baseUri: http://{{env.TRINO_HOST}}\n    description: Trino distributed SQL query engine REST API\n    authentication:\n      type: apikey\n      key: X-Trino-User\n      value: '{{env.TRINO_USER}}'\n      placement: header\n    resources:\n    - name: statements\n      path:\
  \ /v1/statement\n      description: SQL query submission and result streaming\n      operations:\n      - name: submit-statement\n        method: POST\n        description: Submit an SQL query for execution and receive initial results\n        inputParameters:\n        - name: X-Trino-Catalog\n          in: header\n          type: string\n          required: false\n          description: Default catalog for the query session\n        - name: X-Trino-Schema\n          in: header\n          type: string\n          required: false\n          description: Default schema for the query session\n        - name: X-Trino-Source\n          in: header\n          type: string\n          required: false\n          description: Client application identifier\n        - name: X-Trino-Session\n          in: header\n          type: string\n          required: false\n          description: Comma-separated session property assignments\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        body:\n          type: text\n          data:\n            query: '{{tools.sql_query}}'\n    - name: query-results\n      path: /v1/statement/{queryId}/{token}\n      description: Poll for query result pages and cancel queries\n      operations:\n      - name: get-query-results\n        method: GET\n        description: Retrieve the next page of results for a running query\n        inputParameters:\n        - name: queryId\n          in: path\n          type: string\n          required: true\n          description: Unique query identifier from submit-statement response\n        - name: token\n          in: path\n          type: integer\n          required: true\n          description: Sequential token for result page\n        - name: maxWait\n          in: query\n          type: string\n          required: false\n          description: Maximum wait duration before returning empty batch\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-query\n        method: DELETE\n        description: Cancel a running query\n        inputParameters:\n        - name: queryId\n          in: path\n          type: string\n          required: true\n          description: Unique query identifier\n        - name: token\n          in: path\n          type: integer\n          required: true\n          description: Sequential token matching current position\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster-info\n      path: /v1/info\n      description: Trino cluster health and version information\n      operations:\n      - name: get-cluster-info\n        method: GET\n        description: Retrieve cluster version, environment, and startup status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n    - name: nodes\n      path: /v1/node\n      description: Trino cluster worker node listing\n      operations:\n      - name: list-nodes\n        method: GET\n        description: List all active worker nodes in the Trino cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queries\n      path: /v1/query\n      description: Active and historical query management\n      operations:\n      - name: list-queries\n        method: GET\n        description: List running and recently completed queries\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: Filter by query state (RUNNING, FINISHED, FAILED, etc.)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of queries to return\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: trino-analytics-api\n    description: Unified REST API for submitting and managing Trino SQL queries.\n    resources:\n    - path: /v1/queries\n      name: queries\n      description: Submit SQL queries and list query history\n      operations:\n      - method: POST\n        name: submit-query\n        description: Submit an SQL query to Trino for distributed execution\n        call: trino-client.submit-statement\n        with:\n          sql_query: rest.body.query\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-queries\n        description: List active and recently completed queries\n        call: trino-client.list-queries\n        with:\n          state: rest.state\n          limit: rest.limit\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/queries/{queryId}/{token}\n      name: query-results\n      description: Retrieve paginated results or cancel a query\n      operations:\n      - method: GET\n        name: get-query-results\n        description: Get the next page of results for a running query\n        call: trino-client.get-query-results\n        with:\n          queryId: rest.queryId\n          token: rest.token\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-query\n        description: Cancel a running query\n        call: trino-client.cancel-query\n        with:\n          queryId: rest.queryId\n          token: rest.token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cluster/info\n      name: cluster-info\n      description: Trino cluster health and version information\n      operations:\n      - method: GET\n        name: get-cluster-info\n        description:\
  \ Get Trino cluster version, environment, and startup state\n        call: trino-client.get-cluster-info\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cluster/nodes\n      name: nodes\n      description: Worker node listing and status\n      operations:\n      - method: GET\n        name: list-nodes\n        description: List all active worker nodes in the cluster\n        call: trino-client.list-nodes\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: trino-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted SQL analytics with Trino distributed query engine.\n    tools:\n    - name: submit-sql-query\n      description: Submit an SQL query to Trino for distributed execution across data lakes and databases. Returns initial\n        results and a nextUri for polling more data.\n      hints:\n        readOnly: true\n        openWorld: true\n      call:\
  \ trino-client.submit-statement\n      with:\n        sql_query: tools.sql_query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-query-results\n      description: Retrieve the next page of results for a running or recently completed query. Follow the nextUri from a\n        previous query response.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trino-client.get-query-results\n      with:\n        queryId: tools.queryId\n        token: tools.token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-query\n      description: Cancel a running Trino query by its queryId and current token.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: trino-client.cancel-query\n      with:\n        queryId: tools.queryId\n        token: tools.token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-active-queries\n\
  \      description: List currently running and recently completed queries on the Trino cluster. Filter by state (RUNNING, FINISHED,\n        FAILED) or limit the result count.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trino-client.list-queries\n      with:\n        state: tools.state\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cluster-info\n      description: Retrieve Trino cluster metadata including version, environment name, and whether the coordinator is still\n        starting. Use for health checks.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trino-client.get-cluster-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cluster-nodes\n      description: List all active worker nodes in the Trino cluster with their node IDs, URIs, heartbeat times, and resource\n        utilization.\n      hints:\n        readOnly:\
  \ true\n        openWorld: false\n      call: trino-client.list-nodes\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
