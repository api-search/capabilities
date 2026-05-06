---
categories: []
consumed_apis: []
description: The Apigee API enables full lifecycle API management including creating and deploying API proxies, managing organizations and environments, configuring API products, and monitoring API analytics.
layout: capability
name: Google Apigee API
operations:
- description: Google Apigee List organizations
  method: GET
  name: listorganizations
  path: /v1/organizations
- description: Google Apigee Get an organization
  method: GET
  name: getorganization
  path: /v1/organizations/{organization}
- description: Google Apigee List API proxies
  method: GET
  name: listapiproxies
  path: /v1/organizations/{organization}/apis
- description: Google Apigee Create an API proxy
  method: POST
  name: createapiproxy
  path: /v1/organizations/{organization}/apis
- description: Google Apigee Get an API proxy
  method: GET
  name: getapiproxy
  path: /v1/organizations/{organization}/apis/{api}
- description: Google Apigee Delete an API proxy
  method: DELETE
  name: deleteapiproxy
  path: /v1/organizations/{organization}/apis/{api}
- description: Google Apigee List environments
  method: GET
  name: listenvironments
  path: /v1/organizations/{organization}/environments
- description: Google Apigee Create an environment
  method: POST
  name: createenvironment
  path: /v1/organizations/{organization}/environments
- description: Google Apigee Get an environment
  method: GET
  name: getenvironment
  path: /v1/organizations/{organization}/environments/{environment}
- description: Google Apigee Delete an environment
  method: DELETE
  name: deleteenvironment
  path: /v1/organizations/{organization}/environments/{environment}
- description: Google Apigee Get deployment status
  method: GET
  name: getdeployment
  path: /v1/organizations/{organization}/environments/{environment}/apis/{api}/revisions/{revision}/deployments
- description: Google Apigee List API products
  method: GET
  name: listapiproducts
  path: /v1/organizations/{organization}/apiproducts
- description: Google Apigee Create an API product
  method: POST
  name: createapiproduct
  path: /v1/organizations/{organization}/apiproducts
- description: Google Apigee List developers
  method: GET
  name: listdevelopers
  path: /v1/organizations/{organization}/developers
- description: Google Apigee Create a developer
  method: POST
  name: createdeveloper
  path: /v1/organizations/{organization}/developers
