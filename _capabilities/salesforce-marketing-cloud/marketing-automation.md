---
categories: []
consumed_apis:
- marketing-cloud-rest
description: Unified workflow for digital marketers to manage contacts, orchestrate customer journeys, and automate multi-channel campaigns across email, SMS, and push channels.
layout: capability
name: Salesforce Marketing Cloud Automation
operations:
- description: Create one or more contacts
  method: POST
  name: create-contacts
  path: /v1/contacts
- description: Search contacts by criteria
  method: POST
  name: search-contacts
  path: /v1/contacts/search
- description: Get a contact
  method: GET
  name: get-contact
  path: /v1/contacts/{contactKey}
- description: Update a contact
  method: PATCH
  name: update-contact
  path: /v1/contacts/{contactKey}
- description: Delete a contact
  method: DELETE
  name: delete-contact
  path: /v1/contacts/{contactKey}
- description: List all journeys
  method: GET
  name: list-journeys
  path: /v1/journeys
- description: Create a journey
  method: POST
  name: create-journey
  path: /v1/journeys
- description: Get a journey
  method: GET
  name: get-journey
  path: /v1/journeys/{id}
- description: Update a journey
  method: PUT
  name: update-journey
  path: /v1/journeys/{id}
- description: Delete a journey
  method: DELETE
  name: delete-journey
  path: /v1/journeys/{id}
- description: Publish a journey
  method: POST
  name: publish-journey
  path: /v1/journeys/{id}/publish
- description: List attribute sets
  method: GET
  name: list-attribute-sets
  path: /v1/attribute-sets
