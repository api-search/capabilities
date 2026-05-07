---
categories: []
consumed_apis: []
description: We are Leaf Agriculture, provider of a unified farm data API. After experiencing the difficulty of building applications in food and agriculture first hand as software developers, and hearing similar stories of frustration with existing tools and often insurmountable technical barriers from other companies, we decided to tackle the problem at hand.
layout: capability
name: Leaf Agriculture Leaf API
operations:
- description: Leaf Agriculture Get your Leaf Token
  method: POST
  name: post-api-authenticate
  path: /api/authenticate
- description: Leaf Agriculture Get all fields
  method: GET
  name: get-services-fields-api-fields
  path: /services/fields/api/fields
- description: Leaf Agriculture Get all files
  method: GET
  name: get-services-operations-api-files
  path: /services/operations/api/files
- description: Leaf Agriculture Get specific file by id
  method: GET
  name: get-services-operations-api-files-file-id
  path: /services/operations/api/files/{file_id}
- description: Leaf Agriculture Get file summary
  method: GET
  name: get-services-operations-api-files-file-id-summar
  path: /services/operations/api/files/{file_id}/summary
- description: Leaf Agriculture Get file images
  method: GET
  name: get-services-operations-api-files-file-id-images
  path: /services/operations/api/files/{file_id}/images
- description: Leaf Agriculture Get all satellite fields
  method: GET
  name: get-services-satellite-api-fields
  path: /services/satellite/api/fields
- description: Leaf Agriculture Create a satellite field
  method: POST
  name: post-services-satellite-api-fields
  path: /services/satellite/api/fields
- description: Leaf Agriculture Get images of satellite field
  method: GET
  name: get-services-satellite-api-fields-sat-external-i
  path: /services/satellite/api/fields/{sat_external_id}/processes
- description: Leaf Agriculture Get Trimble auth URL
  method: POST
  name: post-get-url
  path: /get_url
- description: Leaf Agriculture Get Trimble Token
  method: POST
  name: post-get-token
  path: /get_token
- description: Leaf Agriculture 1. Get CFV auth URL
  method: POST
  name: post-url
  path: /url
- description: Leaf Agriculture 2. Get CFV Tokens
  method: POST
  name: post-api-oauth-token
  path: /api/oauth/token
- description: Leaf Agriculture Get Stara API key
  method: POST
  name: post-autenticacao
  path: /autenticacao
- description: Leaf Agriculture Get Stara Tokens
  method: POST
  name: post-token
  path: /token
- description: Leaf Agriculture 1. Get Lindsay auth URL
  method: POST
  name: post-lindsay-url
  path: /lindsay/url
- description: Leaf Agriculture 2. Get Lindsay Token
  method: POST
  name: post-lindsay-token
  path: /lindsay/token
- description: Leaf Agriculture Get ClimateFieldView credentials of the LeafUser
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/climate-field-view-credentials
- description: Leaf Agriculture Add ClimateFieldView credentials to the LeafUser
  method: POST
  name: post-services-usermanagement-api-users-leaf-user
  path: /services/usermanagement/api/users/{leaf_user_id}/climate-field-view-credentials
- description: Leaf Agriculture Delete ClimateFieldView credentials of the LeafUser
  method: DELETE
  name: delete-services-usermanagement-api-users-leaf-us
  path: /services/usermanagement/api/users/{leaf_user_id}/climate-field-view-credentials
- description: Leaf Agriculture Get ClimateFieldView credentials Events
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/climate-field-view-credentials/events
- description: Leaf Agriculture Get JohnDeere credentials of the LeafUser
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/john-deere-credentials
- description: Leaf Agriculture Add JohnDeere credentials to the LeafUser
  method: POST
  name: post-services-usermanagement-api-users-leaf-user
  path: /services/usermanagement/api/users/{leaf_user_id}/john-deere-credentials
- description: Leaf Agriculture Delete JohnDeere credentials of the LeafUser
  method: DELETE
  name: delete-services-usermanagement-api-users-leaf-us
  path: /services/usermanagement/api/users/{leaf_user_id}/john-deere-credentials
- description: Leaf Agriculture Get JohnDeere credentials Events
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/john-deere-credentials/events
- description: Leaf Agriculture Get AgLeader credentials from Leaf User
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/ag-leader-credentials
- description: Leaf Agriculture Add AgLeader credentials to a Leaf User
  method: POST
  name: post-services-usermanagement-api-users-leaf-user
  path: /services/usermanagement/api/users/{leaf_user_id}/ag-leader-credentials
