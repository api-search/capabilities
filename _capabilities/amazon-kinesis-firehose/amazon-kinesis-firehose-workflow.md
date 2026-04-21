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
- aws
- amazon kinesis data firehose
- creates a kinesis data firehose delivery stream.
- manages resources and configurations
- data delivery
- Developer
- streaming
- delivery streams list delivery streams
- delivery streams create delivery stream
- lists your delivery streams in alphabetical order of their names.
- describes the specified delivery stream.
- Administrator
- analytics
- workflow
- unified workflow for amazon kinesis data firehose resource management
- integrates api into applications
- delivery streams describe delivery stream
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
