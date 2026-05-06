---
categories: []
consumed_apis: []
description: The OpenSearch Security plugin REST API lets administrators programmatically create and manage internal users, roles, role mappings, action groups, tenants, security configuration, audit log configuration, certificates, cache, allowlists, distinguished node names, and inspect the running security configuration. Endpoints are exposed under /_plugins/_security/api on the OpenSearch cluster.
layout: capability
name: OpenSearch Security Plugin REST API
operations:
- description: Get current user account
  method: GET
  name: getaccount
  path: /_plugins/_security/api/account
- description: Change current user password
  method: PUT
  name: changepassword
  path: /_plugins/_security/api/account
- description: List all internal users
  method: GET
  name: listinternalusers
  path: /_plugins/_security/api/internalusers
- description: Get internal user
  method: GET
  name: getinternaluser
  path: /_plugins/_security/api/internalusers/{username}
- description: Create or replace an internal user
  method: PUT
  name: createorreplaceinternaluser
  path: /_plugins/_security/api/internalusers/{username}
- description: Delete internal user
  method: DELETE
  name: deleteinternaluser
  path: /_plugins/_security/api/internalusers/{username}
- description: Patch internal user
  method: PATCH
  name: patchinternaluser
  path: /_plugins/_security/api/internalusers/{username}
- description: List all roles
  method: GET
  name: listroles
  path: /_plugins/_security/api/roles
- description: Get role
  method: GET
  name: getrole
  path: /_plugins/_security/api/roles/{name}
- description: Create or replace a role
  method: PUT
  name: createorreplacerole
  path: /_plugins/_security/api/roles/{name}
- description: Delete role
  method: DELETE
  name: deleterole
  path: /_plugins/_security/api/roles/{name}
- description: Patch role
  method: PATCH
  name: patchrole
  path: /_plugins/_security/api/roles/{name}
- description: List all role mappings
  method: GET
  name: listrolemappings
  path: /_plugins/_security/api/rolesmapping
- description: Get role mapping
  method: GET
  name: getrolemapping
  path: /_plugins/_security/api/rolesmapping/{name}
- description: Create or replace a role mapping
  method: PUT
  name: createorreplacerolemapping
  path: /_plugins/_security/api/rolesmapping/{name}
- description: Delete role mapping
  method: DELETE
  name: deleterolemapping
  path: /_plugins/_security/api/rolesmapping/{name}
- description: Patch role mapping
  method: PATCH
  name: patchrolemapping
  path: /_plugins/_security/api/rolesmapping/{name}
- description: List all action groups
  method: GET
  name: listactiongroups
  path: /_plugins/_security/api/actiongroups
- description: Get action group
  method: GET
  name: getactiongroup
  path: /_plugins/_security/api/actiongroups/{name}
- description: Create or replace an action group
  method: PUT
  name: createorreplaceactiongroup
  path: /_plugins/_security/api/actiongroups/{name}
- description: Delete action group
  method: DELETE
  name: deleteactiongroup
  path: /_plugins/_security/api/actiongroups/{name}
- description: Patch action group
  method: PATCH
  name: patchactiongroup
  path: /_plugins/_security/api/actiongroups/{name}
- description: List all tenants
  method: GET
  name: listtenants
  path: /_plugins/_security/api/tenants
- description: Get tenant
  method: GET
  name: gettenant
  path: /_plugins/_security/api/tenants/{name}
- description: Create or replace a tenant
  method: PUT
  name: createorreplacetenant
  path: /_plugins/_security/api/tenants/{name}
- description: Delete tenant
  method: DELETE
  name: deletetenant
  path: /_plugins/_security/api/tenants/{name}
- description: Patch tenant
  method: PATCH
  name: patchtenant
  path: /_plugins/_security/api/tenants/{name}
- description: Get security configuration
  method: GET
  name: getsecurityconfig
  path: /_plugins/_security/api/securityconfig
- description: Patch security configuration
  method: PATCH
  name: patchsecurityconfig
  path: /_plugins/_security/api/securityconfig
