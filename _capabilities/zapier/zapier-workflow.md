---
categories: []
consumed_apis:
- partner-api
description: Unified workflow capability composing Zapier APIs.
layout: capability
name: Zapier Workflow
operations:
- description: Zapier Get Apps [v1]
  method: GET
  name: v1-apps-list
  path: /v1/partner-api
- description: Zapier Get Categories
  method: GET
  name: v1-categories-list
  path: /v1/partner-api
- description: Zapier User Profile
  method: GET
  name: v1-profiles-me-list
  path: /v1/partner-api
- description: Zapier Get Zap Templates
  method: GET
  name: v1-zap-templates-list
  path: /v1/partner-api
- description: Zapier Get Zaps [v1]
  method: GET
  name: v1-zaps-list
  path: /v1/partner-api
- description: Zapier Create an Action Run
  method: POST
  name: create-action-run
  path: /v1/partner-api
- description: Zapier Retrieve Action Run
  method: GET
  name: retrieve-action-run
  path: /v1/partner-api
- description: Zapier Get Actions
  method: GET
  name: get-actions
  path: /v1/partner-api
- description: Zapier Get Input Fields
  method: POST
  name: get-fields-inputs
  path: /v1/partner-api
- description: Zapier Get Choices
  method: POST
  name: get-choices
  path: /v1/partner-api
- description: Zapier Get Output Fields
  method: POST
  name: get-fields-outputs
  path: /v1/partner-api
- description: Zapier Step Test
  method: POST
  name: test-action
  path: /v1/partner-api
- description: Zapier Get Apps [v2]
  method: GET
  name: get-v2-apps
  path: /v1/partner-api
- description: Zapier Get Authentications
  method: GET
  name: get-authentications
  path: /v1/partner-api
- description: Zapier Create Authentication
  method: POST
  name: create-authentication
  path: /v1/partner-api
- description: Zapier Create Account
  method: GET
  name: v2-authorize-list
  path: /v1/partner-api
- description: Zapier Guess a Zap [Beta]
  method: POST
  name: create-zap-guess
  path: /v1/partner-api
- description: Zapier Get Whitelabel Apps [v2]
  method: GET
  name: v2-whitelabel-apps-list
  path: /v1/partner-api
- description: Zapier Get Zap Runs
  method: GET
  name: get-zap-runs
  path: /v1/partner-api
- description: Zapier Get Zaps [v2]
  method: GET
  name: get-v2-zaps
  path: /v1/partner-api
