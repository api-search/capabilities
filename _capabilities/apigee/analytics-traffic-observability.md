---
categories:
- monitoring
consumed_apis: []
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
- API Platform Engineer
- API Governance Lead
- get traffic analytics
- list environments
- traffic analytics stats by dimension.
- analytics
- list observation jobs
- list observed api operations
- developer portal
- Platform Architect
- list all shadow api observation jobs configured to detect undocumented apis in traffic.
- list observed shadow apis.
- list all proxy deployments across environments to correlate with traffic anomalies.
- list deployments
- enterprise
- list all environments (dev, staging, prod) to identify which to query analytics for.
- apigee
- api governance
- integrations
- query traffic analytics for an environment.
- API Product Manager
- hybrid
- monetization
- shadow api observation jobs.
- observability
- query api traffic analytics for an apigee environment by dimension (e.g. apis, apiproducts, devs, apps). returns request counts, latency, and error rates.
- api hub
- api gateway
- api management
- shadow api discovery
- list observation jobs.
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- list individual http operations observed for a specific shadow api — method, path, count, and parameters seen in traffic.
- shadow apis discovered by observation jobs.
- list observed apis
- discover shadow apis
- manager packaging api products and managing developer relationships.
- engineer managing api proxies, deployments, and policies in apigee.
- architect overseeing api platform strategy and governance across the organization.
- list shadow apis discovered by an observation job — apis found in live traffic that are not yet documented or governed.
- microservices
- google cloud
- get stats
slug: analytics-traffic-observability
source_filename: analytics-traffic-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apigee Analytics and Traffic Observability\n  description: Unified workflow for API traffic analytics and observability on Apigee — querying runtime analytics by dimension,\n    discovering undocumented shadow APIs via APIM observation jobs, and correlating traffic patterns with known API products.\n    Provides platform architects, SREs, and governance teams with the operational visibility needed to monitor performance,\n    detect anomalies, and govern API usage at scale.\n  tags:\n  - Apigee\n  - Analytics\n  - Observability\n  - Shadow API Discovery\n  - Google Cloud\n  created: '2026-04-20'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_ACCESS_TOKEN: GOOGLE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: api-management\n    baseUri: https://apigee.googleapis.com/v1\n    description: Apigee API Management REST API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_ACCESS_TOKEN}}'\n\
  \    resources:\n    - name: api-proxies\n      path: /organizations/{organizationId}/apis\n      operations:\n      - name: listApiProxies\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: proxies\n          type: array\n          value: $.proxies\n    - name: api-proxy\n      path: /organizations/{organizationId}/apis/{apiId}\n      operations:\n      - name: getApiProxy\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: apiId\n          in: path\n        outputParameters:\n        - name: proxy\n          type: object\n          value: $.\n    - name: api-products\n      path: /organizations/{organizationId}/apiproducts\n      operations:\n      - name: listApiProducts\n        method: GET\n        inputParameters:\n        - name: organizationId\n\
  \          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        - name: filter\n          in: query\n        outputParameters:\n        - name: products\n          type: array\n          value: $.products\n    - name: api-product\n      path: /organizations/{organizationId}/apiproducts/{productId}\n      operations:\n      - name: getApiProduct\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: productId\n          in: path\n        outputParameters:\n        - name: product\n          type: object\n          value: $.\n    - name: developers\n      path: /organizations/{organizationId}/developers\n      operations:\n      - name: listDevelopers\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        - name: filter\n \
  \         in: query\n        outputParameters:\n        - name: developers\n          type: array\n          value: $.developers\n    - name: developer\n      path: /organizations/{organizationId}/developers/{developerId}\n      operations:\n      - name: getDeveloper\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: developerId\n          in: path\n        outputParameters:\n        - name: developer\n          type: object\n          value: $.\n    - name: developer-apps\n      path: /organizations/{organizationId}/developers/{developerId}/apps\n      operations:\n      - name: listDeveloperApps\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: developerId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: apps\n          type: array\n          value:\
  \ $.apps\n    - name: developer-app\n      path: /organizations/{organizationId}/developers/{developerId}/apps/{appId}\n      operations:\n      - name: getDeveloperApp\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: developerId\n          in: path\n        - name: appId\n          in: path\n        outputParameters:\n        - name: app\n          type: object\n          value: $.\n    - name: environments\n      path: /organizations/{organizationId}/environments\n      operations:\n      - name: listEnvironments\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: environments\n          type: array\n          value: $.environments\n    - name: environment\n      path: /organizations/{organizationId}/environments/{environmentId}\n    \
  \  operations:\n      - name: getEnvironment\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: environmentId\n          in: path\n        outputParameters:\n        - name: environment\n          type: object\n          value: $.\n    - name: deployments\n      path: /organizations/{organizationId}/deployments\n      operations:\n      - name: listOrganizationDeployments\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        - name: filter\n          in: query\n        outputParameters:\n        - name: deployments\n          type: array\n          value: $.deployments\n    - name: proxy-deployment\n      path: /organizations/{organizationId}/environments/{environmentId}/apis/{apiId}/revisions/{revisionId}/deployments\n      operations:\n      - name: deployApiProxyRevision\n\
  \        method: POST\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: environmentId\n          in: path\n        - name: apiId\n          in: path\n        - name: revisionId\n          in: path\n        - name: override\n          in: query\n        outputParameters:\n        - name: deployment\n          type: object\n          value: $.\n      - name: undeployApiProxyRevision\n        method: DELETE\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: environmentId\n          in: path\n        - name: apiId\n          in: path\n        - name: revisionId\n          in: path\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shared-flows\n      path: /organizations/{organizationId}/sharedflows\n      operations:\n      - name: listSharedFlows\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n\
  \        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: sharedFlows\n          type: array\n          value: $.sharedFlows\n    - name: target-servers\n      path: /organizations/{organizationId}/environments/{environmentId}/targetservers\n      operations:\n      - name: listTargetServers\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in: path\n        - name: environmentId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: targetServers\n          type: array\n          value: $.targetServers\n    - name: analytics-stats\n      path: /organizations/{organizationId}/environments/{environmentId}/stats/{statsType}\n      operations:\n      - name: getEnvironmentStats\n        method: GET\n        inputParameters:\n        - name: organizationId\n          in:\
  \ path\n        - name: environmentId\n          in: path\n        - name: statsType\n          in: path\n        - name: timeRange\n          in: query\n        - name: timeUnit\n          in: query\n        - name: filter\n          in: query\n        - name: limit\n          in: query\n        outputParameters:\n        - name: stats\n          type: object\n          value: $.\n  - type: http\n    namespace: apim\n    baseUri: https://apim.googleapis.com/v1alpha\n    description: Apigee API Observation REST API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_ACCESS_TOKEN}}'\n    resources:\n    - name: observation-jobs\n      path: /projects/{projectId}/locations/{locationId}/observationJobs\n      operations:\n      - name: listObservationJobs\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n     \
  \     in: query\n        outputParameters:\n        - name: observationJobs\n          type: array\n          value: $.observationJobs\n    - name: observation-job\n      path: /projects/{projectId}/locations/{locationId}/observationJobs/{observationJobId}\n      operations:\n      - name: getObservationJob\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: observationJobId\n          in: path\n        outputParameters:\n        - name: observationJob\n          type: object\n          value: $.\n    - name: enable-observation-job\n      path: /projects/{projectId}/locations/{locationId}/observationJobs/{observationJobId}:enable\n      operations:\n      - name: enableObservationJob\n        method: POST\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: observationJobId\n          in: path\n \
  \       outputParameters:\n        - name: operation\n          type: object\n          value: $.\n    - name: disable-observation-job\n      path: /projects/{projectId}/locations/{locationId}/observationJobs/{observationJobId}:disable\n      operations:\n      - name: disableObservationJob\n        method: POST\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: observationJobId\n          in: path\n        outputParameters:\n        - name: operation\n          type: object\n          value: $.\n    - name: api-observations\n      path: /projects/{projectId}/locations/{locationId}/observationJobs/{observationJobId}/apiObservations\n      operations:\n      - name: listApiObservations\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: observationJobId\n          in: path\n        - name: pageSize\n\
  \          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: apiObservations\n          type: array\n          value: $.apiObservations\n    - name: api-observation\n      path: /projects/{projectId}/locations/{locationId}/observationJobs/{observationJobId}/apiObservations/{apiObservationId}\n      operations:\n      - name: getApiObservation\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: observationJobId\n          in: path\n        - name: apiObservationId\n          in: path\n        outputParameters:\n        - name: apiObservation\n          type: object\n          value: $.\n    - name: batch-edit-observation-tags\n      path: /projects/{projectId}/locations/{locationId}/observationJobs/{observationJobId}/apiObservations:batchEditTags\n      operations:\n      - name: batchEditApiObservationTags\n        method: POST\n\
  \        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: observationJobId\n          in: path\n        outputParameters:\n        - name: apiObservations\n          type: array\n          value: $.apiObservations\n    - name: api-operations\n      path: /projects/{projectId}/locations/{locationId}/observationJobs/{observationJobId}/apiObservations/{apiObservationId}/apiOperations\n      operations:\n      - name: listApiOperations\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: observationJobId\n          in: path\n        - name: apiObservationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: apiOperations\n          type: array\n          value: $.apiOperations\n  exposes:\n  - type: rest\n\
  \    port: 8084\n    namespace: apigee-analytics-api\n    description: Unified REST API for Apigee analytics and traffic observability.\n    resources:\n    - path: /v1/analytics/stats\n      name: analytics-stats\n      description: Traffic analytics stats by dimension.\n      operations:\n      - method: GET\n        name: get-stats\n        description: Query traffic analytics for an environment.\n        call: api-management.getEnvironmentStats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/observation-jobs\n      name: observation-jobs\n      description: Shadow API observation jobs.\n      operations:\n      - method: GET\n        name: list-observation-jobs\n        description: List observation jobs.\n        call: apim.listObservationJobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/observed-apis\n      name: observed-apis\n      description: Shadow APIs discovered by observation jobs.\n\
  \      operations:\n      - method: GET\n        name: list-observed-apis\n        description: List observed shadow APIs.\n        call: apim.listApiObservations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9094\n    namespace: apigee-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted Apigee analytics and shadow API observability.\n    tools:\n    - name: get-traffic-analytics\n      description: Query API traffic analytics for an Apigee environment by dimension (e.g. apis, apiproducts, devs, apps).\n        Returns request counts, latency, and error rates.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-management.getEnvironmentStats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-environments\n      description: List all environments (dev, staging, prod) to identify which to query analytics for.\n     \
  \ hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-management.listEnvironments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-observation-jobs\n      description: List all shadow API observation jobs configured to detect undocumented APIs in traffic.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apim.listObservationJobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: discover-shadow-apis\n      description: List shadow APIs discovered by an observation job — APIs found in live traffic that are not yet documented\n        or governed.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apim.listApiObservations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-observed-api-operations\n      description: List individual\
  \ HTTP operations observed for a specific shadow API — method, path, count, and parameters\n        seen in traffic.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apim.listApiOperations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-deployments\n      description: List all proxy deployments across environments to correlate with traffic anomalies.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-management.listOrganizationDeployments\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
