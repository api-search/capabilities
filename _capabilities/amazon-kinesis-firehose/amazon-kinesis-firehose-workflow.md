---
consumed_apis:
- kinesis-firehose
description: Unified workflow capability for Amazon Kinesis Data Firehose combining resource management and operations.
layout: capability
name: Amazon Kinesis Data Firehose Workflow
operations: []
personas: []
provider_name: Amazon Kinesis Data Firehose
provider_slug: amazon-kinesis-firehose
search_terms:
- streaming
- creates a kinesis data firehose delivery stream.
- workflow
- delivery streams list delivery streams
- data delivery
- analytics
- lists your delivery streams in alphabetical order of their names.
- aws
- delivery streams describe delivery stream
- delivery streams create delivery stream
- Administrator
- integrates api into applications
- unified workflow for amazon kinesis data firehose resource management
- manages resources and configurations
- describes the specified delivery stream.
- Developer
- amazon kinesis data firehose
slug: amazon-kinesis-firehose-workflow
tags:
- Amazon Kinesis Data Firehose
- AWS
- Workflow
tools:
- description: Creates a Kinesis Data Firehose delivery stream.
  hints:
    idempotent: false
    readOnly: false
  name: delivery-streams-create-delivery-stream
- description: Lists your delivery streams in alphabetical order of their names.
  hints:
    idempotent: true
    readOnly: true
  name: delivery-streams-list-delivery-streams
- description: Describes the specified delivery stream.
  hints:
    idempotent: true
    readOnly: true
  name: delivery-streams-describe-delivery-stream
---
