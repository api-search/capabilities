---
api_specs:
- filename: gitlab-webhooks-openapi.yml
  format: yaml
  label: gitlab-webhooks
  slug: gitlab-webhooks
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/gitlab/refs/heads/main/openapi/gitlab-webhooks-openapi.yml
categories: []
consumed_apis:
- gitlab-webhooks
description: Unified capability for managing GitLab project webhooks, including CRUD operations, custom header and URL variable configuration, delivery event history, and testing. Used by DevOps engineers and platform administrators to set up and maintain event-driven integrations.
layout: capability
name: GitLab Webhook Management
operations:
- description: List all webhooks for a project.
  method: GET
  name: list-project-webhooks
  path: /v1/projects/{id}/webhooks
- description: Add a new webhook to a project.
  method: POST
  name: add-project-webhook
  path: /v1/projects/{id}/webhooks
- description: Get details of a specific project webhook.
  method: GET
  name: get-project-webhook
  path: /v1/projects/{id}/webhooks/{hook_id}
- description: Update a project webhook configuration.
  method: PUT
  name: update-project-webhook
  path: /v1/projects/{id}/webhooks/{hook_id}
- description: Delete a project webhook.
  method: DELETE
  name: delete-project-webhook
  path: /v1/projects/{id}/webhooks/{hook_id}
- description: List delivery events for a webhook from the past 7 days.
  method: GET
  name: list-webhook-events
  path: /v1/projects/{id}/webhooks/{hook_id}/events
- description: Resend a previously triggered webhook event.
  method: POST
  name: resend-webhook-event
  path: /v1/projects/{id}/webhooks/{hook_id}/events/{hook_event_id}/resend
- description: Send a test webhook payload of a specified trigger type.
  method: POST
  name: test-project-webhook
  path: /v1/projects/{id}/webhooks/{hook_id}/tests/{trigger}
- description: Set a custom header for a webhook.
  method: PUT
  name: set-webhook-custom-header
  path: /v1/projects/{id}/webhooks/{hook_id}/custom-headers/{key}
- description: Delete a custom header from a webhook.
  method: DELETE
  name: delete-webhook-custom-header
  path: /v1/projects/{id}/webhooks/{hook_id}/custom-headers/{key}
- description: Set a URL variable for a webhook.
  method: PUT
  name: set-webhook-url-variable
  path: /v1/projects/{id}/webhooks/{hook_id}/url-variables/{key}
- description: Delete a URL variable from a webhook.
  method: DELETE
  name: delete-webhook-url-variable
  path: /v1/projects/{id}/webhooks/{hook_id}/url-variables/{key}
