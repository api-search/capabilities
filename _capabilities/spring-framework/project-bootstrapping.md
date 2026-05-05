---
api_specs:
- filename: spring-initializr-openapi.yml
  format: yaml
  label: spring-initializr
  slug: spring-initializr
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/spring-framework/refs/heads/main/openapi/spring-initializr-openapi.yml
categories: []
consumed_apis:
- spring-initializr
description: Workflow capability for discovering Spring Boot options and generating new Spring Boot projects. Combines Spring Initializr metadata discovery and project generation. Used by developers, DevOps teams, and CI/CD pipelines to scaffold new Spring-based microservices and applications.
layout: capability
name: Spring Framework - Project Bootstrapping
operations:
- description: List all available Spring Boot starter dependencies
  method: GET
  name: list-starters
  path: /v1/starters
- description: Get all available options for Spring Boot project generation
  method: GET
  name: get-options
  path: /v1/options
- description: Generate a Spring Boot project with the specified configuration
  method: GET
  name: generate-project
  path: /v1/projects/generate
personas: []
provider_name: Spring Framework
provider_slug: spring-framework
search_terms:
- spring boot
- framework
- project generation
- enterprise
- generate a spring boot project with the specified configuration
- generate a new spring boot application project. specify build tool (maven-project or gradle-project), language (java/kotlin/groovy), spring boot version, group id, artifact id, and comma-separated dependency ids (e.g., 'web,data-jpa,security,actuator').
- list all available spring boot starter dependencies
- generate project
- get options
- bootstrap
- aop
- discover all available spring boot versions, build tools, languages, and java versions from spring initializr
- microservices
- find available spring boot starter dependencies, optionally filtered by a specific spring boot version
- list starters
- find spring starters
- discover spring boot options
- developer experience
- create spring boot project
- spring boot starter dependency discovery
- spring boot project generation
- dependency injection
- mvc
- spring
- code generation
- ioc
- project generation configuration options
- get all available options for spring boot project generation
- java
slug: project-bootstrapping
source_filename: project-bootstrapping.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Spring Framework - Project Bootstrapping\"\n  description: >-\n    Workflow capability for discovering Spring Boot options and generating new\n    Spring Boot projects. Combines Spring Initializr metadata discovery and\n    project generation. Used by developers, DevOps teams, and CI/CD pipelines\n    to scaffold new Spring-based microservices and applications.\n  tags:\n    - Bootstrap\n    - Code Generation\n    - Developer Experience\n    - Framework\n    - Project Generation\n    - Spring\n    - Spring Boot\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\ncapability:\n  consumes:\n    - import: spring-initializr\n      location: ./shared/spring-initializr.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: project-bootstrapping-api\n      description: \"Unified REST API for Spring Boot project discovery and generation.\"\n      resources:\n        - path: /v1/starters\n          name: starters\n\
  \          description: \"Spring Boot starter dependency discovery\"\n          operations:\n            - method: GET\n              name: list-starters\n              description: \"List all available Spring Boot starter dependencies\"\n              call: \"spring-initializr.list-dependencies\"\n              with:\n                bootVersion: \"rest.bootVersion\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/options\n          name: generation-options\n          description: \"Project generation configuration options\"\n          operations:\n            - method: GET\n              name: get-options\n              description: \"Get all available options for Spring Boot project generation\"\n              call: \"spring-initializr.get-metadata\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/generate\n          name: project-generation\n\
  \          description: \"Spring Boot project generation\"\n          operations:\n            - method: GET\n              name: generate-project\n              description: \"Generate a Spring Boot project with the specified configuration\"\n              call: \"spring-initializr.generate-project\"\n              with:\n                type: \"rest.type\"\n                language: \"rest.language\"\n                bootVersion: \"rest.bootVersion\"\n                groupId: \"rest.groupId\"\n                artifactId: \"rest.artifactId\"\n                dependencies: \"rest.dependencies\"\n                javaVersion: \"rest.javaVersion\"\n                packaging: \"rest.packaging\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: project-bootstrapping-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Spring Boot project bootstrapping and dependency\
  \ discovery.\"\n      tools:\n        - name: discover-spring-boot-options\n          description: \"Discover all available Spring Boot versions, build tools, languages, and Java versions from Spring Initializr\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-initializr.get-metadata\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-spring-starters\n          description: \"Find available Spring Boot starter dependencies, optionally filtered by a specific Spring Boot version\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spring-initializr.list-dependencies\"\n          with:\n            bootVersion: \"tools.bootVersion\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-spring-boot-project\n          description: >-\n            Generate a new Spring Boot application\
  \ project. Specify build tool (maven-project or gradle-project),\n            language (java/kotlin/groovy), Spring Boot version, group ID, artifact ID, and comma-separated\n            dependency IDs (e.g., 'web,data-jpa,security,actuator').\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"spring-initializr.generate-project\"\n          with:\n            type: \"tools.buildTool\"\n            language: \"tools.language\"\n            bootVersion: \"tools.bootVersion\"\n            groupId: \"tools.groupId\"\n            artifactId: \"tools.artifactId\"\n            dependencies: \"tools.dependencies\"\n            javaVersion: \"tools.javaVersion\"\n            packaging: \"tools.packaging\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spring-framework/refs/heads/main/capabilities/project-bootstrapping.yaml
tags:
- Bootstrap
- Code Generation
- Developer Experience
- Framework
- Project Generation
- Spring
- Spring Boot
tools:
- description: Discover all available Spring Boot versions, build tools, languages, and Java versions from Spring Initializr
  hints:
    openWorld: true
    readOnly: true
  name: discover-spring-boot-options
- description: Find available Spring Boot starter dependencies, optionally filtered by a specific Spring Boot version
  hints:
    openWorld: true
    readOnly: true
  name: find-spring-starters
- description: Generate a new Spring Boot application project. Specify build tool (maven-project or gradle-project), language (java/kotlin/groovy), Spring Boot version, group ID, artifact ID, and comma-separated dependency IDs (e.g., 'web,data-jpa,security,actuator').
  hints:
    destructive: false
    readOnly: false
  name: create-spring-boot-project
---
