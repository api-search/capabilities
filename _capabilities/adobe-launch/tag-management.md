---
categories: []
consumed_apis:
- reactor
- extension
description: Unified workflow for managing Adobe Experience Platform Tags. Combines the Reactor API and Extension API for marketing technologists and web developers managing tag properties, rules, data elements, extensions, and library builds.
layout: capability
name: Adobe Launch Tag Management
operations:
- description: List all companies
  method: GET
  name: list-companies
  path: /v1/companies
- description: List properties for a company
  method: GET
  name: list-properties
  path: /v1/properties
- description: Create a new tag property
  method: POST
  name: create-property
  path: /v1/properties
- description: List rules for a property
  method: GET
  name: list-rules
  path: /v1/rules
- description: Create a new rule
  method: POST
  name: create-rule
  path: /v1/rules
- description: List data elements for a property
  method: GET
  name: list-data-elements
  path: /v1/data-elements
- description: List extensions installed on a property
  method: GET
  name: list-extensions
  path: /v1/extensions
- description: List available extension packages
  method: GET
  name: list-extension-packages
  path: /v1/extension-packages
- description: List libraries for a property
  method: GET
  name: list-libraries
  path: /v1/libraries
- description: List environments for a property
  method: GET
  name: list-environments
  path: /v1/environments
personas: []
provider_name: Adobe Launch
provider_slug: adobe-launch
search_terms:
- list environments
- list properties for a company
- browse available extension packages in the marketplace
- create library
- data element management
- search across all tag management resources
- event forwarding
- extensions
- create a new tag property
- list all companies
- create build
- adobe launch
- list tag properties for a company
- edge network
- list rules configured for a property
- list available extension packages
- create a new tag rule
- list data elements for a property
- list rules for a property
- create a new data element
- data collection
- list libraries
- list companies
- environment management
- list libraries for a property
- list all companies you have access to
- create a new rule
- get property
- library and build management
- create property
- tag management
- list extensions installed on a property
- build a library for deployment
- create rule
- tag property management
- install extension
- list extensions
- install an extension on a property
- search
- list extension packages
- list data elements
- marketing technology
- company management
- list environments for a property
- create data element
- create a new library
- rule management
- extension package marketplace
- get details of a specific property
- list rules
- list properties
- extension management
slug: tag-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Adobe Launch Tag Management\"\n  description: \"Unified workflow for managing Adobe Experience Platform Tags. Combines the Reactor API and Extension API for marketing technologists and web developers managing tag properties, rules, data elements, extensions, and library builds.\"\n  tags:\n    - Adobe Launch\n    - Tag Management\n    - Marketing Technology\n    - Extensions\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ADOBE_ACCESS_TOKEN: ADOBE_ACCESS_TOKEN\n      ADOBE_API_KEY: ADOBE_API_KEY\n      ADOBE_ORG_ID: ADOBE_ORG_ID\n\ncapability:\n  consumes:\n    - import: reactor\n      location: ./shared/reactor.yaml\n    - import: extension\n      location: ./shared/extension.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tag-management-api\n      description: \"Unified REST API for Adobe Launch tag management.\"\n      resources:\n        - path:\
  \ /v1/companies\n          name: companies\n          description: \"Company management\"\n          operations:\n            - method: GET\n              name: list-companies\n              description: \"List all companies\"\n              call: \"reactor.list-companies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/properties\n          name: properties\n          description: \"Tag property management\"\n          operations:\n            - method: GET\n              name: list-properties\n              description: \"List properties for a company\"\n              call: \"reactor.list-properties\"\n              with:\n                companyId: \"rest.companyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-property\n              description: \"Create a new tag property\"\n              call: \"\
  reactor.create-property\"\n              with:\n                companyId: \"rest.companyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rules\n          name: rules\n          description: \"Rule management\"\n          operations:\n            - method: GET\n              name: list-rules\n              description: \"List rules for a property\"\n              call: \"reactor.list-rules\"\n              with:\n                propertyId: \"rest.propertyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-rule\n              description: \"Create a new rule\"\n              call: \"reactor.create-rule\"\n              with:\n                propertyId: \"rest.propertyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data-elements\n\
  \          name: data-elements\n          description: \"Data element management\"\n          operations:\n            - method: GET\n              name: list-data-elements\n              description: \"List data elements for a property\"\n              call: \"reactor.list-data-elements\"\n              with:\n                propertyId: \"rest.propertyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/extensions\n          name: extensions\n          description: \"Extension management\"\n          operations:\n            - method: GET\n              name: list-extensions\n              description: \"List extensions installed on a property\"\n              call: \"reactor.list-extensions\"\n              with:\n                propertyId: \"rest.propertyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/extension-packages\n          name:\
  \ extension-packages\n          description: \"Extension package marketplace\"\n          operations:\n            - method: GET\n              name: list-extension-packages\n              description: \"List available extension packages\"\n              call: \"extension.list-extension-packages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/libraries\n          name: libraries\n          description: \"Library and build management\"\n          operations:\n            - method: GET\n              name: list-libraries\n              description: \"List libraries for a property\"\n              call: \"reactor.list-libraries\"\n              with:\n                propertyId: \"rest.propertyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/environments\n          name: environments\n          description: \"Environment management\"\n   \
  \       operations:\n            - method: GET\n              name: list-environments\n              description: \"List environments for a property\"\n              call: \"reactor.list-environments\"\n              with:\n                propertyId: \"rest.propertyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tag-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Adobe Launch tag management.\"\n      tools:\n        - name: list-companies\n          description: \"List all companies you have access to\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reactor.list-companies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-properties\n          description: \"List tag properties for a company\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"reactor.list-properties\"\n          with:\n            companyId: \"tools.companyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-property\n          description: \"Get details of a specific property\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reactor.get-property\"\n          with:\n            propertyId: \"tools.propertyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-property\n          description: \"Create a new tag property\"\n          hints:\n            readOnly: false\n          call: \"reactor.create-property\"\n          with:\n            companyId: \"tools.companyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-rules\n          description: \"List rules configured for a\
  \ property\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reactor.list-rules\"\n          with:\n            propertyId: \"tools.propertyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-rule\n          description: \"Create a new tag rule\"\n          hints:\n            readOnly: false\n          call: \"reactor.create-rule\"\n          with:\n            propertyId: \"tools.propertyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-data-elements\n          description: \"List data elements for a property\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reactor.list-data-elements\"\n          with:\n            propertyId: \"tools.propertyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-data-element\n\
  \          description: \"Create a new data element\"\n          hints:\n            readOnly: false\n          call: \"reactor.create-data-element\"\n          with:\n            propertyId: \"tools.propertyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-extensions\n          description: \"List extensions installed on a property\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reactor.list-extensions\"\n          with:\n            propertyId: \"tools.propertyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-extension-packages\n          description: \"Browse available extension packages in the marketplace\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"extension.list-extension-packages\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: install-extension\n          description: \"Install an extension on a property\"\n          hints:\n            readOnly: false\n          call: \"extension.install-extension\"\n          with:\n            propertyId: \"tools.propertyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-libraries\n          description: \"List libraries for a property\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reactor.list-libraries\"\n          with:\n            propertyId: \"tools.propertyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-library\n          description: \"Create a new library\"\n          hints:\n            readOnly: false\n          call: \"reactor.create-library\"\n          with:\n            propertyId: \"tools.propertyId\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: create-build\n          description: \"Build a library for deployment\"\n          hints:\n            readOnly: false\n          call: \"reactor.create-build\"\n          with:\n            libraryId: \"tools.libraryId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-environments\n          description: \"List environments for a property\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reactor.list-environments\"\n          with:\n            propertyId: \"tools.propertyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search\n          description: \"Search across all tag management resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reactor.search\"\n          outputParameters:\n            - type: object\n        \
  \      mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-launch/refs/heads/main/capabilities/tag-management.yaml