personas: []
provider_name: GitLab
provider_slug: gitlab
search_terms:
- add project webhook
- list all webhooks for a project.
- integrations
- delete webhook custom header
- get details of a specific project webhook.
- url variable management for dynamic webhook url substitution.
- list delivery events for a webhook from the past 7 days.
- code
- resend a webhook event delivery.
- update a project webhook configuration.
- list all webhooks configured for a project.
- resend a previously triggered webhook event.
- remove a url variable from a webhook.
- add or update a custom http header sent with webhook deliveries.
- test project webhook
- delete project webhook
- delete webhook url variable
- resend a previously triggered webhook event to retry failed deliveries.
- devops
- delete a url variable from a webhook.
- set webhook custom header
- remove a webhook from a project.
- test webhook triggers.
- individual webhook operations.
- add or update a url variable for dynamic webhook url substitution.
- update project webhook
- webhook delivery event history.
- send a test webhook payload of a specified trigger type to verify endpoint configuration.
- webhooks
- platform
- delete a project webhook.
- get configuration details for a specific project webhook.
- get project webhook
- delete a custom header from a webhook.
- remove a custom http header from a webhook.
- project webhook collection operations.
- gitlab
- custom http header management for webhook deliveries.
- set webhook url variable
- create a new webhook for a project with configurable event triggers.
- source control
- list webhook events
- resend webhook event
- software development
- event driven
- list project webhooks
- send a test webhook payload of a specified trigger type.
- set a custom header for a webhook.
- add a new webhook to a project.
- set a url variable for a webhook.
- update the configuration of an existing project webhook.
slug: webhook-management
source_filename: webhook-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"GitLab Webhook Management\"\n  description: \"Unified capability for managing GitLab project webhooks, including CRUD operations, custom header and URL variable configuration, delivery event history, and testing. Used by DevOps engineers and platform administrators to set up and maintain event-driven integrations.\"\n  tags:\n    - Gitlab\n    - Webhooks\n    - Integrations\n    - Devops\n    - Event Driven\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GITLAB_PRIVATE_TOKEN: GITLAB_PRIVATE_TOKEN\n\ncapability:\n  consumes:\n    - import: gitlab-webhooks\n      location: ./shared/gitlab-webhooks.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: gitlab-webhooks-mgmt-api\n      description: \"Unified REST API for GitLab webhook management, configuration, and event monitoring.\"\n      resources:\n        - path: /v1/projects/{id}/webhooks\n          name:\
  \ project-webhooks\n          description: \"Project webhook collection operations.\"\n          operations:\n            - method: GET\n              name: list-project-webhooks\n              description: \"List all webhooks for a project.\"\n              call: \"gitlab-webhooks.list-project-webhooks\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-project-webhook\n              description: \"Add a new webhook to a project.\"\n              call: \"gitlab-webhooks.add-project-webhook\"\n              with:\n                id: \"rest.id\"\n                url: \"rest.url\"\n                name: \"rest.name\"\n                description: \"rest.description\"\n                secret_token: \"rest.secret_token\"\n                enable_ssl_verification: \"rest.enable_ssl_verification\"\n                push_events: \"rest.push_events\"\
  \n                tag_push_events: \"rest.tag_push_events\"\n                issues_events: \"rest.issues_events\"\n                confidential_issues_events: \"rest.confidential_issues_events\"\n                merge_requests_events: \"rest.merge_requests_events\"\n                note_events: \"rest.note_events\"\n                confidential_note_events: \"rest.confidential_note_events\"\n                job_events: \"rest.job_events\"\n                pipeline_events: \"rest.pipeline_events\"\n                wiki_page_events: \"rest.wiki_page_events\"\n                deployment_events: \"rest.deployment_events\"\n                releases_events: \"rest.releases_events\"\n                member_events: \"rest.member_events\"\n                push_events_branch_filter: \"rest.push_events_branch_filter\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{id}/webhooks/{hook_id}\n          name: project-webhook-detail\n\
  \          description: \"Individual webhook operations.\"\n          operations:\n            - method: GET\n              name: get-project-webhook\n              description: \"Get details of a specific project webhook.\"\n              call: \"gitlab-webhooks.get-project-webhook\"\n              with:\n                id: \"rest.id\"\n                hook_id: \"rest.hook_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-project-webhook\n              description: \"Update a project webhook configuration.\"\n              call: \"gitlab-webhooks.update-project-webhook\"\n              with:\n                id: \"rest.id\"\n                hook_id: \"rest.hook_id\"\n                url: \"rest.url\"\n                name: \"rest.name\"\n                description: \"rest.description\"\n                secret_token: \"rest.secret_token\"\n                enable_ssl_verification:\
  \ \"rest.enable_ssl_verification\"\n                push_events: \"rest.push_events\"\n                tag_push_events: \"rest.tag_push_events\"\n                issues_events: \"rest.issues_events\"\n                confidential_issues_events: \"rest.confidential_issues_events\"\n                merge_requests_events: \"rest.merge_requests_events\"\n                note_events: \"rest.note_events\"\n                confidential_note_events: \"rest.confidential_note_events\"\n                job_events: \"rest.job_events\"\n                pipeline_events: \"rest.pipeline_events\"\n                wiki_page_events: \"rest.wiki_page_events\"\n                deployment_events: \"rest.deployment_events\"\n                releases_events: \"rest.releases_events\"\n                member_events: \"rest.member_events\"\n                push_events_branch_filter: \"rest.push_events_branch_filter\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n            - method: DELETE\n              name: delete-project-webhook\n              description: \"Delete a project webhook.\"\n              call: \"gitlab-webhooks.delete-project-webhook\"\n              with:\n                id: \"rest.id\"\n                hook_id: \"rest.hook_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{id}/webhooks/{hook_id}/events\n          name: webhook-events\n          description: \"Webhook delivery event history.\"\n          operations:\n            - method: GET\n              name: list-webhook-events\n              description: \"List delivery events for a webhook from the past 7 days.\"\n              call: \"gitlab-webhooks.list-webhook-events\"\n              with:\n                id: \"rest.id\"\n                hook_id: \"rest.hook_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n     \
  \   - path: /v1/projects/{id}/webhooks/{hook_id}/events/{hook_event_id}/resend\n          name: webhook-event-resend\n          description: \"Resend a webhook event delivery.\"\n          operations:\n            - method: POST\n              name: resend-webhook-event\n              description: \"Resend a previously triggered webhook event.\"\n              call: \"gitlab-webhooks.resend-webhook-event\"\n              with:\n                id: \"rest.id\"\n                hook_id: \"rest.hook_id\"\n                hook_event_id: \"rest.hook_event_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{id}/webhooks/{hook_id}/tests/{trigger}\n          name: webhook-test\n          description: \"Test webhook triggers.\"\n          operations:\n            - method: POST\n              name: test-project-webhook\n              description: \"Send a test webhook payload of a specified trigger type.\"\n \
  \             call: \"gitlab-webhooks.test-project-webhook\"\n              with:\n                id: \"rest.id\"\n                hook_id: \"rest.hook_id\"\n                trigger: \"rest.trigger\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{id}/webhooks/{hook_id}/custom-headers/{key}\n          name: webhook-custom-headers\n          description: \"Custom HTTP header management for webhook deliveries.\"\n          operations:\n            - method: PUT\n              name: set-webhook-custom-header\n              description: \"Set a custom header for a webhook.\"\n              call: \"gitlab-webhooks.set-webhook-custom-header\"\n              with:\n                id: \"rest.id\"\n                hook_id: \"rest.hook_id\"\n                key: \"rest.key\"\n                value: \"rest.value\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n            - method: DELETE\n              name: delete-webhook-custom-header\n              description: \"Delete a custom header from a webhook.\"\n              call: \"gitlab-webhooks.delete-webhook-custom-header\"\n              with:\n                id: \"rest.id\"\n                hook_id: \"rest.hook_id\"\n                key: \"rest.key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{id}/webhooks/{hook_id}/url-variables/{key}\n          name: webhook-url-variables\n          description: \"URL variable management for dynamic webhook URL substitution.\"\n          operations:\n            - method: PUT\n              name: set-webhook-url-variable\n              description: \"Set a URL variable for a webhook.\"\n              call: \"gitlab-webhooks.set-webhook-url-variable\"\n              with:\n                id: \"rest.id\"\n                hook_id: \"rest.hook_id\"\n              \
  \  key: \"rest.key\"\n                value: \"rest.value\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-webhook-url-variable\n              description: \"Delete a URL variable from a webhook.\"\n              call: \"gitlab-webhooks.delete-webhook-url-variable\"\n              with:\n                id: \"rest.id\"\n                hook_id: \"rest.hook_id\"\n                key: \"rest.key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: gitlab-webhooks-mgmt-mcp\n      transport: http\n      description: \"MCP server for AI-assisted GitLab webhook management, configuration, and event monitoring.\"\n      tools:\n        - name: list-project-webhooks\n          description: \"List all webhooks configured for a project.\"\n          hints:\n            readOnly: true\n\
  \            openWorld: true\n            idempotent: true\n          call: \"gitlab-webhooks.list-project-webhooks\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: add-project-webhook\n          description: \"Create a new webhook for a project with configurable event triggers.\"\n          hints:\n            readOnly: false\n            openWorld: true\n            idempotent: false\n          call: \"gitlab-webhooks.add-project-webhook\"\n          with:\n            id: \"tools.id\"\n            url: \"tools.url\"\n            name: \"tools.name\"\n            description: \"tools.description\"\n            secret_token: \"tools.secret_token\"\n            enable_ssl_verification: \"tools.enable_ssl_verification\"\n            push_events: \"tools.push_events\"\n            tag_push_events: \"tools.tag_push_events\"\n            issues_events: \"tools.issues_events\"\n      \
  \      confidential_issues_events: \"tools.confidential_issues_events\"\n            merge_requests_events: \"tools.merge_requests_events\"\n            note_events: \"tools.note_events\"\n            confidential_note_events: \"tools.confidential_note_events\"\n            job_events: \"tools.job_events\"\n            pipeline_events: \"tools.pipeline_events\"\n            wiki_page_events: \"tools.wiki_page_events\"\n            deployment_events: \"tools.deployment_events\"\n            releases_events: \"tools.releases_events\"\n            member_events: \"tools.member_events\"\n            push_events_branch_filter: \"tools.push_events_branch_filter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-project-webhook\n          description: \"Get configuration details for a specific project webhook.\"\n          hints:\n            readOnly: true\n            openWorld: true\n            idempotent: true\n          call:\
  \ \"gitlab-webhooks.get-project-webhook\"\n          with:\n            id: \"tools.id\"\n            hook_id: \"tools.hook_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-project-webhook\n          description: \"Update the configuration of an existing project webhook.\"\n          hints:\n            readOnly: false\n            openWorld: true\n            idempotent: true\n          call: \"gitlab-webhooks.update-project-webhook\"\n          with:\n            id: \"tools.id\"\n            hook_id: \"tools.hook_id\"\n            url: \"tools.url\"\n            name: \"tools.name\"\n            description: \"tools.description\"\n            secret_token: \"tools.secret_token\"\n            enable_ssl_verification: \"tools.enable_ssl_verification\"\n            push_events: \"tools.push_events\"\n            tag_push_events: \"tools.tag_push_events\"\n            issues_events: \"tools.issues_events\"\n         \
  \   confidential_issues_events: \"tools.confidential_issues_events\"\n            merge_requests_events: \"tools.merge_requests_events\"\n            note_events: \"tools.note_events\"\n            confidential_note_events: \"tools.confidential_note_events\"\n            job_events: \"tools.job_events\"\n            pipeline_events: \"tools.pipeline_events\"\n            wiki_page_events: \"tools.wiki_page_events\"\n            deployment_events: \"tools.deployment_events\"\n            releases_events: \"tools.releases_events\"\n            member_events: \"tools.member_events\"\n            push_events_branch_filter: \"tools.push_events_branch_filter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-project-webhook\n          description: \"Remove a webhook from a project.\"\n          hints:\n            readOnly: false\n            destructive: true\n            openWorld: true\n            idempotent: true\n       \
  \   call: \"gitlab-webhooks.delete-project-webhook\"\n          with:\n            id: \"tools.id\"\n            hook_id: \"tools.hook_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-webhook-events\n          description: \"List delivery events for a webhook from the past 7 days.\"\n          hints:\n            readOnly: true\n            openWorld: true\n            idempotent: true\n          call: \"gitlab-webhooks.list-webhook-events\"\n          with:\n            id: \"tools.id\"\n            hook_id: \"tools.hook_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: resend-webhook-event\n          description: \"Resend a previously triggered webhook event to retry failed deliveries.\"\n          hints:\n            readOnly: false\n            openWorld: true\n            idempotent: false\n          call: \"gitlab-webhooks.resend-webhook-event\"\n    \
  \      with:\n            id: \"tools.id\"\n            hook_id: \"tools.hook_id\"\n            hook_event_id: \"tools.hook_event_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: test-project-webhook\n          description: \"Send a test webhook payload of a specified trigger type to verify endpoint configuration.\"\n          hints:\n            readOnly: false\n            openWorld: true\n            idempotent: false\n          call: \"gitlab-webhooks.test-project-webhook\"\n          with:\n            id: \"tools.id\"\n            hook_id: \"tools.hook_id\"\n            trigger: \"tools.trigger\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: set-webhook-custom-header\n          description: \"Add or update a custom HTTP header sent with webhook deliveries.\"\n          hints:\n            readOnly: false\n            openWorld: true\n            idempotent:\
  \ true\n          call: \"gitlab-webhooks.set-webhook-custom-header\"\n          with:\n            id: \"tools.id\"\n            hook_id: \"tools.hook_id\"\n            key: \"tools.key\"\n            value: \"tools.value\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-webhook-custom-header\n          description: \"Remove a custom HTTP header from a webhook.\"\n          hints:\n            readOnly: false\n            destructive: true\n            openWorld: true\n            idempotent: true\n          call: \"gitlab-webhooks.delete-webhook-custom-header\"\n          with:\n            id: \"tools.id\"\n            hook_id: \"tools.hook_id\"\n            key: \"tools.key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: set-webhook-url-variable\n          description: \"Add or update a URL variable for dynamic webhook URL substitution.\"\n          hints:\n\
  \            readOnly: false\n            openWorld: true\n            idempotent: true\n          call: \"gitlab-webhooks.set-webhook-url-variable\"\n          with:\n            id: \"tools.id\"\n            hook_id: \"tools.hook_id\"\n            key: \"tools.key\"\n            value: \"tools.value\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-webhook-url-variable\n          description: \"Remove a URL variable from a webhook.\"\n          hints:\n            readOnly: false\n            destructive: true\n            openWorld: true\n            idempotent: true\n          call: \"gitlab-webhooks.delete-webhook-url-variable\"\n          with:\n            id: \"tools.id\"\n            hook_id: \"tools.hook_id\"\n            key: \"tools.key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/gitlab/refs/heads/main/capabilities/webhook-management.yaml
