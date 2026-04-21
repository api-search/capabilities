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
- list individual http operations observed for a specific shadow api — method, path, count, and parameters seen in traffic.
- list observed api operations
- list observation jobs.
- list all proxy deployments across environments to correlate with traffic anomalies.
- api hub
- Platform Architect
- shadow api observation jobs.
- list observation jobs
- shadow api discovery
- query traffic analytics for an environment.
- api management
- google cloud
- traffic analytics stats by dimension.
- hybrid
- analytics
- engineer managing api proxies, deployments, and policies in apigee.
- enterprise
- observability
- api gateway
- API Platform Engineer
- architect overseeing api platform strategy and governance across the organization.
- list observed apis
- list deployments
- API Governance Lead
- monetization
- discover shadow apis
- list all shadow api observation jobs configured to detect undocumented apis in traffic.
- list observed shadow apis.
- get stats
- integrations
- query api traffic analytics for an apigee environment by dimension (e.g. apis, apiproducts, devs, apps). returns request counts, latency, and error rates.
- api governance
- list shadow apis discovered by an observation job — apis found in live traffic that are not yet documented or governed.
- microservices
- shadow apis discovered by observation jobs.
- developer portal
- list environments
- apigee
- get traffic analytics
- API Product Manager
- manager packaging api products and managing developer relationships.
- list all environments (dev, staging, prod) to identify which to query analytics for.
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
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
