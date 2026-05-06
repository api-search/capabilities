---
categories: []
consumed_apis: []
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
- discover spring boot options
- discover all available spring boot versions, build tools, languages, and java versions from spring initializr
- list starters
- mvc
- aop
- code generation
- java
- framework
- developer experience
- get options
- find spring starters
- project generation
- get all available options for spring boot project generation
- enterprise
- spring boot project generation
- bootstrap
- create spring boot project
- ioc
- generate a new spring boot application project. specify build tool (maven-project or gradle-project), language (java/kotlin/groovy), spring boot version, group id, artifact id, and comma-separated dependency ids (e.g., 'web,data-jpa,security,actuator').
- project generation configuration options
- generate project
- spring boot
- list all available spring boot starter dependencies
- spring boot starter dependency discovery
- dependency injection
- generate a spring boot project with the specified configuration
- spring
- find available spring boot starter dependencies, optionally filtered by a specific spring boot version
- microservices
slug: project-bootstrapping
source_filename: project-bootstrapping.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spring Framework - Project Bootstrapping\n  description: Workflow capability for discovering Spring Boot options and generating new Spring Boot projects. Combines Spring\n    Initializr metadata discovery and project generation. Used by developers, DevOps teams, and CI/CD pipelines to scaffold\n    new Spring-based microservices and applications.\n  tags:\n  - Bootstrap\n  - Code Generation\n  - Developer Experience\n  - Framework\n  - Project Generation\n  - Spring\n  - Spring Boot\n  created: '2026-05-02'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: spring-initializr\n    baseUri: https://start.spring.io\n    description: Official Spring Initializr project generation API\n    resources:\n    - name: metadata\n      path: /\n      description: Initializr metadata discovery\n      operations:\n      - name: get-metadata\n        method: GET\n        description: Get available dependencies, build tools,\
  \ languages, and Java versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dependencies\n      path: /dependencies\n      description: Available Spring Boot starters\n      operations:\n      - name: list-dependencies\n        method: GET\n        description: List all available Spring Boot starter dependencies\n        inputParameters:\n        - name: bootVersion\n          in: query\n          type: string\n          required: false\n          description: Filter by Spring Boot version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: generate\n      path: /starter.zip\n      description: Project archive generation\n      operations:\n      - name: generate-project\n        method: GET\n        description: Generate a Spring Boot project ZIP archive\n        inputParameters:\n        - name: type\n \
  \         in: query\n          type: string\n          required: false\n          description: Build system (maven-project, gradle-project)\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: Language (java, kotlin, groovy)\n        - name: bootVersion\n          in: query\n          type: string\n          required: false\n          description: Spring Boot version\n        - name: groupId\n          in: query\n          type: string\n          required: false\n          description: Maven group ID\n        - name: artifactId\n          in: query\n          type: string\n          required: false\n          description: Maven artifact ID\n        - name: dependencies\n          in: query\n          type: string\n          required: false\n          description: Comma-separated dependency IDs\n        - name: javaVersion\n          in: query\n          type: string\n          required: false\n          description: Java\
  \ version (21, 17, 11)\n        - name: packaging\n          in: query\n          type: string\n          required: false\n          description: Packaging type (jar, war)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: project-bootstrapping-api\n    description: Unified REST API for Spring Boot project discovery and generation.\n    resources:\n    - path: /v1/starters\n      name: starters\n      description: Spring Boot starter dependency discovery\n      operations:\n      - method: GET\n        name: list-starters\n        description: List all available Spring Boot starter dependencies\n        call: spring-initializr.list-dependencies\n        with:\n          bootVersion: rest.bootVersion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/options\n      name: generation-options\n      description: Project\
  \ generation configuration options\n      operations:\n      - method: GET\n        name: get-options\n        description: Get all available options for Spring Boot project generation\n        call: spring-initializr.get-metadata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/generate\n      name: project-generation\n      description: Spring Boot project generation\n      operations:\n      - method: GET\n        name: generate-project\n        description: Generate a Spring Boot project with the specified configuration\n        call: spring-initializr.generate-project\n        with:\n          type: rest.type\n          language: rest.language\n          bootVersion: rest.bootVersion\n          groupId: rest.groupId\n          artifactId: rest.artifactId\n          dependencies: rest.dependencies\n          javaVersion: rest.javaVersion\n          packaging: rest.packaging\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: project-bootstrapping-mcp\n    transport: http\n    description: MCP server for AI-assisted Spring Boot project bootstrapping and dependency discovery.\n    tools:\n    - name: discover-spring-boot-options\n      description: Discover all available Spring Boot versions, build tools, languages, and Java versions from Spring Initializr\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-initializr.get-metadata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-spring-starters\n      description: Find available Spring Boot starter dependencies, optionally filtered by a specific Spring Boot version\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spring-initializr.list-dependencies\n      with:\n        bootVersion: tools.bootVersion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-spring-boot-project\n\
  \      description: Generate a new Spring Boot application project. Specify build tool (maven-project or gradle-project), language\n        (java/kotlin/groovy), Spring Boot version, group ID, artifact ID, and comma-separated dependency IDs (e.g., 'web,data-jpa,security,actuator').\n      hints:\n        readOnly: false\n        destructive: false\n      call: spring-initializr.generate-project\n      with:\n        type: tools.buildTool\n        language: tools.language\n        bootVersion: tools.bootVersion\n        groupId: tools.groupId\n        artifactId: tools.artifactId\n        dependencies: tools.dependencies\n        javaVersion: tools.javaVersion\n        packaging: tools.packaging\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
