---
categories: []
consumed_apis: []
description: Unified translation management workflow for developers and localization teams. Combines translation CRUD, language management, project management, customer segmentation, and CDN publication into a single capability. Used by engineering teams to automate localization pipelines in CI/CD and by localization managers to manage multilingual content at scale.
layout: capability
name: SimpleLocalize Translation Management
operations:
- description: List translations with filtering by language, key, or namespace
  method: GET
  name: list-translations
  path: /v1/translations
- description: Create or update a translation string
  method: POST
  name: create-translation
  path: /v1/translations
- description: List all languages in the project
  method: GET
  name: list-languages
  path: /v1/languages
- description: Add a new language to the project
  method: POST
  name: create-language
  path: /v1/languages
- description: Remove a language and all its translations
  method: DELETE
  name: delete-language
  path: /v1/languages/{languageKey}
- description: List all translation projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a new translation project
  method: POST
  name: create-project
  path: /v1/projects
- description: List all customer segments
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a new customer segment
  method: POST
  name: create-customer
  path: /v1/customers
- description: Retrieve a specific customer segment
  method: GET
  name: get-customer
  path: /v1/customers/{customerKey}
- description: Remove a customer segment
  method: DELETE
  name: delete-customer
  path: /v1/customers/{customerKey}
- description: Export translations in the requested file format
  method: GET
  name: export-translations
  path: /v1/export
- description: Publish translations to CDN environment
  method: POST
  name: publish-translations
  path: /v1/publish
