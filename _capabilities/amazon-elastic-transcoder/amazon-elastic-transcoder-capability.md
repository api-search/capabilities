---
categories: []
consumed_apis: []
description: <fullname>AWS Elastic Transcoder Service</fullname> <p>The AWS Elastic Transcoder Service.</p>
layout: capability
name: Amazon Elastic Transcoder
operations:
- description: Amazon Elastic Transcoder CancelJob
  method: DELETE
  name: canceljob
  path: /2012-09-25/jobs/{Id}
- description: Amazon Elastic Transcoder ReadJob
  method: GET
  name: readjob
  path: /2012-09-25/jobs/{Id}
- description: Amazon Elastic Transcoder CreateJob
  method: POST
  name: createjob
  path: /2012-09-25/jobs
- description: Amazon Elastic Transcoder CreatePipeline
  method: POST
  name: createpipeline
  path: /2012-09-25/pipelines
- description: Amazon Elastic Transcoder ListPipelines
  method: GET
  name: listpipelines
  path: /2012-09-25/pipelines
- description: Amazon Elastic Transcoder CreatePreset
  method: POST
  name: createpreset
  path: /2012-09-25/presets
- description: Amazon Elastic Transcoder ListPresets
  method: GET
  name: listpresets
  path: /2012-09-25/presets
- description: Amazon Elastic Transcoder DeletePipeline
  method: DELETE
  name: deletepipeline
  path: /2012-09-25/pipelines/{Id}
- description: Amazon Elastic Transcoder ReadPipeline
  method: GET
  name: readpipeline
  path: /2012-09-25/pipelines/{Id}
- description: Amazon Elastic Transcoder UpdatePipeline
  method: PUT
  name: updatepipeline
  path: /2012-09-25/pipelines/{Id}
- description: Amazon Elastic Transcoder DeletePreset
  method: DELETE
  name: deletepreset
  path: /2012-09-25/presets/{Id}
- description: Amazon Elastic Transcoder ReadPreset
  method: GET
  name: readpreset
  path: /2012-09-25/presets/{Id}
- description: Amazon Elastic Transcoder ListJobsByPipeline
  method: GET
  name: listjobsbypipeline
  path: /2012-09-25/jobsByPipeline/{PipelineId}
- description: Amazon Elastic Transcoder ListJobsByStatus
  method: GET
  name: listjobsbystatus
  path: /2012-09-25/jobsByStatus/{Status}
- description: Amazon Elastic Transcoder TestRole
  method: POST
  name: testrole
  path: /2012-09-25/roleTests
- description: Amazon Elastic Transcoder UpdatePipelineNotifications
  method: POST
  name: updatepipelinenotifications
  path: /2012-09-25/pipelines/{Id}/notifications
- description: Amazon Elastic Transcoder UpdatePipelineStatus
  method: POST
  name: updatepipelinestatus
  path: /2012-09-25/pipelines/{Id}/status
