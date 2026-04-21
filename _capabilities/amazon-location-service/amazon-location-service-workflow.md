---
consumed_apis:
- location-service
description: Unified workflow capability for Amazon Location Service combining resource management and operations.
layout: capability
name: Amazon Location Service Workflow
operations: []
personas: []
provider_name: Amazon Location Service
provider_slug: amazon-location-service
search_terms:
- geofencing
- amazon location service
- retrieves the map resource details.
- creates a map resource in your aws account.
- integrates api into applications
- Developer
- map resources create map
- map resources describe map
- location
- manages resources and configurations
- Administrator
- workflow
- geocoding
- aws
- unified workflow for amazon location service resource management
- map resources list maps
- routing
- lists map resources in your aws account.
- maps
slug: amazon-location-service-workflow
tags:
- Amazon Location Service
- AWS
- Workflow
tools:
- description: Creates a map resource in your AWS account.
  hints:
    idempotent: false
    readOnly: false
  name: map-resources-create-map
- description: Lists map resources in your AWS account.
  hints:
    idempotent: true
    readOnly: true
  name: map-resources-list-maps
- description: Retrieves the map resource details.
  hints:
    idempotent: true
    readOnly: true
  name: map-resources-describe-map
---