personas: []
provider_name: SimpleLocalize
provider_slug: simplelocalize
search_terms:
- remove a language and all associated translations from the project
- export translations
- internationalization
- export translations in the requested file format
- create or update a translation string for a specific language and key
- remove a language and all its translations
- create a new customer segment
- delete customer
- delete language
- manage a specific language
- list all customer segments
- add a new language to the project
- manage a specific customer segment
- get customer
- publish translations to cdn environment
- retrieve translations with filtering by language, key, namespace, or text content
- publish translations to cdn environment for production use
- list all translation projects in the account
- content management
- export translations in a specified file format (json, yaml, xliff, etc.)
- create project
- list languages
- add a new language to the translation project
- list all customer segments with their translation overrides
- create translation
- list all languages in the project
- manage translation projects
- export translations in various formats
- create customer
- get details for a specific customer segment
- list translations with filtering by language, key, or namespace
- list projects
- list all languages configured in the translation project
- list customers
- manage project languages
- create language
- list all translation projects
- publish translations to cdn
- create or update a translation string
- translation
- create a new translation project
- remove a customer segment
- publish translations
- retrieve a specific customer segment
- manage customer translation segments
- list translations
- manage translation strings
- localization
- create a new customer segment for localized translation overrides
slug: translation-management
source_filename: translation-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SimpleLocalize Translation Management\n  description: Unified translation management workflow for developers and localization teams. Combines translation CRUD, language\n    management, project management, customer segmentation, and CDN publication into a single capability. Used by engineering\n    teams to automate localization pipelines in CI/CD and by localization managers to manage multilingual content at scale.\n  tags:\n  - Localization\n  - Translation\n  - Internationalization\n  - Content Management\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SIMPLELOCALIZE_API_KEY: SIMPLELOCALIZE_API_KEY\n    SIMPLELOCALIZE_PERSONAL_TOKEN: SIMPLELOCALIZE_PERSONAL_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: simplelocalize\n    baseUri: https://api.simplelocalize.io\n    description: SimpleLocalize translation management REST API\n    authentication:\n      type: apikey\n      key:\
  \ X-SimpleLocalize-Token\n      value: '{{SIMPLELOCALIZE_API_KEY}}'\n      placement: header\n    resources:\n    - name: translations\n      path: /api/v2/translations\n      description: Manage translation strings across languages and namespaces\n      operations:\n      - name: list-translations\n        method: GET\n        description: Retrieve translations with filtering and pagination\n        inputParameters:\n        - name: text\n          in: query\n          type: string\n          required: false\n          description: Search translated text using case-insensitive partial matching\n        - name: textStatus\n          in: query\n          type: string\n          required: false\n          description: Filter by translation completeness (EMPTY, NOT_EMPTY)\n        - name: reviewsStatus\n          in: query\n          type: string\n          required: false\n          description: Filter by review status (REVIEWED, NOT_REVIEWED)\n        - name: key\n          in: query\n\
  \          type: string\n          required: false\n          description: Exact match filter for translation key\n        - name: namespace\n          in: query\n          type: string\n          required: false\n          description: Exact match filter for translation namespace\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: Exact match filter for language identifier\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination page number\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Results per page (max 500)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: translations-v1\n      path: /api/v1/translations\n      description: Create or update translation strings\n      operations:\n\
  \      - name: create-or-update-translation\n        method: POST\n        description: Creates a new translation or updates an existing one\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{tools.key}}'\n            language: '{{tools.language}}'\n            namespace: '{{tools.namespace}}'\n            text: '{{tools.text}}'\n    - name: languages\n      path: /api/v1/languages\n      description: Manage project languages\n      operations:\n      - name: list-languages\n        method: GET\n        description: Retrieves all languages configured in the project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-language\n        method: POST\n        description: Creates a new language in the project\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{tools.key}}'\n            name: '{{tools.name}}'\n    - name: language\n      path: /api/v1/languages/{languageKey}\n      description: Manage a specific language\n      operations:\n      - name: update-language\n        method: PATCH\n        description: Modifies an existing language's key or display name\n        inputParameters:\n        - name: languageKey\n          in: path\n          type: string\n          required: true\n          description: The language identifier to update\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{tools.key}}'\n            name: '{{tools.name}}'\n      - name: delete-language\n        method: DELETE\n        description: Removes a language\
  \ and all its translations from the project\n        inputParameters:\n        - name: languageKey\n          in: path\n          type: string\n          required: true\n          description: The language identifier to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers\n      path: /api/v1/customers\n      description: Manage customer-specific translation segments\n      operations:\n      - name: list-customers\n        method: GET\n        description: Returns all available customers in the project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-customer\n        method: POST\n        description: Creates a new customer record for project-specific translations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        body:\n          type: json\n          data:\n            key: '{{tools.key}}'\n            description: '{{tools.description}}'\n    - name: customer\n      path: /api/v1/customers/{customerKey}\n      description: Manage a specific customer\n      operations:\n      - name: get-customer\n        method: GET\n        description: Retrieves details for a specific customer by their key\n        inputParameters:\n        - name: customerKey\n          in: path\n          type: string\n          required: true\n          description: The unique customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-customer\n        method: PATCH\n        description: Modifies an existing customer's key or description\n        inputParameters:\n        - name: customerKey\n          in: path\n          type: string\n          required: true\n          description: The unique customer\
  \ identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{tools.key}}'\n            description: '{{tools.description}}'\n      - name: delete-customer\n        method: DELETE\n        description: Removes a customer record from the project\n        inputParameters:\n        - name: customerKey\n          in: path\n          type: string\n          required: true\n          description: The unique customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: import\n      path: /api/v1/import\n      description: Import translation files in various formats\n      operations:\n      - name: import-translations\n        method: POST\n        description: Imports translation files in 30+ supported formats\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: export\n      path: /api/v1/export\n      description: Export translation files in various formats\n      operations:\n      - name: export-translations\n        method: GET\n        description: Exports translation files in the requested format\n        inputParameters:\n        - name: downloadFormat\n          in: query\n          type: string\n          required: true\n          description: Target file format for export\n        - name: languageKey\n          in: query\n          type: string\n          required: false\n          description: Export only the specified language\n        - name: namespace\n          in: query\n          type: string\n          required: false\n          description: Export only the specified namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: publish\n\
  \      path: /api/v1/publish\n      description: Publish translations to CDN environments\n      operations:\n      - name: publish-translations\n        method: POST\n        description: Publishes translations to CDN environments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            environment: '{{tools.environment}}'\n    - name: projects\n      path: /api/v2/projects\n      description: Manage translation projects\n      operations:\n      - name: list-projects\n        method: GET\n        description: Retrieves all existing projects with metadata and statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Creates a new translation project\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: translation-management-api\n    description: Unified REST API for SimpleLocalize translation management workflows.\n    resources:\n    - path: /v1/translations\n      name: translations\n      description: Manage translation strings\n      operations:\n      - method: GET\n        name: list-translations\n        description: List translations with filtering by language, key, or namespace\n        call: simplelocalize.list-translations\n        with:\n          language: rest.language\n          key: rest.key\n          namespace: rest.namespace\n          text: rest.text\n          textStatus: rest.textStatus\n          reviewsStatus: rest.reviewsStatus\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-translation\n\
  \        description: Create or update a translation string\n        call: simplelocalize.create-or-update-translation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/languages\n      name: languages\n      description: Manage project languages\n      operations:\n      - method: GET\n        name: list-languages\n        description: List all languages in the project\n        call: simplelocalize.list-languages\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-language\n        description: Add a new language to the project\n        call: simplelocalize.create-language\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/languages/{languageKey}\n      name: language\n      description: Manage a specific language\n      operations:\n      - method: DELETE\n        name: delete-language\n        description: Remove a language and all its translations\n\
  \        call: simplelocalize.delete-language\n        with:\n          languageKey: rest.languageKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects\n      name: projects\n      description: Manage translation projects\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all translation projects\n        call: simplelocalize.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-project\n        description: Create a new translation project\n        call: simplelocalize.create-project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers\n      name: customers\n      description: Manage customer translation segments\n      operations:\n      - method: GET\n        name: list-customers\n        description: List all customer segments\n        call: simplelocalize.list-customers\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-customer\n        description: Create a new customer segment\n        call: simplelocalize.create-customer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers/{customerKey}\n      name: customer\n      description: Manage a specific customer segment\n      operations:\n      - method: GET\n        name: get-customer\n        description: Retrieve a specific customer segment\n        call: simplelocalize.get-customer\n        with:\n          customerKey: rest.customerKey\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-customer\n        description: Remove a customer segment\n        call: simplelocalize.delete-customer\n        with:\n          customerKey: rest.customerKey\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /v1/export\n      name: export\n      description: Export translations in various formats\n      operations:\n      - method: GET\n        name: export-translations\n        description: Export translations in the requested file format\n        call: simplelocalize.export-translations\n        with:\n          downloadFormat: rest.downloadFormat\n          languageKey: rest.languageKey\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/publish\n      name: publish\n      description: Publish translations to CDN\n      operations:\n      - method: POST\n        name: publish-translations\n        description: Publish translations to CDN environment\n        call: simplelocalize.publish-translations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: translation-management-mcp\n    transport: http\n    description: MCP server for AI-assisted\
  \ translation management and localization workflows.\n    tools:\n    - name: list-translations\n      description: Retrieve translations with filtering by language, key, namespace, or text content\n      hints:\n        readOnly: true\n        openWorld: true\n      call: simplelocalize.list-translations\n      with:\n        language: tools.language\n        key: tools.key\n        namespace: tools.namespace\n        text: tools.text\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-translation\n      description: Create or update a translation string for a specific language and key\n      hints:\n        readOnly: false\n        destructive: false\n      call: simplelocalize.create-or-update-translation\n      with:\n        key: tools.key\n        language: tools.language\n        namespace: tools.namespace\n        text: tools.text\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-languages\n      description:\
  \ List all languages configured in the translation project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: simplelocalize.list-languages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-language\n      description: Add a new language to the translation project\n      hints:\n        readOnly: false\n        destructive: false\n      call: simplelocalize.create-language\n      with:\n        key: tools.key\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-language\n      description: Remove a language and all associated translations from the project\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: simplelocalize.delete-language\n      with:\n        languageKey: tools.languageKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-projects\n      description: List all\
  \ translation projects in the account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: simplelocalize.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create a new translation project\n      hints:\n        readOnly: false\n        destructive: false\n      call: simplelocalize.create-project\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-customers\n      description: List all customer segments with their translation overrides\n      hints:\n        readOnly: true\n        openWorld: false\n      call: simplelocalize.list-customers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-customer\n      description: Create a new customer segment for localized translation overrides\n      hints:\n        readOnly: false\n        destructive: false\n      call: simplelocalize.create-customer\n\
  \      with:\n        key: tools.key\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer\n      description: Get details for a specific customer segment\n      hints:\n        readOnly: true\n        openWorld: false\n      call: simplelocalize.get-customer\n      with:\n        customerKey: tools.customerKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-translations\n      description: Export translations in a specified file format (JSON, YAML, XLIFF, etc.)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: simplelocalize.export-translations\n      with:\n        downloadFormat: tools.downloadFormat\n        languageKey: tools.languageKey\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-translations\n      description: Publish translations to CDN environment for\
  \ production use\n      hints:\n        readOnly: false\n        destructive: false\n      call: simplelocalize.publish-translations\n      with:\n        environment: tools.environment\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/simplelocalize/refs/heads/main/capabilities/translation-management.yaml
