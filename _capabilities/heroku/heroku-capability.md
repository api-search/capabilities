---
categories: []
consumed_apis: []
description: The Heroku Platform API enables programmatic access to Heroku's deployment platform. Manage apps, dynos, add-ons, config vars, domains, pipelines, releases, and other platform resources.
layout: capability
name: Heroku Platform API
operations:
- description: List apps
  method: GET
  name: listapps
  path: /apps
- description: Create an app
  method: POST
  name: createapp
  path: /apps
- description: Get app info
  method: GET
  name: getapp
  path: /apps/{app_id_or_name}
- description: Update an app
  method: PATCH
  name: updateapp
  path: /apps/{app_id_or_name}
- description: Delete an app
  method: DELETE
  name: deleteapp
  path: /apps/{app_id_or_name}
- description: List dynos
  method: GET
  name: listdynos
  path: /apps/{app_id_or_name}/dynos
- description: Create a dyno
  method: POST
  name: createdyno
  path: /apps/{app_id_or_name}/dynos
- description: Get dyno info
  method: GET
  name: getdyno
  path: /apps/{app_id_or_name}/dynos/{dyno_id_or_name}
- description: Stop a dyno
  method: POST
  name: stopdyno
  path: /apps/{app_id_or_name}/dynos/{dyno_id_or_name}/actions/stop
- description: Restart all dynos
  method: POST
  name: restartalldynos
  path: /apps/{app_id_or_name}/dynos/actions/restart-all
- description: Get config vars
  method: GET
  name: getconfigvars
  path: /apps/{app_id_or_name}/config-vars
- description: Update config vars
  method: PATCH
  name: updateconfigvars
  path: /apps/{app_id_or_name}/config-vars
- description: List add-ons for an app
  method: GET
  name: listaddons
  path: /apps/{app_id_or_name}/addons
- description: Create an add-on
  method: POST
  name: createaddon
  path: /apps/{app_id_or_name}/addons
- description: Get add-on info
  method: GET
  name: getaddon
  path: /apps/{app_id_or_name}/addons/{addon_id_or_name}
- description: Delete an add-on
  method: DELETE
  name: deleteaddon
  path: /apps/{app_id_or_name}/addons/{addon_id_or_name}
- description: List domains
  method: GET
  name: listdomains
  path: /apps/{app_id_or_name}/domains
- description: Create a domain
  method: POST
  name: createdomain
  path: /apps/{app_id_or_name}/domains
- description: Get domain info
  method: GET
  name: getdomain
  path: /apps/{app_id_or_name}/domains/{domain_id_or_hostname}
- description: Delete a domain
  method: DELETE
  name: deletedomain
  path: /apps/{app_id_or_name}/domains/{domain_id_or_hostname}
- description: List formation
  method: GET
  name: listformation
  path: /apps/{app_id_or_name}/formation
- description: Batch update formation
  method: PATCH
  name: batchupdateformation
  path: /apps/{app_id_or_name}/formation
- description: Update a process type
  method: PATCH
  name: updateformation
  path: /apps/{app_id_or_name}/formation/{formation_id_or_type}
- description: List releases
  method: GET
  name: listreleases
  path: /apps/{app_id_or_name}/releases
- description: Create a release (rollback)
  method: POST
  name: createrelease
  path: /apps/{app_id_or_name}/releases
- description: Get release info
  method: GET
  name: getrelease
  path: /apps/{app_id_or_name}/releases/{release_id_or_version}
- description: List builds
  method: GET
  name: listbuilds
  path: /apps/{app_id_or_name}/builds
- description: Create a build
  method: POST
  name: createbuild
  path: /apps/{app_id_or_name}/builds
- description: Get build info
  method: GET
  name: getbuild
  path: /apps/{app_id_or_name}/builds/{build_id}
- description: Create a log session
  method: POST
  name: createlogsession
  path: /apps/{app_id_or_name}/log-sessions
- description: List pipelines
  method: GET
  name: listpipelines
  path: /pipelines
- description: Create a pipeline
  method: POST
  name: createpipeline
  path: /pipelines
- description: Get pipeline info
  method: GET
  name: getpipeline
  path: /pipelines/{pipeline_id}
- description: Update a pipeline
  method: PATCH
  name: updatepipeline
  path: /pipelines/{pipeline_id}
- description: Delete a pipeline
  method: DELETE
  name: deletepipeline
  path: /pipelines/{pipeline_id}