tags:
- Adobe Launch
- Tag Management
- Marketing Technology
- Extensions
tools:
- description: List all companies you have access to
  hints:
    openWorld: true
    readOnly: true
  name: list-companies
- description: List tag properties for a company
  hints:
    openWorld: true
    readOnly: true
  name: list-properties
- description: Get details of a specific property
  hints:
    openWorld: true
    readOnly: true
  name: get-property
- description: Create a new tag property
  hints:
    readOnly: false
  name: create-property
- description: List rules configured for a property
  hints:
    openWorld: true
    readOnly: true
  name: list-rules
- description: Create a new tag rule
  hints:
    readOnly: false
  name: create-rule
- description: List data elements for a property
  hints:
    openWorld: true
    readOnly: true
  name: list-data-elements
- description: Create a new data element
  hints:
    readOnly: false
  name: create-data-element
- description: List extensions installed on a property
  hints:
    openWorld: true
    readOnly: true
  name: list-extensions
- description: Browse available extension packages in the marketplace
  hints:
    openWorld: true
    readOnly: true
  name: list-extension-packages
- description: Install an extension on a property
  hints:
    readOnly: false
  name: install-extension
- description: List libraries for a property
  hints:
    openWorld: true
    readOnly: true
  name: list-libraries
- description: Create a new library
  hints:
    readOnly: false
  name: create-library
- description: Build a library for deployment
  hints:
    readOnly: false
  name: create-build
- description: List environments for a property
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
- description: Search across all tag management resources
  hints:
    openWorld: true
    readOnly: true
  name: search
---
