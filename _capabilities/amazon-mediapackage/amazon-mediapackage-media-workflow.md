---
categories: []
consumed_apis: []
description: Workflow capability for Amazon MediaPackage media processing operations for broadcast engineers and media developers.
layout: capability
name: Amazon MediaPackage Workflow
operations:
- description: List jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Amazon MediaPackage
provider_slug: amazon-mediapackage
search_terms:
- aws
- amazon mediapackage media processing workflow
- list jobs
- Broadcast Engineer
- workflow
- create harvest job
- describechannel
- configurelogs
- list harvest jobs
- createharvestjob
- listharvestjobs
- listchannels
- configure logs
- createchannel
- createoriginendpoint
- aws media processing and delivery
- manage media processing jobs
- media processing
- media
- create channel
- describe channel
- developer building media processing applications
- list channels
- Media Developer
- broadcasting
- listoriginendpoints
- engineer managing broadcast media workflows
- list origin endpoints
- create origin endpoint
slug: amazon-mediapackage-media-workflow
source_filename: amazon-mediapackage-media-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon MediaPackage Workflow\n  description: Workflow capability for Amazon MediaPackage media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: mediapackage\n    baseUri: http://mediapackage.{region}.amazonaws.com\n    description: Amazon MediaPackage REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: default\n      path: /\n      description: Amazon MediaPackage resources\n      operations:\n      - name: configure-logs\n        method: PUT\n        description: ConfigureLogs\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the channel to log subscription.\n        body:\n          type: json\n          data: {}\n      - name: list-channels\n        method: GET\n        description: ListChannels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: Upper bound on number of records to return.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: A token used to resume pagination from the end of a previous request.\n        - name: MaxResults\n       \
  \   in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n      - name: create-channel\n        method: POST\n        description: CreateChannel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: list-harvest-jobs\n        method: GET\n        description: ListHarvestJobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: includeChannelId\n          in: query\n          type: string\n          required: false\n          description: When specified, the request will return only HarvestJobs associated with the given Channel ID.\n        - name:\
  \ includeStatus\n          in: query\n          type: string\n          required: false\n          description: When specified, the request will return only HarvestJobs in the given status.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The upper bound on the number of records to return.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: A token used to resume pagination from the end of a previous request.\n        - name: MaxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n      - name: create-harvest-job\n        method: POST\n        description: CreateHarvestJob\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: list-origin-endpoints\n        method: GET\n        description: ListOriginEndpoints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: channelId\n          in: query\n          type: string\n          required: false\n          description: When specified, the request will return only OriginEndpoints associated with the given Channel ID.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The upper bound on the number of records to return.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: A token used to resume pagination from the end of a previous request.\n        - name: MaxResults\n   \
  \       in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n      - name: create-origin-endpoint\n        method: POST\n        description: CreateOriginEndpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: describe-channel\n        method: GET\n        description: DescribeChannel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of a Channel.\n      - name: update-channel\n        method: PUT\n        description: UpdateChannel\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the Channel to update.\n        body:\n          type: json\n          data: {}\n      - name: delete-channel\n        method: DELETE\n        description: DeleteChannel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the Channel to delete.\n      - name: describe-origin-endpoint\n        method: GET\n        description: DescribeOriginEndpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the OriginEndpoint.\n      - name: update-origin-endpoint\n        method: PUT\n        description: UpdateOriginEndpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the OriginEndpoint to update.\n        body:\n          type: json\n          data: {}\n      - name: delete-origin-endpoint\n        method: DELETE\n        description: DeleteOriginEndpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the OriginEndpoint\
  \ to delete.\n      - name: describe-harvest-job\n        method: GET\n        description: DescribeHarvestJob\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the HarvestJob.\n      - name: list-tags-for-resource\n        method: GET\n        description: ListTagsForResource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: resource-arn\n          in: path\n          type: string\n          required: true\n          description: ''\n      - name: tag-resource\n        method: POST\n        description: TagResource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \      inputParameters:\n        - name: resource-arn\n          in: path\n          type: string\n          required: true\n          description: ''\n        body:\n          type: json\n          data: {}\n      - name: rotate-channel-credentials\n        method: PUT\n        description: RotateChannelCredentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the channel to update.\n        body:\n          type: json\n          data: {}\n      - name: rotate-ingest-endpoint-credentials\n        method: PUT\n        description: RotateIngestEndpointCredentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: id\n          in: path\n     \
  \     type: string\n          required: true\n          description: The ID of the channel the IngestEndpoint is on.\n        - name: ingest_endpoint_id\n          in: path\n          type: string\n          required: true\n          description: The id of the IngestEndpoint whose credentials should be rotated\n        body:\n          type: json\n          data: {}\n      - name: untag-resource\n        method: DELETE\n        description: UntagResource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: resource-arn\n          in: path\n          type: string\n          required: true\n          description: ''\n        - name: tagKeys\n          in: query\n          type: array\n          required: true\n          description: The key(s) of tag to be deleted\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mediapackage-workflow-api\n    description: Unified\
  \ REST API for Amazon MediaPackage workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: mediapackage.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mediapackage-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon MediaPackage workflow management.\n    tools:\n    - name: configure-logs\n      description: ConfigureLogs\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediapackage.configure-logs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-channels\n      description: ListChannels\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mediapackage.list-channels\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: create-channel\n      description: CreateChannel\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediapackage.create-channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-harvest-jobs\n      description: ListHarvestJobs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mediapackage.list-harvest-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-harvest-job\n      description: CreateHarvestJob\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediapackage.create-harvest-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-origin-endpoints\n      description: ListOriginEndpoints\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mediapackage.list-origin-endpoints\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: create-origin-endpoint\n      description: CreateOriginEndpoint\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediapackage.create-origin-endpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-channel\n      description: DescribeChannel\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mediapackage.describe-channel\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-mediapackage/refs/heads/main/capabilities/amazon-mediapackage-media-workflow.yaml
tags:
- Media
- Broadcasting
- Workflow
tools:
- description: ConfigureLogs
  hints:
    openWorld: true
    readOnly: false
  name: configure-logs
- description: ListChannels
  hints:
    openWorld: true
    readOnly: true
  name: list-channels
- description: CreateChannel
  hints:
    openWorld: true
    readOnly: false
  name: create-channel
- description: ListHarvestJobs
  hints:
    openWorld: true
    readOnly: true
  name: list-harvest-jobs
- description: CreateHarvestJob
  hints:
    openWorld: true
    readOnly: false
  name: create-harvest-job
- description: ListOriginEndpoints
  hints:
    openWorld: true
    readOnly: true
  name: list-origin-endpoints
- description: CreateOriginEndpoint
  hints:
    openWorld: true
    readOnly: false
  name: create-origin-endpoint
- description: DescribeChannel
  hints:
    openWorld: true
    readOnly: true
  name: describe-channel
---
