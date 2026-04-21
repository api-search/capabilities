---
consumed_apis:
- ahasend
description: Unified workflow for sending transactional emails, managing domains, configuring webhooks, and monitoring delivery statistics. Used by developers integrating email notifications into applications.
layout: capability
name: AhaSend Email Operations
operations:
- description: List email messages
  method: GET
  name: list-messages
  path: /v1/messages
- description: Send a transactional email
  method: POST
  name: send-message
  path: /v1/messages
- description: List domains
  method: GET
  name: list-domains
  path: /v1/domains
- description: List webhooks
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: List suppressed addresses
  method: GET
  name: list-suppressions
  path: /v1/suppressions
- description: Get deliverability statistics
  method: GET
  name: get-deliverability-stats
  path: /v1/statistics/deliverability
personas: []
provider_name: AhaSend
provider_slug: ahasend
search_terms:
- manage email suppressions
- get deliverability stats
- list domains
- list webhooks
- list configured webhooks for email event notifications
- email
- list suppressed email addresses (bounces, complaints, unsubscribes)
- deliverability
- manage sending domains
- send and retrieve transactional email messages
- list configured sending domains and their dns verification status
- get deliverability statistics
- managing email suppression lists
- manage event webhooks
- Developer
- list suppressed addresses
- list sent email messages with delivery status
- send email
- transactional email
- developer tools
- email delivery statistics
- get transactional email deliverability statistics and metrics
- send a transactional email message via ahasend
- application developer integrating transactional email into their application
- sending and tracking transactional emails
- send emails, manage domains, configure webhooks, and monitor delivery statistics
- list email messages
- list suppressions
- infrastructure engineer monitoring email delivery health and managing domains
- list messages
- send message
- DevOps Engineer
- configuring and validating sending domains
- webhooks
- webhook and route configuration for email events
- send a transactional email
- smtp
slug: email-operations
tags:
- Email
- Transactional Email
- Developer Tools
- Webhooks
- Deliverability
tools:
- description: Send a transactional email message via AhaSend
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-email
- description: List sent email messages with delivery status
  hints:
    openWorld: true
    readOnly: true
  name: list-messages
- description: List configured sending domains and their DNS verification status
  hints:
    openWorld: true
    readOnly: true
  name: list-domains
- description: List configured webhooks for email event notifications
  hints:
    openWorld: true
    readOnly: true
  name: list-webhooks
- description: List suppressed email addresses (bounces, complaints, unsubscribes)
  hints:
    openWorld: true
    readOnly: true
  name: list-suppressions
- description: Get transactional email deliverability statistics and metrics
  hints:
    openWorld: true
    readOnly: true
  name: get-deliverability-stats
---
