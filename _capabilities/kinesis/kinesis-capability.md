---
categories: []
consumed_apis: []
description: <fullname>Amazon Kinesis Data Firehose API Reference</fullname> <p>Amazon Kinesis Data Firehose is a fully managed service that delivers real-time streaming data to destinations such as Amazon Simple Storage Service (Amazon S3), Amazon OpenSearch Service, Amazon Redshift, Splunk, and various other supportd destinations.</p>
layout: capability
name: Amazon Kinesis Firehose
operations:
- description: <p>Creates a Kinesis Data Firehose delivery stream.</p> <p>By default, you can create up to 50 delivery streams per Amazon Web Services Region.</p> <p>This is an asynchronous operation that immediately returns. The initial status of the del
  method: POST
  name: createdeliverystream
  path: /#X-Amz-Target=Firehose_20150804.CreateDeliveryStream
- description: '<p>Deletes a delivery stream and its data.</p> <p>To check the state of a delivery stream, use <a>DescribeDeliveryStream</a>. You can delete a delivery stream only if it is in one of the following states: <code>ACTIVE</code>, <code>DELETING'
  method: POST
  name: deletedeliverystream
  path: /#X-Amz-Target=Firehose_20150804.DeleteDeliveryStream
- description: <p>Describes the specified delivery stream and its status. For example, after your delivery stream is created, call <code>DescribeDeliveryStream</code> to see whether the delivery stream is <code>ACTIVE</code> and therefore ready for data t
  method: POST
  name: describedeliverystream
  path: /#X-Amz-Target=Firehose_20150804.DescribeDeliveryStream
- description: <p>Lists your delivery streams in alphabetical order of their names.</p> <p>The number of delivery streams might be too large to return using a single call to <code>ListDeliveryStreams</code>. You can limit the number of delivery streams re
  method: POST
  name: listdeliverystreams
  path: /#X-Amz-Target=Firehose_20150804.ListDeliveryStreams
- description: Lists the tags for the specified delivery stream. This operation has a limit of five transactions per second per account.
  method: POST
  name: listtagsfordeliverystream
  path: /#X-Amz-Target=Firehose_20150804.ListTagsForDeliveryStream
- description: <p>Writes a single data record into an Amazon Kinesis Data Firehose delivery stream. To write multiple data records into a delivery stream, use <a>PutRecordBatch</a>. Applications using these operations are referred to as producers.</p> <p>
  method: POST
  name: putrecord
  path: /#X-Amz-Target=Firehose_20150804.PutRecord
- description: <p>Writes multiple data records into a delivery stream in a single call, which can achieve higher throughput per producer than when writing single records. To write single data records into a delivery stream, use <a>PutRecord</a>. Applicati
  method: POST
  name: putrecordbatch
  path: /#X-Amz-Target=Firehose_20150804.PutRecordBatch
- description: <p>Enables server-side encryption (SSE) for the delivery stream. </p> <p>This operation is asynchronous. It returns immediately. When you invoke it, Kinesis Data Firehose first sets the encryption status of the stream to <code>ENABLING</cod
  method: POST
  name: startdeliverystreamencryption
  path: /#X-Amz-Target=Firehose_20150804.StartDeliveryStreamEncryption
- description: <p>Disables server-side encryption (SSE) for the delivery stream. </p> <p>This operation is asynchronous. It returns immediately. When you invoke it, Kinesis Data Firehose first sets the encryption status of the stream to <code>DISABLING</c
  method: POST
  name: stopdeliverystreamencryption
  path: /#X-Amz-Target=Firehose_20150804.StopDeliveryStreamEncryption
- description: <p>Adds or updates tags for the specified delivery stream. A tag is a key-value pair that you can define and assign to Amazon Web Services resources. If you specify a tag that already exists, the tag value is replaced with the value that yo
  method: POST
  name: tagdeliverystream
  path: /#X-Amz-Target=Firehose_20150804.TagDeliveryStream
- description: <p>Removes tags from the specified delivery stream. Removed tags are deleted, and you can't recover them after this operation successfully completes.</p> <p>If you specify a tag that doesn't exist, the operation ignores it.</p> <p>This oper
  method: POST
  name: untagdeliverystream
  path: /#X-Amz-Target=Firehose_20150804.UntagDeliveryStream
