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
- list dns records for a zone.
- dns
- cloudflare
- dns list records
- dns create record
- turnstile delete widget
- artificial intelligence
- list turnstile widgets
- object storage
- delete a logpush job.
- list logpush jobs.
- dns get record
- web performance
- dns record management.
- serverless
- dns batch records
- turnstile widget management.
- cdn
- get dnssec settings.
- turnstile verify token
- list dataset fields.
- platform
- turnstile create widget
- list dns records
- security
- create a dns record.
- get logpush job details.
- logpush job management.
- create a logpush job.
- observability
- delete a turnstile widget.
- dns update record
- execute batch dns operations.
- logpush list dataset fields
- api gateway
- update a dns record.
- dns delete record
- list logpush jobs
- delete a dns record.
- create a turnstile widget.
- ai gateway
- ddos protection
- turnstile list widgets
- list dns records.
- get dns record details.
- containers
- edge
- edge computing
- list turnstile widgets.
- logpush get job
- real-time communication
- verify a turnstile token.
- logpush list jobs
- logpush create job
- logpush delete job
- cloud
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
