---
categories: []
consumed_apis: []
description: The AWS Lambda API enables you to create, configure, and manage Lambda functions, layers, event source mappings, aliases, versions, and function URLs programmatically. Lambda runs your code on high-availability compute infrastructure without provisioning or managing servers, performing all administration of compute resources including capacity provisioning, automatic scaling, and logging. The API version used is 2015-03-31.
layout: capability
name: AWS Lambda API
operations:
- description: Aws Lambda List Functions
  method: GET
  name: listfunctions
  path: /2015-03-31/functions
- description: Aws Lambda Create a Function
  method: POST
  name: createfunction
  path: /2015-03-31/functions
- description: Aws Lambda Get a Function
  method: GET
  name: getfunction
  path: /2015-03-31/functions/{FunctionName}
- description: Aws Lambda Delete a Function
  method: DELETE
  name: deletefunction
  path: /2015-03-31/functions/{FunctionName}
- description: Aws Lambda Get Function Configuration
  method: GET
  name: getfunctionconfiguration
  path: /2015-03-31/functions/{FunctionName}/configuration
- description: Aws Lambda Update Function Configuration
  method: PUT
  name: updatefunctionconfiguration
  path: /2015-03-31/functions/{FunctionName}/configuration
- description: Aws Lambda Update Function Code
  method: PUT
  name: updatefunctioncode
  path: /2015-03-31/functions/{FunctionName}/code
- description: Aws Lambda Invoke a Function
  method: POST
  name: invoke
  path: /2015-03-31/functions/{FunctionName}/invocations
- description: Aws Lambda Publish a Version
  method: POST
  name: publishversion
  path: /2015-03-31/functions/{FunctionName}/versions
- description: Aws Lambda List Function Versions
  method: GET
  name: listversionsbyfunction
  path: /2015-03-31/functions/{FunctionName}/versions
- description: Aws Lambda List Aliases
  method: GET
  name: listaliases
  path: /2015-03-31/functions/{FunctionName}/aliases
- description: Aws Lambda Create an Alias
  method: POST
  name: createalias
  path: /2015-03-31/functions/{FunctionName}/aliases
- description: Aws Lambda Get an Alias
  method: GET
  name: getalias
  path: /2015-03-31/functions/{FunctionName}/aliases/{AliasName}
- description: Aws Lambda Update an Alias
  method: PUT
  name: updatealias
  path: /2015-03-31/functions/{FunctionName}/aliases/{AliasName}
- description: Aws Lambda Delete an Alias
  method: DELETE
  name: deletealias
  path: /2015-03-31/functions/{FunctionName}/aliases/{AliasName}
- description: Aws Lambda List Event Source Mappings
  method: GET
  name: listeventsourcemappings
  path: /2015-03-31/event-source-mappings
- description: Aws Lambda Create an Event Source Mapping
  method: POST
  name: createeventsourcemapping
  path: /2015-03-31/event-source-mappings
- description: Aws Lambda Get an Event Source Mapping
  method: GET
  name: geteventsourcemapping
  path: /2015-03-31/event-source-mappings/{UUID}
- description: Aws Lambda Update an Event Source Mapping
  method: PUT
  name: updateeventsourcemapping
  path: /2015-03-31/event-source-mappings/{UUID}
- description: Aws Lambda Delete an Event Source Mapping
  method: DELETE
  name: deleteeventsourcemapping
  path: /2015-03-31/event-source-mappings/{UUID}
- description: Aws Lambda List Layers
  method: GET
  name: listlayers
  path: /2015-03-31/layers
- description: Aws Lambda List Layer Versions
  method: GET
  name: listlayerversions
  path: /2015-03-31/layers/{LayerName}/versions
- description: Aws Lambda Publish a Layer Version
  method: POST
  name: publishlayerversion
  path: /2015-03-31/layers/{LayerName}/versions
- description: Aws Lambda Get a Layer Version
  method: GET
  name: getlayerversion
  path: /2015-03-31/layers/{LayerName}/versions/{VersionNumber}
