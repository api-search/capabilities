---
categories: []
consumed_apis: []
description: The DreamFactory System API provides administrative management capabilities for DreamFactory instances. It allows administrators to manage services, apps, roles, users, CORS configurations, email templates, environment settings, lookups, events, scripts, and more. All system resources are accessible under the /api/v2/system/ base path. Authentication requires either an X-DreamFactory-Session-Token header (for system admins) or an X-DreamFactory-API-Key header (for users with appropriate permissions).
layout: capability
name: DreamFactory System API
operations:
- description: DreamFactory List administrators
  method: GET
  name: listadmins
  path: /system/admin
- description: DreamFactory Create administrator
  method: POST
  name: createadmin
  path: /system/admin
- description: DreamFactory Get administrator
  method: GET
  name: getadmin
  path: /system/admin/{id}
- description: DreamFactory Update administrator
  method: PATCH
  name: updateadmin
  path: /system/admin/{id}
- description: DreamFactory Delete administrator
  method: DELETE
  name: deleteadmin
  path: /system/admin/{id}
- description: DreamFactory List applications
  method: GET
  name: listapps
  path: /system/app
- description: DreamFactory Create application
  method: POST
  name: createapp
  path: /system/app
- description: DreamFactory Get application
  method: GET
  name: getapp
  path: /system/app/{id}
- description: DreamFactory Update application
  method: PATCH
  name: updateapp
  path: /system/app/{id}
- description: DreamFactory Delete application
  method: DELETE
  name: deleteapp
  path: /system/app/{id}
- description: DreamFactory List application groups
  method: GET
  name: listappgroups
  path: /system/app_group
- description: DreamFactory Create application group
  method: POST
  name: createappgroup
  path: /system/app_group
- description: DreamFactory List CORS configurations
  method: GET
  name: listcorsconfigs
  path: /system/cors
- description: DreamFactory Create CORS configuration
  method: POST
  name: createcorsconfig
  path: /system/cors
- description: DreamFactory Get CORS configuration
  method: GET
  name: getcorsconfig
  path: /system/cors/{id}
- description: DreamFactory Update CORS configuration
  method: PATCH
  name: updatecorsconfig
  path: /system/cors/{id}
- description: DreamFactory Delete CORS configuration
  method: DELETE
  name: deletecorsconfig
  path: /system/cors/{id}
- description: DreamFactory List email templates
  method: GET
  name: listemailtemplates
  path: /system/email_template
- description: DreamFactory Create email template
  method: POST
  name: createemailtemplate
  path: /system/email_template
- description: DreamFactory Get environment information
  method: GET
  name: getenvironment
  path: /system/environment
- description: DreamFactory List events
  method: GET
  name: listevents
  path: /system/event
- description: DreamFactory List API limits
  method: GET
  name: listlimits
  path: /system/limit
- description: DreamFactory Create API limit
  method: POST
  name: createlimit
  path: /system/limit
- description: DreamFactory Get API limit
  method: GET
  name: getlimit
  path: /system/limit/{id}
- description: DreamFactory Update API limit
  method: PATCH
  name: updatelimit
  path: /system/limit/{id}
- description: DreamFactory Delete API limit
  method: DELETE
  name: deletelimit
  path: /system/limit/{id}
- description: DreamFactory List limit cache
  method: GET
  name: listlimitcache
  path: /system/limit_cache
- description: DreamFactory Reset limit counters
  method: DELETE
  name: resetlimitcache
  path: /system/limit_cache
- description: DreamFactory List lookups
  method: GET
  name: listlookups
  path: /system/lookup
- description: DreamFactory Create lookup
  method: POST
  name: createlookup
  path: /system/lookup
- description: DreamFactory List roles
  method: GET
  name: listroles
  path: /system/role
- description: DreamFactory Create role
  method: POST
  name: createrole
  path: /system/role
- description: DreamFactory Get role
  method: GET
  name: getrole
  path: /system/role/{id}
