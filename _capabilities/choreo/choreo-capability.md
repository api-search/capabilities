---
categories: []
consumed_apis: []
description: The Choreo API Management API provides programmatic access to manage the full lifecycle of APIs on the WSO2 Choreo platform. It allows API creators to create, publish, version, and manage APIs, configure rate limiting policies, and manage API documentation. Choreo is an AI-native internal developer platform that simplifies building, deploying, and managing cloud-native applications.
layout: capability
name: Choreo API Management API
operations:
- description: Choreo List organizations
  method: GET
  name: listorganizations
  path: /organizations
- description: Choreo List projects
  method: GET
  name: listprojects
  path: /organizations/{orgId}/projects
- description: Choreo Create a project
  method: POST
  name: createproject
  path: /organizations/{orgId}/projects
- description: Choreo List components
  method: GET
  name: listcomponents
  path: /organizations/{orgId}/projects/{projectId}/components
- description: Choreo Create a component
  method: POST
  name: createcomponent
  path: /organizations/{orgId}/projects/{projectId}/components
- description: Choreo Get a component
  method: GET
  name: getcomponent
  path: /organizations/{orgId}/projects/{projectId}/components/{componentId}
- description: Choreo Delete a component
  method: DELETE
  name: deletecomponent
  path: /organizations/{orgId}/projects/{projectId}/components/{componentId}
- description: Choreo List builds
  method: GET
  name: listbuilds
  path: /organizations/{orgId}/projects/{projectId}/components/{componentId}/builds
- description: Choreo Trigger a build
  method: POST
  name: createbuild
  path: /organizations/{orgId}/projects/{projectId}/components/{componentId}/builds
- description: Choreo List deployments
  method: GET
  name: listdeployments
  path: /organizations/{orgId}/projects/{projectId}/components/{componentId}/deployments
- description: Choreo Promote a build to an environment
  method: POST
  name: createdeployment
  path: /organizations/{orgId}/projects/{projectId}/components/{componentId}/deployments
- description: Choreo List APIs
  method: GET
  name: listapis
  path: /organizations/{orgId}/apis
- description: Choreo Get API details
  method: GET
  name: getapi
  path: /organizations/{orgId}/apis/{apiId}
- description: Choreo List environments
  method: GET
  name: listenvironments
  path: /organizations/{orgId}/environments
