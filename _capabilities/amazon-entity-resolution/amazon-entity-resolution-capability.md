---
categories: []
consumed_apis: []
description: <p>Welcome to the <i>AWS Entity Resolution API Reference</i>.</p> <p>AWS Entity Resolution is an AWS service that provides pre-configured entity resolution capabilities that enable developers and analysts at advertising and marketing companies to build an accurate and complete view of their consumers.</p> <p> With AWS Entity Resolution, you have the ability to match source records containing consumer identifiers, such as name, email address, and phone number. This holds true even when these records have incomplete or conflicting identifiers. For example, AWS Entity Resolution can effectively m
layout: capability
name: AWS EntityResolution
operations:
- description: Amazon Entity Resolution CreateMatchingWorkflow
  method: POST
  name: creatematchingworkflow
  path: /matchingworkflows
- description: Amazon Entity Resolution ListMatchingWorkflows
  method: GET
  name: listmatchingworkflows
  path: /matchingworkflows
- description: Amazon Entity Resolution CreateSchemaMapping
  method: POST
  name: createschemamapping
  path: /schemas
- description: Amazon Entity Resolution ListSchemaMappings
  method: GET
  name: listschemamappings
  path: /schemas
- description: Amazon Entity Resolution DeleteMatchingWorkflow
  method: DELETE
  name: deletematchingworkflow
  path: /matchingworkflows/{workflowName}
- description: Amazon Entity Resolution GetMatchingWorkflow
  method: GET
  name: getmatchingworkflow
  path: /matchingworkflows/{workflowName}
- description: Amazon Entity Resolution UpdateMatchingWorkflow
  method: PUT
  name: updatematchingworkflow
  path: /matchingworkflows/{workflowName}
- description: Amazon Entity Resolution DeleteSchemaMapping
  method: DELETE
  name: deleteschemamapping
  path: /schemas/{schemaName}
- description: Amazon Entity Resolution GetSchemaMapping
  method: GET
  name: getschemamapping
  path: /schemas/{schemaName}
- description: Amazon Entity Resolution GetMatchId
  method: POST
  name: getmatchid
  path: /matchingworkflows/{workflowName}/matches
- description: Amazon Entity Resolution GetMatchingJob
  method: GET
  name: getmatchingjob
  path: /matchingworkflows/{workflowName}/jobs/{jobId}
- description: Amazon Entity Resolution ListMatchingJobs
  method: GET
  name: listmatchingjobs
  path: /matchingworkflows/{workflowName}/jobs
- description: Amazon Entity Resolution StartMatchingJob
  method: POST
  name: startmatchingjob
  path: /matchingworkflows/{workflowName}/jobs
- description: Amazon Entity Resolution ListTagsForResource
  method: GET
  name: listtagsforresource
  path: /tags/{resourceArn}
- description: Amazon Entity Resolution TagResource
  method: POST
  name: tagresource
  path: /tags/{resourceArn}
- description: Amazon Entity Resolution UntagResource
  method: DELETE
  name: untagresource
  path: /tags/{resourceArn}#tagKeys
