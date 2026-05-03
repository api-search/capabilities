---
api_specs:
- filename: simplelocalize-openapi.yml
  format: yaml
  label: simplelocalize
  slug: simplelocalize
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/simplelocalize/refs/heads/main/openapi/simplelocalize-openapi.yml
categories: []
consumed_apis:
- simplelocalize
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
- retrieve a specific customer segment
- create or update a translation string for a specific language and key
- remove a language and all its translations
- translation
- add a new language to the project
- publish translations
- list projects
- create a new customer segment
- export translations in various formats
- export translations in a specified file format (json, yaml, xliff, etc.)
- create a new translation project
- publish translations to cdn environment for production use
- content management
- manage translation strings
- delete language
- retrieve translations with filtering by language, key, namespace, or text content
- manage translation projects
- create or update a translation string
- publish translations to cdn
- list languages
- create project
- localization
- manage a specific language
- internationalization
- create translation
- create language
- list all translation projects
- list translations with filtering by language, key, or namespace
- publish translations to cdn environment
- list translations
- manage a specific customer segment
- delete customer
- add a new language to the translation project
- get details for a specific customer segment
- list all customer segments
- list customers
- remove a customer segment
- list all languages in the project
- list all customer segments with their translation overrides
- list all translation projects in the account
- get customer
- list all languages configured in the translation project
- export translations
- create customer
- remove a language and all associated translations from the project
- manage project languages
- create a new customer segment for localized translation overrides
- manage customer translation segments
- export translations in the requested file format
slug: translation-management
source_filename: translation-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SimpleLocalize Translation Management\"\n  description: >-\n    Unified translation management workflow for developers and localization teams.\n    Combines translation CRUD, language management, project management, customer\n    segmentation, and CDN publication into a single capability. Used by engineering\n    teams to automate localization pipelines in CI/CD and by localization managers\n    to manage multilingual content at scale.\n  tags:\n    - Localization\n    - Translation\n    - Internationalization\n    - Content Management\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SIMPLELOCALIZE_API_KEY: SIMPLELOCALIZE_API_KEY\n      SIMPLELOCALIZE_PERSONAL_TOKEN: SIMPLELOCALIZE_PERSONAL_TOKEN\n\ncapability:\n  consumes:\n    - import: simplelocalize\n      location: ./shared/simplelocalize.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: translation-management-api\n\
  \      description: \"Unified REST API for SimpleLocalize translation management workflows.\"\n      resources:\n        - path: /v1/translations\n          name: translations\n          description: Manage translation strings\n          operations:\n            - method: GET\n              name: list-translations\n              description: List translations with filtering by language, key, or namespace\n              call: \"simplelocalize.list-translations\"\n              with:\n                language: \"rest.language\"\n                key: \"rest.key\"\n                namespace: \"rest.namespace\"\n                text: \"rest.text\"\n                textStatus: \"rest.textStatus\"\n                reviewsStatus: \"rest.reviewsStatus\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-translation\n              description: Create or update a translation string\n         \
  \     call: \"simplelocalize.create-or-update-translation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/languages\n          name: languages\n          description: Manage project languages\n          operations:\n            - method: GET\n              name: list-languages\n              description: List all languages in the project\n              call: \"simplelocalize.list-languages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-language\n              description: Add a new language to the project\n              call: \"simplelocalize.create-language\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/languages/{languageKey}\n          name: language\n          description: Manage a specific language\n          operations:\n\
  \            - method: DELETE\n              name: delete-language\n              description: Remove a language and all its translations\n              call: \"simplelocalize.delete-language\"\n              with:\n                languageKey: \"rest.languageKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects\n          name: projects\n          description: Manage translation projects\n          operations:\n            - method: GET\n              name: list-projects\n              description: List all translation projects\n              call: \"simplelocalize.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: Create a new translation project\n              call: \"simplelocalize.create-project\"\n              outputParameters:\n              \
  \  - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers\n          name: customers\n          description: Manage customer translation segments\n          operations:\n            - method: GET\n              name: list-customers\n              description: List all customer segments\n              call: \"simplelocalize.list-customers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: Create a new customer segment\n              call: \"simplelocalize.create-customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers/{customerKey}\n          name: customer\n          description: Manage a specific customer segment\n          operations:\n            - method: GET\n              name: get-customer\n              description: Retrieve a\
  \ specific customer segment\n              call: \"simplelocalize.get-customer\"\n              with:\n                customerKey: \"rest.customerKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-customer\n              description: Remove a customer segment\n              call: \"simplelocalize.delete-customer\"\n              with:\n                customerKey: \"rest.customerKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/export\n          name: export\n          description: Export translations in various formats\n          operations:\n            - method: GET\n              name: export-translations\n              description: Export translations in the requested file format\n              call: \"simplelocalize.export-translations\"\n              with:\n                downloadFormat: \"\
  rest.downloadFormat\"\n                languageKey: \"rest.languageKey\"\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/publish\n          name: publish\n          description: Publish translations to CDN\n          operations:\n            - method: POST\n              name: publish-translations\n              description: Publish translations to CDN environment\n              call: \"simplelocalize.publish-translations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: translation-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted translation management and localization workflows.\"\n      tools:\n        - name: list-translations\n          description: Retrieve translations with filtering by language, key, namespace, or text\
  \ content\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"simplelocalize.list-translations\"\n          with:\n            language: \"tools.language\"\n            key: \"tools.key\"\n            namespace: \"tools.namespace\"\n            text: \"tools.text\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-translation\n          description: Create or update a translation string for a specific language and key\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"simplelocalize.create-or-update-translation\"\n          with:\n            key: \"tools.key\"\n            language: \"tools.language\"\n            namespace: \"tools.namespace\"\n            text: \"tools.text\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-languages\n          description: List all languages\
  \ configured in the translation project\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"simplelocalize.list-languages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-language\n          description: Add a new language to the translation project\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"simplelocalize.create-language\"\n          with:\n            key: \"tools.key\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-language\n          description: Remove a language and all associated translations from the project\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"simplelocalize.delete-language\"\n          with:\n            languageKey: \"tools.languageKey\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-projects\n          description: List all translation projects in the account\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"simplelocalize.list-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-project\n          description: Create a new translation project\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"simplelocalize.create-project\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-customers\n          description: List all customer segments with their translation overrides\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"simplelocalize.list-customers\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-customer\n          description: Create a new customer segment for localized translation overrides\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"simplelocalize.create-customer\"\n          with:\n            key: \"tools.key\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-customer\n          description: Get details for a specific customer segment\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"simplelocalize.get-customer\"\n          with:\n            customerKey: \"tools.customerKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: export-translations\n          description: Export translations in a specified\
  \ file format (JSON, YAML, XLIFF, etc.)\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"simplelocalize.export-translations\"\n          with:\n            downloadFormat: \"tools.downloadFormat\"\n            languageKey: \"tools.languageKey\"\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-translations\n          description: Publish translations to CDN environment for production use\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"simplelocalize.publish-translations\"\n          with:\n            environment: \"tools.environment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