- description: Replace security configuration
  method: PUT
  name: replacesecurityconfig
  path: /_plugins/_security/api/securityconfig/config
- description: Get audit log configuration
  method: GET
  name: getauditconfig
  path: /_plugins/_security/api/audit
- description: Replace audit log configuration
  method: PUT
  name: replaceauditconfig
  path: /_plugins/_security/api/audit/config
- description: Patch audit log configuration
  method: PATCH
  name: patchauditconfig
  path: /_plugins/_security/api/audit/config
- description: Get allowlist
  method: GET
  name: getallowlist
  path: /_plugins/_security/api/allowlist
- description: Replace allowlist
  method: PUT
  name: replaceallowlist
  path: /_plugins/_security/api/allowlist
- description: Patch allowlist
  method: PATCH
  name: patchallowlist
  path: /_plugins/_security/api/allowlist
- description: List all node DN entries
  method: GET
  name: listnodesdn
  path: /_plugins/_security/api/nodesdn
- description: Get node DN entry
  method: GET
  name: getnodesdn
  path: /_plugins/_security/api/nodesdn/{name}
- description: Create or replace node DN entry
  method: PUT
  name: createorreplacenodesdn
  path: /_plugins/_security/api/nodesdn/{name}
- description: Delete node DN entry
  method: DELETE
  name: deletenodesdn
  path: /_plugins/_security/api/nodesdn/{name}
- description: Get SSL certificates loaded by the cluster
  method: GET
  name: getcertificates
  path: /_plugins/_security/api/ssl/certs
- description: Reload transport-layer SSL certificates
  method: PUT
  name: reloadtransportcerts
  path: /_plugins/_security/api/ssl/transport/reloadcerts
- description: Reload HTTP-layer SSL certificates
  method: PUT
  name: reloadhttpcerts
  path: /_plugins/_security/api/ssl/http/reloadcerts
- description: Flush security cache
  method: DELETE
  name: flushsecuritycache
  path: /_plugins/_security/api/cache
- description: Security plugin health
  method: GET
  name: securityhealth
  path: /_plugins/_security/health
- description: Get authentication info for current request
  method: GET
  name: authinfo
  path: /_plugins/_security/authinfo
- description: Get SSL handshake info for current request
  method: GET
  name: sslinfo
  path: /_plugins/_security/sslinfo
