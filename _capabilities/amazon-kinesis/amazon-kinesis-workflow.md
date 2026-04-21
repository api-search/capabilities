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
- streams create stream
- streaming
- aws
- big data
- Administrator
- analytics
- workflow
- real-time
- data processing
- manages resources and configurations
- amazon kinesis
- integrates api into applications
- streams describe stream summary
- lists your kinesis data streams.
- creates a kinesis data stream.
- unified workflow for amazon kinesis resource management
- Developer
- streams list streams
- provides a summarized description of the specified kinesis data stream.
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
