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
- create a turnstile widget.
- ai gateway
- cloudflare
- verify a turnstile token.
- delete a logpush job.
- delete a turnstile widget.
- edge
- update a dns record.
- dns update record
- artificial intelligence
- ddos protection
- get dnssec settings.
- turnstile list widgets
- list turnstile widgets.
- execute batch dns operations.
- logpush create job
- logpush list dataset fields
- cloud
- get logpush job details.
- observability
- dns delete record
- dns
- security
- dns batch records
- logpush get job
- edge computing
- list dns records
- containers
- platform
- cdn
- logpush delete job
- object storage
- real-time communication
- turnstile widget management.
- logpush job management.
- dns create record
- list logpush jobs
- logpush list jobs
- web performance
- list turnstile widgets
- create a dns record.
- turnstile delete widget
- list dataset fields.
- serverless
- delete a dns record.
- create a logpush job.
- turnstile verify token
- list dns records.
- api gateway
- dns record management.
- list dns records for a zone.
- dns list records
- dns get record
- turnstile create widget
- get dns record details.
- list logpush jobs.
- dns get dnssec
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
