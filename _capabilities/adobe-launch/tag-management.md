---
categories: []
consumed_apis: []
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
- event forwarding
- create a new tag property
- install an extension on a property
- build a library for deployment
- create a new tag rule
- create a new rule
- company management
- create data element
- get details of a specific property
- list tag properties for a company
- library and build management
- create a new data element
- extension management
- data collection
- create build
- list libraries
- list environments
- list properties
- list available extension packages
- list rules configured for a property
- list rules for a property
- create property
- create library
- list properties for a company
- browse available extension packages in the marketplace
- install extension
- tag management
- list data elements
- rule management
- list rules
- adobe launch
- edge network
- extension package marketplace
- create rule
- search across all tag management resources
- tag property management
- list all companies you have access to
- data element management
- get property
- list extension packages
- extensions
- list extensions
- list all companies
- search
- list data elements for a property
- create a new library
- list libraries for a property
- list companies
- environment management
- marketing technology
- list extensions installed on a property
- list environments for a property
slug: tag-management
source_filename: tag-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Launch Tag Management\n  description: Unified workflow for managing Adobe Experience Platform Tags. Combines the Reactor API and Extension API for\n    marketing technologists and web developers managing tag properties, rules, data elements, extensions, and library builds.\n  tags:\n  - Adobe Launch\n  - Tag Management\n  - Marketing Technology\n  - Extensions\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ADOBE_ACCESS_TOKEN: ADOBE_ACCESS_TOKEN\n    ADOBE_API_KEY: ADOBE_API_KEY\n    ADOBE_ORG_ID: ADOBE_ORG_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: reactor\n    baseUri: https://reactor.adobe.io\n    description: Adobe Launch Reactor API\n    authentication:\n      type: bearer\n      token: '{{ADOBE_ACCESS_TOKEN}}'\n    resources:\n    - name: companies\n      path: /companies\n      description: Company management\n      operations:\n      - name: list-companies\n   \
  \     method: GET\n        description: Retrieve all companies you have access to\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-company\n        method: GET\n        description: Retrieve a specific company\n        inputParameters:\n        - name: companyId\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: properties\n      path: /companies/{companyId}/properties\n      description: Tag property management\n      operations:\n      - name: list-properties\n        method: GET\n        description: List properties for a company\n        inputParameters:\n        - name: companyId\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-property\n        method: POST\n        description: Create a new property\n        inputParameters:\n        - name: companyId\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n      - name: get-property\n        method: GET\n        description: Retrieve a specific property\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-property\n     \
  \   method: PATCH\n        description: Update a property\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n      - name: delete-property\n        method: DELETE\n        description: Delete a property\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rules\n      path: /properties/{propertyId}/rules\n      description: Rule management\n      operations:\n      - name: list-rules\n        method: GET\n        description:\
  \ List rules for a property\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-rule\n        method: POST\n        description: Create a new rule\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n      - name: get-rule\n        method: GET\n        description: Retrieve a specific rule\n        inputParameters:\n        - name: ruleId\n          in: path\n          type: string\n          required: true\n     \
  \     description: Rule ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-rule\n        method: DELETE\n        description: Delete a rule\n        inputParameters:\n        - name: ruleId\n          in: path\n          type: string\n          required: true\n          description: Rule ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-elements\n      path: /properties/{propertyId}/data_elements\n      description: Data element management\n      operations:\n      - name: list-data-elements\n        method: GET\n        description: List data elements for a property\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n      - name: create-data-element\n        method: POST\n        description: Create a new data element\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n    - name: extensions\n      path: /properties/{propertyId}/extensions\n      description: Extension management\n      operations:\n      - name: list-extensions\n        method: GET\n        description: List extensions installed on a property\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-extension\n        method: POST\n        description: Install an extension on a property\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n    - name: libraries\n      path: /properties/{propertyId}/libraries\n      description: Library and build management\n      operations:\n      - name: list-libraries\n        method: GET\n        description: List libraries for a property\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-library\n        method: POST\n        description: Create a new library\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n    - name: environments\n      path: /properties/{propertyId}/environments\n      description: Environment management\n      operations:\n      - name: list-environments\n        method: GET\n        description: List environments for a property\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-environment\n        method: POST\n        description: Create a new environment\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n    - name: builds\n      path: /libraries/{libraryId}/builds\n      description: Build management\n      operations:\n      - name: create-build\n        method: POST\n        description: Create a new build from a library\n        inputParameters:\n        - name: libraryId\n          in: path\n          type: string\n          required: true\n          description: Library ID\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: Search across resources\n      operations:\n      - name: search\n        method: POST\n        description: Search across all resources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n  - type: http\n    namespace: extension\n    baseUri: https://reactor.adobe.io\n    description: Adobe Launch Extension API\n    authentication:\n      type: bearer\n      token: '{{ADOBE_ACCESS_TOKEN}}'\n    resources:\n    - name: extension-packages\n      path: /extension_packages\n      description: Extension package management\n      operations:\n      - name: list-extension-packages\n        method: GET\n        description: List all extension packages\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-extension-package\n        method: POST\n        description: Create an extension package\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n      - name: get-extension-package\n        method: GET\n        description: Retrieve a specific extension package\n        inputParameters:\n        - name: extensionPackageId\n          in: path\n          type: string\n          required: true\n          description: Extension package ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-extension-package\n        method: PATCH\n        description: Update an extension package\n        inputParameters:\n        - name: extensionPackageId\n   \
  \       in: path\n          type: string\n          required: true\n          description: Extension package ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n    - name: extensions\n      path: /properties/{propertyId}/extensions\n      description: Extension installation management\n      operations:\n      - name: list-extensions\n        method: GET\n        description: List extensions installed on a property\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: install-extension\n        method: POST\n        description: Install an extension on a property\n        inputParameters:\n\
  \        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n      - name: get-extension\n        method: GET\n        description: Retrieve a specific extension\n        inputParameters:\n        - name: extensionId\n          in: path\n          type: string\n          required: true\n          description: Extension ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-extension\n        method: DELETE\n        description: Delete an extension from a property\n        inputParameters:\n        - name: extensionId\n          in: path\n          type: string\n          required: true\n          description:\
  \ Extension ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tag-management-api\n    description: Unified REST API for Adobe Launch tag management.\n    resources:\n    - path: /v1/companies\n      name: companies\n      description: Company management\n      operations:\n      - method: GET\n        name: list-companies\n        description: List all companies\n        call: reactor.list-companies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/properties\n      name: properties\n      description: Tag property management\n      operations:\n      - method: GET\n        name: list-properties\n        description: List properties for a company\n        call: reactor.list-properties\n        with:\n          companyId: rest.companyId\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \      - method: POST\n        name: create-property\n        description: Create a new tag property\n        call: reactor.create-property\n        with:\n          companyId: rest.companyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rules\n      name: rules\n      description: Rule management\n      operations:\n      - method: GET\n        name: list-rules\n        description: List rules for a property\n        call: reactor.list-rules\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-rule\n        description: Create a new rule\n        call: reactor.create-rule\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-elements\n      name: data-elements\n      description: Data element management\n      operations:\n     \
  \ - method: GET\n        name: list-data-elements\n        description: List data elements for a property\n        call: reactor.list-data-elements\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/extensions\n      name: extensions\n      description: Extension management\n      operations:\n      - method: GET\n        name: list-extensions\n        description: List extensions installed on a property\n        call: reactor.list-extensions\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/extension-packages\n      name: extension-packages\n      description: Extension package marketplace\n      operations:\n      - method: GET\n        name: list-extension-packages\n        description: List available extension packages\n        call: extension.list-extension-packages\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/libraries\n      name: libraries\n      description: Library and build management\n      operations:\n      - method: GET\n        name: list-libraries\n        description: List libraries for a property\n        call: reactor.list-libraries\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/environments\n      name: environments\n      description: Environment management\n      operations:\n      - method: GET\n        name: list-environments\n        description: List environments for a property\n        call: reactor.list-environments\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tag-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Adobe Launch tag management.\n    tools:\n\
  \    - name: list-companies\n      description: List all companies you have access to\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reactor.list-companies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-properties\n      description: List tag properties for a company\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reactor.list-properties\n      with:\n        companyId: tools.companyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-property\n      description: Get details of a specific property\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reactor.get-property\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-property\n      description: Create a new tag property\n      hints:\n        readOnly: false\n      call: reactor.create-property\n\
  \      with:\n        companyId: tools.companyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-rules\n      description: List rules configured for a property\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reactor.list-rules\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-rule\n      description: Create a new tag rule\n      hints:\n        readOnly: false\n      call: reactor.create-rule\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-data-elements\n      description: List data elements for a property\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reactor.list-data-elements\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-data-element\n\
  \      description: Create a new data element\n      hints:\n        readOnly: false\n      call: reactor.create-data-element\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-extensions\n      description: List extensions installed on a property\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reactor.list-extensions\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-extension-packages\n      description: Browse available extension packages in the marketplace\n      hints:\n        readOnly: true\n        openWorld: true\n      call: extension.list-extension-packages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: install-extension\n      description: Install an extension on a property\n      hints:\n        readOnly: false\n      call: extension.install-extension\n\
  \      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-libraries\n      description: List libraries for a property\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reactor.list-libraries\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-library\n      description: Create a new library\n      hints:\n        readOnly: false\n      call: reactor.create-library\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-build\n      description: Build a library for deployment\n      hints:\n        readOnly: false\n      call: reactor.create-build\n      with:\n        libraryId: tools.libraryId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-environments\n      description: List\
  \ environments for a property\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reactor.list-environments\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search\n      description: Search across all tag management resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: reactor.search\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
