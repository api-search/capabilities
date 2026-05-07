---
categories: []
consumed_apis: []
description: The etcd HTTP/JSON gateway translates HTTP requests into gRPC calls, enabling clients without gRPC support to interact with the etcd v3 key-value store. The gateway exposes the full etcd v3 API surface including key-value operations (put, get, delete, range queries), watch streams for change notifications, lease management for TTL-based key expiration, cluster membership management, maintenance operations such as snapshots and defragmentation, and authentication and authorization controls. The gateway is served on port 2379 by default and accepts JSON-encoded request bodies that mirror the pro
layout: capability
name: etcd HTTP Gateway API
operations:
- description: Etcd Put a key-value pair
  method: POST
  name: kvput
  path: /kv/put
- description: Etcd Get a range of key-value pairs
  method: POST
  name: kvrange
  path: /kv/range
- description: Etcd Delete a range of key-value pairs
  method: POST
  name: kvdeleterange
  path: /kv/deleterange
- description: Etcd Execute a transaction
  method: POST
  name: kvtxn
  path: /kv/txn
- description: Etcd Compact the event history
  method: POST
  name: kvcompact
  path: /kv/compaction
- description: Etcd Watch for key change events
  method: POST
  name: watchevents
  path: /watch
- description: Etcd Grant a lease
  method: POST
  name: leasegrant
  path: /lease/grant
- description: Etcd Revoke a lease
  method: POST
  name: leaserevoke
  path: /lease/revoke
- description: Etcd Renew a lease
  method: POST
  name: leasekeepalive
  path: /lease/keepalive
- description: Etcd Get lease time to live
  method: POST
  name: leasetimetolive
  path: /lease/timetolive
- description: Etcd List all leases
  method: POST
  name: leaseleases
  path: /lease/leases
- description: Etcd Add a member to the cluster
  method: POST
  name: clustermemberadd
  path: /cluster/member/add
- description: Etcd Remove a member from the cluster
  method: POST
  name: clustermemberremove
  path: /cluster/member/remove
- description: Etcd Update a cluster member
  method: POST
  name: clustermemberupdate
  path: /cluster/member/update
- description: Etcd List cluster members
  method: POST
  name: clustermemberlist
  path: /cluster/member/list
- description: Etcd Promote a learner member
  method: POST
  name: clustermemberpromote
  path: /cluster/member/promote
- description: Etcd Stream a database snapshot
  method: POST
  name: maintenancesnapshot
  path: /maintenance/snapshot
- description: Etcd Defragment a member's backend
  method: POST
  name: maintenancedefragment
  path: /maintenance/defragment
- description: Etcd Get member status
  method: POST
  name: maintenancestatus
  path: /maintenance/status
- description: Etcd Manage cluster alarms
  method: POST
  name: maintenancealarm
  path: /maintenance/alarm
- description: Etcd Get member backend hash
  method: POST
  name: maintenancehash
  path: /maintenance/hash
- description: Etcd Transfer cluster leadership
  method: POST
  name: maintenancetransferleadership
  path: /maintenance/transfer-leadership
- description: Etcd Enable authentication
  method: POST
  name: authenable
  path: /auth/enable
- description: Etcd Disable authentication
  method: POST
  name: authdisable
  path: /auth/disable
- description: Etcd Authenticate a user
  method: POST
  name: authauthenticate
  path: /auth/authenticate
- description: Etcd Add a user
  method: POST
  name: authuseradd
  path: /auth/user/add
- description: Etcd Get user details
  method: POST
  name: authuserget
  path: /auth/user/get
- description: Etcd Delete a user
  method: POST
  name: authuserdelete
  path: /auth/user/delete
- description: Etcd List all users
  method: POST
  name: authuserlist
  path: /auth/user/list
- description: Etcd Change a user's password
  method: POST
  name: authuserchangepassword
  path: /auth/user/changepw
- description: Etcd Grant a role to a user
  method: POST
  name: authusergrantrole
  path: /auth/user/grant
- description: Etcd Revoke a role from a user
  method: POST
  name: authuserrevokerole
  path: /auth/user/revoke
- description: Etcd Add a role
  method: POST
  name: authroleadd
  path: /auth/role/add
- description: Etcd Get role details
  method: POST
  name: authroleget
  path: /auth/role/get
- description: Etcd Delete a role
  method: POST
  name: authroledelete
  path: /auth/role/delete