- description: DreamFactory Update role
  method: PATCH
  name: updaterole
  path: /system/role/{id}
- description: DreamFactory Delete role
  method: DELETE
  name: deleterole
  path: /system/role/{id}
- description: DreamFactory List services
  method: GET
  name: listservices
  path: /system/service
- description: DreamFactory Create service
  method: POST
  name: createservice
  path: /system/service
- description: DreamFactory Get service
  method: GET
  name: getservice
  path: /system/service/{id}
- description: DreamFactory Update service
  method: PATCH
  name: updateservice
  path: /system/service/{id}
- description: DreamFactory Delete service
  method: DELETE
  name: deleteservice
  path: /system/service/{id}
- description: DreamFactory List service types
  method: GET
  name: listservicetypes
  path: /system/service_type
- description: DreamFactory List script types
  method: GET
  name: listscripttypes
  path: /system/script_type
- description: DreamFactory List users
  method: GET
  name: listusers
  path: /system/user
- description: DreamFactory Create user
  method: POST
  name: createuser
  path: /system/user
- description: DreamFactory Get user
  method: GET
  name: getuser
  path: /system/user/{id}
- description: DreamFactory Update user
  method: PATCH
  name: updateuser
  path: /system/user/{id}
- description: DreamFactory Delete user
  method: DELETE
  name: deleteuser
  path: /system/user/{id}
- description: DreamFactory List custom settings
  method: GET
  name: listcustomsettings
  path: /system/custom
- description: DreamFactory Set custom settings
  method: POST
  name: setcustomsettings
  path: /system/custom
- description: DreamFactory List packages
  method: GET
  name: listpackages
  path: /system/package
- description: DreamFactory Import package
  method: POST
  name: importpackage
  path: /system/package
