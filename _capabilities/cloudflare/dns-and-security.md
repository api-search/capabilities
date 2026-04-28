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
- dns list records
- logpush get job
- verify a turnstile token.
- list logpush jobs
- create a turnstile widget.
- logpush list jobs
- dns record management.
- list dns records
- edge
- turnstile list widgets
- delete a logpush job.
- get dnssec settings.
- platform
- dns batch records
- real-time communication
- delete a turnstile widget.
- list turnstile widgets
- edge computing
- logpush delete job
- create a dns record.
- logpush job management.
- turnstile delete widget
- dns create record
- dns update record
- execute batch dns operations.
- api gateway
- get logpush job details.
- containers
- turnstile create widget
- web performance
- security
- turnstile verify token
- list dataset fields.
- observability
- ai gateway
- turnstile widget management.
- get dns record details.
- cdn
- ddos protection
- artificial intelligence
- serverless
- cloudflare
- list dns records.
- create a logpush job.
- list turnstile widgets.
- cloud
- dns
- delete a dns record.
- logpush create job
- list logpush jobs.
- object storage
- dns delete record
- update a dns record.
- dns get record
- list dns records for a zone.
- logpush list dataset fields
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
