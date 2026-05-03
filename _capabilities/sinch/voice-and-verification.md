---
categories: []
consumed_apis:
- sinch-voice
- sinch-verification
description: Unified voice and identity verification workflow combining the Sinch Voice API and Verification API. Used by identity platforms, financial services, healthcare applications, and any business needing to verify user phone numbers via OTP SMS, flashcalls, or automated phone verification calls.
layout: capability
name: Sinch Voice and Verification
operations:
- description: Initiate a voice callout with TTS or custom audio
  method: POST
  name: make-callout
  path: /v1/callouts
- description: Get information about a voice call
  method: GET
  name: get-call
  path: /v1/calls/{callId}
- description: Start a phone number verification via SMS or call
  method: POST
  name: start-verification
  path: /v1/verifications
personas: []
provider_name: Sinch
provider_slug: sinch
search_terms:
- make outbound voice calls
- start a phone number verification via automated phone call
- get information about a voice call
- start phone number verification flows
- verification
- start call verification
- make voice call
- initiate a voice callout with tts or custom audio
- report verification code
- get call
- voice
- make an outbound voice call with text-to-speech or ivr
- start verification
- start sms verification
- get the status and details of a voice call
- authentication
- get call status
- sms
- otp
- report the otp code entered by the user to complete verification
- calling
- communications
- messaging
- identity
- manage active voice calls
- start a phone number verification via sms or call
- start a phone number verification flow sending an otp via sms
- make callout
- cpaas
slug: voice-and-verification
source_filename: voice-and-verification.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sinch Voice and Verification\"\n  description: >-\n    Unified voice and identity verification workflow combining the Sinch Voice\n    API and Verification API. Used by identity platforms, financial services,\n    healthcare applications, and any business needing to verify user phone\n    numbers via OTP SMS, flashcalls, or automated phone verification calls.\n  tags:\n    - Voice\n    - Verification\n    - Identity\n    - OTP\n    - Authentication\n    - Calling\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SINCH_APPLICATION_KEY: SINCH_APPLICATION_KEY\n      SINCH_APPLICATION_SECRET: SINCH_APPLICATION_SECRET\n\ncapability:\n  consumes:\n    - import: sinch-voice\n      location: ./shared/voice.yaml\n    - import: sinch-verification\n      location: ./shared/verification.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: voice-and-verification-api\n\
  \      description: \"Unified REST API for Sinch voice calls and phone number verification.\"\n      resources:\n        - path: /v1/callouts\n          name: callouts\n          description: Make outbound voice calls\n          operations:\n            - method: POST\n              name: make-callout\n              description: Initiate a voice callout with TTS or custom audio\n              call: \"sinch-voice.make-callout\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/calls/{callId}\n          name: calls\n          description: Manage active voice calls\n          operations:\n            - method: GET\n              name: get-call\n              description: Get information about a voice call\n              call: \"sinch-voice.get-call\"\n              with:\n                callId: \"rest.callId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n       \
  \ - path: /v1/verifications\n          name: verifications\n          description: Start phone number verification flows\n          operations:\n            - method: POST\n              name: start-verification\n              description: Start a phone number verification via SMS or call\n              call: \"sinch-verification.start-verification\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: voice-and-verification-mcp\n      transport: http\n      description: \"MCP server for AI-assisted voice calling and phone number verification.\"\n      tools:\n        - name: make-voice-call\n          description: Make an outbound voice call with text-to-speech or IVR\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"sinch-voice.make-callout\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n     \
  \   - name: get-call-status\n          description: Get the status and details of a voice call\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sinch-voice.get-call\"\n          with:\n            callId: \"tools.callId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-sms-verification\n          description: Start a phone number verification flow sending an OTP via SMS\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"sinch-verification.start-verification\"\n          with:\n            method: \"sms\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-call-verification\n          description: Start a phone number verification via automated phone call\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"sinch-verification.start-verification\"\
  \n          with:\n            method: \"callout\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: report-verification-code\n          description: Report the OTP code entered by the user to complete verification\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"sinch-verification.report-verification-by-id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sinch/refs/heads/main/capabilities/voice-and-verification.yaml
tags:
- Voice
- Verification
- Identity
- OTP
- Authentication
- Calling
tools:
- description: Make an outbound voice call with text-to-speech or IVR
  hints:
    destructive: false
    readOnly: false
  name: make-voice-call
- description: Get the status and details of a voice call
  hints:
    openWorld: false
    readOnly: true
  name: get-call-status
- description: Start a phone number verification flow sending an OTP via SMS
  hints:
    destructive: false
    readOnly: false
  name: start-sms-verification
- description: Start a phone number verification via automated phone call
  hints:
    destructive: false
    readOnly: false
  name: start-call-verification
- description: Report the OTP code entered by the user to complete verification
  hints:
    destructive: false
    readOnly: false
  name: report-verification-code
---
