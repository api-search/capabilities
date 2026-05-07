---
categories: []
consumed_apis: []
description: The Admin SDK Directory API enables management of users, groups, devices, organizational units, roles, domains, and other directory resources in a Google Workspace domain.
layout: capability
name: Google Admin SDK Directory API
operations:
- description: Google Admin SDK List users
  method: GET
  name: listusers
  path: /admin/directory/v1/users
- description: Google Admin SDK Create user
  method: POST
  name: createuser
  path: /admin/directory/v1/users
- description: Google Admin SDK Get user
  method: GET
  name: getuser
  path: /admin/directory/v1/users/{userKey}
- description: Google Admin SDK Update user
  method: PUT
  name: updateuser
  path: /admin/directory/v1/users/{userKey}
- description: Google Admin SDK Patch user
  method: PATCH
  name: patchuser
  path: /admin/directory/v1/users/{userKey}
- description: Google Admin SDK Delete user
  method: DELETE
  name: deleteuser
  path: /admin/directory/v1/users/{userKey}
- description: Google Admin SDK Make user admin
  method: POST
  name: makeuseradmin
  path: /admin/directory/v1/users/{userKey}/makeAdmin
- description: Google Admin SDK List groups
  method: GET
  name: listgroups
  path: /admin/directory/v1/groups
- description: Google Admin SDK Create group
  method: POST
  name: creategroup
  path: /admin/directory/v1/groups
- description: Google Admin SDK Get group
  method: GET
  name: getgroup
  path: /admin/directory/v1/groups/{groupKey}
- description: Google Admin SDK Update group
  method: PUT
  name: updategroup
  path: /admin/directory/v1/groups/{groupKey}
- description: Google Admin SDK Delete group
  method: DELETE
  name: deletegroup
  path: /admin/directory/v1/groups/{groupKey}
- description: Google Admin SDK List group members
  method: GET
  name: listmembers
  path: /admin/directory/v1/groups/{groupKey}/members
- description: Google Admin SDK Add group member
  method: POST
  name: addmember
  path: /admin/directory/v1/groups/{groupKey}/members
- description: Google Admin SDK List organizational units
  method: GET
  name: listorgunits
  path: /admin/directory/v1/customer/{customerId}/orgunits
- description: Google Admin SDK Create organizational unit
  method: POST
  name: createorgunit
  path: /admin/directory/v1/customer/{customerId}/orgunits
- description: Google Admin SDK List Chrome OS devices
  method: GET
  name: listchromeosdevices
  path: /admin/directory/v1/customer/{customerId}/devices/chromeos
- description: Google Admin SDK List mobile devices
  method: GET
  name: listmobiledevices
  path: /admin/directory/v1/customer/{customerId}/devices/mobile
- description: Google Admin SDK List roles
  method: GET
  name: listroles
  path: /admin/directory/v1/customer/{customerId}/roles
- description: Google Admin SDK List domains
  method: GET
  name: listdomains
  path: /admin/directory/v1/customer/{customer}/domains
