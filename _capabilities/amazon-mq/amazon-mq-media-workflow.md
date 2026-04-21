---
consumed_apis:
- mq
description: Workflow capability for Amazon MQ media processing operations for broadcast engineers and media developers.
layout: capability
name: Amazon MQ Workflow
operations:
- description: List jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Amazon MQ
provider_slug: amazon-mq
search_terms:
- list brokers
- aws
- createuser
- developer building media processing applications
- media processing
- media
- aws media processing and delivery
- createconfiguration
- describeuser
- create tags
- workflow
- list configurations
- create broker
- describe user
- Broadcast Engineer
- listtags
- amazon mq media processing workflow
- create configuration
- manage media processing jobs
- listconfigurations
- list jobs
- listbrokers
- broadcasting
- createbroker
- Media Developer
- engineer managing broadcast media workflows
- list tags
- createtags
- create user
slug: amazon-mq-media-workflow
tags:
- AWS
- Media
- Broadcasting
- Workflow
tools:
- description: ListBrokers
  hints:
    openWorld: true
    readOnly: true
  name: list-brokers
- description: CreateBroker
  hints:
    openWorld: true
    readOnly: false
  name: create-broker
- description: ListConfigurations
  hints:
    openWorld: true
    readOnly: true
  name: list-configurations
- description: CreateConfiguration
  hints:
    openWorld: true
    readOnly: false
  name: create-configuration
- description: ListTags
  hints:
    openWorld: true
    readOnly: true
  name: list-tags
- description: CreateTags
  hints:
    openWorld: true
    readOnly: false
  name: create-tags
- description: DescribeUser
  hints:
    openWorld: true
    readOnly: true
  name: describe-user
- description: CreateUser
  hints:
    openWorld: true
    readOnly: false
  name: create-user
---
