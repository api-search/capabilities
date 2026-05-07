---
categories: []
consumed_apis: []
description: Nebraska is an update manager.
layout: capability
name: Nebraska
operations:
- description: GitHub OAuth callback (GitHub mode only)
  method: GET
  name: logincb
  path: /login/cb
- description: validate JWT access token (OIDC mode only)
  method: GET
  name: validatetoken
  path: /login/validate_token
- description: GitHub webhook (GitHub mode only)
  method: POST
  name: loginwebhook
  path: /login/webhook
- description: health endpoint
  method: GET
  name: health
  path: /health
- description: get app config
  method: GET
  name: getconfig
  path: /config
- description: omaha endpoint
  method: POST
  name: omaha
  path: /v1/update
- description: get Apps
  method: GET
  name: paginateapps
  path: /api/apps
- description: create app
  method: POST
  name: createapp
  path: /api/apps
- description: get app
  method: GET
  name: getapp
  path: /api/apps/{appIDorProductID}
- description: update app
  method: PUT
  name: updateapp
  path: /api/apps/{appIDorProductID}
- description: delete app
  method: DELETE
  name: deleteapp
  path: /api/apps/{appIDorProductID}
- description: paginate groups of an app
  method: GET
  name: paginategroups
  path: /api/apps/{appIDorProductID}/groups
- description: create group in app
  method: POST
  name: creategroup
  path: /api/apps/{appIDorProductID}/groups
- description: get group given its groupID and appID
  method: GET
  name: getgroup
  path: /api/apps/{appIDorProductID}/groups/{groupID}
- description: update group given its groupID and appID
  method: PUT
  name: updategroup
  path: /api/apps/{appIDorProductID}/groups/{groupID}
- description: delete group given its groupID and appID
  method: DELETE
  name: deletegroup
  path: /api/apps/{appIDorProductID}/groups/{groupID}
- description: get version timeline of a group given its groupID and appID
  method: GET
  name: getgroupversiontimeline
  path: /api/apps/{appIDorProductID}/groups/{groupID}/version_timeline
- description: get status timeline of a group given its groupID and appID
  method: GET
  name: getgroupstatustimeline
  path: /api/apps/{appIDorProductID}/groups/{groupID}/status_timeline
- description: get instance stats of a group given its groupID and appID
  method: GET
  name: getgroupinstancestats
  path: /api/apps/{appIDorProductID}/groups/{groupID}/instances_stats
- description: get version breakdown of a group given its groupID and appID
  method: GET
  name: getgroupversionbreakdown
  path: /api/apps/{appIDorProductID}/groups/{groupID}/version_breakdown
- description: paginate channels of an app
  method: GET
  name: paginatechannels
  path: /api/apps/{appIDorProductID}/channels
- description: create channel
  method: POST
  name: createchannel
  path: /api/apps/{appIDorProductID}/channels
- description: get channel by id
  method: GET
  name: getchannel
  path: /api/apps/{appIDorProductID}/channels/{channelID}
- description: update channel by id
  method: PUT
  name: updatechannel
  path: /api/apps/{appIDorProductID}/channels/{channelID}
- description: delete channel by id
  method: DELETE
  name: deletechannel
  path: /api/apps/{appIDorProductID}/channels/{channelID}
- description: paginate floor packages of a channel
  method: GET
  name: paginatechannelfloors
  path: /api/channels/{channelID}/floors
- description: Create or update a floor package relationship (idempotent operation)
  method: PUT
  name: setchannelfloor
  path: /api/channels/{channelID}/floors/{packageID}
- description: remove package as floor for a channel
  method: DELETE
  name: removechannelfloor
  path: /api/channels/{channelID}/floors/{packageID}
- description: paginate packages of an app
  method: GET
  name: paginatepackages
  path: /api/apps/{appIDorProductID}/packages
- description: create package
  method: POST
  name: createpackage
  path: /api/apps/{appIDorProductID}/packages