- description: Etcd List all roles
  method: POST
  name: authrolelist
  path: /auth/role/list
- description: Etcd Grant a permission to a role
  method: POST
  name: authrolegrantpermission
  path: /auth/role/grant
- description: Etcd Revoke a permission from a role
  method: POST
  name: authrolerevokepermission
  path: /auth/role/revoke
personas: []
provider_name: Etcd
provider_slug: etcd
search_terms:
- etcd renew a lease
- authrolerevokepermission
- distributed systems
- kvput
- etcd get a range of key-value pairs
- api
- authrolegrantpermission
- etcd list all roles
- kvtxn
- etcd get user details
- etcd manage cluster alarms
- etcd compact the event history
- authuseradd
- etcd add a role
- etcd get member status
- authuserrevokerole
- etcd update a cluster member
- leasegrant
- etcd revoke a role from a user
- authuserlist
- leaserevoke
- etcd delete a range of key-value pairs
- authroleadd
- etcd grant a permission to a role
- etcd delete a user
- cloud native
- etcd enable authentication
- authdisable
- etcd put a key-value pair
- maintenancehash
- etcd promote a learner member
- authauthenticate
- etcd grant a lease
- etcd transfer cluster leadership
- maintenancetransferleadership
- clustermemberremove
- leasekeepalive
- authuserdelete
- authenable
- etcd disable authentication
- authusergrantrole
- etcd add a member to the cluster
- maintenancestatus
- etcd change a user's password
- kvrange
- authroleget
- kvcompact
- watchevents
- etcd delete a role
- authuserget
- kubernetes
- maintenancesnapshot
- clustermemberlist
- etcd stream a database snapshot
- etcd list all users
- authrolelist
- etcd list cluster members
- leasetimetolive
- etcd add a user
- etcd authenticate a user
- maintenancedefragment
- clustermemberupdate
- etcd get member backend hash
- maintenancealarm
- consensus
- etcd revoke a permission from a role
- etcd get role details
- etcd revoke a lease
- graduated
- clustermemberpromote
- leaseleases
- etcd remove a member from the cluster
- etcd
- authuserchangepassword
- etcd defragment a member's backend
- etcd get lease time to live
- kvdeleterange
- etcd grant a role to a user
- etcd watch for key change events
- etcd list all leases
- key-value store
- clustermemberadd
- authroledelete
- etcd execute a transaction
slug: etcd-capability
source_filename: etcd-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: etcd HTTP Gateway API\n  description: The etcd HTTP/JSON gateway translates HTTP requests into gRPC calls, enabling clients without gRPC support\n    to interact with the etcd v3 key-value store. The gateway exposes the full etcd v3 API surface including key-value operations\n    (put, get, delete, range queries), watch streams for change notifications, lease management for TTL-based key expiration,\n    cluster membership management, maintenance operations such as snapshots and defragmentation, and authentication and authorization\n    controls. The gateway is served on port 2379 by default and accepts JSON-encoded request bodies that mirror the pro\n  tags:\n  - Etcd\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: etcd\n    baseUri: http://localhost:2379/v3\n    description: etcd HTTP Gateway API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ETCD_TOKEN}}'\n\
  \    resources:\n    - name: kv-put\n      path: /kv/put\n      operations:\n      - name: kvput\n        method: POST\n        description: Etcd Put a key-value pair\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kv-range\n      path: /kv/range\n      operations:\n      - name: kvrange\n        method: POST\n        description: Etcd Get a range of key-value pairs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kv-deleterange\n      path: /kv/deleterange\n      operations:\n      - name: kvdeleterange\n        method: POST\n        description: Etcd Delete a range of key-value pairs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kv-txn\n      path: /kv/txn\n      operations:\n      - name: kvtxn\n        method:\
  \ POST\n        description: Etcd Execute a transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kv-compaction\n      path: /kv/compaction\n      operations:\n      - name: kvcompact\n        method: POST\n        description: Etcd Compact the event history\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: watch\n      path: /watch\n      operations:\n      - name: watchevents\n        method: POST\n        description: Etcd Watch for key change events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lease-grant\n      path: /lease/grant\n      operations:\n      - name: leasegrant\n        method: POST\n        description: Etcd Grant a lease\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: lease-revoke\n      path: /lease/revoke\n      operations:\n      - name: leaserevoke\n        method: POST\n        description: Etcd Revoke a lease\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lease-keepalive\n      path: /lease/keepalive\n      operations:\n      - name: leasekeepalive\n        method: POST\n        description: Etcd Renew a lease\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lease-timetolive\n      path: /lease/timetolive\n      operations:\n      - name: leasetimetolive\n        method: POST\n        description: Etcd Get lease time to live\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lease-leases\n      path: /lease/leases\n\
  \      operations:\n      - name: leaseleases\n        method: POST\n        description: Etcd List all leases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster-member-add\n      path: /cluster/member/add\n      operations:\n      - name: clustermemberadd\n        method: POST\n        description: Etcd Add a member to the cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster-member-remove\n      path: /cluster/member/remove\n      operations:\n      - name: clustermemberremove\n        method: POST\n        description: Etcd Remove a member from the cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster-member-update\n      path: /cluster/member/update\n      operations:\n      - name: clustermemberupdate\n\
  \        method: POST\n        description: Etcd Update a cluster member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster-member-list\n      path: /cluster/member/list\n      operations:\n      - name: clustermemberlist\n        method: POST\n        description: Etcd List cluster members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster-member-promote\n      path: /cluster/member/promote\n      operations:\n      - name: clustermemberpromote\n        method: POST\n        description: Etcd Promote a learner member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: maintenance-snapshot\n      path: /maintenance/snapshot\n      operations:\n      - name: maintenancesnapshot\n        method: POST\n        description:\
  \ Etcd Stream a database snapshot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: maintenance-defragment\n      path: /maintenance/defragment\n      operations:\n      - name: maintenancedefragment\n        method: POST\n        description: Etcd Defragment a member's backend\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: maintenance-status\n      path: /maintenance/status\n      operations:\n      - name: maintenancestatus\n        method: POST\n        description: Etcd Get member status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: maintenance-alarm\n      path: /maintenance/alarm\n      operations:\n      - name: maintenancealarm\n        method: POST\n        description: Etcd Manage cluster alarms\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: maintenance-hash\n      path: /maintenance/hash\n      operations:\n      - name: maintenancehash\n        method: POST\n        description: Etcd Get member backend hash\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: maintenance-transfer-leadership\n      path: /maintenance/transfer-leadership\n      operations:\n      - name: maintenancetransferleadership\n        method: POST\n        description: Etcd Transfer cluster leadership\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-enable\n      path: /auth/enable\n      operations:\n      - name: authenable\n        method: POST\n        description: Etcd Enable authentication\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: auth-disable\n      path: /auth/disable\n      operations:\n      - name: authdisable\n        method: POST\n        description: Etcd Disable authentication\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-authenticate\n      path: /auth/authenticate\n      operations:\n      - name: authauthenticate\n        method: POST\n        description: Etcd Authenticate a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-user-add\n      path: /auth/user/add\n      operations:\n      - name: authuseradd\n        method: POST\n        description: Etcd Add a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-user-get\n      path:\
  \ /auth/user/get\n      operations:\n      - name: authuserget\n        method: POST\n        description: Etcd Get user details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-user-delete\n      path: /auth/user/delete\n      operations:\n      - name: authuserdelete\n        method: POST\n        description: Etcd Delete a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-user-list\n      path: /auth/user/list\n      operations:\n      - name: authuserlist\n        method: POST\n        description: Etcd List all users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-user-changepw\n      path: /auth/user/changepw\n      operations:\n      - name: authuserchangepassword\n        method: POST\n   \
  \     description: Etcd Change a user's password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-user-grant\n      path: /auth/user/grant\n      operations:\n      - name: authusergrantrole\n        method: POST\n        description: Etcd Grant a role to a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-user-revoke\n      path: /auth/user/revoke\n      operations:\n      - name: authuserrevokerole\n        method: POST\n        description: Etcd Revoke a role from a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-role-add\n      path: /auth/role/add\n      operations:\n      - name: authroleadd\n        method: POST\n        description: Etcd Add a role\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-role-get\n      path: /auth/role/get\n      operations:\n      - name: authroleget\n        method: POST\n        description: Etcd Get role details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-role-delete\n      path: /auth/role/delete\n      operations:\n      - name: authroledelete\n        method: POST\n        description: Etcd Delete a role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-role-list\n      path: /auth/role/list\n      operations:\n      - name: authrolelist\n        method: POST\n        description: Etcd List all roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-role-grant\n\
  \      path: /auth/role/grant\n      operations:\n      - name: authrolegrantpermission\n        method: POST\n        description: Etcd Grant a permission to a role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-role-revoke\n      path: /auth/role/revoke\n      operations:\n      - name: authrolerevokepermission\n        method: POST\n        description: Etcd Revoke a permission from a role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: etcd-rest\n    description: REST adapter for etcd HTTP Gateway API.\n    resources:\n    - path: /kv/put\n      name: kvput\n      operations:\n      - method: POST\n        name: kvput\n        description: Etcd Put a key-value pair\n        call: etcd.kvput\n        outputParameters:\n        - type: object\n      \
  \    mapping: $.\n    - path: /kv/range\n      name: kvrange\n      operations:\n      - method: POST\n        name: kvrange\n        description: Etcd Get a range of key-value pairs\n        call: etcd.kvrange\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kv/deleterange\n      name: kvdeleterange\n      operations:\n      - method: POST\n        name: kvdeleterange\n        description: Etcd Delete a range of key-value pairs\n        call: etcd.kvdeleterange\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kv/txn\n      name: kvtxn\n      operations:\n      - method: POST\n        name: kvtxn\n        description: Etcd Execute a transaction\n        call: etcd.kvtxn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kv/compaction\n      name: kvcompact\n      operations:\n      - method: POST\n        name: kvcompact\n        description: Etcd Compact the event history\n\
  \        call: etcd.kvcompact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /watch\n      name: watchevents\n      operations:\n      - method: POST\n        name: watchevents\n        description: Etcd Watch for key change events\n        call: etcd.watchevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lease/grant\n      name: leasegrant\n      operations:\n      - method: POST\n        name: leasegrant\n        description: Etcd Grant a lease\n        call: etcd.leasegrant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lease/revoke\n      name: leaserevoke\n      operations:\n      - method: POST\n        name: leaserevoke\n        description: Etcd Revoke a lease\n        call: etcd.leaserevoke\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lease/keepalive\n      name: leasekeepalive\n      operations:\n      - method:\
  \ POST\n        name: leasekeepalive\n        description: Etcd Renew a lease\n        call: etcd.leasekeepalive\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lease/timetolive\n      name: leasetimetolive\n      operations:\n      - method: POST\n        name: leasetimetolive\n        description: Etcd Get lease time to live\n        call: etcd.leasetimetolive\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lease/leases\n      name: leaseleases\n      operations:\n      - method: POST\n        name: leaseleases\n        description: Etcd List all leases\n        call: etcd.leaseleases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cluster/member/add\n      name: clustermemberadd\n      operations:\n      - method: POST\n        name: clustermemberadd\n        description: Etcd Add a member to the cluster\n        call: etcd.clustermemberadd\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /cluster/member/remove\n      name: clustermemberremove\n      operations:\n      - method: POST\n        name: clustermemberremove\n        description: Etcd Remove a member from the cluster\n        call: etcd.clustermemberremove\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cluster/member/update\n      name: clustermemberupdate\n      operations:\n      - method: POST\n        name: clustermemberupdate\n        description: Etcd Update a cluster member\n        call: etcd.clustermemberupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cluster/member/list\n      name: clustermemberlist\n      operations:\n      - method: POST\n        name: clustermemberlist\n        description: Etcd List cluster members\n        call: etcd.clustermemberlist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cluster/member/promote\n\
  \      name: clustermemberpromote\n      operations:\n      - method: POST\n        name: clustermemberpromote\n        description: Etcd Promote a learner member\n        call: etcd.clustermemberpromote\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /maintenance/snapshot\n      name: maintenancesnapshot\n      operations:\n      - method: POST\n        name: maintenancesnapshot\n        description: Etcd Stream a database snapshot\n        call: etcd.maintenancesnapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /maintenance/defragment\n      name: maintenancedefragment\n      operations:\n      - method: POST\n        name: maintenancedefragment\n        description: Etcd Defragment a member's backend\n        call: etcd.maintenancedefragment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /maintenance/status\n      name: maintenancestatus\n      operations:\n  \
  \    - method: POST\n        name: maintenancestatus\n        description: Etcd Get member status\n        call: etcd.maintenancestatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /maintenance/alarm\n      name: maintenancealarm\n      operations:\n      - method: POST\n        name: maintenancealarm\n        description: Etcd Manage cluster alarms\n        call: etcd.maintenancealarm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /maintenance/hash\n      name: maintenancehash\n      operations:\n      - method: POST\n        name: maintenancehash\n        description: Etcd Get member backend hash\n        call: etcd.maintenancehash\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /maintenance/transfer-leadership\n      name: maintenancetransferleadership\n      operations:\n      - method: POST\n        name: maintenancetransferleadership\n        description: Etcd\
  \ Transfer cluster leadership\n        call: etcd.maintenancetransferleadership\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/enable\n      name: authenable\n      operations:\n      - method: POST\n        name: authenable\n        description: Etcd Enable authentication\n        call: etcd.authenable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/disable\n      name: authdisable\n      operations:\n      - method: POST\n        name: authdisable\n        description: Etcd Disable authentication\n        call: etcd.authdisable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/authenticate\n      name: authauthenticate\n      operations:\n      - method: POST\n        name: authauthenticate\n        description: Etcd Authenticate a user\n        call: etcd.authauthenticate\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /auth/user/add\n      name: authuseradd\n      operations:\n      - method: POST\n        name: authuseradd\n        description: Etcd Add a user\n        call: etcd.authuseradd\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/user/get\n      name: authuserget\n      operations:\n      - method: POST\n        name: authuserget\n        description: Etcd Get user details\n        call: etcd.authuserget\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/user/delete\n      name: authuserdelete\n      operations:\n      - method: POST\n        name: authuserdelete\n        description: Etcd Delete a user\n        call: etcd.authuserdelete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/user/list\n      name: authuserlist\n      operations:\n      - method: POST\n        name: authuserlist\n        description: Etcd List all users\n        call: etcd.authuserlist\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/user/changepw\n      name: authuserchangepassword\n      operations:\n      - method: POST\n        name: authuserchangepassword\n        description: Etcd Change a user's password\n        call: etcd.authuserchangepassword\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/user/grant\n      name: authusergrantrole\n      operations:\n      - method: POST\n        name: authusergrantrole\n        description: Etcd Grant a role to a user\n        call: etcd.authusergrantrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/user/revoke\n      name: authuserrevokerole\n      operations:\n      - method: POST\n        name: authuserrevokerole\n        description: Etcd Revoke a role from a user\n        call: etcd.authuserrevokerole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /auth/role/add\n      name: authroleadd\n      operations:\n      - method: POST\n        name: authroleadd\n        description: Etcd Add a role\n        call: etcd.authroleadd\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/role/get\n      name: authroleget\n      operations:\n      - method: POST\n        name: authroleget\n        description: Etcd Get role details\n        call: etcd.authroleget\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/role/delete\n      name: authroledelete\n      operations:\n      - method: POST\n        name: authroledelete\n        description: Etcd Delete a role\n        call: etcd.authroledelete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/role/list\n      name: authrolelist\n      operations:\n      - method: POST\n        name: authrolelist\n        description: Etcd List all roles\n        call: etcd.authrolelist\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/role/grant\n      name: authrolegrantpermission\n      operations:\n      - method: POST\n        name: authrolegrantpermission\n        description: Etcd Grant a permission to a role\n        call: etcd.authrolegrantpermission\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/role/revoke\n      name: authrolerevokepermission\n      operations:\n      - method: POST\n        name: authrolerevokepermission\n        description: Etcd Revoke a permission from a role\n        call: etcd.authrolerevokepermission\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: etcd-mcp\n    transport: http\n    description: MCP adapter for etcd HTTP Gateway API for AI agent use.\n    tools:\n    - name: kvput\n      description: Etcd Put a key-value pair\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: etcd.kvput\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: kvrange\n      description: Etcd Get a range of key-value pairs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.kvrange\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: kvdeleterange\n      description: Etcd Delete a range of key-value pairs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.kvdeleterange\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: kvtxn\n      description: Etcd Execute a transaction\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.kvtxn\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: kvcompact\n      description: Etcd Compact the event history\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.kvcompact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: watchevents\n      description: Etcd Watch for key change events\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.watchevents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: leasegrant\n      description: Etcd Grant a lease\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.leasegrant\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: leaserevoke\n      description: Etcd Revoke a lease\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.leaserevoke\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: leasekeepalive\n\
  \      description: Etcd Renew a lease\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.leasekeepalive\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: leasetimetolive\n      description: Etcd Get lease time to live\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.leasetimetolive\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: leaseleases\n      description: Etcd List all leases\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.leaseleases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clustermemberadd\n      description: Etcd Add a member to the cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.clustermemberadd\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: clustermemberremove\n      description: Etcd Remove a member from the cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.clustermemberremove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clustermemberupdate\n      description: Etcd Update a cluster member\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.clustermemberupdate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clustermemberlist\n      description: Etcd List cluster members\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.clustermemberlist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clustermemberpromote\n      description: Etcd Promote a learner member\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: etcd.clustermemberpromote\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: maintenancesnapshot\n      description: Etcd Stream a database snapshot\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.maintenancesnapshot\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: maintenancedefragment\n      description: Etcd Defragment a member's backend\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.maintenancedefragment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: maintenancestatus\n      description: Etcd Get member status\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.maintenancestatus\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: maintenancealarm\n      description: Etcd Manage cluster alarms\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.maintenancealarm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: maintenancehash\n      description: Etcd Get member backend hash\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.maintenancehash\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: maintenancetransferleadership\n      description: Etcd Transfer cluster leadership\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.maintenancetransferleadership\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authenable\n      description: Etcd Enable authentication\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: etcd.authenable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authdisable\n      description: Etcd Disable authentication\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.authdisable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authauthenticate\n      description: Etcd Authenticate a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.authauthenticate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authuseradd\n      description: Etcd Add a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.authuseradd\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authuserget\n      description: Etcd Get user details\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.authuserget\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authuserdelete\n      description: Etcd Delete a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.authuserdelete\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authuserlist\n      description: Etcd List all users\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.authuserlist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authuserchangepassword\n      description: Etcd Change a user's password\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.authuserchangepassword\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ authusergrantrole\n      description: Etcd Grant a role to a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.authusergrantrole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authuserrevokerole\n      description: Etcd Revoke a role from a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.authuserrevokerole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authroleadd\n      description: Etcd Add a role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.authroleadd\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authroleget\n      description: Etcd Get role details\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.authroleget\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: authroledelete\n      description: Etcd Delete a role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.authroledelete\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authrolelist\n      description: Etcd List all roles\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.authrolelist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authrolegrantpermission\n      description: Etcd Grant a permission to a role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etcd.authrolegrantpermission\n      outputParameters:\n      - type: object\n       \n\n# --- truncated at 32 KB (32 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/etcd/refs/heads/main/capabilities/etcd-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/etcd/refs/heads/main/capabilities/etcd-capability.yaml
