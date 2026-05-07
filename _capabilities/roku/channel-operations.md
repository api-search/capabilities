---
categories: []
consumed_apis: []
description: 'Unified workflow capability for Roku channel teams. Combines the External Control Protocol (local-network device control), Roku Pay Web Services (entitlement validation, refunds, subscriptions), and Roku Nabu Cloud (remote test devices, snapshots, builds) into a single REST and MCP surface. Personas: channel developer, QA engineer, billing operator.'
layout: capability
name: Roku Channel Operations
operations:
- description: Returns device metadata.
  method: GET
  name: get-device-info
  path: /v1/devices
- description: Lists installed channels on the device.
  method: GET
  name: list-installed-apps
  path: /v1/devices
- description: Returns the currently active channel.
  method: GET
  name: get-active-app
  path: /v1/devices
- description: Returns video player state.
  method: GET
  name: get-media-player-state
  path: /v1/devices
- description: Launches an installed channel with optional deep-link.
  method: POST
  name: launch-app
  path: /v1/devices
- description: Sends a remote-control key press.
  method: POST
  name: press-key
  path: /v1/devices
- description: Validates a Roku Pay transaction.
  method: GET
  name: validate-transaction
  path: /v1/entitlements
- description: Validates a Roku Pay refund.
  method: GET
  name: validate-refund
  path: /v1/entitlements
- description: Cancels a Roku Pay subscription.
  method: POST
  name: cancel-subscription
  path: /v1/subscriptions
- description: Issues a subscription refund.
  method: POST
  name: refund-subscription
  path: /v1/subscriptions
- description: Adjusts the subscription billing date.
  method: POST
  name: update-bill-cycle
  path: /v1/subscriptions
- description: Issues an account-level service credit.
  method: POST
  name: issue-service-credit
  path: /v1/subscriptions
- description: Lists Nabu Cloud test devices in a project.
  method: GET
  name: list-test-devices
  path: /v1/test-devices
- description: Allocates a Nabu Cloud test device.
  method: POST
  name: create-test-device
  path: /v1/test-devices
- description: Starts a remote test device run.
  method: POST
  name: start-test-device
  path: /v1/test-devices
- description: Stops a remote test device run.
  method: POST
  name: stop-test-device
  path: /v1/test-devices
- description: Reads logs from a test device run instance.
  method: GET
  name: read-test-device-logs
  path: /v1/test-devices
- description: Lists channel builds.
  method: GET
  name: list-builds
  path: /v1/builds
- description: Returns a single build.
  method: GET
  name: get-build
  path: /v1/builds