personas: []
provider_name: Zapier
provider_slug: zapier
search_terms:
- create zap guess
- partner api v1 profiles me list
- zapier retrieve action run
- v2 whitelabel apps list
- partner api get fields outputs
- test action
- zapier get zap templates
- get authentications
- partner api get actions
- ipaas
- get choices
- zapier get apps [v2]
- partner api create zap guess
- get v2 apps
- get zap runs
- create action run
- zapier user profile
- partner api create action run
- v1 categories list
- zapier get zaps [v1]
- partner api v1 categories list
- partner api get authentications
- zapier create an action run
- partner api v1 zaps list
- create authentication
- zapier guess a zap [beta]
- zapier get input fields
- partner api get v2 zaps
- zapier step test
- zapier get output fields
- v1 zaps list
- zapier create authentication
- zapier get categories
- v2 authorize list
- zapier get actions
- get fields inputs
- get fields outputs
- partner api v2 authorize list
- partner api v2 whitelabel apps list
- integrations
- v1 zap templates list
- partner api create authentication
- partner api get choices
- operations for partner-api
- zapier create account
- v1 apps list
- partner api retrieve action run
- partner api test action
- v1 profiles me list
- zapier get choices
- zapier
- partner api v1 zap templates list
- retrieve action run
- zapier get zap runs
- partner api v1 apps list
- zapier get apps [v1]
- zapier get whitelabel apps [v2]
- zapier get zaps [v2]
- partner api get fields inputs
- get v2 zaps
- partner api get zap runs
- partner api get v2 apps
- get actions
- zapier get authentications
slug: zapier-workflow
source_filename: zapier-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Zapier Workflow\n  description: Unified workflow capability composing Zapier APIs.\n  tags:\n    - Zapier\n  created: '2026-05-03'\n  modified: '2026-05-03'\ncapability:\n  consumes:\n    - import: partner-api\n      location: ./shared/partner-api.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: zapier-api\n      description: Unified REST API for Zapier\n      resources:\n        - path: /v1/partner-api\n          name: partner-api\n          description: Operations for partner-api\n          operations:\n            - method: GET\n              name: v1-apps-list\n              description: Zapier Get Apps [v1]\n              call: partner-api.v1-apps-list\n            - method: GET\n              name: v1-categories-list\n              description: Zapier Get Categories\n              call: partner-api.v1-categories-list\n            - method: GET\n              name: v1-profiles-me-list\n              description:\
  \ Zapier User Profile\n              call: partner-api.v1-profiles-me-list\n            - method: GET\n              name: v1-zap-templates-list\n              description: Zapier Get Zap Templates\n              call: partner-api.v1-zap-templates-list\n            - method: GET\n              name: v1-zaps-list\n              description: Zapier Get Zaps [v1]\n              call: partner-api.v1-zaps-list\n            - method: POST\n              name: create-action-run\n              description: Zapier Create an Action Run\n              call: partner-api.create-action-run\n            - method: GET\n              name: retrieve-action-run\n              description: Zapier Retrieve Action Run\n              call: partner-api.retrieve-action-run\n            - method: GET\n              name: get-actions\n              description: Zapier Get Actions\n              call: partner-api.get-actions\n            - method: POST\n              name: get-fields-inputs\n              description:\
  \ Zapier Get Input Fields\n              call: partner-api.get-fields-inputs\n            - method: POST\n              name: get-choices\n              description: Zapier Get Choices\n              call: partner-api.get-choices\n            - method: POST\n              name: get-fields-outputs\n              description: Zapier Get Output Fields\n              call: partner-api.get-fields-outputs\n            - method: POST\n              name: test-action\n              description: Zapier Step Test\n              call: partner-api.test-action\n            - method: GET\n              name: get-v2-apps\n              description: Zapier Get Apps [v2]\n              call: partner-api.get-v2-apps\n            - method: GET\n              name: get-authentications\n              description: Zapier Get Authentications\n              call: partner-api.get-authentications\n            - method: POST\n              name: create-authentication\n              description: Zapier Create Authentication\n\
  \              call: partner-api.create-authentication\n            - method: GET\n              name: v2-authorize-list\n              description: Zapier Create Account\n              call: partner-api.v2-authorize-list\n            - method: POST\n              name: create-zap-guess\n              description: Zapier Guess a Zap [Beta]\n              call: partner-api.create-zap-guess\n            - method: GET\n              name: v2-whitelabel-apps-list\n              description: Zapier Get Whitelabel Apps [v2]\n              call: partner-api.v2-whitelabel-apps-list\n            - method: GET\n              name: get-zap-runs\n              description: Zapier Get Zap Runs\n              call: partner-api.get-zap-runs\n            - method: GET\n              name: get-v2-zaps\n              description: Zapier Get Zaps [v2]\n              call: partner-api.get-v2-zaps\n    - type: mcp\n      port: 9090\n      namespace: zapier-mcp\n      transport: http\n      description: MCP\
  \ server for Zapier\n      tools:\n        - name: partner-api-v1-apps-list\n          description: Zapier Get Apps [v1]\n          hints:\n            readOnly: true\n            openWorld: true\n          call: partner-api.v1-apps-list\n        - name: partner-api-v1-categories-list\n          description: Zapier Get Categories\n          hints:\n            readOnly: true\n            openWorld: true\n          call: partner-api.v1-categories-list\n        - name: partner-api-v1-profiles-me-list\n          description: Zapier User Profile\n          hints:\n            readOnly: true\n            openWorld: true\n          call: partner-api.v1-profiles-me-list\n        - name: partner-api-v1-zap-templates-list\n          description: Zapier Get Zap Templates\n          hints:\n            readOnly: true\n            openWorld: true\n          call: partner-api.v1-zap-templates-list\n        - name: partner-api-v1-zaps-list\n          description: Zapier Get Zaps [v1]\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: partner-api.v1-zaps-list\n        - name: partner-api-create-action-run\n          description: Zapier Create an Action Run\n          hints:\n            readOnly: false\n            openWorld: true\n          call: partner-api.create-action-run\n        - name: partner-api-retrieve-action-run\n          description: Zapier Retrieve Action Run\n          hints:\n            readOnly: true\n            openWorld: true\n          call: partner-api.retrieve-action-run\n        - name: partner-api-get-actions\n          description: Zapier Get Actions\n          hints:\n            readOnly: true\n            openWorld: true\n          call: partner-api.get-actions\n        - name: partner-api-get-fields-inputs\n          description: Zapier Get Input Fields\n          hints:\n            readOnly: false\n            openWorld: true\n          call: partner-api.get-fields-inputs\n        - name: partner-api-get-choices\n\
  \          description: Zapier Get Choices\n          hints:\n            readOnly: false\n            openWorld: true\n          call: partner-api.get-choices\n        - name: partner-api-get-fields-outputs\n          description: Zapier Get Output Fields\n          hints:\n            readOnly: false\n            openWorld: true\n          call: partner-api.get-fields-outputs\n        - name: partner-api-test-action\n          description: Zapier Step Test\n          hints:\n            readOnly: false\n            openWorld: true\n          call: partner-api.test-action\n        - name: partner-api-get-v2-apps\n          description: Zapier Get Apps [v2]\n          hints:\n            readOnly: true\n            openWorld: true\n          call: partner-api.get-v2-apps\n        - name: partner-api-get-authentications\n          description: Zapier Get Authentications\n          hints:\n            readOnly: true\n            openWorld: true\n          call: partner-api.get-authentications\n\
  \        - name: partner-api-create-authentication\n          description: Zapier Create Authentication\n          hints:\n            readOnly: false\n            openWorld: true\n          call: partner-api.create-authentication\n        - name: partner-api-v2-authorize-list\n          description: Zapier Create Account\n          hints:\n            readOnly: true\n            openWorld: true\n          call: partner-api.v2-authorize-list\n        - name: partner-api-create-zap-guess\n          description: Zapier Guess a Zap [Beta]\n          hints:\n            readOnly: false\n            openWorld: true\n          call: partner-api.create-zap-guess\n        - name: partner-api-v2-whitelabel-apps-list\n          description: Zapier Get Whitelabel Apps [v2]\n          hints:\n            readOnly: true\n            openWorld: true\n          call: partner-api.v2-whitelabel-apps-list\n        - name: partner-api-get-zap-runs\n          description: Zapier Get Zap Runs\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: partner-api.get-zap-runs\n        - name: partner-api-get-v2-zaps\n          description: Zapier Get Zaps [v2]\n          hints:\n            readOnly: true\n            openWorld: true\n          call: partner-api.get-v2-zaps\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zapier/refs/heads/main/capabilities/zapier-workflow.yaml
