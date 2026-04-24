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
- manages resources and configurations
- instances get instances
- instances create instances
- integrates api into applications
- instances get instance
- unified workflow for amazon lightsail resource management
- Developer
- Administrator
- returns information about all amazon lightsail virtual private servers.
- returns information about a specific amazon lightsail instance.
- amazon lightsail
- aws
- creates one or more amazon lightsail instances.
- workflow
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
