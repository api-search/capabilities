---
categories: []
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
- analytics
- workflow
- delivery streams describe delivery stream
- amazon kinesis data firehose
- delivery streams list delivery streams
- describes the specified delivery stream.
- lists your delivery streams in alphabetical order of their names.
- aws
- unified workflow for amazon kinesis data firehose resource management
- creates a kinesis data firehose delivery stream.
- Developer
- delivery streams create delivery stream
- manages resources and configurations
- data delivery
- streaming
- Administrator
- integrates api into applications
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
