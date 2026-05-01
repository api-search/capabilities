---
categories: []
consumed_apis:
- zones-mgmt
description: Unified zone lifecycle workflow combining zone creation, configuration, administration, monitoring, and migration. Used by system administrators and platform engineers to manage Solaris virtualization infrastructure.
layout: capability
name: Solaris Zone Lifecycle Management
operations:
- description: List all zones.
  method: GET
  name: list-zones
  path: /v1/zones
- description: Create a new zone.
  method: POST
  name: create-zone
  path: /v1/zones
- description: Get zone details.
  method: GET
  name: get-zone
  path: /v1/zones/{zoneName}
- description: Delete a zone.
  method: DELETE
  name: delete-zone
  path: /v1/zones/{zoneName}
- description: Get current zone state.
  method: GET
  name: get-zone-state
  path: /v1/zones/{zoneName}/state
- description: Boot the zone.
  method: POST
  name: boot-zone
  path: /v1/zones/{zoneName}/boot
- description: Gracefully shutdown.
  method: POST
  name: shutdown-zone
  path: /v1/zones/{zoneName}/shutdown
- description: Reboot the zone.
  method: POST
  name: reboot-zone
  path: /v1/zones/{zoneName}/reboot
- description: Migrate to another host.
  method: POST
  name: migrate-zone
  path: /v1/zones/{zoneName}/migrate
personas: []
provider_name: Solaris Zones
provider_slug: solaris-zones
search_terms:
- zones
- migrate a zone to another host.
- zone inventory and creation.
- reboot zone
- get zone details.
- create a new zone.
- gracefully shutdown a zone.
- zone state operations.
- reboot a solaris zone.
- clone a solaris zone.
- delete a solaris zone.
- migrate a zone.
- gracefully shutdown.
- get solaris zone details.
- containers
- individual zone operations.
- halt a zone immediately.
- operating systems
- migrate zone
- uninstall a solaris zone.
- install zone
- list all solaris zones with status.
- verify zone
- rad
- get zone
- statsstore
- boot zone
- kernel zones
- create a new solaris zone.
- verify zone configuration integrity.
- lifecycle management
- shutdown zone
- reboot the zone.
- get current zone state.
- uninstall zone
- install a solaris zone.
- clone zone
- boot a solaris zone.
- resource management
- delete zone
- shutdown a zone.
- reboot a zone.
- list zones
- oracle
- boot a zone.
- boot the zone.
- virtualization
- migrate to another host.
- list all zones.
- create zone
- delete a zone.
- halt zone
- solaris
- get zone state
slug: zone-lifecycle
source_filename: zone-lifecycle.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Solaris Zone Lifecycle Management\"\n  description: \"Unified zone lifecycle workflow combining zone creation, configuration, administration, monitoring, and migration. Used by system administrators and platform engineers to manage Solaris virtualization infrastructure.\"\n  tags:\n    - Solaris\n    - Zones\n    - Virtualization\n    - Lifecycle Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SOLARIS_AUTH_TOKEN: SOLARIS_AUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: zones-mgmt\n      location: ./shared/zones-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: solaris-lifecycle-api\n      description: \"Unified REST API for Solaris zone lifecycle management.\"\n      resources:\n        - path: /v1/zones\n          name: zones\n          description: \"Zone inventory and creation.\"\n          operations:\n            - method:\
  \ GET\n              name: list-zones\n              description: \"List all zones.\"\n              call: \"zones-mgmt.list-zone-info\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-zone\n              description: \"Create a new zone.\"\n              call: \"zones-mgmt.create-zone\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/zones/{zoneName}\n          name: zone-detail\n          description: \"Individual zone operations.\"\n          operations:\n            - method: GET\n              name: get-zone\n              description: \"Get zone details.\"\n              call: \"zones-mgmt.get-zone\"\n              with:\n                zoneName: \"rest.zoneName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n       \
  \       name: delete-zone\n              description: \"Delete a zone.\"\n              call: \"zones-mgmt.delete-zone\"\n              with:\n                zoneName: \"rest.zoneName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/zones/{zoneName}/state\n          name: zone-state\n          description: \"Zone state operations.\"\n          operations:\n            - method: GET\n              name: get-zone-state\n              description: \"Get current zone state.\"\n              call: \"zones-mgmt.get-zone-state\"\n              with:\n                zoneName: \"rest.zoneName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/zones/{zoneName}/boot\n          name: zone-boot\n          description: \"Boot a zone.\"\n          operations:\n            - method: POST\n              name: boot-zone\n              description: \"Boot the\
  \ zone.\"\n              call: \"zones-mgmt.boot-zone\"\n              with:\n                zoneName: \"rest.zoneName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/zones/{zoneName}/shutdown\n          name: zone-shutdown\n          description: \"Shutdown a zone.\"\n          operations:\n            - method: POST\n              name: shutdown-zone\n              description: \"Gracefully shutdown.\"\n              call: \"zones-mgmt.shutdown-zone\"\n              with:\n                zoneName: \"rest.zoneName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/zones/{zoneName}/reboot\n          name: zone-reboot\n          description: \"Reboot a zone.\"\n          operations:\n            - method: POST\n              name: reboot-zone\n              description: \"Reboot the zone.\"\n              call: \"zones-mgmt.reboot-zone\"\n\
  \              with:\n                zoneName: \"rest.zoneName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/zones/{zoneName}/migrate\n          name: zone-migrate\n          description: \"Migrate a zone.\"\n          operations:\n            - method: POST\n              name: migrate-zone\n              description: \"Migrate to another host.\"\n              call: \"zones-mgmt.migrate-zone\"\n              with:\n                zoneName: \"rest.zoneName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: solaris-lifecycle-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Solaris zone lifecycle management.\"\n      tools:\n        - name: list-zones\n          description: \"List all Solaris zones with status.\"\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n          call: \"zones-mgmt.list-zone-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-zone\n          description: \"Create a new Solaris zone.\"\n          hints:\n            readOnly: false\n          call: \"zones-mgmt.create-zone\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-zone\n          description: \"Get Solaris zone details.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zones-mgmt.get-zone\"\n          with:\n            zoneName: \"tools.zoneName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-zone-state\n          description: \"Get current zone state.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zones-mgmt.get-zone-state\"\n          with:\n            zoneName: \"tools.zoneName\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: boot-zone\n          description: \"Boot a Solaris zone.\"\n          hints:\n            readOnly: false\n          call: \"zones-mgmt.boot-zone\"\n          with:\n            zoneName: \"tools.zoneName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: halt-zone\n          description: \"Halt a zone immediately.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"zones-mgmt.halt-zone\"\n          with:\n            zoneName: \"tools.zoneName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: shutdown-zone\n          description: \"Gracefully shutdown a zone.\"\n          hints:\n            readOnly: false\n          call: \"zones-mgmt.shutdown-zone\"\n          with:\n            zoneName: \"tools.zoneName\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: reboot-zone\n          description: \"Reboot a Solaris zone.\"\n          hints:\n            readOnly: false\n          call: \"zones-mgmt.reboot-zone\"\n          with:\n            zoneName: \"tools.zoneName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: install-zone\n          description: \"Install a Solaris zone.\"\n          hints:\n            readOnly: false\n          call: \"zones-mgmt.install-zone\"\n          with:\n            zoneName: \"tools.zoneName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: uninstall-zone\n          description: \"Uninstall a Solaris zone.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"zones-mgmt.uninstall-zone\"\n          with:\n            zoneName: \"tools.zoneName\"\n          outputParameters:\n \
  \           - type: object\n              mapping: \"$.\"\n        - name: clone-zone\n          description: \"Clone a Solaris zone.\"\n          hints:\n            readOnly: false\n          call: \"zones-mgmt.clone-zone\"\n          with:\n            zoneName: \"tools.zoneName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: migrate-zone\n          description: \"Migrate a zone to another host.\"\n          hints:\n            readOnly: false\n          call: \"zones-mgmt.migrate-zone\"\n          with:\n            zoneName: \"tools.zoneName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: verify-zone\n          description: \"Verify zone configuration integrity.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zones-mgmt.verify-zone\"\n          with:\n            zoneName: \"tools.zoneName\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: delete-zone\n          description: \"Delete a Solaris zone.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"zones-mgmt.delete-zone\"\n          with:\n            zoneName: \"tools.zoneName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/solaris-zones/refs/heads/main/capabilities/zone-lifecycle.yaml
