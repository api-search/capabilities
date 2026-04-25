---
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
- dns create record
- list dns records for a zone.
- delete a dns record.
- list dataset fields.
- list dns records.
- turnstile list widgets
- dns get record
- dns get dnssec
- update a dns record.
- logpush list jobs
- dns record management.
- list turnstile widgets
- edge
- real-time communication
- create a turnstile widget.
- execute batch dns operations.
- logpush job management.
- logpush create job
- logpush list dataset fields
- containers
- get dns record details.
- create a logpush job.
- get logpush job details.
- ai gateway
- create a dns record.
- dns update record
- dns batch records
- turnstile verify token
- delete a turnstile widget.
- serverless
- security
- api gateway
- artificial intelligence
- dns list records
- platform
- list turnstile widgets.
- ddos protection
- turnstile widget management.
- turnstile create widget
- cloudflare
- dns
- object storage
- observability
- logpush get job
- delete a logpush job.
- cdn
- list logpush jobs
- get dnssec settings.
- verify a turnstile token.
- list logpush jobs.
- cloud
- turnstile delete widget
- logpush delete job
- dns delete record
- list dns records
- web performance
- edge computing
slug: dns-and-security
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
