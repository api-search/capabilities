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
- manages resources and configurations
- unified workflow for amazon kinesis resource management
- lists your kinesis data streams.
- data processing
- workflow
- analytics
- streams describe stream summary
- integrates api into applications
- streams create stream
- Administrator
- provides a summarized description of the specified kinesis data stream.
- amazon kinesis
- streaming
- real-time
- aws
- big data
- Developer
- streams list streams
- creates a kinesis data stream.
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