personas: []
provider_name: Amazon Elastic Transcoder
provider_slug: amazon-elastic-transcoder
search_terms:
- video
- readpipeline
- amazon elastic transcoder updatepipelinestatus
- amazon web services
- amazon elastic transcoder readjob
- transcoder
- api
- deletepipeline
- amazon elastic transcoder createpreset
- amazon elastic transcoder updatepipelinenotifications
- updatepipelinenotifications
- amazon elastic transcoder createjob
- amazon elastic transcoder updatepipeline
- updatepipeline
- amazon
- unified capability for managing amazon elastic transcoder resources. combines amazon elastic transcoder apis for media engineer workflows in media processing.
- amazon elastic transcoder readpreset
- updatepipelinestatus
- amazon elastic transcoder listpresets
- canceljob
- readpreset
- deletepreset
- amazon elastic transcoder listpipelines
- listpresets
- elastic
- developers building applications using amazon elastic transcoder
- amazon elastic transcoder deletepipeline
- amazon elastic transcoder listjobsbypipeline
- createpreset
- createpipeline
- transcoding
- amazon elastic transcoder listjobsbystatus
- media transcoding service for converting media files to various formats
- listpipelines
- media
- amazon elastic transcoder createpipeline
- amazon elastic transcoder deletepreset
- amazon elastic transcoder testrole
- testrole
- readjob
- listjobsbystatus
- listjobsbypipeline
- operations teams managing amazon elastic transcoder infrastructure
- amazon elastic transcoder canceljob
- amazon elastic transcoder readpipeline
- createjob
slug: amazon-elastic-transcoder-capability
source_filename: amazon-elastic-transcoder-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Elastic Transcoder\n  description: <fullname>AWS Elastic Transcoder Service</fullname> <p>The AWS Elastic Transcoder Service.</p>\n  tags:\n  - Amazon\n  - Elastic\n  - Transcoder\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-elastic-transcoder\n    baseUri: http://elastictranscoder.us-east-1.amazonaws.com\n    description: Amazon Elastic Transcoder HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{AMAZON_ELASTIC_TRANSCODER_TOKEN}}'\n    resources:\n    - name: 2012-09-25-jobs-id\n      path: /2012-09-25/jobs/{Id}\n      operations:\n      - name: canceljob\n        method: DELETE\n        description: Amazon Elastic Transcoder CancelJob\n        inputParameters:\n        - name: Id\n          in: path\n          type: string\n          required: true\n          description: <p>The identifier\
  \ of the job that you want to cancel.</p> <p>To get a list of the jobs (including their\n            <code>jobId</code>) that have a status of <code>Submitte\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: readjob\n        method: GET\n        description: Amazon Elastic Transcoder ReadJob\n        inputParameters:\n        - name: Id\n          in: path\n          type: string\n          required: true\n          description: The identifier of the job for which you want to get detailed information.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2012-09-25-jobs\n      path: /2012-09-25/jobs\n      operations:\n      - name: createjob\n        method: POST\n        description: Amazon Elastic Transcoder CreateJob\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n    - name: 2012-09-25-pipelines\n      path: /2012-09-25/pipelines\n      operations:\n      - name: createpipeline\n        method: POST\n        description: Amazon Elastic Transcoder CreatePipeline\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listpipelines\n        method: GET\n        description: Amazon Elastic Transcoder ListPipelines\n        inputParameters:\n        - name: Ascending\n          in: query\n          type: string\n          description: To list pipelines in chronological order by the date and time that they were created, enter <code>true</code>.\n            To list pipelines in reverse chronological order,\n        - name: PageToken\n          in: query\n          type: string\n          description: When Elastic Transcoder returns more than one page of results, use <code>pageToken</code> in subsequent\n            <code>GET</code>\
  \ requests to get each successive page of\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2012-09-25-presets\n      path: /2012-09-25/presets\n      operations:\n      - name: createpreset\n        method: POST\n        description: Amazon Elastic Transcoder CreatePreset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listpresets\n        method: GET\n        description: Amazon Elastic Transcoder ListPresets\n        inputParameters:\n        - name: Ascending\n          in: query\n          type: string\n          description: To list presets in chronological order by the date and time that they were created, enter <code>true</code>.\n            To list presets in reverse chronological order, ent\n        - name: PageToken\n          in: query\n          type: string\n          description: When Elastic\
  \ Transcoder returns more than one page of results, use <code>pageToken</code> in subsequent\n            <code>GET</code> requests to get each successive page of\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2012-09-25-pipelines-id\n      path: /2012-09-25/pipelines/{Id}\n      operations:\n      - name: deletepipeline\n        method: DELETE\n        description: Amazon Elastic Transcoder DeletePipeline\n        inputParameters:\n        - name: Id\n          in: path\n          type: string\n          required: true\n          description: The identifier of the pipeline that you want to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: readpipeline\n        method: GET\n        description: Amazon Elastic Transcoder ReadPipeline\n        inputParameters:\n        - name: Id\n          in: path\n\
  \          type: string\n          required: true\n          description: The identifier of the pipeline to read.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepipeline\n        method: PUT\n        description: Amazon Elastic Transcoder UpdatePipeline\n        inputParameters:\n        - name: Id\n          in: path\n          type: string\n          required: true\n          description: The ID of the pipeline that you want to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2012-09-25-presets-id\n      path: /2012-09-25/presets/{Id}\n      operations:\n      - name: deletepreset\n        method: DELETE\n        description: Amazon Elastic Transcoder DeletePreset\n        inputParameters:\n        - name: Id\n          in: path\n          type: string\n          required: true\n       \
  \   description: The identifier of the preset for which you want to get detailed information.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: readpreset\n        method: GET\n        description: Amazon Elastic Transcoder ReadPreset\n        inputParameters:\n        - name: Id\n          in: path\n          type: string\n          required: true\n          description: The identifier of the preset for which you want to get detailed information.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2012-09-25-jobsbypipeline-pipelineid\n      path: /2012-09-25/jobsByPipeline/{PipelineId}\n      operations:\n      - name: listjobsbypipeline\n        method: GET\n        description: Amazon Elastic Transcoder ListJobsByPipeline\n        inputParameters:\n        - name: PipelineId\n          in: path\n         \
  \ type: string\n          required: true\n          description: The ID of the pipeline for which you want to get job information.\n        - name: Ascending\n          in: query\n          type: string\n          description: To list jobs in chronological order by the date and time that they were submitted, enter <code>true</code>.\n            To list jobs in reverse chronological order, enter <\n        - name: PageToken\n          in: query\n          type: string\n          description: When Elastic Transcoder returns more than one page of results, use <code>pageToken</code> in subsequent\n            <code>GET</code> requests to get each successive page of\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2012-09-25-jobsbystatus-status\n      path: /2012-09-25/jobsByStatus/{Status}\n      operations:\n      - name: listjobsbystatus\n        method: GET\n        description: Amazon Elastic Transcoder\
  \ ListJobsByStatus\n        inputParameters:\n        - name: Status\n          in: path\n          type: string\n          required: true\n          description: 'To get information about all of the jobs associated with the current AWS account that have a given\n            status, specify the following status: <code>Submitted</code>,'\n        - name: Ascending\n          in: query\n          type: string\n          description: To list jobs in chronological order by the date and time that they were submitted, enter <code>true</code>.\n            To list jobs in reverse chronological order, enter <\n        - name: PageToken\n          in: query\n          type: string\n          description: When Elastic Transcoder returns more than one page of results, use <code>pageToken</code> in subsequent\n            <code>GET</code> requests to get each successive page of\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: 2012-09-25-roletests\n      path: /2012-09-25/roleTests\n      operations:\n      - name: testrole\n        method: POST\n        description: Amazon Elastic Transcoder TestRole\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2012-09-25-pipelines-id-notifications\n      path: /2012-09-25/pipelines/{Id}/notifications\n      operations:\n      - name: updatepipelinenotifications\n        method: POST\n        description: Amazon Elastic Transcoder UpdatePipelineNotifications\n        inputParameters:\n        - name: Id\n          in: path\n          type: string\n          required: true\n          description: The identifier of the pipeline for which you want to change notification settings.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2012-09-25-pipelines-id-status\n      path: /2012-09-25/pipelines/{Id}/status\n\
  \      operations:\n      - name: updatepipelinestatus\n        method: POST\n        description: Amazon Elastic Transcoder UpdatePipelineStatus\n        inputParameters:\n        - name: Id\n          in: path\n          type: string\n          required: true\n          description: The identifier of the pipeline to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-elastic-transcoder-rest\n    description: REST adapter for Amazon Elastic Transcoder.\n    resources:\n    - path: /2012-09-25/jobs/{Id}\n      name: canceljob\n      operations:\n      - method: DELETE\n        name: canceljob\n        description: Amazon Elastic Transcoder CancelJob\n        call: amazon-elastic-transcoder.canceljob\n        with:\n          Id: rest.Id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/jobs/{Id}\n\
  \      name: readjob\n      operations:\n      - method: GET\n        name: readjob\n        description: Amazon Elastic Transcoder ReadJob\n        call: amazon-elastic-transcoder.readjob\n        with:\n          Id: rest.Id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/jobs\n      name: createjob\n      operations:\n      - method: POST\n        name: createjob\n        description: Amazon Elastic Transcoder CreateJob\n        call: amazon-elastic-transcoder.createjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/pipelines\n      name: createpipeline\n      operations:\n      - method: POST\n        name: createpipeline\n        description: Amazon Elastic Transcoder CreatePipeline\n        call: amazon-elastic-transcoder.createpipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/pipelines\n      name: listpipelines\n      operations:\n\
  \      - method: GET\n        name: listpipelines\n        description: Amazon Elastic Transcoder ListPipelines\n        call: amazon-elastic-transcoder.listpipelines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/presets\n      name: createpreset\n      operations:\n      - method: POST\n        name: createpreset\n        description: Amazon Elastic Transcoder CreatePreset\n        call: amazon-elastic-transcoder.createpreset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/presets\n      name: listpresets\n      operations:\n      - method: GET\n        name: listpresets\n        description: Amazon Elastic Transcoder ListPresets\n        call: amazon-elastic-transcoder.listpresets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/pipelines/{Id}\n      name: deletepipeline\n      operations:\n      - method: DELETE\n        name: deletepipeline\n\
  \        description: Amazon Elastic Transcoder DeletePipeline\n        call: amazon-elastic-transcoder.deletepipeline\n        with:\n          Id: rest.Id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/pipelines/{Id}\n      name: readpipeline\n      operations:\n      - method: GET\n        name: readpipeline\n        description: Amazon Elastic Transcoder ReadPipeline\n        call: amazon-elastic-transcoder.readpipeline\n        with:\n          Id: rest.Id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/pipelines/{Id}\n      name: updatepipeline\n      operations:\n      - method: PUT\n        name: updatepipeline\n        description: Amazon Elastic Transcoder UpdatePipeline\n        call: amazon-elastic-transcoder.updatepipeline\n        with:\n          Id: rest.Id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/presets/{Id}\n\
  \      name: deletepreset\n      operations:\n      - method: DELETE\n        name: deletepreset\n        description: Amazon Elastic Transcoder DeletePreset\n        call: amazon-elastic-transcoder.deletepreset\n        with:\n          Id: rest.Id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/presets/{Id}\n      name: readpreset\n      operations:\n      - method: GET\n        name: readpreset\n        description: Amazon Elastic Transcoder ReadPreset\n        call: amazon-elastic-transcoder.readpreset\n        with:\n          Id: rest.Id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/jobsByPipeline/{PipelineId}\n      name: listjobsbypipeline\n      operations:\n      - method: GET\n        name: listjobsbypipeline\n        description: Amazon Elastic Transcoder ListJobsByPipeline\n        call: amazon-elastic-transcoder.listjobsbypipeline\n        with:\n          PipelineId: rest.PipelineId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/jobsByStatus/{Status}\n      name: listjobsbystatus\n      operations:\n      - method: GET\n        name: listjobsbystatus\n        description: Amazon Elastic Transcoder ListJobsByStatus\n        call: amazon-elastic-transcoder.listjobsbystatus\n        with:\n          Status: rest.Status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/roleTests\n      name: testrole\n      operations:\n      - method: POST\n        name: testrole\n        description: Amazon Elastic Transcoder TestRole\n        call: amazon-elastic-transcoder.testrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/pipelines/{Id}/notifications\n      name: updatepipelinenotifications\n      operations:\n      - method: POST\n        name: updatepipelinenotifications\n        description: Amazon Elastic Transcoder UpdatePipelineNotifications\n\
  \        call: amazon-elastic-transcoder.updatepipelinenotifications\n        with:\n          Id: rest.Id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2012-09-25/pipelines/{Id}/status\n      name: updatepipelinestatus\n      operations:\n      - method: POST\n        name: updatepipelinestatus\n        description: Amazon Elastic Transcoder UpdatePipelineStatus\n        call: amazon-elastic-transcoder.updatepipelinestatus\n        with:\n          Id: rest.Id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-elastic-transcoder-mcp\n    transport: http\n    description: MCP adapter for Amazon Elastic Transcoder for AI agent use.\n    tools:\n    - name: canceljob\n      description: Amazon Elastic Transcoder CancelJob\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amazon-elastic-transcoder.canceljob\n      with:\n\
  \        Id: tools.Id\n      inputParameters:\n      - name: Id\n        type: string\n        description: <p>The identifier of the job that you want to cancel.</p> <p>To get a list of the jobs (including their\n          <code>jobId</code>) that have a status of <code>Submitte\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readjob\n      description: Amazon Elastic Transcoder ReadJob\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-transcoder.readjob\n      with:\n        Id: tools.Id\n      inputParameters:\n      - name: Id\n        type: string\n        description: The identifier of the job for which you want to get detailed information.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createjob\n      description: Amazon Elastic Transcoder CreateJob\n      hints:\n        readOnly: false\n       \
  \ destructive: false\n        idempotent: false\n      call: amazon-elastic-transcoder.createjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpipeline\n      description: Amazon Elastic Transcoder CreatePipeline\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-elastic-transcoder.createpipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpipelines\n      description: Amazon Elastic Transcoder ListPipelines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-transcoder.listpipelines\n      with:\n        Ascending: tools.Ascending\n        PageToken: tools.PageToken\n      inputParameters:\n      - name: Ascending\n        type: string\n        description: To list pipelines in chronological order by the date and time that they were created, enter <code>true</code>.\n       \
  \   To list pipelines in reverse chronological order,\n      - name: PageToken\n        type: string\n        description: When Elastic Transcoder returns more than one page of results, use <code>pageToken</code> in subsequent\n          <code>GET</code> requests to get each successive page of\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpreset\n      description: Amazon Elastic Transcoder CreatePreset\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-elastic-transcoder.createpreset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpresets\n      description: Amazon Elastic Transcoder ListPresets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-transcoder.listpresets\n      with:\n        Ascending: tools.Ascending\n        PageToken: tools.PageToken\n      inputParameters:\n \
  \     - name: Ascending\n        type: string\n        description: To list presets in chronological order by the date and time that they were created, enter <code>true</code>.\n          To list presets in reverse chronological order, ent\n      - name: PageToken\n        type: string\n        description: When Elastic Transcoder returns more than one page of results, use <code>pageToken</code> in subsequent\n          <code>GET</code> requests to get each successive page of\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletepipeline\n      description: Amazon Elastic Transcoder DeletePipeline\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amazon-elastic-transcoder.deletepipeline\n      with:\n        Id: tools.Id\n      inputParameters:\n      - name: Id\n        type: string\n        description: The identifier of the pipeline that you want to delete.\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: readpipeline\n      description: Amazon Elastic Transcoder ReadPipeline\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-transcoder.readpipeline\n      with:\n        Id: tools.Id\n      inputParameters:\n      - name: Id\n        type: string\n        description: The identifier of the pipeline to read.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepipeline\n      description: Amazon Elastic Transcoder UpdatePipeline\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-transcoder.updatepipeline\n      with:\n        Id: tools.Id\n      inputParameters:\n      - name: Id\n        type: string\n        description: The ID of the pipeline that you want to update.\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: deletepreset\n      description: Amazon Elastic Transcoder DeletePreset\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amazon-elastic-transcoder.deletepreset\n      with:\n        Id: tools.Id\n      inputParameters:\n      - name: Id\n        type: string\n        description: The identifier of the preset for which you want to get detailed information.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readpreset\n      description: Amazon Elastic Transcoder ReadPreset\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-transcoder.readpreset\n      with:\n        Id: tools.Id\n      inputParameters:\n      - name: Id\n        type: string\n        description: The identifier of the preset for which you want to get detailed information.\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listjobsbypipeline\n      description: Amazon Elastic Transcoder ListJobsByPipeline\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-transcoder.listjobsbypipeline\n      with:\n        PipelineId: tools.PipelineId\n        Ascending: tools.Ascending\n        PageToken: tools.PageToken\n      inputParameters:\n      - name: PipelineId\n        type: string\n        description: The ID of the pipeline for which you want to get job information.\n        required: true\n      - name: Ascending\n        type: string\n        description: To list jobs in chronological order by the date and time that they were submitted, enter <code>true</code>.\n          To list jobs in reverse chronological order, enter <\n      - name: PageToken\n        type: string\n        description: When Elastic Transcoder returns more than one page of results, use <code>pageToken</code> in\
  \ subsequent\n          <code>GET</code> requests to get each successive page of\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjobsbystatus\n      description: Amazon Elastic Transcoder ListJobsByStatus\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-transcoder.listjobsbystatus\n      with:\n        Status: tools.Status\n        Ascending: tools.Ascending\n        PageToken: tools.PageToken\n      inputParameters:\n      - name: Status\n        type: string\n        description: 'To get information about all of the jobs associated with the current AWS account that have a given status,\n          specify the following status: <code>Submitted</code>,'\n        required: true\n      - name: Ascending\n        type: string\n        description: To list jobs in chronological order by the date and time that they were submitted, enter <code>true</code>.\n          To list jobs in reverse\
  \ chronological order, enter <\n      - name: PageToken\n        type: string\n        description: When Elastic Transcoder returns more than one page of results, use <code>pageToken</code> in subsequent\n          <code>GET</code> requests to get each successive page of\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: testrole\n      description: Amazon Elastic Transcoder TestRole\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-elastic-transcoder.testrole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepipelinenotifications\n      description: Amazon Elastic Transcoder UpdatePipelineNotifications\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-elastic-transcoder.updatepipelinenotifications\n      with:\n        Id: tools.Id\n      inputParameters:\n      - name: Id\n        type: string\n\
  \        description: The identifier of the pipeline for which you want to change notification settings.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepipelinestatus\n      description: Amazon Elastic Transcoder UpdatePipelineStatus\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-elastic-transcoder.updatepipelinestatus\n      with:\n        Id: tools.Id\n      inputParameters:\n      - name: Id\n        type: string\n        description: The identifier of the pipeline to update.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AMAZON_ELASTIC_TRANSCODER_TOKEN: AMAZON_ELASTIC_TRANSCODER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-elastic-transcoder/refs/heads/main/capabilities/amazon-elastic-transcoder-capability.yaml