tags:
- Localization
- Translation
- Internationalization
- Content Management
tools:
- description: Retrieve translations with filtering by language, key, namespace, or text content
  hints:
    openWorld: true
    readOnly: true
  name: list-translations
- description: Create or update a translation string for a specific language and key
  hints:
    destructive: false
    readOnly: false
  name: create-translation
- description: List all languages configured in the translation project
  hints:
    openWorld: false
    readOnly: true
  name: list-languages
- description: Add a new language to the translation project
  hints:
    destructive: false
    readOnly: false
  name: create-language
- description: Remove a language and all associated translations from the project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-language
- description: List all translation projects in the account
  hints:
    openWorld: false
    readOnly: true
  name: list-projects
- description: Create a new translation project
  hints:
    destructive: false
    readOnly: false
  name: create-project
- description: List all customer segments with their translation overrides
  hints:
    openWorld: false
    readOnly: true
  name: list-customers
- description: Create a new customer segment for localized translation overrides
  hints:
    destructive: false
    readOnly: false
  name: create-customer
- description: Get details for a specific customer segment
  hints:
    openWorld: false
    readOnly: true
  name: get-customer
- description: Export translations in a specified file format (JSON, YAML, XLIFF, etc.)
  hints:
    openWorld: false
    readOnly: true
  name: export-translations
- description: Publish translations to CDN environment for production use
  hints:
    destructive: false
    readOnly: false
  name: publish-translations
---
