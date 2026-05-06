---
categories:
- ci-cd
consumed_apis: []
description: Workflow for developers and platform engineers to deploy, manage, and monitor containerized web applications and APIs using AWS App Runner. Covers service lifecycle, deployments, auto-scaling, and VPC connectivity.
layout: capability
name: AWS App Runner Application Deployment Workflow
operations:
- description: List all App Runner services
  method: GET
  name: list-services
  path: /v1/services
- description: Deploy a new containerized application
  method: POST
  name: create-service
  path: /v1/services
- description: Trigger a new deployment
  method: POST
  name: start-deployment
  path: /v1/services/{serviceArn}/deployments
- description: List auto-scaling configurations
  method: GET
  name: list-auto-scaling-configurations
  path: /v1/auto-scaling-configurations
- description: List VPC connectors
  method: GET
  name: list-vpc-connectors
  path: /v1/vpc-connectors
personas: []
provider_name: AWS App Runner
provider_slug: aws-app-runner
search_terms:
- auto-scaling and observability configuration
- aws
- list auto-scaling configurations for capacity management
- list auto-scaling configurations
- vpc connectivity management
- Developer
- update service
- auto-scaling configuration
- get detailed status and configuration of an app runner service
- trigger a new deployment of the current image or code
- list github or bitbucket source code connections
- deploys and manages containerized web applications and apis
- resume a paused service to resume traffic handling
- serverless
- list vpc connectors
- list services
- deployment
- containers
- list auto scaling configurations
- delete an app runner service and all its resources
- application service lifecycle
- deployment management
- pause service
- manages app runner infrastructure, scaling, and vpc connectivity
- create service
- ci/cd
- update application configuration, image, or code source
- list all app runner services
- list vpc connectors for private backend connectivity
- deploy, manage, and scale containerized applications with app runner
- service lifecycle from creation to deletion
- list all app runner services and their status
- deploy a new containerized application
- trigger a new deployment
- deploy a new containerized web application or api
- list connections
- pause a service to save costs during idle periods
- Platform Engineer
- aws app runner
- start deployment
- network connectivity including custom domains and vpc access
- delete service
- microservices
- resume service
- describe service
slug: app-deployment-workflow
source_filename: app-deployment-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AWS App Runner Application Deployment Workflow\n  description: Workflow for developers and platform engineers to deploy, manage, and monitor containerized web applications\n    and APIs using AWS App Runner. Covers service lifecycle, deployments, auto-scaling, and VPC connectivity.\n  tags:\n  - AWS App Runner\n  - AWS\n  - Containers\n  - Deployment\n  - Serverless\n  - CI/CD\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: app-runner\n    baseUri: https://apprunner.{region}.amazonaws.com\n    description: AWS App Runner control plane API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_SIGV4_TOKEN}}'\n      placement: header\n    resources:\n    - name: services\n      path: /20200101/Service\n\
  \      description: Manage App Runner services\n      operations:\n      - name: list-services\n        method: GET\n        description: List all App Runner services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-service\n        method: POST\n        description: Create a new App Runner service\n        body:\n          type: json\n          data:\n            ServiceName: '{{tools.service_name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-service\n        method: POST\n        description: Get details of an App Runner service\n        body:\n          type: json\n          data:\n            ServiceArn: '{{tools.service_arn}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-service\n\
  \        method: POST\n        description: Update an App Runner service configuration\n        body:\n          type: json\n          data:\n            ServiceArn: '{{tools.service_arn}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-service\n        method: POST\n        description: Delete an App Runner service\n        body:\n          type: json\n          data:\n            ServiceArn: '{{tools.service_arn}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: pause-service\n        method: POST\n        description: Pause an App Runner service to stop billing\n        body:\n          type: json\n          data:\n            ServiceArn: '{{tools.service_arn}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: resume-service\n        method: POST\n        description: Resume a paused App Runner service\n        body:\n          type: json\n          data:\n            ServiceArn: '{{tools.service_arn}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-deployment\n        method: POST\n        description: Trigger a new deployment for an App Runner service\n        body:\n          type: json\n          data:\n            ServiceArn: '{{tools.service_arn}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connections\n      path: /20200101/Connection\n      description: Manage connections to source repositories\n      operations:\n      - name: list-connections\n        method: GET\n        description: List all App Runner connections\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: auto-scaling\n      path: /20200101/AutoScalingConfiguration\n      description: Manage auto-scaling configurations\n      operations:\n      - name: list-auto-scaling-configurations\n        method: GET\n        description: List auto-scaling configurations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-auto-scaling-configuration\n        method: POST\n        description: Create an auto-scaling configuration\n        body:\n          type: json\n          data:\n            AutoScalingConfigurationName: '{{tools.config_name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vpc-connectors\n      path: /20200101/VpcConnector\n      description: Manage VPC connectors for private network access\n      operations:\n\
  \      - name: list-vpc-connectors\n        method: GET\n        description: List VPC connectors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: app-runner-workflow-api\n    description: Unified REST API for AWS App Runner application deployment management.\n    resources:\n    - path: /v1/services\n      name: services\n      description: Application service lifecycle\n      operations:\n      - method: GET\n        name: list-services\n        description: List all App Runner services\n        call: app-runner.list-services\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-service\n        description: Deploy a new containerized application\n        call: app-runner.create-service\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{serviceArn}/deployments\n\
  \      name: deployments\n      description: Deployment management\n      operations:\n      - method: POST\n        name: start-deployment\n        description: Trigger a new deployment\n        call: app-runner.start-deployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/auto-scaling-configurations\n      name: auto-scaling\n      description: Auto-scaling configuration\n      operations:\n      - method: GET\n        name: list-auto-scaling-configurations\n        description: List auto-scaling configurations\n        call: app-runner.list-auto-scaling-configurations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vpc-connectors\n      name: vpc-connectors\n      description: VPC connectivity management\n      operations:\n      - method: GET\n        name: list-vpc-connectors\n        description: List VPC connectors\n        call: app-runner.list-vpc-connectors\n        outputParameters:\n  \
  \      - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: app-runner-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted AWS App Runner application deployment.\n    tools:\n    - name: list-services\n      description: List all App Runner services and their status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: app-runner.list-services\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-service\n      description: Deploy a new containerized web application or API\n      hints:\n        readOnly: false\n      call: app-runner.create-service\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-service\n      description: Get detailed status and configuration of an App Runner service\n      hints:\n        readOnly: true\n      call: app-runner.describe-service\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: update-service\n      description: Update application configuration, image, or code source\n      hints:\n        readOnly: false\n      call: app-runner.update-service\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-service\n      description: Delete an App Runner service and all its resources\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: app-runner.delete-service\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-deployment\n      description: Trigger a new deployment of the current image or code\n      hints:\n        readOnly: false\n      call: app-runner.start-deployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pause-service\n      description: Pause a service to save costs during idle periods\n      hints:\n        readOnly: false\n      call: app-runner.pause-service\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: resume-service\n      description: Resume a paused service to resume traffic handling\n      hints:\n        readOnly: false\n      call: app-runner.resume-service\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-connections\n      description: List GitHub or Bitbucket source code connections\n      hints:\n        readOnly: true\n      call: app-runner.list-connections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-auto-scaling-configurations\n      description: List auto-scaling configurations for capacity management\n      hints:\n        readOnly: true\n      call: app-runner.list-auto-scaling-configurations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vpc-connectors\n      description: List VPC connectors for private backend connectivity\n      hints:\n        readOnly: true\n      call: app-runner.list-vpc-connectors\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aws-app-runner/refs/heads/main/capabilities/app-deployment-workflow.yaml
tags:
- AWS App Runner
- Containers
- Deployment
- Serverless
- CI/CD
tools:
- description: List all App Runner services and their status
  hints:
    openWorld: true
    readOnly: true
  name: list-services
- description: Deploy a new containerized web application or API
  hints:
    readOnly: false
  name: create-service
- description: Get detailed status and configuration of an App Runner service
  hints:
    readOnly: true
  name: describe-service
- description: Update application configuration, image, or code source
  hints:
    readOnly: false
  name: update-service
- description: Delete an App Runner service and all its resources
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-service
- description: Trigger a new deployment of the current image or code
  hints:
    readOnly: false
  name: start-deployment
- description: Pause a service to save costs during idle periods
  hints:
    readOnly: false
  name: pause-service
- description: Resume a paused service to resume traffic handling
  hints:
    readOnly: false
  name: resume-service
- description: List GitHub or Bitbucket source code connections
  hints:
    readOnly: true
  name: list-connections
- description: List auto-scaling configurations for capacity management
  hints:
    readOnly: true
  name: list-auto-scaling-configurations
- description: List VPC connectors for private backend connectivity
  hints:
    readOnly: true
  name: list-vpc-connectors
---
