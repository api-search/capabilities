---
categories:
- monitoring
consumed_apis:
- api-management
- apim
description: Unified workflow for API traffic analytics and observability on Apigee — querying runtime analytics by dimension, discovering undocumented shadow APIs via APIM observation jobs, and correlating traffic patterns with known API products. Provides platform architects, SREs, and governance teams with the operational visibility needed to monitor performance, detect anomalies, and govern API usage at scale.
layout: capability
name: Apigee Analytics and Traffic Observability
operations:
- description: Query traffic analytics for an environment.
  method: GET
  name: get-stats
  path: /v1/analytics/stats
- description: List observation jobs.
  method: GET
  name: list-observation-jobs
  path: /v1/observation-jobs
- description: List observed shadow APIs.
  method: GET
  name: list-observed-apis
  path: /v1/observed-apis
personas: []
provider_name: Apigee
provider_slug: apigee
search_terms:
- get stats
- analytics
- shadow apis discovered by observation jobs.
- integrations
- api governance
- google cloud
- list observed shadow apis.
- list deployments
- hybrid
- engineer managing api proxies, deployments, and policies in apigee.
- list observed api operations
- list all proxy deployments across environments to correlate with traffic anomalies.
- list all shadow api observation jobs configured to detect undocumented apis in traffic.
- list environments
- enterprise
- api management
- discover shadow apis
- list all environments (dev, staging, prod) to identify which to query analytics for.
- get traffic analytics
- microservices
- Platform Architect
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- developer portal
- apigee
- architect overseeing api platform strategy and governance across the organization.
- API Governance Lead
- list observation jobs
- shadow api discovery
- list observed apis
- list observation jobs.
- manager packaging api products and managing developer relationships.
- traffic analytics stats by dimension.
- api gateway
- shadow api observation jobs.
- observability
- query api traffic analytics for an apigee environment by dimension (e.g. apis, apiproducts, devs, apps). returns request counts, latency, and error rates.
- api hub
- list shadow apis discovered by an observation job — apis found in live traffic that are not yet documented or governed.
- API Product Manager
- API Platform Engineer
- query traffic analytics for an environment.
- monetization
- list individual http operations observed for a specific shadow api — method, path, count, and parameters seen in traffic.
slug: analytics-traffic-observability
source_filename: analytics-traffic-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apigee Analytics and Traffic Observability\"\n  description: \"Unified workflow for API traffic analytics and observability on Apigee — querying runtime analytics by dimension, discovering undocumented shadow APIs via APIM observation jobs, and correlating traffic patterns with known API products. Provides platform architects, SREs, and governance teams with the operational visibility needed to monitor performance, detect anomalies, and govern API usage at scale.\"\n  tags:\n    - Apigee\n    - Analytics\n    - Observability\n    - Shadow API Discovery\n    - Google Cloud\n  created: \"2026-04-20\"\n  modified: \"2026-04-20\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_ACCESS_TOKEN: GOOGLE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: api-management\n      location: ./shared/api-management.yaml\n    - import: apim\n      location: ./shared/apim.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace:\
  \ apigee-analytics-api\n      description: \"Unified REST API for Apigee analytics and traffic observability.\"\n      resources:\n        - path: /v1/analytics/stats\n          name: analytics-stats\n          description: \"Traffic analytics stats by dimension.\"\n          operations:\n            - method: GET\n              name: get-stats\n              description: \"Query traffic analytics for an environment.\"\n              call: \"api-management.getEnvironmentStats\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/observation-jobs\n          name: observation-jobs\n          description: \"Shadow API observation jobs.\"\n          operations:\n            - method: GET\n              name: list-observation-jobs\n              description: \"List observation jobs.\"\n              call: \"apim.listObservationJobs\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/observed-apis\n          name: observed-apis\n          description: \"Shadow APIs discovered by observation jobs.\"\n          operations:\n            - method: GET\n              name: list-observed-apis\n              description: \"List observed shadow APIs.\"\n              call: \"apim.listApiObservations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9094\n      namespace: apigee-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Apigee analytics and shadow API observability.\"\n      tools:\n        - name: get-traffic-analytics\n          description: \"Query API traffic analytics for an Apigee environment by dimension (e.g. apis, apiproducts, devs, apps). Returns request counts, latency, and error rates.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call:\
  \ \"api-management.getEnvironmentStats\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-environments\n          description: \"List all environments (dev, staging, prod) to identify which to query analytics for.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-management.listEnvironments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-observation-jobs\n          description: \"List all shadow API observation jobs configured to detect undocumented APIs in traffic.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"apim.listObservationJobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: discover-shadow-apis\n          description: \"List shadow\
  \ APIs discovered by an observation job — APIs found in live traffic that are not yet documented or governed.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"apim.listApiObservations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-observed-api-operations\n          description: \"List individual HTTP operations observed for a specific shadow API — method, path, count, and parameters seen in traffic.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"apim.listApiOperations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-deployments\n          description: \"List all proxy deployments across environments to correlate with traffic anomalies.\"\n          hints:\n            readOnly: true\n            destructive:\
  \ false\n            idempotent: true\n          call: \"api-management.listOrganizationDeployments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apigee/refs/heads/main/capabilities/analytics-traffic-observability.yaml
tags:
- Apigee
- Analytics
- Observability
- Shadow API Discovery
- Google Cloud
tools:
- description: Query API traffic analytics for an Apigee environment by dimension (e.g. apis, apiproducts, devs, apps). Returns request counts, latency, and error rates.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-traffic-analytics
- description: List all environments (dev, staging, prod) to identify which to query analytics for.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-environments
- description: List all shadow API observation jobs configured to detect undocumented APIs in traffic.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-observation-jobs
- description: List shadow APIs discovered by an observation job — APIs found in live traffic that are not yet documented or governed.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: discover-shadow-apis
- description: List individual HTTP operations observed for a specific shadow API — method, path, count, and parameters seen in traffic.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-observed-api-operations
- description: List all proxy deployments across environments to correlate with traffic anomalies.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-deployments
---
