---
categories: []
consumed_apis: []
description: AWS X-Ray provides APIs for managing trace data, sampling rules, groups, and encryption configuration. X-Ray helps developers analyze and debug distributed applications by collecting trace data as requests travel through application components.
layout: capability
name: AWS X-Ray API
operations:
- description: AWS X-Ray Upload Trace Segments
  method: POST
  name: puttracesegments
  path: /Traces
- description: AWS X-Ray Get a List of Traces by ID
  method: POST
  name: batchgettraces
  path: /TraceGraph
- description: AWS X-Ray Get Trace Summaries
  method: POST
  name: gettracesummaries
  path: /TraceSummaries
- description: AWS X-Ray Get the Service Graph
  method: POST
  name: getservicegraph
  path: /ServiceGraph
- description: AWS X-Ray Get Time Series Service Statistics
  method: POST
  name: gettimeseriesservicestatistics
  path: /TimeSeriesServiceStatistics
- description: AWS X-Ray Create a Group
  method: POST
  name: creategroup
  path: /Groups
- description: AWS X-Ray Get All Active Groups
  method: POST
  name: getgroups
  path: /GetGroups
- description: AWS X-Ray Get a Group
  method: POST
  name: getgroup
  path: /Group
- description: AWS X-Ray Update a Group
  method: POST
  name: updategroup
  path: /UpdateGroup
- description: AWS X-Ray Delete a Group
  method: POST
  name: deletegroup
  path: /DeleteGroup
- description: AWS X-Ray Get All Sampling Rules
  method: POST
  name: getsamplingrules
  path: /SamplingRules
- description: AWS X-Ray Create a Sampling Rule
  method: POST
  name: createsamplingrule
  path: /CreateSamplingRule
- description: AWS X-Ray Update a Sampling Rule
  method: POST
  name: updatesamplingrule
  path: /UpdateSamplingRule
- description: AWS X-Ray Delete a Sampling Rule
  method: POST
  name: deletesamplingrule
  path: /DeleteSamplingRule
- description: AWS X-Ray Get Sampling Targets
  method: POST
  name: getsamplingtargets
  path: /SamplingTargets
- description: AWS X-Ray Get Encryption Configuration
  method: POST
  name: getencryptionconfig
  path: /EncryptionConfig
- description: AWS X-Ray Update Encryption Configuration
  method: POST
  name: putencryptionconfig
  path: /PutEncryptionConfig
- description: AWS X-Ray List Tags for a Resource
  method: POST
  name: listtagsforresource
  path: /Tags
- description: AWS X-Ray Tag a Resource
  method: POST
  name: tagresource
  path: /TagResource
- description: AWS X-Ray Untag a Resource
  method: POST
  name: untagresource
  path: /UntagResource
- description: AWS X-Ray Get Insight Summaries
  method: POST
  name: getinsightsummaries
  path: /Insights
- description: AWS X-Ray Get Insight Details
  method: POST
  name: getinsight
  path: /Insight