personas: []
provider_name: OpenSearch
provider_slug: opensearch
search_terms:
- list all roles
- changepassword
- getrolemapping
- delete role mapping
- get audit log configuration
- analytics
- getrole
- patch role
- createorreplacerole
- create or replace a tenant
- list all action groups
- get ssl certificates loaded by the cluster
- security
- list all tenants
- replacesecurityconfig
- listnodesdn
- api
- observability
- reloadhttpcerts
- search
- createorreplacerolemapping
- patchauditconfig
- opensearch
- list all internal users
- get node dn entry
- replaceallowlist
- getallowlist
- patch internal user
- create or replace node dn entry
- patchrolemapping
- getauditconfig
- change current user password
- listactiongroups
- replaceauditconfig
- deleterolemapping
- deletetenant
- patchtenant
- securityhealth
- getinternaluser
- patchactiongroup
- security plugin health
- patch role mapping
- reload transport-layer ssl certificates
- listinternalusers
- get action group
- patch tenant
- reload http-layer ssl certificates
- open source
- listroles
- create or replace an action group
- gettenant
- deletenodesdn
- listrolemappings
- patchrole
- get allowlist
- get role mapping
- get security configuration
- replace security configuration
- get current user account
- patch action group
- listtenants
- deleterole
- delete internal user
- getnodesdn
- delete action group
- flush security cache
- getactiongroup
- list all role mappings
- get tenant
- patchsecurityconfig
- patch security configuration
- replace allowlist
- create or replace an internal user
- delete tenant
- patchallowlist
- patchinternaluser
- get ssl handshake info for current request
- get internal user
- reloadtransportcerts
- delete node dn entry
- patch audit log configuration
- get role
- getsecurityconfig
- flushsecuritycache
- deleteinternaluser
- authinfo
- getaccount
- createorreplacenodesdn
- sslinfo
- replace audit log configuration
- getcertificates
- patch allowlist
- createorreplaceactiongroup
- createorreplacetenant
- list all node dn entries
- create or replace a role mapping
- delete role
- create or replace a role
- get authentication info for current request
- createorreplaceinternaluser
- deleteactiongroup
slug: opensearch-capability
source_filename: opensearch-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenSearch Security Plugin REST API\n  description: The OpenSearch Security plugin REST API lets administrators programmatically create and manage internal users,\n    roles, role mappings, action groups, tenants, security configuration, audit log configuration, certificates, cache, allowlists,\n    distinguished node names, and inspect the running security configuration. Endpoints are exposed under /_plugins/_security/api\n    on the OpenSearch cluster.\n  tags:\n  - Opensearch\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: opensearch\n    baseUri: https://localhost:9200\n    description: OpenSearch Security Plugin REST API HTTP API.\n    authentication:\n      type: basic\n      username: '{{OPENSEARCH_USERNAME}}'\n      password: '{{OPENSEARCH_PASSWORD}}'\n    resources:\n    - name: plugins-security-api-account\n      path: /_plugins/_security/api/account\n    \
  \  operations:\n      - name: getaccount\n        method: GET\n        description: Get current user account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: changepassword\n        method: PUT\n        description: Change current user password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-internalusers\n      path: /_plugins/_security/api/internalusers\n      operations:\n      - name: listinternalusers\n        method: GET\n        description: List all internal users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-internalusers-username\n      path: /_plugins/_security/api/internalusers/{username}\n      operations:\n      - name: getinternaluser\n        method: GET\n\
  \        description: Get internal user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorreplaceinternaluser\n        method: PUT\n        description: Create or replace an internal user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteinternaluser\n        method: DELETE\n        description: Delete internal user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchinternaluser\n        method: PATCH\n        description: Patch internal user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-roles\n      path: /_plugins/_security/api/roles\n      operations:\n      - name: listroles\n   \
  \     method: GET\n        description: List all roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-roles-name\n      path: /_plugins/_security/api/roles/{name}\n      operations:\n      - name: getrole\n        method: GET\n        description: Get role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorreplacerole\n        method: PUT\n        description: Create or replace a role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterole\n        method: DELETE\n        description: Delete role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchrole\n        method: PATCH\n        description:\
  \ Patch role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-rolesmapping\n      path: /_plugins/_security/api/rolesmapping\n      operations:\n      - name: listrolemappings\n        method: GET\n        description: List all role mappings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-rolesmapping-name\n      path: /_plugins/_security/api/rolesmapping/{name}\n      operations:\n      - name: getrolemapping\n        method: GET\n        description: Get role mapping\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorreplacerolemapping\n        method: PUT\n        description: Create or replace a role mapping\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deleterolemapping\n        method: DELETE\n        description: Delete role mapping\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchrolemapping\n        method: PATCH\n        description: Patch role mapping\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-actiongroups\n      path: /_plugins/_security/api/actiongroups\n      operations:\n      - name: listactiongroups\n        method: GET\n        description: List all action groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-actiongroups-name\n      path: /_plugins/_security/api/actiongroups/{name}\n      operations:\n      - name:\
  \ getactiongroup\n        method: GET\n        description: Get action group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorreplaceactiongroup\n        method: PUT\n        description: Create or replace an action group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteactiongroup\n        method: DELETE\n        description: Delete action group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchactiongroup\n        method: PATCH\n        description: Patch action group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-tenants\n      path: /_plugins/_security/api/tenants\n      operations:\n\
  \      - name: listtenants\n        method: GET\n        description: List all tenants\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-tenants-name\n      path: /_plugins/_security/api/tenants/{name}\n      operations:\n      - name: gettenant\n        method: GET\n        description: Get tenant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorreplacetenant\n        method: PUT\n        description: Create or replace a tenant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetenant\n        method: DELETE\n        description: Delete tenant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ patchtenant\n        method: PATCH\n        description: Patch tenant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-securityconfig\n      path: /_plugins/_security/api/securityconfig\n      operations:\n      - name: getsecurityconfig\n        method: GET\n        description: Get security configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchsecurityconfig\n        method: PATCH\n        description: Patch security configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-securityconfig-config\n      path: /_plugins/_security/api/securityconfig/config\n      operations:\n      - name: replacesecurityconfig\n        method: PUT\n        description: Replace\
  \ security configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-audit\n      path: /_plugins/_security/api/audit\n      operations:\n      - name: getauditconfig\n        method: GET\n        description: Get audit log configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-audit-config\n      path: /_plugins/_security/api/audit/config\n      operations:\n      - name: replaceauditconfig\n        method: PUT\n        description: Replace audit log configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchauditconfig\n        method: PATCH\n        description: Patch audit log configuration\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-allowlist\n      path: /_plugins/_security/api/allowlist\n      operations:\n      - name: getallowlist\n        method: GET\n        description: Get allowlist\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replaceallowlist\n        method: PUT\n        description: Replace allowlist\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchallowlist\n        method: PATCH\n        description: Patch allowlist\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-nodesdn\n      path: /_plugins/_security/api/nodesdn\n      operations:\n      - name: listnodesdn\n        method: GET\n        description:\
  \ List all node DN entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-nodesdn-name\n      path: /_plugins/_security/api/nodesdn/{name}\n      operations:\n      - name: getnodesdn\n        method: GET\n        description: Get node DN entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorreplacenodesdn\n        method: PUT\n        description: Create or replace node DN entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenodesdn\n        method: DELETE\n        description: Delete node DN entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-ssl-certs\n     \
  \ path: /_plugins/_security/api/ssl/certs\n      operations:\n      - name: getcertificates\n        method: GET\n        description: Get SSL certificates loaded by the cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-ssl-transport-reloadcerts\n      path: /_plugins/_security/api/ssl/transport/reloadcerts\n      operations:\n      - name: reloadtransportcerts\n        method: PUT\n        description: Reload transport-layer SSL certificates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-ssl-http-reloadcerts\n      path: /_plugins/_security/api/ssl/http/reloadcerts\n      operations:\n      - name: reloadhttpcerts\n        method: PUT\n        description: Reload HTTP-layer SSL certificates\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n    - name: plugins-security-api-cache\n      path: /_plugins/_security/api/cache\n      operations:\n      - name: flushsecuritycache\n        method: DELETE\n        description: Flush security cache\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-health\n      path: /_plugins/_security/health\n      operations:\n      - name: securityhealth\n        method: GET\n        description: Security plugin health\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-security-authinfo\n      path: /_plugins/_security/authinfo\n      operations:\n      - name: authinfo\n        method: GET\n        description: Get authentication info for current request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: plugins-security-sslinfo\n      path: /_plugins/_security/sslinfo\n      operations:\n      - name: sslinfo\n        method: GET\n        description: Get SSL handshake info for current request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: opensearch-rest\n    description: REST adapter for OpenSearch Security Plugin REST API.\n    resources:\n    - path: /_plugins/_security/api/account\n      name: getaccount\n      operations:\n      - method: GET\n        name: getaccount\n        description: Get current user account\n        call: opensearch.getaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/account\n      name: changepassword\n      operations:\n      - method: PUT\n        name: changepassword\n        description:\
  \ Change current user password\n        call: opensearch.changepassword\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/internalusers\n      name: listinternalusers\n      operations:\n      - method: GET\n        name: listinternalusers\n        description: List all internal users\n        call: opensearch.listinternalusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/internalusers/{username}\n      name: getinternaluser\n      operations:\n      - method: GET\n        name: getinternaluser\n        description: Get internal user\n        call: opensearch.getinternaluser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/internalusers/{username}\n      name: createorreplaceinternaluser\n      operations:\n      - method: PUT\n        name: createorreplaceinternaluser\n        description: Create or\
  \ replace an internal user\n        call: opensearch.createorreplaceinternaluser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/internalusers/{username}\n      name: deleteinternaluser\n      operations:\n      - method: DELETE\n        name: deleteinternaluser\n        description: Delete internal user\n        call: opensearch.deleteinternaluser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/internalusers/{username}\n      name: patchinternaluser\n      operations:\n      - method: PATCH\n        name: patchinternaluser\n        description: Patch internal user\n        call: opensearch.patchinternaluser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/roles\n      name: listroles\n      operations:\n      - method: GET\n        name: listroles\n        description: List all roles\n        call: opensearch.listroles\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/roles/{name}\n      name: getrole\n      operations:\n      - method: GET\n        name: getrole\n        description: Get role\n        call: opensearch.getrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/roles/{name}\n      name: createorreplacerole\n      operations:\n      - method: PUT\n        name: createorreplacerole\n        description: Create or replace a role\n        call: opensearch.createorreplacerole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/roles/{name}\n      name: deleterole\n      operations:\n      - method: DELETE\n        name: deleterole\n        description: Delete role\n        call: opensearch.deleterole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/roles/{name}\n\
  \      name: patchrole\n      operations:\n      - method: PATCH\n        name: patchrole\n        description: Patch role\n        call: opensearch.patchrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/rolesmapping\n      name: listrolemappings\n      operations:\n      - method: GET\n        name: listrolemappings\n        description: List all role mappings\n        call: opensearch.listrolemappings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/rolesmapping/{name}\n      name: getrolemapping\n      operations:\n      - method: GET\n        name: getrolemapping\n        description: Get role mapping\n        call: opensearch.getrolemapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/rolesmapping/{name}\n      name: createorreplacerolemapping\n      operations:\n      - method: PUT\n     \
  \   name: createorreplacerolemapping\n        description: Create or replace a role mapping\n        call: opensearch.createorreplacerolemapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/rolesmapping/{name}\n      name: deleterolemapping\n      operations:\n      - method: DELETE\n        name: deleterolemapping\n        description: Delete role mapping\n        call: opensearch.deleterolemapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/rolesmapping/{name}\n      name: patchrolemapping\n      operations:\n      - method: PATCH\n        name: patchrolemapping\n        description: Patch role mapping\n        call: opensearch.patchrolemapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/actiongroups\n      name: listactiongroups\n      operations:\n      - method: GET\n        name: listactiongroups\n\
  \        description: List all action groups\n        call: opensearch.listactiongroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/actiongroups/{name}\n      name: getactiongroup\n      operations:\n      - method: GET\n        name: getactiongroup\n        description: Get action group\n        call: opensearch.getactiongroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/actiongroups/{name}\n      name: createorreplaceactiongroup\n      operations:\n      - method: PUT\n        name: createorreplaceactiongroup\n        description: Create or replace an action group\n        call: opensearch.createorreplaceactiongroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/actiongroups/{name}\n      name: deleteactiongroup\n      operations:\n      - method: DELETE\n        name: deleteactiongroup\n \
  \       description: Delete action group\n        call: opensearch.deleteactiongroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/actiongroups/{name}\n      name: patchactiongroup\n      operations:\n      - method: PATCH\n        name: patchactiongroup\n        description: Patch action group\n        call: opensearch.patchactiongroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/tenants\n      name: listtenants\n      operations:\n      - method: GET\n        name: listtenants\n        description: List all tenants\n        call: opensearch.listtenants\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/tenants/{name}\n      name: gettenant\n      operations:\n      - method: GET\n        name: gettenant\n        description: Get tenant\n        call: opensearch.gettenant\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/tenants/{name}\n      name: createorreplacetenant\n      operations:\n      - method: PUT\n        name: createorreplacetenant\n        description: Create or replace a tenant\n        call: opensearch.createorreplacetenant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/tenants/{name}\n      name: deletetenant\n      operations:\n      - method: DELETE\n        name: deletetenant\n        description: Delete tenant\n        call: opensearch.deletetenant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/tenants/{name}\n      name: patchtenant\n      operations:\n      - method: PATCH\n        name: patchtenant\n        description: Patch tenant\n        call: opensearch.patchtenant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/securityconfig\n\
  \      name: getsecurityconfig\n      operations:\n      - method: GET\n        name: getsecurityconfig\n        description: Get security configuration\n        call: opensearch.getsecurityconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/securityconfig\n      name: patchsecurityconfig\n      operations:\n      - method: PATCH\n        name: patchsecurityconfig\n        description: Patch security configuration\n        call: opensearch.patchsecurityconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/securityconfig/config\n      name: replacesecurityconfig\n      operations:\n      - method: PUT\n        name: replacesecurityconfig\n        description: Replace security configuration\n        call: opensearch.replacesecurityconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/audit\n     \
  \ name: getauditconfig\n      operations:\n      - method: GET\n        name: getauditconfig\n        description: Get audit log configuration\n        call: opensearch.getauditconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/audit/config\n      name: replaceauditconfig\n      operations:\n      - method: PUT\n        name: replaceauditconfig\n        description: Replace audit log configuration\n        call: opensearch.replaceauditconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/audit/config\n      name: patchauditconfig\n      operations:\n      - method: PATCH\n        name: patchauditconfig\n        description: Patch audit log configuration\n        call: opensearch.patchauditconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/allowlist\n      name: getallowlist\n      operations:\n\
  \      - method: GET\n        name: getallowlist\n        description: Get allowlist\n        call: opensearch.getallowlist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/allowlist\n      name: replaceallowlist\n      operations:\n      - method: PUT\n        name: replaceallowlist\n        description: Replace allowlist\n        call: opensearch.replaceallowlist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/allowlist\n      name: patchallowlist\n      operations:\n      - method: PATCH\n        name: patchallowlist\n        description: Patch allowlist\n        call: opensearch.patchallowlist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/nodesdn\n      name: listnodesdn\n      operations:\n      - method: GET\n        name: listnodesdn\n        description: List all node DN entries\n        call:\
  \ opensearch.listnodesdn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/nodesdn/{name}\n      name: getnodesdn\n      operations:\n      - method: GET\n        name: getnodesdn\n        description: Get node DN entry\n        call: opensearch.getnodesdn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/nodesdn/{name}\n      name: createorreplacenodesdn\n      operations:\n      - method: PUT\n        name: createorreplacenodesdn\n        description: Create or replace node DN entry\n        call: opensearch.createorreplacenodesdn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/nodesdn/{name}\n      name: deletenodesdn\n      operations:\n      - method: DELETE\n        name: deletenodesdn\n        description: Delete node DN entry\n        call: opensearch.deletenodesdn\n        outputParameters:\n  \
  \      - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/ssl/certs\n      name: getcertificates\n      operations:\n      - method: GET\n        name: getcertificates\n        description: Get SSL certificates loaded by the cluster\n        call: opensearch.getcertificates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/ssl/transport/reloadcerts\n      name: reloadtransportcerts\n      operations:\n      - method: PUT\n        name: reloadtransportcerts\n        description: Reload transport-layer SSL certificates\n        call: opensearch.reloadtransportcerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/ssl/http/reloadcerts\n      name: reloadhttpcerts\n      operations:\n      - method: PUT\n        name: reloadhttpcerts\n        description: Reload HTTP-layer SSL certificates\n        call: opensearch.reloadhttpcerts\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /_plugins/_security/api/cache\n      name: flushsecuritycache\n      operations:\n      - method: DELETE\n        name: flushsecuritycache\n        description: Flush security cache\n        call: opensearch.flushsecuritycache\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/health\n      name: securityhealth\n      operations:\n      - method: GET\n        name: securityhealth\n        description: Security plugin health\n        call: opensearch.securityhealth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/authinfo\n      name: authinfo\n      operations:\n      - method: GET\n        name: authinfo\n        description: Get authentication info for current request\n        call: opensearch.authinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /_plugins/_security/sslinfo\n\
  \      name: sslinfo\n      operations:\n      - method: GET\n        name: sslinfo\n        description: Get SSL handshake info for current request\n        call: opensearch.sslinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: opensearch-mcp\n    transport: http\n    description: MCP adapter for OpenSearch Security Plugin REST API for AI agent use.\n    tools:\n    - name: getaccount\n      description: Get current user account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: opensearch.getaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: changepassword\n      description: Change current user password\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: opensearch.changepassword\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinternalusers\n\
  \      description: List all internal users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: opensearch.listinternalusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinternaluser\n      description: Get internal user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: opensearch.getinternaluser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorreplaceinternaluser\n      description: Create or replace an internal user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: opensearch.createorreplaceinternaluser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteinternaluser\n      description: Delete internal user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call:\
  \ opensearch.deleteinternaluser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchinternaluser\n      description: Patch internal user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: opensearch.patchinternaluser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listroles\n      description: List all roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: opensearch.listroles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrole\n      description: Get role\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: opensearch.getrole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorreplacerole\n      description: Create or replace a role\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: true\n      call: opensearch.createorreplacerole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterole\n      description: Delete role\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: opensearch.deleterole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchrole\n      description: Patch role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: opensearch.patchrole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrolemappings\n      description: List all role mappings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: opensearch.listrolemappings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrolemapping\n      description: Get role mapping\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: opensearch.getrolemapping\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorreplacerolemapping\n      description: Create or replace a role mapping\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: opensearch.createorreplacerolemapping\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterolemapping\n      description: Delete role mapping\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: opensearch.deleterolemapping\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchr\n\n# --- truncated at 32 KB (40 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/opensearch/refs/heads/main/capabilities/opensearch-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/opensearch/refs/heads/main/capabilities/opensearch-capability.yaml