- description: get package given its packageID and appID
  method: GET
  name: getpackage
  path: /api/apps/{appIDorProductID}/packages/{packageID}
- description: update package given its packageID and appID
  method: PUT
  name: updatepackage
  path: /api/apps/{appIDorProductID}/packages/{packageID}
- description: delete package given its packageID and appID
  method: DELETE
  name: deletepackage
  path: /api/apps/{appIDorProductID}/packages/{packageID}
- description: get all channels where a package is marked as a floor
  method: GET
  name: getpackagefloorchannels
  path: /api/apps/{appIDorProductID}/packages/{packageID}/floor-channels
- description: get instances of a group given its groupID and appID
  method: GET
  name: getgroupinstances
  path: /api/apps/{appIDorProductID}/groups/{groupID}/instances
- description: get instance count of a group given its groupID and appID
  method: GET
  name: getgroupinstancescount
  path: /api/apps/{appIDorProductID}/groups/{groupID}/instancescount
- description: get instance of a group given its groupID and appID
  method: GET
  name: getinstance
  path: /api/apps/{appIDorProductID}/groups/{groupID}/instances/{instanceID}
- description: get instance status_history.
  method: GET
  name: getinstancestatushistory
  path: /api/apps/{appIDorProductID}/groups/{groupID}/instances/{instanceID}/status_history
- description: update instance
  method: PUT
  name: updateinstance
  path: /api/instances/{instanceID}
- description: paginate activity
  method: GET
  name: paginateactivity
  path: /api/activity
