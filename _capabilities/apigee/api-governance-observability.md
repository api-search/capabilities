---
categories: []
consumed_apis: []
description: Unified workflow for API governance, discovery, and observability using Apigee API Hub for cataloguing, API Observation (APIM) for shadow API discovery, and Registry for tracking specifications.
layout: capability
name: Apigee API Governance and Observability
operations:
- description: List all catalogued APIs.
  method: GET
  name: list-apis
  path: /v1/apis
- description: List observed shadow APIs.
  method: GET
  name: list-observed-apis
  path: /v1/observed-apis
personas: []
provider_name: Apigee
provider_slug: apigee
search_terms:
- API Platform Engineer
- list api specifications tracked in the apigee registry.
- API Governance Lead
- analytics
- shadow apis discovered via apim.
- developer portal
- Platform Architect
- list observed shadow apis.
- discover undocumented shadow apis in google cloud infrastructure using apim.
- enterprise
- list catalogued apis
- api discovery
- apigee
- list all catalogued apis.
- api governance
- api catalog
- list all apis in the apigee api hub catalog.
- integrations
- hybrid
- API Product Manager
- monetization
- api hub
- api catalog from api hub.
- list api specs
- api gateway
- api management
- list apis
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- manager packaging api products and managing developer relationships.
- list observed apis
- discover shadow apis
- engineer managing api proxies, deployments, and policies in apigee.
- architect overseeing api platform strategy and governance across the organization.
- microservices
- google cloud
slug: api-governance-observability
source_filename: api-governance-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apigee API Governance and Observability\n  description: Unified workflow for API governance, discovery, and observability using Apigee API Hub for cataloguing, API\n    Observation (APIM) for shadow API discovery, and Registry for tracking specifications.\n  tags:\n  - Apigee\n  - API Governance\n  - API Catalog\n  - API Discovery\n  - Google Cloud\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_ACCESS_TOKEN: GOOGLE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: api-hub\n    baseUri: https://apihub.googleapis.com/v1\n    description: Apigee API Hub REST API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_ACCESS_TOKEN}}'\n    resources:\n    - name: apis\n      path: /projects/{projectId}/locations/{locationId}/apis\n      operations:\n      - name: listApis\n        method: GET\n        inputParameters:\n        - name: projectId\n          in:\
  \ path\n        - name: locationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        - name: filter\n          in: query\n        outputParameters:\n        - name: apis\n          type: array\n          value: $.apis\n    - name: api\n      path: /projects/{projectId}/locations/{locationId}/apis/{apiId}\n      operations:\n      - name: getApi\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: apiId\n          in: path\n        outputParameters:\n        - name: api\n          type: object\n          value: $.\n    - name: api-versions\n      path: /projects/{projectId}/locations/{locationId}/apis/{apiId}/versions\n      operations:\n      - name: listApiVersions\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n \
  \       - name: apiId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: versions\n          type: array\n          value: $.versions\n    - name: api-specs\n      path: /projects/{projectId}/locations/{locationId}/apis/{apiId}/versions/{versionId}/specs\n      operations:\n      - name: listApiSpecs\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: apiId\n          in: path\n        - name: versionId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: specs\n          type: array\n          value: $.specs\n    - name: api-spec-contents\n      path: /projects/{projectId}/locations/{locationId}/apis/{apiId}/versions/{versionId}/specs/{specId}:getContents\n      operations:\n\
  \      - name: getApiSpecContents\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: apiId\n          in: path\n        - name: versionId\n          in: path\n        - name: specId\n          in: path\n        outputParameters:\n        - name: contents\n          type: object\n          value: $.\n    - name: api-spec-lint\n      path: /projects/{projectId}/locations/{locationId}/apis/{apiId}/versions/{versionId}/specs/{specId}:lint\n      operations:\n      - name: lintApiSpec\n        method: POST\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: apiId\n          in: path\n        - name: versionId\n          in: path\n        - name: specId\n          in: path\n        outputParameters:\n        - name: operation\n          type: object\n          value: $.\n    - name: deployments\n    \
  \  path: /projects/{projectId}/locations/{locationId}/deployments\n      operations:\n      - name: listDeployments\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        - name: filter\n          in: query\n        outputParameters:\n        - name: deployments\n          type: array\n          value: $.deployments\n    - name: dependencies\n      path: /projects/{projectId}/locations/{locationId}/dependencies\n      operations:\n      - name: listDependencies\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        - name: filter\n          in: query\n        outputParameters:\n        - name: dependencies\n  \
  \        type: array\n          value: $.dependencies\n    - name: search\n      path: /projects/{projectId}/locations/{locationId}:searchResources\n      operations:\n      - name: searchResources\n        method: POST\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        outputParameters:\n        - name: searchResults\n          type: array\n          value: $.searchResults\n  - type: http\n    namespace: apim\n    baseUri: https://apim.googleapis.com/v1alpha\n    description: Apigee API Observation REST API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_ACCESS_TOKEN}}'\n    resources:\n    - name: observation-jobs\n      path: /projects/{projectId}/locations/{locationId}/observationJobs\n      operations:\n      - name: listObservationJobs\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n       \
  \ - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: observationJobs\n          type: array\n          value: $.observationJobs\n    - name: observation-job\n      path: /projects/{projectId}/locations/{locationId}/observationJobs/{observationJobId}\n      operations:\n      - name: getObservationJob\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: observationJobId\n          in: path\n        outputParameters:\n        - name: observationJob\n          type: object\n          value: $.\n    - name: enable-observation-job\n      path: /projects/{projectId}/locations/{locationId}/observationJobs/{observationJobId}:enable\n      operations:\n      - name: enableObservationJob\n        method: POST\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n   \
  \       in: path\n        - name: observationJobId\n          in: path\n        outputParameters:\n        - name: operation\n          type: object\n          value: $.\n    - name: disable-observation-job\n      path: /projects/{projectId}/locations/{locationId}/observationJobs/{observationJobId}:disable\n      operations:\n      - name: disableObservationJob\n        method: POST\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: observationJobId\n          in: path\n        outputParameters:\n        - name: operation\n          type: object\n          value: $.\n    - name: api-observations\n      path: /projects/{projectId}/locations/{locationId}/observationJobs/{observationJobId}/apiObservations\n      operations:\n      - name: listApiObservations\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n   \
  \     - name: observationJobId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: apiObservations\n          type: array\n          value: $.apiObservations\n    - name: api-observation\n      path: /projects/{projectId}/locations/{locationId}/observationJobs/{observationJobId}/apiObservations/{apiObservationId}\n      operations:\n      - name: getApiObservation\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: observationJobId\n          in: path\n        - name: apiObservationId\n          in: path\n        outputParameters:\n        - name: apiObservation\n          type: object\n          value: $.\n    - name: batch-edit-observation-tags\n      path: /projects/{projectId}/locations/{locationId}/observationJobs/{observationJobId}/apiObservations:batchEditTags\n      operations:\n\
  \      - name: batchEditApiObservationTags\n        method: POST\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: observationJobId\n          in: path\n        outputParameters:\n        - name: apiObservations\n          type: array\n          value: $.apiObservations\n    - name: api-operations\n      path: /projects/{projectId}/locations/{locationId}/observationJobs/{observationJobId}/apiObservations/{apiObservationId}/apiOperations\n      operations:\n      - name: listApiOperations\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: observationJobId\n          in: path\n        - name: apiObservationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: apiOperations\n          type:\
  \ array\n          value: $.apiOperations\n  - type: http\n    namespace: registry\n    baseUri: https://apigeeregistry.googleapis.com/v1\n    description: Apigee Registry REST API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_ACCESS_TOKEN}}'\n    resources:\n    - name: apis\n      path: /projects/{projectId}/locations/{locationId}/apis\n      operations:\n      - name: listApis\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        - name: filter\n          in: query\n        outputParameters:\n        - name: apis\n          type: array\n          value: $.apis\n    - name: api\n      path: /projects/{projectId}/locations/{locationId}/apis/{apiId}\n      operations:\n      - name: getApi\n        method: GET\n        inputParameters:\n        - name: projectId\n          in:\
  \ path\n        - name: locationId\n          in: path\n        - name: apiId\n          in: path\n        outputParameters:\n        - name: api\n          type: object\n          value: $.\n    - name: api-versions\n      path: /projects/{projectId}/locations/{locationId}/apis/{apiId}/versions\n      operations:\n      - name: listApiVersions\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: apiId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: apiVersions\n          type: array\n          value: $.apiVersions\n    - name: api-specs\n      path: /projects/{projectId}/locations/{locationId}/apis/{apiId}/versions/{versionId}/specs\n      operations:\n      - name: listApiSpecs\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n\
  \        - name: locationId\n          in: path\n        - name: apiId\n          in: path\n        - name: versionId\n          in: path\n        - name: pageSize\n          in: query\n        - name: pageToken\n          in: query\n        outputParameters:\n        - name: apiSpecs\n          type: array\n          value: $.apiSpecs\n    - name: api-spec-contents\n      path: /projects/{projectId}/locations/{locationId}/apis/{apiId}/versions/{versionId}/specs/{specId}:getContents\n      operations:\n      - name: getApiSpecContents\n        method: GET\n        inputParameters:\n        - name: projectId\n          in: path\n        - name: locationId\n          in: path\n        - name: apiId\n          in: path\n        - name: versionId\n          in: path\n        - name: specId\n          in: path\n        outputParameters:\n        - name: contents\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: apigee-governance-api\n \
  \   description: Unified REST API for Apigee API governance and observability.\n    resources:\n    - path: /v1/apis\n      name: api-catalog\n      description: API catalog from API Hub.\n      operations:\n      - method: GET\n        name: list-apis\n        description: List all catalogued APIs.\n        call: api-hub.listApis\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/observed-apis\n      name: observed-apis\n      description: Shadow APIs discovered via APIM.\n      operations:\n      - method: GET\n        name: list-observed-apis\n        description: List observed shadow APIs.\n        call: apim.listObservedApis\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: apigee-governance-mcp\n    transport: http\n    description: MCP server for AI-assisted API governance and catalog management.\n    tools:\n    - name: list-catalogued-apis\n      description: List all\
  \ APIs in the Apigee API Hub catalog.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-hub.listApis\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: discover-shadow-apis\n      description: Discover undocumented shadow APIs in Google Cloud infrastructure using APIM.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apim.listObservedApis\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-specs\n      description: List API specifications tracked in the Apigee Registry.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: registry.listApiSpecs\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apigee/refs/heads/main/capabilities/api-governance-observability.yaml
tags:
- Apigee
- API Governance
- API Catalog
- API Discovery
- Google Cloud
tools:
- description: List all APIs in the Apigee API Hub catalog.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-catalogued-apis
- description: Discover undocumented shadow APIs in Google Cloud infrastructure using APIM.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: discover-shadow-apis
- description: List API specifications tracked in the Apigee Registry.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-api-specs
---
