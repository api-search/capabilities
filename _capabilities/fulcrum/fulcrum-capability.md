---
categories: []
consumed_apis: []
description: The Fulcrum API is a RESTful HTTP API for the Fulcrum field data collection platform. It provides programmatic access to forms, records, media (photos, videos, audio, signatures), choice lists, classification sets, projects, layers, memberships, roles, webhooks, ad hoc query and SQL execution, and changesets. Requests and responses use JSON and authenticate with an X-ApiToken header issued from a Fulcrum account.
layout: capability
name: Fulcrum API
operations:
- description: List forms
  method: GET
  name: listforms
  path: /forms.json
- description: Create form
  method: POST
  name: createform
  path: /forms.json
- description: Get form
  method: GET
  name: getform
  path: /forms/{id}.json
- description: Update form
  method: PUT
  name: updateform
  path: /forms/{id}.json
- description: Delete form
  method: DELETE
  name: deleteform
  path: /forms/{id}.json
- description: List records
  method: GET
  name: listrecords
  path: /records.json
- description: Create record
  method: POST
  name: createrecord
  path: /records.json
- description: Get record
  method: GET
  name: getrecord
  path: /records/{id}.json
- description: Update record
  method: PUT
  name: updaterecord
  path: /records/{id}.json
- description: Delete record
  method: DELETE
  name: deleterecord
  path: /records/{id}.json
- description: List photos
  method: GET
  name: listphotos
  path: /photos.json
- description: Upload photo
  method: POST
  name: uploadphoto
  path: /photos.json
- description: Get photo metadata
  method: GET
  name: getphoto
  path: /photos/{id}.json
- description: Download photo
  method: GET
  name: downloadphoto
  path: /photos/{id}.jpg
- description: List videos
  method: GET
  name: listvideos
  path: /videos.json
- description: Upload video
  method: POST
  name: uploadvideo
  path: /videos.json
- description: List audio clips
  method: GET
  name: listaudio
  path: /audio.json
- description: Upload audio
  method: POST
  name: uploadaudio
  path: /audio.json
- description: List signatures
  method: GET
  name: listsignatures
  path: /signatures.json
- description: Upload signature
  method: POST
  name: uploadsignature
  path: /signatures.json
- description: List choice lists
  method: GET
  name: listchoicelists
  path: /choice_lists.json
- description: Create choice list
  method: POST
  name: createchoicelist
  path: /choice_lists.json
- description: Get choice list
  method: GET
  name: getchoicelist
  path: /choice_lists/{id}.json
- description: Update choice list
  method: PUT
  name: updatechoicelist
  path: /choice_lists/{id}.json
- description: Delete choice list
  method: DELETE
  name: deletechoicelist
  path: /choice_lists/{id}.json
- description: List classification sets
  method: GET
  name: listclassificationsets
  path: /classification_sets.json
- description: Create classification set
  method: POST
  name: createclassificationset
  path: /classification_sets.json
- description: Get classification set
  method: GET
  name: getclassificationset
  path: /classification_sets/{id}.json
- description: Update classification set
  method: PUT
  name: updateclassificationset
  path: /classification_sets/{id}.json
- description: Delete classification set
  method: DELETE
  name: deleteclassificationset
  path: /classification_sets/{id}.json
- description: List projects
  method: GET
  name: listprojects
  path: /projects.json
- description: Create project
  method: POST
  name: createproject
  path: /projects.json
- description: Get project
  method: GET
  name: getproject
  path: /projects/{id}.json
- description: Update project
  method: PUT
  name: updateproject
  path: /projects/{id}.json
- description: Delete project
  method: DELETE
  name: deleteproject
  path: /projects/{id}.json
- description: List layers
  method: GET
  name: listlayers
  path: /layers.json
- description: Create layer
  method: POST
  name: createlayer
  path: /layers.json
- description: Get layer
  method: GET
  name: getlayer
  path: /layers/{id}.json
- description: Update layer
  method: PUT
  name: updatelayer
  path: /layers/{id}.json
- description: Delete layer
  method: DELETE
  name: deletelayer
  path: /layers/{id}.json
- description: List memberships
  method: GET
  name: listmemberships
  path: /memberships.json
- description: Update membership
  method: PUT
  name: updatemembership
  path: /memberships/{id}.json
- description: List roles
  method: GET
  name: listroles
  path: /roles.json
- description: Create role
  method: POST
  name: createrole
  path: /roles.json
- description: Get role
  method: GET
  name: getrole
  path: /roles/{id}.json
