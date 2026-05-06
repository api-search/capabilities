---
categories: []
consumed_apis: []
description: Provisions and manages developer App Engine applications, including deploying versions, managing traffic, and configuring services.
layout: capability
name: Google Cloud App Engine Admin API
operations:
- description: Google Cloud App Engine Get Application
  method: GET
  name: getapplication
  path: /apps/{appsId}
- description: Google Cloud App Engine Update Application
  method: PATCH
  name: updateapplication
  path: /apps/{appsId}
- description: Google Cloud App Engine List Services
  method: GET
  name: listservices
  path: /apps/{appsId}/services
- description: Google Cloud App Engine Get Service
  method: GET
  name: getservice
  path: /apps/{appsId}/services/{servicesId}
- description: Google Cloud App Engine Delete Service
  method: DELETE
  name: deleteservice
  path: /apps/{appsId}/services/{servicesId}
- description: Google Cloud App Engine List Versions
  method: GET
  name: listversions
  path: /apps/{appsId}/services/{servicesId}/versions
- description: Google Cloud App Engine Create Version
  method: POST
  name: createversion
  path: /apps/{appsId}/services/{servicesId}/versions
- description: Google Cloud App Engine List Instances
  method: GET
  name: listinstances
  path: /apps/{appsId}/services/{servicesId}/versions/{versionsId}/instances
