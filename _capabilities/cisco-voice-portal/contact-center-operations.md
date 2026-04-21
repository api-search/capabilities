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
- get details of a specific active call
- telephony
- get statistics
- list sessions
- list devices
- vxml session monitoring
- get real-time call statistics
- list cdrs
- list active sessions
- individual call details
- list applications
- list call detail records from the reporting server
- list vxml applications
- list active calls
- check cvp call server health status
- list all active calls on the cvp call server
- application management
- call detail records
- list active vxml sessions
- ivr
- get health
- real-time statistics
- list deployed cvp applications
- vxml
- device management
- voice portal
- system health
- list configured dialed number patterns
- cisco
- list managed devices
- voice
- list call detail records
- get call server health
- active call management
- list deployed applications
- list deployed vxml applications
- list dialed number patterns
- list managed cvp devices
- get call details
- get call
- contact center
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