- description: List pipeline couplings
  method: GET
  name: listpipelinecouplings
  path: /pipelines/{pipeline_id}/pipeline-couplings
- description: Create a pipeline coupling
  method: POST
  name: createpipelinecoupling
  path: /pipeline-couplings
- description: Get account info
  method: GET
  name: getaccount
  path: /account
- description: Update account
  method: PATCH
  name: updateaccount
  path: /account
- description: List regions
  method: GET
  name: listregions
  path: /regions
- description: List stacks
  method: GET
  name: liststacks
  path: /stacks
- description: List collaborators
  method: GET
  name: listcollaborators
  path: /apps/{app_id_or_name}/collaborators
- description: Create a collaborator
  method: POST
  name: createcollaborator
  path: /apps/{app_id_or_name}/collaborators
- description: Delete a collaborator
  method: DELETE
  name: deletecollaborator
  path: /apps/{app_id_or_name}/collaborators/{collaborator_email_or_id}
personas: []
provider_name: Heroku
provider_slug: heroku
search_terms:
- createbuild
- cloud platform
- getaccount
- liststacks
- list apps
- updateaccount
- api
- list regions
- update a process type
- list add-ons for an app
- list domains
- getdomain
- batch update formation
- list pipelines
- list builds
- create an add-on
- update an app
- get release info
- createaddon
- heroku
- getapp
- create a collaborator
- delete a collaborator
- stop a dyno
- getbuild
- listapps
- update config vars
- list pipeline couplings
- listdomains
- list dynos
- create an app
- getdyno
- create a log session
- getaddon
- get app info
- listregions
- updateformation
- application deployment
- listdynos
- list formation
- delete an add-on
- createcollaborator
- batchupdateformation
- listbuilds
- get pipeline info
- create a domain
- deletepipeline
- updatepipeline
- listpipelinecouplings
- delete a domain
- get config vars
- delete a pipeline
- stopdyno
- createpipeline
- createdyno
- getrelease
- update account
- list collaborators
- createrelease
- createdomain
- restart all dynos
- devops
- deletecollaborator
- create a dyno
- deletedomain
- createlogsession
- get add-on info
- restartalldynos
- listaddons
- paas
- getconfigvars
- deleteaddon
- get account info
- list releases
- create a build
- get dyno info
- updateapp
- create a pipeline coupling
- createpipelinecoupling
- create a release (rollback)
- get domain info
- listcollaborators
- deleteapp
- listpipelines
- updateconfigvars
- createapp
- delete an app
- update a pipeline
- get build info
- create a pipeline
- getpipeline
- listreleases
- list stacks
- listformation
slug: heroku-capability
source_filename: heroku-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Heroku Platform API\n  description: The Heroku Platform API enables programmatic access to Heroku's deployment platform. Manage apps, dynos, add-ons,\n    config vars, domains, pipelines, releases, and other platform resources.\n  tags:\n  - Heroku\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: heroku\n    baseUri: https://api.heroku.com\n    description: Heroku Platform API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{HEROKU_TOKEN}}'\n    resources:\n    - name: apps\n      path: /apps\n      operations:\n      - name: listapps\n        method: GET\n        description: List apps\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapp\n        method: POST\n        description: Create an app\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name\n      path: /apps/{app_id_or_name}\n      operations:\n      - name: getapp\n        method: GET\n        description: Get app info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapp\n        method: PATCH\n        description: Update an app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapp\n        method: DELETE\n        description: Delete an app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-dynos\n      path: /apps/{app_id_or_name}/dynos\n      operations:\n      - name: listdynos\n        method: GET\n        description: List dynos\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdyno\n        method: POST\n        description: Create a dyno\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-dynos-dyno-id-or-name\n      path: /apps/{app_id_or_name}/dynos/{dyno_id_or_name}\n      operations:\n      - name: getdyno\n        method: GET\n        description: Get dyno info\n        inputParameters:\n        - name: dyno_id_or_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-dynos-dyno-id-or-name-action\n      path: /apps/{app_id_or_name}/dynos/{dyno_id_or_name}/actions/stop\n      operations:\n      - name: stopdyno\n        method: POST\n        description: Stop\
  \ a dyno\n        inputParameters:\n        - name: dyno_id_or_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-dynos-actions-restart-all\n      path: /apps/{app_id_or_name}/dynos/actions/restart-all\n      operations:\n      - name: restartalldynos\n        method: POST\n        description: Restart all dynos\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-config-vars\n      path: /apps/{app_id_or_name}/config-vars\n      operations:\n      - name: getconfigvars\n        method: GET\n        description: Get config vars\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateconfigvars\n        method:\
  \ PATCH\n        description: Update config vars\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-addons\n      path: /apps/{app_id_or_name}/addons\n      operations:\n      - name: listaddons\n        method: GET\n        description: List add-ons for an app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createaddon\n        method: POST\n        description: Create an add-on\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-addons-addon-id-or-name\n      path: /apps/{app_id_or_name}/addons/{addon_id_or_name}\n      operations:\n      - name: getaddon\n        method: GET\n        description: Get add-on info\n        inputParameters:\n        - name: addon_id_or_name\n    \
  \      in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteaddon\n        method: DELETE\n        description: Delete an add-on\n        inputParameters:\n        - name: addon_id_or_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-domains\n      path: /apps/{app_id_or_name}/domains\n      operations:\n      - name: listdomains\n        method: GET\n        description: List domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdomain\n        method: POST\n        description: Create a domain\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-domains-domain-id-or-hostnam\n      path: /apps/{app_id_or_name}/domains/{domain_id_or_hostname}\n      operations:\n      - name: getdomain\n        method: GET\n        description: Get domain info\n        inputParameters:\n        - name: domain_id_or_hostname\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedomain\n        method: DELETE\n        description: Delete a domain\n        inputParameters:\n        - name: domain_id_or_hostname\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-formation\n      path: /apps/{app_id_or_name}/formation\n\
  \      operations:\n      - name: listformation\n        method: GET\n        description: List formation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: batchupdateformation\n        method: PATCH\n        description: Batch update formation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-formation-formation-id-or-ty\n      path: /apps/{app_id_or_name}/formation/{formation_id_or_type}\n      operations:\n      - name: updateformation\n        method: PATCH\n        description: Update a process type\n        inputParameters:\n        - name: formation_id_or_type\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-releases\n\
  \      path: /apps/{app_id_or_name}/releases\n      operations:\n      - name: listreleases\n        method: GET\n        description: List releases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrelease\n        method: POST\n        description: Create a release (rollback)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-releases-release-id-or-versi\n      path: /apps/{app_id_or_name}/releases/{release_id_or_version}\n      operations:\n      - name: getrelease\n        method: GET\n        description: Get release info\n        inputParameters:\n        - name: release_id_or_version\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: apps-app-id-or-name-builds\n      path: /apps/{app_id_or_name}/builds\n      operations:\n      - name: listbuilds\n        method: GET\n        description: List builds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbuild\n        method: POST\n        description: Create a build\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-builds-build-id\n      path: /apps/{app_id_or_name}/builds/{build_id}\n      operations:\n      - name: getbuild\n        method: GET\n        description: Get build info\n        inputParameters:\n        - name: build_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-log-sessions\n\
  \      path: /apps/{app_id_or_name}/log-sessions\n      operations:\n      - name: createlogsession\n        method: POST\n        description: Create a log session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipelines\n      path: /pipelines\n      operations:\n      - name: listpipelines\n        method: GET\n        description: List pipelines\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpipeline\n        method: POST\n        description: Create a pipeline\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipelines-pipeline-id\n      path: /pipelines/{pipeline_id}\n      operations:\n      - name: getpipeline\n        method: GET\n        description: Get pipeline info\n        inputParameters:\n \
  \       - name: pipeline_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepipeline\n        method: PATCH\n        description: Update a pipeline\n        inputParameters:\n        - name: pipeline_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepipeline\n        method: DELETE\n        description: Delete a pipeline\n        inputParameters:\n        - name: pipeline_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipelines-pipeline-id-pipeline-couplings\n      path: /pipelines/{pipeline_id}/pipeline-couplings\n\
  \      operations:\n      - name: listpipelinecouplings\n        method: GET\n        description: List pipeline couplings\n        inputParameters:\n        - name: pipeline_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipeline-couplings\n      path: /pipeline-couplings\n      operations:\n      - name: createpipelinecoupling\n        method: POST\n        description: Create a pipeline coupling\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account\n      path: /account\n      operations:\n      - name: getaccount\n        method: GET\n        description: Get account info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateaccount\n\
  \        method: PATCH\n        description: Update account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: regions\n      path: /regions\n      operations:\n      - name: listregions\n        method: GET\n        description: List regions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stacks\n      path: /stacks\n      operations:\n      - name: liststacks\n        method: GET\n        description: List stacks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-collaborators\n      path: /apps/{app_id_or_name}/collaborators\n      operations:\n      - name: listcollaborators\n        method: GET\n        description: List collaborators\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n      - name: createcollaborator\n        method: POST\n        description: Create a collaborator\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-app-id-or-name-collaborators-collaborator-e\n      path: /apps/{app_id_or_name}/collaborators/{collaborator_email_or_id}\n      operations:\n      - name: deletecollaborator\n        method: DELETE\n        description: Delete a collaborator\n        inputParameters:\n        - name: collaborator_email_or_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: heroku-rest\n    description: REST adapter for Heroku Platform API.\n    resources:\n    - path: /apps\n      name: listapps\n\
  \      operations:\n      - method: GET\n        name: listapps\n        description: List apps\n        call: heroku.listapps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps\n      name: createapp\n      operations:\n      - method: POST\n        name: createapp\n        description: Create an app\n        call: heroku.createapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}\n      name: getapp\n      operations:\n      - method: GET\n        name: getapp\n        description: Get app info\n        call: heroku.getapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}\n      name: updateapp\n      operations:\n      - method: PATCH\n        name: updateapp\n        description: Update an app\n        call: heroku.updateapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}\n\
  \      name: deleteapp\n      operations:\n      - method: DELETE\n        name: deleteapp\n        description: Delete an app\n        call: heroku.deleteapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/dynos\n      name: listdynos\n      operations:\n      - method: GET\n        name: listdynos\n        description: List dynos\n        call: heroku.listdynos\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/dynos\n      name: createdyno\n      operations:\n      - method: POST\n        name: createdyno\n        description: Create a dyno\n        call: heroku.createdyno\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/dynos/{dyno_id_or_name}\n      name: getdyno\n      operations:\n      - method: GET\n        name: getdyno\n        description: Get dyno info\n        call: heroku.getdyno\n        with:\n\
  \          dyno_id_or_name: rest.dyno_id_or_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/dynos/{dyno_id_or_name}/actions/stop\n      name: stopdyno\n      operations:\n      - method: POST\n        name: stopdyno\n        description: Stop a dyno\n        call: heroku.stopdyno\n        with:\n          dyno_id_or_name: rest.dyno_id_or_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/dynos/actions/restart-all\n      name: restartalldynos\n      operations:\n      - method: POST\n        name: restartalldynos\n        description: Restart all dynos\n        call: heroku.restartalldynos\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/config-vars\n      name: getconfigvars\n      operations:\n      - method: GET\n        name: getconfigvars\n        description: Get config vars\n        call: heroku.getconfigvars\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/config-vars\n      name: updateconfigvars\n      operations:\n      - method: PATCH\n        name: updateconfigvars\n        description: Update config vars\n        call: heroku.updateconfigvars\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/addons\n      name: listaddons\n      operations:\n      - method: GET\n        name: listaddons\n        description: List add-ons for an app\n        call: heroku.listaddons\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/addons\n      name: createaddon\n      operations:\n      - method: POST\n        name: createaddon\n        description: Create an add-on\n        call: heroku.createaddon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/addons/{addon_id_or_name}\n\
  \      name: getaddon\n      operations:\n      - method: GET\n        name: getaddon\n        description: Get add-on info\n        call: heroku.getaddon\n        with:\n          addon_id_or_name: rest.addon_id_or_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/addons/{addon_id_or_name}\n      name: deleteaddon\n      operations:\n      - method: DELETE\n        name: deleteaddon\n        description: Delete an add-on\n        call: heroku.deleteaddon\n        with:\n          addon_id_or_name: rest.addon_id_or_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/domains\n      name: listdomains\n      operations:\n      - method: GET\n        name: listdomains\n        description: List domains\n        call: heroku.listdomains\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/domains\n      name:\
  \ createdomain\n      operations:\n      - method: POST\n        name: createdomain\n        description: Create a domain\n        call: heroku.createdomain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/domains/{domain_id_or_hostname}\n      name: getdomain\n      operations:\n      - method: GET\n        name: getdomain\n        description: Get domain info\n        call: heroku.getdomain\n        with:\n          domain_id_or_hostname: rest.domain_id_or_hostname\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/domains/{domain_id_or_hostname}\n      name: deletedomain\n      operations:\n      - method: DELETE\n        name: deletedomain\n        description: Delete a domain\n        call: heroku.deletedomain\n        with:\n          domain_id_or_hostname: rest.domain_id_or_hostname\n        outputParameters:\n        - type: object\n          mapping: $.\n   \
  \ - path: /apps/{app_id_or_name}/formation\n      name: listformation\n      operations:\n      - method: GET\n        name: listformation\n        description: List formation\n        call: heroku.listformation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/formation\n      name: batchupdateformation\n      operations:\n      - method: PATCH\n        name: batchupdateformation\n        description: Batch update formation\n        call: heroku.batchupdateformation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/formation/{formation_id_or_type}\n      name: updateformation\n      operations:\n      - method: PATCH\n        name: updateformation\n        description: Update a process type\n        call: heroku.updateformation\n        with:\n          formation_id_or_type: rest.formation_id_or_type\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /apps/{app_id_or_name}/releases\n      name: listreleases\n      operations:\n      - method: GET\n        name: listreleases\n        description: List releases\n        call: heroku.listreleases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/releases\n      name: createrelease\n      operations:\n      - method: POST\n        name: createrelease\n        description: Create a release (rollback)\n        call: heroku.createrelease\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/releases/{release_id_or_version}\n      name: getrelease\n      operations:\n      - method: GET\n        name: getrelease\n        description: Get release info\n        call: heroku.getrelease\n        with:\n          release_id_or_version: rest.release_id_or_version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/builds\n\
  \      name: listbuilds\n      operations:\n      - method: GET\n        name: listbuilds\n        description: List builds\n        call: heroku.listbuilds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/builds\n      name: createbuild\n      operations:\n      - method: POST\n        name: createbuild\n        description: Create a build\n        call: heroku.createbuild\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/builds/{build_id}\n      name: getbuild\n      operations:\n      - method: GET\n        name: getbuild\n        description: Get build info\n        call: heroku.getbuild\n        with:\n          build_id: rest.build_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/log-sessions\n      name: createlogsession\n      operations:\n      - method: POST\n        name: createlogsession\n  \
  \      description: Create a log session\n        call: heroku.createlogsession\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines\n      name: listpipelines\n      operations:\n      - method: GET\n        name: listpipelines\n        description: List pipelines\n        call: heroku.listpipelines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines\n      name: createpipeline\n      operations:\n      - method: POST\n        name: createpipeline\n        description: Create a pipeline\n        call: heroku.createpipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines/{pipeline_id}\n      name: getpipeline\n      operations:\n      - method: GET\n        name: getpipeline\n        description: Get pipeline info\n        call: heroku.getpipeline\n        with:\n          pipeline_id: rest.pipeline_id\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /pipelines/{pipeline_id}\n      name: updatepipeline\n      operations:\n      - method: PATCH\n        name: updatepipeline\n        description: Update a pipeline\n        call: heroku.updatepipeline\n        with:\n          pipeline_id: rest.pipeline_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines/{pipeline_id}\n      name: deletepipeline\n      operations:\n      - method: DELETE\n        name: deletepipeline\n        description: Delete a pipeline\n        call: heroku.deletepipeline\n        with:\n          pipeline_id: rest.pipeline_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines/{pipeline_id}/pipeline-couplings\n      name: listpipelinecouplings\n      operations:\n      - method: GET\n        name: listpipelinecouplings\n        description: List pipeline couplings\n        call: heroku.listpipelinecouplings\n        with:\n          pipeline_id:\
  \ rest.pipeline_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipeline-couplings\n      name: createpipelinecoupling\n      operations:\n      - method: POST\n        name: createpipelinecoupling\n        description: Create a pipeline coupling\n        call: heroku.createpipelinecoupling\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account\n      name: getaccount\n      operations:\n      - method: GET\n        name: getaccount\n        description: Get account info\n        call: heroku.getaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account\n      name: updateaccount\n      operations:\n      - method: PATCH\n        name: updateaccount\n        description: Update account\n        call: heroku.updateaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /regions\n      name: listregions\n      operations:\n\
  \      - method: GET\n        name: listregions\n        description: List regions\n        call: heroku.listregions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stacks\n      name: liststacks\n      operations:\n      - method: GET\n        name: liststacks\n        description: List stacks\n        call: heroku.liststacks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/collaborators\n      name: listcollaborators\n      operations:\n      - method: GET\n        name: listcollaborators\n        description: List collaborators\n        call: heroku.listcollaborators\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/collaborators\n      name: createcollaborator\n      operations:\n      - method: POST\n        name: createcollaborator\n        description: Create a collaborator\n        call: heroku.createcollaborator\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{app_id_or_name}/collaborators/{collaborator_email_or_id}\n      name: deletecollaborator\n      operations:\n      - method: DELETE\n        name: deletecollaborator\n        description: Delete a collaborator\n        call: heroku.deletecollaborator\n        with:\n          collaborator_email_or_id: rest.collaborator_email_or_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: heroku-mcp\n    transport: http\n    description: MCP adapter for Heroku Platform API for AI agent use.\n    tools:\n    - name: listapps\n      description: List apps\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: heroku.listapps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapp\n      description: Create an app\n      hints:\n        readOnly: false\n \
  \       destructive: false\n        idempotent: false\n      call: heroku.createapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapp\n      description: Get app info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: heroku.getapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateapp\n      description: Update an app\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: heroku.updateapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteapp\n      description: Delete an app\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: heroku.deleteapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdynos\n      description: List dynos\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: heroku.listdynos\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdyno\n      description: Create a dyno\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: heroku.createdyno\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdyno\n      description: Get dyno info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: heroku.getdyno\n      with:\n        dyno_id_or_name: tools.dyno_id_or_name\n      inputParameters:\n      - name: dyno_id_or_name\n        type: string\n        description: dyno_id_or_name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stopdyno\n      description: Stop a dyno\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: heroku.stopdyno\n\
  \      with:\n        dyno_id_or_name: tools.dyno_id_or_name\n      inputParameters:\n      - name: dyno_id_or_name\n        type: string\n        description: dyno_id_or_name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restartalldynos\n      description: Restart all dynos\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: heroku.restartalldynos\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconfigvars\n      description: Get config vars\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: heroku.getconfigvars\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateconfigvars\n      description: Update config vars\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: heroku.updateconfigvars\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listaddons\n      description: List add-ons for an app\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: heroku.listaddons\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createaddon\n      description: Create an add-on\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: heroku.createaddon\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaddon\n      description: Get add-on info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: heroku.getaddon\n      with:\n        addon_id_or_name: tools.addon_id_or_name\n      inputParameters:\n      - name: addon_id_or_name\n        type: string\n        description: addon_id_or_name\n        required: true\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: deleteaddon\n      description: Delete an add-on\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: heroku.deleteaddon\n      with:\n        addon_id_or_name: tools.addon_id_or_name\n      inputParameters:\n      - name: addon_id_or_name\n        type: string\n        description: addon_id_or_name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdomains\n      description: List domains\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: heroku.listdomains\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdomain\n      description: Create a domain\n      hints:\n        readOnly: false\n        destruc\n\n# --- truncated at 32 KB (40 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/heroku/refs/heads/main/capabilities/heroku-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/heroku/refs/heads/main/capabilities/heroku-capability.yaml
