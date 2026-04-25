---
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
- engineer managing api proxies, deployments, and policies in apigee.
- get stats
- integrations
- api hub
- analytics
- api gateway
- list all shadow api observation jobs configured to detect undocumented apis in traffic.
- enterprise
- apigee
- query traffic analytics for an environment.
- query api traffic analytics for an apigee environment by dimension (e.g. apis, apiproducts, devs, apps). returns request counts, latency, and error rates.
- Platform Architect
- list all environments (dev, staging, prod) to identify which to query analytics for.
- get traffic analytics
- shadow apis discovered by observation jobs.
- list all proxy deployments across environments to correlate with traffic anomalies.
- api management
- developer portal
- observability
- microservices
- api governance
- architect overseeing api platform strategy and governance across the organization.
- list deployments
- manager packaging api products and managing developer relationships.
- shadow api observation jobs.
- list environments
- list observed shadow apis.
- list observation jobs.
- API Product Manager
- traffic analytics stats by dimension.
- list observed api operations
- google cloud
- list individual http operations observed for a specific shadow api — method, path, count, and parameters seen in traffic.
- API Platform Engineer
- discover shadow apis
- list observation jobs
- hybrid
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- API Governance Lead
- shadow api discovery
- list observed apis
- list shadow apis discovered by an observation job — apis found in live traffic that are not yet documented or governed.
- monetization
slug: analytics-traffic-observability
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