personas: []
provider_name: DreamFactory
provider_slug: dreamfactory
search_terms:
- dreamfactory delete administrator
- dreamfactory list custom settings
- getlimit
- importpackage
- api
- updaterole
- documentation
- listlimitcache
- deployment
- deleteuser
- listadmins
- dreamfactory create lookup
- getrole
- dreamfactory get role
- dreamfactory update application
- dreamfactory
- dreamfactory get administrator
- listcustomsettings
- dreamfactory list cors configurations
- getapp
- listevents
- listapps
- deleteservice
- dreamfactory list limit cache
- createrole
- listservices
- dreamfactory create application group
- dreamfactory list application groups
- dreamfactory get environment information
- getenvironment
- dreamfactory list lookups
- dreamfactory update service
- listcorsconfigs
- dreamfactory get cors configuration
- dreamfactory delete user
- dreamfactory delete cors configuration
- setcustomsettings
- dreamfactory delete service
- listlookups
- dreamfactory get application
- dreamfactory list events
- dreamfactory create api limit
- createuser
- dreamfactory get api limit
- createcorsconfig
- dreamfactory create role
- security
- dreamfactory list packages
- dreamfactory update user
- deletelimit
- dreamfactory list applications
- dreamfactory update role
- automation
- listscripttypes
- dreamfactory get service
- resetlimitcache
- dreamfactory create email template
- generation
- dreamfactory create user
- updateadmin
- dreamfactory import package
- updateuser
- dreamfactory set custom settings
- listpackages
- createappgroup
- listusers
- deletecorsconfig
- createservice
- deleteadmin
- dreamfactory update cors configuration
- createlookup
- dreamfactory list service types
- listemailtemplates
- listservicetypes
- getservice
- dreamfactory update api limit
- dreamfactory update administrator
- dreamfactory list roles
- deleterole
- updatecorsconfig
- dreamfactory list services
- getuser
- updateservice
- createlimit
- dreamfactory reset limit counters
- updateapp
- dreamfactory list api limits
- getadmin
- dreamfactory list administrators
- createadmin
- dreamfactory delete application
- dreamfactory create application
- getcorsconfig
- dreamfactory list users
- dreamfactory delete api limit
- dreamfactory get user
- dreamfactory create cors configuration
- listappgroups
- createemailtemplate
- deleteapp
- dreamfactory delete role
- updatelimit
- createapp
- dreamfactory create service
- listroles
- dreamfactory list script types
- dreamfactory list email templates
- listlimits
- dreamfactory create administrator
slug: dreamfactory-capability
source_filename: dreamfactory-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: DreamFactory System API\n  description: The DreamFactory System API provides administrative management capabilities for DreamFactory instances. It\n    allows administrators to manage services, apps, roles, users, CORS configurations, email templates, environment settings,\n    lookups, events, scripts, and more. All system resources are accessible under the /api/v2/system/ base path. Authentication\n    requires either an X-DreamFactory-Session-Token header (for system admins) or an X-DreamFactory-API-Key header (for users\n    with appropriate permissions).\n  tags:\n  - Dreamfactory\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: dreamfactory\n    baseUri: https://example.dreamfactory.com/api/v2\n    description: DreamFactory System API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-DreamFactory-Session-Token\n      value: '{{DREAMFACTORY_TOKEN}}'\n\
  \    resources:\n    - name: system-admin\n      path: /system/admin\n      operations:\n      - name: listadmins\n        method: GET\n        description: DreamFactory List administrators\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createadmin\n        method: POST\n        description: DreamFactory Create administrator\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-admin-id\n      path: /system/admin/{id}\n      operations:\n      - name: getadmin\n        method: GET\n        description: DreamFactory Get administrator\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateadmin\n        method: PATCH\n        description: DreamFactory Update administrator\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteadmin\n        method: DELETE\n        description: DreamFactory Delete administrator\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-app\n      path: /system/app\n      operations:\n      - name: listapps\n        method: GET\n        description: DreamFactory List applications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapp\n        method: POST\n        description: DreamFactory Create application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-app-id\n      path: /system/app/{id}\n      operations:\n      - name: getapp\n        method: GET\n        description: DreamFactory Get\
  \ application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapp\n        method: PATCH\n        description: DreamFactory Update application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapp\n        method: DELETE\n        description: DreamFactory Delete application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-app-group\n      path: /system/app_group\n      operations:\n      - name: listappgroups\n        method: GET\n        description: DreamFactory List application groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createappgroup\n        method: POST\n        description: DreamFactory\
  \ Create application group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-cors\n      path: /system/cors\n      operations:\n      - name: listcorsconfigs\n        method: GET\n        description: DreamFactory List CORS configurations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcorsconfig\n        method: POST\n        description: DreamFactory Create CORS configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-cors-id\n      path: /system/cors/{id}\n      operations:\n      - name: getcorsconfig\n        method: GET\n        description: DreamFactory Get CORS configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n      - name: updatecorsconfig\n        method: PATCH\n        description: DreamFactory Update CORS configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecorsconfig\n        method: DELETE\n        description: DreamFactory Delete CORS configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-email-template\n      path: /system/email_template\n      operations:\n      - name: listemailtemplates\n        method: GET\n        description: DreamFactory List email templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createemailtemplate\n        method: POST\n        description: DreamFactory Create email template\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: system-environment\n      path: /system/environment\n      operations:\n      - name: getenvironment\n        method: GET\n        description: DreamFactory Get environment information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-event\n      path: /system/event\n      operations:\n      - name: listevents\n        method: GET\n        description: DreamFactory List events\n        inputParameters:\n        - name: as_list\n          in: query\n          type: boolean\n          description: Return events as a simple list.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-limit\n      path: /system/limit\n      operations:\n      - name: listlimits\n        method: GET\n        description: DreamFactory List API\
  \ limits\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlimit\n        method: POST\n        description: DreamFactory Create API limit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-limit-id\n      path: /system/limit/{id}\n      operations:\n      - name: getlimit\n        method: GET\n        description: DreamFactory Get API limit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelimit\n        method: PATCH\n        description: DreamFactory Update API limit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelimit\n        method: DELETE\n        description: DreamFactory Delete API limit\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-limit-cache\n      path: /system/limit_cache\n      operations:\n      - name: listlimitcache\n        method: GET\n        description: DreamFactory List limit cache\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: resetlimitcache\n        method: DELETE\n        description: DreamFactory Reset limit counters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-lookup\n      path: /system/lookup\n      operations:\n      - name: listlookups\n        method: GET\n        description: DreamFactory List lookups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlookup\n\
  \        method: POST\n        description: DreamFactory Create lookup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-role\n      path: /system/role\n      operations:\n      - name: listroles\n        method: GET\n        description: DreamFactory List roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrole\n        method: POST\n        description: DreamFactory Create role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-role-id\n      path: /system/role/{id}\n      operations:\n      - name: getrole\n        method: GET\n        description: DreamFactory Get role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: updaterole\n        method: PATCH\n        description: DreamFactory Update role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterole\n        method: DELETE\n        description: DreamFactory Delete role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-service\n      path: /system/service\n      operations:\n      - name: listservices\n        method: GET\n        description: DreamFactory List services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createservice\n        method: POST\n        description: DreamFactory Create service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-service-id\n\
  \      path: /system/service/{id}\n      operations:\n      - name: getservice\n        method: GET\n        description: DreamFactory Get service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateservice\n        method: PATCH\n        description: DreamFactory Update service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteservice\n        method: DELETE\n        description: DreamFactory Delete service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-service-type\n      path: /system/service_type\n      operations:\n      - name: listservicetypes\n        method: GET\n        description: DreamFactory List service types\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: system-script-type\n      path: /system/script_type\n      operations:\n      - name: listscripttypes\n        method: GET\n        description: DreamFactory List script types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-user\n      path: /system/user\n      operations:\n      - name: listusers\n        method: GET\n        description: DreamFactory List users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: DreamFactory Create user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-user-id\n      path: /system/user/{id}\n      operations:\n      - name: getuser\n        method: GET\n\
  \        description: DreamFactory Get user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PATCH\n        description: DreamFactory Update user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: DreamFactory Delete user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-custom\n      path: /system/custom\n      operations:\n      - name: listcustomsettings\n        method: GET\n        description: DreamFactory List custom settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setcustomsettings\n        method: POST\n        description:\
  \ DreamFactory Set custom settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-package\n      path: /system/package\n      operations:\n      - name: listpackages\n        method: GET\n        description: DreamFactory List packages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: importpackage\n        method: POST\n        description: DreamFactory Import package\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: dreamfactory-rest\n    description: REST adapter for DreamFactory System API.\n    resources:\n    - path: /system/admin\n      name: listadmins\n      operations:\n      - method: GET\n        name: listadmins\n        description: DreamFactory List\
  \ administrators\n        call: dreamfactory.listadmins\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/admin\n      name: createadmin\n      operations:\n      - method: POST\n        name: createadmin\n        description: DreamFactory Create administrator\n        call: dreamfactory.createadmin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/admin/{id}\n      name: getadmin\n      operations:\n      - method: GET\n        name: getadmin\n        description: DreamFactory Get administrator\n        call: dreamfactory.getadmin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/admin/{id}\n      name: updateadmin\n      operations:\n      - method: PATCH\n        name: updateadmin\n        description: DreamFactory Update administrator\n        call: dreamfactory.updateadmin\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /system/admin/{id}\n      name: deleteadmin\n      operations:\n      - method: DELETE\n        name: deleteadmin\n        description: DreamFactory Delete administrator\n        call: dreamfactory.deleteadmin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/app\n      name: listapps\n      operations:\n      - method: GET\n        name: listapps\n        description: DreamFactory List applications\n        call: dreamfactory.listapps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/app\n      name: createapp\n      operations:\n      - method: POST\n        name: createapp\n        description: DreamFactory Create application\n        call: dreamfactory.createapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/app/{id}\n      name: getapp\n      operations:\n      - method: GET\n        name: getapp\n        description: DreamFactory Get\
  \ application\n        call: dreamfactory.getapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/app/{id}\n      name: updateapp\n      operations:\n      - method: PATCH\n        name: updateapp\n        description: DreamFactory Update application\n        call: dreamfactory.updateapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/app/{id}\n      name: deleteapp\n      operations:\n      - method: DELETE\n        name: deleteapp\n        description: DreamFactory Delete application\n        call: dreamfactory.deleteapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/app_group\n      name: listappgroups\n      operations:\n      - method: GET\n        name: listappgroups\n        description: DreamFactory List application groups\n        call: dreamfactory.listappgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /system/app_group\n      name: createappgroup\n      operations:\n      - method: POST\n        name: createappgroup\n        description: DreamFactory Create application group\n        call: dreamfactory.createappgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/cors\n      name: listcorsconfigs\n      operations:\n      - method: GET\n        name: listcorsconfigs\n        description: DreamFactory List CORS configurations\n        call: dreamfactory.listcorsconfigs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/cors\n      name: createcorsconfig\n      operations:\n      - method: POST\n        name: createcorsconfig\n        description: DreamFactory Create CORS configuration\n        call: dreamfactory.createcorsconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/cors/{id}\n      name: getcorsconfig\n      operations:\n \
  \     - method: GET\n        name: getcorsconfig\n        description: DreamFactory Get CORS configuration\n        call: dreamfactory.getcorsconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/cors/{id}\n      name: updatecorsconfig\n      operations:\n      - method: PATCH\n        name: updatecorsconfig\n        description: DreamFactory Update CORS configuration\n        call: dreamfactory.updatecorsconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/cors/{id}\n      name: deletecorsconfig\n      operations:\n      - method: DELETE\n        name: deletecorsconfig\n        description: DreamFactory Delete CORS configuration\n        call: dreamfactory.deletecorsconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/email_template\n      name: listemailtemplates\n      operations:\n      - method: GET\n        name: listemailtemplates\n  \
  \      description: DreamFactory List email templates\n        call: dreamfactory.listemailtemplates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/email_template\n      name: createemailtemplate\n      operations:\n      - method: POST\n        name: createemailtemplate\n        description: DreamFactory Create email template\n        call: dreamfactory.createemailtemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/environment\n      name: getenvironment\n      operations:\n      - method: GET\n        name: getenvironment\n        description: DreamFactory Get environment information\n        call: dreamfactory.getenvironment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/event\n      name: listevents\n      operations:\n      - method: GET\n        name: listevents\n        description: DreamFactory List events\n        call: dreamfactory.listevents\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/limit\n      name: listlimits\n      operations:\n      - method: GET\n        name: listlimits\n        description: DreamFactory List API limits\n        call: dreamfactory.listlimits\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/limit\n      name: createlimit\n      operations:\n      - method: POST\n        name: createlimit\n        description: DreamFactory Create API limit\n        call: dreamfactory.createlimit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/limit/{id}\n      name: getlimit\n      operations:\n      - method: GET\n        name: getlimit\n        description: DreamFactory Get API limit\n        call: dreamfactory.getlimit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/limit/{id}\n      name: updatelimit\n      operations:\n   \
  \   - method: PATCH\n        name: updatelimit\n        description: DreamFactory Update API limit\n        call: dreamfactory.updatelimit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/limit/{id}\n      name: deletelimit\n      operations:\n      - method: DELETE\n        name: deletelimit\n        description: DreamFactory Delete API limit\n        call: dreamfactory.deletelimit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/limit_cache\n      name: listlimitcache\n      operations:\n      - method: GET\n        name: listlimitcache\n        description: DreamFactory List limit cache\n        call: dreamfactory.listlimitcache\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/limit_cache\n      name: resetlimitcache\n      operations:\n      - method: DELETE\n        name: resetlimitcache\n        description: DreamFactory Reset limit counters\n\
  \        call: dreamfactory.resetlimitcache\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/lookup\n      name: listlookups\n      operations:\n      - method: GET\n        name: listlookups\n        description: DreamFactory List lookups\n        call: dreamfactory.listlookups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/lookup\n      name: createlookup\n      operations:\n      - method: POST\n        name: createlookup\n        description: DreamFactory Create lookup\n        call: dreamfactory.createlookup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/role\n      name: listroles\n      operations:\n      - method: GET\n        name: listroles\n        description: DreamFactory List roles\n        call: dreamfactory.listroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/role\n      name: createrole\n\
  \      operations:\n      - method: POST\n        name: createrole\n        description: DreamFactory Create role\n        call: dreamfactory.createrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/role/{id}\n      name: getrole\n      operations:\n      - method: GET\n        name: getrole\n        description: DreamFactory Get role\n        call: dreamfactory.getrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/role/{id}\n      name: updaterole\n      operations:\n      - method: PATCH\n        name: updaterole\n        description: DreamFactory Update role\n        call: dreamfactory.updaterole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/role/{id}\n      name: deleterole\n      operations:\n      - method: DELETE\n        name: deleterole\n        description: DreamFactory Delete role\n        call: dreamfactory.deleterole\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /system/service\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: DreamFactory List services\n        call: dreamfactory.listservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/service\n      name: createservice\n      operations:\n      - method: POST\n        name: createservice\n        description: DreamFactory Create service\n        call: dreamfactory.createservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/service/{id}\n      name: getservice\n      operations:\n      - method: GET\n        name: getservice\n        description: DreamFactory Get service\n        call: dreamfactory.getservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/service/{id}\n      name: updateservice\n      operations:\n      - method:\
  \ PATCH\n        name: updateservice\n        description: DreamFactory Update service\n        call: dreamfactory.updateservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/service/{id}\n      name: deleteservice\n      operations:\n      - method: DELETE\n        name: deleteservice\n        description: DreamFactory Delete service\n        call: dreamfactory.deleteservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/service_type\n      name: listservicetypes\n      operations:\n      - method: GET\n        name: listservicetypes\n        description: DreamFactory List service types\n        call: dreamfactory.listservicetypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/script_type\n      name: listscripttypes\n      operations:\n      - method: GET\n        name: listscripttypes\n        description: DreamFactory List script types\n \
  \       call: dreamfactory.listscripttypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/user\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: DreamFactory List users\n        call: dreamfactory.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/user\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: DreamFactory Create user\n        call: dreamfactory.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/user/{id}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: DreamFactory Get user\n        call: dreamfactory.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/user/{id}\n      name: updateuser\n      operations:\n\
  \      - method: PATCH\n        name: updateuser\n        description: DreamFactory Update user\n        call: dreamfactory.updateuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/user/{id}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: DreamFactory Delete user\n        call: dreamfactory.deleteuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/custom\n      name: listcustomsettings\n      operations:\n      - method: GET\n        name: listcustomsettings\n        description: DreamFactory List custom settings\n        call: dreamfactory.listcustomsettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/custom\n      name: setcustomsettings\n      operations:\n      - method: POST\n        name: setcustomsettings\n        description: DreamFactory Set custom settings\n      \
  \  call: dreamfactory.setcustomsettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/package\n      name: listpackages\n      operations:\n      - method: GET\n        name: listpackages\n        description: DreamFactory List packages\n        call: dreamfactory.listpackages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system/package\n      name: importpackage\n      operations:\n      - method: POST\n        name: importpackage\n        description: DreamFactory Import package\n        call: dreamfactory.importpackage\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: dreamfactory-mcp\n    transport: http\n    description: MCP adapter for DreamFactory System API for AI agent use.\n    tools:\n    - name: listadmins\n      description: DreamFactory List administrators\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: dreamfactory.listadmins\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createadmin\n      description: DreamFactory Create administrator\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: dreamfactory.createadmin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getadmin\n      description: DreamFactory Get administrator\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: dreamfactory.getadmin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateadmin\n      description: DreamFactory Update administrator\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: dreamfactory.updateadmin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteadmin\n      description:\
  \ DreamFactory Delete administrator\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: dreamfactory.deleteadmin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapps\n      description: DreamFactory List applications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: dreamfactory.listapps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapp\n      description: DreamFactory Create application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: dreamfactory.createapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapp\n      description: DreamFactory Get application\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: dreamfactory.getapp\n      outputParameters:\n    \
  \  - type: object\n        mapping: $.\n    - name: updateapp\n      description: DreamFactory Update application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: dreamfactory.updateapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteapp\n      description: DreamFactory Delete application\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: dreamfactory.deleteapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listappgroups\n      description: DreamFactory List application groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: dreamfactory.listappgroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createappgroup\n      description: DreamFactory Create application group\n      hints:\n        readOnly: false\n      \
  \  destructive: false\n        idempotent: false\n      call: dreamfactory.createappgroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcorsconfigs\n      description: DreamFactory List CORS configurations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: dreamfactory.listcorsconfigs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcorsconfig\n      description: DreamFactory Create CORS configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: dreamfactory.createcorsconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcorsconfig\n      description: DreamFactory Get CORS configuration\n      hints:\n        readOnly: true\n        \n\n# --- truncated at 32 KB (41 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/dreamfactory/refs/heads/main/capabilities/dreamfactory-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/dreamfactory/refs/heads/main/capabilities/dreamfactory-capability.yaml
