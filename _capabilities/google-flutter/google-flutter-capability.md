---
categories: []
consumed_apis: []
description: The Pub.dev API provides programmatic access to the official Dart and Flutter package repository. It allows searching packages, retrieving metadata, version information, package scores, and documentation.
layout: capability
name: Google Flutter Pub.dev API
operations:
- description: Google Flutter Search packages
  method: GET
  name: searchpackages
  path: /search
- description: Google Flutter Get package metadata
  method: GET
  name: getpackage
  path: /packages/{package}
- description: Google Flutter Get package version
  method: GET
  name: getpackageversion
  path: /packages/{package}/versions/{version}
- description: Google Flutter Get package score
  method: GET
  name: getpackagescore
  path: /packages/{package}/score
- description: Google Flutter Get package documentation
  method: GET
  name: getpackagedocs
  path: /documentation/{package}/latest/
personas: []
provider_name: Google Flutter
provider_slug: google-flutter
search_terms:
- google flutter get package documentation
- mobile development
- google flutter get package metadata
- dart
- getpackageversion
- getpackagedocs
- flutter
- google
- api
- google flutter get package score
- getpackagescore
- searchpackages
- google flutter get package version
- getpackage
- cross-platform
- ui framework
- open source
- google flutter search packages
slug: google-flutter-capability
source_filename: google-flutter-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Flutter Pub.dev API\n  description: The Pub.dev API provides programmatic access to the official Dart and Flutter package repository. It allows\n    searching packages, retrieving metadata, version information, package scores, and documentation.\n  tags:\n  - Google\n  - Flutter\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-flutter\n    baseUri: https://pub.dev/api\n    description: Google Flutter Pub.dev API HTTP API.\n    resources:\n    - name: search\n      path: /search\n      operations:\n      - name: searchpackages\n        method: GET\n        description: Google Flutter Search packages\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description: Search query string\n        - name: page\n          in: query\n          type: integer\n          description: Page number for pagination\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packages-package\n      path: /packages/{package}\n      operations:\n      - name: getpackage\n        method: GET\n        description: Google Flutter Get package metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packages-package-versions-version\n      path: /packages/{package}/versions/{version}\n      operations:\n      - name: getpackageversion\n        method: GET\n        description: Google Flutter Get package version\n        inputParameters:\n        - name: version\n          in: path\n          type: string\n          required: true\n          description: The package version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packages-package-score\n     \
  \ path: /packages/{package}/score\n      operations:\n      - name: getpackagescore\n        method: GET\n        description: Google Flutter Get package score\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documentation-package-latest\n      path: /documentation/{package}/latest/\n      operations:\n      - name: getpackagedocs\n        method: GET\n        description: Google Flutter Get package documentation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-flutter-rest\n    description: REST adapter for Google Flutter Pub.dev API.\n    resources:\n    - path: /search\n      name: searchpackages\n      operations:\n      - method: GET\n        name: searchpackages\n        description: Google Flutter Search packages\n        call: google-flutter.searchpackages\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /packages/{package}\n      name: getpackage\n      operations:\n      - method: GET\n        name: getpackage\n        description: Google Flutter Get package metadata\n        call: google-flutter.getpackage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /packages/{package}/versions/{version}\n      name: getpackageversion\n      operations:\n      - method: GET\n        name: getpackageversion\n        description: Google Flutter Get package version\n        call: google-flutter.getpackageversion\n        with:\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /packages/{package}/score\n      name: getpackagescore\n      operations:\n      - method: GET\n        name: getpackagescore\n        description: Google Flutter Get package score\n        call: google-flutter.getpackagescore\n     \
  \   outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documentation/{package}/latest/\n      name: getpackagedocs\n      operations:\n      - method: GET\n        name: getpackagedocs\n        description: Google Flutter Get package documentation\n        call: google-flutter.getpackagedocs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-flutter-mcp\n    transport: http\n    description: MCP adapter for Google Flutter Pub.dev API for AI agent use.\n    tools:\n    - name: searchpackages\n      description: Google Flutter Search packages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-flutter.searchpackages\n      with:\n        q: tools.q\n        page: tools.page\n      inputParameters:\n      - name: q\n        type: string\n        description: Search query string\n      - name: page\n        type: integer\n    \
  \    description: Page number for pagination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpackage\n      description: Google Flutter Get package metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-flutter.getpackage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpackageversion\n      description: Google Flutter Get package version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-flutter.getpackageversion\n      with:\n        version: tools.version\n      inputParameters:\n      - name: version\n        type: string\n        description: The package version\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpackagescore\n      description: Google Flutter Get package score\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: google-flutter.getpackagescore\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpackagedocs\n      description: Google Flutter Get package documentation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-flutter.getpackagedocs\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-flutter/refs/heads/main/capabilities/google-flutter-capability.yaml
tags:
- Google
- Flutter
- API
tools:
- description: Google Flutter Search packages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchpackages
- description: Google Flutter Get package metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpackage
- description: Google Flutter Get package version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpackageversion
- description: Google Flutter Get package score
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpackagescore
- description: Google Flutter Get package documentation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpackagedocs
---
