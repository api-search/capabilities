---
categories: []
consumed_apis:
- kinesis
description: Unified workflow capability for Amazon Kinesis combining resource management and operations.
layout: capability
name: Amazon Kinesis Workflow
operations: []
personas: []
provider_name: Amazon Kinesis
provider_slug: amazon-kinesis
search_terms:
- provides a summarized description of the specified kinesis data stream.
- Developer
- Administrator
- analytics
- unified workflow for amazon kinesis resource management
- streams create stream
- data processing
- streaming
- streams describe stream summary
- streams list streams
- real-time
- creates a kinesis data stream.
- lists your kinesis data streams.
- big data
- integrates api into applications
- aws
- workflow
- amazon kinesis
- manages resources and configurations
slug: amazon-kinesis-workflow
tags:
- Amazon Kinesis
- AWS
- Workflow
tools:
- description: Creates a Kinesis data stream.
  hints:
    idempotent: false
    readOnly: false
  name: streams-create-stream
- description: Lists your Kinesis data streams.
  hints:
    idempotent: true
    readOnly: true
  name: streams-list-streams
- description: Provides a summarized description of the specified Kinesis data stream.
  hints:
    idempotent: true
    readOnly: true
  name: streams-describe-stream-summary
---