personas: []
provider_name: Google Admin SDK
provider_slug: google-admin-sdk
search_terms:
- google admin sdk list organizational units
- addmember
- google admin sdk update group
- listmobiledevices
- admin
- users
- listchromeosdevices
- google admin sdk update user
- creategroup
- sdk
- api
- listorgunits
- google admin sdk delete user
- createorgunit
- directory
- google
- getuser
- google admin sdk patch user
- getgroup
- listgroups
- deleteuser
- listmembers
- google admin sdk make user admin
- google admin sdk add group member
- administration
- updategroup
- google admin sdk list roles
- google admin sdk create user
- groups
- enterprise
- updateuser
- google admin sdk list chrome os devices
- devices
- google admin sdk list groups
- google admin sdk list users
- google admin sdk get user
- patchuser
- google admin sdk create organizational unit
- google admin sdk get group
- createuser
- google admin sdk list group members
- listroles
- listusers
- google workspace
- makeuseradmin
- listdomains
- google admin sdk list mobile devices
- google admin sdk create group
- google admin sdk list domains
- deletegroup
- google admin sdk delete group
slug: google-admin-sdk-capability
source_filename: google-admin-sdk-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Admin SDK Directory API\n  description: The Admin SDK Directory API enables management of users, groups, devices, organizational units, roles, domains,\n    and other directory resources in a Google Workspace domain.\n  tags:\n  - Google\n  - Admin\n  - Sdk\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-admin-sdk\n    baseUri: https://admin.googleapis.com\n    description: Google Admin SDK Directory API HTTP API.\n    resources:\n    - name: admin-directory-v1-users\n      path: /admin/directory/v1/users\n      operations:\n      - name: listusers\n        method: GET\n        description: Google Admin SDK List users\n        inputParameters:\n        - name: domain\n          in: query\n          type: string\n        - name: customer\n          in: query\n          type: string\n        - name: maxResults\n          in: query\n          type: integer\n\
  \        - name: pageToken\n          in: query\n          type: string\n        - name: query\n          in: query\n          type: string\n        - name: orderBy\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: Google Admin SDK Create user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-directory-v1-users-userkey\n      path: /admin/directory/v1/users/{userKey}\n      operations:\n      - name: getuser\n        method: GET\n        description: Google Admin SDK Get user\n        inputParameters:\n        - name: userKey\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: updateuser\n        method: PUT\n        description: Google Admin SDK Update user\n        inputParameters:\n        - name: userKey\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchuser\n        method: PATCH\n        description: Google Admin SDK Patch user\n        inputParameters:\n        - name: userKey\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Google Admin SDK Delete user\n        inputParameters:\n        - name: userKey\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: admin-directory-v1-users-userkey-makeadmin\n      path: /admin/directory/v1/users/{userKey}/makeAdmin\n      operations:\n      - name: makeuseradmin\n        method: POST\n        description: Google Admin SDK Make user admin\n        inputParameters:\n        - name: userKey\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-directory-v1-groups\n      path: /admin/directory/v1/groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: Google Admin SDK List groups\n        inputParameters:\n        - name: domain\n          in: query\n          type: string\n        - name: customer\n          in: query\n          type: string\n        - name: maxResults\n          in: query\n          type: integer\n        - name:\
  \ pageToken\n          in: query\n          type: string\n        - name: userKey\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method: POST\n        description: Google Admin SDK Create group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-directory-v1-groups-groupkey\n      path: /admin/directory/v1/groups/{groupKey}\n      operations:\n      - name: getgroup\n        method: GET\n        description: Google Admin SDK Get group\n        inputParameters:\n        - name: groupKey\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategroup\n        method: PUT\n       \
  \ description: Google Admin SDK Update group\n        inputParameters:\n        - name: groupKey\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegroup\n        method: DELETE\n        description: Google Admin SDK Delete group\n        inputParameters:\n        - name: groupKey\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-directory-v1-groups-groupkey-members\n      path: /admin/directory/v1/groups/{groupKey}/members\n      operations:\n      - name: listmembers\n        method: GET\n        description: Google Admin SDK List group members\n        inputParameters:\n        - name: groupKey\n          in: path\n          type: string\n          required:\
  \ true\n        - name: maxResults\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addmember\n        method: POST\n        description: Google Admin SDK Add group member\n        inputParameters:\n        - name: groupKey\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-directory-v1-customer-customerid-orgunits\n      path: /admin/directory/v1/customer/{customerId}/orgunits\n      operations:\n      - name: listorgunits\n        method: GET\n        description: Google Admin SDK List organizational units\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorgunit\n        method: POST\n        description: Google Admin SDK Create organizational unit\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-directory-v1-customer-customerid-devices-c\n      path: /admin/directory/v1/customer/{customerId}/devices/chromeos\n      operations:\n      - name: listchromeosdevices\n        method: GET\n        description: Google Admin SDK List Chrome OS devices\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n        - name: maxResults\n          in: query\n          type: integer\n        - name: pageToken\n\
  \          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-directory-v1-customer-customerid-devices-m\n      path: /admin/directory/v1/customer/{customerId}/devices/mobile\n      operations:\n      - name: listmobiledevices\n        method: GET\n        description: Google Admin SDK List mobile devices\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n        - name: maxResults\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-directory-v1-customer-customerid-roles\n      path: /admin/directory/v1/customer/{customerId}/roles\n      operations:\n      - name: listroles\n  \
  \      method: GET\n        description: Google Admin SDK List roles\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-directory-v1-customer-customer-domains\n      path: /admin/directory/v1/customer/{customer}/domains\n      operations:\n      - name: listdomains\n        method: GET\n        description: Google Admin SDK List domains\n        inputParameters:\n        - name: customer\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-admin-sdk-rest\n    description: REST adapter for Google Admin SDK Directory API.\n    resources:\n    - path: /admin/directory/v1/users\n\
  \      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: Google Admin SDK List users\n        call: google-admin-sdk.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/users\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: Google Admin SDK Create user\n        call: google-admin-sdk.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/users/{userKey}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Google Admin SDK Get user\n        call: google-admin-sdk.getuser\n        with:\n          userKey: rest.userKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/users/{userKey}\n      name: updateuser\n      operations:\n      - method:\
  \ PUT\n        name: updateuser\n        description: Google Admin SDK Update user\n        call: google-admin-sdk.updateuser\n        with:\n          userKey: rest.userKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/users/{userKey}\n      name: patchuser\n      operations:\n      - method: PATCH\n        name: patchuser\n        description: Google Admin SDK Patch user\n        call: google-admin-sdk.patchuser\n        with:\n          userKey: rest.userKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/users/{userKey}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: Google Admin SDK Delete user\n        call: google-admin-sdk.deleteuser\n        with:\n          userKey: rest.userKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/users/{userKey}/makeAdmin\n\
  \      name: makeuseradmin\n      operations:\n      - method: POST\n        name: makeuseradmin\n        description: Google Admin SDK Make user admin\n        call: google-admin-sdk.makeuseradmin\n        with:\n          userKey: rest.userKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/groups\n      name: listgroups\n      operations:\n      - method: GET\n        name: listgroups\n        description: Google Admin SDK List groups\n        call: google-admin-sdk.listgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/groups\n      name: creategroup\n      operations:\n      - method: POST\n        name: creategroup\n        description: Google Admin SDK Create group\n        call: google-admin-sdk.creategroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/groups/{groupKey}\n      name: getgroup\n    \
  \  operations:\n      - method: GET\n        name: getgroup\n        description: Google Admin SDK Get group\n        call: google-admin-sdk.getgroup\n        with:\n          groupKey: rest.groupKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/groups/{groupKey}\n      name: updategroup\n      operations:\n      - method: PUT\n        name: updategroup\n        description: Google Admin SDK Update group\n        call: google-admin-sdk.updategroup\n        with:\n          groupKey: rest.groupKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/groups/{groupKey}\n      name: deletegroup\n      operations:\n      - method: DELETE\n        name: deletegroup\n        description: Google Admin SDK Delete group\n        call: google-admin-sdk.deletegroup\n        with:\n          groupKey: rest.groupKey\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /admin/directory/v1/groups/{groupKey}/members\n      name: listmembers\n      operations:\n      - method: GET\n        name: listmembers\n        description: Google Admin SDK List group members\n        call: google-admin-sdk.listmembers\n        with:\n          groupKey: rest.groupKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/groups/{groupKey}/members\n      name: addmember\n      operations:\n      - method: POST\n        name: addmember\n        description: Google Admin SDK Add group member\n        call: google-admin-sdk.addmember\n        with:\n          groupKey: rest.groupKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/customer/{customerId}/orgunits\n      name: listorgunits\n      operations:\n      - method: GET\n        name: listorgunits\n        description: Google Admin SDK List organizational units\n        call: google-admin-sdk.listorgunits\n\
  \        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/customer/{customerId}/orgunits\n      name: createorgunit\n      operations:\n      - method: POST\n        name: createorgunit\n        description: Google Admin SDK Create organizational unit\n        call: google-admin-sdk.createorgunit\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/customer/{customerId}/devices/chromeos\n      name: listchromeosdevices\n      operations:\n      - method: GET\n        name: listchromeosdevices\n        description: Google Admin SDK List Chrome OS devices\n        call: google-admin-sdk.listchromeosdevices\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/customer/{customerId}/devices/mobile\n\
  \      name: listmobiledevices\n      operations:\n      - method: GET\n        name: listmobiledevices\n        description: Google Admin SDK List mobile devices\n        call: google-admin-sdk.listmobiledevices\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/customer/{customerId}/roles\n      name: listroles\n      operations:\n      - method: GET\n        name: listroles\n        description: Google Admin SDK List roles\n        call: google-admin-sdk.listroles\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/customer/{customer}/domains\n      name: listdomains\n      operations:\n      - method: GET\n        name: listdomains\n        description: Google Admin SDK List domains\n        call: google-admin-sdk.listdomains\n        with:\n          customer: rest.customer\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-admin-sdk-mcp\n    transport: http\n    description: MCP adapter for Google Admin SDK Directory API for AI agent use.\n    tools:\n    - name: listusers\n      description: Google Admin SDK List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-admin-sdk.listusers\n      with:\n        domain: tools.domain\n        customer: tools.customer\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n        query: tools.query\n        orderBy: tools.orderBy\n      inputParameters:\n      - name: domain\n        type: string\n        description: domain\n      - name: customer\n        type: string\n        description: customer\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n        description: pageToken\n\
  \      - name: query\n        type: string\n        description: query\n      - name: orderBy\n        type: string\n        description: orderBy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createuser\n      description: Google Admin SDK Create user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-admin-sdk.createuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: Google Admin SDK Get user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-admin-sdk.getuser\n      with:\n        userKey: tools.userKey\n      inputParameters:\n      - name: userKey\n        type: string\n        description: userKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateuser\n      description: Google Admin SDK Update user\n  \
  \    hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-admin-sdk.updateuser\n      with:\n        userKey: tools.userKey\n      inputParameters:\n      - name: userKey\n        type: string\n        description: userKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchuser\n      description: Google Admin SDK Patch user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-admin-sdk.patchuser\n      with:\n        userKey: tools.userKey\n      inputParameters:\n      - name: userKey\n        type: string\n        description: userKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuser\n      description: Google Admin SDK Delete user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-admin-sdk.deleteuser\n\
  \      with:\n        userKey: tools.userKey\n      inputParameters:\n      - name: userKey\n        type: string\n        description: userKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: makeuseradmin\n      description: Google Admin SDK Make user admin\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-admin-sdk.makeuseradmin\n      with:\n        userKey: tools.userKey\n      inputParameters:\n      - name: userKey\n        type: string\n        description: userKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgroups\n      description: Google Admin SDK List groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-admin-sdk.listgroups\n      with:\n        domain: tools.domain\n        customer: tools.customer\n        maxResults: tools.maxResults\n\
  \        pageToken: tools.pageToken\n        userKey: tools.userKey\n      inputParameters:\n      - name: domain\n        type: string\n        description: domain\n      - name: customer\n        type: string\n        description: customer\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: userKey\n        type: string\n        description: userKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategroup\n      description: Google Admin SDK Create group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-admin-sdk.creategroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgroup\n      description: Google Admin SDK Get group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-admin-sdk.getgroup\n\
  \      with:\n        groupKey: tools.groupKey\n      inputParameters:\n      - name: groupKey\n        type: string\n        description: groupKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updategroup\n      description: Google Admin SDK Update group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-admin-sdk.updategroup\n      with:\n        groupKey: tools.groupKey\n      inputParameters:\n      - name: groupKey\n        type: string\n        description: groupKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletegroup\n      description: Google Admin SDK Delete group\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-admin-sdk.deletegroup\n      with:\n        groupKey: tools.groupKey\n      inputParameters:\n      - name: groupKey\n    \
  \    type: string\n        description: groupKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmembers\n      description: Google Admin SDK List group members\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-admin-sdk.listmembers\n      with:\n        groupKey: tools.groupKey\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: groupKey\n        type: string\n        description: groupKey\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addmember\n      description: Google Admin SDK Add group member\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: google-admin-sdk.addmember\n      with:\n        groupKey: tools.groupKey\n      inputParameters:\n      - name: groupKey\n        type: string\n        description: groupKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorgunits\n      description: Google Admin SDK List organizational units\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-admin-sdk.listorgunits\n      with:\n        customerId: tools.customerId\n      inputParameters:\n      - name: customerId\n        type: string\n        description: customerId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorgunit\n      description: Google Admin SDK Create organizational unit\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-admin-sdk.createorgunit\n      with:\n    \
  \    customerId: tools.customerId\n      inputParameters:\n      - name: customerId\n        type: string\n        description: customerId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listchromeosdevices\n      description: Google Admin SDK List Chrome OS devices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-admin-sdk.listchromeosdevices\n      with:\n        customerId: tools.customerId\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: customerId\n        type: string\n        description: customerId\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmobiledevices\n      description:\
  \ Google Admin SDK List mobile devices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-admin-sdk.listmobiledevices\n      with:\n        customerId: tools.customerId\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: customerId\n        type: string\n        description: customerId\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listroles\n      description: Google Admin SDK List roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-admin-sdk.listroles\n      with:\n        customerId: tools.customerId\n      inputParameters:\n      - name: customerId\n        type: string\n        description:\
  \ customerId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdomains\n      description: Google Admin SDK List domains\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-admin-sdk.listdomains\n      with:\n        customer: tools.customer\n      inputParameters:\n      - name: customer\n        type: string\n        description: customer\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-admin-sdk/refs/heads/main/capabilities/google-admin-sdk-capability.yaml
tags:
- Google
- Admin
- Sdk
- API
tools:
- description: Google Admin SDK List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Google Admin SDK Create user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Google Admin SDK Get user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Google Admin SDK Update user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateuser
- description: Google Admin SDK Patch user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchuser
- description: Google Admin SDK Delete user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: Google Admin SDK Make user admin
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: makeuseradmin
- description: Google Admin SDK List groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: Google Admin SDK Create group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: Google Admin SDK Get group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroup
- description: Google Admin SDK Update group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updategroup
- description: Google Admin SDK Delete group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroup
- description: Google Admin SDK List group members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmembers
- description: Google Admin SDK Add group member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addmember
- description: Google Admin SDK List organizational units
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorgunits
- description: Google Admin SDK Create organizational unit
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorgunit
- description: Google Admin SDK List Chrome OS devices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchromeosdevices
- description: Google Admin SDK List mobile devices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmobiledevices
- description: Google Admin SDK List roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroles
- description: Google Admin SDK List domains
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdomains
---