personas: []
provider_name: Amazon Entity Resolution
provider_slug: amazon-entity-resolution
search_terms:
- entity
- entity resolution
- updatematchingworkflow
- developers building applications using amazon entity resolution
- getschemamapping
- amazon entity resolution listmatchingworkflows
- amazon web services
- data integration
- createschemamapping
- tagresource
- amazon entity resolution startmatchingjob
- amazon
- resolution
- listtagsforresource
- amazon entity resolution getmatchingjob
- startmatchingjob
- data matching
- amazon entity resolution tagresource
- listmatchingjobs
- amazon entity resolution updatematchingworkflow
- unified capability for managing amazon entity resolution resources. combines amazon entity resolution apis for data analyst workflows in data quality.
- getmatchingjob
- amazon entity resolution deletematchingworkflow
- amazon entity resolution getmatchid
- amazon entity resolution listschemamappings
- amazon entity resolution listtagsforresource
- amazon entity resolution getmatchingworkflow
- listschemamappings
- amazon entity resolution deleteschemamapping
- untagresource
- machine learning
- listmatchingworkflows
- amazon entity resolution listmatchingjobs
- api
- creatematchingworkflow
- deleteschemamapping
- getmatchid
- deletematchingworkflow
- operations teams managing amazon entity resolution infrastructure
- amazon entity resolution untagresource
- amazon entity resolution creatematchingworkflow
- machine learning service for matching and linking related records
- getmatchingworkflow
- amazon entity resolution createschemamapping
- amazon entity resolution getschemamapping
slug: amazon-entity-resolution-capability
source_filename: amazon-entity-resolution-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AWS EntityResolution\n  description: <p>Welcome to the <i>AWS Entity Resolution API Reference</i>.</p> <p>AWS Entity Resolution is an AWS service\n    that provides pre-configured entity resolution capabilities that enable developers and analysts at advertising and marketing\n    companies to build an accurate and complete view of their consumers.</p> <p> With AWS Entity Resolution, you have the\n    ability to match source records containing consumer identifiers, such as name, email address, and phone number. This holds\n    true even when these records have incomplete or conflicting identifiers. For example, AWS Entity Resolution can effectively\n    m\n  tags:\n  - Amazon\n  - Entity\n  - Resolution\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-entity-resolution\n    baseUri: http://entityresolution.us-east-1.amazonaws.com\n    description: AWS EntityResolution\
  \ HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{AMAZON_ENTITY_RESOLUTION_TOKEN}}'\n    resources:\n    - name: matchingworkflows\n      path: /matchingworkflows\n      operations:\n      - name: creatematchingworkflow\n        method: POST\n        description: Amazon Entity Resolution CreateMatchingWorkflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listmatchingworkflows\n        method: GET\n        description: Amazon Entity Resolution ListMatchingWorkflows\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: integer\n          description: The maximum number of objects returned per page.\n        - name: nextToken\n          in: query\n          type: string\n          description: The pagination token from the previous <code>ListSchemaMappings</code> API call.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schemas\n      path: /schemas\n      operations:\n      - name: createschemamapping\n        method: POST\n        description: Amazon Entity Resolution CreateSchemaMapping\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listschemamappings\n        method: GET\n        description: Amazon Entity Resolution ListSchemaMappings\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: integer\n          description: The maximum number of objects returned per page.\n        - name: nextToken\n          in: query\n          type: string\n          description: The pagination token from the previous <code>ListSchemaMappings</code> API call.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n    - name: matchingworkflows-workflowname\n      path: /matchingworkflows/{workflowName}\n      operations:\n      - name: deletematchingworkflow\n        method: DELETE\n        description: Amazon Entity Resolution DeleteMatchingWorkflow\n        inputParameters:\n        - name: workflowName\n          in: path\n          type: string\n          required: true\n          description: The name of the workflow to be retrieved.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getmatchingworkflow\n        method: GET\n        description: Amazon Entity Resolution GetMatchingWorkflow\n        inputParameters:\n        - name: workflowName\n          in: path\n          type: string\n          required: true\n          description: The name of the workflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: updatematchingworkflow\n        method: PUT\n        description: Amazon Entity Resolution UpdateMatchingWorkflow\n        inputParameters:\n        - name: workflowName\n          in: path\n          type: string\n          required: true\n          description: The name of the workflow to be retrieved.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schemas-schemaname\n      path: /schemas/{schemaName}\n      operations:\n      - name: deleteschemamapping\n        method: DELETE\n        description: Amazon Entity Resolution DeleteSchemaMapping\n        inputParameters:\n        - name: schemaName\n          in: path\n          type: string\n          required: true\n          description: The name of the schema to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getschemamapping\n\
  \        method: GET\n        description: Amazon Entity Resolution GetSchemaMapping\n        inputParameters:\n        - name: schemaName\n          in: path\n          type: string\n          required: true\n          description: The name of the schema to be retrieved.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: matchingworkflows-workflowname-matches\n      path: /matchingworkflows/{workflowName}/matches\n      operations:\n      - name: getmatchid\n        method: POST\n        description: Amazon Entity Resolution GetMatchId\n        inputParameters:\n        - name: workflowName\n          in: path\n          type: string\n          required: true\n          description: The name of the workflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: matchingworkflows-workflowname-jobs-jobid\n      path:\
  \ /matchingworkflows/{workflowName}/jobs/{jobId}\n      operations:\n      - name: getmatchingjob\n        method: GET\n        description: Amazon Entity Resolution GetMatchingJob\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The ID of the job.\n        - name: workflowName\n          in: path\n          type: string\n          required: true\n          description: The name of the workflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: matchingworkflows-workflowname-jobs\n      path: /matchingworkflows/{workflowName}/jobs\n      operations:\n      - name: listmatchingjobs\n        method: GET\n        description: Amazon Entity Resolution ListMatchingJobs\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: integer\n          description: The maximum number\
  \ of objects returned per page.\n        - name: nextToken\n          in: query\n          type: string\n          description: The pagination token from the previous <code>ListSchemaMappings</code> API call.\n        - name: workflowName\n          in: path\n          type: string\n          required: true\n          description: The name of the workflow to be retrieved.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: startmatchingjob\n        method: POST\n        description: Amazon Entity Resolution StartMatchingJob\n        inputParameters:\n        - name: workflowName\n          in: path\n          type: string\n          required: true\n          description: The name of the matching job to be retrieved.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags-resourcearn\n      path: /tags/{resourceArn}\n\
  \      operations:\n      - name: listtagsforresource\n        method: GET\n        description: Amazon Entity Resolution ListTagsForResource\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the resource for which you want to view tags.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: tagresource\n        method: POST\n        description: Amazon Entity Resolution TagResource\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the resource for which you want to view tags.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags-resourcearn-tagkeys\n      path: /tags/{resourceArn}#tagKeys\n   \
  \   operations:\n      - name: untagresource\n        method: DELETE\n        description: Amazon Entity Resolution UntagResource\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the resource for which you want to untag.\n        - name: tagKeys\n          in: query\n          type: array\n          required: true\n          description: The list of tag keys to remove from the resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-entity-resolution-rest\n    description: REST adapter for AWS EntityResolution.\n    resources:\n    - path: /matchingworkflows\n      name: creatematchingworkflow\n      operations:\n      - method: POST\n        name: creatematchingworkflow\n        description: Amazon Entity Resolution CreateMatchingWorkflow\n\
  \        call: amazon-entity-resolution.creatematchingworkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /matchingworkflows\n      name: listmatchingworkflows\n      operations:\n      - method: GET\n        name: listmatchingworkflows\n        description: Amazon Entity Resolution ListMatchingWorkflows\n        call: amazon-entity-resolution.listmatchingworkflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schemas\n      name: createschemamapping\n      operations:\n      - method: POST\n        name: createschemamapping\n        description: Amazon Entity Resolution CreateSchemaMapping\n        call: amazon-entity-resolution.createschemamapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schemas\n      name: listschemamappings\n      operations:\n      - method: GET\n        name: listschemamappings\n        description: Amazon Entity Resolution ListSchemaMappings\n\
  \        call: amazon-entity-resolution.listschemamappings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /matchingworkflows/{workflowName}\n      name: deletematchingworkflow\n      operations:\n      - method: DELETE\n        name: deletematchingworkflow\n        description: Amazon Entity Resolution DeleteMatchingWorkflow\n        call: amazon-entity-resolution.deletematchingworkflow\n        with:\n          workflowName: rest.workflowName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /matchingworkflows/{workflowName}\n      name: getmatchingworkflow\n      operations:\n      - method: GET\n        name: getmatchingworkflow\n        description: Amazon Entity Resolution GetMatchingWorkflow\n        call: amazon-entity-resolution.getmatchingworkflow\n        with:\n          workflowName: rest.workflowName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /matchingworkflows/{workflowName}\n\
  \      name: updatematchingworkflow\n      operations:\n      - method: PUT\n        name: updatematchingworkflow\n        description: Amazon Entity Resolution UpdateMatchingWorkflow\n        call: amazon-entity-resolution.updatematchingworkflow\n        with:\n          workflowName: rest.workflowName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schemas/{schemaName}\n      name: deleteschemamapping\n      operations:\n      - method: DELETE\n        name: deleteschemamapping\n        description: Amazon Entity Resolution DeleteSchemaMapping\n        call: amazon-entity-resolution.deleteschemamapping\n        with:\n          schemaName: rest.schemaName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schemas/{schemaName}\n      name: getschemamapping\n      operations:\n      - method: GET\n        name: getschemamapping\n        description: Amazon Entity Resolution GetSchemaMapping\n        call: amazon-entity-resolution.getschemamapping\n\
  \        with:\n          schemaName: rest.schemaName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /matchingworkflows/{workflowName}/matches\n      name: getmatchid\n      operations:\n      - method: POST\n        name: getmatchid\n        description: Amazon Entity Resolution GetMatchId\n        call: amazon-entity-resolution.getmatchid\n        with:\n          workflowName: rest.workflowName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /matchingworkflows/{workflowName}/jobs/{jobId}\n      name: getmatchingjob\n      operations:\n      - method: GET\n        name: getmatchingjob\n        description: Amazon Entity Resolution GetMatchingJob\n        call: amazon-entity-resolution.getmatchingjob\n        with:\n          jobId: rest.jobId\n          workflowName: rest.workflowName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /matchingworkflows/{workflowName}/jobs\n\
  \      name: listmatchingjobs\n      operations:\n      - method: GET\n        name: listmatchingjobs\n        description: Amazon Entity Resolution ListMatchingJobs\n        call: amazon-entity-resolution.listmatchingjobs\n        with:\n          workflowName: rest.workflowName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /matchingworkflows/{workflowName}/jobs\n      name: startmatchingjob\n      operations:\n      - method: POST\n        name: startmatchingjob\n        description: Amazon Entity Resolution StartMatchingJob\n        call: amazon-entity-resolution.startmatchingjob\n        with:\n          workflowName: rest.workflowName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags/{resourceArn}\n      name: listtagsforresource\n      operations:\n      - method: GET\n        name: listtagsforresource\n        description: Amazon Entity Resolution ListTagsForResource\n        call: amazon-entity-resolution.listtagsforresource\n\
  \        with:\n          resourceArn: rest.resourceArn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags/{resourceArn}\n      name: tagresource\n      operations:\n      - method: POST\n        name: tagresource\n        description: Amazon Entity Resolution TagResource\n        call: amazon-entity-resolution.tagresource\n        with:\n          resourceArn: rest.resourceArn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags/{resourceArn}#tagKeys\n      name: untagresource\n      operations:\n      - method: DELETE\n        name: untagresource\n        description: Amazon Entity Resolution UntagResource\n        call: amazon-entity-resolution.untagresource\n        with:\n          resourceArn: rest.resourceArn\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-entity-resolution-mcp\n    transport: http\n    description: MCP\
  \ adapter for AWS EntityResolution for AI agent use.\n    tools:\n    - name: creatematchingworkflow\n      description: Amazon Entity Resolution CreateMatchingWorkflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-entity-resolution.creatematchingworkflow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmatchingworkflows\n      description: Amazon Entity Resolution ListMatchingWorkflows\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-entity-resolution.listmatchingworkflows\n      with:\n        maxResults: tools.maxResults\n        nextToken: tools.nextToken\n      inputParameters:\n      - name: maxResults\n        type: integer\n        description: The maximum number of objects returned per page.\n      - name: nextToken\n        type: string\n        description: The pagination token from the previous <code>ListSchemaMappings</code>\
  \ API call.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createschemamapping\n      description: Amazon Entity Resolution CreateSchemaMapping\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-entity-resolution.createschemamapping\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listschemamappings\n      description: Amazon Entity Resolution ListSchemaMappings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-entity-resolution.listschemamappings\n      with:\n        maxResults: tools.maxResults\n        nextToken: tools.nextToken\n      inputParameters:\n      - name: maxResults\n        type: integer\n        description: The maximum number of objects returned per page.\n      - name: nextToken\n        type: string\n        description: The pagination token from the previous <code>ListSchemaMappings</code>\
  \ API call.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletematchingworkflow\n      description: Amazon Entity Resolution DeleteMatchingWorkflow\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amazon-entity-resolution.deletematchingworkflow\n      with:\n        workflowName: tools.workflowName\n      inputParameters:\n      - name: workflowName\n        type: string\n        description: The name of the workflow to be retrieved.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmatchingworkflow\n      description: Amazon Entity Resolution GetMatchingWorkflow\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-entity-resolution.getmatchingworkflow\n      with:\n        workflowName: tools.workflowName\n      inputParameters:\n      - name: workflowName\n        type: string\n\
  \        description: The name of the workflow.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatematchingworkflow\n      description: Amazon Entity Resolution UpdateMatchingWorkflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amazon-entity-resolution.updatematchingworkflow\n      with:\n        workflowName: tools.workflowName\n      inputParameters:\n      - name: workflowName\n        type: string\n        description: The name of the workflow to be retrieved.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteschemamapping\n      description: Amazon Entity Resolution DeleteSchemaMapping\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amazon-entity-resolution.deleteschemamapping\n      with:\n        schemaName: tools.schemaName\n      inputParameters:\n\
  \      - name: schemaName\n        type: string\n        description: The name of the schema to delete.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getschemamapping\n      description: Amazon Entity Resolution GetSchemaMapping\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-entity-resolution.getschemamapping\n      with:\n        schemaName: tools.schemaName\n      inputParameters:\n      - name: schemaName\n        type: string\n        description: The name of the schema to be retrieved.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmatchid\n      description: Amazon Entity Resolution GetMatchId\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-entity-resolution.getmatchid\n      with:\n        workflowName: tools.workflowName\n      inputParameters:\n\
  \      - name: workflowName\n        type: string\n        description: The name of the workflow.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmatchingjob\n      description: Amazon Entity Resolution GetMatchingJob\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-entity-resolution.getmatchingjob\n      with:\n        jobId: tools.jobId\n        workflowName: tools.workflowName\n      inputParameters:\n      - name: jobId\n        type: string\n        description: The ID of the job.\n        required: true\n      - name: workflowName\n        type: string\n        description: The name of the workflow.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmatchingjobs\n      description: Amazon Entity Resolution ListMatchingJobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: amazon-entity-resolution.listmatchingjobs\n      with:\n        workflowName: tools.workflowName\n        maxResults: tools.maxResults\n        nextToken: tools.nextToken\n      inputParameters:\n      - name: workflowName\n        type: string\n        description: The name of the workflow to be retrieved.\n        required: true\n      - name: maxResults\n        type: integer\n        description: The maximum number of objects returned per page.\n      - name: nextToken\n        type: string\n        description: The pagination token from the previous <code>ListSchemaMappings</code> API call.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startmatchingjob\n      description: Amazon Entity Resolution StartMatchingJob\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-entity-resolution.startmatchingjob\n      with:\n        workflowName: tools.workflowName\n      inputParameters:\n\
  \      - name: workflowName\n        type: string\n        description: The name of the matching job to be retrieved.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtagsforresource\n      description: Amazon Entity Resolution ListTagsForResource\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-entity-resolution.listtagsforresource\n      with:\n        resourceArn: tools.resourceArn\n      inputParameters:\n      - name: resourceArn\n        type: string\n        description: The ARN of the resource for which you want to view tags.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tagresource\n      description: Amazon Entity Resolution TagResource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-entity-resolution.tagresource\n      with:\n    \
  \    resourceArn: tools.resourceArn\n      inputParameters:\n      - name: resourceArn\n        type: string\n        description: The ARN of the resource for which you want to view tags.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: untagresource\n      description: Amazon Entity Resolution UntagResource\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amazon-entity-resolution.untagresource\n      with:\n        resourceArn: tools.resourceArn\n        tagKeys: tools.tagKeys\n      inputParameters:\n      - name: resourceArn\n        type: string\n        description: The ARN of the resource for which you want to untag.\n        required: true\n      - name: tagKeys\n        type: array\n        description: The list of tag keys to remove from the resource.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n\
  \  keys:\n    AMAZON_ENTITY_RESOLUTION_TOKEN: AMAZON_ENTITY_RESOLUTION_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-entity-resolution/refs/heads/main/capabilities/amazon-entity-resolution-capability.yaml