- description: <p>Updates the specified destination of the specified delivery stream.</p> <p>Use this operation to change the destination type (for example, to replace the Amazon S3 destination with Amazon Redshift) or change the parameters associated wit
  method: POST
  name: updatedestination
  path: /#X-Amz-Target=Firehose_20150804.UpdateDestination
personas: []
provider_name: AWS Kinesis
provider_slug: kinesis
search_terms:
- analytics
- streaming
- video
- listtagsfordeliverystream
- <p>lists your delivery streams in alphabetical order of their names.</p> <p>the number of delivery streams might be too large to return using a single call to <code>listdeliverystreams</code>. you can limit the number of delivery streams re
- <p>writes a single data record into an amazon kinesis data firehose delivery stream. to write multiple data records into a delivery stream, use <a>putrecordbatch</a>. applications using these operations are referred to as producers.</p> <p>
- kinesis
- deletedeliverystream
- api
- putrecordbatch
- stopdeliverystreamencryption
- listdeliverystreams
- <p>creates a kinesis data firehose delivery stream.</p> <p>by default, you can create up to 50 delivery streams per amazon web services region.</p> <p>this is an asynchronous operation that immediately returns. the initial status of the del
- describedeliverystream
- startdeliverystreamencryption
- big data
- lists the tags for the specified delivery stream. this operation has a limit of five transactions per second per account.
- data processing
- <p>describes the specified delivery stream and its status. for example, after your delivery stream is created, call <code>describedeliverystream</code> to see whether the delivery stream is <code>active</code> and therefore ready for data t
- <p>updates the specified destination of the specified delivery stream.</p> <p>use this operation to change the destination type (for example, to replace the amazon s3 destination with amazon redshift) or change the parameters associated wit
- <p>disables server-side encryption (sse) for the delivery stream. </p> <p>this operation is asynchronous. it returns immediately. when you invoke it, kinesis data firehose first sets the encryption status of the stream to <code>disabling</c
- putrecord
- <p>writes multiple data records into a delivery stream in a single call, which can achieve higher throughput per producer than when writing single records. to write single data records into a delivery stream, use <a>putrecord</a>. applicati
- <p>removes tags from the specified delivery stream. removed tags are deleted, and you can't recover them after this operation successfully completes.</p> <p>if you specify a tag that doesn't exist, the operation ignores it.</p> <p>this oper
- apache flink
- '<p>deletes a delivery stream and its data.</p> <p>to check the state of a delivery stream, use <a>describedeliverystream</a>. you can delete a delivery stream only if it is in one of the following states: <code>active</code>, <code>deleting'
- <p>enables server-side encryption (sse) for the delivery stream. </p> <p>this operation is asynchronous. it returns immediately. when you invoke it, kinesis data firehose first sets the encryption status of the stream to <code>enabling</cod
- real-time
- untagdeliverystream
- createdeliverystream
- <p>adds or updates tags for the specified delivery stream. a tag is a key-value pair that you can define and assign to amazon web services resources. if you specify a tag that already exists, the tag value is replaced with the value that yo
- updatedestination
- tagdeliverystream
slug: kinesis-capability
source_filename: kinesis-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Kinesis Firehose\n  description: <fullname>Amazon Kinesis Data Firehose API Reference</fullname> <p>Amazon Kinesis Data Firehose is a fully\n    managed service that delivers real-time streaming data to destinations such as Amazon Simple Storage Service (Amazon S3),\n    Amazon OpenSearch Service, Amazon Redshift, Splunk, and various other supportd destinations.</p>\n  tags:\n  - Kinesis\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: kinesis\n    baseUri: http://firehose.us-east-1.amazonaws.com\n    description: Amazon Kinesis Firehose HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{KINESIS_TOKEN}}'\n    resources:\n    - name: x-amz-target-firehose-20150804-createdeliverystr\n      path: /#X-Amz-Target=Firehose_20150804.CreateDeliveryStream\n      operations:\n      - name: createdeliverystream\n\
  \        method: POST\n        description: <p>Creates a Kinesis Data Firehose delivery stream.</p> <p>By default, you can create up to 50 delivery\n          streams per Amazon Web Services Region.</p> <p>This is an asynchronous operation that immediately returns. The initial\n          status of the del\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-firehose-20150804-deletedeliverystr\n      path: /#X-Amz-Target=Firehose_20150804.DeleteDeliveryStream\n      operations:\n      - name: deletedeliverystream\n        method: POST\n        description: '<p>Deletes a delivery stream and its data.</p> <p>To check the state of a delivery stream, use <a>DescribeDeliveryStream</a>.\n          You can delete a delivery stream only if it is in one of the following states:\
  \ <code>ACTIVE</code>, <code>DELETING'\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-firehose-20150804-describedeliverys\n      path: /#X-Amz-Target=Firehose_20150804.DescribeDeliveryStream\n      operations:\n      - name: describedeliverystream\n        method: POST\n        description: <p>Describes the specified delivery stream and its status. For example, after your delivery stream is\n          created, call <code>DescribeDeliveryStream</code> to see whether the delivery stream is <code>ACTIVE</code> and\n          therefore ready for data t\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: x-amz-target-firehose-20150804-listdeliverystrea\n      path: /#X-Amz-Target=Firehose_20150804.ListDeliveryStreams\n      operations:\n      - name: listdeliverystreams\n        method: POST\n        description: <p>Lists your delivery streams in alphabetical order of their names.</p> <p>The number of delivery streams\n          might be too large to return using a single call to <code>ListDeliveryStreams</code>. You can limit the number of\n          delivery streams re\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-firehose-20150804-listtagsfordelive\n      path: /#X-Amz-Target=Firehose_20150804.ListTagsForDeliveryStream\n      operations:\n      - name: listtagsfordeliverystream\n        method:\
  \ POST\n        description: Lists the tags for the specified delivery stream. This operation has a limit of five transactions per\n          second per account.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-firehose-20150804-putrecord\n      path: /#X-Amz-Target=Firehose_20150804.PutRecord\n      operations:\n      - name: putrecord\n        method: POST\n        description: <p>Writes a single data record into an Amazon Kinesis Data Firehose delivery stream. To write multiple\n          data records into a delivery stream, use <a>PutRecordBatch</a>. Applications using these operations are referred\n          to as producers.</p> <p>\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-firehose-20150804-putrecordbatch\n      path: /#X-Amz-Target=Firehose_20150804.PutRecordBatch\n      operations:\n      - name: putrecordbatch\n        method: POST\n        description: <p>Writes multiple data records into a delivery stream in a single call, which can achieve higher throughput\n          per producer than when writing single records. To write single data records into a delivery stream, use <a>PutRecord</a>.\n          Applicati\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-firehose-20150804-startdeliverystre\n      path: /#X-Amz-Target=Firehose_20150804.StartDeliveryStreamEncryption\n\
  \      operations:\n      - name: startdeliverystreamencryption\n        method: POST\n        description: <p>Enables server-side encryption (SSE) for the delivery stream. </p> <p>This operation is asynchronous.\n          It returns immediately. When you invoke it, Kinesis Data Firehose first sets the encryption status of the stream\n          to <code>ENABLING</cod\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-firehose-20150804-stopdeliverystrea\n      path: /#X-Amz-Target=Firehose_20150804.StopDeliveryStreamEncryption\n      operations:\n      - name: stopdeliverystreamencryption\n        method: POST\n        description: <p>Disables server-side encryption (SSE) for the delivery stream. </p> <p>This operation is asynchronous.\n          It returns immediately.\
  \ When you invoke it, Kinesis Data Firehose first sets the encryption status of the stream\n          to <code>DISABLING</c\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-firehose-20150804-tagdeliverystream\n      path: /#X-Amz-Target=Firehose_20150804.TagDeliveryStream\n      operations:\n      - name: tagdeliverystream\n        method: POST\n        description: <p>Adds or updates tags for the specified delivery stream. A tag is a key-value pair that you can define\n          and assign to Amazon Web Services resources. If you specify a tag that already exists, the tag value is replaced\n          with the value that yo\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-firehose-20150804-untagdeliverystre\n      path: /#X-Amz-Target=Firehose_20150804.UntagDeliveryStream\n      operations:\n      - name: untagdeliverystream\n        method: POST\n        description: <p>Removes tags from the specified delivery stream. Removed tags are deleted, and you can't recover them\n          after this operation successfully completes.</p> <p>If you specify a tag that doesn't exist, the operation ignores\n          it.</p> <p>This oper\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-firehose-20150804-updatedestination\n      path: /#X-Amz-Target=Firehose_20150804.UpdateDestination\n      operations:\n\
  \      - name: updatedestination\n        method: POST\n        description: <p>Updates the specified destination of the specified delivery stream.</p> <p>Use this operation to change\n          the destination type (for example, to replace the Amazon S3 destination with Amazon Redshift) or change the parameters\n          associated wit\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: kinesis-rest\n    description: REST adapter for Amazon Kinesis Firehose.\n    resources:\n    - path: /#X-Amz-Target=Firehose_20150804.CreateDeliveryStream\n      name: createdeliverystream\n      operations:\n      - method: POST\n        name: createdeliverystream\n        description: <p>Creates a Kinesis Data Firehose delivery stream.</p>\
  \ <p>By default, you can create up to 50 delivery\n          streams per Amazon Web Services Region.</p> <p>This is an asynchronous operation that immediately returns. The initial\n          status of the del\n        call: kinesis.createdeliverystream\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=Firehose_20150804.DeleteDeliveryStream\n      name: deletedeliverystream\n      operations:\n      - method: POST\n        name: deletedeliverystream\n        description: '<p>Deletes a delivery stream and its data.</p> <p>To check the state of a delivery stream, use <a>DescribeDeliveryStream</a>.\n          You can delete a delivery stream only if it is in one of the following states: <code>ACTIVE</code>, <code>DELETING'\n        call: kinesis.deletedeliverystream\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=Firehose_20150804.DescribeDeliveryStream\n      name: describedeliverystream\n\
  \      operations:\n      - method: POST\n        name: describedeliverystream\n        description: <p>Describes the specified delivery stream and its status. For example, after your delivery stream is\n          created, call <code>DescribeDeliveryStream</code> to see whether the delivery stream is <code>ACTIVE</code> and\n          therefore ready for data t\n        call: kinesis.describedeliverystream\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=Firehose_20150804.ListDeliveryStreams\n      name: listdeliverystreams\n      operations:\n      - method: POST\n        name: listdeliverystreams\n        description: <p>Lists your delivery streams in alphabetical order of their names.</p> <p>The number of delivery streams\n          might be too large to return using a single call to <code>ListDeliveryStreams</code>. You can limit the number of\n          delivery streams re\n        call: kinesis.listdeliverystreams\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=Firehose_20150804.ListTagsForDeliveryStream\n      name: listtagsfordeliverystream\n      operations:\n      - method: POST\n        name: listtagsfordeliverystream\n        description: Lists the tags for the specified delivery stream. This operation has a limit of five transactions per\n          second per account.\n        call: kinesis.listtagsfordeliverystream\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=Firehose_20150804.PutRecord\n      name: putrecord\n      operations:\n      - method: POST\n        name: putrecord\n        description: <p>Writes a single data record into an Amazon Kinesis Data Firehose delivery stream. To write multiple\n          data records into a delivery stream, use <a>PutRecordBatch</a>. Applications using these operations are referred\n          to as producers.</p> <p>\n        call: kinesis.putrecord\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=Firehose_20150804.PutRecordBatch\n      name: putrecordbatch\n      operations:\n      - method: POST\n        name: putrecordbatch\n        description: <p>Writes multiple data records into a delivery stream in a single call, which can achieve higher throughput\n          per producer than when writing single records. To write single data records into a delivery stream, use <a>PutRecord</a>.\n          Applicati\n        call: kinesis.putrecordbatch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=Firehose_20150804.StartDeliveryStreamEncryption\n      name: startdeliverystreamencryption\n      operations:\n      - method: POST\n        name: startdeliverystreamencryption\n        description: <p>Enables server-side encryption (SSE) for the delivery stream. </p> <p>This operation is asynchronous.\n          It returns immediately. When you invoke it, Kinesis Data\
  \ Firehose first sets the encryption status of the stream\n          to <code>ENABLING</cod\n        call: kinesis.startdeliverystreamencryption\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=Firehose_20150804.StopDeliveryStreamEncryption\n      name: stopdeliverystreamencryption\n      operations:\n      - method: POST\n        name: stopdeliverystreamencryption\n        description: <p>Disables server-side encryption (SSE) for the delivery stream. </p> <p>This operation is asynchronous.\n          It returns immediately. When you invoke it, Kinesis Data Firehose first sets the encryption status of the stream\n          to <code>DISABLING</c\n        call: kinesis.stopdeliverystreamencryption\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=Firehose_20150804.TagDeliveryStream\n      name: tagdeliverystream\n      operations:\n      - method: POST\n        name: tagdeliverystream\n\
  \        description: <p>Adds or updates tags for the specified delivery stream. A tag is a key-value pair that you can define\n          and assign to Amazon Web Services resources. If you specify a tag that already exists, the tag value is replaced\n          with the value that yo\n        call: kinesis.tagdeliverystream\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=Firehose_20150804.UntagDeliveryStream\n      name: untagdeliverystream\n      operations:\n      - method: POST\n        name: untagdeliverystream\n        description: <p>Removes tags from the specified delivery stream. Removed tags are deleted, and you can't recover them\n          after this operation successfully completes.</p> <p>If you specify a tag that doesn't exist, the operation ignores\n          it.</p> <p>This oper\n        call: kinesis.untagdeliverystream\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=Firehose_20150804.UpdateDestination\n\
  \      name: updatedestination\n      operations:\n      - method: POST\n        name: updatedestination\n        description: <p>Updates the specified destination of the specified delivery stream.</p> <p>Use this operation to change\n          the destination type (for example, to replace the Amazon S3 destination with Amazon Redshift) or change the parameters\n          associated wit\n        call: kinesis.updatedestination\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: kinesis-mcp\n    transport: http\n    description: MCP adapter for Amazon Kinesis Firehose for AI agent use.\n    tools:\n    - name: createdeliverystream\n      description: <p>Creates a Kinesis Data Firehose delivery stream.</p> <p>By default, you can create up to 50 delivery\n        streams per Amazon Web Services Region.</p> <p>This is an asynchronous operation that immediately returns. The initial\n        status of the del\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kinesis.createdeliverystream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedeliverystream\n      description: '<p>Deletes a delivery stream and its data.</p> <p>To check the state of a delivery stream, use <a>DescribeDeliveryStream</a>.\n        You can delete a delivery stream only if it is in one of the following states: <code>ACTIVE</code>, <code>DELETING'\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kinesis.deletedeliverystream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describedeliverystream\n      description: <p>Describes the specified delivery stream and its status. For example, after your delivery stream is created,\n        call <code>DescribeDeliveryStream</code> to see whether the delivery stream is <code>ACTIVE</code> and therefore ready\n   \
  \     for data t\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kinesis.describedeliverystream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdeliverystreams\n      description: <p>Lists your delivery streams in alphabetical order of their names.</p> <p>The number of delivery streams\n        might be too large to return using a single call to <code>ListDeliveryStreams</code>. You can limit the number of\n        delivery streams re\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kinesis.listdeliverystreams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtagsfordeliverystream\n      description: Lists the tags for the specified delivery stream. This operation has a limit of five transactions per second\n        per account.\n      hints:\n        readOnly: false\n        destructive: false\n   \
  \     idempotent: false\n      call: kinesis.listtagsfordeliverystream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putrecord\n      description: <p>Writes a single data record into an Amazon Kinesis Data Firehose delivery stream. To write multiple\n        data records into a delivery stream, use <a>PutRecordBatch</a>. Applications using these operations are referred to\n        as producers.</p> <p>\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kinesis.putrecord\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putrecordbatch\n      description: <p>Writes multiple data records into a delivery stream in a single call, which can achieve higher throughput\n        per producer than when writing single records. To write single data records into a delivery stream, use <a>PutRecord</a>.\n        Applicati\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: kinesis.putrecordbatch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startdeliverystreamencryption\n      description: <p>Enables server-side encryption (SSE) for the delivery stream. </p> <p>This operation is asynchronous.\n        It returns immediately. When you invoke it, Kinesis Data Firehose first sets the encryption status of the stream to\n        <code>ENABLING</cod\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kinesis.startdeliverystreamencryption\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stopdeliverystreamencryption\n      description: <p>Disables server-side encryption (SSE) for the delivery stream. </p> <p>This operation is asynchronous.\n        It returns immediately. When you invoke it, Kinesis Data Firehose first sets the encryption status of the stream to\n        <code>DISABLING</c\n   \
  \   hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kinesis.stopdeliverystreamencryption\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tagdeliverystream\n      description: <p>Adds or updates tags for the specified delivery stream. A tag is a key-value pair that you can define\n        and assign to Amazon Web Services resources. If you specify a tag that already exists, the tag value is replaced with\n        the value that yo\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kinesis.tagdeliverystream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: untagdeliverystream\n      description: <p>Removes tags from the specified delivery stream. Removed tags are deleted, and you can't recover them\n        after this operation successfully completes.</p> <p>If you specify a tag that doesn't exist, the operation ignores\n\
  \        it.</p> <p>This oper\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kinesis.untagdeliverystream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatedestination\n      description: <p>Updates the specified destination of the specified delivery stream.</p> <p>Use this operation to change\n        the destination type (for example, to replace the Amazon S3 destination with Amazon Redshift) or change the parameters\n        associated wit\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kinesis.updatedestination\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    KINESIS_TOKEN: KINESIS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/kinesis/refs/heads/main/capabilities/kinesis-capability.yaml