personas: []
provider_name: Roku
provider_slug: roku
search_terms:
- issue an account-level service credit.
- nabu read test device logs
- start a nabu cloud test device run.
- allocate a nabu cloud test device.
- launch an installed channel with optional deep-link.
- ecp launch app
- get active app
- read logs from a nabu cloud test device run.
- launches an installed channel with optional deep-link.
- get build
- returns a single build.
- validates a roku pay transaction.
- Billing Operator
- channel development
- launch app
- Channel Developer
- list builds
- issues a subscription refund.
- read test device logs
- refund a roku pay subscription.
- validates roku pay transactions, processes refunds, manages subscriptions, and issues service credits.
- pay validate refund
- list test devices
- nabu list builds
- roku
- confirm a roku pay refund.
- get device info
- issues an account-level service credit.
- pay issue service credit
- subscription lifecycle and billing.
- nabu list test devices
- press key
- list channels installed on the local roku device.
- get media player state
- allocates a nabu cloud test device.
- reads logs from a test device run instance.
- channel builds in nabu cloud.
- ecp get media player state
- cancels a roku pay subscription.
- get channel cpu and memory metrics (developer mode).
- nabu create test device
- runs automated channel certification tests on remote nabu cloud devices and exercises the channel via ecp key injection.
- cancel subscription
- roku pay transaction validation.
- returns device metadata.
- ecp get device info
- pay validate transaction
- monetization
- cancel a roku pay subscription.
- update bill cycle
- adjusts the subscription billing date.
- get the video player state.
- connected tv
- returns video player state.
- lists nabu cloud test devices in a project.
- ecp list installed apps
- sends a remote-control key press.
- get roku device metadata via ecp.
- nabu cloud remote test devices and runs.
- list nabu cloud test devices in a project.
- stops a remote test device run.
- lists channel builds.
- local device control via ecp.
- nabu start test device
- pay update bill cycle
- issue service credit
- list installed apps
- list channel builds in nabu cloud.
- validate transaction
- nabu stop test device
- validate refund
- lists installed channels on the device.
- television
- send a remote-control key press to the device.
- ecp query chanperf
- get a nabu cloud build by id.
- pay refund subscription
- starts a remote test device run.
- suspend or terminate a running channel.
- adjust the next billing date on a subscription.
- stop a nabu cloud test device run.
- streaming
- nabu get build
- ecp press key
- pay cancel subscription
- start test device
- validates a roku pay refund.
- validate a roku pay transaction and return entitlement state.
- ecp get active app
- stop test device
- QA Engineer
- builds and ships roku channels. uses ecp for local-device debugging and nabu cloud for builds and remote test devices.
- test automation
- returns the currently active channel.
- consumer electronics
- ecp exit app
- unified channel developer, qa, and billing workflow combining ecp, roku pay, and nabu cloud.
- entertainment
- get the active channel on the device.
- media
- refund subscription
- create test device
slug: channel-operations
source_filename: channel-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Roku Channel Operations\n  description: 'Unified workflow capability for Roku channel teams. Combines the External Control Protocol\n\n    (local-network device control), Roku Pay Web Services (entitlement validation, refunds,\n\n    subscriptions), and Roku Nabu Cloud (remote test devices, snapshots, builds) into a single\n\n    REST and MCP surface. Personas: channel developer, QA engineer, billing operator.\n\n    '\n  tags:\n  - Roku\n  - Streaming\n  - Channel Development\n  - Test Automation\n  - Monetization\n  created: '2026-05-05'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ROKU_DEVICE_IP: ROKU_DEVICE_IP\n    ROKU_PAY_PARTNER_API_KEY: ROKU_PAY_PARTNER_API_KEY\n    ROKU_NABU_CLOUD_TOKEN: ROKU_NABU_CLOUD_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: roku-ecp\n    baseUri: http://{{ROKU_DEVICE_IP}}:8060\n    description: Roku device on the local network.\n    resources:\n    - name: discovery\n\
  \      path: /\n      description: SSDP device description and metadata.\n      operations:\n      - name: get-device-root\n        method: GET\n        path: /\n        description: Returns the SSDP device description XML.\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: query-device-info\n        method: GET\n        path: /query/device-info\n        description: Returns device metadata (model, serial, software version, network state).\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps\n      path: /query/apps\n      description: Installed channel listing and active-app queries.\n      operations:\n      - name: query-apps\n        method: GET\n        path: /query/apps\n        description: Lists channels installed on the device.\n        outputRawFormat: xml\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: query-active-app\n        method: GET\n        path: /query/active-app\n        description: Returns the currently active channel.\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: query-app-icon\n        method: GET\n        path: /query/icon/{appId}\n        description: Returns the binary icon image for the specified channel.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: Roku channel/app identifier.\n        outputRawFormat: binary\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: launch-app\n        method: POST\n        path: /launch/{appId}\n        description: Launches an installed channel; supports deep-link contentId/mediaType.\n        inputParameters:\n        -\
  \ name: appId\n          in: path\n          type: string\n          required: true\n          description: Roku channel/app identifier.\n        - name: contentId\n          in: query\n          type: string\n          required: false\n          description: Deep-link content identifier.\n        - name: mediaType\n          in: query\n          type: string\n          required: false\n          description: Deep-link content type.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: install-app\n        method: POST\n        path: /install/{appId}\n        description: Opens the channel store details page for the specified channel.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: Roku channel/app identifier.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: exit-app\n      \
  \  method: POST\n        path: /exit-app/{appId}\n        description: Suspends or terminates a running channel (Roku OS 14.1+).\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: Roku channel/app identifier.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: keypress\n      path: /keypress\n      description: Simulated remote-control key injection.\n      operations:\n      - name: key-press\n        method: POST\n        path: /keypress/{key}\n        description: Press-and-release a remote-control key.\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: Key name (Home, Up, Down, Left, Right, Select, Back, Play, etc.) or Lit_<char> for a literal character.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: key-down\n        method: POST\n        path: /keydown/{key}\n        description: Press and hold a remote-control key.\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: Key name.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: key-up\n        method: POST\n        path: /keyup/{key}\n        description: Release a previously held key.\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: Key name.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: media-player\n      path: /query/media-player\n      description: Active video player playback state.\n      operations:\n      - name: query-media-player\n        method: GET\n        path: /query/media-player\n        description:\
  \ Returns playback state, position, duration, and buffering metrics.\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: diagnostics\n      path: /query\n      description: Developer-mode diagnostics (chanperf, sgnodes, registry).\n      operations:\n      - name: query-chanperf\n        method: GET\n        path: /query/chanperf\n        description: CPU and memory metrics for the foreground channel.\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: query-sgnodes-all\n        method: GET\n        path: /query/sgnodes/all\n        description: All SceneGraph nodes with reference counts.\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: query-registry\n        method: GET\n        path: /query/registry/{appId}\n        description:\
  \ Persistent registry entries for the specified channel.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: Roku channel identifier.\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: roku-pay\n    baseUri: https://apipub.roku.com/listen/transaction-service.svc\n    description: Roku Pay production transaction service.\n    authentication:\n      type: apikey\n      key: partnerAPIKey\n      value: '{{ROKU_PAY_PARTNER_API_KEY}}'\n      placement: query\n    resources:\n    - name: validation\n      path: /validate-transaction\n      description: Transaction and refund validation.\n      operations:\n      - name: validate-transaction\n        method: GET\n        path: /validate-transaction/{partnerAPIKey}/{transactionId}\n        description: Verifies a customer's entitlement to a Roku Pay-purchased\
  \ product.\n        inputParameters:\n        - name: partnerAPIKey\n          in: path\n          type: string\n          required: true\n          description: Roku-issued partner API key.\n        - name: transactionId\n          in: path\n          type: string\n          required: true\n          description: Transaction identifier returned by ChannelStore.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: validate-refund\n        method: GET\n        path: /validate-refund/{partnerAPIKey}/{refundId}\n        description: Confirms a refund has been issued.\n        inputParameters:\n        - name: partnerAPIKey\n          in: path\n          type: string\n          required: true\n          description: Roku-issued partner API key.\n        - name: refundId\n          in: path\n          type: string\n          required: true\n          description: Roku-issued refund identifier.\n       \
  \ outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscription\n      path: /cancel-subscription\n      description: Subscription lifecycle management.\n      operations:\n      - name: cancel-subscription\n        method: POST\n        path: /cancel-subscription\n        description: Cancels a Roku Pay subscription.\n        body:\n          type: json\n          data:\n            partnerAPIKey: '{{ROKU_PAY_PARTNER_API_KEY}}'\n            rokuCustomerId: '{{tools.rokuCustomerId}}'\n            productCode: '{{tools.productCode}}'\n            reason: '{{tools.reason}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: refund-subscription\n        method: POST\n        path: /refund-subscription\n        description: Issues a partial or full refund against a subscription.\n        body:\n          type: json\n  \
  \        data:\n            partnerAPIKey: '{{ROKU_PAY_PARTNER_API_KEY}}'\n            rokuCustomerId: '{{tools.rokuCustomerId}}'\n            transactionId: '{{tools.transactionId}}'\n            refundAmount: '{{tools.refundAmount}}'\n            currency: '{{tools.currency}}'\n            reason: '{{tools.reason}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-bill-cycle\n        method: POST\n        path: /update-bill-cycle\n        description: Adjusts the next billing date on an active subscription.\n        body:\n          type: json\n          data:\n            partnerAPIKey: '{{ROKU_PAY_PARTNER_API_KEY}}'\n            rokuCustomerId: '{{tools.rokuCustomerId}}'\n            productCode: '{{tools.productCode}}'\n            nextBillDate: '{{tools.nextBillDate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n      - name: issue-service-credit\n        method: POST\n        path: /issue-service-credit\n        description: Grants an account-level service credit to the customer.\n        body:\n          type: json\n          data:\n            partnerAPIKey: '{{ROKU_PAY_PARTNER_API_KEY}}'\n            rokuCustomerId: '{{tools.rokuCustomerId}}'\n            amount: '{{tools.amount}}'\n            currency: '{{tools.currency}}'\n            reason: '{{tools.reason}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: roku-nabu-cloud\n    baseUri: https://api.cloud.roku.dev\n    description: Roku Nabu Cloud production API.\n    authentication:\n      type: bearer\n      token: '{{ROKU_NABU_CLOUD_TOKEN}}'\n    resources:\n    - name: health\n      path: /api/v1/-\n      description: Service health endpoints.\n      operations:\n      - name: livez\n        method: GET\n  \
  \      path: /api/v1/-/livez\n        description: Liveness probe.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: readyz\n        method: GET\n        path: /api/v1/-/readyz\n        description: Readiness probe.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /api/v1/users/me\n      description: Current user, organisations, projects, groups, and personal access tokens.\n      operations:\n      - name: get-me\n        method: GET\n        path: /api/v1/users/me\n        description: Returns the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-my-organisations\n        method: GET\n        path: /api/v1/users/me/organisations\n        description: Lists organisations the\
  \ user belongs to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-my-projects\n        method: GET\n        path: /api/v1/users/me/projects\n        description: Lists projects the user has access to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-my-groups\n        method: GET\n        path: /api/v1/users/me/groups\n        description: Lists groups the user belongs to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-personal-access-tokens\n        method: GET\n        path: /api/v1/users/me/personal_access_tokens\n        description: Lists the user's personal access tokens.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: create-personal-access-token\n        method: POST\n        path: /api/v1/users/me/personal_access_tokens\n        description: Creates a new personal access token.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            scopes: '{{tools.scopes}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: revoke-personal-access-token\n        method: DELETE\n        path: /api/v1/users/me/personal_access_tokens/{token_id}\n        description: Revokes a personal access token.\n        inputParameters:\n        - name: token_id\n          in: path\n          type: string\n          required: true\n          description: Token identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: builds\n      path: /api/v1/builds\n      description: Channel builds.\n\
  \      operations:\n      - name: list-builds\n        method: GET\n        path: /api/v1/builds\n        description: Lists all builds visible to the caller.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-build\n        method: GET\n        path: /api/v1/builds/{build_id}\n        description: Returns a single build by id.\n        inputParameters:\n        - name: build_id\n          in: path\n          type: string\n          required: true\n          description: Build identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /api/v1/organisations/{organisation_id}/projects\n      description: Project lifecycle inside an organisation.\n      operations:\n      - name: list-projects\n        method: GET\n        path: /api/v1/organisations/{organisation_id}/projects\n   \
  \     description: Lists projects in an organisation.\n        inputParameters:\n        - name: organisation_id\n          in: path\n          type: string\n          required: true\n          description: Organisation identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        path: /api/v1/organisations/{organisation_id}/projects\n        description: Creates a project.\n        inputParameters:\n        - name: organisation_id\n          in: path\n          type: string\n          required: true\n          description: Organisation identifier.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-project\n        method:\
  \ GET\n        path: /api/v1/organisations/{organisation_id}/projects/{project_id}\n        description: Returns a single project.\n        inputParameters:\n        - name: organisation_id\n          in: path\n          type: string\n          required: true\n          description: Organisation identifier.\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: Project identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-project\n        method: DELETE\n        path: /api/v1/organisations/{organisation_id}/projects/{project_id}\n        description: Deletes a project.\n        inputParameters:\n        - name: organisation_id\n          in: path\n          type: string\n          required: true\n          description: Organisation identifier.\n        - name: project_id\n          in: path\n          type: string\n\
  \          required: true\n          description: Project identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devices\n      path: /api/v1/organisations/{organisation_id}/projects/{project_id}/devices\n      description: Remote test device lifecycle and runs.\n      operations:\n      - name: list-devices\n        method: GET\n        path: /api/v1/organisations/{organisation_id}/projects/{project_id}/devices\n        description: Lists devices in a project.\n        inputParameters:\n        - name: organisation_id\n          in: path\n          type: string\n          required: true\n          description: Organisation identifier.\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: Project identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n      - name: create-device\n        method: POST\n        path: /api/v1/organisations/{organisation_id}/projects/{project_id}/devices\n        description: Allocates a new test device.\n        inputParameters:\n        - name: organisation_id\n          in: path\n          type: string\n          required: true\n          description: Organisation identifier.\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: Project identifier.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            region: '{{tools.region}}'\n            model: '{{tools.model}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-device\n        method: GET\n        path: /api/v1/organisations/{organisation_id}/projects/{project_id}/devices/{device_id}\n        description: Returns a single device.\n\
  \        inputParameters:\n        - name: organisation_id\n          in: path\n          type: string\n          required: true\n          description: Organisation identifier.\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: Project identifier.\n        - name: device_id\n          in: path\n          type: string\n          required: true\n          description: Device identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-device\n        method: POST\n        path: /api/v1/organisations/{organisation_id}/projects/{project_id}/devices/{device_id}/start\n        description: Starts a device run.\n        inputParameters:\n        - name: organisation_id\n          in: path\n          type: string\n          required: true\n          description: Organisation identifier.\n        - name: project_id\n         \
  \ in: path\n          type: string\n          required: true\n          description: Project identifier.\n        - name: device_id\n          in: path\n          type: string\n          required: true\n          description: Device identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-device\n        method: POST\n        path: /api/v1/organisations/{organisation_id}/projects/{project_id}/devices/{device_id}/stop\n        description: Stops a device run.\n        inputParameters:\n        - name: organisation_id\n          in: path\n          type: string\n          required: true\n          description: Organisation identifier.\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: Project identifier.\n        - name: device_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Device identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: read-device-logs\n        method: GET\n        path: /api/v1/organisations/{organisation_id}/projects/{project_id}/devices/{device_id}/logs/{instance_id}\n        description: Reads logs for a device run instance.\n        inputParameters:\n        - name: organisation_id\n          in: path\n          type: string\n          required: true\n          description: Organisation identifier.\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: Project identifier.\n        - name: device_id\n          in: path\n          type: string\n          required: true\n          description: Device identifier.\n        - name: instance_id\n          in: path\n          type: string\n          required: true\n          description: Run instance identifier.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: snapshots\n      path: /api/v1/organisations/{organisation_id}/projects/{project_id}/devices/{device_id}/snapshots\n      description: Device snapshot management.\n      operations:\n      - name: list-snapshots\n        method: GET\n        path: /api/v1/organisations/{organisation_id}/projects/{project_id}/devices/{device_id}/snapshots\n        description: Lists snapshots for a device.\n        inputParameters:\n        - name: organisation_id\n          in: path\n          type: string\n          required: true\n          description: Organisation identifier.\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: Project identifier.\n        - name: device_id\n          in: path\n          type: string\n          required: true\n          description: Device identifier.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-snapshot\n        method: POST\n        path: /api/v1/organisations/{organisation_id}/projects/{project_id}/devices/{device_id}/snapshots\n        description: Creates a snapshot of a device.\n        inputParameters:\n        - name: organisation_id\n          in: path\n          type: string\n          required: true\n          description: Organisation identifier.\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: Project identifier.\n        - name: device_id\n          in: path\n          type: string\n          required: true\n          description: Device identifier.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ delete-snapshot\n        method: DELETE\n        path: /api/v1/organisations/{organisation_id}/projects/{project_id}/devices/{device_id}/snapshots/{snapshot_id}\n        description: Deletes a snapshot.\n        inputParameters:\n        - name: organisation_id\n          in: path\n          type: string\n          required: true\n          description: Organisation identifier.\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: Project identifier.\n        - name: device_id\n          in: path\n          type: string\n          required: true\n          description: Device identifier.\n        - name: snapshot_id\n          in: path\n          type: string\n          required: true\n          description: Snapshot identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: roku-channel-operations-api\n\
  \    description: Unified REST API for Roku channel operations.\n    resources:\n    - path: /v1/devices\n      name: devices\n      description: Local device control via ECP.\n      operations:\n      - method: GET\n        name: get-device-info\n        description: Returns device metadata.\n        call: roku-ecp.query-device-info\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-installed-apps\n        description: Lists installed channels on the device.\n        call: roku-ecp.query-apps\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-active-app\n        description: Returns the currently active channel.\n        call: roku-ecp.query-active-app\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-media-player-state\n        description: Returns video player state.\n        call: roku-ecp.query-media-player\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: launch-app\n        description: Launches an installed channel with optional deep-link.\n        call: roku-ecp.launch-app\n        with:\n          appId: rest.appId\n          contentId: rest.contentId\n          mediaType: rest.mediaType\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: press-key\n        description: Sends a remote-control key press.\n        call: roku-ecp.key-press\n        with:\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entitlements\n      name: entitlements\n      description: Roku Pay transaction validation.\n      operations:\n      - method: GET\n        name: validate-transaction\n        description: Validates a Roku Pay transaction.\n        call: roku-pay.validate-transaction\n        with:\n          partnerAPIKey:\
  \ rest.partnerAPIKey\n          transactionId: rest.transactionId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: validate-refund\n        description: Validates a Roku Pay refund.\n        call: roku-pay.validate-refund\n        with:\n          partnerAPIKey: rest.partnerAPIKey\n          refundId: rest.refundId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscriptions\n      name: subscriptions\n      description: Subscription lifecycle and billing.\n      operations:\n      - method: POST\n        name: cancel-subscription\n        description: Cancels a Roku Pay subscription.\n        call: roku-pay.cancel-subscription\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: refund-subscription\n        description: Issues a subscription refund.\n        call: roku-pay.refund-subscription\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n      - method: POST\n        name: update-bill-cycle\n        description: Adjusts the subscription billing date.\n        call: roku-pay.update-bill-cycle\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: issue-service-credit\n        description: Issues an account-level service credit.\n        call: roku-pay.issue-service-credit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/test-devices\n      name: test-devices\n      description: Nabu Cloud remote test devices and runs.\n      operations:\n      - method: GET\n        name: list-test-devices\n        description: Lists Nabu Cloud test devices in a project.\n        call: roku-nabu-cloud.list-devices\n        with:\n          organisation_id: rest.organisation_id\n          project_id: rest.project_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      -\
  \ method: POST\n        name: create-test-device\n        description: Allocates a Nabu Cloud test device.\n        call: roku-nabu-cloud.create-device\n        with:\n          organisation_id: rest.organisation_id\n          project_id: rest.project_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: start-test-device\n        description: Starts a remote test device run.\n        call: roku-nabu-cloud.start-device\n        with:\n          organisation_id: rest.organisation_id\n          project_id: rest.project_id\n          device_id: rest.device_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: stop-test-device\n        description: Stops a remote test device run.\n        call: roku-nabu-cloud.stop-device\n        with:\n          organisation_id: rest.organisation_id\n          project_id: rest.project_id\n          device_id: rest.device_id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: GET\n        name: read-test-device-logs\n        description: Reads logs from a test device run instance.\n        call: roku-nabu-cloud.read-device-logs\n        with:\n          organisation_id: rest.organisation_id\n          project_id: rest.project_id\n          device_id: rest.device_id\n          instance_id: rest.instance_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/builds\n      name: builds\n      description: Channel builds in Nabu Cloud.\n      operations:\n      - method: GET\n        name: list-builds\n        description: Lists channel builds.\n        call: roku-nabu-cloud.list-builds\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-build\n        description: Returns a single build.\n        call: roku-nabu-cloud.get-build\n        with:\n          build_id: rest.build_id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: roku-channel-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted Roku channel development, QA, and billing workflows.\n    tools:\n    - name: ecp-get-device-info\n      description: Get Roku device metadata via ECP.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: roku-ecp.query-device-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ecp-list-installed-apps\n      description: List channels installed on the local Roku device.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: roku-ecp.query-apps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ecp-get-active-app\n      description: Get the active channel on the device.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: roku-ecp.query-active-app\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: ecp-get-media-player-state\n      description: Get the video player state.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: roku-ecp.query-media-player\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ecp-launch-app\n      description: Launch an installed channel with optional deep-link.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n        openWorld: true\n      call: roku-ecp.launch-app\n      with:\n        appId: tools.appId\n        contentId: tools.contentId\n        mediaType: tools.mediaType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ecp-press-k\n\n# --- truncated at 32 KB (37 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/roku/refs/heads/main/capabilities/channel-operations.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/roku/refs/heads/main/capabilities/channel-operations.yaml
tags:
- Roku
- Streaming
- Channel Development
- Test Automation
- Monetization
tools:
- description: Get Roku device metadata via ECP.
  hints:
    openWorld: true
    readOnly: true
  name: ecp-get-device-info
- description: List channels installed on the local Roku device.
  hints:
    openWorld: true
    readOnly: true
  name: ecp-list-installed-apps
- description: Get the active channel on the device.
  hints:
    openWorld: true
    readOnly: true
  name: ecp-get-active-app
- description: Get the video player state.
  hints:
    openWorld: true
    readOnly: true
  name: ecp-get-media-player-state
- description: Launch an installed channel with optional deep-link.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: ecp-launch-app
- description: Send a remote-control key press to the device.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: ecp-press-key
- description: Suspend or terminate a running channel.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: ecp-exit-app
- description: Get channel CPU and memory metrics (developer mode).
  hints:
    openWorld: true
    readOnly: true
  name: ecp-query-chanperf
- description: Validate a Roku Pay transaction and return entitlement state.
  hints:
    openWorld: true
    readOnly: true
  name: pay-validate-transaction
- description: Confirm a Roku Pay refund.
  hints:
    openWorld: true
    readOnly: true
  name: pay-validate-refund
- description: Cancel a Roku Pay subscription.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: pay-cancel-subscription
- description: Refund a Roku Pay subscription.
  hints:
    destructive: true
    idempotent: false
    openWorld: true
    readOnly: false
  name: pay-refund-subscription
- description: Adjust the next billing date on a subscription.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: pay-update-bill-cycle
- description: Issue an account-level service credit.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: pay-issue-service-credit
- description: List Nabu Cloud test devices in a project.
  hints:
    openWorld: true
    readOnly: true
  name: nabu-list-test-devices
- description: Allocate a Nabu Cloud test device.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: nabu-create-test-device
- description: Start a Nabu Cloud test device run.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: nabu-start-test-device
- description: Stop a Nabu Cloud test device run.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: nabu-stop-test-device
- description: Read logs from a Nabu Cloud test device run.
  hints:
    openWorld: true
    readOnly: true
  name: nabu-read-test-device-logs
- description: List channel builds in Nabu Cloud.
  hints:
    openWorld: true
    readOnly: true
  name: nabu-list-builds
- description: Get a Nabu Cloud build by id.
  hints:
    openWorld: true
    readOnly: true
  name: nabu-get-build
---