- description: Aws Lambda Delete a Layer Version
  method: DELETE
  name: deletelayerversion
  path: /2015-03-31/layers/{LayerName}/versions/{VersionNumber}
- description: Aws Lambda Get Function Url Configuration
  method: GET
  name: getfunctionurlconfig
  path: /2021-10-31/functions/{FunctionName}/url
- description: Aws Lambda Create a Function Url
  method: POST
  name: createfunctionurlconfig
  path: /2021-10-31/functions/{FunctionName}/url
- description: Aws Lambda Update a Function Url
  method: PUT
  name: updatefunctionurlconfig
  path: /2021-10-31/functions/{FunctionName}/url
- description: Aws Lambda Delete a Function Url
  method: DELETE
  name: deletefunctionurlconfig
  path: /2021-10-31/functions/{FunctionName}/url
- description: Aws Lambda Get Reserved Concurrency
  method: GET
  name: getreservedconcurrency
  path: /2015-03-31/functions/{FunctionName}/concurrency
- description: Aws Lambda Set Reserved Concurrency
  method: PUT
  name: putfunctionconcurrency
  path: /2015-03-31/functions/{FunctionName}/concurrency
- description: Aws Lambda Delete Reserved Concurrency
  method: DELETE
  name: deletefunctionconcurrency
  path: /2015-03-31/functions/{FunctionName}/concurrency
- description: Aws Lambda Get Provisioned Concurrency
  method: GET
  name: getprovisionedconcurrencyconfig
  path: /2015-03-31/functions/{FunctionName}/provisioned-concurrency
- description: Aws Lambda Set Provisioned Concurrency
  method: PUT
  name: putprovisionedconcurrencyconfig
  path: /2015-03-31/functions/{FunctionName}/provisioned-concurrency
- description: Aws Lambda Delete Provisioned Concurrency
  method: DELETE
  name: deleteprovisionedconcurrencyconfig
  path: /2015-03-31/functions/{FunctionName}/provisioned-concurrency
- description: Aws Lambda List Tags
  method: GET
  name: listtags
  path: /2015-03-31/tags/{ARN}
- description: Aws Lambda Add Tags
  method: POST
  name: tagresource
  path: /2015-03-31/tags/{ARN}
- description: Aws Lambda Remove Tags
  method: DELETE
  name: untagresource
  path: /2015-03-31/tags/{ARN}