personas: []
provider_name: AWS X-Ray
provider_slug: aws-x-ray
search_terms:
- puttracesegments
- creategroup
- getsamplingrules
- aws x-ray update a sampling rule
- aws
- aws x-ray get encryption configuration
- tagresource
- aws x-ray untag a resource
- deletegroup
- debugging
- aws x-ray get insight details
- deletesamplingrule
- getencryptionconfig
- gettimeseriesservicestatistics
- aws x-ray create a sampling rule
- aws x-ray get sampling targets
- aws x-ray delete a sampling rule
- aws x-ray delete a group
- listtagsforresource
- aws x-ray get the service graph
- aws x-ray update a group
- getsamplingtargets
- aws x-ray get insight summaries
- updatesamplingrule
- aws x-ray tag a resource
- aws x-ray upload trace segments
- aws x-ray get all active groups
- putencryptionconfig
- aws x-ray get a list of traces by id
- untagresource
- getservicegraph
- api
- getgroups
- observability
- aws x-ray get trace summaries
- aws x-ray list tags for a resource
- aws x-ray create a group
- batchgettraces
- ray
- getinsightsummaries
- createsamplingrule
- aws x-ray get all sampling rules
- getgroup
- getinsight
- aws x-ray get time series service statistics
- distributed tracing
- gettracesummaries
- microservices
- aws x-ray update encryption configuration
- updategroup
- aws x-ray get a group
slug: aws-x-ray-capability
source_filename: aws-x-ray-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AWS X-Ray API\n  description: AWS X-Ray provides APIs for managing trace data, sampling rules, groups, and encryption configuration. X-Ray\n    helps developers analyze and debug distributed applications by collecting trace data as requests travel through application\n    components.\n  tags:\n  - Aws\n  - X\n  - Ray\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: aws-x-ray\n    baseUri: https://xray.us-east-1.amazonaws.com\n    description: AWS X-Ray API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{AWS_X_RAY_TOKEN}}'\n    resources:\n    - name: traces\n      path: /Traces\n      operations:\n      - name: puttracesegments\n        method: POST\n        description: AWS X-Ray Upload Trace Segments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: tracegraph\n      path: /TraceGraph\n      operations:\n      - name: batchgettraces\n        method: POST\n        description: AWS X-Ray Get a List of Traces by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tracesummaries\n      path: /TraceSummaries\n      operations:\n      - name: gettracesummaries\n        method: POST\n        description: AWS X-Ray Get Trace Summaries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: servicegraph\n      path: /ServiceGraph\n      operations:\n      - name: getservicegraph\n        method: POST\n        description: AWS X-Ray Get the Service Graph\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: timeseriesservicestatistics\n      path: /TimeSeriesServiceStatistics\n\
  \      operations:\n      - name: gettimeseriesservicestatistics\n        method: POST\n        description: AWS X-Ray Get Time Series Service Statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /Groups\n      operations:\n      - name: creategroup\n        method: POST\n        description: AWS X-Ray Create a Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getgroups\n      path: /GetGroups\n      operations:\n      - name: getgroups\n        method: POST\n        description: AWS X-Ray Get All Active Groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: group\n      path: /Group\n      operations:\n      - name: getgroup\n        method: POST\n        description: AWS X-Ray Get a\
  \ Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: updategroup\n      path: /UpdateGroup\n      operations:\n      - name: updategroup\n        method: POST\n        description: AWS X-Ray Update a Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deletegroup\n      path: /DeleteGroup\n      operations:\n      - name: deletegroup\n        method: POST\n        description: AWS X-Ray Delete a Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: samplingrules\n      path: /SamplingRules\n      operations:\n      - name: getsamplingrules\n        method: POST\n        description: AWS X-Ray Get All Sampling Rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: createsamplingrule\n      path: /CreateSamplingRule\n      operations:\n      - name: createsamplingrule\n        method: POST\n        description: AWS X-Ray Create a Sampling Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: updatesamplingrule\n      path: /UpdateSamplingRule\n      operations:\n      - name: updatesamplingrule\n        method: POST\n        description: AWS X-Ray Update a Sampling Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deletesamplingrule\n      path: /DeleteSamplingRule\n      operations:\n      - name: deletesamplingrule\n        method: POST\n        description: AWS X-Ray Delete a Sampling Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \  - name: samplingtargets\n      path: /SamplingTargets\n      operations:\n      - name: getsamplingtargets\n        method: POST\n        description: AWS X-Ray Get Sampling Targets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: encryptionconfig\n      path: /EncryptionConfig\n      operations:\n      - name: getencryptionconfig\n        method: POST\n        description: AWS X-Ray Get Encryption Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: putencryptionconfig\n      path: /PutEncryptionConfig\n      operations:\n      - name: putencryptionconfig\n        method: POST\n        description: AWS X-Ray Update Encryption Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path:\
  \ /Tags\n      operations:\n      - name: listtagsforresource\n        method: POST\n        description: AWS X-Ray List Tags for a Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tagresource\n      path: /TagResource\n      operations:\n      - name: tagresource\n        method: POST\n        description: AWS X-Ray Tag a Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: untagresource\n      path: /UntagResource\n      operations:\n      - name: untagresource\n        method: POST\n        description: AWS X-Ray Untag a Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights\n      path: /Insights\n      operations:\n      - name: getinsightsummaries\n        method: POST\n        description:\
  \ AWS X-Ray Get Insight Summaries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insight\n      path: /Insight\n      operations:\n      - name: getinsight\n        method: POST\n        description: AWS X-Ray Get Insight Details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: aws-x-ray-rest\n    description: REST adapter for AWS X-Ray API.\n    resources:\n    - path: /Traces\n      name: puttracesegments\n      operations:\n      - method: POST\n        name: puttracesegments\n        description: AWS X-Ray Upload Trace Segments\n        call: aws-x-ray.puttracesegments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /TraceGraph\n      name: batchgettraces\n      operations:\n      - method: POST\n        name: batchgettraces\n\
  \        description: AWS X-Ray Get a List of Traces by ID\n        call: aws-x-ray.batchgettraces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /TraceSummaries\n      name: gettracesummaries\n      operations:\n      - method: POST\n        name: gettracesummaries\n        description: AWS X-Ray Get Trace Summaries\n        call: aws-x-ray.gettracesummaries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ServiceGraph\n      name: getservicegraph\n      operations:\n      - method: POST\n        name: getservicegraph\n        description: AWS X-Ray Get the Service Graph\n        call: aws-x-ray.getservicegraph\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /TimeSeriesServiceStatistics\n      name: gettimeseriesservicestatistics\n      operations:\n      - method: POST\n        name: gettimeseriesservicestatistics\n        description: AWS X-Ray Get Time Series Service\
  \ Statistics\n        call: aws-x-ray.gettimeseriesservicestatistics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Groups\n      name: creategroup\n      operations:\n      - method: POST\n        name: creategroup\n        description: AWS X-Ray Create a Group\n        call: aws-x-ray.creategroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetGroups\n      name: getgroups\n      operations:\n      - method: POST\n        name: getgroups\n        description: AWS X-Ray Get All Active Groups\n        call: aws-x-ray.getgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Group\n      name: getgroup\n      operations:\n      - method: POST\n        name: getgroup\n        description: AWS X-Ray Get a Group\n        call: aws-x-ray.getgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /UpdateGroup\n      name: updategroup\n\
  \      operations:\n      - method: POST\n        name: updategroup\n        description: AWS X-Ray Update a Group\n        call: aws-x-ray.updategroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /DeleteGroup\n      name: deletegroup\n      operations:\n      - method: POST\n        name: deletegroup\n        description: AWS X-Ray Delete a Group\n        call: aws-x-ray.deletegroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /SamplingRules\n      name: getsamplingrules\n      operations:\n      - method: POST\n        name: getsamplingrules\n        description: AWS X-Ray Get All Sampling Rules\n        call: aws-x-ray.getsamplingrules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /CreateSamplingRule\n      name: createsamplingrule\n      operations:\n      - method: POST\n        name: createsamplingrule\n        description: AWS X-Ray Create a Sampling Rule\n\
  \        call: aws-x-ray.createsamplingrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /UpdateSamplingRule\n      name: updatesamplingrule\n      operations:\n      - method: POST\n        name: updatesamplingrule\n        description: AWS X-Ray Update a Sampling Rule\n        call: aws-x-ray.updatesamplingrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /DeleteSamplingRule\n      name: deletesamplingrule\n      operations:\n      - method: POST\n        name: deletesamplingrule\n        description: AWS X-Ray Delete a Sampling Rule\n        call: aws-x-ray.deletesamplingrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /SamplingTargets\n      name: getsamplingtargets\n      operations:\n      - method: POST\n        name: getsamplingtargets\n        description: AWS X-Ray Get Sampling Targets\n        call: aws-x-ray.getsamplingtargets\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /EncryptionConfig\n      name: getencryptionconfig\n      operations:\n      - method: POST\n        name: getencryptionconfig\n        description: AWS X-Ray Get Encryption Configuration\n        call: aws-x-ray.getencryptionconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /PutEncryptionConfig\n      name: putencryptionconfig\n      operations:\n      - method: POST\n        name: putencryptionconfig\n        description: AWS X-Ray Update Encryption Configuration\n        call: aws-x-ray.putencryptionconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Tags\n      name: listtagsforresource\n      operations:\n      - method: POST\n        name: listtagsforresource\n        description: AWS X-Ray List Tags for a Resource\n        call: aws-x-ray.listtagsforresource\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /TagResource\n      name: tagresource\n      operations:\n      - method: POST\n        name: tagresource\n        description: AWS X-Ray Tag a Resource\n        call: aws-x-ray.tagresource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /UntagResource\n      name: untagresource\n      operations:\n      - method: POST\n        name: untagresource\n        description: AWS X-Ray Untag a Resource\n        call: aws-x-ray.untagresource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Insights\n      name: getinsightsummaries\n      operations:\n      - method: POST\n        name: getinsightsummaries\n        description: AWS X-Ray Get Insight Summaries\n        call: aws-x-ray.getinsightsummaries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /Insight\n      name: getinsight\n      operations:\n      - method: POST\n        name: getinsight\n        description:\
  \ AWS X-Ray Get Insight Details\n        call: aws-x-ray.getinsight\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: aws-x-ray-mcp\n    transport: http\n    description: MCP adapter for AWS X-Ray API for AI agent use.\n    tools:\n    - name: puttracesegments\n      description: AWS X-Ray Upload Trace Segments\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.puttracesegments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batchgettraces\n      description: AWS X-Ray Get a List of Traces by ID\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.batchgettraces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettracesummaries\n      description: AWS X-Ray Get Trace Summaries\n      hints:\n        readOnly: false\n       \
  \ destructive: false\n        idempotent: false\n      call: aws-x-ray.gettracesummaries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getservicegraph\n      description: AWS X-Ray Get the Service Graph\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.getservicegraph\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettimeseriesservicestatistics\n      description: AWS X-Ray Get Time Series Service Statistics\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.gettimeseriesservicestatistics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategroup\n      description: AWS X-Ray Create a Group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.creategroup\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: getgroups\n      description: AWS X-Ray Get All Active Groups\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.getgroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgroup\n      description: AWS X-Ray Get a Group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.getgroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updategroup\n      description: AWS X-Ray Update a Group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.updategroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletegroup\n      description: AWS X-Ray Delete a Group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ aws-x-ray.deletegroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsamplingrules\n      description: AWS X-Ray Get All Sampling Rules\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.getsamplingrules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsamplingrule\n      description: AWS X-Ray Create a Sampling Rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.createsamplingrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesamplingrule\n      description: AWS X-Ray Update a Sampling Rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.updatesamplingrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesamplingrule\n      description:\
  \ AWS X-Ray Delete a Sampling Rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.deletesamplingrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsamplingtargets\n      description: AWS X-Ray Get Sampling Targets\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.getsamplingtargets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getencryptionconfig\n      description: AWS X-Ray Get Encryption Configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.getencryptionconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putencryptionconfig\n      description: AWS X-Ray Update Encryption Configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: aws-x-ray.putencryptionconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtagsforresource\n      description: AWS X-Ray List Tags for a Resource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.listtagsforresource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tagresource\n      description: AWS X-Ray Tag a Resource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.tagresource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: untagresource\n      description: AWS X-Ray Untag a Resource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.untagresource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinsightsummaries\n      description:\
  \ AWS X-Ray Get Insight Summaries\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.getinsightsummaries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinsight\n      description: AWS X-Ray Get Insight Details\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-x-ray.getinsight\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AWS_X_RAY_TOKEN: AWS_X_RAY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aws-x-ray/refs/heads/main/capabilities/aws-x-ray-capability.yaml