tags:
- Amazon
- Entity
- Resolution
- API
tools:
- description: Amazon Entity Resolution CreateMatchingWorkflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creatematchingworkflow
- description: Amazon Entity Resolution ListMatchingWorkflows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmatchingworkflows
- description: Amazon Entity Resolution CreateSchemaMapping
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createschemamapping
- description: Amazon Entity Resolution ListSchemaMappings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschemamappings
- description: Amazon Entity Resolution DeleteMatchingWorkflow
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletematchingworkflow
- description: Amazon Entity Resolution GetMatchingWorkflow
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmatchingworkflow
- description: Amazon Entity Resolution UpdateMatchingWorkflow
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatematchingworkflow
- description: Amazon Entity Resolution DeleteSchemaMapping
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteschemamapping
- description: Amazon Entity Resolution GetSchemaMapping
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getschemamapping
- description: Amazon Entity Resolution GetMatchId
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getmatchid
- description: Amazon Entity Resolution GetMatchingJob
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmatchingjob
- description: Amazon Entity Resolution ListMatchingJobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmatchingjobs
- description: Amazon Entity Resolution StartMatchingJob
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startmatchingjob
- description: Amazon Entity Resolution ListTagsForResource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtagsforresource
- description: Amazon Entity Resolution TagResource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: tagresource
- description: Amazon Entity Resolution UntagResource
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: untagresource
---
