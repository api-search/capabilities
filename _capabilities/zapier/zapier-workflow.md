---
categories: []
consumed_apis: []
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
- partner api v2 whitelabel apps list
- test action
- v1 zaps list
- get fields outputs
- get choices
- operations for partner-api
- get v2 apps
- partner api v1 zap templates list
- create action run
- partner api get v2 apps
- v2 whitelabel apps list
- v2 authorize list
- v1 apps list
- v1 zap templates list
- zapier get zaps [v1]
- partner api get fields outputs
- v1 profiles me list
- zapier create authentication
- zapier get zap runs
- partner api create action run
- zapier get actions
- partner api v1 profiles me list
- zapier create an action run
- zapier get choices
- partner api retrieve action run
- partner api get authentications
- partner api v2 authorize list
- zapier get output fields
- partner api v1 categories list
- zapier get zap templates
- partner api v1 apps list
- integrations
- zapier get apps [v1]
- zapier get authentications
- zapier
- zapier get zaps [v2]
- partner api test action
- v1 categories list
- ipaas
- get authentications
- zapier guess a zap [beta]
- create authentication
- partner api create zap guess
- zapier user profile
- zapier get apps [v2]
- partner api create authentication
- get fields inputs
- zapier get input fields
- zapier get categories
- retrieve action run
- zapier create account
- get v2 zaps
- get zap runs
- partner api v1 zaps list
- partner api get zap runs
- partner api get fields inputs
- zapier get whitelabel apps [v2]
- partner api get v2 zaps
- partner api get actions
- zapier step test
- get actions
- partner api get choices
- zapier retrieve action run
- create zap guess
slug: zapier-workflow
source_filename: zapier-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Zapier Workflow\n  description: Unified workflow capability composing Zapier APIs.\n  tags:\n  - Zapier\n  created: '2026-05-03'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: partner-api\n    baseUri: https://api.zapier.com\n    description: '## Introduction'\n    resources:\n    - name: partner-api\n      path: /\n      description: '## Introduction'\n      operations:\n      - name: v1-apps-list\n        method: GET\n        path: /v1/apps\n        description: Zapier Get Apps [v1]\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Categories that apps must have in order to be returned in the response\n        - name: is_in_zap_template_with\n          in: query\n          type: string\n          required: false\n          description: If set, only return apps that are in a Zap Template with your app\n\
  \        - name: page\n          in: query\n          type: number\n          required: false\n          description: Which page to return\n        - name: per_page\n          in: query\n          type: number\n          required: false\n          description: Number of results to return per page\n        - name: title_search\n          in: query\n          type: string\n          required: false\n          description: Case-insensitive parameter to limit the results to apps whose titles match\n        - name: title_starts_with\n          in: query\n          type: string\n          required: false\n          description: Case-insensitive parameter to only return apps whose titles start with the parameter value in the response\n        outputRawFormat: json\n      - name: v1-categories-list\n        method: GET\n        path: /v1/categories\n        description: Zapier Get Categories\n        inputParameters:\n        - name: limit\n          in: query\n          type: number\n       \
  \   required: false\n          description: Limit the number of Zap categories returned.\n        - name: offset\n          in: query\n          type: number\n          required: false\n          description: The number of Zap categories to skip over. The default value is 0, which is the offset of the first\n            item.\n        outputRawFormat: json\n      - name: v1-profiles-me-list\n        method: GET\n        path: /v1/profiles/me\n        description: Zapier User Profile\n        inputParameters: []\n        outputRawFormat: json\n      - name: v1-zap-templates-list\n        method: GET\n        path: /v1/zap-templates\n        description: Zapier Get Zap Templates\n        inputParameters:\n        - name: apps\n          in: query\n          type: string\n          required: false\n          description: 'A comma separated list of Zapier Apps to match Zap templates against. Note:\n\n            - Your app will always be one of the apps in the template\n\n            - The\
  \ list will return Zap Templates with all the provided apps, n'\n        - name: limit\n          in: query\n          type: number\n          required: false\n          description: '(Max: 100) Limit the number of Zap templates returned.'\n        - name: offset\n          in: query\n          type: number\n          required: false\n          description: The number of Zap templates to skip before beginning to return the Zap templates. The default value\n            is 0, which is the offset of the first item.\n        outputRawFormat: json\n      - name: v1-zaps-list\n        method: GET\n        path: /v1/zaps\n        description: Zapier Get Zaps [v1]\n        inputParameters:\n        - name: get_params\n          in: query\n          type: string\n          required: false\n          description: If set, guarantees that the 'params' of any node belonging to your app will be present in the response\n        - name: limit\n          in: query\n          type: number\n          required:\
  \ false\n          description: '(Max: 100) Limit the number of Zap templates returned.'\n        - name: offset\n          in: query\n          type: number\n          required: false\n          description: The number of Zap templates to skip before beginning to return the Zap templates. The default value\n            is 0, which is the offset of the first item.\n        - name: params__{{KEY}}\n          in: query\n          type: string\n          required: false\n          description: Filter for Zaps that contain the given parameter's {{KEY}} and the value of the query parameter. Keys\n            are defined by your app on the [developer platform](https://zapier.com/platform/login).\n        outputRawFormat: json\n      - name: create-action-run\n        method: POST\n        path: /v2/action-runs\n        description: Zapier Create an Action Run\n        inputParameters: []\n        outputRawFormat: json\n      - name: retrieve-action-run\n        method: GET\n        path: /v2/action-runs/{id}\n\
  \        description: Zapier Retrieve Action Run\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: An Action Run ID.\n        outputRawFormat: json\n      - name: get-actions\n        method: GET\n        path: /v2/actions\n        description: Zapier Get Actions\n        inputParameters:\n        - name: action_type\n          in: query\n          type: string\n          required: false\n          description: The type of Action to filter for. Defaults to returning all actions regardless of type.\n        - name: app\n          in: query\n          type: string\n          required: true\n          description: A canonical App ID, as provided by the `/apps` endpoint.\n        outputRawFormat: json\n      - name: get-fields-inputs\n        method: POST\n        path: /v2/actions/{action_id}/inputs\n        description: Zapier Get Input Fields\n        inputParameters:\n        - name: action_id\n \
  \         in: path\n          type: string\n          required: true\n          description: An Action ID, as provided by the `/actions` endpoint.\n        outputRawFormat: json\n      - name: get-choices\n        method: POST\n        path: /v2/actions/{action_id}/inputs/{input_id}/choices\n        description: Zapier Get Choices\n        inputParameters:\n        - name: action_id\n          in: path\n          type: string\n          required: true\n          description: An Action ID, as provided by the `/actions` endpoint.\n        - name: input_id\n          in: path\n          type: string\n          required: true\n          description: An Input Field ID, as provided by the `/inputs` endpoint.\n        - name: page\n          in: query\n          type: string\n          required: false\n          description: The page of choices to return, defaults to the first\n        outputRawFormat: json\n      - name: get-fields-outputs\n        method: POST\n        path: /v2/actions/{action_id}/outputs\n\
  \        description: Zapier Get Output Fields\n        inputParameters:\n        - name: action_id\n          in: path\n          type: string\n          required: true\n          description: An Action ID, as provided by the `/actions` endpoint.\n        outputRawFormat: json\n      - name: test-action\n        method: POST\n        path: /v2/actions/{action_id}/test\n        description: Zapier Step Test\n        inputParameters:\n        - name: action_id\n          in: path\n          type: string\n          required: true\n          description: An Action ID, as provided by the `/actions` endpoint.\n        outputRawFormat: json\n      - name: get-v2-apps\n        method: GET\n        path: /v2/apps\n        description: Zapier Get Apps [v2]\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: \"Categories that apps must have in order to be returned in the response. \\nThe full list of\
  \ valid categories\\\n            \\ can be retrieved using the `category` endpoint, detailed [here](https://platform.zapier.com/e\"\n        - name: ids\n          in: query\n          type: string\n          required: false\n          description: Parameter to restrict the results to apps whose ID matches those in the provided comma-separated value.\n            Cannot be combined with `category`.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Used for paginating results. Specifies the maximum number of items to return per page. If this value\n            is not set, it defaults to 10.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Used for paginating results. Specifies the offset to use.\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Parameter to limit the results to\
  \ apps whose titles match the provided query.\n        outputRawFormat: json\n      - name: get-authentications\n        method: GET\n        path: /v2/authentications\n        description: Zapier Get Authentications\n        inputParameters:\n        - name: app\n          in: query\n          type: string\n          required: true\n          description: A canonical App ID, as provided by the `/apps` endpoint.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Used for paginating results. Specifies the maximum number of items to return per page. If this value\n            is not set, it defaults to 10.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Used for paginating results. Specifies the offset to use.\n        outputRawFormat: json\n      - name: create-authentication\n        method: POST\n        path: /v2/authentications\n        description:\
  \ Zapier Create Authentication\n        inputParameters: []\n        outputRawFormat: json\n      - name: v2-authorize-list\n        method: GET\n        path: /v2/authorize\n        description: Zapier Create Account\n        inputParameters:\n        - name: client_id\n          in: query\n          type: string\n          required: true\n          description: Your application Client ID.\n        - name: redirect_uri\n          in: query\n          type: string\n          required: true\n          description: The page the user will be redirect to after OAuth flow.\n        - name: referer\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: response_type\n          in: query\n          type: string\n          required: true\n          description: Only OAuth response type `code` is supported\n        - name: scope\n          in: query\n          type: string\n          required: true\n          description: Space (`%20`)\
  \ separated values\n        - name: sign_up_email\n          in: query\n          type: string\n          required: false\n          description: Email of the user signing up.\n        - name: sign_up_first_name\n          in: query\n          type: string\n          required: false\n          description: First name of the user signing up.\n        - name: sign_up_last_name\n          in: query\n          type: string\n          required: false\n          description: Last name of the user signing up.\n        - name: utm_campaign\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: utm_content\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: utm_medium\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: utm_source\n          in: query\n          type: string\n          required: false\n      \
  \    description: ''\n        outputRawFormat: json\n      - name: create-zap-guess\n        method: POST\n        path: /v2/guess\n        description: Zapier Guess a Zap [Beta]\n        inputParameters:\n        - name: client_id\n          in: query\n          type: string\n          required: true\n          description: See our authentication documentation for how to find your client ID\n        outputRawFormat: json\n      - name: v2-whitelabel-apps-list\n        method: GET\n        path: /v2/whitelabel/apps\n        description: Zapier Get Whitelabel Apps [v2]\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter apps by category slug.\n        - name: limit\n          in: query\n          type: number\n          required: false\n          description: Limit the number of apps returned.\n        - name: offset\n          in: query\n          type: number\n          required: false\n\
  \          description: The number of apps to skip before beginning to return results.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Case-insensitive search to filter apps by title.\n        outputRawFormat: json\n      - name: get-zap-runs\n        method: GET\n        path: /v2/zap-runs\n        description: Zapier Get Zap Runs\n        inputParameters:\n        - name: from_date\n          in: query\n          type: string\n          required: false\n          description: Filter Zap runs that occurred on or after this date. If not provided, the results default to Zap runs\n            from the last 30 days.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Used for paginating results. Specifies the maximum number of items to return per page. If this value\n            is not set, it defaults to 10.\n        - name: offset\n          in: query\n\
  \          type: integer\n          required: false\n          description: Used for paginating results. Specifies the offset to use.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Performs a text search against the zap_title, data_in, and data_out fields, returning only zap runs\n            that match the specified keywords.\n        - name: statuses\n          in: query\n          type: array\n          required: false\n          description: Accepts one or more status values separated by comma, enabling the filtering of zap runs based on the\n            specified status or statuses provided.\n        - name: to_date\n          in: query\n          type: string\n          required: false\n          description: Filter Zap runs that occurred before this date.\n        - name: zap_id\n          in: query\n          type: integer\n          required: false\n          description: Find Zap runs for the specified Zap\
  \ ID.\n        outputRawFormat: json\n      - name: get-v2-zaps\n        method: GET\n        path: /v2/zaps\n        description: Zapier Get Zaps [v2]\n        inputParameters:\n        - name: expand\n          in: query\n          type: string\n          required: false\n          description: A comma separated list of Zap fields that should be expanded from ids to full objects in the response.\n            Fields that may not be expanded will remain as ids.\n        - name: include_shared\n          in: query\n          type: boolean\n          required: false\n          description: If true, all Zaps that are shared with the user, rather than only those owned by them, are returned.\n            If the zap:account:all scope is not present this has no effect.\n        - name: inputs\n          in: query\n          type: string\n          required: false\n          description: You may pass inputs[KEY]=VALUE1,VALUE2 to filter for Zaps that contain those settings. Keys are defined\n \
  \           by your app on the developer platform.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Used for paginating results. Specifies the maximum number of items to return per page. If this value\n            is not set, it defaults to 10.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Used for paginating results. Specifies the offset to use.\n        outputRawFormat: json\n      - name: post-zaps\n        method: POST\n        path: /v2/zaps\n        description: Zapier Create a Zap\n        inputParameters:\n        - name: expand\n          in: query\n          type: string\n          required: false\n          description: A comma separated list of Zap fields that should be expanded from ids to full objects in the response.\n            Fields that may not be expanded will remain as ids.\n        outputRawFormat: json\n    authentication:\n\
  \      type: apikey\n      key: client_id\n      value: '{{API_KEY}}'\n      placement: query\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: zapier-api\n    description: Unified REST API for Zapier\n    resources:\n    - path: /v1/partner-api\n      name: partner-api\n      description: Operations for partner-api\n      operations:\n      - method: GET\n        name: v1-apps-list\n        description: Zapier Get Apps [v1]\n        call: partner-api.v1-apps-list\n      - method: GET\n        name: v1-categories-list\n        description: Zapier Get Categories\n        call: partner-api.v1-categories-list\n      - method: GET\n        name: v1-profiles-me-list\n        description: Zapier User Profile\n        call: partner-api.v1-profiles-me-list\n      - method: GET\n        name: v1-zap-templates-list\n        description: Zapier Get Zap Templates\n        call: partner-api.v1-zap-templates-list\n      - method: GET\n        name: v1-zaps-list\n        description: Zapier\
  \ Get Zaps [v1]\n        call: partner-api.v1-zaps-list\n      - method: POST\n        name: create-action-run\n        description: Zapier Create an Action Run\n        call: partner-api.create-action-run\n      - method: GET\n        name: retrieve-action-run\n        description: Zapier Retrieve Action Run\n        call: partner-api.retrieve-action-run\n      - method: GET\n        name: get-actions\n        description: Zapier Get Actions\n        call: partner-api.get-actions\n      - method: POST\n        name: get-fields-inputs\n        description: Zapier Get Input Fields\n        call: partner-api.get-fields-inputs\n      - method: POST\n        name: get-choices\n        description: Zapier Get Choices\n        call: partner-api.get-choices\n      - method: POST\n        name: get-fields-outputs\n        description: Zapier Get Output Fields\n        call: partner-api.get-fields-outputs\n      - method: POST\n        name: test-action\n        description: Zapier Step Test\n\
  \        call: partner-api.test-action\n      - method: GET\n        name: get-v2-apps\n        description: Zapier Get Apps [v2]\n        call: partner-api.get-v2-apps\n      - method: GET\n        name: get-authentications\n        description: Zapier Get Authentications\n        call: partner-api.get-authentications\n      - method: POST\n        name: create-authentication\n        description: Zapier Create Authentication\n        call: partner-api.create-authentication\n      - method: GET\n        name: v2-authorize-list\n        description: Zapier Create Account\n        call: partner-api.v2-authorize-list\n      - method: POST\n        name: create-zap-guess\n        description: Zapier Guess a Zap [Beta]\n        call: partner-api.create-zap-guess\n      - method: GET\n        name: v2-whitelabel-apps-list\n        description: Zapier Get Whitelabel Apps [v2]\n        call: partner-api.v2-whitelabel-apps-list\n      - method: GET\n        name: get-zap-runs\n        description:\
  \ Zapier Get Zap Runs\n        call: partner-api.get-zap-runs\n      - method: GET\n        name: get-v2-zaps\n        description: Zapier Get Zaps [v2]\n        call: partner-api.get-v2-zaps\n  - type: mcp\n    port: 9090\n    namespace: zapier-mcp\n    transport: http\n    description: MCP server for Zapier\n    tools:\n    - name: partner-api-v1-apps-list\n      description: Zapier Get Apps [v1]\n      hints:\n        readOnly: true\n        openWorld: true\n      call: partner-api.v1-apps-list\n    - name: partner-api-v1-categories-list\n      description: Zapier Get Categories\n      hints:\n        readOnly: true\n        openWorld: true\n      call: partner-api.v1-categories-list\n    - name: partner-api-v1-profiles-me-list\n      description: Zapier User Profile\n      hints:\n        readOnly: true\n        openWorld: true\n      call: partner-api.v1-profiles-me-list\n    - name: partner-api-v1-zap-templates-list\n      description: Zapier Get Zap Templates\n      hints:\n   \
  \     readOnly: true\n        openWorld: true\n      call: partner-api.v1-zap-templates-list\n    - name: partner-api-v1-zaps-list\n      description: Zapier Get Zaps [v1]\n      hints:\n        readOnly: true\n        openWorld: true\n      call: partner-api.v1-zaps-list\n    - name: partner-api-create-action-run\n      description: Zapier Create an Action Run\n      hints:\n        readOnly: false\n        openWorld: true\n      call: partner-api.create-action-run\n    - name: partner-api-retrieve-action-run\n      description: Zapier Retrieve Action Run\n      hints:\n        readOnly: true\n        openWorld: true\n      call: partner-api.retrieve-action-run\n    - name: partner-api-get-actions\n      description: Zapier Get Actions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: partner-api.get-actions\n    - name: partner-api-get-fields-inputs\n      description: Zapier Get Input Fields\n      hints:\n        readOnly: false\n        openWorld: true\n\
  \      call: partner-api.get-fields-inputs\n    - name: partner-api-get-choices\n      description: Zapier Get Choices\n      hints:\n        readOnly: false\n        openWorld: true\n      call: partner-api.get-choices\n    - name: partner-api-get-fields-outputs\n      description: Zapier Get Output Fields\n      hints:\n        readOnly: false\n        openWorld: true\n      call: partner-api.get-fields-outputs\n    - name: partner-api-test-action\n      description: Zapier Step Test\n      hints:\n        readOnly: false\n        openWorld: true\n      call: partner-api.test-action\n    - name: partner-api-get-v2-apps\n      description: Zapier Get Apps [v2]\n      hints:\n        readOnly: true\n        openWorld: true\n      call: partner-api.get-v2-apps\n    - name: partner-api-get-authentications\n      description: Zapier Get Authentications\n      hints:\n        readOnly: true\n        openWorld: true\n      call: partner-api.get-authentications\n    - name: partner-api-create-authentication\n\
  \      description: Zapier Create Authentication\n      hints:\n        readOnly: false\n        openWorld: true\n      call: partner-api.create-authentication\n    - name: partner-api-v2-authorize-list\n      description: Zapier Create Account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: partner-api.v2-authorize-list\n    - name: partner-api-create-zap-guess\n      description: Zapier Guess a Zap [Beta]\n      hints:\n        readOnly: false\n        openWorld: true\n      call: partner-api.create-zap-guess\n    - name: partner-api-v2-whitelabel-apps-list\n      description: Zapier Get Whitelabel Apps [v2]\n      hints:\n        readOnly: true\n        openWorld: true\n      call: partner-api.v2-whitelabel-apps-list\n    - name: partner-api-get-zap-runs\n      description: Zapier Get Zap Runs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: partner-api.get-zap-runs\n    - name: partner-api-get-v2-zaps\n      description: Zapier\
  \ Get Zaps [v2]\n      hints:\n        readOnly: true\n        openWorld: true\n      call: partner-api.get-v2-zaps\n"
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