- description: Leaf Agriculture Delete AgLeader credentials from a Leaf User
  method: DELETE
  name: delete-services-usermanagement-api-users-leaf-us
  path: /services/usermanagement/api/users/{leaf_user_id}/ag-leader-credentials
- description: Leaf Agriculture Get AgLeader credentials Events
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/ag-leader-credentials/events
- description: Leaf Agriculture Get Agvance credentials from Leaf User
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/agvance-credentials
- description: Leaf Agriculture Add Agvance credentials to a Leaf User
  method: POST
  name: post-services-usermanagement-api-users-leaf-user
  path: /services/usermanagement/api/users/{leaf_user_id}/agvance-credentials
- description: Leaf Agriculture Delete Agvance credentials from a Leaf User
  method: DELETE
  name: delete-services-usermanagement-api-users-leaf-us
  path: /services/usermanagement/api/users/{leaf_user_id}/agvance-credentials
- description: Leaf Agriculture Get Agvance credentials Events
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/agvance-credentials/events
- description: Leaf Agriculture Get CNHi credentials of the LeafUser
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/cnhi-credentials
- description: Leaf Agriculture Add CNHi credentials to LeafUser
  method: POST
  name: post-services-usermanagement-api-users-leaf-user
  path: /services/usermanagement/api/users/{leaf_user_id}/cnhi-credentials
- description: Leaf Agriculture Delete CNHi credentials of the LeafUser
  method: DELETE
  name: delete-services-usermanagement-api-users-leaf-us
  path: /services/usermanagement/api/users/{leaf_user_id}/cnhi-credentials
- description: Leaf Agriculture Get CNHI credentials Events
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/cnhi-credentials/events
- description: Leaf Agriculture Get Lindsay credentials of the LeafUser
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/lindsay-credentials
- description: Leaf Agriculture Add Lindsay credentials to the LeafUser
  method: POST
  name: post-services-usermanagement-api-users-leaf-user
  path: /services/usermanagement/api/users/{leaf_user_id}/lindsay-credentials
- description: Leaf Agriculture Delete Lindsay credentials of the LeafUser
  method: DELETE
  name: delete-services-usermanagement-api-users-leaf-us
  path: /services/usermanagement/api/users/{leaf_user_id}/lindsay-credentials
- description: Leaf Agriculture Get Lindsay credentials Events
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/lindsay-credentials/events
- description: Leaf Agriculture Get Raven credentials of the LeafUser
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/raven-credentials
- description: Leaf Agriculture Add Raven credentials to the LeafUser
  method: POST
  name: post-services-usermanagement-api-users-leaf-user
  path: /services/usermanagement/api/users/{leaf_user_id}/raven-credentials
- description: Leaf Agriculture Delete Raven credentials of the LeafUser
  method: DELETE
  name: delete-services-usermanagement-api-users-leaf-us
  path: /services/usermanagement/api/users/{leaf_user_id}/raven-credentials
- description: Leaf Agriculture Get Raven credentials Events
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/raven-credentials/events
- description: Leaf Agriculture Get RavenSlingshot credentials of the LeafUser
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/raven-slingshot-credentials
- description: Leaf Agriculture Add RavenSlingshot credentials to the LeafUser
  method: POST
  name: post-services-usermanagement-api-users-leaf-user
  path: /services/usermanagement/api/users/{leaf_user_id}/raven-slingshot-credentials
- description: Leaf Agriculture Delete RavenSlingshot credentials of the LeafUser
  method: DELETE
  name: delete-services-usermanagement-api-users-leaf-us
  path: /services/usermanagement/api/users/{leaf_user_id}/raven-slingshot-credentials
- description: Leaf Agriculture Get RavenSlingshot credentials Events
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/raven-slingshot-credentials/events
- description: Leaf Agriculture Get Sentera credentials from Leaf User
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/sentera-credentials
- description: Leaf Agriculture Add Sentera credentials to a Leaf User
  method: POST
  name: post-services-usermanagement-api-users-leaf-user
  path: /services/usermanagement/api/users/{leaf_user_id}/sentera-credentials
- description: Leaf Agriculture Delete Sentera credentials from a Leaf User
  method: DELETE
  name: delete-services-usermanagement-api-users-leaf-us
  path: /services/usermanagement/api/users/{leaf_user_id}/sentera-credentials