personas: []
provider_name: AWS Lambda
provider_slug: aws-lambda
search_terms:
- aws lambda update an event source mapping
- getprovisionedconcurrencyconfig
- aws lambda update function configuration
- putprovisionedconcurrencyconfig
- getfunctionurlconfig
- api
- deletealias
- aws lambda get reserved concurrency
- listlayers
- getfunctionconfiguration
- publishlayerversion
- aws lambda create a function
- aws lambda update a function url
- createfunctionurlconfig
- aws lambda delete a layer version
- aws lambda delete an alias
- lambda
- aws lambda set reserved concurrency
- updatealias
- aws lambda set provisioned concurrency
- aws lambda delete a function
- listversionsbyfunction
- aws lambda remove tags
- aws lambda get an event source mapping
- aws lambda list layer versions
- createalias
- getreservedconcurrency
- aws lambda get a function
- getfunction
- aws lambda get provisioned concurrency
- listtags
- updateeventsourcemapping
- aws lambda update function code
- deleteeventsourcemapping
- aws lambda get an alias
- aws lambda delete an event source mapping
- untagresource
- deleteprovisionedconcurrencyconfig
- getalias
- updatefunctionurlconfig
- geteventsourcemapping
- aws lambda list tags
- aws lambda list event source mappings
- aws lambda get function configuration
- listfunctions
- updatefunctioncode
- aws lambda list functions
- invoke
- aws lambda get a layer version
- tagresource
- getlayerversion
- deletefunctionurlconfig
- aws lambda list function versions
- aws lambda publish a version
- aws lambda delete a function url
- deletefunctionconcurrency
- aws lambda delete reserved concurrency
- listlayerversions
- putfunctionconcurrency
- aws
- aws lambda create a function url
- aws lambda add tags
- aws lambda list aliases
- deletefunction
- createfunction
- publishversion
- createeventsourcemapping
- aws lambda publish a layer version
- aws lambda update an alias
- aws lambda get function url configuration
- aws lambda create an alias
- aws lambda delete provisioned concurrency
- aws lambda invoke a function
- deletelayerversion
- aws lambda list layers
- listaliases
- updatefunctionconfiguration
- listeventsourcemappings
- aws lambda create an event source mapping
slug: aws-lambda-capability
source_filename: aws-lambda-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AWS Lambda API\n  description: The AWS Lambda API enables you to create, configure, and manage Lambda functions, layers, event source mappings,\n    aliases, versions, and function URLs programmatically. Lambda runs your code on high-availability compute infrastructure\n    without provisioning or managing servers, performing all administration of compute resources including capacity provisioning,\n    automatic scaling, and logging. The API version used is 2015-03-31.\n  tags:\n  - Aws\n  - Lambda\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: aws-lambda\n    baseUri: https://lambda.us-east-1.amazonaws.com\n    description: AWS Lambda API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{AWS_LAMBDA_TOKEN}}'\n    resources:\n    - name: 2015-03-31-functions\n      path: /2015-03-31/functions\n      operations:\n\
  \      - name: listfunctions\n        method: GET\n        description: Aws Lambda List Functions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfunction\n        method: POST\n        description: Aws Lambda Create a Function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2015-03-31-functions-functionname\n      path: /2015-03-31/functions/{FunctionName}\n      operations:\n      - name: getfunction\n        method: GET\n        description: Aws Lambda Get a Function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefunction\n        method: DELETE\n        description: Aws Lambda Delete a Function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: 2015-03-31-functions-functionname-configuration\n      path: /2015-03-31/functions/{FunctionName}/configuration\n      operations:\n      - name: getfunctionconfiguration\n        method: GET\n        description: Aws Lambda Get Function Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefunctionconfiguration\n        method: PUT\n        description: Aws Lambda Update Function Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2015-03-31-functions-functionname-code\n      path: /2015-03-31/functions/{FunctionName}/code\n      operations:\n      - name: updatefunctioncode\n        method: PUT\n        description: Aws Lambda Update Function Code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: 2015-03-31-functions-functionname-invocations\n      path: /2015-03-31/functions/{FunctionName}/invocations\n      operations:\n      - name: invoke\n        method: POST\n        description: Aws Lambda Invoke a Function\n        inputParameters:\n        - name: X-Amz-Invocation-Type\n          in: header\n          type: string\n          description: Choose from RequestResponse (synchronous, default), Event (asynchronous), or DryRun (validate parameters\n            and permissions)\n        - name: X-Amz-Log-Type\n          in: header\n          type: string\n          description: Set to Tail to include the execution log in the response\n        - name: X-Amz-Client-Context\n          in: header\n          type: string\n          description: Base64-encoded client context data to pass to the function in the context object. Maximum 3583 bytes\n            of base64-encoded data.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: 2015-03-31-functions-functionname-versions\n      path: /2015-03-31/functions/{FunctionName}/versions\n      operations:\n      - name: publishversion\n        method: POST\n        description: Aws Lambda Publish a Version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listversionsbyfunction\n        method: GET\n        description: Aws Lambda List Function Versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2015-03-31-functions-functionname-aliases\n      path: /2015-03-31/functions/{FunctionName}/aliases\n      operations:\n      - name: listaliases\n        method: GET\n        description: Aws Lambda List Aliases\n        inputParameters:\n        - name: FunctionVersion\n          in: query\n          type: string\n\
  \          description: Filter by the version that aliases point to\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createalias\n        method: POST\n        description: Aws Lambda Create an Alias\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2015-03-31-functions-functionname-aliases-aliasn\n      path: /2015-03-31/functions/{FunctionName}/aliases/{AliasName}\n      operations:\n      - name: getalias\n        method: GET\n        description: Aws Lambda Get an Alias\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatealias\n        method: PUT\n        description: Aws Lambda Update an Alias\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n      - name: deletealias\n        method: DELETE\n        description: Aws Lambda Delete an Alias\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2015-03-31-event-source-mappings\n      path: /2015-03-31/event-source-mappings\n      operations:\n      - name: listeventsourcemappings\n        method: GET\n        description: Aws Lambda List Event Source Mappings\n        inputParameters:\n        - name: EventSourceArn\n          in: query\n          type: string\n          description: The ARN of the event source (Amazon Kinesis stream, Amazon DynamoDB stream, Amazon SQS queue, Amazon\n            MSK cluster, or self-managed Apache Kafka cluster)\n        - name: FunctionName\n          in: query\n          type: string\n          description: The name, ARN, or partial ARN of the Lambda function to filter by\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: createeventsourcemapping\n        method: POST\n        description: Aws Lambda Create an Event Source Mapping\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2015-03-31-event-source-mappings-uuid\n      path: /2015-03-31/event-source-mappings/{UUID}\n      operations:\n      - name: geteventsourcemapping\n        method: GET\n        description: Aws Lambda Get an Event Source Mapping\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateeventsourcemapping\n        method: PUT\n        description: Aws Lambda Update an Event Source Mapping\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteeventsourcemapping\n        method: DELETE\n\
  \        description: Aws Lambda Delete an Event Source Mapping\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2015-03-31-layers\n      path: /2015-03-31/layers\n      operations:\n      - name: listlayers\n        method: GET\n        description: Aws Lambda List Layers\n        inputParameters:\n        - name: CompatibleRuntime\n          in: query\n          type: string\n          description: Filter layers by compatible runtime\n        - name: CompatibleArchitecture\n          in: query\n          type: string\n          description: Filter layers by compatible instruction set architecture\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2015-03-31-layers-layername-versions\n      path: /2015-03-31/layers/{LayerName}/versions\n      operations:\n      - name: listlayerversions\n        method: GET\n\
  \        description: Aws Lambda List Layer Versions\n        inputParameters:\n        - name: CompatibleRuntime\n          in: query\n          type: string\n          description: Filter by compatible runtime\n        - name: CompatibleArchitecture\n          in: query\n          type: string\n          description: Filter by compatible architecture\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: publishlayerversion\n        method: POST\n        description: Aws Lambda Publish a Layer Version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2015-03-31-layers-layername-versions-versionnumb\n      path: /2015-03-31/layers/{LayerName}/versions/{VersionNumber}\n      operations:\n      - name: getlayerversion\n        method: GET\n        description: Aws Lambda Get a Layer Version\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelayerversion\n        method: DELETE\n        description: Aws Lambda Delete a Layer Version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2021-10-31-functions-functionname-url\n      path: /2021-10-31/functions/{FunctionName}/url\n      operations:\n      - name: getfunctionurlconfig\n        method: GET\n        description: Aws Lambda Get Function Url Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfunctionurlconfig\n        method: POST\n        description: Aws Lambda Create a Function Url\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefunctionurlconfig\n\
  \        method: PUT\n        description: Aws Lambda Update a Function Url\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefunctionurlconfig\n        method: DELETE\n        description: Aws Lambda Delete a Function Url\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2015-03-31-functions-functionname-concurrency\n      path: /2015-03-31/functions/{FunctionName}/concurrency\n      operations:\n      - name: getreservedconcurrency\n        method: GET\n        description: Aws Lambda Get Reserved Concurrency\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putfunctionconcurrency\n        method: PUT\n        description: Aws Lambda Set Reserved Concurrency\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deletefunctionconcurrency\n        method: DELETE\n        description: Aws Lambda Delete Reserved Concurrency\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2015-03-31-functions-functionname-provisioned-co\n      path: /2015-03-31/functions/{FunctionName}/provisioned-concurrency\n      operations:\n      - name: getprovisionedconcurrencyconfig\n        method: GET\n        description: Aws Lambda Get Provisioned Concurrency\n        inputParameters:\n        - name: Qualifier\n          in: query\n          type: string\n          required: true\n          description: The version number or alias name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putprovisionedconcurrencyconfig\n        method: PUT\n        description:\
  \ Aws Lambda Set Provisioned Concurrency\n        inputParameters:\n        - name: Qualifier\n          in: query\n          type: string\n          required: true\n          description: The version number or alias name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteprovisionedconcurrencyconfig\n        method: DELETE\n        description: Aws Lambda Delete Provisioned Concurrency\n        inputParameters:\n        - name: Qualifier\n          in: query\n          type: string\n          required: true\n          description: The version number or alias name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 2015-03-31-tags-arn\n      path: /2015-03-31/tags/{ARN}\n      operations:\n      - name: listtags\n        method: GET\n        description: Aws Lambda List Tags\n        inputParameters:\n \
  \       - name: ARN\n          in: path\n          type: string\n          required: true\n          description: The function's Amazon Resource Name (ARN)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: tagresource\n        method: POST\n        description: Aws Lambda Add Tags\n        inputParameters:\n        - name: ARN\n          in: path\n          type: string\n          required: true\n          description: The function's Amazon Resource Name (ARN)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: untagresource\n        method: DELETE\n        description: Aws Lambda Remove Tags\n        inputParameters:\n        - name: ARN\n          in: path\n          type: string\n          required: true\n          description: The function's Amazon Resource Name (ARN)\n        - name: tagKeys\n        \
  \  in: query\n          type: array\n          required: true\n          description: List of tag keys to remove\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: aws-lambda-rest\n    description: REST adapter for AWS Lambda API.\n    resources:\n    - path: /2015-03-31/functions\n      name: listfunctions\n      operations:\n      - method: GET\n        name: listfunctions\n        description: Aws Lambda List Functions\n        call: aws-lambda.listfunctions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions\n      name: createfunction\n      operations:\n      - method: POST\n        name: createfunction\n        description: Aws Lambda Create a Function\n        call: aws-lambda.createfunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}\n\
  \      name: getfunction\n      operations:\n      - method: GET\n        name: getfunction\n        description: Aws Lambda Get a Function\n        call: aws-lambda.getfunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}\n      name: deletefunction\n      operations:\n      - method: DELETE\n        name: deletefunction\n        description: Aws Lambda Delete a Function\n        call: aws-lambda.deletefunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/configuration\n      name: getfunctionconfiguration\n      operations:\n      - method: GET\n        name: getfunctionconfiguration\n        description: Aws Lambda Get Function Configuration\n        call: aws-lambda.getfunctionconfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/configuration\n\
  \      name: updatefunctionconfiguration\n      operations:\n      - method: PUT\n        name: updatefunctionconfiguration\n        description: Aws Lambda Update Function Configuration\n        call: aws-lambda.updatefunctionconfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/code\n      name: updatefunctioncode\n      operations:\n      - method: PUT\n        name: updatefunctioncode\n        description: Aws Lambda Update Function Code\n        call: aws-lambda.updatefunctioncode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/invocations\n      name: invoke\n      operations:\n      - method: POST\n        name: invoke\n        description: Aws Lambda Invoke a Function\n        call: aws-lambda.invoke\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/versions\n\
  \      name: publishversion\n      operations:\n      - method: POST\n        name: publishversion\n        description: Aws Lambda Publish a Version\n        call: aws-lambda.publishversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/versions\n      name: listversionsbyfunction\n      operations:\n      - method: GET\n        name: listversionsbyfunction\n        description: Aws Lambda List Function Versions\n        call: aws-lambda.listversionsbyfunction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/aliases\n      name: listaliases\n      operations:\n      - method: GET\n        name: listaliases\n        description: Aws Lambda List Aliases\n        call: aws-lambda.listaliases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/aliases\n      name: createalias\n\
  \      operations:\n      - method: POST\n        name: createalias\n        description: Aws Lambda Create an Alias\n        call: aws-lambda.createalias\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/aliases/{AliasName}\n      name: getalias\n      operations:\n      - method: GET\n        name: getalias\n        description: Aws Lambda Get an Alias\n        call: aws-lambda.getalias\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/aliases/{AliasName}\n      name: updatealias\n      operations:\n      - method: PUT\n        name: updatealias\n        description: Aws Lambda Update an Alias\n        call: aws-lambda.updatealias\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/aliases/{AliasName}\n      name: deletealias\n      operations:\n      - method: DELETE\n\
  \        name: deletealias\n        description: Aws Lambda Delete an Alias\n        call: aws-lambda.deletealias\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/event-source-mappings\n      name: listeventsourcemappings\n      operations:\n      - method: GET\n        name: listeventsourcemappings\n        description: Aws Lambda List Event Source Mappings\n        call: aws-lambda.listeventsourcemappings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/event-source-mappings\n      name: createeventsourcemapping\n      operations:\n      - method: POST\n        name: createeventsourcemapping\n        description: Aws Lambda Create an Event Source Mapping\n        call: aws-lambda.createeventsourcemapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/event-source-mappings/{UUID}\n      name: geteventsourcemapping\n      operations:\n\
  \      - method: GET\n        name: geteventsourcemapping\n        description: Aws Lambda Get an Event Source Mapping\n        call: aws-lambda.geteventsourcemapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/event-source-mappings/{UUID}\n      name: updateeventsourcemapping\n      operations:\n      - method: PUT\n        name: updateeventsourcemapping\n        description: Aws Lambda Update an Event Source Mapping\n        call: aws-lambda.updateeventsourcemapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/event-source-mappings/{UUID}\n      name: deleteeventsourcemapping\n      operations:\n      - method: DELETE\n        name: deleteeventsourcemapping\n        description: Aws Lambda Delete an Event Source Mapping\n        call: aws-lambda.deleteeventsourcemapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/layers\n\
  \      name: listlayers\n      operations:\n      - method: GET\n        name: listlayers\n        description: Aws Lambda List Layers\n        call: aws-lambda.listlayers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/layers/{LayerName}/versions\n      name: listlayerversions\n      operations:\n      - method: GET\n        name: listlayerversions\n        description: Aws Lambda List Layer Versions\n        call: aws-lambda.listlayerversions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/layers/{LayerName}/versions\n      name: publishlayerversion\n      operations:\n      - method: POST\n        name: publishlayerversion\n        description: Aws Lambda Publish a Layer Version\n        call: aws-lambda.publishlayerversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/layers/{LayerName}/versions/{VersionNumber}\n      name: getlayerversion\n\
  \      operations:\n      - method: GET\n        name: getlayerversion\n        description: Aws Lambda Get a Layer Version\n        call: aws-lambda.getlayerversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/layers/{LayerName}/versions/{VersionNumber}\n      name: deletelayerversion\n      operations:\n      - method: DELETE\n        name: deletelayerversion\n        description: Aws Lambda Delete a Layer Version\n        call: aws-lambda.deletelayerversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2021-10-31/functions/{FunctionName}/url\n      name: getfunctionurlconfig\n      operations:\n      - method: GET\n        name: getfunctionurlconfig\n        description: Aws Lambda Get Function Url Configuration\n        call: aws-lambda.getfunctionurlconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2021-10-31/functions/{FunctionName}/url\n  \
  \    name: createfunctionurlconfig\n      operations:\n      - method: POST\n        name: createfunctionurlconfig\n        description: Aws Lambda Create a Function Url\n        call: aws-lambda.createfunctionurlconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2021-10-31/functions/{FunctionName}/url\n      name: updatefunctionurlconfig\n      operations:\n      - method: PUT\n        name: updatefunctionurlconfig\n        description: Aws Lambda Update a Function Url\n        call: aws-lambda.updatefunctionurlconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2021-10-31/functions/{FunctionName}/url\n      name: deletefunctionurlconfig\n      operations:\n      - method: DELETE\n        name: deletefunctionurlconfig\n        description: Aws Lambda Delete a Function Url\n        call: aws-lambda.deletefunctionurlconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n   \
  \ - path: /2015-03-31/functions/{FunctionName}/concurrency\n      name: getreservedconcurrency\n      operations:\n      - method: GET\n        name: getreservedconcurrency\n        description: Aws Lambda Get Reserved Concurrency\n        call: aws-lambda.getreservedconcurrency\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/concurrency\n      name: putfunctionconcurrency\n      operations:\n      - method: PUT\n        name: putfunctionconcurrency\n        description: Aws Lambda Set Reserved Concurrency\n        call: aws-lambda.putfunctionconcurrency\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/concurrency\n      name: deletefunctionconcurrency\n      operations:\n      - method: DELETE\n        name: deletefunctionconcurrency\n        description: Aws Lambda Delete Reserved Concurrency\n        call: aws-lambda.deletefunctionconcurrency\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/provisioned-concurrency\n      name: getprovisionedconcurrencyconfig\n      operations:\n      - method: GET\n        name: getprovisionedconcurrencyconfig\n        description: Aws Lambda Get Provisioned Concurrency\n        call: aws-lambda.getprovisionedconcurrencyconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/provisioned-concurrency\n      name: putprovisionedconcurrencyconfig\n      operations:\n      - method: PUT\n        name: putprovisionedconcurrencyconfig\n        description: Aws Lambda Set Provisioned Concurrency\n        call: aws-lambda.putprovisionedconcurrencyconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/functions/{FunctionName}/provisioned-concurrency\n      name: deleteprovisionedconcurrencyconfig\n    \
  \  operations:\n      - method: DELETE\n        name: deleteprovisionedconcurrencyconfig\n        description: Aws Lambda Delete Provisioned Concurrency\n        call: aws-lambda.deleteprovisionedconcurrencyconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/tags/{ARN}\n      name: listtags\n      operations:\n      - method: GET\n        name: listtags\n        description: Aws Lambda List Tags\n        call: aws-lambda.listtags\n        with:\n          ARN: rest.ARN\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/tags/{ARN}\n      name: tagresource\n      operations:\n      - method: POST\n        name: tagresource\n        description: Aws Lambda Add Tags\n        call: aws-lambda.tagresource\n        with:\n          ARN: rest.ARN\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /2015-03-31/tags/{ARN}\n      name: untagresource\n      operations:\n\
  \      - method: DELETE\n        name: untagresource\n        description: Aws Lambda Remove Tags\n        call: aws-lambda.untagresource\n        with:\n          ARN: rest.ARN\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: aws-lambda-mcp\n    transport: http\n    description: MCP adapter for AWS Lambda API for AI agent use.\n    tools:\n    - name: listfunctions\n      description: Aws Lambda List Functions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aws-lambda.listfunctions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createfunction\n      description: Aws Lambda Create a Function\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-lambda.createfunction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfunction\n      description:\
  \ Aws Lambda Get a Function\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aws-lambda.getfunction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletefunction\n      description: Aws Lambda Delete a Function\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: aws-lambda.deletefunction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfunctionconfiguration\n      description: Aws Lambda Get Function Configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aws-lambda.getfunctionconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatefunctionconfiguration\n      description: Aws Lambda Update Function Configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n\
  \      call: aws-lambda.updatefunctionconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatefunctioncode\n      description: Aws Lambda Update Function Code\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: aws-lambda.updatefunctioncode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: invoke\n      description: Aws Lambda Invoke a Function\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-lambda.invoke\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publishversion\n      description: Aws Lambda Publish a Version\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-lambda.publishversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listversionsbyfunction\n      description:\
  \ Aws Lambda List Function Versions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aws-lambda.listversionsbyfunction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listaliases\n      description: Aws Lambda List Aliases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aws-lambda.listaliases\n      with:\n        FunctionVersion: tools.FunctionVersion\n      inputParameters:\n      - name: FunctionVersion\n        type: string\n        description: Filter by the version that aliases point to\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createalias\n      description: Aws Lambda Create an Alias\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-lambda.createalias\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getalias\n\
  \      description: Aws Lambda Get an Alias\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aws-lambda.getalias\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatealias\n      description: Aws Lambda Update an Alias\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: aws-lambda.updatealias\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletealias\n      description: Aws Lambda Delete an Alias\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: aws-lambda.deletealias\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listeventsourcemappings\n      description: Aws Lambda List Event Source Mappings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aws-lambda.listeventsourcemappings\n\
  \      with:\n        EventSourceArn: tools.EventSourceArn\n        FunctionName: tools.FunctionName\n      inputParameters:\n      - name: EventSourceArn\n        type: string\n        description: The ARN of the event source (Amazon Kinesis stream, Amazon DynamoDB stream, Amazon SQS queue, Amazon\n          MSK cluster, or self-managed Apache Kafka cluster)\n      - name: FunctionName\n        type: string\n        description: The name, ARN, or partial ARN of the Lambda function to filter by\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createeventsourcemapping\n      description: Aws Lambda Create an Event Source Mapping\n      hints:\n        readOnly: false\n        destructive: f\n\n# --- truncated at 32 KB (40 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/aws-lambda/refs/heads/main/capabilities/aws-lambda-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aws-lambda/refs/heads/main/capabilities/aws-lambda-capability.yaml