personas: []
provider_name: Flatcar Container Linux
provider_slug: flatcar-container-linux
search_terms:
- get instance status_history.
- get apps
- paginateapps
- paginate channels of an app
- containers
- api
- update app
- getgroup
- getgroupinstances
- linux
- container
- health endpoint
- get instance count of a group given its groupid and appid
- create channel
- paginate packages of an app
- update group given its groupid and appid
- getapp
- paginategroups
- updatechannel
- update channel by id
- getgroupinstancestats
- get all channels where a package is marked as a floor
- deletegroup
- delete group given its groupid and appid
- getinstancestatushistory
- omaha endpoint
- creategroup
- get instance stats of a group given its groupid and appid
- paginate activity
- cloud native
- omaha
- health
- create group in app
- get version timeline of a group given its groupid and appid
- logincb
- update instance
- removechannelfloor
- create package
- create app
- paginatechannelfloors
- deletechannel
- getgroupstatustimeline
- paginate groups of an app
- getgroupversiontimeline
- remove package as floor for a channel
- get app
- getconfig
- create or update a floor package relationship (idempotent operation)
- github oauth callback (github mode only)
- getinstance
- validatetoken
- getgroupversionbreakdown
- get package given its packageid and appid
- get group given its groupid and appid
- operating system
- get app config
- get channel by id
- getchannel
- delete app
- createpackage
- updatepackage
- createchannel
- validate jwt access token (oidc mode only)
- get instance of a group given its groupid and appid
- updateinstance
- update package given its packageid and appid
- paginateactivity
- flatcar
- get status timeline of a group given its groupid and appid
- getpackage
- incubating
- deletepackage
- updateapp
- getpackagefloorchannels
- delete package given its packageid and appid
- updategroup
- getgroupinstancescount
- paginatechannels
- github webhook (github mode only)
- deleteapp
- paginatepackages
- createapp
- immutable infrastructure
- delete channel by id
- get instances of a group given its groupid and appid
- setchannelfloor
- paginate floor packages of a channel
- get version breakdown of a group given its groupid and appid
- loginwebhook
slug: flatcar-container-linux-capability
source_filename: flatcar-container-linux-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Nebraska\n  description: Nebraska is an update manager.\n  tags:\n  - Flatcar\n  - Container\n  - Linux\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: flatcar-container-linux\n    baseUri: https://api.example.com\n    description: Nebraska HTTP API.\n    authentication:\n      type: bearer\n      token: '{{FLATCAR_CONTAINER_LINUX_TOKEN}}'\n    resources:\n    - name: login-cb\n      path: /login/cb\n      operations:\n      - name: logincb\n        method: GET\n        description: GitHub OAuth callback (GitHub mode only)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: login-validate-token\n      path: /login/validate_token\n      operations:\n      - name: validatetoken\n        method: GET\n        description: validate JWT access token (OIDC mode only)\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: login-webhook\n      path: /login/webhook\n      operations:\n      - name: loginwebhook\n        method: POST\n        description: GitHub webhook (GitHub mode only)\n        inputParameters:\n        - name: X-Hub-Signature\n          in: header\n          type: string\n          required: true\n        - name: X-Github-Event\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /health\n      operations:\n      - name: health\n        method: GET\n        description: health endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: config\n      path: /config\n      operations:\n      - name: getconfig\n\
  \        method: GET\n        description: get app config\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-update\n      path: /v1/update\n      operations:\n      - name: omaha\n        method: POST\n        description: omaha endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-apps\n      path: /api/apps\n      operations:\n      - name: paginateapps\n        method: GET\n        description: get Apps\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n        - name: perpage\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapp\n        method: POST\n        description: create app\n        inputParameters:\n\
  \        - name: clone_from\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-apps-appidorproductid\n      path: /api/apps/{appIDorProductID}\n      operations:\n      - name: getapp\n        method: GET\n        description: get app\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapp\n        method: PUT\n        description: update app\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapp\n       \
  \ method: DELETE\n        description: delete app\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-apps-appidorproductid-groups\n      path: /api/apps/{appIDorProductID}/groups\n      operations:\n      - name: paginategroups\n        method: GET\n        description: paginate groups of an app\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: page\n          in: query\n          type: integer\n        - name: perpage\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method: POST\n        description: create group\
  \ in app\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-apps-appidorproductid-groups-groupid\n      path: /api/apps/{appIDorProductID}/groups/{groupID}\n      operations:\n      - name: getgroup\n        method: GET\n        description: get group given its groupID and appID\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: groupID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategroup\n        method: PUT\n        description: update group given its groupID and appID\n        inputParameters:\n      \
  \  - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: groupID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegroup\n        method: DELETE\n        description: delete group given its groupID and appID\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: groupID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-apps-appidorproductid-groups-groupid-version\n      path: /api/apps/{appIDorProductID}/groups/{groupID}/version_timeline\n      operations:\n      - name: getgroupversiontimeline\n        method: GET\n\
  \        description: get version timeline of a group given its groupID and appID\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: groupID\n          in: path\n          type: string\n          required: true\n        - name: duration\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-apps-appidorproductid-groups-groupid-status-\n      path: /api/apps/{appIDorProductID}/groups/{groupID}/status_timeline\n      operations:\n      - name: getgroupstatustimeline\n        method: GET\n        description: get status timeline of a group given its groupID and appID\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: groupID\n          in: path\n\
  \          type: string\n          required: true\n        - name: duration\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-apps-appidorproductid-groups-groupid-instanc\n      path: /api/apps/{appIDorProductID}/groups/{groupID}/instances_stats\n      operations:\n      - name: getgroupinstancestats\n        method: GET\n        description: get instance stats of a group given its groupID and appID\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: groupID\n          in: path\n          type: string\n          required: true\n        - name: duration\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n    - name: api-apps-appidorproductid-groups-groupid-version\n      path: /api/apps/{appIDorProductID}/groups/{groupID}/version_breakdown\n      operations:\n      - name: getgroupversionbreakdown\n        method: GET\n        description: get version breakdown of a group given its groupID and appID\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: groupID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-apps-appidorproductid-channels\n      path: /api/apps/{appIDorProductID}/channels\n      operations:\n      - name: paginatechannels\n        method: GET\n        description: paginate channels of an app\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n\
  \          required: true\n        - name: page\n          in: query\n          type: integer\n        - name: perpage\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createchannel\n        method: POST\n        description: create channel\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-apps-appidorproductid-channels-channelid\n      path: /api/apps/{appIDorProductID}/channels/{channelID}\n      operations:\n      - name: getchannel\n        method: GET\n        description: get channel by id\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n    \
  \    - name: channelID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatechannel\n        method: PUT\n        description: update channel by id\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: channelID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletechannel\n        method: DELETE\n        description: delete channel by id\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: channelID\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-channels-channelid-floors\n      path: /api/channels/{channelID}/floors\n      operations:\n      - name: paginatechannelfloors\n        method: GET\n        description: paginate floor packages of a channel\n        inputParameters:\n        - name: channelID\n          in: path\n          type: string\n          required: true\n        - name: page\n          in: query\n          type: integer\n        - name: perpage\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-channels-channelid-floors-packageid\n      path: /api/channels/{channelID}/floors/{packageID}\n      operations:\n      - name: setchannelfloor\n        method: PUT\n        description: Create or update a floor package relationship (idempotent operation)\n        inputParameters:\n\
  \        - name: channelID\n          in: path\n          type: string\n          required: true\n        - name: packageID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removechannelfloor\n        method: DELETE\n        description: remove package as floor for a channel\n        inputParameters:\n        - name: channelID\n          in: path\n          type: string\n          required: true\n        - name: packageID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-apps-appidorproductid-packages\n      path: /api/apps/{appIDorProductID}/packages\n      operations:\n      - name: paginatepackages\n        method: GET\n        description: paginate packages of\
  \ an app\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: page\n          in: query\n          type: integer\n        - name: perpage\n          in: query\n          type: integer\n        - name: searchVersion\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpackage\n        method: POST\n        description: create package\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-apps-appidorproductid-packages-packageid\n      path: /api/apps/{appIDorProductID}/packages/{packageID}\n      operations:\n      - name: getpackage\n      \
  \  method: GET\n        description: get package given its packageID and appID\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: packageID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepackage\n        method: PUT\n        description: update package given its packageID and appID\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: packageID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepackage\n        method: DELETE\n        description: delete package given\
  \ its packageID and appID\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: packageID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-apps-appidorproductid-packages-packageid-flo\n      path: /api/apps/{appIDorProductID}/packages/{packageID}/floor-channels\n      operations:\n      - name: getpackagefloorchannels\n        method: GET\n        description: get all channels where a package is marked as a floor\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: packageID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: api-apps-appidorproductid-groups-groupid-instanc\n      path: /api/apps/{appIDorProductID}/groups/{groupID}/instances\n      operations:\n      - name: getgroupinstances\n        method: GET\n        description: get instances of a group given its groupID and appID\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: groupID\n          in: path\n          type: string\n          required: true\n        - name: status\n          in: query\n          type: integer\n          required: true\n        - name: page\n          in: query\n          type: integer\n        - name: perpage\n          in: query\n          type: integer\n        - name: sortFilter\n          in: query\n          type: string\n        - name: sortOrder\n          in: query\n          type: string\n        - name: searchFilter\n          in: query\n          type: string\n        -\
  \ name: searchValue\n          in: query\n          type: string\n        - name: duration\n          in: query\n          type: string\n          required: true\n        - name: version\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-apps-appidorproductid-groups-groupid-instanc\n      path: /api/apps/{appIDorProductID}/groups/{groupID}/instancescount\n      operations:\n      - name: getgroupinstancescount\n        method: GET\n        description: get instance count of a group given its groupID and appID\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: groupID\n          in: path\n          type: string\n          required: true\n        - name: duration\n          in: query\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-apps-appidorproductid-groups-groupid-instanc\n      path: /api/apps/{appIDorProductID}/groups/{groupID}/instances/{instanceID}\n      operations:\n      - name: getinstance\n        method: GET\n        description: get instance of a group given its groupID and appID\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: groupID\n          in: path\n          type: string\n          required: true\n        - name: instanceID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-apps-appidorproductid-groups-groupid-instanc\n      path: /api/apps/{appIDorProductID}/groups/{groupID}/instances/{instanceID}/status_history\n \
  \     operations:\n      - name: getinstancestatushistory\n        method: GET\n        description: get instance status_history.\n        inputParameters:\n        - name: appIDorProductID\n          in: path\n          type: string\n          required: true\n        - name: groupID\n          in: path\n          type: string\n          required: true\n        - name: instanceID\n          in: path\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-instances-instanceid\n      path: /api/instances/{instanceID}\n      operations:\n      - name: updateinstance\n        method: PUT\n        description: update instance\n        inputParameters:\n        - name: instanceID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-activity\n      path: /api/activity\n      operations:\n      - name: paginateactivity\n        method: GET\n        description: paginate activity\n        inputParameters:\n        - name: appIDorProductID\n          in: query\n          type: string\n        - name: groupID\n          in: query\n          type: string\n        - name: channelID\n          in: query\n          type: string\n        - name: instanceID\n          in: query\n          type: string\n        - name: version\n          in: query\n          type: string\n        - name: severity\n          in: query\n          type: integer\n        - name: start\n          in: query\n          type: string\n          required: true\n        - name: end\n          in: query\n          type: string\n          required: true\n        - name: page\n          in: query\n          type: integer\n        - name: perpage\n   \
  \       in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: flatcar-container-linux-rest\n    description: REST adapter for Nebraska.\n    resources:\n    - path: /login/cb\n      name: logincb\n      operations:\n      - method: GET\n        name: logincb\n        description: GitHub OAuth callback (GitHub mode only)\n        call: flatcar-container-linux.logincb\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /login/validate_token\n      name: validatetoken\n      operations:\n      - method: GET\n        name: validatetoken\n        description: validate JWT access token (OIDC mode only)\n        call: flatcar-container-linux.validatetoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /login/webhook\n      name: loginwebhook\n      operations:\n\
  \      - method: POST\n        name: loginwebhook\n        description: GitHub webhook (GitHub mode only)\n        call: flatcar-container-linux.loginwebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /health\n      name: health\n      operations:\n      - method: GET\n        name: health\n        description: health endpoint\n        call: flatcar-container-linux.health\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /config\n      name: getconfig\n      operations:\n      - method: GET\n        name: getconfig\n        description: get app config\n        call: flatcar-container-linux.getconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/update\n      name: omaha\n      operations:\n      - method: POST\n        name: omaha\n        description: omaha endpoint\n        call: flatcar-container-linux.omaha\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /api/apps\n      name: paginateapps\n      operations:\n      - method: GET\n        name: paginateapps\n        description: get Apps\n        call: flatcar-container-linux.paginateapps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps\n      name: createapp\n      operations:\n      - method: POST\n        name: createapp\n        description: create app\n        call: flatcar-container-linux.createapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}\n      name: getapp\n      operations:\n      - method: GET\n        name: getapp\n        description: get app\n        call: flatcar-container-linux.getapp\n        with:\n          appIDorProductID: rest.appIDorProductID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}\n      name: updateapp\n      operations:\n      - method:\
  \ PUT\n        name: updateapp\n        description: update app\n        call: flatcar-container-linux.updateapp\n        with:\n          appIDorProductID: rest.appIDorProductID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}\n      name: deleteapp\n      operations:\n      - method: DELETE\n        name: deleteapp\n        description: delete app\n        call: flatcar-container-linux.deleteapp\n        with:\n          appIDorProductID: rest.appIDorProductID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/groups\n      name: paginategroups\n      operations:\n      - method: GET\n        name: paginategroups\n        description: paginate groups of an app\n        call: flatcar-container-linux.paginategroups\n        with:\n          appIDorProductID: rest.appIDorProductID\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /api/apps/{appIDorProductID}/groups\n      name: creategroup\n      operations:\n      - method: POST\n        name: creategroup\n        description: create group in app\n        call: flatcar-container-linux.creategroup\n        with:\n          appIDorProductID: rest.appIDorProductID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/groups/{groupID}\n      name: getgroup\n      operations:\n      - method: GET\n        name: getgroup\n        description: get group given its groupID and appID\n        call: flatcar-container-linux.getgroup\n        with:\n          appIDorProductID: rest.appIDorProductID\n          groupID: rest.groupID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/groups/{groupID}\n      name: updategroup\n      operations:\n      - method: PUT\n        name: updategroup\n        description: update group given its groupID\
  \ and appID\n        call: flatcar-container-linux.updategroup\n        with:\n          appIDorProductID: rest.appIDorProductID\n          groupID: rest.groupID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/groups/{groupID}\n      name: deletegroup\n      operations:\n      - method: DELETE\n        name: deletegroup\n        description: delete group given its groupID and appID\n        call: flatcar-container-linux.deletegroup\n        with:\n          appIDorProductID: rest.appIDorProductID\n          groupID: rest.groupID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/groups/{groupID}/version_timeline\n      name: getgroupversiontimeline\n      operations:\n      - method: GET\n        name: getgroupversiontimeline\n        description: get version timeline of a group given its groupID and appID\n        call: flatcar-container-linux.getgroupversiontimeline\n\
  \        with:\n          appIDorProductID: rest.appIDorProductID\n          groupID: rest.groupID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/groups/{groupID}/status_timeline\n      name: getgroupstatustimeline\n      operations:\n      - method: GET\n        name: getgroupstatustimeline\n        description: get status timeline of a group given its groupID and appID\n        call: flatcar-container-linux.getgroupstatustimeline\n        with:\n          appIDorProductID: rest.appIDorProductID\n          groupID: rest.groupID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/groups/{groupID}/instances_stats\n      name: getgroupinstancestats\n      operations:\n      - method: GET\n        name: getgroupinstancestats\n        description: get instance stats of a group given its groupID and appID\n        call: flatcar-container-linux.getgroupinstancestats\n\
  \        with:\n          appIDorProductID: rest.appIDorProductID\n          groupID: rest.groupID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/groups/{groupID}/version_breakdown\n      name: getgroupversionbreakdown\n      operations:\n      - method: GET\n        name: getgroupversionbreakdown\n        description: get version breakdown of a group given its groupID and appID\n        call: flatcar-container-linux.getgroupversionbreakdown\n        with:\n          appIDorProductID: rest.appIDorProductID\n          groupID: rest.groupID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/channels\n      name: paginatechannels\n      operations:\n      - method: GET\n        name: paginatechannels\n        description: paginate channels of an app\n        call: flatcar-container-linux.paginatechannels\n        with:\n          appIDorProductID: rest.appIDorProductID\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/channels\n      name: createchannel\n      operations:\n      - method: POST\n        name: createchannel\n        description: create channel\n        call: flatcar-container-linux.createchannel\n        with:\n          appIDorProductID: rest.appIDorProductID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/channels/{channelID}\n      name: getchannel\n      operations:\n      - method: GET\n        name: getchannel\n        description: get channel by id\n        call: flatcar-container-linux.getchannel\n        with:\n          appIDorProductID: rest.appIDorProductID\n          channelID: rest.channelID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/channels/{channelID}\n      name: updatechannel\n      operations:\n      - method: PUT\n\
  \        name: updatechannel\n        description: update channel by id\n        call: flatcar-container-linux.updatechannel\n        with:\n          appIDorProductID: rest.appIDorProductID\n          channelID: rest.channelID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/channels/{channelID}\n      name: deletechannel\n      operations:\n      - method: DELETE\n        name: deletechannel\n        description: delete channel by id\n        call: flatcar-container-linux.deletechannel\n        with:\n          appIDorProductID: rest.appIDorProductID\n          channelID: rest.channelID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/channels/{channelID}/floors\n      name: paginatechannelfloors\n      operations:\n      - method: GET\n        name: paginatechannelfloors\n        description: paginate floor packages of a channel\n        call: flatcar-container-linux.paginatechannelfloors\n\
  \        with:\n          channelID: rest.channelID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/channels/{channelID}/floors/{packageID}\n      name: setchannelfloor\n      operations:\n      - method: PUT\n        name: setchannelfloor\n        description: Create or update a floor package relationship (idempotent operation)\n        call: flatcar-container-linux.setchannelfloor\n        with:\n          channelID: rest.channelID\n          packageID: rest.packageID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/channels/{channelID}/floors/{packageID}\n      name: removechannelfloor\n      operations:\n      - method: DELETE\n        name: removechannelfloor\n        description: remove package as floor for a channel\n        call: flatcar-container-linux.removechannelfloor\n        with:\n          channelID: rest.channelID\n          packageID: rest.packageID\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/packages\n      name: paginatepackages\n      operations:\n      - method: GET\n        name: paginatepackages\n        description: paginate packages of an app\n        call: flatcar-container-linux.paginatepackages\n        with:\n          appIDorProductID: rest.appIDorProductID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/packages\n      name: createpackage\n      operations:\n      - method: POST\n        name: createpackage\n        description: create package\n        call: flatcar-container-linux.createpackage\n        with:\n          appIDorProductID: rest.appIDorProductID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/apps/{appIDorProductID}/packa\n\n# --- truncated at 32 KB (60 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/flatcar-container-linux/refs/heads/main/capabilities/flatcar-container-linux-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/flatcar-container-linux/refs/heads/main/capabilities/flatcar-container-linux-capability.yaml