tags:
- Kinesis
- API
tools:
- description: <p>Creates a Kinesis Data Firehose delivery stream.</p> <p>By default, you can create up to 50 delivery streams per Amazon Web Services Region.</p> <p>This is an asynchronous operation that immediately returns. The initial status of the del
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdeliverystream
- description: '<p>Deletes a delivery stream and its data.</p> <p>To check the state of a delivery stream, use <a>DescribeDeliveryStream</a>. You can delete a delivery stream only if it is in one of the following states: <code>ACTIVE</code>, <code>DELETING'
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deletedeliverystream
- description: <p>Describes the specified delivery stream and its status. For example, after your delivery stream is created, call <code>DescribeDeliveryStream</code> to see whether the delivery stream is <code>ACTIVE</code> and therefore ready for data t
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describedeliverystream
- description: <p>Lists your delivery streams in alphabetical order of their names.</p> <p>The number of delivery streams might be too large to return using a single call to <code>ListDeliveryStreams</code>. You can limit the number of delivery streams re
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listdeliverystreams
- description: Lists the tags for the specified delivery stream. This operation has a limit of five transactions per second per account.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listtagsfordeliverystream
- description: <p>Writes a single data record into an Amazon Kinesis Data Firehose delivery stream. To write multiple data records into a delivery stream, use <a>PutRecordBatch</a>. Applications using these operations are referred to as producers.</p> <p>
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: putrecord
- description: <p>Writes multiple data records into a delivery stream in a single call, which can achieve higher throughput per producer than when writing single records. To write single data records into a delivery stream, use <a>PutRecord</a>. Applicati
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: putrecordbatch
- description: <p>Enables server-side encryption (SSE) for the delivery stream. </p> <p>This operation is asynchronous. It returns immediately. When you invoke it, Kinesis Data Firehose first sets the encryption status of the stream to <code>ENABLING</cod
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startdeliverystreamencryption
- description: <p>Disables server-side encryption (SSE) for the delivery stream. </p> <p>This operation is asynchronous. It returns immediately. When you invoke it, Kinesis Data Firehose first sets the encryption status of the stream to <code>DISABLING</c
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stopdeliverystreamencryption
- description: <p>Adds or updates tags for the specified delivery stream. A tag is a key-value pair that you can define and assign to Amazon Web Services resources. If you specify a tag that already exists, the tag value is replaced with the value that yo
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: tagdeliverystream
- description: <p>Removes tags from the specified delivery stream. Removed tags are deleted, and you can't recover them after this operation successfully completes.</p> <p>If you specify a tag that doesn't exist, the operation ignores it.</p> <p>This oper
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: untagdeliverystream
- description: <p>Updates the specified destination of the specified delivery stream.</p> <p>Use this operation to change the destination type (for example, to replace the Amazon S3 destination with Amazon Redshift) or change the parameters associated wit
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedestination
---