personas: []
provider_name: Google Cloud App Engine
provider_slug: google-cloud-app-engine
search_terms:
- google cloud app engine create version
- compute
- google cloud app engine update application
- google cloud app engine list services
- serverless
- cloud
- engine
- getservice
- google
- deleteservice
- updateapplication
- web applications
- app
- google cloud app engine delete service
- api
- listversions
- google cloud app engine get application
- getapplication
- listinstances
- google cloud app engine list versions
- google cloud app engine get service
- google cloud app engine list instances
- listservices
- app engine
- paas
- google cloud
- createversion
slug: google-cloud-app-engine-capability
source_filename: google-cloud-app-engine-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud App Engine Admin API\n  description: Provisions and manages developer App Engine applications, including deploying versions, managing traffic, and\n    configuring services.\n  tags:\n  - Google\n  - Cloud\n  - App\n  - Engine\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-app-engine\n    baseUri: https://appengine.googleapis.com/v1\n    description: Google Cloud App Engine Admin API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_APP_ENGINE_TOKEN}}'\n    resources:\n    - name: apps-appsid\n      path: /apps/{appsId}\n      operations:\n      - name: getapplication\n        method: GET\n        description: Google Cloud App Engine Get Application\n        inputParameters:\n        - name: appsId\n          in: path\n          type: string\n          required: true\n          description: The application ID.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapplication\n        method: PATCH\n        description: Google Cloud App Engine Update Application\n        inputParameters:\n        - name: appsId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appsid-services\n      path: /apps/{appsId}/services\n      operations:\n      - name: listservices\n        method: GET\n        description: Google Cloud App Engine List Services\n        inputParameters:\n        - name: appsId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appsid-services-servicesid\n      path: /apps/{appsId}/services/{servicesId}\n\
  \      operations:\n      - name: getservice\n        method: GET\n        description: Google Cloud App Engine Get Service\n        inputParameters:\n        - name: appsId\n          in: path\n          type: string\n          required: true\n        - name: servicesId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteservice\n        method: DELETE\n        description: Google Cloud App Engine Delete Service\n        inputParameters:\n        - name: appsId\n          in: path\n          type: string\n          required: true\n        - name: servicesId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appsid-services-servicesid-versions\n      path: /apps/{appsId}/services/{servicesId}/versions\n\
  \      operations:\n      - name: listversions\n        method: GET\n        description: Google Cloud App Engine List Versions\n        inputParameters:\n        - name: appsId\n          in: path\n          type: string\n          required: true\n        - name: servicesId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createversion\n        method: POST\n        description: Google Cloud App Engine Create Version\n        inputParameters:\n        - name: appsId\n          in: path\n          type: string\n          required: true\n        - name: servicesId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appsid-services-servicesid-versions-version\n      path:\
  \ /apps/{appsId}/services/{servicesId}/versions/{versionsId}/instances\n      operations:\n      - name: listinstances\n        method: GET\n        description: Google Cloud App Engine List Instances\n        inputParameters:\n        - name: appsId\n          in: path\n          type: string\n          required: true\n        - name: servicesId\n          in: path\n          type: string\n          required: true\n        - name: versionsId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-app-engine-rest\n    description: REST adapter for Google Cloud App Engine Admin API.\n    resources:\n    - path: /apps/{appsId}\n      name: getapplication\n      operations:\n      - method: GET\n        name: getapplication\n        description: Google Cloud App Engine Get Application\n\
  \        call: google-cloud-app-engine.getapplication\n        with:\n          appsId: rest.appsId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appsId}\n      name: updateapplication\n      operations:\n      - method: PATCH\n        name: updateapplication\n        description: Google Cloud App Engine Update Application\n        call: google-cloud-app-engine.updateapplication\n        with:\n          appsId: rest.appsId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appsId}/services\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: Google Cloud App Engine List Services\n        call: google-cloud-app-engine.listservices\n        with:\n          appsId: rest.appsId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appsId}/services/{servicesId}\n      name: getservice\n      operations:\n\
  \      - method: GET\n        name: getservice\n        description: Google Cloud App Engine Get Service\n        call: google-cloud-app-engine.getservice\n        with:\n          appsId: rest.appsId\n          servicesId: rest.servicesId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appsId}/services/{servicesId}\n      name: deleteservice\n      operations:\n      - method: DELETE\n        name: deleteservice\n        description: Google Cloud App Engine Delete Service\n        call: google-cloud-app-engine.deleteservice\n        with:\n          appsId: rest.appsId\n          servicesId: rest.servicesId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appsId}/services/{servicesId}/versions\n      name: listversions\n      operations:\n      - method: GET\n        name: listversions\n        description: Google Cloud App Engine List Versions\n        call: google-cloud-app-engine.listversions\n\
  \        with:\n          appsId: rest.appsId\n          servicesId: rest.servicesId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appsId}/services/{servicesId}/versions\n      name: createversion\n      operations:\n      - method: POST\n        name: createversion\n        description: Google Cloud App Engine Create Version\n        call: google-cloud-app-engine.createversion\n        with:\n          appsId: rest.appsId\n          servicesId: rest.servicesId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appsId}/services/{servicesId}/versions/{versionsId}/instances\n      name: listinstances\n      operations:\n      - method: GET\n        name: listinstances\n        description: Google Cloud App Engine List Instances\n        call: google-cloud-app-engine.listinstances\n        with:\n          appsId: rest.appsId\n          servicesId: rest.servicesId\n          versionsId: rest.versionsId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-app-engine-mcp\n    transport: http\n    description: MCP adapter for Google Cloud App Engine Admin API for AI agent use.\n    tools:\n    - name: getapplication\n      description: Google Cloud App Engine Get Application\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-app-engine.getapplication\n      with:\n        appsId: tools.appsId\n      inputParameters:\n      - name: appsId\n        type: string\n        description: The application ID.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateapplication\n      description: Google Cloud App Engine Update Application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-app-engine.updateapplication\n      with:\n\
  \        appsId: tools.appsId\n      inputParameters:\n      - name: appsId\n        type: string\n        description: appsId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listservices\n      description: Google Cloud App Engine List Services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-app-engine.listservices\n      with:\n        appsId: tools.appsId\n      inputParameters:\n      - name: appsId\n        type: string\n        description: appsId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getservice\n      description: Google Cloud App Engine Get Service\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-app-engine.getservice\n      with:\n        appsId: tools.appsId\n        servicesId: tools.servicesId\n      inputParameters:\n\
  \      - name: appsId\n        type: string\n        description: appsId\n        required: true\n      - name: servicesId\n        type: string\n        description: servicesId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteservice\n      description: Google Cloud App Engine Delete Service\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-app-engine.deleteservice\n      with:\n        appsId: tools.appsId\n        servicesId: tools.servicesId\n      inputParameters:\n      - name: appsId\n        type: string\n        description: appsId\n        required: true\n      - name: servicesId\n        type: string\n        description: servicesId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listversions\n      description: Google Cloud App Engine List Versions\n      hints:\n        readOnly: true\n  \
  \      destructive: false\n        idempotent: true\n      call: google-cloud-app-engine.listversions\n      with:\n        appsId: tools.appsId\n        servicesId: tools.servicesId\n      inputParameters:\n      - name: appsId\n        type: string\n        description: appsId\n        required: true\n      - name: servicesId\n        type: string\n        description: servicesId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createversion\n      description: Google Cloud App Engine Create Version\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-app-engine.createversion\n      with:\n        appsId: tools.appsId\n        servicesId: tools.servicesId\n      inputParameters:\n      - name: appsId\n        type: string\n        description: appsId\n        required: true\n      - name: servicesId\n        type: string\n        description: servicesId\n       \
  \ required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinstances\n      description: Google Cloud App Engine List Instances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-app-engine.listinstances\n      with:\n        appsId: tools.appsId\n        servicesId: tools.servicesId\n        versionsId: tools.versionsId\n      inputParameters:\n      - name: appsId\n        type: string\n        description: appsId\n        required: true\n      - name: servicesId\n        type: string\n        description: servicesId\n        required: true\n      - name: versionsId\n        type: string\n        description: versionsId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_APP_ENGINE_TOKEN: GOOGLE_CLOUD_APP_ENGINE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-app-engine/refs/heads/main/capabilities/google-cloud-app-engine-capability.yaml
tags:
- Google
- Cloud
- App
- Engine
- API
tools:
- description: Google Cloud App Engine Get Application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplication
- description: Google Cloud App Engine Update Application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateapplication
- description: Google Cloud App Engine List Services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: Google Cloud App Engine Get Service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservice
- description: Google Cloud App Engine Delete Service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteservice
- description: Google Cloud App Engine List Versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listversions
- description: Google Cloud App Engine Create Version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createversion
- description: Google Cloud App Engine List Instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstances
---