personas: []
provider_name: Salesforce Marketing Cloud
provider_slug: salesforce-marketing-cloud
search_terms:
- update an existing journey specification
- digital marketing
- update contact
- create journey
- list journeys
- search for contacts using filter criteria
- update a contact
- single journey operations
- create a journey
- get journey
- delete a journey
- list all contact attribute set definitions
- create a new customer journey
- publish a journey to activate customer entry
- update an existing contact's attributes
- create contacts
- list attribute sets
- retrieve a contact by contact key
- email
- marketing automation
- search contacts
- attribute set definitions
- email marketing
- single contact operations
- personalization
- salesforce
- get a contact
- contact search
- update a journey
- get contact
- customer journey
- journey management
- automation
- search contacts by criteria
- delete a contact from marketing cloud
- delete a contact
- delete journey
- retrieve a journey by id
- marketing
- list customer journeys with filtering and pagination
- get a journey
- create one or more contacts
- create one or more contacts in marketing cloud
- journey publishing
- publish journey
- delete contact
- contact management
- publish a journey
- update journey
- list all journeys
slug: marketing-automation
source_filename: marketing-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce Marketing Cloud Automation\"\n  description: \"Unified workflow for digital marketers to manage contacts, orchestrate customer journeys, and automate multi-channel campaigns across email, SMS, and push channels.\"\n  tags:\n    - Salesforce\n    - Marketing Automation\n    - Customer Journey\n    - Email Marketing\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      SFMC_ACCESS_TOKEN: SFMC_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: marketing-cloud-rest\n      location: ./shared/marketing-cloud-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: marketing-automation-api\n      description: \"Unified REST API for marketing automation workflows.\"\n      resources:\n        - path: /v1/contacts\n          name: contacts\n          description: \"Contact management\"\n          operations:\n            - method: POST\n              name:\
  \ create-contacts\n              description: \"Create one or more contacts\"\n              call: \"marketing-cloud-rest.create-contacts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/contacts/search\n          name: contact-search\n          description: \"Contact search\"\n          operations:\n            - method: POST\n              name: search-contacts\n              description: \"Search contacts by criteria\"\n              call: \"marketing-cloud-rest.search-contacts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/contacts/{contactKey}\n          name: contact-detail\n          description: \"Single contact operations\"\n          operations:\n            - method: GET\n              name: get-contact\n              description: \"Get a contact\"\n              call: \"marketing-cloud-rest.get-contact\"\n              with:\n\
  \                contactKey: \"rest.contactKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-contact\n              description: \"Update a contact\"\n              call: \"marketing-cloud-rest.update-contact\"\n              with:\n                contactKey: \"rest.contactKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-contact\n              description: \"Delete a contact\"\n              call: \"marketing-cloud-rest.delete-contact\"\n              with:\n                contactKey: \"rest.contactKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/journeys\n          name: journeys\n          description: \"Journey management\"\n          operations:\n            - method: GET\n     \
  \         name: list-journeys\n              description: \"List all journeys\"\n              call: \"marketing-cloud-rest.list-journeys\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-journey\n              description: \"Create a journey\"\n              call: \"marketing-cloud-rest.create-journey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/journeys/{id}\n          name: journey-detail\n          description: \"Single journey operations\"\n          operations:\n            - method: GET\n              name: get-journey\n              description: \"Get a journey\"\n              call: \"marketing-cloud-rest.get-journey\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n\
  \              name: update-journey\n              description: \"Update a journey\"\n              call: \"marketing-cloud-rest.update-journey\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-journey\n              description: \"Delete a journey\"\n              call: \"marketing-cloud-rest.delete-journey\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/journeys/{id}/publish\n          name: journey-publish\n          description: \"Journey publishing\"\n          operations:\n            - method: POST\n              name: publish-journey\n              description: \"Publish a journey\"\n              call: \"marketing-cloud-rest.publish-journey\"\n              with:\n                id: \"rest.id\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/attribute-sets\n          name: attribute-sets\n          description: \"Attribute set definitions\"\n          operations:\n            - method: GET\n              name: list-attribute-sets\n              description: \"List attribute sets\"\n              call: \"marketing-cloud-rest.list-attribute-sets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: marketing-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted marketing automation.\"\n      tools:\n        - name: create-contacts\n          description: \"Create one or more contacts in Marketing Cloud\"\n          hints:\n            readOnly: false\n          call: \"marketing-cloud-rest.create-contacts\"\n          with:\n            contactKey: \"tools.contactKey\"\n\
  \            attributeSets: \"tools.attributeSets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-contacts\n          description: \"Search for contacts using filter criteria\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"marketing-cloud-rest.search-contacts\"\n          with:\n            conditionSet: \"tools.conditionSet\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-contact\n          description: \"Retrieve a contact by contact key\"\n          hints:\n            readOnly: true\n          call: \"marketing-cloud-rest.get-contact\"\n          with:\n            contactKey: \"tools.contactKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-contact\n          description: \"Update an existing contact's attributes\"\n          hints:\n      \
  \      readOnly: false\n            idempotent: true\n          call: \"marketing-cloud-rest.update-contact\"\n          with:\n            contactKey: \"tools.contactKey\"\n            attributeSets: \"tools.attributeSets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-contact\n          description: \"Delete a contact from Marketing Cloud\"\n          hints:\n            destructive: true\n          call: \"marketing-cloud-rest.delete-contact\"\n          with:\n            contactKey: \"tools.contactKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-attribute-sets\n          description: \"List all contact attribute set definitions\"\n          hints:\n            readOnly: true\n          call: \"marketing-cloud-rest.list-attribute-sets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-journeys\n\
  \          description: \"List customer journeys with filtering and pagination\"\n          hints:\n            readOnly: true\n          call: \"marketing-cloud-rest.list-journeys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-journey\n          description: \"Create a new customer journey\"\n          hints:\n            readOnly: false\n          call: \"marketing-cloud-rest.create-journey\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-journey\n          description: \"Retrieve a journey by ID\"\n          hints:\n            readOnly: true\n          call: \"marketing-cloud-rest.get-journey\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-journey\n\
  \          description: \"Update an existing journey specification\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"marketing-cloud-rest.update-journey\"\n          with:\n            id: \"tools.id\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-journey\n          description: \"Delete a journey\"\n          hints:\n            destructive: true\n          call: \"marketing-cloud-rest.delete-journey\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-journey\n          description: \"Publish a journey to activate customer entry\"\n          hints:\n            readOnly: false\n          call: \"marketing-cloud-rest.publish-journey\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce-marketing-cloud/refs/heads/main/capabilities/marketing-automation.yaml
tags:
- Salesforce
- Marketing Automation
- Customer Journey
- Email Marketing
tools:
- description: Create one or more contacts in Marketing Cloud
  hints:
    readOnly: false
  name: create-contacts
- description: Search for contacts using filter criteria
  hints:
    idempotent: true
    readOnly: true
  name: search-contacts
- description: Retrieve a contact by contact key
  hints:
    readOnly: true
  name: get-contact
- description: Update an existing contact's attributes
  hints:
    idempotent: true
    readOnly: false
  name: update-contact
- description: Delete a contact from Marketing Cloud
  hints:
    destructive: true
  name: delete-contact
- description: List all contact attribute set definitions
  hints:
    readOnly: true
  name: list-attribute-sets
- description: List customer journeys with filtering and pagination
  hints:
    readOnly: true
  name: list-journeys
- description: Create a new customer journey
  hints:
    readOnly: false
  name: create-journey
- description: Retrieve a journey by ID
  hints:
    readOnly: true
  name: get-journey
- description: Update an existing journey specification
  hints:
    idempotent: true
    readOnly: false
  name: update-journey
- description: Delete a journey
  hints:
    destructive: true
  name: delete-journey
- description: Publish a journey to activate customer entry
  hints:
    readOnly: false
  name: publish-journey
---
