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
- streams list streams
- unified workflow for amazon kinesis resource management
- workflow
- real-time
- integrates api into applications
- big data
- provides a summarized description of the specified kinesis data stream.
- aws
- manages resources and configurations
- amazon kinesis
- creates a kinesis data stream.
- data processing
- streaming
- Administrator
- analytics
- streams create stream
- Developer
- lists your kinesis data streams.
- streams describe stream summary
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