tags:
- Dreamfactory
- API
tools:
- description: DreamFactory List administrators
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listadmins
- description: DreamFactory Create administrator
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createadmin
- description: DreamFactory Get administrator
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getadmin
- description: DreamFactory Update administrator
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateadmin
- description: DreamFactory Delete administrator
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteadmin
- description: DreamFactory List applications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapps
- description: DreamFactory Create application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapp
- description: DreamFactory Get application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapp
- description: DreamFactory Update application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateapp
- description: DreamFactory Delete application
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapp
- description: DreamFactory List application groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listappgroups
- description: DreamFactory Create application group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createappgroup
- description: DreamFactory List CORS configurations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcorsconfigs
- description: DreamFactory Create CORS configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcorsconfig
- description: DreamFactory Get CORS configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcorsconfig
- description: DreamFactory Update CORS configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecorsconfig
- description: DreamFactory Delete CORS configuration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecorsconfig
- description: DreamFactory List email templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listemailtemplates
- description: DreamFactory Create email template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createemailtemplate
- description: DreamFactory Get environment information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvironment
- description: DreamFactory List events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listevents
- description: DreamFactory List API limits
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlimits
- description: DreamFactory Create API limit
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlimit
- description: DreamFactory Get API limit
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlimit
- description: DreamFactory Update API limit
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatelimit
- description: DreamFactory Delete API limit
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelimit
- description: DreamFactory List limit cache
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlimitcache
- description: DreamFactory Reset limit counters
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: resetlimitcache
- description: DreamFactory List lookups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlookups
- description: DreamFactory Create lookup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlookup
- description: DreamFactory List roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroles
- description: DreamFactory Create role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrole
- description: DreamFactory Get role
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrole
- description: DreamFactory Update role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updaterole
- description: DreamFactory Delete role
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterole
- description: DreamFactory List services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: DreamFactory Create service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createservice
- description: DreamFactory Get service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservice
- description: DreamFactory Update service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateservice
- description: DreamFactory Delete service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteservice
- description: DreamFactory List service types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservicetypes
- description: DreamFactory List script types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listscripttypes
- description: DreamFactory List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: DreamFactory Create user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: DreamFactory Get user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: DreamFactory Update user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateuser
- description: DreamFactory Delete user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: DreamFactory List custom settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcustomsettings
- description: DreamFactory Set custom settings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setcustomsettings
- description: DreamFactory List packages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpackages
- description: DreamFactory Import package
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: importpackage
---