tags:
- Heroku
- API
tools:
- description: List apps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapps
- description: Create an app
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapp
- description: Get app info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapp
- description: Update an app
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateapp
- description: Delete an app
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapp
- description: List dynos
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdynos
- description: Create a dyno
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdyno
- description: Get dyno info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdyno
- description: Stop a dyno
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stopdyno
- description: Restart all dynos
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restartalldynos
- description: Get config vars
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconfigvars
- description: Update config vars
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateconfigvars
- description: List add-ons for an app
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaddons
- description: Create an add-on
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaddon
- description: Get add-on info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaddon
- description: Delete an add-on
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteaddon
- description: List domains
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdomains
- description: Create a domain
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdomain
- description: Get domain info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdomain
- description: Delete a domain
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedomain
- description: List formation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listformation
- description: Batch update formation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: batchupdateformation
- description: Update a process type
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateformation
- description: List releases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreleases
- description: Create a release (rollback)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrelease
- description: Get release info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrelease
- description: List builds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbuilds
- description: Create a build
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbuild
- description: Get build info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbuild
- description: Create a log session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlogsession
- description: List pipelines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpipelines
- description: Create a pipeline
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpipeline
- description: Get pipeline info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpipeline
- description: Update a pipeline
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatepipeline
- description: Delete a pipeline
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepipeline
- description: List pipeline couplings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpipelinecouplings
- description: Create a pipeline coupling
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpipelinecoupling
- description: Get account info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccount
- description: Update account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateaccount
- description: List regions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listregions
- description: List stacks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststacks
- description: List collaborators
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcollaborators
- description: Create a collaborator
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcollaborator
- description: Delete a collaborator
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecollaborator
---
