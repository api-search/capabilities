---
categories:
- security
consumed_apis: []
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
- dns delete record
- list dns records.
- create a dns record.
- dns
- turnstile list widgets
- object storage
- list logpush jobs
- verify a turnstile token.
- list dns records
- dns list records
- dns get record
- logpush delete job
- serverless
- cloud
- security
- containers
- turnstile widget management.
- edge
- delete a logpush job.
- turnstile delete widget
- ddos protection
- dns update record
- logpush get job
- artificial intelligence
- cloudflare
- dns create record
- edge computing
- list turnstile widgets
- ai gateway
- cdn
- list logpush jobs.
- observability
- dns record management.
- execute batch dns operations.
- turnstile verify token
- logpush create job
- dns get dnssec
- api gateway
- web performance
- logpush list jobs
- list dns records for a zone.
- update a dns record.
- dns batch records
- get logpush job details.
- turnstile create widget
- platform
- create a turnstile widget.
- create a logpush job.
- list turnstile widgets.
- delete a dns record.
- logpush list dataset fields
- delete a turnstile widget.
- logpush job management.
- list dataset fields.
- real-time communication
- get dns record details.
- get dnssec settings.
slug: dns-and-security
source_filename: dns-and-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Cloudflare DNS and Security\n  description: DNS management and web security combining DNS record management with Turnstile bot protection and Logpush observability.\n    Used by site reliability engineers and security teams.\n  tags:\n  - Cloudflare\n  - DNS\n  - Security\n  - Observability\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CLOUDFLARE_API_TOKEN: CLOUDFLARE_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: cloudflare-dns\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare DNS API for managing DNS records, batch operations, scanning, and DNSSEC.\n    authentication:\n      type: bearer\n      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: dns-records\n      path: /zones/{zone_id}/dns_records\n      description: Manage DNS records for a zone.\n      operations:\n      - name: list-dns-records\n        method: GET\n      \
  \  description: List, search, sort, and filter a zone's DNS records.\n        inputParameters:\n        - name: zone_id\n          in: path\n          type: string\n          required: true\n          description: Zone identifier.\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: DNS record type to filter by.\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: DNS record name to filter by.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number of paginated results.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Number of records per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-dns-record\n       \
  \ method: POST\n        description: Create a new DNS record for a zone.\n        inputParameters:\n        - name: zone_id\n          in: path\n          type: string\n          required: true\n          description: Zone identifier.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            name: '{{tools.name}}'\n            content: '{{tools.content}}'\n            ttl: '{{tools.ttl}}'\n            proxied: '{{tools.proxied}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dns-record\n      path: /zones/{zone_id}/dns_records/{dns_record_id}\n      description: Manage a specific DNS record.\n      operations:\n      - name: get-dns-record\n        method: GET\n        description: Get details of a specific DNS record.\n        inputParameters:\n        - name: zone_id\n          in: path\n          type: string\n          required: true\n         \
  \ description: Zone identifier.\n        - name: dns_record_id\n          in: path\n          type: string\n          required: true\n          description: DNS record identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-dns-record\n        method: PATCH\n        description: Update an existing DNS record.\n        inputParameters:\n        - name: zone_id\n          in: path\n          type: string\n          required: true\n          description: Zone identifier.\n        - name: dns_record_id\n          in: path\n          type: string\n          required: true\n          description: DNS record identifier.\n        body:\n          type: json\n          data:\n            content: '{{tools.content}}'\n            ttl: '{{tools.ttl}}'\n            proxied: '{{tools.proxied}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: delete-dns-record\n        method: DELETE\n        description: Delete a DNS record.\n        inputParameters:\n        - name: zone_id\n          in: path\n          type: string\n          required: true\n          description: Zone identifier.\n        - name: dns_record_id\n          in: path\n          type: string\n          required: true\n          description: DNS record identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dns-batch\n      path: /zones/{zone_id}/dns_records/batch\n      description: Batch DNS record operations.\n      operations:\n      - name: batch-dns-records\n        method: POST\n        description: Execute multiple DNS record operations in a single call.\n        inputParameters:\n        - name: zone_id\n          in: path\n          type: string\n          required: true\n          description: Zone identifier.\n     \
  \   body:\n          type: json\n          data:\n            posts: '{{tools.posts}}'\n            puts: '{{tools.puts}}'\n            patches: '{{tools.patches}}'\n            deletes: '{{tools.deletes}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dnssec\n      path: /zones/{zone_id}/dnssec\n      description: DNSSEC configuration for a zone.\n      operations:\n      - name: get-dnssec\n        method: GET\n        description: Get DNSSEC settings for a zone.\n        inputParameters:\n        - name: zone_id\n          in: path\n          type: string\n          required: true\n          description: Zone identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: cloudflare-turnstile\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare Turnstile API\
  \ for managing CAPTCHA widgets and verifying tokens.\n    authentication:\n      type: bearer\n      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: widgets\n      path: /accounts/{account_id}/challenges/widgets\n      description: Manage Turnstile widgets.\n      operations:\n      - name: list-turnstile-widgets\n        method: GET\n        description: List all Turnstile widgets.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-turnstile-widget\n        method: POST\n        description: Create a new Turnstile widget.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n     \
  \     type: json\n          data:\n            name: '{{tools.name}}'\n            domains: '{{tools.domains}}'\n            mode: '{{tools.mode}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: widget\n      path: /accounts/{account_id}/challenges/widgets/{sitekey}\n      description: Manage a specific Turnstile widget.\n      operations:\n      - name: get-turnstile-widget\n        method: GET\n        description: Get Turnstile widget details.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: sitekey\n          in: path\n          type: string\n          required: true\n          description: Widget site key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-turnstile-widget\n\
  \        method: DELETE\n        description: Delete a Turnstile widget.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: sitekey\n          in: path\n          type: string\n          required: true\n          description: Widget site key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: verify\n      path: /siteverify\n      description: Verify Turnstile tokens.\n      operations:\n      - name: verify-turnstile-token\n        method: POST\n        description: Verify a Turnstile response token.\n        body:\n          type: json\n          data:\n            secret: '{{tools.secret}}'\n            response: '{{tools.response}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  -\
  \ type: http\n    namespace: cloudflare-logpush\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare Logpush API for managing log push jobs and datasets.\n    authentication:\n      type: bearer\n      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: jobs\n      path: /zones/{zone_id}/logpush/jobs\n      description: Manage Logpush jobs.\n      operations:\n      - name: list-logpush-jobs\n        method: GET\n        description: List all Logpush jobs for a zone.\n        inputParameters:\n        - name: zone_id\n          in: path\n          type: string\n          required: true\n          description: Zone identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-logpush-job\n        method: POST\n        description: Create a new Logpush job.\n        inputParameters:\n        - name: zone_id\n          in: path\n          type: string\n\
  \          required: true\n          description: Zone identifier.\n        body:\n          type: json\n          data:\n            destination_conf: '{{tools.destination_conf}}'\n            dataset: '{{tools.dataset}}'\n            enabled: '{{tools.enabled}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job\n      path: /zones/{zone_id}/logpush/jobs/{job_id}\n      description: Manage a specific Logpush job.\n      operations:\n      - name: get-logpush-job\n        method: GET\n        description: Get Logpush job details.\n        inputParameters:\n        - name: zone_id\n          in: path\n          type: string\n          required: true\n          description: Zone identifier.\n        - name: job_id\n          in: path\n          type: string\n          required: true\n          description: Job identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: delete-logpush-job\n        method: DELETE\n        description: Delete a Logpush job.\n        inputParameters:\n        - name: zone_id\n          in: path\n          type: string\n          required: true\n          description: Zone identifier.\n        - name: job_id\n          in: path\n          type: string\n          required: true\n          description: Job identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasets\n      path: /zones/{zone_id}/logpush/datasets/{dataset}/fields\n      description: List dataset fields.\n      operations:\n      - name: list-dataset-fields\n        method: GET\n        description: List available fields for a dataset.\n        inputParameters:\n        - name: zone_id\n          in: path\n          type: string\n          required: true\n          description: Zone identifier.\n\
  \        - name: dataset\n          in: path\n          type: string\n          required: true\n          description: Dataset name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: dns-security-api\n    description: Unified REST API for Cloudflare DNS and security services.\n    resources:\n    - path: /v1/dns-records\n      name: dns-records\n      description: DNS record management.\n      operations:\n      - method: GET\n        name: list-dns-records\n        description: List DNS records.\n        call: cloudflare-dns.list-dns-records\n        with:\n          zone_id: rest.zone_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/turnstile-widgets\n      name: turnstile-widgets\n      description: Turnstile widget management.\n      operations:\n      - method: GET\n        name: list-turnstile-widgets\n\
  \        description: List Turnstile widgets.\n        call: cloudflare-turnstile.list-turnstile-widgets\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/logpush-jobs\n      name: logpush-jobs\n      description: Logpush job management.\n      operations:\n      - method: GET\n        name: list-logpush-jobs\n        description: List Logpush jobs.\n        call: cloudflare-logpush.list-logpush-jobs\n        with:\n          zone_id: rest.zone_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9084\n    namespace: dns-security-mcp\n    transport: http\n    description: MCP server for AI-assisted Cloudflare DNS and security management.\n    tools:\n    - name: dns-list-records\n      description: List DNS records for a zone.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloudflare-dns.list-dns-records\n      with:\n\
  \        zone_id: tools.zone_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dns-create-record\n      description: Create a DNS record.\n      hints:\n        readOnly: false\n      call: cloudflare-dns.create-dns-record\n      with:\n        zone_id: tools.zone_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dns-get-record\n      description: Get DNS record details.\n      hints:\n        readOnly: true\n      call: cloudflare-dns.get-dns-record\n      with:\n        zone_id: tools.zone_id\n        dns_record_id: tools.dns_record_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dns-update-record\n      description: Update a DNS record.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: cloudflare-dns.update-dns-record\n      with:\n        zone_id: tools.zone_id\n        dns_record_id: tools.dns_record_id\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: dns-delete-record\n      description: Delete a DNS record.\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloudflare-dns.delete-dns-record\n      with:\n        zone_id: tools.zone_id\n        dns_record_id: tools.dns_record_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dns-batch-records\n      description: Execute batch DNS operations.\n      hints:\n        readOnly: false\n      call: cloudflare-dns.batch-dns-records\n      with:\n        zone_id: tools.zone_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dns-get-dnssec\n      description: Get DNSSEC settings.\n      hints:\n        readOnly: true\n      call: cloudflare-dns.get-dnssec\n      with:\n        zone_id: tools.zone_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: turnstile-list-widgets\n      description: List Turnstile widgets.\n      hints:\n   \
  \     readOnly: true\n        openWorld: true\n      call: cloudflare-turnstile.list-turnstile-widgets\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: turnstile-create-widget\n      description: Create a Turnstile widget.\n      hints:\n        readOnly: false\n      call: cloudflare-turnstile.create-turnstile-widget\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: turnstile-verify-token\n      description: Verify a Turnstile token.\n      hints:\n        readOnly: true\n      call: cloudflare-turnstile.verify-turnstile-token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: turnstile-delete-widget\n      description: Delete a Turnstile widget.\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloudflare-turnstile.delete-turnstile-widget\n      with:\n        account_id:\
  \ tools.account_id\n        sitekey: tools.sitekey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: logpush-list-jobs\n      description: List Logpush jobs.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloudflare-logpush.list-logpush-jobs\n      with:\n        zone_id: tools.zone_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: logpush-create-job\n      description: Create a Logpush job.\n      hints:\n        readOnly: false\n      call: cloudflare-logpush.create-logpush-job\n      with:\n        zone_id: tools.zone_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: logpush-get-job\n      description: Get Logpush job details.\n      hints:\n        readOnly: true\n      call: cloudflare-logpush.get-logpush-job\n      with:\n        zone_id: tools.zone_id\n        job_id: tools.job_id\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: logpush-delete-job\n      description: Delete a Logpush job.\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloudflare-logpush.delete-logpush-job\n      with:\n        zone_id: tools.zone_id\n        job_id: tools.job_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: logpush-list-dataset-fields\n      description: List dataset fields.\n      hints:\n        readOnly: true\n      call: cloudflare-logpush.list-dataset-fields\n      with:\n        zone_id: tools.zone_id\n        dataset: tools.dataset\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
