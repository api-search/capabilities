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
- get logpush job details.
- list dataset fields.
- get dnssec settings.
- cdn
- dns
- logpush create job
- delete a dns record.
- update a dns record.
- list dns records for a zone.
- edge computing
- object storage
- edge
- ddos protection
- create a dns record.
- delete a logpush job.
- list dns records.
- dns batch records
- list turnstile widgets
- logpush job management.
- dns create record
- turnstile verify token
- create a logpush job.
- serverless
- dns get dnssec
- platform
- observability
- api gateway
- artificial intelligence
- create a turnstile widget.
- containers
- dns list records
- execute batch dns operations.
- turnstile widget management.
- logpush list dataset fields
- ai gateway
- cloudflare
- cloud
- delete a turnstile widget.
- dns record management.
- get dns record details.
- logpush get job
- turnstile delete widget
- list logpush jobs
- list dns records
- list logpush jobs.
- real-time communication
- security
- list turnstile widgets.
- turnstile list widgets
- verify a turnstile token.
- dns get record
- web performance
- dns update record
- logpush list jobs
- logpush delete job
- turnstile create widget
- dns delete record
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
