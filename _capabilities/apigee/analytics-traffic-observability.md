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
- monetization
- list environments
- shadow apis discovered by observation jobs.
- engineer managing api proxies, deployments, and policies in apigee.
- api management
- developer portal
- list all proxy deployments across environments to correlate with traffic anomalies.
- enterprise
- api gateway
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- shadow api discovery
- get traffic analytics
- shadow api observation jobs.
- hybrid
- list observed apis
- apigee
- Platform Architect
- list observation jobs.
- list individual http operations observed for a specific shadow api — method, path, count, and parameters seen in traffic.
- api hub
- microservices
- traffic analytics stats by dimension.
- API Governance Lead
- analytics
- list all shadow api observation jobs configured to detect undocumented apis in traffic.
- integrations
- get stats
- api governance
- list deployments
- API Product Manager
- discover shadow apis
- list observed api operations
- list shadow apis discovered by an observation job — apis found in live traffic that are not yet documented or governed.
- list observed shadow apis.
- google cloud
- query traffic analytics for an environment.
- observability
- API Platform Engineer
- list observation jobs
- list all environments (dev, staging, prod) to identify which to query analytics for.
- architect overseeing api platform strategy and governance across the organization.
- query api traffic analytics for an apigee environment by dimension (e.g. apis, apiproducts, devs, apps). returns request counts, latency, and error rates.
- manager packaging api products and managing developer relationships.
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
