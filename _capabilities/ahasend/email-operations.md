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
- send a transactional email message via ahasend
- application developer integrating transactional email into their application
- get deliverability stats
- email
- manage sending domains
- list email messages
- list configured webhooks for email event notifications
- email delivery statistics
- send a transactional email
- managing email suppression lists
- smtp
- sending and tracking transactional emails
- webhook and route configuration for email events
- developer tools
- send and retrieve transactional email messages
- configuring and validating sending domains
- get deliverability statistics
- list suppressions
- transactional email
- infrastructure engineer monitoring email delivery health and managing domains
- list webhooks
- manage event webhooks
- deliverability
- list suppressed addresses
- manage email suppressions
- list suppressed email addresses (bounces, complaints, unsubscribes)
- send message
- Developer
- send email
- webhooks
- list domains
- get transactional email deliverability statistics and metrics
- send emails, manage domains, configure webhooks, and monitor delivery statistics
- DevOps Engineer
- list configured sending domains and their dns verification status
- list messages
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
