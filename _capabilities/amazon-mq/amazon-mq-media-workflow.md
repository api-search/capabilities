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
- createtags
- broadcasting
- media
- listtags
- createuser
- list configurations
- list tags
- createbroker
- describeuser
- engineer managing broadcast media workflows
- describe user
- create user
- developer building media processing applications
- listbrokers
- aws media processing and delivery
- list jobs
- list brokers
- manage media processing jobs
- create tags
- media processing
- create configuration
- listconfigurations
- workflow
- amazon mq media processing workflow
- Media Developer
- createconfiguration
- create broker
- aws
- Broadcast Engineer
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