personas: []
provider_name: Choreo
provider_slug: choreo
search_terms:
- createbuild
- devops
- choreo create a project
- choreo promote a build to an environment
- choreo list builds
- choreo
- choreo create a component
- getcomponent
- listbuilds
- ci/cd
- api
- listorganizations
- cloud native
- api management
- listapis
- unified
- orchestration
- choreo get api details
- lifecycle
- ide
- developer portal
- listcomponents
- choreo trigger a build
- ai apps
- kubernetes
- choreo delete a component
- choreo list environments
- observability
- platform engineering
- getapi
- deletecomponent
- internal developer platform
- choreo list projects
- choreo list deployments
- pro-code api composition
- createcomponent
- choreo list components
- createdeployment
- listenvironments
- listdeployments
- choreo list apis
- choreo list organizations
- listprojects
- workflows
- wso2
- choreo get a component
- finops
- createproject
slug: choreo-capability
source_filename: choreo-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Choreo API Management API\n  description: The Choreo API Management API provides programmatic access to manage the full lifecycle of APIs on the WSO2\n    Choreo platform. It allows API creators to create, publish, version, and manage APIs, configure rate limiting policies,\n    and manage API documentation. Choreo is an AI-native internal developer platform that simplifies building, deploying,\n    and managing cloud-native applications.\n  tags:\n  - Choreo\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: choreo\n    baseUri: https://console.choreo.dev/api/v1\n    description: Choreo API Management API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CHOREO_TOKEN}}'\n    resources:\n    - name: organizations\n      path: /organizations\n      operations:\n      - name: listorganizations\n        method: GET\n        description: Choreo List organizations\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-projects\n      path: /organizations/{orgId}/projects\n      operations:\n      - name: listprojects\n        method: GET\n        description: Choreo List projects\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n        method: POST\n        description: Choreo Create a project\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: organizations-orgid-projects-projectid-component\n      path: /organizations/{orgId}/projects/{projectId}/components\n      operations:\n      - name: listcomponents\n        method: GET\n        description: Choreo List components\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcomponent\n        method: POST\n        description: Choreo Create a component\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        - name: projectId\n       \
  \   in: path\n          type: string\n          required: true\n          description: Project identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-projects-projectid-component\n      path: /organizations/{orgId}/projects/{projectId}/components/{componentId}\n      operations:\n      - name: getcomponent\n        method: GET\n        description: Choreo Get a component\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: componentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecomponent\n        method: DELETE\n        description:\
  \ Choreo Delete a component\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: componentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-projects-projectid-component\n      path: /organizations/{orgId}/projects/{projectId}/components/{componentId}/builds\n      operations:\n      - name: listbuilds\n        method: GET\n        description: Choreo List builds\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: componentId\n          in: path\n     \
  \     type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbuild\n        method: POST\n        description: Choreo Trigger a build\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: componentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-projects-projectid-component\n      path: /organizations/{orgId}/projects/{projectId}/components/{componentId}/deployments\n      operations:\n      - name: listdeployments\n        method: GET\n        description: Choreo List deployments\n        inputParameters:\n\
  \        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: componentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdeployment\n        method: POST\n        description: Choreo Promote a build to an environment\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: componentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-apis\n\
  \      path: /organizations/{orgId}/apis\n      operations:\n      - name: listapis\n        method: GET\n        description: Choreo List APIs\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of results to return.\n        - name: offset\n          in: query\n          type: integer\n          description: Number of results to skip.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-apis-apiid\n      path: /organizations/{orgId}/apis/{apiId}\n      operations:\n      - name: getapi\n        method: GET\n        description: Choreo Get API details\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required:\
  \ true\n        - name: apiId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-orgid-environments\n      path: /organizations/{orgId}/environments\n      operations:\n      - name: listenvironments\n        method: GET\n        description: Choreo List environments\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: choreo-rest\n    description: REST adapter for Choreo API Management API.\n    resources:\n    - path: /organizations\n      name: listorganizations\n      operations:\n      - method: GET\n        name:\
  \ listorganizations\n        description: Choreo List organizations\n        call: choreo.listorganizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{orgId}/projects\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: Choreo List projects\n        call: choreo.listprojects\n        with:\n          orgId: rest.orgId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{orgId}/projects\n      name: createproject\n      operations:\n      - method: POST\n        name: createproject\n        description: Choreo Create a project\n        call: choreo.createproject\n        with:\n          orgId: rest.orgId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{orgId}/projects/{projectId}/components\n      name: listcomponents\n      operations:\n      - method: GET\n   \
  \     name: listcomponents\n        description: Choreo List components\n        call: choreo.listcomponents\n        with:\n          orgId: rest.orgId\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{orgId}/projects/{projectId}/components\n      name: createcomponent\n      operations:\n      - method: POST\n        name: createcomponent\n        description: Choreo Create a component\n        call: choreo.createcomponent\n        with:\n          orgId: rest.orgId\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{orgId}/projects/{projectId}/components/{componentId}\n      name: getcomponent\n      operations:\n      - method: GET\n        name: getcomponent\n        description: Choreo Get a component\n        call: choreo.getcomponent\n        with:\n          orgId: rest.orgId\n          projectId: rest.projectId\n\
  \          componentId: rest.componentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{orgId}/projects/{projectId}/components/{componentId}\n      name: deletecomponent\n      operations:\n      - method: DELETE\n        name: deletecomponent\n        description: Choreo Delete a component\n        call: choreo.deletecomponent\n        with:\n          orgId: rest.orgId\n          projectId: rest.projectId\n          componentId: rest.componentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{orgId}/projects/{projectId}/components/{componentId}/builds\n      name: listbuilds\n      operations:\n      - method: GET\n        name: listbuilds\n        description: Choreo List builds\n        call: choreo.listbuilds\n        with:\n          orgId: rest.orgId\n          projectId: rest.projectId\n          componentId: rest.componentId\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /organizations/{orgId}/projects/{projectId}/components/{componentId}/builds\n      name: createbuild\n      operations:\n      - method: POST\n        name: createbuild\n        description: Choreo Trigger a build\n        call: choreo.createbuild\n        with:\n          orgId: rest.orgId\n          projectId: rest.projectId\n          componentId: rest.componentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{orgId}/projects/{projectId}/components/{componentId}/deployments\n      name: listdeployments\n      operations:\n      - method: GET\n        name: listdeployments\n        description: Choreo List deployments\n        call: choreo.listdeployments\n        with:\n          orgId: rest.orgId\n          projectId: rest.projectId\n          componentId: rest.componentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{orgId}/projects/{projectId}/components/{componentId}/deployments\n\
  \      name: createdeployment\n      operations:\n      - method: POST\n        name: createdeployment\n        description: Choreo Promote a build to an environment\n        call: choreo.createdeployment\n        with:\n          orgId: rest.orgId\n          projectId: rest.projectId\n          componentId: rest.componentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{orgId}/apis\n      name: listapis\n      operations:\n      - method: GET\n        name: listapis\n        description: Choreo List APIs\n        call: choreo.listapis\n        with:\n          orgId: rest.orgId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{orgId}/apis/{apiId}\n      name: getapi\n      operations:\n      - method: GET\n        name: getapi\n        description: Choreo Get API details\n        call: choreo.getapi\n        with:\n          orgId: rest.orgId\n          apiId: rest.apiId\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{orgId}/environments\n      name: listenvironments\n      operations:\n      - method: GET\n        name: listenvironments\n        description: Choreo List environments\n        call: choreo.listenvironments\n        with:\n          orgId: rest.orgId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: choreo-mcp\n    transport: http\n    description: MCP adapter for Choreo API Management API for AI agent use.\n    tools:\n    - name: listorganizations\n      description: Choreo List organizations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: choreo.listorganizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprojects\n      description: Choreo List projects\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: choreo.listprojects\n      with:\n        orgId: tools.orgId\n      inputParameters:\n      - name: orgId\n        type: string\n        description: Organization identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproject\n      description: Choreo Create a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: choreo.createproject\n      with:\n        orgId: tools.orgId\n      inputParameters:\n      - name: orgId\n        type: string\n        description: Organization identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcomponents\n      description: Choreo List components\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: choreo.listcomponents\n      with:\n        orgId: tools.orgId\n       \
  \ projectId: tools.projectId\n      inputParameters:\n      - name: orgId\n        type: string\n        description: Organization identifier.\n        required: true\n      - name: projectId\n        type: string\n        description: Project identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcomponent\n      description: Choreo Create a component\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: choreo.createcomponent\n      with:\n        orgId: tools.orgId\n        projectId: tools.projectId\n      inputParameters:\n      - name: orgId\n        type: string\n        description: Organization identifier.\n        required: true\n      - name: projectId\n        type: string\n        description: Project identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcomponent\n      description: Choreo\
  \ Get a component\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: choreo.getcomponent\n      with:\n        orgId: tools.orgId\n        projectId: tools.projectId\n        componentId: tools.componentId\n      inputParameters:\n      - name: orgId\n        type: string\n        description: orgId\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: componentId\n        type: string\n        description: componentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecomponent\n      description: Choreo Delete a component\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: choreo.deletecomponent\n      with:\n        orgId: tools.orgId\n        projectId: tools.projectId\n        componentId: tools.componentId\n      inputParameters:\n\
  \      - name: orgId\n        type: string\n        description: orgId\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: componentId\n        type: string\n        description: componentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbuilds\n      description: Choreo List builds\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: choreo.listbuilds\n      with:\n        orgId: tools.orgId\n        projectId: tools.projectId\n        componentId: tools.componentId\n      inputParameters:\n      - name: orgId\n        type: string\n        description: orgId\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: componentId\n        type: string\n        description: componentId\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbuild\n      description: Choreo Trigger a build\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: choreo.createbuild\n      with:\n        orgId: tools.orgId\n        projectId: tools.projectId\n        componentId: tools.componentId\n      inputParameters:\n      - name: orgId\n        type: string\n        description: orgId\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: componentId\n        type: string\n        description: componentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdeployments\n      description: Choreo List deployments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: choreo.listdeployments\n      with:\n \
  \       orgId: tools.orgId\n        projectId: tools.projectId\n        componentId: tools.componentId\n      inputParameters:\n      - name: orgId\n        type: string\n        description: orgId\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: componentId\n        type: string\n        description: componentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdeployment\n      description: Choreo Promote a build to an environment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: choreo.createdeployment\n      with:\n        orgId: tools.orgId\n        projectId: tools.projectId\n        componentId: tools.componentId\n      inputParameters:\n      - name: orgId\n        type: string\n        description: orgId\n        required: true\n      - name: projectId\n        type: string\n\
  \        description: projectId\n        required: true\n      - name: componentId\n        type: string\n        description: componentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapis\n      description: Choreo List APIs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: choreo.listapis\n      with:\n        orgId: tools.orgId\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: orgId\n        type: string\n        description: Organization identifier.\n        required: true\n      - name: limit\n        type: integer\n        description: Maximum number of results to return.\n      - name: offset\n        type: integer\n        description: Number of results to skip.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapi\n      description: Choreo Get API details\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: choreo.getapi\n      with:\n        orgId: tools.orgId\n        apiId: tools.apiId\n      inputParameters:\n      - name: orgId\n        type: string\n        description: orgId\n        required: true\n      - name: apiId\n        type: string\n        description: apiId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listenvironments\n      description: Choreo List environments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: choreo.listenvironments\n      with:\n        orgId: tools.orgId\n      inputParameters:\n      - name: orgId\n        type: string\n        description: Organization identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CHOREO_TOKEN: CHOREO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/choreo/refs/heads/main/capabilities/choreo-capability.yaml
tags:
- Choreo
- API
tools:
- description: Choreo List organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizations
- description: Choreo List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Choreo Create a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: Choreo List components
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcomponents
- description: Choreo Create a component
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcomponent
- description: Choreo Get a component
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcomponent
- description: Choreo Delete a component
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecomponent
- description: Choreo List builds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbuilds
- description: Choreo Trigger a build
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbuild
- description: Choreo List deployments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeployments
- description: Choreo Promote a build to an environment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdeployment
- description: Choreo List APIs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapis
- description: Choreo Get API details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapi
- description: Choreo List environments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listenvironments
---
