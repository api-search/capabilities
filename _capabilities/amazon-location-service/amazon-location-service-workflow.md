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
- aws
- amazon location service
- Administrator
- retrieves the map resource details.
- location
- maps
- workflow
- manages resources and configurations
- unified workflow for amazon location service resource management
- geofencing
- integrates api into applications
- geocoding
- map resources list maps
- map resources describe map
- creates a map resource in your aws account.
- map resources create map
- Developer
- lists map resources in your aws account.
- routing
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
