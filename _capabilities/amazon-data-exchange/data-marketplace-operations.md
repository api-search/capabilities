---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Data Marketplace Operations
operations: []
personas: []
provider_name: Amazon Data Exchange
provider_slug: amazon-data-exchange
search_terms:
- subscriptions
- data marketplace
- third-party data
- data exchange
- aws
- analytics
slug: data-marketplace-operations
source_filename: data-marketplace-operations.yaml
source_heading: Capability Spec
source_yaml: "id: https://api-evangelist.github.io/amazon-data-exchange/capabilities/data-marketplace-operations.yaml\nname: Data Marketplace Operations\ndescription: Workflow-oriented Naftiko capability for data marketplace operations using AWS Data Exchange, covering data publishing, subscription management, and automated data delivery workflows.\nversion: 1.0.0-alpha1\nspecificationVersion: 1.0.0-alpha1\n\ntags:\n  - Data Marketplace\n  - Data Exchange\n  - Data Publishing\n  - Subscriptions\n  - Analytics\n\nimports:\n  - url: capabilities/shared/data-exchange.yaml\n    as: dataExchange\n\npersonas:\n  - name: Data Provider\n    description: Organization publishing data products to the AWS Data Exchange marketplace\n  - name: Data Subscriber\n    description: Organization subscribing to and consuming third-party data products\n  - name: Data Engineer\n    description: Engineer automating data ingestion and delivery pipelines using AWS Data Exchange\n\nworkflows:\n  - name: Publish Data\
  \ Product\n    description: Create and publish a data set with revisions and assets to the marketplace\n    steps:\n      - step: createDataSet\n        capability: dataExchange\n        description: Create the data set with name, description, and asset type\n      - step: createRevision\n        capability: dataExchange\n        description: Create a revision representing this data release\n      - step: createJob\n        capability: dataExchange\n        description: Import assets into the revision via an import job\n      - step: startJob\n        capability: dataExchange\n        description: Start the import job\n      - step: updateRevision\n        capability: dataExchange\n        description: Finalize the revision to make it available to subscribers\n    persona: Data Provider\n\n  - name: Export Subscribed Data\n    description: Export data from a subscribed data set to Amazon S3\n    steps:\n      - step: listDataSets\n        capability: dataExchange\n        description:\
  \ List available entitled data sets from subscriptions\n      - step: listDataSetRevisions\n        capability: dataExchange\n        description: Find the latest revision of the data set\n      - step: createJob\n        capability: dataExchange\n        description: Create an export job to copy assets to S3\n      - step: startJob\n        capability: dataExchange\n        description: Start the export job\n      - step: getJob\n        capability: dataExchange\n        description: Poll job status until completion\n    persona: Data Subscriber\n\n  - name: Automate Data Delivery\n    description: Configure automatic delivery of new data set revisions to S3\n    steps:\n      - step: createEventAction\n        capability: dataExchange\n        description: Create an event action triggered on RevisionPublished\n      - step: listEventActions\n        capability: dataExchange\n        description: Verify the event action is active\n    persona: Data Engineer\n\n  - name: Update Data Release\n\
  \    description: Add a new revision with updated data to an existing data set\n    steps:\n      - step: createRevision\n        capability: dataExchange\n        description: Create a new revision for the update\n      - step: createJob\n        capability: dataExchange\n        description: Import new/updated assets\n      - step: startJob\n        capability: dataExchange\n        description: Start the import job\n      - step: updateRevision\n        capability: dataExchange\n        description: Finalize the revision to notify subscribers\n    persona: Data Provider\n\nrest:\n  port: 8080\n  baseURL: https://dataexchange.amazonaws.com\n  auth:\n    type: aws-signature-v4\n    service: dataexchange\n\nmcp:\n  port: 9090\n  tools:\n    - name: publish_data_product\n      description: Create a data set, add a revision, import assets, and finalize for publishing\n      workflow: Publish Data Product\n    - name: export_subscribed_data\n      description: Export data from a subscribed\
  \ data set to Amazon S3\n      workflow: Export Subscribed Data\n    - name: automate_data_delivery\n      description: Set up automatic delivery of new data revisions to S3\n      workflow: Automate Data Delivery\n    - name: update_data_release\n      description: Add a new revision with updated data to an existing data set\n      workflow: Update Data Release\n    - name: list_data_sets\n      description: List available data sets\n      operationId: listDataSets\n    - name: get_job_status\n      description: Check the status of a data import or export job\n      operationId: getJob\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-data-exchange/refs/heads/main/capabilities/data-marketplace-operations.yaml
tags: []
tools: []
---
