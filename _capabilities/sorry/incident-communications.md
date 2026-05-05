---
api_specs:
- filename: sorry-status-page-openapi.yml
  format: yaml
  label: sorry-api
  slug: sorry-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sorry/refs/heads/main/openapi/sorry-status-page-openapi.yml
categories: []
consumed_apis:
- sorry-api
description: Unified capability for automated incident communication workflows using the Sorry™ API. Enables DevOps and support teams to programmatically manage status pages, publish incident notices, post updates as incidents evolve, and manage subscriber notifications during service disruptions and maintenance windows.
layout: capability
name: Sorry Incident Communications
operations:
- description: List all status pages in the account
  method: GET
  name: list-pages
  path: /v1/pages
- description: Create a new status page
  method: POST
  name: create-page
  path: /v1/pages
- description: List components for a status page
  method: GET
  name: list-components
  path: /v1/pages/{page_id}/components
- description: Add a component to a status page
  method: POST
  name: create-component
  path: /v1/pages/{page_id}/components
- description: List all notices for a status page
  method: GET
  name: list-notices
  path: /v1/pages/{page_id}/notices
- description: Create an incident or maintenance notice
  method: POST
  name: create-notice
  path: /v1/pages/{page_id}/notices
- description: List all updates for a notice
  method: GET
  name: list-notice-updates
  path: /v1/pages/{page_id}/notices/{notice_id}/updates
- description: Publish an update to an active incident notice
  method: POST
  name: create-notice-update
  path: /v1/pages/{page_id}/notices/{notice_id}/updates
- description: List all subscribers for a status page
  method: GET
  name: list-subscribers
  path: /v1/pages/{page_id}/subscribers
- description: Add a subscriber to a status page
  method: POST
  name: create-subscriber
  path: /v1/pages/{page_id}/subscribers