tags:
- Aws
- X
- Ray
- API
tools:
- description: AWS X-Ray Upload Trace Segments
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: puttracesegments
- description: AWS X-Ray Get a List of Traces by ID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: batchgettraces
- description: AWS X-Ray Get Trace Summaries
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: gettracesummaries
- description: AWS X-Ray Get the Service Graph
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getservicegraph
- description: AWS X-Ray Get Time Series Service Statistics
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: gettimeseriesservicestatistics
- description: AWS X-Ray Create a Group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: AWS X-Ray Get All Active Groups
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getgroups
- description: AWS X-Ray Get a Group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getgroup
- description: AWS X-Ray Update a Group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updategroup
- description: AWS X-Ray Delete a Group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deletegroup
- description: AWS X-Ray Get All Sampling Rules
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getsamplingrules
- description: AWS X-Ray Create a Sampling Rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsamplingrule
- description: AWS X-Ray Update a Sampling Rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatesamplingrule
- description: AWS X-Ray Delete a Sampling Rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deletesamplingrule
- description: AWS X-Ray Get Sampling Targets
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getsamplingtargets
- description: AWS X-Ray Get Encryption Configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getencryptionconfig
- description: AWS X-Ray Update Encryption Configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: putencryptionconfig
- description: AWS X-Ray List Tags for a Resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listtagsforresource
- description: AWS X-Ray Tag a Resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: tagresource
- description: AWS X-Ray Untag a Resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: untagresource
- description: AWS X-Ray Get Insight Summaries
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getinsightsummaries
- description: AWS X-Ray Get Insight Details
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getinsight
---