tags:
- Zapier
tools:
- description: Zapier Get Apps [v1]
  hints:
    openWorld: true
    readOnly: true
  name: partner-api-v1-apps-list
- description: Zapier Get Categories
  hints:
    openWorld: true
    readOnly: true
  name: partner-api-v1-categories-list
- description: Zapier User Profile
  hints:
    openWorld: true
    readOnly: true
  name: partner-api-v1-profiles-me-list
- description: Zapier Get Zap Templates
  hints:
    openWorld: true
    readOnly: true
  name: partner-api-v1-zap-templates-list
- description: Zapier Get Zaps [v1]
  hints:
    openWorld: true
    readOnly: true
  name: partner-api-v1-zaps-list
- description: Zapier Create an Action Run
  hints:
    openWorld: true
    readOnly: false
  name: partner-api-create-action-run
- description: Zapier Retrieve Action Run
  hints:
    openWorld: true
    readOnly: true
  name: partner-api-retrieve-action-run
- description: Zapier Get Actions
  hints:
    openWorld: true
    readOnly: true
  name: partner-api-get-actions
- description: Zapier Get Input Fields
  hints:
    openWorld: true
    readOnly: false
  name: partner-api-get-fields-inputs
- description: Zapier Get Choices
  hints:
    openWorld: true
    readOnly: false
  name: partner-api-get-choices
- description: Zapier Get Output Fields
  hints:
    openWorld: true
    readOnly: false
  name: partner-api-get-fields-outputs
- description: Zapier Step Test
  hints:
    openWorld: true
    readOnly: false
  name: partner-api-test-action
- description: Zapier Get Apps [v2]
  hints:
    openWorld: true
    readOnly: true
  name: partner-api-get-v2-apps
- description: Zapier Get Authentications
  hints:
    openWorld: true
    readOnly: true
  name: partner-api-get-authentications
- description: Zapier Create Authentication
  hints:
    openWorld: true
    readOnly: false
  name: partner-api-create-authentication
- description: Zapier Create Account
  hints:
    openWorld: true
    readOnly: true
  name: partner-api-v2-authorize-list
- description: Zapier Guess a Zap [Beta]
  hints:
    openWorld: true
    readOnly: false
  name: partner-api-create-zap-guess
- description: Zapier Get Whitelabel Apps [v2]
  hints:
    openWorld: true
    readOnly: true
  name: partner-api-v2-whitelabel-apps-list
- description: Zapier Get Zap Runs
  hints:
    openWorld: true
    readOnly: true
  name: partner-api-get-zap-runs
- description: Zapier Get Zaps [v2]
  hints:
    openWorld: true
    readOnly: true
  name: partner-api-get-v2-zaps
---
