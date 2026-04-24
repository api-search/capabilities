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
- send a transactional email
- sending and tracking transactional emails
- managing email suppression lists
- email delivery statistics
- list suppressed addresses
- send email
- get deliverability stats
- application developer integrating transactional email into their application
- send and retrieve transactional email messages
- get deliverability statistics
- list suppressions
- list configured sending domains and their dns verification status
- email
- manage event webhooks
- send a transactional email message via ahasend
- get transactional email deliverability statistics and metrics
- list email messages
- transactional email
- list domains
- list webhooks
- infrastructure engineer monitoring email delivery health and managing domains
- smtp
- developer tools
- deliverability
- send message
- list configured webhooks for email event notifications
- list messages
- manage email suppressions
- send emails, manage domains, configure webhooks, and monitor delivery statistics
- manage sending domains
- webhooks
- configuring and validating sending domains
- webhook and route configuration for email events
- Developer
- list suppressed email addresses (bounces, complaints, unsubscribes)
- DevOps Engineer
- list sent email messages with delivery status
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
