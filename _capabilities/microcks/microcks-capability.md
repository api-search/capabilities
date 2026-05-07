---
categories: []
consumed_apis: []
description: API offered by Microcks, the Kubernetes native tool for API and microservices mocking and testing (microcks.io)
layout: capability
name: Microcks API v1.14
operations:
- description: Get Services and APIs
  method: GET
  name: getservices
  path: /services
- description: Create a new Test
  method: POST
  name: createtest
  path: /tests
- description: Get the Services counter
  method: GET
  name: getservicescounter
  path: /services/count
- description: Get ImportJobs
  method: GET
  name: getimportjobs
  path: /jobs
- description: Create ImportJob
  method: POST
  name: createimportjob
  path: /jobs
- description: Get ImportJob
  method: GET
  name: getimportjob
  path: /jobs/{id}
- description: Update ImportJob
  method: POST
  name: updateimportjob
  path: /jobs/{id}
- description: Delete ImportJob
  method: DELETE
  name: deleteimportjob
  path: /jobs/{id}
- description: Get Service
  method: GET
  name: getservice
  path: /services/{id}
- description: Delete Service
  method: DELETE
  name: deleteservice
  path: /services/{id}
- description: Get the ImportJobs counter
  method: GET
  name: getimportjobcounter
  path: /jobs/count
- description: Get Secrets
  method: GET
  name: getsecrets
  path: /secrets
- description: Create a new Secret
  method: POST
  name: createsecret
  path: /secrets
- description: Get Secret
  method: GET
  name: getsecret
  path: /secrets/{id}
- description: Update Secret
  method: PUT
  name: updatesecret
  path: /secrets/{id}
- description: Delete Secret
  method: DELETE
  name: deletesecret
  path: /secrets/{id}
- description: Get the Secrets counter
  method: GET
  name: getsecretscounter
  path: /secrets/count
- description: Get TestResults by Service
  method: GET
  name: gettestresultsbyservice
  path: /tests/service/{serviceId}
- description: Get the TestResults for Service counter
  method: GET
  name: gettestresultsbyservicecounter
  path: /tests/service/{serviceId}/count
- description: Get TestResult
  method: GET
  name: gettestresult
  path: /tests/{id}
- description: Get messages for TestCase
  method: GET
  name: getmessagesbytestcase
  path: /tests/{id}/messages/{testCaseId}
- description: Report and create a new TestCaseResult
  method: POST
  name: reporttestcaseresult
  path: /tests/{id}/testCaseResult
- description: Get authentification configuration
  method: GET
  name: getkeycloakconfig
  path: /keycloak/config
- description: Override Service Operation
  method: PUT
  name: overrideserviceoperation
  path: /services/{id}/operation
- description: Update Service Metadata
  method: PUT
  name: updateservicemetadata
  path: /services/{id}/metadata
- description: Search for Services and APIs
  method: GET
  name: searchservices
  path: /services/search
- description: Get events for TestCase
  method: GET
  name: geteventsbytestcase
  path: /tests/{id}/events/{testCaseId}
- description: Get Resource
  method: GET
  name: getresource
  path: /resources/{name}
- description: Get Resources by Service
  method: GET
  name: getresourcesbyservice
  path: /resources/service/{serviceId}
- description: Get features configuration
  method: GET
  name: getfeaturesconfig
  path: /features/config
- description: Import a snapshot
  method: POST
  name: importsnapshot
  path: /import
- description: Export a snapshot
  method: GET
  name: exportsnapshot
  path: /export
- description: Get aggregated invocation statistics for a day
  method: GET
  name: getaggregatedinvocationsstats
  path: /metrics/invocations/global
- description: Get aggregation of conformance metrics
  method: GET
  name: getconformancemetricsaggregation
  path: /metrics/conformance/aggregate
- description: Get conformance metrics for a Service
  method: GET
  name: getservicetestconformancemetric
  path: /metrics/conformance/service/{serviceId}
- description: Get top invocation statistics for a day
  method: GET
  name: gettopivnocationsstatsbyday
  path: /metrics/invocations/top
- description: Get invocation statistics for Service
  method: GET
  name: getinvocationstatsbyservice
  path: /metrics/invocations/{serviceName}/{serviceVersion}
