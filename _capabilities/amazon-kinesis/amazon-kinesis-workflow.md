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
- streams describe stream summary
- analytics
- provides a summarized description of the specified kinesis data stream.
- integrates api into applications
- Developer
- amazon kinesis
- unified workflow for amazon kinesis resource management
- manages resources and configurations
- Administrator
- big data
- workflow
- data processing
- streams create stream
- streaming
- creates a kinesis data stream.
- streams list streams
- aws
- lists your kinesis data streams.
- real-time
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
