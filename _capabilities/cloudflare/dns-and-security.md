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
- turnstile create widget
- edge computing
- dns create record
- logpush delete job
- delete a logpush job.
- cloud
- verify a turnstile token.
- object storage
- create a turnstile widget.
- list logpush jobs
- containers
- real-time communication
- logpush job management.
- dns get dnssec
- dns batch records
- ai gateway
- list dns records for a zone.
- list turnstile widgets
- dns
- turnstile widget management.
- execute batch dns operations.
- turnstile verify token
- logpush list dataset fields
- create a dns record.
- security
- platform
- logpush list jobs
- update a dns record.
- cloudflare
- dns get record
- dns delete record
- get dns record details.
- list turnstile widgets.
- edge
- api gateway
- list dns records
- dns update record
- list logpush jobs.
- list dns records.
- dns record management.
- logpush get job
- list dataset fields.
- turnstile list widgets
- get dnssec settings.
- cdn
- get logpush job details.
- ddos protection
- delete a dns record.
- serverless
- logpush create job
- artificial intelligence
- observability
- web performance
- turnstile delete widget
- delete a turnstile widget.
- dns list records
- create a logpush job.
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
