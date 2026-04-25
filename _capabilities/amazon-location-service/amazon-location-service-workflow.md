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
- creates a map resource in your aws account.
- unified workflow for amazon location service resource management
- Administrator
- retrieves the map resource details.
- map resources create map
- amazon location service
- workflow
- map resources describe map
- maps
- location
- integrates api into applications
- routing
- manages resources and configurations
- geocoding
- lists map resources in your aws account.
- aws
- geofencing
- map resources list maps
- Developer
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