tags:
- Gitlab
- Webhooks
- Integrations
- Devops
- Event Driven
tools:
- description: List all webhooks configured for a project.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-project-webhooks
- description: Create a new webhook for a project with configurable event triggers.
  hints:
    idempotent: false
    openWorld: true
    readOnly: false
  name: add-project-webhook
- description: Get configuration details for a specific project webhook.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-project-webhook
- description: Update the configuration of an existing project webhook.
  hints:
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-project-webhook
- description: Remove a webhook from a project.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-project-webhook
- description: List delivery events for a webhook from the past 7 days.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-webhook-events
- description: Resend a previously triggered webhook event to retry failed deliveries.
  hints:
    idempotent: false
    openWorld: true
    readOnly: false
  name: resend-webhook-event
- description: Send a test webhook payload of a specified trigger type to verify endpoint configuration.
  hints:
    idempotent: false
    openWorld: true
    readOnly: false
  name: test-project-webhook
- description: Add or update a custom HTTP header sent with webhook deliveries.
  hints:
    idempotent: true
    openWorld: true
    readOnly: false
  name: set-webhook-custom-header
- description: Remove a custom HTTP header from a webhook.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-webhook-custom-header
- description: Add or update a URL variable for dynamic webhook URL substitution.
  hints:
    idempotent: true
    openWorld: true
    readOnly: false
  name: set-webhook-url-variable
- description: Remove a URL variable from a webhook.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-webhook-url-variable
---
