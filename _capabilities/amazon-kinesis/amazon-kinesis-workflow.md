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
- lists your kinesis data streams.
- Administrator
- data processing
- creates a kinesis data stream.
- unified workflow for amazon kinesis resource management
- analytics
- manages resources and configurations
- streaming
- streams describe stream summary
- aws
- amazon kinesis
- streams list streams
- integrates api into applications
- streams create stream
- workflow
- real-time
- big data
- Developer
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