tags:
- Flatcar
- Container
- Linux
- API
tools:
- description: GitHub OAuth callback (GitHub mode only)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: logincb
- description: validate JWT access token (OIDC mode only)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: validatetoken
- description: GitHub webhook (GitHub mode only)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: loginwebhook
- description: health endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: health
- description: get app config
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconfig
- description: omaha endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: omaha
- description: get Apps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: paginateapps
- description: create app
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapp
- description: get app
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapp
- description: update app
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateapp
- description: delete app
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapp
- description: paginate groups of an app
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: paginategroups
- description: create group in app
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: get group given its groupID and appID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroup
- description: update group given its groupID and appID
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updategroup
- description: delete group given its groupID and appID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroup
- description: get version timeline of a group given its groupID and appID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupversiontimeline
- description: get status timeline of a group given its groupID and appID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupstatustimeline
- description: get instance stats of a group given its groupID and appID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupinstancestats
- description: get version breakdown of a group given its groupID and appID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupversionbreakdown
- description: paginate channels of an app
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: paginatechannels
- description: create channel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchannel
- description: get channel by id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchannel
- description: update channel by id
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatechannel
- description: delete channel by id
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletechannel
- description: paginate floor packages of a channel
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: paginatechannelfloors
- description: Create or update a floor package relationship (idempotent operation)
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setchannelfloor
- description: remove package as floor for a channel
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removechannelfloor
- description: paginate packages of an app
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: paginatepackages
- description: create package
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpackage
- description: get package given its packageID and appID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpackage
- description: update package given its packageID and appID
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepackage
- description: delete package given its packageID and appID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepackage
- description: get all channels where a package is marked as a floor
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpackagefloorchannels
- description: get instances of a group given its groupID and appID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupinstances
- description: get instance count of a group given its groupID and appID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupinstancescount
- description: get instance of a group given its groupID and appID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstance
- description: get instance status_history.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstancestatushistory
- description: update instance
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateinstance
- description: paginate activity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: paginateactivity
---
