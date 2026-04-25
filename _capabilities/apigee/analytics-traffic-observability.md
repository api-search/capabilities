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
- traffic analytics stats by dimension.
- enterprise
- query traffic analytics for an environment.
- list shadow apis discovered by an observation job — apis found in live traffic that are not yet documented or governed.
- API Governance Lead
- integrations
- architect overseeing api platform strategy and governance across the organization.
- api management
- query api traffic analytics for an apigee environment by dimension (e.g. apis, apiproducts, devs, apps). returns request counts, latency, and error rates.
- google cloud
- list observed apis
- shadow api observation jobs.
- microservices
- list observation jobs.
- observability
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- list observed shadow apis.
- get traffic analytics
- API Product Manager
- shadow api discovery
- API Platform Engineer
- list deployments
- list environments
- list all environments (dev, staging, prod) to identify which to query analytics for.
- list all proxy deployments across environments to correlate with traffic anomalies.
- hybrid
- list individual http operations observed for a specific shadow api — method, path, count, and parameters seen in traffic.
- engineer managing api proxies, deployments, and policies in apigee.
- get stats
- api governance
- list observation jobs
- manager packaging api products and managing developer relationships.
- shadow apis discovered by observation jobs.
- monetization
- discover shadow apis
- Platform Architect
- api gateway
- analytics
- api hub
- list observed api operations
- apigee
- developer portal
- list all shadow api observation jobs configured to detect undocumented apis in traffic.
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
