---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Data Catalog Operations
operations: []
personas: []
provider_name: Amazon DataZone
provider_slug: amazon-datazone
search_terms:
- data sharing
- data management
- data catalog
- analytics
- data governance
slug: data-catalog-operations
source_filename: data-catalog-operations.yaml
source_heading: Capability Spec
source_yaml: "id: https://api-evangelist.github.io/amazon-datazone/capabilities/data-catalog-operations.yaml\nname: Data Catalog Operations\ndescription: Workflow-oriented Naftiko capability for data catalog and governance operations using Amazon DataZone, covering domain setup, data asset publishing, access request management, and environment provisioning.\nversion: 1.0.0-alpha1\nspecificationVersion: 1.0.0-alpha1\n\ntags:\n  - Data Catalog\n  - Data Governance\n  - Data Sharing\n  - Data Management\n\nimports:\n  - url: capabilities/shared/datazone.yaml\n    as: datazone\n\npersonas:\n  - name: Data Domain Owner\n    description: Owner of a DataZone domain responsible for governance policies and domain configuration\n  - name: Data Producer\n    description: Data owner who publishes data assets to the DataZone catalog for discovery and sharing\n  - name: Data Consumer\n    description: Analyst or engineer who discovers and requests access to data assets in the catalog\n\nworkflows:\n \
  \ - name: Set Up Data Domain\n    description: Initialize a DataZone domain with projects and environments for data sharing\n    steps:\n      - step: createDomain\n        capability: datazone\n        description: Create a DataZone domain as the governance boundary\n      - step: createProject\n        capability: datazone\n        description: Create an initial project for the data team\n      - step: createEnvironment\n        capability: datazone\n        description: Provision an environment with data access tools\n    persona: Data Domain Owner\n\n  - name: Publish Data Asset\n    description: Catalog a data asset and make it discoverable in the DataZone portal\n    steps:\n      - step: createAsset\n        capability: datazone\n        description: Create a data asset entry in the catalog\n    persona: Data Producer\n\n  - name: Request Data Access\n    description: Discover and request access to a data asset in the catalog\n    steps:\n      - step: searchListings\n        capability:\
  \ datazone\n        description: Browse the catalog to find needed data assets\n      - step: createSubscriptionRequest\n        capability: datazone\n        description: Submit a subscription request with business justification\n      - step: listSubscriptions\n        capability: datazone\n        description: Confirm subscription approval and access\n    persona: Data Consumer\n\nrest:\n  port: 8080\n  baseURL: https://datazone.amazonaws.com\n  auth:\n    type: aws-signature-v4\n    service: datazone\n\nmcp:\n  port: 9090\n  tools:\n    - name: setup_data_domain\n      description: Create a DataZone domain with initial project and environment\n      workflow: Set Up Data Domain\n    - name: publish_data_asset\n      description: Catalog a data asset for discovery in the DataZone portal\n      workflow: Publish Data Asset\n    - name: request_data_access\n      description: Search for and request access to a data asset\n      workflow: Request Data Access\n    - name: list_domains\n\
  \      description: List all DataZone domains\n      operationId: listDomains\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-datazone/refs/heads/main/capabilities/data-catalog-operations.yaml
tags: []
tools: []
---