- description: Update role
  method: PUT
  name: updaterole
  path: /roles/{id}.json
- description: Delete role
  method: DELETE
  name: deleterole
  path: /roles/{id}.json
- description: List webhooks
  method: GET
  name: listwebhooks
  path: /webhooks.json
- description: Create webhook
  method: POST
  name: createwebhook
  path: /webhooks.json
- description: Get webhook
  method: GET
  name: getwebhook
  path: /webhooks/{id}.json
- description: Update webhook
  method: PUT
  name: updatewebhook
  path: /webhooks/{id}.json
- description: Delete webhook
  method: DELETE
  name: deletewebhook
  path: /webhooks/{id}.json
- description: List changesets
  method: GET
  name: listchangesets
  path: /changesets.json
- description: Get changeset
  method: GET
  name: getchangeset
  path: /changesets/{id}.json
- description: Execute SQL query
  method: GET
  name: executequery
  path: /query
personas: []
provider_name: Fulcrum
provider_slug: fulcrum
search_terms:
- listaudio
- get webhook
- updaterecord
- createrecord
- list signatures
- api
- getchoicelist
- listrecords
- updaterole
- listlayers
- delete role
- deletelayer
- delete record
- updatechoicelist
- getrole
- update choice list
- update form
- deleteproject
- listvideos
- list videos
- upload audio
- listclassificationsets
- update layer
- get choice list
- updatemembership
- createrole
- field data
- get form
- createchoicelist
- upload photo
- update membership
- list photos
- create form
- get record
- listsignatures
- updateproject
- update record
- list projects
- create role
- list webhooks
- fulcrum
- list changesets
- list choice lists
- update webhook
- create choice list
- listmemberships
- list audio clips
- list roles
- deletechoicelist
- getproject
- create record
- list memberships
- data collection
- uploadphoto
- create webhook
- getrecord
- download photo
- updatewebhook
- deleteclassificationset
- downloadphoto
- updateform
- get changeset
- delete project
- delete layer
- list records
- list classification sets
- list forms
- get project
- listchangesets
- update role
- update project
- createclassificationset
- createproject
- updatelayer
- getwebhook
- upload signature
- delete webhook
- uploadvideo
- getlayer
- execute sql query
- mobile
- getform
- updateclassificationset
- get role
- createlayer
- deleterole
- create layer
- listforms
- createwebhook
- get layer
- delete choice list
- deleterecord
- geospatial
- create project
- get classification set
- uploadsignature
- delete classification set
- getclassificationset
- update classification set
- deleteform
- get photo metadata
- uploadaudio
- delete form
- listroles
- list layers
- listwebhooks
- deletewebhook
- listprojects
- process management
- createform
- upload video
- executequery
- getphoto
- listphotos
- create classification set
- getchangeset
- listchoicelists
slug: fulcrum-capability
source_filename: fulcrum-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Fulcrum API\n  description: The Fulcrum API is a RESTful HTTP API for the Fulcrum field data collection platform. It provides programmatic\n    access to forms, records, media (photos, videos, audio, signatures), choice lists, classification sets, projects, layers,\n    memberships, roles, webhooks, ad hoc query and SQL execution, and changesets. Requests and responses use JSON and authenticate\n    with an X-ApiToken header issued from a Fulcrum account.\n  tags:\n  - Fulcrum\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fulcrum\n    baseUri: https://api.fulcrumapp.com/api/v2\n    description: Fulcrum API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-ApiToken\n      value: '{{FULCRUM_TOKEN}}'\n    resources:\n    - name: forms-json\n      path: /forms.json\n      operations:\n      - name: listforms\n        method: GET\n    \
  \    description: List forms\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createform\n        method: POST\n        description: Create form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forms-id-json\n      path: /forms/{id}.json\n      operations:\n      - name: getform\n        method: GET\n        description: Get form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateform\n        method: PUT\n        description: Update form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteform\n        method: DELETE\n        description: Delete form\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: records-json\n      path: /records.json\n      operations:\n      - name: listrecords\n        method: GET\n        description: List records\n        inputParameters:\n        - name: form_id\n          in: query\n          type: string\n          description: Filter by form (app) identifier\n        - name: project_id\n          in: query\n          type: string\n          description: Filter by project identifier\n        - name: assigned_to_id\n          in: query\n          type: string\n          description: Filter by assignment\n        - name: status\n          in: query\n          type: string\n          description: Filter by record status\n        - name: bounding_box\n          in: query\n          type: string\n          description: Comma-separated south,west,north,east bounding box\n        - name: per_page\n          in: query\n          type: integer\n        - name: page\n          in: query\n\
  \          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrecord\n        method: POST\n        description: Create record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: records-id-json\n      path: /records/{id}.json\n      operations:\n      - name: getrecord\n        method: GET\n        description: Get record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterecord\n        method: PUT\n        description: Update record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterecord\n        method: DELETE\n        description: Delete record\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: photos-json\n      path: /photos.json\n      operations:\n      - name: listphotos\n        method: GET\n        description: List photos\n        inputParameters:\n        - name: form_id\n          in: query\n          type: string\n        - name: record_id\n          in: query\n          type: string\n        - name: per_page\n          in: query\n          type: integer\n        - name: page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploadphoto\n        method: POST\n        description: Upload photo\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: photos-id-json\n      path: /photos/{id}.json\n      operations:\n      - name: getphoto\n        method: GET\n        description:\
  \ Get photo metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: photos-id-jpg\n      path: /photos/{id}.jpg\n      operations:\n      - name: downloadphoto\n        method: GET\n        description: Download photo\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: videos-json\n      path: /videos.json\n      operations:\n      - name: listvideos\n        method: GET\n        description: List videos\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploadvideo\n        method: POST\n        description: Upload video\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audio-json\n      path: /audio.json\n      operations:\n   \
  \   - name: listaudio\n        method: GET\n        description: List audio clips\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploadaudio\n        method: POST\n        description: Upload audio\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: signatures-json\n      path: /signatures.json\n      operations:\n      - name: listsignatures\n        method: GET\n        description: List signatures\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploadsignature\n        method: POST\n        description: Upload signature\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: choice-lists-json\n      path: /choice_lists.json\n  \
  \    operations:\n      - name: listchoicelists\n        method: GET\n        description: List choice lists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createchoicelist\n        method: POST\n        description: Create choice list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: choice-lists-id-json\n      path: /choice_lists/{id}.json\n      operations:\n      - name: getchoicelist\n        method: GET\n        description: Get choice list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatechoicelist\n        method: PUT\n        description: Update choice list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletechoicelist\n\
  \        method: DELETE\n        description: Delete choice list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: classification-sets-json\n      path: /classification_sets.json\n      operations:\n      - name: listclassificationsets\n        method: GET\n        description: List classification sets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createclassificationset\n        method: POST\n        description: Create classification set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: classification-sets-id-json\n      path: /classification_sets/{id}.json\n      operations:\n      - name: getclassificationset\n        method: GET\n        description: Get classification set\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateclassificationset\n        method: PUT\n        description: Update classification set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteclassificationset\n        method: DELETE\n        description: Delete classification set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-json\n      path: /projects.json\n      operations:\n      - name: listprojects\n        method: GET\n        description: List projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n        method: POST\n        description: Create project\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n    - name: projects-id-json\n      path: /projects/{id}.json\n      operations:\n      - name: getproject\n        method: GET\n        description: Get project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproject\n        method: PUT\n        description: Update project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproject\n        method: DELETE\n        description: Delete project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: layers-json\n      path: /layers.json\n      operations:\n      - name: listlayers\n        method: GET\n        description: List layers\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createlayer\n        method: POST\n        description: Create layer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: layers-id-json\n      path: /layers/{id}.json\n      operations:\n      - name: getlayer\n        method: GET\n        description: Get layer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelayer\n        method: PUT\n        description: Update layer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelayer\n        method: DELETE\n        description: Delete layer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: memberships-json\n\
  \      path: /memberships.json\n      operations:\n      - name: listmemberships\n        method: GET\n        description: List memberships\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: memberships-id-json\n      path: /memberships/{id}.json\n      operations:\n      - name: updatemembership\n        method: PUT\n        description: Update membership\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles-json\n      path: /roles.json\n      operations:\n      - name: listroles\n        method: GET\n        description: List roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrole\n        method: POST\n        description: Create role\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: roles-id-json\n      path: /roles/{id}.json\n      operations:\n      - name: getrole\n        method: GET\n        description: Get role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterole\n        method: PUT\n        description: Update role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterole\n        method: DELETE\n        description: Delete role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks-json\n      path: /webhooks.json\n      operations:\n      - name: listwebhooks\n        method: GET\n        description: List webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: createwebhook\n        method: POST\n        description: Create webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks-id-json\n      path: /webhooks/{id}.json\n      operations:\n      - name: getwebhook\n        method: GET\n        description: Get webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatewebhook\n        method: PUT\n        description: Update webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletewebhook\n        method: DELETE\n        description: Delete webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: changesets-json\n\
  \      path: /changesets.json\n      operations:\n      - name: listchangesets\n        method: GET\n        description: List changesets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: changesets-id-json\n      path: /changesets/{id}.json\n      operations:\n      - name: getchangeset\n        method: GET\n        description: Get changeset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query\n      path: /query\n      operations:\n      - name: executequery\n        method: GET\n        description: Execute SQL query\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: SQL query string\n        - name: format\n          in: query\n          type: string\n          description: Result format\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fulcrum-rest\n    description: REST adapter for Fulcrum API.\n    resources:\n    - path: /forms.json\n      name: listforms\n      operations:\n      - method: GET\n        name: listforms\n        description: List forms\n        call: fulcrum.listforms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /forms.json\n      name: createform\n      operations:\n      - method: POST\n        name: createform\n        description: Create form\n        call: fulcrum.createform\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /forms/{id}.json\n      name: getform\n      operations:\n      - method: GET\n        name: getform\n        description: Get form\n        call: fulcrum.getform\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /forms/{id}.json\n      name: updateform\n      operations:\n      - method: PUT\n        name: updateform\n        description: Update form\n        call: fulcrum.updateform\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /forms/{id}.json\n      name: deleteform\n      operations:\n      - method: DELETE\n        name: deleteform\n        description: Delete form\n        call: fulcrum.deleteform\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /records.json\n      name: listrecords\n      operations:\n      - method: GET\n        name: listrecords\n        description: List records\n        call: fulcrum.listrecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /records.json\n      name: createrecord\n      operations:\n      - method: POST\n        name: createrecord\n        description: Create record\n        call: fulcrum.createrecord\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /records/{id}.json\n      name: getrecord\n      operations:\n      - method: GET\n        name: getrecord\n        description: Get record\n        call: fulcrum.getrecord\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /records/{id}.json\n      name: updaterecord\n      operations:\n      - method: PUT\n        name: updaterecord\n        description: Update record\n        call: fulcrum.updaterecord\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /records/{id}.json\n      name: deleterecord\n      operations:\n      - method: DELETE\n        name: deleterecord\n        description: Delete record\n        call: fulcrum.deleterecord\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /photos.json\n      name: listphotos\n      operations:\n      - method: GET\n        name: listphotos\n        description: List photos\n\
  \        call: fulcrum.listphotos\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /photos.json\n      name: uploadphoto\n      operations:\n      - method: POST\n        name: uploadphoto\n        description: Upload photo\n        call: fulcrum.uploadphoto\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /photos/{id}.json\n      name: getphoto\n      operations:\n      - method: GET\n        name: getphoto\n        description: Get photo metadata\n        call: fulcrum.getphoto\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /photos/{id}.jpg\n      name: downloadphoto\n      operations:\n      - method: GET\n        name: downloadphoto\n        description: Download photo\n        call: fulcrum.downloadphoto\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /videos.json\n      name: listvideos\n      operations:\n      - method: GET\n\
  \        name: listvideos\n        description: List videos\n        call: fulcrum.listvideos\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /videos.json\n      name: uploadvideo\n      operations:\n      - method: POST\n        name: uploadvideo\n        description: Upload video\n        call: fulcrum.uploadvideo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /audio.json\n      name: listaudio\n      operations:\n      - method: GET\n        name: listaudio\n        description: List audio clips\n        call: fulcrum.listaudio\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /audio.json\n      name: uploadaudio\n      operations:\n      - method: POST\n        name: uploadaudio\n        description: Upload audio\n        call: fulcrum.uploadaudio\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /signatures.json\n      name: listsignatures\n\
  \      operations:\n      - method: GET\n        name: listsignatures\n        description: List signatures\n        call: fulcrum.listsignatures\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /signatures.json\n      name: uploadsignature\n      operations:\n      - method: POST\n        name: uploadsignature\n        description: Upload signature\n        call: fulcrum.uploadsignature\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /choice_lists.json\n      name: listchoicelists\n      operations:\n      - method: GET\n        name: listchoicelists\n        description: List choice lists\n        call: fulcrum.listchoicelists\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /choice_lists.json\n      name: createchoicelist\n      operations:\n      - method: POST\n        name: createchoicelist\n        description: Create choice list\n        call: fulcrum.createchoicelist\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /choice_lists/{id}.json\n      name: getchoicelist\n      operations:\n      - method: GET\n        name: getchoicelist\n        description: Get choice list\n        call: fulcrum.getchoicelist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /choice_lists/{id}.json\n      name: updatechoicelist\n      operations:\n      - method: PUT\n        name: updatechoicelist\n        description: Update choice list\n        call: fulcrum.updatechoicelist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /choice_lists/{id}.json\n      name: deletechoicelist\n      operations:\n      - method: DELETE\n        name: deletechoicelist\n        description: Delete choice list\n        call: fulcrum.deletechoicelist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /classification_sets.json\n      name: listclassificationsets\n\
  \      operations:\n      - method: GET\n        name: listclassificationsets\n        description: List classification sets\n        call: fulcrum.listclassificationsets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /classification_sets.json\n      name: createclassificationset\n      operations:\n      - method: POST\n        name: createclassificationset\n        description: Create classification set\n        call: fulcrum.createclassificationset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /classification_sets/{id}.json\n      name: getclassificationset\n      operations:\n      - method: GET\n        name: getclassificationset\n        description: Get classification set\n        call: fulcrum.getclassificationset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /classification_sets/{id}.json\n      name: updateclassificationset\n      operations:\n      - method:\
  \ PUT\n        name: updateclassificationset\n        description: Update classification set\n        call: fulcrum.updateclassificationset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /classification_sets/{id}.json\n      name: deleteclassificationset\n      operations:\n      - method: DELETE\n        name: deleteclassificationset\n        description: Delete classification set\n        call: fulcrum.deleteclassificationset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects.json\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: List projects\n        call: fulcrum.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects.json\n      name: createproject\n      operations:\n      - method: POST\n        name: createproject\n        description: Create project\n        call: fulcrum.createproject\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{id}.json\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Get project\n        call: fulcrum.getproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{id}.json\n      name: updateproject\n      operations:\n      - method: PUT\n        name: updateproject\n        description: Update project\n        call: fulcrum.updateproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{id}.json\n      name: deleteproject\n      operations:\n      - method: DELETE\n        name: deleteproject\n        description: Delete project\n        call: fulcrum.deleteproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /layers.json\n      name: listlayers\n      operations:\n      - method: GET\n        name:\
  \ listlayers\n        description: List layers\n        call: fulcrum.listlayers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /layers.json\n      name: createlayer\n      operations:\n      - method: POST\n        name: createlayer\n        description: Create layer\n        call: fulcrum.createlayer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /layers/{id}.json\n      name: getlayer\n      operations:\n      - method: GET\n        name: getlayer\n        description: Get layer\n        call: fulcrum.getlayer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /layers/{id}.json\n      name: updatelayer\n      operations:\n      - method: PUT\n        name: updatelayer\n        description: Update layer\n        call: fulcrum.updatelayer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /layers/{id}.json\n      name: deletelayer\n  \
  \    operations:\n      - method: DELETE\n        name: deletelayer\n        description: Delete layer\n        call: fulcrum.deletelayer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /memberships.json\n      name: listmemberships\n      operations:\n      - method: GET\n        name: listmemberships\n        description: List memberships\n        call: fulcrum.listmemberships\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /memberships/{id}.json\n      name: updatemembership\n      operations:\n      - method: PUT\n        name: updatemembership\n        description: Update membership\n        call: fulcrum.updatemembership\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles.json\n      name: listroles\n      operations:\n      - method: GET\n        name: listroles\n        description: List roles\n        call: fulcrum.listroles\n        outputParameters:\n     \
  \   - type: object\n          mapping: $.\n    - path: /roles.json\n      name: createrole\n      operations:\n      - method: POST\n        name: createrole\n        description: Create role\n        call: fulcrum.createrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles/{id}.json\n      name: getrole\n      operations:\n      - method: GET\n        name: getrole\n        description: Get role\n        call: fulcrum.getrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles/{id}.json\n      name: updaterole\n      operations:\n      - method: PUT\n        name: updaterole\n        description: Update role\n        call: fulcrum.updaterole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles/{id}.json\n      name: deleterole\n      operations:\n      - method: DELETE\n        name: deleterole\n        description: Delete role\n        call: fulcrum.deleterole\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks.json\n      name: listwebhooks\n      operations:\n      - method: GET\n        name: listwebhooks\n        description: List webhooks\n        call: fulcrum.listwebhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks.json\n      name: createwebhook\n      operations:\n      - method: POST\n        name: createwebhook\n        description: Create webhook\n        call: fulcrum.createwebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{id}.json\n      name: getwebhook\n      operations:\n      - method: GET\n        name: getwebhook\n        description: Get webhook\n        call: fulcrum.getwebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{id}.json\n      name: updatewebhook\n      operations:\n      - method: PUT\n        name: updatewebhook\n\
  \        description: Update webhook\n        call: fulcrum.updatewebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{id}.json\n      name: deletewebhook\n      operations:\n      - method: DELETE\n        name: deletewebhook\n        description: Delete webhook\n        call: fulcrum.deletewebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /changesets.json\n      name: listchangesets\n      operations:\n      - method: GET\n        name: listchangesets\n        description: List changesets\n        call: fulcrum.listchangesets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /changesets/{id}.json\n      name: getchangeset\n      operations:\n      - method: GET\n        name: getchangeset\n        description: Get changeset\n        call: fulcrum.getchangeset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /query\n\
  \      name: executequery\n      operations:\n      - method: GET\n        name: executequery\n        description: Execute SQL query\n        call: fulcrum.executequery\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fulcrum-mcp\n    transport: http\n    description: MCP adapter for Fulcrum API for AI agent use.\n    tools:\n    - name: listforms\n      description: List forms\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fulcrum.listforms\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createform\n      description: Create form\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fulcrum.createform\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getform\n      description: Get form\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: fulcrum.getform\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateform\n      description: Update form\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: fulcrum.updateform\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteform\n      description: Delete form\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: fulcrum.deleteform\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrecords\n      description: List records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fulcrum.listrecords\n      with:\n        form_id: tools.form_id\n        project_id: tools.project_id\n        assigned_to_id: tools.assigned_to_id\n        status: tools.status\n        bounding_box: tools.bounding_box\n\
  \        per_page: tools.per_page\n        page: tools.page\n      inputParameters:\n      - name: form_id\n        type: string\n        description: Filter by form (app) identifier\n      - name: project_id\n        type: string\n        description: Filter by project identifier\n      - name: assigned_to_id\n        type: string\n        description: Filter by assignment\n      - name: status\n        type: string\n        description: Filter by record status\n      - name: bounding_box\n        type: string\n        description: Comma-separated south,west,north,east bounding box\n      - name: per_page\n        type: integer\n        description: per_page\n      - name: page\n        type: integer\n        description: page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrecord\n      description: Create record\n      hints:\n        readOnly: f\n\n# --- truncated at 32 KB (44 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/fulcrum/refs/heads/main/capabilities/fulcrum-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fulcrum/refs/heads/main/capabilities/fulcrum-capability.yaml
