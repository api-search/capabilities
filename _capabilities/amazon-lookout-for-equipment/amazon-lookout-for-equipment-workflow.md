---
consumed_apis:
- lookout-for-equipment
description: Unified workflow capability for Amazon Lookout for Equipment combining resource management and operations.
layout: capability
name: Amazon Lookout for Equipment Workflow
operations: []
personas: []
provider_name: Amazon Lookout for Equipment
provider_slug: amazon-lookout-for-equipment
search_terms:
- industrial iot
- workflow
- creates a container (dataset) for a collection of data being ingested for analysis.
- machine learning
- provides a json containing the overall information about a specific dataset.
- datasets list datasets
- Administrator
- aws
- manages resources and configurations
- datasets describe dataset
- predictive maintenance
- lists all datasets currently available in your account.
- integrates api into applications
- amazon lookout for equipment
- Developer
- equipment monitoring
- unified workflow for amazon lookout for equipment resource management
- datasets create dataset
slug: amazon-lookout-for-equipment-workflow
tags:
- Amazon Lookout for Equipment
- AWS
- Workflow
tools:
- description: Creates a container (dataset) for a collection of data being ingested for analysis.
  hints:
    idempotent: false
    readOnly: false
  name: datasets-create-dataset
- description: Lists all datasets currently available in your account.
  hints:
    idempotent: true
    readOnly: true
  name: datasets-list-datasets
- description: Provides a JSON containing the overall information about a specific dataset.
  hints:
    idempotent: true
    readOnly: true
  name: datasets-describe-dataset
---