tags:
- Opensearch
- API
tools:
- description: Get current user account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccount
- description: Change current user password
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: changepassword
- description: List all internal users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinternalusers
- description: Get internal user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinternaluser
- description: Create or replace an internal user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createorreplaceinternaluser
- description: Delete internal user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteinternaluser
- description: Patch internal user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchinternaluser
- description: List all roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroles
- description: Get role
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrole
- description: Create or replace a role
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createorreplacerole
- description: Delete role
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterole
- description: Patch role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchrole
- description: List all role mappings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrolemappings
- description: Get role mapping
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrolemapping
- description: Create or replace a role mapping
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createorreplacerolemapping
- description: Delete role mapping
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterolemapping
- description: Patch role mapping
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchrolemapping
- description: List all action groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listactiongroups
- description: Get action group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getactiongroup
- description: Create or replace an action group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createorreplaceactiongroup
- description: Delete action group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteactiongroup
- description: Patch action group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchactiongroup
- description: List all tenants
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtenants
- description: Get tenant
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettenant
- description: Create or replace a tenant
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createorreplacetenant
- description: Delete tenant
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetenant
- description: Patch tenant
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchtenant
- description: Get security configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsecurityconfig
- description: Patch security configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchsecurityconfig
- description: Replace security configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacesecurityconfig
- description: Get audit log configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauditconfig
- description: Replace audit log configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replaceauditconfig
- description: Patch audit log configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchauditconfig
- description: Get allowlist
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallowlist
- description: Replace allowlist
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replaceallowlist
- description: Patch allowlist
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchallowlist
- description: List all node DN entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnodesdn
- description: Get node DN entry
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnodesdn
- description: Create or replace node DN entry
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createorreplacenodesdn
- description: Delete node DN entry
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenodesdn
- description: Get SSL certificates loaded by the cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcertificates
- description: Reload transport-layer SSL certificates
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: reloadtransportcerts
- description: Reload HTTP-layer SSL certificates
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: reloadhttpcerts
- description: Flush security cache
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: flushsecuritycache
- description: Security plugin health
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: securityhealth
- description: Get authentication info for current request
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: authinfo
- description: Get SSL handshake info for current request
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: sslinfo
---