tags:
- Fulcrum
- API
tools:
- description: List forms
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listforms
- description: Create form
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createform
- description: Get form
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getform
- description: Update form
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateform
- description: Delete form
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteform
- description: List records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrecords
- description: Create record
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrecord
- description: Get record
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrecord
- description: Update record
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updaterecord
- description: Delete record
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterecord
- description: List photos
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listphotos
- description: Upload photo
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadphoto
- description: Get photo metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getphoto
- description: Download photo
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloadphoto
- description: List videos
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvideos
- description: Upload video
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadvideo
- description: List audio clips
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaudio
- description: Upload audio
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadaudio
- description: List signatures
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsignatures
- description: Upload signature
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadsignature
- description: List choice lists
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchoicelists
- description: Create choice list
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchoicelist
- description: Get choice list
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchoicelist
- description: Update choice list
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatechoicelist
- description: Delete choice list
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletechoicelist
- description: List classification sets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclassificationsets
- description: Create classification set
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createclassificationset
- description: Get classification set
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclassificationset
- description: Update classification set
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateclassificationset
- description: Delete classification set
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteclassificationset
- description: List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Create project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: Get project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Update project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateproject
- description: Delete project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproject
- description: List layers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlayers
- description: Create layer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlayer
- description: Get layer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlayer
- description: Update layer
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatelayer
- description: Delete layer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelayer
- description: List memberships
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmemberships
- description: Update membership
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatemembership
- description: List roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroles
- description: Create role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrole
- description: Get role
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrole
- description: Update role
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updaterole
- description: Delete role
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterole
- description: List webhooks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwebhooks
- description: Create webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwebhook
- description: Get webhook
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwebhook
- description: Update webhook
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatewebhook
- description: Delete webhook
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletewebhook
- description: List changesets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchangesets
- description: Get changeset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchangeset
- description: Execute SQL query
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: executequery
---