- description: Leaf Agriculture Get Sentera credentials Events
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/sentera-credentials/events
- description: Leaf Agriculture Get Stara credentials of the LeafUser
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/stara-credentials
- description: Leaf Agriculture Add Stara credentials to the LeafUser
  method: POST
  name: post-services-usermanagement-api-users-leaf-user
  path: /services/usermanagement/api/users/{leaf_user_id}/stara-credentials
- description: Leaf Agriculture Delete Stara credentials of the LeafUser
  method: DELETE
  name: delete-services-usermanagement-api-users-leaf-us
  path: /services/usermanagement/api/users/{leaf_user_id}/stara-credentials
- description: Leaf Agriculture Get Stara credentials Events
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/stara-credentials/events
- description: Leaf Agriculture Get Trimble credentials of the LeafUser
  method: GET
  name: get-services-usermanagement-api-users-leaf-user-
  path: /services/usermanagement/api/users/{leaf_user_id}/trimble-credentials
- description: Leaf Agriculture Add Trimble credentials to the LeafUser
  method: POST
  name: post-services-usermanagement-api-users-leaf-user
  path: /services/usermanagement/api/users/{leaf_user_id}/trimble-credentials
- description: Leaf Agriculture Delete Trimble credentials of the LeafUser
  method: DELETE
  name: delete-services-usermanagement-api-users-leaf-us
  path: /services/usermanagement/api/users/{leaf_user_id}/trimble-credentials
