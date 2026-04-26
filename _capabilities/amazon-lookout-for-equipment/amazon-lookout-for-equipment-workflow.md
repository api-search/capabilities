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
- unified workflow for amazon lookout for equipment resource management
- integrates api into applications
- workflow
- manages resources and configurations
- provides a json containing the overall information about a specific dataset.
- equipment monitoring
- machine learning
- creates a container (dataset) for a collection of data being ingested for analysis.
- amazon lookout for equipment
- aws
- datasets create dataset
- Developer
- lists all datasets currently available in your account.
- industrial iot
- datasets list datasets
- predictive maintenance
- Administrator
- datasets describe dataset
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
