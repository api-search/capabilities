---
consumed_apis:
- lambda
description: Unified workflow capability for Amazon Lambda combining resource management and operations.
layout: capability
name: Amazon Lambda Workflow
operations: []
personas: []
provider_name: Amazon Lambda
provider_slug: amazon-lambda
search_terms:
- event source mappings create event source mapping
- functions create function
- serverless
- functions list functions
- amazon lambda
- event-driven
- returns details about an event source mapping.
- aws
- lists event source mappings.
- faas
- creates a lambda function.
- Administrator
- integrates api into applications
- event source mappings list event source mappings
- manages resources and configurations
- event source mappings get event source mapping
- returns a list of lambda functions, with the version-specific configuration of each.
- returns information about the function or function version.
- functions
- compute
- workflow
- unified workflow for amazon lambda resource management
- Developer
- functions get function
- creates a mapping between an event source and an aws lambda function.
slug: amazon-lambda-workflow
tags:
- Amazon Lambda
- AWS
- Workflow
tools:
- description: Creates a Lambda function.
  hints:
    idempotent: false
    readOnly: false
  name: functions-create-function
- description: Returns a list of Lambda functions, with the version-specific configuration of each.
  hints:
    idempotent: true
    readOnly: true
  name: functions-list-functions
- description: Returns information about the function or function version.
  hints:
    idempotent: true
    readOnly: true
  name: functions-get-function
- description: Creates a mapping between an event source and an AWS Lambda function.
  hints:
    idempotent: false
    readOnly: false
  name: event-source-mappings-create-event-source-mapping
- description: Lists event source mappings.
  hints:
    idempotent: true
    readOnly: true
  name: event-source-mappings-list-event-source-mappings
- description: Returns details about an event source mapping.
  hints:
    idempotent: true
    readOnly: true
  name: event-source-mappings-get-event-source-mapping
---