personas: []
provider_name: Google Apigee
provider_slug: google-apigee
search_terms:
- google apigee create an api product
- google apigee list api products
- google apigee create an environment
- createdeveloper
- getenvironment
- listdevelopers
- createenvironment
- listapiproducts
- google apigee list developers
- deleteapiproxy
- google apigee delete an api proxy
- google
- getorganization
- google apigee list organizations
- enterprise
- google cloud
- apigee
- google apigee create an api proxy
- google apigee get an organization
- listorganizations
- getapiproxy
- createapiproxy
- api
- google apigee get an api proxy
- listenvironments
- listapiproxies
- api gateway
- api management
- google apigee create a developer
- google apigee get an environment
- google apigee list api proxies
- getdeployment
- google apigee list environments
- google apigee get deployment status
- deleteenvironment
- createapiproduct
- google apigee delete an environment
slug: google-apigee-capability
source_filename: google-apigee-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Apigee API\n  description: The Apigee API enables full lifecycle API management including creating and deploying API proxies, managing\n    organizations and environments, configuring API products, and monitoring API analytics.\n  tags:\n  - Google\n  - Apigee\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-apigee\n    baseUri: https://apigee.googleapis.com\n    description: Google Apigee API HTTP API.\n    resources:\n    - name: v1-organizations\n      path: /v1/organizations\n      operations:\n      - name: listorganizations\n        method: GET\n        description: Google Apigee List organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-organizations-organization\n      path: /v1/organizations/{organization}\n      operations:\n      - name: getorganization\n\
  \        method: GET\n        description: Google Apigee Get an organization\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-organizations-organization-apis\n      path: /v1/organizations/{organization}/apis\n      operations:\n      - name: listapiproxies\n        method: GET\n        description: Google Apigee List API proxies\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapiproxy\n        method: POST\n        description: Google Apigee Create an API proxy\n        inputParameters:\n        - name: organization\n          in: path\n         \
  \ type: string\n          required: true\n        - name: name\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-organizations-organization-apis-api\n      path: /v1/organizations/{organization}/apis/{api}\n      operations:\n      - name: getapiproxy\n        method: GET\n        description: Google Apigee Get an API proxy\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        - name: api\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapiproxy\n        method: DELETE\n        description: Google Apigee Delete an API proxy\n        inputParameters:\n        - name: organization\n          in: path\n    \
  \      type: string\n          required: true\n        - name: api\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-organizations-organization-environments\n      path: /v1/organizations/{organization}/environments\n      operations:\n      - name: listenvironments\n        method: GET\n        description: Google Apigee List environments\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createenvironment\n        method: POST\n        description: Google Apigee Create an environment\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-organizations-organization-environments-envir\n      path: /v1/organizations/{organization}/environments/{environment}\n      operations:\n      - name: getenvironment\n        method: GET\n        description: Google Apigee Get an environment\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        - name: environment\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteenvironment\n        method: DELETE\n        description: Google Apigee Delete an environment\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        - name: environment\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-organizations-organization-environments-envir\n      path: /v1/organizations/{organization}/environments/{environment}/apis/{api}/revisions/{revision}/deployments\n      operations:\n      - name: getdeployment\n        method: GET\n        description: Google Apigee Get deployment status\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        - name: environment\n          in: path\n          type: string\n          required: true\n        - name: api\n          in: path\n          type: string\n          required: true\n        - name: revision\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n    - name: v1-organizations-organization-apiproducts\n      path: /v1/organizations/{organization}/apiproducts\n      operations:\n      - name: listapiproducts\n        method: GET\n        description: Google Apigee List API products\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapiproduct\n        method: POST\n        description: Google Apigee Create an API product\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-organizations-organization-developers\n      path: /v1/organizations/{organization}/developers\n\
  \      operations:\n      - name: listdevelopers\n        method: GET\n        description: Google Apigee List developers\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdeveloper\n        method: POST\n        description: Google Apigee Create a developer\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-apigee-rest\n    description: REST adapter for Google Apigee API.\n    resources:\n    - path: /v1/organizations\n      name: listorganizations\n      operations:\n      - method: GET\n        name:\
  \ listorganizations\n        description: Google Apigee List organizations\n        call: google-apigee.listorganizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization}\n      name: getorganization\n      operations:\n      - method: GET\n        name: getorganization\n        description: Google Apigee Get an organization\n        call: google-apigee.getorganization\n        with:\n          organization: rest.organization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization}/apis\n      name: listapiproxies\n      operations:\n      - method: GET\n        name: listapiproxies\n        description: Google Apigee List API proxies\n        call: google-apigee.listapiproxies\n        with:\n          organization: rest.organization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization}/apis\n\
  \      name: createapiproxy\n      operations:\n      - method: POST\n        name: createapiproxy\n        description: Google Apigee Create an API proxy\n        call: google-apigee.createapiproxy\n        with:\n          organization: rest.organization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization}/apis/{api}\n      name: getapiproxy\n      operations:\n      - method: GET\n        name: getapiproxy\n        description: Google Apigee Get an API proxy\n        call: google-apigee.getapiproxy\n        with:\n          organization: rest.organization\n          api: rest.api\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization}/apis/{api}\n      name: deleteapiproxy\n      operations:\n      - method: DELETE\n        name: deleteapiproxy\n        description: Google Apigee Delete an API proxy\n        call: google-apigee.deleteapiproxy\n        with:\n\
  \          organization: rest.organization\n          api: rest.api\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization}/environments\n      name: listenvironments\n      operations:\n      - method: GET\n        name: listenvironments\n        description: Google Apigee List environments\n        call: google-apigee.listenvironments\n        with:\n          organization: rest.organization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization}/environments\n      name: createenvironment\n      operations:\n      - method: POST\n        name: createenvironment\n        description: Google Apigee Create an environment\n        call: google-apigee.createenvironment\n        with:\n          organization: rest.organization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization}/environments/{environment}\n\
  \      name: getenvironment\n      operations:\n      - method: GET\n        name: getenvironment\n        description: Google Apigee Get an environment\n        call: google-apigee.getenvironment\n        with:\n          organization: rest.organization\n          environment: rest.environment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization}/environments/{environment}\n      name: deleteenvironment\n      operations:\n      - method: DELETE\n        name: deleteenvironment\n        description: Google Apigee Delete an environment\n        call: google-apigee.deleteenvironment\n        with:\n          organization: rest.organization\n          environment: rest.environment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization}/environments/{environment}/apis/{api}/revisions/{revision}/deployments\n      name: getdeployment\n      operations:\n      -\
  \ method: GET\n        name: getdeployment\n        description: Google Apigee Get deployment status\n        call: google-apigee.getdeployment\n        with:\n          organization: rest.organization\n          environment: rest.environment\n          api: rest.api\n          revision: rest.revision\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization}/apiproducts\n      name: listapiproducts\n      operations:\n      - method: GET\n        name: listapiproducts\n        description: Google Apigee List API products\n        call: google-apigee.listapiproducts\n        with:\n          organization: rest.organization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization}/apiproducts\n      name: createapiproduct\n      operations:\n      - method: POST\n        name: createapiproduct\n        description: Google Apigee Create an API product\n        call:\
  \ google-apigee.createapiproduct\n        with:\n          organization: rest.organization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization}/developers\n      name: listdevelopers\n      operations:\n      - method: GET\n        name: listdevelopers\n        description: Google Apigee List developers\n        call: google-apigee.listdevelopers\n        with:\n          organization: rest.organization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization}/developers\n      name: createdeveloper\n      operations:\n      - method: POST\n        name: createdeveloper\n        description: Google Apigee Create a developer\n        call: google-apigee.createdeveloper\n        with:\n          organization: rest.organization\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-apigee-mcp\n\
  \    transport: http\n    description: MCP adapter for Google Apigee API for AI agent use.\n    tools:\n    - name: listorganizations\n      description: Google Apigee List organizations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-apigee.listorganizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorganization\n      description: Google Apigee Get an organization\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-apigee.getorganization\n      with:\n        organization: tools.organization\n      inputParameters:\n      - name: organization\n        type: string\n        description: organization\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapiproxies\n      description: Google Apigee List API proxies\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: google-apigee.listapiproxies\n      with:\n        organization: tools.organization\n      inputParameters:\n      - name: organization\n        type: string\n        description: organization\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapiproxy\n      description: Google Apigee Create an API proxy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-apigee.createapiproxy\n      with:\n        organization: tools.organization\n        name: tools.name\n      inputParameters:\n      - name: organization\n        type: string\n        description: organization\n        required: true\n      - name: name\n        type: string\n        description: name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapiproxy\n      description: Google Apigee Get an API proxy\n      hints:\n       \
  \ readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-apigee.getapiproxy\n      with:\n        organization: tools.organization\n        api: tools.api\n      inputParameters:\n      - name: organization\n        type: string\n        description: organization\n        required: true\n      - name: api\n        type: string\n        description: api\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteapiproxy\n      description: Google Apigee Delete an API proxy\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-apigee.deleteapiproxy\n      with:\n        organization: tools.organization\n        api: tools.api\n      inputParameters:\n      - name: organization\n        type: string\n        description: organization\n        required: true\n      - name: api\n        type: string\n        description: api\n        required: true\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listenvironments\n      description: Google Apigee List environments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-apigee.listenvironments\n      with:\n        organization: tools.organization\n      inputParameters:\n      - name: organization\n        type: string\n        description: organization\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createenvironment\n      description: Google Apigee Create an environment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-apigee.createenvironment\n      with:\n        organization: tools.organization\n      inputParameters:\n      - name: organization\n        type: string\n        description: organization\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getenvironment\n      description: Google Apigee Get an environment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-apigee.getenvironment\n      with:\n        organization: tools.organization\n        environment: tools.environment\n      inputParameters:\n      - name: organization\n        type: string\n        description: organization\n        required: true\n      - name: environment\n        type: string\n        description: environment\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteenvironment\n      description: Google Apigee Delete an environment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-apigee.deleteenvironment\n      with:\n        organization: tools.organization\n        environment: tools.environment\n      inputParameters:\n      - name: organization\n\
  \        type: string\n        description: organization\n        required: true\n      - name: environment\n        type: string\n        description: environment\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdeployment\n      description: Google Apigee Get deployment status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-apigee.getdeployment\n      with:\n        organization: tools.organization\n        environment: tools.environment\n        api: tools.api\n        revision: tools.revision\n      inputParameters:\n      - name: organization\n        type: string\n        description: organization\n        required: true\n      - name: environment\n        type: string\n        description: environment\n        required: true\n      - name: api\n        type: string\n        description: api\n        required: true\n      - name: revision\n        type: string\n\
  \        description: revision\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapiproducts\n      description: Google Apigee List API products\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-apigee.listapiproducts\n      with:\n        organization: tools.organization\n      inputParameters:\n      - name: organization\n        type: string\n        description: organization\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapiproduct\n      description: Google Apigee Create an API product\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-apigee.createapiproduct\n      with:\n        organization: tools.organization\n      inputParameters:\n      - name: organization\n        type: string\n        description: organization\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdevelopers\n      description: Google Apigee List developers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-apigee.listdevelopers\n      with:\n        organization: tools.organization\n      inputParameters:\n      - name: organization\n        type: string\n        description: organization\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdeveloper\n      description: Google Apigee Create a developer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-apigee.createdeveloper\n      with:\n        organization: tools.organization\n      inputParameters:\n      - name: organization\n        type: string\n        description: organization\n        required: true\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-apigee/refs/heads/main/capabilities/google-apigee-capability.yaml
tags:
- Google
- Apigee
- API
tools:
- description: Google Apigee List organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizations
- description: Google Apigee Get an organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganization
- description: Google Apigee List API proxies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapiproxies
- description: Google Apigee Create an API proxy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapiproxy
- description: Google Apigee Get an API proxy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapiproxy
- description: Google Apigee Delete an API proxy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapiproxy
- description: Google Apigee List environments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listenvironments
- description: Google Apigee Create an environment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createenvironment
- description: Google Apigee Get an environment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvironment
- description: Google Apigee Delete an environment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteenvironment
- description: Google Apigee Get deployment status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeployment
- description: Google Apigee List API products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapiproducts
- description: Google Apigee Create an API product
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapiproduct
- description: Google Apigee List developers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdevelopers
- description: Google Apigee Create a developer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdeveloper
---