tags:
- Solaris
- Zones
- Virtualization
- Lifecycle Management
tools:
- description: List all Solaris zones with status.
  hints:
    idempotent: true
    readOnly: true
  name: list-zones
- description: Create a new Solaris zone.
  hints:
    readOnly: false
  name: create-zone
- description: Get Solaris zone details.
  hints:
    idempotent: true
    readOnly: true
  name: get-zone
- description: Get current zone state.
  hints:
    idempotent: true
    readOnly: true
  name: get-zone-state
- description: Boot a Solaris zone.
  hints:
    readOnly: false
  name: boot-zone
- description: Halt a zone immediately.
  hints:
    destructive: true
    readOnly: false
  name: halt-zone
- description: Gracefully shutdown a zone.
  hints:
    readOnly: false
  name: shutdown-zone
- description: Reboot a Solaris zone.
  hints:
    readOnly: false
  name: reboot-zone
- description: Install a Solaris zone.
  hints:
    readOnly: false
  name: install-zone
- description: Uninstall a Solaris zone.
  hints:
    destructive: true
    readOnly: false
  name: uninstall-zone
- description: Clone a Solaris zone.
  hints:
    readOnly: false
  name: clone-zone
- description: Migrate a zone to another host.
  hints:
    readOnly: false
  name: migrate-zone
- description: Verify zone configuration integrity.
  hints:
    idempotent: true
    readOnly: true
  name: verify-zone
- description: Delete a Solaris zone.
  hints:
    destructive: true
    readOnly: false
  name: delete-zone
---