tags:
- Amazon
- Elastic
- Transcoder
- API
tools:
- description: Amazon Elastic Transcoder CancelJob
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: canceljob
- description: Amazon Elastic Transcoder ReadJob
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readjob
- description: Amazon Elastic Transcoder CreateJob
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createjob
- description: Amazon Elastic Transcoder CreatePipeline
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpipeline
- description: Amazon Elastic Transcoder ListPipelines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpipelines
- description: Amazon Elastic Transcoder CreatePreset
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpreset
- description: Amazon Elastic Transcoder ListPresets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpresets
- description: Amazon Elastic Transcoder DeletePipeline
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepipeline
- description: Amazon Elastic Transcoder ReadPipeline
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readpipeline
- description: Amazon Elastic Transcoder UpdatePipeline
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepipeline
- description: Amazon Elastic Transcoder DeletePreset
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepreset
- description: Amazon Elastic Transcoder ReadPreset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readpreset
- description: Amazon Elastic Transcoder ListJobsByPipeline
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobsbypipeline
- description: Amazon Elastic Transcoder ListJobsByStatus
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobsbystatus
- description: Amazon Elastic Transcoder TestRole
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: testrole
- description: Amazon Elastic Transcoder UpdatePipelineNotifications
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatepipelinenotifications
- description: Amazon Elastic Transcoder UpdatePipelineStatus
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatepipelinestatus
---