- description: Get aggregated invocations statistics for latest days
  method: GET
  name: getlatestaggregatedinvocationsstats
  path: /metrics/invocations/global/latest
- description: Get latest tests results
  method: GET
  name: getlatesttestresults
  path: /metrics/tests/latest
- description: Start an ImportJob
  method: PUT
  name: startimportjob
  path: /jobs/{id}/start
- description: Stop an ImportJob
  method: PUT
  name: stopimportjob
  path: /jobs/{id}/stop
- description: Activate an ImportJob
  method: PUT
  name: activateimportjob
  path: /jobs/{id}/activate
- description: Get the already used labels for Services
  method: GET
  name: getserviceslabels
  path: /services/labels
- description: Download an artifact
  method: POST
  name: downloadartifact
  path: /artifact/download
- description: Search for Secrets
  method: GET
  name: searchsecrets
  path: /secrets/search
- description: Upload an artifact
  method: POST
  name: uploadartifact
  path: /artifact/upload
personas: []
provider_name: Microcks
provider_slug: microcks
search_terms:
- get conformance metrics for a service
- delete secret
- mocking
- api
- gettestresult
- upload an artifact
- create a new secret
- getsecretscounter
- getsecret
- downloadartifact
- searchservices
- gettestresultsbyservicecounter
- stopimportjob
- importsnapshot
- search for services and apis
- get the importjobs counter
- deletesecret
- createimportjob
- get aggregated invocations statistics for latest days
- deleteservice
- getfeaturesconfig
- getlatesttestresults
- updateservicemetadata
- get importjob
- createsecret
- api testing
- geteventsbytestcase
- update service metadata
- updateimportjob
- get aggregated invocation statistics for a day
- download an artifact
- getimportjobcounter
- searchsecrets
- cloud native
- overrideserviceoperation
- get the services counter
- get the already used labels for services
- get invocation statistics for service
- getconformancemetricsaggregation
- get aggregation of conformance metrics
- getresource
- get messages for testcase
- getimportjobs
- createtest
- get services and apis
- update secret
- getmessagesbytestcase
- stop an importjob
- start an importjob
- search for secrets
- exportsnapshot
- getsecrets
- get the secrets counter
- report and create a new testcaseresult
- get secrets
- activateimportjob
- uploadartifact
- get resources by service
- getlatestaggregatedinvocationsstats
- get latest tests results
- get top invocation statistics for a day
- update importjob
- delete importjob
- microcks
- get service
- import a snapshot
- gettopivnocationsstatsbyday
- gettestresultsbyservice
- deleteimportjob
- getaggregatedinvocationsstats
- override service operation
- getservicescounter
- getserviceslabels
- getservices
- delete service
- reporttestcaseresult
- get resource
- create a new test
- create importjob
- getinvocationstatsbyservice
- devops
- get importjobs
- get features configuration
- getimportjob
- getservice
- get testresults by service
- getkeycloakconfig
- get secret
- getservicetestconformancemetric
- get the testresults for service counter
- get events for testcase
- get testresult
- open source
- get authentification configuration
- startimportjob
- activate an importjob
- export a snapshot
- getresourcesbyservice
- updatesecret
slug: microcks-capability
source_filename: microcks-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microcks API v1.14\n  description: API offered by Microcks, the Kubernetes native tool for API and microservices mocking and testing (microcks.io)\n  tags:\n  - Microcks\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microcks\n    baseUri: http://microcks.example.com/api\n    description: Microcks API v1.14 HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROCKS_TOKEN}}'\n    resources:\n    - name: services\n      path: /services\n      operations:\n      - name: getservices\n        method: GET\n        description: Get Services and APIs\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Page of Services to retrieve (starts at and defaults to 0)\n        - name: size\n          in: query\n          type: integer\n          description: Size of a page. Maximum number of Services\
  \ to include in a response (defaults to 20)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tests\n      path: /tests\n      operations:\n      - name: createtest\n        method: POST\n        description: Create a new Test\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-count\n      path: /services/count\n      operations:\n      - name: getservicescounter\n        method: GET\n        description: Get the Services counter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /jobs\n      operations:\n      - name: getimportjobs\n        method: GET\n        description: Get ImportJobs\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description:\
  \ Page of ImportJobs to retrieve (starts at and defaults to 0)\n        - name: size\n          in: query\n          type: integer\n          description: Size of a page. Maximum number of ImportJobs to include in a response (defaults to 20)\n        - name: name\n          in: query\n          type: string\n          description: Name like criterion for query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createimportjob\n        method: POST\n        description: Create ImportJob\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-id\n      path: /jobs/{id}\n      operations:\n      - name: getimportjob\n        method: GET\n        description: Get ImportJob\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ updateimportjob\n        method: POST\n        description: Update ImportJob\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteimportjob\n        method: DELETE\n        description: Delete ImportJob\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-id\n      path: /services/{id}\n      operations:\n      - name: getservice\n        method: GET\n        description: Get Service\n        inputParameters:\n        - name: messages\n          in: query\n          type: boolean\n          description: Whether to include details on services messages into result. Default is false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteservice\n        method: DELETE\n        description: Delete Service\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-count\n      path: /jobs/count\n      operations:\n      - name: getimportjobcounter\n        method: GET\n        description: Get the ImportJobs counter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secrets\n      path: /secrets\n      operations:\n      - name: getsecrets\n        method: GET\n        description: Get Secrets\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Page of Secrets to retrieve (starts at and defaults to 0)\n        - name: size\n          in: query\n          type: integer\n          description: Size of a page. Maximum number of Secrets to include in a response (defaults to 20)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: createsecret\n        method: POST\n        description: Create a new Secret\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secrets-id\n      path: /secrets/{id}\n      operations:\n      - name: getsecret\n        method: GET\n        description: Get Secret\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesecret\n        method: PUT\n        description: Update Secret\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesecret\n        method: DELETE\n        description: Delete Secret\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secrets-count\n    \
  \  path: /secrets/count\n      operations:\n      - name: getsecretscounter\n        method: GET\n        description: Get the Secrets counter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tests-service-serviceid\n      path: /tests/service/{serviceId}\n      operations:\n      - name: gettestresultsbyservice\n        method: GET\n        description: Get TestResults by Service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tests-service-serviceid-count\n      path: /tests/service/{serviceId}/count\n      operations:\n      - name: gettestresultsbyservicecounter\n        method: GET\n        description: Get the TestResults for Service counter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tests-id\n      path:\
  \ /tests/{id}\n      operations:\n      - name: gettestresult\n        method: GET\n        description: Get TestResult\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tests-id-messages-testcaseid\n      path: /tests/{id}/messages/{testCaseId}\n      operations:\n      - name: getmessagesbytestcase\n        method: GET\n        description: Get messages for TestCase\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tests-id-testcaseresult\n      path: /tests/{id}/testCaseResult\n      operations:\n      - name: reporttestcaseresult\n        method: POST\n        description: Report and create a new TestCaseResult\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: keycloak-config\n      path: /keycloak/config\n      operations:\n\
  \      - name: getkeycloakconfig\n        method: GET\n        description: Get authentification configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-id-operation\n      path: /services/{id}/operation\n      operations:\n      - name: overrideserviceoperation\n        method: PUT\n        description: Override Service Operation\n        inputParameters:\n        - name: operationName\n          in: query\n          type: string\n          required: true\n          description: Name of operation to update\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-id-metadata\n      path: /services/{id}/metadata\n      operations:\n      - name: updateservicemetadata\n        method: PUT\n        description: Update Service Metadata\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: services-search\n      path: /services/search\n      operations:\n      - name: searchservices\n        method: GET\n        description: Search for Services and APIs\n        inputParameters:\n        - name: queryMap\n          in: query\n          type: object\n          required: true\n          description: Map of criterion. Key can be simply 'name' with value as the searched string. You can also search by\n            label using keys like 'labels.x' where 'x' is the label and\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tests-id-events-testcaseid\n      path: /tests/{id}/events/{testCaseId}\n      operations:\n      - name: geteventsbytestcase\n        method: GET\n        description: Get events for TestCase\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: resources-name\n      path: /resources/{name}\n      operations:\n      - name: getresource\n        method: GET\n        description: Get Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resources-service-serviceid\n      path: /resources/service/{serviceId}\n      operations:\n      - name: getresourcesbyservice\n        method: GET\n        description: Get Resources by Service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: features-config\n      path: /features/config\n      operations:\n      - name: getfeaturesconfig\n        method: GET\n        description: Get features configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: import\n      path: /import\n\
  \      operations:\n      - name: importsnapshot\n        method: POST\n        description: Import a snapshot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: export\n      path: /export\n      operations:\n      - name: exportsnapshot\n        method: GET\n        description: Export a snapshot\n        inputParameters:\n        - name: serviceIds\n          in: query\n          type: array\n          required: true\n          description: List of service identifiers to export\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics-invocations-global\n      path: /metrics/invocations/global\n      operations:\n      - name: getaggregatedinvocationsstats\n        method: GET\n        description: Get aggregated invocation statistics for a day\n        inputParameters:\n        - name: day\n          in: query\n\
  \          type: string\n          description: The day to get statistics for (formatted with yyyyMMdd pattern). Default to today if not provided.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics-conformance-aggregate\n      path: /metrics/conformance/aggregate\n      operations:\n      - name: getconformancemetricsaggregation\n        method: GET\n        description: Get aggregation of conformance metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics-conformance-service-serviceid\n      path: /metrics/conformance/service/{serviceId}\n      operations:\n      - name: getservicetestconformancemetric\n        method: GET\n        description: Get conformance metrics for a Service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n   \
  \       value: $.\n    - name: metrics-invocations-top\n      path: /metrics/invocations/top\n      operations:\n      - name: gettopivnocationsstatsbyday\n        method: GET\n        description: Get top invocation statistics for a day\n        inputParameters:\n        - name: day\n          in: query\n          type: string\n          description: The day to get statistics for (formatted with yyyyMMdd pattern). Default to today if not provided.\n        - name: limit\n          in: query\n          type: integer\n          description: The number of top invoked mocks to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics-invocations-servicename-serviceversion\n      path: /metrics/invocations/{serviceName}/{serviceVersion}\n      operations:\n      - name: getinvocationstatsbyservice\n        method: GET\n        description: Get invocation statistics for Service\n        inputParameters:\n\
  \        - name: day\n          in: query\n          type: string\n          description: The day to get statistics for (formatted with yyyyMMdd pattern). Default to today if not provided.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics-invocations-global-latest\n      path: /metrics/invocations/global/latest\n      operations:\n      - name: getlatestaggregatedinvocationsstats\n        method: GET\n        description: Get aggregated invocations statistics for latest days\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          description: Number of days to get back in time. Default is 20.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics-tests-latest\n      path: /metrics/tests/latest\n      operations:\n      - name: getlatesttestresults\n\
  \        method: GET\n        description: Get latest tests results\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          description: Number of days to consider for test results to return. Default is 7 (one week)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-id-start\n      path: /jobs/{id}/start\n      operations:\n      - name: startimportjob\n        method: PUT\n        description: Start an ImportJob\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-id-stop\n      path: /jobs/{id}/stop\n      operations:\n      - name: stopimportjob\n        method: PUT\n        description: Stop an ImportJob\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-id-activate\n\
  \      path: /jobs/{id}/activate\n      operations:\n      - name: activateimportjob\n        method: PUT\n        description: Activate an ImportJob\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-labels\n      path: /services/labels\n      operations:\n      - name: getserviceslabels\n        method: GET\n        description: Get the already used labels for Services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: artifact-download\n      path: /artifact/download\n      operations:\n      - name: downloadartifact\n        method: POST\n        description: Download an artifact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secrets-search\n      path: /secrets/search\n      operations:\n      - name: searchsecrets\n\
  \        method: GET\n        description: Search for Secrets\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: Search using this name-like criterion\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: artifact-upload\n      path: /artifact/upload\n      operations:\n      - name: uploadartifact\n        method: POST\n        description: Upload an artifact\n        inputParameters:\n        - name: mainArtifact\n          in: query\n          type: boolean\n          required: true\n          description: Flag telling if this should be considered as primary or secondary artifact. Default to 'true'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microcks-rest\n    description:\
  \ REST adapter for Microcks API v1.14.\n    resources:\n    - path: /services\n      name: getservices\n      operations:\n      - method: GET\n        name: getservices\n        description: Get Services and APIs\n        call: microcks.getservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tests\n      name: createtest\n      operations:\n      - method: POST\n        name: createtest\n        description: Create a new Test\n        call: microcks.createtest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services/count\n      name: getservicescounter\n      operations:\n      - method: GET\n        name: getservicescounter\n        description: Get the Services counter\n        call: microcks.getservicescounter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs\n      name: getimportjobs\n      operations:\n      - method: GET\n        name: getimportjobs\n\
  \        description: Get ImportJobs\n        call: microcks.getimportjobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs\n      name: createimportjob\n      operations:\n      - method: POST\n        name: createimportjob\n        description: Create ImportJob\n        call: microcks.createimportjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{id}\n      name: getimportjob\n      operations:\n      - method: GET\n        name: getimportjob\n        description: Get ImportJob\n        call: microcks.getimportjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{id}\n      name: updateimportjob\n      operations:\n      - method: POST\n        name: updateimportjob\n        description: Update ImportJob\n        call: microcks.updateimportjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{id}\n      name:\
  \ deleteimportjob\n      operations:\n      - method: DELETE\n        name: deleteimportjob\n        description: Delete ImportJob\n        call: microcks.deleteimportjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services/{id}\n      name: getservice\n      operations:\n      - method: GET\n        name: getservice\n        description: Get Service\n        call: microcks.getservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services/{id}\n      name: deleteservice\n      operations:\n      - method: DELETE\n        name: deleteservice\n        description: Delete Service\n        call: microcks.deleteservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/count\n      name: getimportjobcounter\n      operations:\n      - method: GET\n        name: getimportjobcounter\n        description: Get the ImportJobs counter\n        call: microcks.getimportjobcounter\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secrets\n      name: getsecrets\n      operations:\n      - method: GET\n        name: getsecrets\n        description: Get Secrets\n        call: microcks.getsecrets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secrets\n      name: createsecret\n      operations:\n      - method: POST\n        name: createsecret\n        description: Create a new Secret\n        call: microcks.createsecret\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secrets/{id}\n      name: getsecret\n      operations:\n      - method: GET\n        name: getsecret\n        description: Get Secret\n        call: microcks.getsecret\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secrets/{id}\n      name: updatesecret\n      operations:\n      - method: PUT\n        name: updatesecret\n        description: Update\
  \ Secret\n        call: microcks.updatesecret\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secrets/{id}\n      name: deletesecret\n      operations:\n      - method: DELETE\n        name: deletesecret\n        description: Delete Secret\n        call: microcks.deletesecret\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secrets/count\n      name: getsecretscounter\n      operations:\n      - method: GET\n        name: getsecretscounter\n        description: Get the Secrets counter\n        call: microcks.getsecretscounter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tests/service/{serviceId}\n      name: gettestresultsbyservice\n      operations:\n      - method: GET\n        name: gettestresultsbyservice\n        description: Get TestResults by Service\n        call: microcks.gettestresultsbyservice\n        outputParameters:\n        - type: object\n         \
  \ mapping: $.\n    - path: /tests/service/{serviceId}/count\n      name: gettestresultsbyservicecounter\n      operations:\n      - method: GET\n        name: gettestresultsbyservicecounter\n        description: Get the TestResults for Service counter\n        call: microcks.gettestresultsbyservicecounter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tests/{id}\n      name: gettestresult\n      operations:\n      - method: GET\n        name: gettestresult\n        description: Get TestResult\n        call: microcks.gettestresult\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tests/{id}/messages/{testCaseId}\n      name: getmessagesbytestcase\n      operations:\n      - method: GET\n        name: getmessagesbytestcase\n        description: Get messages for TestCase\n        call: microcks.getmessagesbytestcase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tests/{id}/testCaseResult\n\
  \      name: reporttestcaseresult\n      operations:\n      - method: POST\n        name: reporttestcaseresult\n        description: Report and create a new TestCaseResult\n        call: microcks.reporttestcaseresult\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /keycloak/config\n      name: getkeycloakconfig\n      operations:\n      - method: GET\n        name: getkeycloakconfig\n        description: Get authentification configuration\n        call: microcks.getkeycloakconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services/{id}/operation\n      name: overrideserviceoperation\n      operations:\n      - method: PUT\n        name: overrideserviceoperation\n        description: Override Service Operation\n        call: microcks.overrideserviceoperation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services/{id}/metadata\n      name: updateservicemetadata\n\
  \      operations:\n      - method: PUT\n        name: updateservicemetadata\n        description: Update Service Metadata\n        call: microcks.updateservicemetadata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services/search\n      name: searchservices\n      operations:\n      - method: GET\n        name: searchservices\n        description: Search for Services and APIs\n        call: microcks.searchservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tests/{id}/events/{testCaseId}\n      name: geteventsbytestcase\n      operations:\n      - method: GET\n        name: geteventsbytestcase\n        description: Get events for TestCase\n        call: microcks.geteventsbytestcase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resources/{name}\n      name: getresource\n      operations:\n      - method: GET\n        name: getresource\n        description: Get\
  \ Resource\n        call: microcks.getresource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resources/service/{serviceId}\n      name: getresourcesbyservice\n      operations:\n      - method: GET\n        name: getresourcesbyservice\n        description: Get Resources by Service\n        call: microcks.getresourcesbyservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /features/config\n      name: getfeaturesconfig\n      operations:\n      - method: GET\n        name: getfeaturesconfig\n        description: Get features configuration\n        call: microcks.getfeaturesconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /import\n      name: importsnapshot\n      operations:\n      - method: POST\n        name: importsnapshot\n        description: Import a snapshot\n        call: microcks.importsnapshot\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n    - path: /export\n      name: exportsnapshot\n      operations:\n      - method: GET\n        name: exportsnapshot\n        description: Export a snapshot\n        call: microcks.exportsnapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics/invocations/global\n      name: getaggregatedinvocationsstats\n      operations:\n      - method: GET\n        name: getaggregatedinvocationsstats\n        description: Get aggregated invocation statistics for a day\n        call: microcks.getaggregatedinvocationsstats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics/conformance/aggregate\n      name: getconformancemetricsaggregation\n      operations:\n      - method: GET\n        name: getconformancemetricsaggregation\n        description: Get aggregation of conformance metrics\n        call: microcks.getconformancemetricsaggregation\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /metrics/conformance/service/{serviceId}\n      name: getservicetestconformancemetric\n      operations:\n      - method: GET\n        name: getservicetestconformancemetric\n        description: Get conformance metrics for a Service\n        call: microcks.getservicetestconformancemetric\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics/invocations/top\n      name: gettopivnocationsstatsbyday\n      operations:\n      - method: GET\n        name: gettopivnocationsstatsbyday\n        description: Get top invocation statistics for a day\n        call: microcks.gettopivnocationsstatsbyday\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics/invocations/{serviceName}/{serviceVersion}\n      name: getinvocationstatsbyservice\n      operations:\n      - method: GET\n        name: getinvocationstatsbyservice\n        description: Get invocation statistics for Service\n\
  \        call: microcks.getinvocationstatsbyservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics/invocations/global/latest\n      name: getlatestaggregatedinvocationsstats\n      operations:\n      - method: GET\n        name: getlatestaggregatedinvocationsstats\n        description: Get aggregated invocations statistics for latest days\n        call: microcks.getlatestaggregatedinvocationsstats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics/tests/latest\n      name: getlatesttestresults\n      operations:\n      - method: GET\n        name: getlatesttestresults\n        description: Get latest tests results\n        call: microcks.getlatesttestresults\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{id}/start\n      name: startimportjob\n      operations:\n      - method: PUT\n        name: startimportjob\n        description: Start an ImportJob\n\
  \        call: microcks.startimportjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{id}/stop\n      name: stopimportjob\n      operations:\n      - method: PUT\n        name: stopimportjob\n        description: Stop an ImportJob\n        call: microcks.stopimportjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/{id}/activate\n      name: activateimportjob\n      operations:\n      - method: PUT\n        name: activateimportjob\n        description: Activate an ImportJob\n        call: microcks.activateimportjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services/labels\n      name: getserviceslabels\n      operations:\n      - method: GET\n        name: getserviceslabels\n        description: Get the already used labels for Services\n        call: microcks.getserviceslabels\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /artifact/download\n      name: downloadartifact\n      operations:\n      - method: POST\n        name: downloadartifact\n        description: Download an artifact\n        call: microcks.downloadartifact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secrets/search\n      name: searchsecrets\n      operations:\n      - method: GET\n        name: searchsecrets\n        description: Search for Secrets\n        call: microcks.searchsecrets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /artifact/upload\n      name: uploadartifact\n      operations:\n      - method: POST\n        name: uploadartifact\n        description: Upload an artifact\n        call: microcks.uploadartifact\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microcks-mcp\n    transport: http\n    description: MCP adapter for Microcks API v1.14 for AI agent\
  \ use.\n    tools:\n    - name: getservices\n      description: Get Services and APIs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microcks.getservices\n      with:\n        page: tools.page\n        size: tools.size\n      inputParameters:\n      - name: page\n        type: integer\n        description: Page of Services to retrieve (starts at and defaults to 0)\n      - name: size\n        type: integer\n        description: Size of a page. Maximum number of Services to include in a response (defaults to 20)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtest\n      description: Create a new Test\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microcks.createtest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getservicescounter\n      description: Get the Services counter\n      hints:\n       \
  \ readOnly: true\n        destructive: false\n        idempotent: true\n      call: microcks.getservicescounter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getimportjobs\n      description: Get ImportJobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microcks.getimportjobs\n      with:\n        page: tools.page\n        size: tools.size\n        name: tools.name\n      inputParameters:\n      - name: page\n        type: integer\n        description: Page of ImportJobs to retrieve (starts at and defaults to 0)\n      - name: size\n        type: integer\n        description: Size of a page. Maximum number of ImportJobs to include in a response (defaults to 20)\n      - name: name\n        type: string\n        description: Name like criter\n\n# --- truncated at 32 KB (45 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/microcks/refs/heads/main/capabilities/microcks-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microcks/refs/heads/main/capabilities/microcks-capability.yaml
