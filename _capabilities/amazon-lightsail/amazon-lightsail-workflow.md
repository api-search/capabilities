---
consumed_apis:
- lightsail
description: Unified workflow capability for Amazon Lightsail combining resource management and operations.
layout: capability
name: Amazon Lightsail Workflow
operations: []
personas: []
provider_name: Amazon Lightsail
provider_slug: amazon-lightsail
search_terms:
- instances get instance
- aws
- unified workflow for amazon lightsail resource management
- workflow
- Developer
- creates one or more amazon lightsail instances.
- instances get instances
- manages resources and configurations
- Administrator
- returns information about all amazon lightsail virtual private servers.
- returns information about a specific amazon lightsail instance.
- instances create instances
- integrates api into applications
- amazon lightsail
slug: amazon-lightsail-workflow
tags:
- Amazon Lightsail
- AWS
- Workflow
tools:
- description: Creates one or more Amazon Lightsail instances.
  hints:
    idempotent: false
    readOnly: false
  name: instances-create-instances
- description: Returns information about all Amazon Lightsail virtual private servers.
  hints:
    idempotent: true
    readOnly: true
  name: instances-get-instances
- description: Returns information about a specific Amazon Lightsail instance.
  hints:
    idempotent: true
    readOnly: true
  name: instances-get-instance
---
