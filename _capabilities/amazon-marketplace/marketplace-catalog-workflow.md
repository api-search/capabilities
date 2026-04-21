---
consumed_apis:
- marketplace-catalog
description: Workflow capability for ISV sellers and marketplace operators to publish, update, and manage software products and offers on AWS Marketplace using the Catalog API.
layout: capability
name: Amazon Marketplace - Catalog Management Workflow
operations:
- description: List entities available in the marketplace catalog.
  method: POST
  name: list-entities
  path: /v1/entities
- description: Get details of a specific marketplace entity.
  method: GET
  name: describe-entity
  path: /v1/entities
- description: List change sets in the marketplace catalog.
  method: POST
  name: list-change-sets
  path: /v1/change-sets
- description: Get details of a specific change set.
  method: GET
  name: describe-change-set
  path: /v1/change-sets
- description: Start a change set to publish or update a marketplace entity.
  method: POST
  name: start-change-set
  path: /v1/publish
personas: []
provider_name: Amazon Marketplace
provider_slug: amazon-marketplace
search_terms:
- retrieve the resource-based policy attached to a marketplace entity.
- list change sets
- list change sets in the marketplace catalog.
- cancel an active change set that has not yet completed.
- get details of a specific marketplace entity.
- describe change set
- commerce
- list entities available in the marketplace catalog.
- software catalog
- describe entity
- list change sets for tracking publishing and update operations on marketplace entities.
- isv
- manage change sets for publishing and updating marketplace entities.
- describe marketplace entity
- list software products, offers, and data products available in the aws marketplace catalog.
- manage marketplace entities (products, offers).
- get detailed information about a specific aws marketplace entity including its attributes and status.
- start change set
- get resource policy
- aws
- start a change set to publish or update a marketplace entity.
- initiate a change set to publish a new product or update an existing marketplace listing.
- publishing and updating software products and offers on aws marketplace.
- Marketplace Operator
- amazon
- managing resource policies for marketplace entities.
- ISV Seller
- publish and update marketplace listings.
- list marketplace entities
- get the status and details of a specific marketplace change set.
- independent software vendor publishing and managing products on aws marketplace.
- marketplace
- get details of a specific change set.
- list entities
- cancel change set
- workflow for isv sellers to publish, update, and manage products on aws marketplace.
- platform operator managing marketplace listings, policies, and change sets at scale.
slug: marketplace-catalog-workflow
tags:
- Amazon
- Marketplace
- Commerce
- Software Catalog
- ISV
tools:
- description: List software products, offers, and data products available in the AWS Marketplace catalog.
  hints:
    openWorld: true
    readOnly: true
  name: list-marketplace-entities
- description: Get detailed information about a specific AWS Marketplace entity including its attributes and status.
  hints:
    readOnly: true
  name: describe-marketplace-entity
- description: List change sets for tracking publishing and update operations on marketplace entities.
  hints:
    readOnly: true
  name: list-change-sets
- description: Get the status and details of a specific marketplace change set.
  hints:
    readOnly: true
  name: describe-change-set
- description: Initiate a change set to publish a new product or update an existing marketplace listing.
  hints:
    readOnly: false
  name: start-change-set
- description: Cancel an active change set that has not yet completed.
  hints:
    destructive: false
    readOnly: false
  name: cancel-change-set
- description: Retrieve the resource-based policy attached to a marketplace entity.
  hints:
    readOnly: true
  name: get-resource-policy
---