tags:
- Microcks
- API
tools:
- description: Get Services and APIs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservices
- description: Create a new Test
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtest
- description: Get the Services counter
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservicescounter
- description: Get ImportJobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getimportjobs
- description: Create ImportJob
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createimportjob
- description: Get ImportJob
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getimportjob
- description: Update ImportJob
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateimportjob
- description: Delete ImportJob
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteimportjob
- description: Get Service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservice
- description: Delete Service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteservice
- description: Get the ImportJobs counter
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getimportjobcounter
- description: Get Secrets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsecrets
- description: Create a new Secret
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsecret
- description: Get Secret
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsecret
- description: Update Secret
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatesecret
- description: Delete Secret
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesecret
- description: Get the Secrets counter
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsecretscounter
- description: Get TestResults by Service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettestresultsbyservice
- description: Get the TestResults for Service counter
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettestresultsbyservicecounter
- description: Get TestResult
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettestresult
- description: Get messages for TestCase
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmessagesbytestcase
- description: Report and create a new TestCaseResult
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: reporttestcaseresult
- description: Get authentification configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getkeycloakconfig
- description: Override Service Operation
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: overrideserviceoperation
- description: Update Service Metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateservicemetadata
- description: Search for Services and APIs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchservices
- description: Get events for TestCase
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteventsbytestcase
- description: Get Resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getresource
- description: Get Resources by Service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getresourcesbyservice
- description: Get features configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfeaturesconfig
- description: Import a snapshot
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: importsnapshot
- description: Export a snapshot
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: exportsnapshot
- description: Get aggregated invocation statistics for a day
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaggregatedinvocationsstats
- description: Get aggregation of conformance metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconformancemetricsaggregation
- description: Get conformance metrics for a Service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservicetestconformancemetric
- description: Get top invocation statistics for a day
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettopivnocationsstatsbyday
- description: Get invocation statistics for Service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinvocationstatsbyservice
- description: Get aggregated invocations statistics for latest days
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlatestaggregatedinvocationsstats
- description: Get latest tests results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlatesttestresults
- description: Start an ImportJob
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: startimportjob
- description: Stop an ImportJob
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: stopimportjob
- description: Activate an ImportJob
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: activateimportjob
- description: Get the already used labels for Services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getserviceslabels
- description: Download an artifact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: downloadartifact
- description: Search for Secrets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchsecrets
- description: Upload an artifact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadartifact
---
