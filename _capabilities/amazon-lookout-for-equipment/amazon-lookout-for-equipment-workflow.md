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
- provides a json containing the overall information about a specific dataset.
- equipment monitoring
- datasets describe dataset
- aws
- industrial iot
- Developer
- workflow
- machine learning
- Administrator
- integrates api into applications
- datasets create dataset
- creates a container (dataset) for a collection of data being ingested for analysis.
- datasets list datasets
- unified workflow for amazon lookout for equipment resource management
- manages resources and configurations
- lists all datasets currently available in your account.
- predictive maintenance
- amazon lookout for equipment
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
