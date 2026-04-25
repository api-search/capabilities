---
consumed_apis:
- call-control
- reporting
- administration
- vxml-services
description: Unified workflow for contact center operations combining call control, reporting, administration, and VXML services. Used by contact center administrators and operations teams for monitoring, managing, and optimizing voice self-service applications.
layout: capability
name: Cisco Voice Portal Contact Center Operations
operations:
- description: List active calls
  method: GET
  name: list-active-calls
  path: /v1/calls
- description: Get call details
  method: GET
  name: get-call
  path: /v1/calls/{callGuid}
- description: List call detail records
  method: GET
  name: list-cdrs
  path: /v1/cdrs
- description: Get real-time call statistics
  method: GET
  name: get-statistics
  path: /v1/statistics
- description: List managed devices
  method: GET
  name: list-devices
  path: /v1/devices
- description: List deployed applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: List active VXML sessions
  method: GET
  name: list-sessions
  path: /v1/sessions
- description: Get call server health
  method: GET
  name: get-health
  path: /v1/health
personas: []
provider_name: Cisco Voice Portal
provider_slug: cisco-voice-portal
search_terms:
- list applications
- list active calls
- get call
- list managed devices
- get statistics
- voice portal
- list deployed applications
- get call server health
- list vxml applications
- list managed cvp devices
- vxml
- vxml session monitoring
- application management
- list call detail records
- list call detail records from the reporting server
- device management
- cisco
- voice
- list sessions
- get call details
- list cdrs
- list all active calls on the cvp call server
- list devices
- check cvp call server health status
- contact center
- get health
- list active vxml sessions
- list active sessions
- call detail records
- list deployed cvp applications
- active call management
- list dialed number patterns
- system health
- real-time statistics
- individual call details
- get real-time call statistics
- get details of a specific active call
- list configured dialed number patterns
- ivr
- list deployed vxml applications
- telephony
slug: contact-center-operations
tags:
- Cisco
- Contact Center
- Voice Portal
- IVR
tools:
- description: List all active calls on the CVP Call Server
  hints:
    idempotent: true
    readOnly: true
  name: list-active-calls
- description: Get details of a specific active call
  hints:
    idempotent: true
    readOnly: true
  name: get-call
- description: Check CVP Call Server health status
  hints:
    idempotent: true
    readOnly: true
  name: get-call-server-health
- description: List call detail records from the Reporting Server
  hints:
    idempotent: true
    readOnly: true
  name: list-cdrs
- description: Get real-time call statistics
  hints:
    idempotent: true
    readOnly: true
  name: get-statistics
- description: List managed CVP devices
  hints:
    idempotent: true
    readOnly: true
  name: list-devices
- description: List deployed CVP applications
  hints:
    idempotent: true
    readOnly: true
  name: list-applications
- description: List configured dialed number patterns
  hints:
    idempotent: true
    readOnly: true
  name: list-dialed-number-patterns
- description: List deployed VXML applications
  hints:
    idempotent: true
    readOnly: true
  name: list-vxml-applications
- description: List active VXML sessions
  hints:
    idempotent: true
    readOnly: true
  name: list-active-sessions
---