personas: []
provider_name: Leaf Agriculture
provider_slug: leaf-agriculture
search_terms:
- leaf agriculture 2. get cfv tokens
- api
- get services satellite api fields
- leaf agriculture get agleader credentials events
- leaf agriculture add lindsay credentials to the leafuser
- leaf
- leaf agriculture get file images
- farm data
- leaf agriculture delete ravenslingshot credentials of the leafuser
- leaf agriculture get sentera credentials events
- leaf agriculture get stara credentials events
- leaf agriculture get all satellite fields
- leaf agriculture get agvance credentials from leaf user
- leaf agriculture 2. get lindsay token
- leaf agriculture add sentera credentials to a leaf user
- post services satellite api fields
- leaf agriculture get specific file by id
- post lindsay token
- leaf agriculture get johndeere credentials of the leafuser
- leaf agriculture get images of satellite field
- leaf agriculture get trimble auth url
- leaf agriculture get trimble token
- post api oauth token
- weather
- leaf agriculture get agleader credentials from leaf user
- post services usermanagement api users leaf user
- leaf agriculture get trimble credentials of the leafuser
- leaf agriculture get all files
- get services operations api files file id
- leaf agriculture get lindsay credentials events
- agriculture
- leaf agriculture add johndeere credentials to the leafuser
- delete services usermanagement api users leaf us
- leaf agriculture add cnhi credentials to leafuser
- leaf agriculture get stara tokens
- leaf agriculture get raven credentials events
- leaf agriculture 1. get lindsay auth url
- leaf agriculture add ravenslingshot credentials to the leafuser
- leaf agriculture get agvance credentials events
- leaf agriculture delete sentera credentials from a leaf user
- leaf agriculture delete lindsay credentials of the leafuser
- leaf agriculture delete stara credentials of the leafuser
- leaf agriculture add agvance credentials to a leaf user
- get services operations api files file id summar
- post api authenticate
- post get token
- leaf agriculture add climatefieldview credentials to the leafuser
- leaf agriculture get climatefieldview credentials events
- leaf agriculture add trimble credentials to the leafuser
- leaf agriculture get sentera credentials from leaf user
- get services satellite api fields sat external i
- unified api
- leaf agriculture get climatefieldview credentials of the leafuser
- leaf agriculture add stara credentials to the leafuser
- post get url
- provider integrations
- leaf agriculture get stara api key
- leaf agriculture delete agleader credentials from a leaf user
- leaf agriculture get stara credentials of the leafuser
- leaf agriculture delete trimble credentials of the leafuser
- leaf agriculture get raven credentials of the leafuser
- get services fields api fields
- leaf agriculture get cnhi credentials of the leafuser
- leaf agriculture get file summary
- leaf agriculture get ravenslingshot credentials of the leafuser
- leaf agriculture add agleader credentials to a leaf user
- leaf agriculture get cnhi credentials events
- post url
- leaf agriculture delete cnhi credentials of the leafuser
- leaf agriculture delete johndeere credentials of the leafuser
- leaf agriculture get ravenslingshot credentials events
- leaf agriculture add raven credentials to the leafuser
- machine operations
- leaf agriculture delete agvance credentials from a leaf user
- leaf agriculture get all fields
- leaf agriculture get johndeere credentials events
- leaf agriculture get your leaf token
- post autenticacao
- leaf agriculture 1. get cfv auth url
- field boundaries
- webhooks
- get services operations api files file id images
- leaf agriculture create a satellite field
- post token
- get services operations api files
- leaf agriculture delete raven credentials of the leafuser
- post lindsay url
- get services usermanagement api users leaf user
- leaf agriculture get lindsay credentials of the leafuser
- leaf agriculture delete climatefieldview credentials of the leafuser
slug: leaf-agriculture-capability
source_filename: leaf-agriculture-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Leaf Agriculture Leaf API\n  description: We are Leaf Agriculture, provider of a unified farm data API. After experiencing the difficulty of building\n    applications in food and agriculture first hand as software developers, and hearing similar stories of frustration with\n    existing tools and often insurmountable technical barriers from other companies, we decided to tackle the problem at hand.\n  tags:\n  - Leaf\n  - Agriculture\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: leaf-agriculture\n    baseUri: https://api.example.com\n    description: Leaf Agriculture Leaf API HTTP API.\n    resources:\n    - name: api-authenticate\n      path: /api/authenticate\n      operations:\n      - name: post-api-authenticate\n        method: POST\n        description: Leaf Agriculture Get your Leaf Token\n        inputParameters:\n        - name: Content-Type\n          in:\
  \ header\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-fields-api-fields\n      path: /services/fields/api/fields\n      operations:\n      - name: get-services-fields-api-fields\n        method: GET\n        description: Leaf Agriculture Get all fields\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n        - name: Authorization\n          in: header\n          type: string\n        - name: leafUserId\n          in: query\n          type: string\n          description: your Leaf User id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-operations-api-files\n      path: /services/operations/api/files\n      operations:\n      - name: get-services-operations-api-files\n        method: GET\n        description:\
  \ Leaf Agriculture Get all files\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n        - name: Authorization\n          in: header\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-operations-api-files-file-id\n      path: /services/operations/api/files/{file_id}\n      operations:\n      - name: get-services-operations-api-files-file-id\n        method: GET\n        description: Leaf Agriculture Get specific file by id\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n        - name: Authorization\n          in: header\n          type: string\n        - name: file_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: services-operations-api-files-file-id-summary\n      path: /services/operations/api/files/{file_id}/summary\n      operations:\n      - name: get-services-operations-api-files-file-id-summar\n        method: GET\n        description: Leaf Agriculture Get file summary\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n        - name: Authorization\n          in: header\n          type: string\n        - name: file_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-operations-api-files-file-id-images\n      path: /services/operations/api/files/{file_id}/images\n      operations:\n      - name: get-services-operations-api-files-file-id-images\n        method: GET\n        description: Leaf Agriculture Get file images\n        inputParameters:\n       \
  \ - name: Content-Type\n          in: header\n          type: string\n        - name: Authorization\n          in: header\n          type: string\n        - name: file_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-satellite-api-fields\n      path: /services/satellite/api/fields\n      operations:\n      - name: get-services-satellite-api-fields\n        method: GET\n        description: Leaf Agriculture Get all satellite fields\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n        - name: Authorization\n          in: header\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-services-satellite-api-fields\n        method: POST\n        description:\
  \ Leaf Agriculture Create a satellite field\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n        - name: Authorization\n          in: header\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-satellite-api-fields-sat-external-id-pr\n      path: /services/satellite/api/fields/{sat_external_id}/processes\n      operations:\n      - name: get-services-satellite-api-fields-sat-external-i\n        method: GET\n        description: Leaf Agriculture Get images of satellite field\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n        - name: Authorization\n          in: header\n          type: string\n        - name: sat_external_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n    - name: get-url\n      path: /get_url\n      operations:\n      - name: post-get-url\n        method: POST\n        description: Leaf Agriculture Get Trimble auth URL\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-token\n      path: /get_token\n      operations:\n      - name: post-get-token\n        method: POST\n        description: Leaf Agriculture Get Trimble Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: url\n      path: /url\n      operations:\n      - name: post-url\n        method: POST\n        description: Leaf Agriculture 1. Get CFV auth URL\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-oauth-token\n      path: /api/oauth/token\n\
  \      operations:\n      - name: post-api-oauth-token\n        method: POST\n        description: Leaf Agriculture 2. Get CFV Tokens\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          description: Basic base64(clientId:clientSecret)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: autenticacao\n      path: /autenticacao\n      operations:\n      - name: post-autenticacao\n        method: POST\n        description: Leaf Agriculture Get Stara API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: token\n      path: /token\n      operations:\n      - name: post-token\n        method: POST\n        description: Leaf Agriculture Get Stara Tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: lindsay-url\n      path: /lindsay/url\n      operations:\n      - name: post-lindsay-url\n        method: POST\n        description: Leaf Agriculture 1. Get Lindsay auth URL\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lindsay-token\n      path: /lindsay/token\n      operations:\n      - name: post-lindsay-token\n        method: POST\n        description: Leaf Agriculture 2. Get Lindsay Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-c\n      path: /services/usermanagement/api/users/{leaf_user_id}/climate-field-view-credentials\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get ClimateFieldView credentials of the LeafUser\n\
  \        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-services-usermanagement-api-users-leaf-user\n        method: POST\n        description: Leaf Agriculture Add ClimateFieldView credentials to the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ delete-services-usermanagement-api-users-leaf-us\n        method: DELETE\n        description: Leaf Agriculture Delete ClimateFieldView credentials of the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-c\n      path: /services/usermanagement/api/users/{leaf_user_id}/climate-field-view-credentials/events\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get ClimateFieldView credentials Events\n        inputParameters:\n        - name: leaf_user_id\n          in: path\n    \
  \      type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-j\n      path: /services/usermanagement/api/users/{leaf_user_id}/john-deere-credentials\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get JohnDeere credentials of the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-services-usermanagement-api-users-leaf-user\n        method: POST\n\
  \        description: Leaf Agriculture Add JohnDeere credentials to the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-services-usermanagement-api-users-leaf-us\n        method: DELETE\n        description: Leaf Agriculture Delete JohnDeere credentials of the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-j\n      path: /services/usermanagement/api/users/{leaf_user_id}/john-deere-credentials/events\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get JohnDeere credentials Events\n        inputParameters:\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-a\n      path: /services/usermanagement/api/users/{leaf_user_id}/ag-leader-credentials\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get AgLeader credentials from Leaf User\n        inputParameters:\n\
  \        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-services-usermanagement-api-users-leaf-user\n        method: POST\n        description: Leaf Agriculture Add AgLeader credentials to a Leaf User\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-services-usermanagement-api-users-leaf-us\n\
  \        method: DELETE\n        description: Leaf Agriculture Delete AgLeader credentials from a Leaf User\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-a\n      path: /services/usermanagement/api/users/{leaf_user_id}/ag-leader-credentials/events\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get AgLeader credentials Events\n        inputParameters:\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-a\n      path: /services/usermanagement/api/users/{leaf_user_id}/agvance-credentials\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get Agvance credentials from Leaf User\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-services-usermanagement-api-users-leaf-user\n        method: POST\n        description: Leaf Agriculture Add Agvance credentials to a Leaf User\n     \
  \   inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-services-usermanagement-api-users-leaf-us\n        method: DELETE\n        description: Leaf Agriculture Delete Agvance credentials from a Leaf User\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-a\n\
  \      path: /services/usermanagement/api/users/{leaf_user_id}/agvance-credentials/events\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get Agvance credentials Events\n        inputParameters:\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-c\n      path: /services/usermanagement/api/users/{leaf_user_id}/cnhi-credentials\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get CNHi credentials of the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n    \
  \      type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-services-usermanagement-api-users-leaf-user\n        method: POST\n        description: Leaf Agriculture Add CNHi credentials to LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-services-usermanagement-api-users-leaf-us\n        method: DELETE\n        description: Leaf Agriculture Delete CNHi credentials of the LeafUser\n        inputParameters:\n\
  \        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-c\n      path: /services/usermanagement/api/users/{leaf_user_id}/cnhi-credentials/events\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get CNHI credentials Events\n        inputParameters:\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-l\n\
  \      path: /services/usermanagement/api/users/{leaf_user_id}/lindsay-credentials\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get Lindsay credentials of the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-services-usermanagement-api-users-leaf-user\n        method: POST\n        description: Leaf Agriculture Add Lindsay credentials to the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n      \
  \    type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-services-usermanagement-api-users-leaf-us\n        method: DELETE\n        description: Leaf Agriculture Delete Lindsay credentials of the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-l\n      path: /services/usermanagement/api/users/{leaf_user_id}/lindsay-credentials/events\n      operations:\n      -\
  \ name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get Lindsay credentials Events\n        inputParameters:\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-r\n      path: /services/usermanagement/api/users/{leaf_user_id}/raven-credentials\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get Raven credentials of the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-services-usermanagement-api-users-leaf-user\n        method: POST\n        description: Leaf Agriculture Add Raven credentials to the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-services-usermanagement-api-users-leaf-us\n        method: DELETE\n        description: Leaf Agriculture Delete Raven credentials of the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n \
  \         in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-r\n      path: /services/usermanagement/api/users/{leaf_user_id}/raven-credentials/events\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get Raven credentials Events\n        inputParameters:\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-r\n      path: /services/usermanagement/api/users/{leaf_user_id}/raven-slingshot-credentials\n\
  \      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get RavenSlingshot credentials of the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-services-usermanagement-api-users-leaf-user\n        method: POST\n        description: Leaf Agriculture Add RavenSlingshot credentials to the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n \
  \         type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-services-usermanagement-api-users-leaf-us\n        method: DELETE\n        description: Leaf Agriculture Delete RavenSlingshot credentials of the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-r\n      path: /services/usermanagement/api/users/{leaf_user_id}/raven-slingshot-credentials/events\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n\
  \        method: GET\n        description: Leaf Agriculture Get RavenSlingshot credentials Events\n        inputParameters:\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-s\n      path: /services/usermanagement/api/users/{leaf_user_id}/sentera-credentials\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get Sentera credentials from Leaf User\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: post-services-usermanagement-api-users-leaf-user\n        method: POST\n        description: Leaf Agriculture Add Sentera credentials to a Leaf User\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-services-usermanagement-api-users-leaf-us\n        method: DELETE\n        description: Leaf Agriculture Delete Sentera credentials from a Leaf User\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        -\
  \ name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-s\n      path: /services/usermanagement/api/users/{leaf_user_id}/sentera-credentials/events\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get Sentera credentials Events\n        inputParameters:\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-s\n      path: /services/usermanagement/api/users/{leaf_user_id}/stara-credentials\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n\
  \        method: GET\n        description: Leaf Agriculture Get Stara credentials of the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-services-usermanagement-api-users-leaf-user\n        method: POST\n        description: Leaf Agriculture Add Stara credentials to the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: delete-services-usermanagement-api-users-leaf-us\n        method: DELETE\n        description: Leaf Agriculture Delete Stara credentials of the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          type: string\n        - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-s\n      path: /services/usermanagement/api/users/{leaf_user_id}/stara-credentials/events\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get Stara credentials Events\n        inputParameters:\n       \
  \ - name: leaf_user_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-usermanagement-api-users-leaf-user-id-t\n      path: /services/usermanagement/api/users/{leaf_user_id}/trimble-credentials\n      operations:\n      - name: get-services-usermanagement-api-users-leaf-user-\n        method: GET\n        description: Leaf Agriculture Get Trimble credentials of the LeafUser\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        - name: Content-Type\n          in: header\n          ty\n\n# --- truncated at 32 KB (90 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/leaf-agriculture/refs/heads/main/capabilities/leaf-agriculture-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/leaf-agriculture/refs/heads/main/capabilities/leaf-agriculture-capability.yaml
