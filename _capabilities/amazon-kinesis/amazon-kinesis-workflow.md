---
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
- analytics
- big data
- amazon kinesis
- data processing
- unified workflow for amazon kinesis resource management
- streams list streams
- aws
- streaming
- real-time
- Administrator
- integrates api into applications
- manages resources and configurations
- streams create stream
- creates a kinesis data stream.
- provides a summarized description of the specified kinesis data stream.
- workflow
- streams describe stream summary
- lists your kinesis data streams.
- Developer
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
