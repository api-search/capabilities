---
categories:
- security
consumed_apis:
- cloudflare-dns
- cloudflare-turnstile
- cloudflare-logpush
description: DNS management and web security combining DNS record management with Turnstile bot protection and Logpush observability. Used by site reliability engineers and security teams.
layout: capability
name: Cloudflare DNS and Security
operations:
- description: List DNS records.
  method: GET
  name: list-dns-records
  path: /v1/dns-records
- description: List Turnstile widgets.
  method: GET
  name: list-turnstile-widgets
  path: /v1/turnstile-widgets
- description: List Logpush jobs.
  method: GET
  name: list-logpush-jobs
  path: /v1/logpush-jobs
personas: []
provider_name: Cloudflare
provider_slug: cloudflare
search_terms:
- list dns records.
- get dnssec settings.
- dns update record
- cdn
- observability
- turnstile create widget
- logpush get job
- security
- get dns record details.
- logpush create job
- dns batch records
- create a logpush job.
- containers
- create a dns record.
- dns create record
- delete a dns record.
- list turnstile widgets
- dns delete record
- edge computing
- dns get dnssec
- platform
- serverless
- ai gateway
- object storage
- logpush job management.
- logpush list jobs
- update a dns record.
- ddos protection
- list logpush jobs.
- logpush delete job
- turnstile list widgets
- web performance
- turnstile delete widget
- artificial intelligence
- delete a turnstile widget.
- verify a turnstile token.
- real-time communication
- list dataset fields.
- dns get record
- logpush list dataset fields
- execute batch dns operations.
- list dns records
- cloudflare
- list dns records for a zone.
- edge
- cloud
- get logpush job details.
- delete a logpush job.
- create a turnstile widget.
- dns
- list logpush jobs
- list turnstile widgets.
- turnstile verify token
- api gateway
- dns list records
- dns record management.
- turnstile widget management.
slug: dns-and-security
source_filename: dns-and-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Cloudflare DNS and Security\"\n  description: \"DNS management and web security combining DNS record management with Turnstile bot protection and Logpush observability. Used by site reliability engineers and security teams.\"\n  tags:\n    - Cloudflare\n    - DNS\n    - Security\n    - Observability\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      CLOUDFLARE_API_TOKEN: CLOUDFLARE_API_TOKEN\n\ncapability:\n  consumes:\n    - import: cloudflare-dns\n      location: ./shared/dns.yaml\n    - import: cloudflare-turnstile\n      location: ./shared/turnstile.yaml\n    - import: cloudflare-logpush\n      location: ./shared/logpush.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: dns-security-api\n      description: \"Unified REST API for Cloudflare DNS and security services.\"\n      resources:\n        - path: /v1/dns-records\n          name: dns-records\n \
  \         description: \"DNS record management.\"\n          operations:\n            - method: GET\n              name: list-dns-records\n              description: \"List DNS records.\"\n              call: \"cloudflare-dns.list-dns-records\"\n              with:\n                zone_id: \"rest.zone_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/turnstile-widgets\n          name: turnstile-widgets\n          description: \"Turnstile widget management.\"\n          operations:\n            - method: GET\n              name: list-turnstile-widgets\n              description: \"List Turnstile widgets.\"\n              call: \"cloudflare-turnstile.list-turnstile-widgets\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/logpush-jobs\n          name: logpush-jobs\n     \
  \     description: \"Logpush job management.\"\n          operations:\n            - method: GET\n              name: list-logpush-jobs\n              description: \"List Logpush jobs.\"\n              call: \"cloudflare-logpush.list-logpush-jobs\"\n              with:\n                zone_id: \"rest.zone_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9084\n      namespace: dns-security-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Cloudflare DNS and security management.\"\n      tools:\n        - name: dns-list-records\n          description: \"List DNS records for a zone.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloudflare-dns.list-dns-records\"\n          with:\n            zone_id: \"tools.zone_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dns-create-record\n\
  \          description: \"Create a DNS record.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-dns.create-dns-record\"\n          with:\n            zone_id: \"tools.zone_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dns-get-record\n          description: \"Get DNS record details.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-dns.get-dns-record\"\n          with:\n            zone_id: \"tools.zone_id\"\n            dns_record_id: \"tools.dns_record_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dns-update-record\n          description: \"Update a DNS record.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"cloudflare-dns.update-dns-record\"\n          with:\n            zone_id: \"tools.zone_id\"\n            dns_record_id: \"tools.dns_record_id\"\n \
  \         outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dns-delete-record\n          description: \"Delete a DNS record.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"cloudflare-dns.delete-dns-record\"\n          with:\n            zone_id: \"tools.zone_id\"\n            dns_record_id: \"tools.dns_record_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dns-batch-records\n          description: \"Execute batch DNS operations.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-dns.batch-dns-records\"\n          with:\n            zone_id: \"tools.zone_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: dns-get-dnssec\n          description: \"Get DNSSEC settings.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-dns.get-dnssec\"\
  \n          with:\n            zone_id: \"tools.zone_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: turnstile-list-widgets\n          description: \"List Turnstile widgets.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloudflare-turnstile.list-turnstile-widgets\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: turnstile-create-widget\n          description: \"Create a Turnstile widget.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-turnstile.create-turnstile-widget\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: turnstile-verify-token\n          description: \"Verify a Turnstile token.\"\n          hints:\n\
  \            readOnly: true\n          call: \"cloudflare-turnstile.verify-turnstile-token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: turnstile-delete-widget\n          description: \"Delete a Turnstile widget.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"cloudflare-turnstile.delete-turnstile-widget\"\n          with:\n            account_id: \"tools.account_id\"\n            sitekey: \"tools.sitekey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: logpush-list-jobs\n          description: \"List Logpush jobs.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloudflare-logpush.list-logpush-jobs\"\n          with:\n            zone_id: \"tools.zone_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: logpush-create-job\n\
  \          description: \"Create a Logpush job.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-logpush.create-logpush-job\"\n          with:\n            zone_id: \"tools.zone_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: logpush-get-job\n          description: \"Get Logpush job details.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-logpush.get-logpush-job\"\n          with:\n            zone_id: \"tools.zone_id\"\n            job_id: \"tools.job_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: logpush-delete-job\n          description: \"Delete a Logpush job.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"cloudflare-logpush.delete-logpush-job\"\n          with:\n            zone_id: \"tools.zone_id\"\n            job_id: \"tools.job_id\"\n       \
  \   outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: logpush-list-dataset-fields\n          description: \"List dataset fields.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-logpush.list-dataset-fields\"\n          with:\n            zone_id: \"tools.zone_id\"\n            dataset: \"tools.dataset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cloudflare/refs/heads/main/capabilities/dns-and-security.yaml