tags:
- Leaf
- Agriculture
- API
tools:
- description: Leaf Agriculture Get your Leaf Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-authenticate
- description: Leaf Agriculture Get all fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-fields-api-fields
- description: Leaf Agriculture Get all files
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-operations-api-files
- description: Leaf Agriculture Get specific file by id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-operations-api-files-file-id
- description: Leaf Agriculture Get file summary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-operations-api-files-file-id-summar
- description: Leaf Agriculture Get file images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-operations-api-files-file-id-images
- description: Leaf Agriculture Get all satellite fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-satellite-api-fields
- description: Leaf Agriculture Create a satellite field
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-services-satellite-api-fields
- description: Leaf Agriculture Get images of satellite field
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-satellite-api-fields-sat-external-i
- description: Leaf Agriculture Get Trimble auth URL
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-get-url
- description: Leaf Agriculture Get Trimble Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-get-token
- description: Leaf Agriculture 1. Get CFV auth URL
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-url
- description: Leaf Agriculture 2. Get CFV Tokens
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-oauth-token
- description: Leaf Agriculture Get Stara API key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-autenticacao
- description: Leaf Agriculture Get Stara Tokens
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-token
- description: Leaf Agriculture 1. Get Lindsay auth URL
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-lindsay-url
- description: Leaf Agriculture 2. Get Lindsay Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-lindsay-token
- description: Leaf Agriculture Get ClimateFieldView credentials of the LeafUser
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Add ClimateFieldView credentials to the LeafUser
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-services-usermanagement-api-users-leaf-user
- description: Leaf Agriculture Delete ClimateFieldView credentials of the LeafUser
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-services-usermanagement-api-users-leaf-us
- description: Leaf Agriculture Get ClimateFieldView credentials Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Get JohnDeere credentials of the LeafUser
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Add JohnDeere credentials to the LeafUser
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-services-usermanagement-api-users-leaf-user
- description: Leaf Agriculture Delete JohnDeere credentials of the LeafUser
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-services-usermanagement-api-users-leaf-us
- description: Leaf Agriculture Get JohnDeere credentials Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Get AgLeader credentials from Leaf User
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Add AgLeader credentials to a Leaf User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-services-usermanagement-api-users-leaf-user
- description: Leaf Agriculture Delete AgLeader credentials from a Leaf User
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-services-usermanagement-api-users-leaf-us
- description: Leaf Agriculture Get AgLeader credentials Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Get Agvance credentials from Leaf User
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Add Agvance credentials to a Leaf User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-services-usermanagement-api-users-leaf-user
- description: Leaf Agriculture Delete Agvance credentials from a Leaf User
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-services-usermanagement-api-users-leaf-us
- description: Leaf Agriculture Get Agvance credentials Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Get CNHi credentials of the LeafUser
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Add CNHi credentials to LeafUser
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-services-usermanagement-api-users-leaf-user
- description: Leaf Agriculture Delete CNHi credentials of the LeafUser
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-services-usermanagement-api-users-leaf-us
- description: Leaf Agriculture Get CNHI credentials Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Get Lindsay credentials of the LeafUser
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Add Lindsay credentials to the LeafUser
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-services-usermanagement-api-users-leaf-user
- description: Leaf Agriculture Delete Lindsay credentials of the LeafUser
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-services-usermanagement-api-users-leaf-us
- description: Leaf Agriculture Get Lindsay credentials Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Get Raven credentials of the LeafUser
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Add Raven credentials to the LeafUser
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-services-usermanagement-api-users-leaf-user
- description: Leaf Agriculture Delete Raven credentials of the LeafUser
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-services-usermanagement-api-users-leaf-us
- description: Leaf Agriculture Get Raven credentials Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Get RavenSlingshot credentials of the LeafUser
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Add RavenSlingshot credentials to the LeafUser
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-services-usermanagement-api-users-leaf-user
- description: Leaf Agriculture Delete RavenSlingshot credentials of the LeafUser
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-services-usermanagement-api-users-leaf-us
- description: Leaf Agriculture Get RavenSlingshot credentials Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Get Sentera credentials from Leaf User
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Add Sentera credentials to a Leaf User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-services-usermanagement-api-users-leaf-user
- description: Leaf Agriculture Delete Sentera credentials from a Leaf User
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-services-usermanagement-api-users-leaf-us
- description: Leaf Agriculture Get Sentera credentials Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Get Stara credentials of the LeafUser
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Add Stara credentials to the LeafUser
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-services-usermanagement-api-users-leaf-user
- description: Leaf Agriculture Delete Stara credentials of the LeafUser
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-services-usermanagement-api-users-leaf-us
- description: Leaf Agriculture Get Stara credentials Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Get Trimble credentials of the LeafUser
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-services-usermanagement-api-users-leaf-user-
- description: Leaf Agriculture Add Trimble credentials to the LeafUser
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-services-usermanagement-api-users-leaf-user
- description: Leaf Agriculture Delete Trimble credentials of the LeafUser
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-services-usermanagement-api-users-leaf-us
---