tags:
- Etcd
- API
tools:
- description: Etcd Put a key-value pair
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: kvput
- description: Etcd Get a range of key-value pairs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: kvrange
- description: Etcd Delete a range of key-value pairs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: kvdeleterange
- description: Etcd Execute a transaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: kvtxn
- description: Etcd Compact the event history
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: kvcompact
- description: Etcd Watch for key change events
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: watchevents
- description: Etcd Grant a lease
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: leasegrant
- description: Etcd Revoke a lease
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: leaserevoke
- description: Etcd Renew a lease
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: leasekeepalive
- description: Etcd Get lease time to live
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: leasetimetolive
- description: Etcd List all leases
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: leaseleases
- description: Etcd Add a member to the cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: clustermemberadd
- description: Etcd Remove a member from the cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: clustermemberremove
- description: Etcd Update a cluster member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: clustermemberupdate
- description: Etcd List cluster members
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: clustermemberlist
- description: Etcd Promote a learner member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: clustermemberpromote
- description: Etcd Stream a database snapshot
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: maintenancesnapshot
- description: Etcd Defragment a member's backend
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: maintenancedefragment
- description: Etcd Get member status
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: maintenancestatus
- description: Etcd Manage cluster alarms
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: maintenancealarm
- description: Etcd Get member backend hash
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: maintenancehash
- description: Etcd Transfer cluster leadership
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: maintenancetransferleadership
- description: Etcd Enable authentication
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authenable
- description: Etcd Disable authentication
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authdisable
- description: Etcd Authenticate a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authauthenticate
- description: Etcd Add a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authuseradd
- description: Etcd Get user details
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authuserget
- description: Etcd Delete a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authuserdelete
- description: Etcd List all users
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authuserlist
- description: Etcd Change a user's password
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authuserchangepassword
- description: Etcd Grant a role to a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authusergrantrole
- description: Etcd Revoke a role from a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authuserrevokerole
- description: Etcd Add a role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authroleadd
- description: Etcd Get role details
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authroleget
- description: Etcd Delete a role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authroledelete
- description: Etcd List all roles
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authrolelist
- description: Etcd Grant a permission to a role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authrolegrantpermission
- description: Etcd Revoke a permission from a role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authrolerevokepermission
---
