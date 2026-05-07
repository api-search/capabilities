---
categories: []
consumed_apis: []
description: Unified capability for centralized configuration management across distributed microservices. Enables retrieving externalized configuration, managing encryption, and triggering runtime refresh for DevOps and platform engineering workflows.
layout: capability
name: Spring Cloud Config Configuration Management
operations:
- description: Get externalized configuration for application and profile
  method: GET
  name: get-configuration
  path: /v1/configuration/{application}/{profile}
- description: Get configuration for specific branch/tag/commit
  method: GET
  name: get-configuration-by-label
  path: /v1/configuration/{application}/{profile}/{label}
- description: Encrypt a configuration secret for safe git storage
  method: POST
  name: encrypt-secret
  path: /v1/secrets/encrypt
- description: Trigger configuration refresh via webhook
  method: POST
  name: trigger-refresh
  path: /v1/refresh
personas: []
provider_name: Spring Cloud Config
provider_slug: spring-cloud-config
search_terms:
- get externalized configuration for application and profile
- encrypt a sensitive configuration value (password, api key, token) for secure storage in git with {cipher} prefix notation
- devops
- get configuration by label
- fetch configuration by branch
- distributed systems
- send a configuration change notification to trigger spring cloud bus refresh events across all subscribed microservices
- fetch configuration for a microservice pinned to a specific git branch, tag, or commit hash for canary or blue-green deployment validation
- git
- application configuration by profile and git label
- java
- trigger configuration refresh via webhook
- get configuration for specific branch/tag/commit
- fetch the complete externalized configuration for a microservice from the central config server, resolving all property sources (git, environment, defaults)
- get configuration
- configuration management
- trigger refresh
- verify encryption ready
- encrypt secret
- spring
- configuration refresh trigger
- application configuration by profile
- encrypt a configuration secret for safe git storage
- spring cloud
- fetch service configuration
- verify that the config server has encryption keys configured and is ready for {cipher} property decryption
- gitops
- configuration secret encryption
- externalized configuration
- notify config change
- microservices
- encrypt sensitive value
- platform engineering
slug: configuration-management
source_filename: configuration-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spring Cloud Config Configuration Management\n  description: Unified capability for centralized configuration management across distributed microservices. Enables retrieving\n    externalized configuration, managing encryption, and triggering runtime refresh for DevOps and platform engineering workflows.\n  tags:\n  - Spring Cloud\n  - Configuration Management\n  - Distributed Systems\n  - GitOps\n  - Platform Engineering\n  - DevOps\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPRING_CONFIG_SERVER_URL: SPRING_CONFIG_SERVER_URL\n    SPRING_CONFIG_SERVER_USERNAME: SPRING_CONFIG_SERVER_USERNAME\n    SPRING_CONFIG_SERVER_PASSWORD: SPRING_CONFIG_SERVER_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: spring-cloud-config\n    baseUri: '{{SPRING_CONFIG_SERVER_URL}}'\n    description: Spring Cloud Config Server API\n    authentication:\n      type: basic\n      username: '{{SPRING_CONFIG_SERVER_USERNAME}}'\n\
  \      password: '{{SPRING_CONFIG_SERVER_PASSWORD}}'\n    resources:\n    - name: configuration\n      path: /{application}/{profile}\n      description: Application configuration retrieval\n      operations:\n      - name: get-environment\n        method: GET\n        description: Get environment configuration for application and profile\n        inputParameters:\n        - name: application\n          in: path\n          type: string\n          required: true\n          description: Application name\n        - name: profile\n          in: path\n          type: string\n          required: true\n          description: Active profile(s)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-environment-with-label\n        method: GET\n        description: Get environment configuration with specific git label\n        inputParameters:\n        - name: application\n          in: path\n          type:\
  \ string\n          required: true\n          description: Application name\n        - name: profile\n          in: path\n          type: string\n          required: true\n          description: Active profile(s)\n        - name: label\n          in: path\n          type: string\n          required: true\n          description: Git branch, tag, or commit hash\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: encryption\n      path: /encrypt\n      description: Value encryption\n      operations:\n      - name: encrypt-value\n        method: POST\n        description: Encrypt a plain text value\n        body:\n          type: text\n          data: '{{tools.plaintext}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: check-encryption-status\n        method: GET\n        description: Check encryption configuration\
  \ status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitoring\n      path: /monitor\n      description: Webhook refresh notifications\n      operations:\n      - name: trigger-refresh\n        method: POST\n        description: Trigger configuration refresh from git webhook\n        body:\n          type: json\n          data: '{{tools.payload}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: configuration-management-api\n    description: Unified REST API for distributed configuration management.\n    resources:\n    - path: /v1/configuration/{application}/{profile}\n      name: configuration\n      description: Application configuration by profile\n      operations:\n      - method: GET\n        name: get-configuration\n        description: Get externalized\
  \ configuration for application and profile\n        call: spring-cloud-config.get-environment\n        with:\n          application: rest.application\n          profile: rest.profile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/configuration/{application}/{profile}/{label}\n      name: labeled-configuration\n      description: Application configuration by profile and git label\n      operations:\n      - method: GET\n        name: get-configuration-by-label\n        description: Get configuration for specific branch/tag/commit\n        call: spring-cloud-config.get-environment-with-label\n        with:\n          application: rest.application\n          profile: rest.profile\n          label: rest.label\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/secrets/encrypt\n      name: secret-encryption\n      description: Configuration secret encryption\n      operations:\n      - method: POST\n       \
  \ name: encrypt-secret\n        description: Encrypt a configuration secret for safe git storage\n        call: spring-cloud-config.encrypt-value\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/refresh\n      name: config-refresh\n      description: Configuration refresh trigger\n      operations:\n      - method: POST\n        name: trigger-refresh\n        description: Trigger configuration refresh via webhook\n        call: spring-cloud-config.trigger-refresh\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: configuration-management-mcp\n    transport: http\n    description: MCP server for AI-assisted distributed configuration management.\n    tools:\n    - name: fetch-service-configuration\n      description: Fetch the complete externalized configuration for a microservice from the central Config Server, resolving\n        all property sources (git, environment, defaults)\n\
  \      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-cloud-config.get-environment\n      with:\n        application: tools.application\n        profile: tools.profile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fetch-configuration-by-branch\n      description: Fetch configuration for a microservice pinned to a specific git branch, tag, or commit hash for canary\n        or blue-green deployment validation\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-cloud-config.get-environment-with-label\n      with:\n        application: tools.application\n        profile: tools.profile\n        label: tools.label\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: encrypt-sensitive-value\n      description: Encrypt a sensitive configuration value (password, API key, token) for secure storage in git with {cipher}\n        prefix notation\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: spring-cloud-config.encrypt-value\n      with:\n        plaintext: tools.plaintext\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: verify-encryption-ready\n      description: Verify that the Config Server has encryption keys configured and is ready for {cipher} property decryption\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-cloud-config.check-encryption-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: notify-config-change\n      description: Send a configuration change notification to trigger Spring Cloud Bus refresh events across all subscribed\n        microservices\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: spring-cloud-config.trigger-refresh\n      with:\n        payload: tools.webhookPayload\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spring-cloud-config/refs/heads/main/capabilities/configuration-management.yaml
tags:
- Spring Cloud
- Configuration Management
- Distributed Systems
- GitOps
- Platform Engineering
- DevOps
tools:
- description: Fetch the complete externalized configuration for a microservice from the central Config Server, resolving all property sources (git, environment, defaults)
  hints:
    openWorld: false
    readOnly: true
  name: fetch-service-configuration
- description: Fetch configuration for a microservice pinned to a specific git branch, tag, or commit hash for canary or blue-green deployment validation
  hints:
    openWorld: false
    readOnly: true
  name: fetch-configuration-by-branch
- description: Encrypt a sensitive configuration value (password, API key, token) for secure storage in git with {cipher} prefix notation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: encrypt-sensitive-value
- description: Verify that the Config Server has encryption keys configured and is ready for {cipher} property decryption
  hints:
    openWorld: false
    readOnly: true
  name: verify-encryption-ready
- description: Send a configuration change notification to trigger Spring Cloud Bus refresh events across all subscribed microservices
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: notify-config-change
---
