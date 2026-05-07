---
categories: []
consumed_apis: []
description: Unified capability for deploying, managing, and monitoring Java web applications on Apache Tomcat. Covers application deployment, lifecycle management (start/stop/reload), session management, server diagnostics, SSL configuration, and JMX access.
layout: capability
name: Apache Tomcat Application Management
operations:
- description: List all deployed web applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: Start a stopped application
  method: POST
  name: start-application
  path: /v1/applications/start
- description: Stop a running application
  method: POST
  name: stop-application
  path: /v1/applications/stop
- description: Reload an application
  method: POST
  name: reload-application
  path: /v1/applications/reload
- description: Get server OS and JVM information
  method: GET
  name: get-server-info
  path: /v1/diagnostics/server-info
- description: Get JVM thread dump
  method: GET
  name: get-thread-dump
  path: /v1/diagnostics/thread-dump
- description: Get JVM memory and system info
  method: GET
  name: get-vm-info
  path: /v1/diagnostics/vm-info
personas: []
provider_name: Apache Tomcat
provider_slug: tomcat
search_terms:
- list all deployed web applications on apache tomcat
- devops
- start a stopped application
- get server info
- servlet container
- get thread dump
- java
- stop a running application
- reload an application
- open source
- stop a running web application on tomcat (makes it unavailable)
- get jvm memory and system info
- server information
- deployment
- stop application
- apache
- get vm info
- start a stopped web application on tomcat
- get jvm memory usage and system properties from apache tomcat
- web server
- get apache tomcat server os, jvm, and version information
- get a full jvm thread dump from apache tomcat for diagnostics
- list all deployed web applications
- reload a tomcat application to pick up web-inf/classes and lib changes
- list applications
- apache tomcat
- get server os and jvm information
- web application listing
- reload application
- jvm information
- get jvm thread dump
- application server
- thread dump
- start application
slug: application-management
source_filename: application-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Tomcat Application Management\n  description: Unified capability for deploying, managing, and monitoring Java web applications on Apache Tomcat. Covers application\n    deployment, lifecycle management (start/stop/reload), session management, server diagnostics, SSL configuration, and JMX\n    access.\n  tags:\n  - Apache Tomcat\n  - Java\n  - Application Server\n  - DevOps\n  - Deployment\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TOMCAT_USERNAME: TOMCAT_USERNAME\n    TOMCAT_PASSWORD: TOMCAT_PASSWORD\n    TOMCAT_BASE_URL: TOMCAT_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: tomcat\n    baseUri: '{{TOMCAT_BASE_URL}}/manager'\n    description: Apache Tomcat Manager text interface\n    authentication:\n      type: basic\n      username: '{{TOMCAT_USERNAME}}'\n      password: '{{TOMCAT_PASSWORD}}'\n    resources:\n    - name: applications\n      path: /text\n    \
  \  description: Web application lifecycle management\n      operations:\n      - name: list-applications\n        method: GET\n        description: List all deployed applications\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-application\n        method: GET\n        description: Start a stopped web application\n        inputParameters:\n        - name: path\n          in: query\n          type: string\n          required: true\n          description: Application context path\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-application\n        method: GET\n        description: Stop a running web application\n        inputParameters:\n        - name: path\n          in: query\n          type: string\n          required: true\n          description: Application context\
  \ path\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reload-application\n        method: GET\n        description: Reload a web application\n        inputParameters:\n        - name: path\n          in: query\n          type: string\n          required: true\n          description: Application context path\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: undeploy-application\n        method: GET\n        description: Undeploy a web application\n        inputParameters:\n        - name: path\n          in: query\n          type: string\n          required: true\n          description: Application context path\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: diagnostics\n      path: /text\n      description: Server\
  \ diagnostics\n      operations:\n      - name: get-server-info\n        method: GET\n        description: Get server OS, JVM, and version information\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-thread-dump\n        method: GET\n        description: Get full JVM thread dump\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-vm-info\n        method: GET\n        description: Get JVM memory and system properties\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tomcat-management-api\n    description: Unified REST API for Tomcat application deployment and management.\n    resources:\n\
  \    - path: /v1/applications\n      name: applications\n      description: Web application listing\n      operations:\n      - method: GET\n        name: list-applications\n        description: List all deployed web applications\n        call: tomcat.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/start\n      name: application-start\n      description: Start application\n      operations:\n      - method: POST\n        name: start-application\n        description: Start a stopped application\n        call: tomcat.start-application\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/stop\n      name: application-stop\n      description: Stop application\n      operations:\n      - method: POST\n        name: stop-application\n        description: Stop a running application\n        call: tomcat.stop-application\n      \
  \  with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/reload\n      name: application-reload\n      description: Reload application\n      operations:\n      - method: POST\n        name: reload-application\n        description: Reload an application\n        call: tomcat.reload-application\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/diagnostics/server-info\n      name: server-info\n      description: Server information\n      operations:\n      - method: GET\n        name: get-server-info\n        description: Get server OS and JVM information\n        call: tomcat.get-server-info\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/diagnostics/thread-dump\n      name: thread-dump\n      description: Thread dump\n      operations:\n      - method: GET\n        name: get-thread-dump\n\
  \        description: Get JVM thread dump\n        call: tomcat.get-thread-dump\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/diagnostics/vm-info\n      name: vm-info\n      description: JVM information\n      operations:\n      - method: GET\n        name: get-vm-info\n        description: Get JVM memory and system info\n        call: tomcat.get-vm-info\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: tomcat-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Apache Tomcat application management.\n    tools:\n    - name: list-applications\n      description: List all deployed web applications on Apache Tomcat\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tomcat.list-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-application\n      description: Start a stopped\
  \ web application on Tomcat\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tomcat.start-application\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-application\n      description: Stop a running web application on Tomcat (makes it unavailable)\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: tomcat.stop-application\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reload-application\n      description: Reload a Tomcat application to pick up WEB-INF/classes and lib changes\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tomcat.reload-application\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-server-info\n\
  \      description: Get Apache Tomcat server OS, JVM, and version information\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tomcat.get-server-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-thread-dump\n      description: Get a full JVM thread dump from Apache Tomcat for diagnostics\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tomcat.get-thread-dump\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vm-info\n      description: Get JVM memory usage and system properties from Apache Tomcat\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tomcat.get-vm-info\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tomcat/refs/heads/main/capabilities/application-management.yaml
tags:
- Apache Tomcat
- Java
- Application Server
- DevOps
- Deployment
tools:
- description: List all deployed web applications on Apache Tomcat
  hints:
    openWorld: false
    readOnly: true
  name: list-applications
- description: Start a stopped web application on Tomcat
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: start-application
- description: Stop a running web application on Tomcat (makes it unavailable)
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: stop-application
- description: Reload a Tomcat application to pick up WEB-INF/classes and lib changes
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: reload-application
- description: Get Apache Tomcat server OS, JVM, and version information
  hints:
    openWorld: false
    readOnly: true
  name: get-server-info
- description: Get a full JVM thread dump from Apache Tomcat for diagnostics
  hints:
    openWorld: false
    readOnly: true
  name: get-thread-dump
- description: Get JVM memory usage and system properties from Apache Tomcat
  hints:
    openWorld: false
    readOnly: true
  name: get-vm-info
---