tags:
- Aws
- Lambda
- API
tools:
- description: Aws Lambda List Functions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfunctions
- description: Aws Lambda Create a Function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfunction
- description: Aws Lambda Get a Function
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfunction
- description: Aws Lambda Delete a Function
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefunction
- description: Aws Lambda Get Function Configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfunctionconfiguration
- description: Aws Lambda Update Function Configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatefunctionconfiguration
- description: Aws Lambda Update Function Code
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatefunctioncode
- description: Aws Lambda Invoke a Function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invoke
- description: Aws Lambda Publish a Version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publishversion
- description: Aws Lambda List Function Versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listversionsbyfunction
- description: Aws Lambda List Aliases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaliases
- description: Aws Lambda Create an Alias
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createalias
- description: Aws Lambda Get an Alias
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getalias
- description: Aws Lambda Update an Alias
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatealias
- description: Aws Lambda Delete an Alias
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletealias
- description: Aws Lambda List Event Source Mappings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listeventsourcemappings
- description: Aws Lambda Create an Event Source Mapping
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createeventsourcemapping
- description: Aws Lambda Get an Event Source Mapping
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteventsourcemapping
- description: Aws Lambda Update an Event Source Mapping
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateeventsourcemapping
- description: Aws Lambda Delete an Event Source Mapping
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteeventsourcemapping
- description: Aws Lambda List Layers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlayers
- description: Aws Lambda List Layer Versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlayerversions
- description: Aws Lambda Publish a Layer Version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publishlayerversion
- description: Aws Lambda Get a Layer Version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlayerversion
- description: Aws Lambda Delete a Layer Version
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelayerversion
- description: Aws Lambda Get Function Url Configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfunctionurlconfig
- description: Aws Lambda Create a Function Url
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfunctionurlconfig
- description: Aws Lambda Update a Function Url
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatefunctionurlconfig
- description: Aws Lambda Delete a Function Url
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefunctionurlconfig
- description: Aws Lambda Get Reserved Concurrency
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreservedconcurrency
- description: Aws Lambda Set Reserved Concurrency
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putfunctionconcurrency
- description: Aws Lambda Delete Reserved Concurrency
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefunctionconcurrency
- description: Aws Lambda Get Provisioned Concurrency
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprovisionedconcurrencyconfig
- description: Aws Lambda Set Provisioned Concurrency
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putprovisionedconcurrencyconfig
- description: Aws Lambda Delete Provisioned Concurrency
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteprovisionedconcurrencyconfig
- description: Aws Lambda List Tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtags
- description: Aws Lambda Add Tags
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: tagresource
- description: Aws Lambda Remove Tags
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: untagresource
---