tags:
- Cloudflare
- DNS
- Security
- Observability
tools:
- description: List DNS records for a zone.
  hints:
    openWorld: true
    readOnly: true
  name: dns-list-records
- description: Create a DNS record.
  hints:
    readOnly: false
  name: dns-create-record
- description: Get DNS record details.
  hints:
    readOnly: true
  name: dns-get-record
- description: Update a DNS record.
  hints:
    idempotent: true
    readOnly: false
  name: dns-update-record
- description: Delete a DNS record.
  hints:
    destructive: true
    idempotent: true
  name: dns-delete-record
- description: Execute batch DNS operations.
  hints:
    readOnly: false
  name: dns-batch-records
- description: Get DNSSEC settings.
  hints:
    readOnly: true
  name: dns-get-dnssec
- description: List Turnstile widgets.
  hints:
    openWorld: true
    readOnly: true
  name: turnstile-list-widgets
- description: Create a Turnstile widget.
  hints:
    readOnly: false
  name: turnstile-create-widget
- description: Verify a Turnstile token.
  hints:
    readOnly: true
  name: turnstile-verify-token
- description: Delete a Turnstile widget.
  hints:
    destructive: true
    idempotent: true
  name: turnstile-delete-widget
- description: List Logpush jobs.
  hints:
    openWorld: true
    readOnly: true
  name: logpush-list-jobs
- description: Create a Logpush job.
  hints:
    readOnly: false
  name: logpush-create-job
- description: Get Logpush job details.
  hints:
    readOnly: true
  name: logpush-get-job
- description: Delete a Logpush job.
  hints:
    destructive: true
    idempotent: true
  name: logpush-delete-job
- description: List dataset fields.
  hints:
    readOnly: true
  name: logpush-list-dataset-fields
---