personas: []
provider_name: Sorry
provider_slug: sorry
search_terms:
- subscriber management
- component management
- create notice update
- incident management
- list all status pages in the account
- create incident notice
- incident status updates
- create component
- create an incident or maintenance notice
- status pages
- list status pages
- list all updates for a notice
- publish an update to an active incident notice
- list subscribers for a status page. use to understand notification reach before publishing a major incident notice.
- create a new status page
- list all subscribers for a status page
- developer tools
- list all components for a status page. use to identify affected components before creating incident notices.
- add subscriber
- update incident state
- publish a new status update to an existing incident notice. use to keep customers informed as the incident investigation progresses.
- devops
- list subscribers
- customer communication
- status page management
- create notice
- publish incident update
- add a new subscriber to receive status page notifications via email or sms.
- notifications
- add a component to a status page
- create page
- create an incident notice on a status page to notify customers of an unplanned outage or service degradation. use for incident declaration.
- sorry
- list notices
- create subscriber
- monitoring
- list notice updates
- list all notices for a status page. use to find active incidents or review recent maintenance windows.
- update the state or details of an existing incident notice. use to progress an incident through monitoring, resolved, or completed states.
- add a subscriber to a status page
- list all status pages in the sorry account. use to find page ids for subsequent operations during incident response.
- list all notices for a status page
- incident and maintenance notices
- list pages
- list components for a status page
- list components
slug: incident-communications
source_filename: incident-communications.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sorry Incident Communications\"\n  description: >-\n    Unified capability for automated incident communication workflows using the\n    Sorry™ API. Enables DevOps and support teams to programmatically manage status\n    pages, publish incident notices, post updates as incidents evolve, and manage\n    subscriber notifications during service disruptions and maintenance windows.\n  tags:\n    - Sorry\n    - Status Pages\n    - Incident Management\n    - Notifications\n    - Customer Communication\n    - DevOps\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SORRY_BEARER_TOKEN: SORRY_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: sorry-api\n      location: ./shared/sorry-status-page.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sorry-incident-comms-api\n      description: \"Unified REST API for automated incident communication workflows via\
  \ Sorry.\"\n      resources:\n        - path: /v1/pages\n          name: pages\n          description: Status page management\n          operations:\n            - method: GET\n              name: list-pages\n              description: List all status pages in the account\n              call: \"sorry-api.list-pages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-page\n              description: Create a new status page\n              call: \"sorry-api.create-page\"\n              with:\n                name: \"rest.name\"\n                timezone: \"rest.timezone\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pages/{page_id}/components\n          name: components\n          description: Component management\n          operations:\n            - method: GET\n              name: list-components\n   \
  \           description: List components for a status page\n              call: \"sorry-api.list-components\"\n              with:\n                page_id: \"rest.page_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-component\n              description: Add a component to a status page\n              call: \"sorry-api.create-component\"\n              with:\n                page_id: \"rest.page_id\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pages/{page_id}/notices\n          name: notices\n          description: Incident and maintenance notices\n          operations:\n            - method: GET\n              name: list-notices\n              description: List all notices for a status page\n              call: \"sorry-api.list-notices\"\n              with:\n\
  \                page_id: \"rest.page_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-notice\n              description: Create an incident or maintenance notice\n              call: \"sorry-api.create-notice\"\n              with:\n                page_id: \"rest.page_id\"\n                type: \"rest.type\"\n                subject: \"rest.subject\"\n                initial_comment: \"rest.initial_comment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pages/{page_id}/notices/{notice_id}/updates\n          name: notice-updates\n          description: Incident status updates\n          operations:\n            - method: GET\n              name: list-notice-updates\n              description: List all updates for a notice\n              call: \"sorry-api.list-notice-updates\"\n              with:\n\
  \                page_id: \"rest.page_id\"\n                notice_id: \"rest.notice_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-notice-update\n              description: Publish an update to an active incident notice\n              call: \"sorry-api.create-notice-update\"\n              with:\n                page_id: \"rest.page_id\"\n                notice_id: \"rest.notice_id\"\n                content: \"rest.content\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pages/{page_id}/subscribers\n          name: subscribers\n          description: Subscriber management\n          operations:\n            - method: GET\n              name: list-subscribers\n              description: List all subscribers for a status page\n              call: \"sorry-api.list-subscribers\"\n              with:\n\
  \                page_id: \"rest.page_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-subscriber\n              description: Add a subscriber to a status page\n              call: \"sorry-api.create-subscriber\"\n              with:\n                page_id: \"rest.page_id\"\n                email: \"rest.email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sorry-incident-comms-mcp\n      transport: http\n      description: \"MCP server for AI-assisted incident communication using Sorry status pages.\"\n      tools:\n        - name: list-status-pages\n          description: >-\n            List all status pages in the Sorry account. Use to find page IDs for\n            subsequent operations during incident response.\n          hints:\n            readOnly: true\n\
  \            openWorld: false\n          call: \"sorry-api.list-pages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-components\n          description: >-\n            List all components for a status page. Use to identify affected components\n            before creating incident notices.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sorry-api.list-components\"\n          with:\n            page_id: \"tools.page_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-incident-notice\n          description: >-\n            Create an incident notice on a status page to notify customers of an unplanned\n            outage or service degradation. Use for incident declaration.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sorry-api.create-notice\"\
  \n          with:\n            page_id: \"tools.page_id\"\n            type: \"tools.type\"\n            subject: \"tools.subject\"\n            initial_comment: \"tools.initial_comment\"\n            should_publish: \"tools.should_publish\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-notices\n          description: >-\n            List all notices for a status page. Use to find active incidents or\n            review recent maintenance windows.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sorry-api.list-notices\"\n          with:\n            page_id: \"tools.page_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-incident-state\n          description: >-\n            Update the state or details of an existing incident notice. Use to\n            progress an incident through monitoring, resolved, or completed\
  \ states.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"sorry-api.update-notice\"\n          with:\n            page_id: \"tools.page_id\"\n            notice_id: \"tools.notice_id\"\n            state: \"tools.state\"\n            additional_comment: \"tools.additional_comment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: publish-incident-update\n          description: >-\n            Publish a new status update to an existing incident notice. Use to keep\n            customers informed as the incident investigation progresses.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sorry-api.create-notice-update\"\n          with:\n            page_id: \"tools.page_id\"\n            notice_id: \"tools.notice_id\"\n            content: \"tools.content\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: list-subscribers\n          description: >-\n            List subscribers for a status page. Use to understand notification reach\n            before publishing a major incident notice.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sorry-api.list-subscribers\"\n          with:\n            page_id: \"tools.page_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: add-subscriber\n          description: >-\n            Add a new subscriber to receive status page notifications via email\n            or SMS.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sorry-api.create-subscriber\"\n          with:\n            page_id: \"tools.page_id\"\n            email: \"tools.email\"\n            first_name: \"tools.first_name\"\n    \
  \        last_name: \"tools.last_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sorry/refs/heads/main/capabilities/incident-communications.yaml
tags:
- Sorry
- Status Pages
- Incident Management
- Notifications
- Customer Communication
- DevOps
tools:
- description: List all status pages in the Sorry account. Use to find page IDs for subsequent operations during incident response.
  hints:
    openWorld: false
    readOnly: true
  name: list-status-pages
- description: List all components for a status page. Use to identify affected components before creating incident notices.
  hints:
    openWorld: false
    readOnly: true
  name: list-components
- description: Create an incident notice on a status page to notify customers of an unplanned outage or service degradation. Use for incident declaration.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-incident-notice
- description: List all notices for a status page. Use to find active incidents or review recent maintenance windows.
  hints:
    openWorld: false
    readOnly: true
  name: list-notices
- description: Update the state or details of an existing incident notice. Use to progress an incident through monitoring, resolved, or completed states.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-incident-state
- description: Publish a new status update to an existing incident notice. Use to keep customers informed as the incident investigation progresses.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publish-incident-update
- description: List subscribers for a status page. Use to understand notification reach before publishing a major incident notice.
  hints:
    openWorld: false
    readOnly: true
  name: list-subscribers
- description: Add a new subscriber to receive status page notifications via email or SMS.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-subscriber
---
