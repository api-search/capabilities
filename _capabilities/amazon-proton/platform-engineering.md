---
categories:
- ci-cd
consumed_apis: []
description: Workflow capability for platform engineering teams using Amazon Proton to publish standardized templates and automate infrastructure provisioning for development teams. Covers template management, environment deployment, and service lifecycle management.
layout: capability
name: Amazon Proton Platform Engineering
operations:
- description: List environment templates
  method: GET
  name: list-environment-templates
  path: /v1/environment-templates
- description: Create an environment template
  method: POST
  name: create-environment-template
  path: /v1/environment-templates
- description: List deployed environments
  method: GET
  name: list-environments
  path: /v1/environments
- description: Create an environment from a template
  method: POST
  name: create-environment
  path: /v1/environments
- description: List service templates
  method: GET
  name: list-service-templates
  path: /v1/service-templates
- description: Create a service template
  method: POST
  name: create-service-template
  path: /v1/service-templates
- description: List deployed services
  method: GET
  name: list-services
  path: /v1/services
- description: Create a service from a template
  method: POST
  name: create-service
  path: /v1/services
personas: []
provider_name: Amazon Proton
provider_slug: amazon-proton
search_terms:
- list services
- devops
- list all deployed services
- list deployed services
- list service templates
- platform engineering template and deployment workflow
- ci/cd
- create a service from a template
- create environment template
- list environment templates
- create a new service template for standardized application deployments
- amazon
- deploy a new environment from a standardized template
- environment template management for platform engineers
- list all deployed environments
- Application Developer
- create a service template
- list environments
- deployed service management
- deployed environment management
- Platform Engineer
- creates and manages environment and service templates for standardized deployments
- serverless
- list service templates available for developer self-service
- templates
- self-service
- create an environment template
- create a new standardized environment template for developers
- create service template
- create an environment from a template
- infrastructure as code
- list deployed environments
- deploys services using self-service templates provided by platform engineers
- aws
- create service
- create environment
- list environment templates for standardized infrastructure
- service template catalog for developers
- deploy a new application service from a service template
- platform engineering
slug: platform-engineering
source_filename: platform-engineering.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Proton Platform Engineering\n  description: Workflow capability for platform engineering teams using Amazon Proton to publish standardized templates and\n    automate infrastructure provisioning for development teams. Covers template management, environment deployment, and service\n    lifecycle management.\n  tags:\n  - Amazon\n  - AWS\n  - DevOps\n  - Platform Engineering\n  - Infrastructure as Code\n  - Self-Service\n  - Templates\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-proton\n    baseUri: https://proton.{region}.amazonaws.com\n    description: Amazon Proton platform engineering and deployment automation API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n\
  \      placement: header\n    resources:\n    - name: environment-templates\n      path: /environment-templates\n      description: Manage environment templates\n      operations:\n      - name: list-environment-templates\n        method: GET\n        description: List environment templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-environment-template\n        method: POST\n        description: Create a new environment template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n    - name: environments\n      path: /environments\n      description: Manage deployed environments\n      operations:\n      - name: list-environments\n        method: GET\n        description:\
  \ List environments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-environment\n        method: POST\n        description: Create a new environment from a template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            templateName: '{{tools.template_name}}'\n            templateMajorVersion: '{{tools.template_version}}'\n            spec: '{{tools.spec}}'\n    - name: service-templates\n      path: /service-templates\n      description: Manage service templates\n      operations:\n      - name: list-service-templates\n        method: GET\n        description: List service templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    \
  \  - name: create-service-template\n        method: POST\n        description: Create a new service template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n    - name: services\n      path: /services\n      description: Manage deployed services\n      operations:\n      - name: list-services\n        method: GET\n        description: List services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-service\n        method: POST\n        description: Create a new service from a service template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n\
  \            name: '{{tools.name}}'\n            templateName: '{{tools.template_name}}'\n            spec: '{{tools.spec}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: platform-engineering-api\n    description: Unified REST API for Amazon Proton platform engineering workflows.\n    resources:\n    - path: /v1/environment-templates\n      name: environment-templates\n      description: Environment template management for platform engineers\n      operations:\n      - method: GET\n        name: list-environment-templates\n        description: List environment templates\n        call: amazon-proton.list-environment-templates\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-environment-template\n        description: Create an environment template\n        call: amazon-proton.create-environment-template\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/environments\n\
  \      name: environments\n      description: Deployed environment management\n      operations:\n      - method: GET\n        name: list-environments\n        description: List deployed environments\n        call: amazon-proton.list-environments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-environment\n        description: Create an environment from a template\n        call: amazon-proton.create-environment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/service-templates\n      name: service-templates\n      description: Service template catalog for developers\n      operations:\n      - method: GET\n        name: list-service-templates\n        description: List service templates\n        call: amazon-proton.list-service-templates\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-service-template\n   \
  \     description: Create a service template\n        call: amazon-proton.create-service-template\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services\n      name: services\n      description: Deployed service management\n      operations:\n      - method: GET\n        name: list-services\n        description: List deployed services\n        call: amazon-proton.list-services\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-service\n        description: Create a service from a template\n        call: amazon-proton.create-service\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: platform-engineering-mcp\n    transport: http\n    description: MCP server for AI-assisted platform engineering workflows with Amazon Proton.\n    tools:\n    - name: list-environment-templates\n      description: List environment\
  \ templates for standardized infrastructure\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amazon-proton.list-environment-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-environment-template\n      description: Create a new standardized environment template for developers\n      hints:\n        readOnly: false\n        destructive: false\n      call: amazon-proton.create-environment-template\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-environments\n      description: List all deployed environments\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amazon-proton.list-environments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-environment\n      description: Deploy a new environment from a standardized template\n      hints:\n        readOnly: false\n        destructive: false\n      call: amazon-proton.create-environment\n\
  \      with:\n        name: tools.name\n        template_name: tools.template_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-service-templates\n      description: List service templates available for developer self-service\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amazon-proton.list-service-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-service-template\n      description: Create a new service template for standardized application deployments\n      hints:\n        readOnly: false\n        destructive: false\n      call: amazon-proton.create-service-template\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-services\n      description: List all deployed services\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amazon-proton.list-services\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: create-service\n      description: Deploy a new application service from a service template\n      hints:\n        readOnly: false\n        destructive: false\n      call: amazon-proton.create-service\n      with:\n        name: tools.name\n        template_name: tools.template_name\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-proton/refs/heads/main/capabilities/platform-engineering.yaml
tags:
- Amazon
- DevOps
- Platform Engineering
- Infrastructure as Code
- Self-Service
- Templates
tools:
- description: List environment templates for standardized infrastructure
  hints:
    openWorld: true
    readOnly: true
  name: list-environment-templates
- description: Create a new standardized environment template for developers
  hints:
    destructive: false
    readOnly: false
  name: create-environment-template
- description: List all deployed environments
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
- description: Deploy a new environment from a standardized template
  hints:
    destructive: false
    readOnly: false
  name: create-environment
- description: List service templates available for developer self-service
  hints:
    openWorld: true
    readOnly: true
  name: list-service-templates
- description: Create a new service template for standardized application deployments
  hints:
    destructive: false
    readOnly: false
  name: create-service-template
- description: List all deployed services
  hints:
    openWorld: true
    readOnly: true
  name: list-services
- description: Deploy a new application service from a service template
  hints:
    destructive: false
    readOnly: false
  name: create-service
---
