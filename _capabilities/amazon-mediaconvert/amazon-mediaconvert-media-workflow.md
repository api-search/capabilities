---
categories: []
consumed_apis: []
description: Workflow capability for Amazon MediaConvert media processing operations for broadcast engineers and media developers.
layout: capability
name: Amazon MediaConvert Workflow
operations:
- description: List jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Amazon MediaConvert
provider_slug: amazon-mediaconvert
search_terms:
- create job
- associatecertificate
- get job
- list presets
- listjobs
- developer building media processing applications
- canceljob
- listjobtemplates
- engineer managing broadcast media workflows
- listpresets
- Media Developer
- cancel job
- create job template
- workflow
- amazon mediaconvert media processing workflow
- createjobtemplate
- list job templates
- aws media processing and delivery
- list jobs
- manage media processing jobs
- getjob
- media
- media processing
- aws
- broadcasting
- Broadcast Engineer
- associate certificate
- createjob
slug: amazon-mediaconvert-media-workflow
source_filename: amazon-mediaconvert-media-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon MediaConvert Workflow\n  description: Workflow capability for Amazon MediaConvert media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: mediaconvert\n    baseUri: http://mediaconvert.{region}.amazonaws.com\n    description: Amazon MediaConvert REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: default\n      path: /\n      description: Amazon MediaConvert resources\n      operations:\n      - name: associate-certificate\n        method: POST\n        description: AssociateCertificate\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-job\n        method: GET\n        description: GetJob\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: the job ID of the job.\n      - name: cancel-job\n        method: DELETE\n        description: CancelJob\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Job ID of the job to be cancelled.\n      - name: list-jobs\n        method: GET\n        description:\
  \ ListJobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: Optional. Number of jobs, up to twenty, that will be returned at one time.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: Optional. Use this string, provided with the response to a previous request, to request the next batch\n            of jobs.\n        - name: order\n          in: query\n          type: string\n          required: false\n          description: Optional. When you request lists of resources, you can specify whether they are sorted in ASCENDING\n            or DESCENDING order. Default varies by resource.\n        - name: queue\n          in: query\n          type: string\n          required: false\n          description:\
  \ Optional. Provide a queue name to get back only jobs from that queue.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Optional. A job's status can be SUBMITTED, PROGRESSING, COMPLETE, CANCELED, or ERROR.\n        - name: MaxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n      - name: create-job\n        method: POST\n        description: CreateJob\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: list-job-templates\n        method: GET\n        description: ListJobTemplates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Optionally, specify a job template category to limit responses to only job templates from that category.\n        - name: listBy\n          in: query\n          type: string\n          required: false\n          description: Optional. When you request a list of job templates, you can choose to list them alphabetically by NAME\n            or chronologically by CREATION_DATE. If you don't specify, the service will list them by name.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: Optional. Number of job templates, up to twenty, that will be returned at one time.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: Use this string, provided with the response\
  \ to a previous request, to request the next batch of job\n            templates.\n        - name: order\n          in: query\n          type: string\n          required: false\n          description: Optional. When you request lists of resources, you can specify whether they are sorted in ASCENDING\n            or DESCENDING order. Default varies by resource.\n        - name: MaxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n      - name: create-job-template\n        method: POST\n        description: CreateJobTemplate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: list-presets\n        method: GET\n        description: ListPresets\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Optionally, specify a preset category to limit responses to only presets from that category.\n        - name: listBy\n          in: query\n          type: string\n          required: false\n          description: Optional. When you request a list of presets, you can choose to list them alphabetically by NAME or\n            chronologically by CREATION_DATE. If you don't specify, the service will list them by name.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: Optional. Number of presets, up to twenty, that will be returned at one time\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n    \
  \      description: Use this string, provided with the response to a previous request, to request the next batch of presets.\n        - name: order\n          in: query\n          type: string\n          required: false\n          description: Optional. When you request lists of resources, you can specify whether they are sorted in ASCENDING\n            or DESCENDING order. Default varies by resource.\n        - name: MaxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n      - name: create-preset\n        method: POST\n        description: CreatePreset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: list-queues\n        method:\
  \ GET\n        description: ListQueues\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: listBy\n          in: query\n          type: string\n          required: false\n          description: Optional. When you request a list of queues, you can choose to list them alphabetically by NAME or\n            chronologically by CREATION_DATE. If you don't specify, the service will list them by creation date.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: Optional. Number of queues, up to twenty, that will be returned at one time.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: Use this string, provided with the response to a previous request, to request the next batch of queues.\n        - name: order\n          in: query\n\
  \          type: string\n          required: false\n          description: Optional. When you request lists of resources, you can specify whether they are sorted in ASCENDING\n            or DESCENDING order. Default varies by resource.\n        - name: MaxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n      - name: create-queue\n        method: POST\n        description: CreateQueue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-job-template\n        method: GET\n        description: GetJobTemplate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the job template.\n      - name: update-job-template\n        method: PUT\n        description: UpdateJobTemplate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the job template you are modifying\n        body:\n          type: json\n          data: {}\n      - name: delete-job-template\n        method: DELETE\n        description: DeleteJobTemplate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        \
  \  description: The name of the job template to be deleted.\n      - name: get-policy\n        method: GET\n        description: GetPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-policy\n        method: PUT\n        description: PutPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-policy\n        method: DELETE\n        description: DeletePolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-preset\n        method: GET\n        description: GetPreset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: name\n\
  \          in: path\n          type: string\n          required: true\n          description: The name of the preset.\n      - name: update-preset\n        method: PUT\n        description: UpdatePreset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the preset you are modifying.\n        body:\n          type: json\n          data: {}\n      - name: delete-preset\n        method: DELETE\n        description: DeletePreset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the preset to be deleted.\n      - name: get-queue\n       \
  \ method: GET\n        description: GetQueue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the queue that you want information about.\n      - name: update-queue\n        method: PUT\n        description: UpdateQueue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the queue that you are modifying.\n        body:\n          type: json\n          data: {}\n      - name: delete-queue\n        method: DELETE\n        description: DeleteQueue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the queue that you want to delete.\n      - name: describe-endpoints\n        method: POST\n        description: DescribeEndpoints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: MaxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        body:\n          type: json\n          data: {}\n      - name: disassociate-certificate\n        method: DELETE\n        description: DisassociateCertificate\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        inputParameters:\n        - name: arn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the ACM certificate that you want to disassociate from your MediaConvert resource.\n      - name: list-tags-for-resource\n        method: GET\n        description: ListTagsForResource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: arn\n          in: path\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the resource that you want to list tags for. To get the ARN, send\n            a GET request with the resource name.\n      - name: untag-resource\n        method: PUT\n        description: UntagResource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        inputParameters:\n        - name: arn\n          in: path\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the resource that you want to remove tags from. To get the ARN, send\n            a GET request with the resource name.\n        body:\n          type: json\n          data: {}\n      - name: tag-resource\n        method: POST\n        description: TagResource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mediaconvert-workflow-api\n    description: Unified REST API for Amazon MediaConvert workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List\
  \ jobs\n        call: mediaconvert.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mediaconvert-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon MediaConvert workflow management.\n    tools:\n    - name: associate-certificate\n      description: AssociateCertificate\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediaconvert.associate-certificate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job\n      description: GetJob\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mediaconvert.get-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-job\n      description: CancelJob\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediaconvert.cancel-job\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: list-jobs\n      description: ListJobs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mediaconvert.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-job\n      description: CreateJob\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediaconvert.create-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-job-templates\n      description: ListJobTemplates\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mediaconvert.list-job-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-job-template\n      description: CreateJobTemplate\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediaconvert.create-job-template\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-presets\n      description: ListPresets\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: mediaconvert.list-presets\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-mediaconvert/refs/heads/main/capabilities/amazon-mediaconvert-media-workflow.yaml
tags:
- Media
- Broadcasting
- Workflow
tools:
- description: AssociateCertificate
  hints:
    openWorld: true
    readOnly: false
  name: associate-certificate
- description: GetJob
  hints:
    openWorld: true
    readOnly: true
  name: get-job
- description: CancelJob
  hints:
    openWorld: true
    readOnly: false
  name: cancel-job
- description: ListJobs
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
- description: CreateJob
  hints:
    openWorld: true
    readOnly: false
  name: create-job
- description: ListJobTemplates
  hints:
    openWorld: true
    readOnly: true
  name: list-job-templates
- description: CreateJobTemplate
  hints:
    openWorld: true
    readOnly: false
  name: create-job-template
- description: ListPresets
  hints:
    openWorld: true
    readOnly: true
  name: list-presets
---
