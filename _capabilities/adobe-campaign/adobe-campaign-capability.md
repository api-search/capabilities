---
categories: []
consumed_apis: []
description: SOAP-based API for Adobe Campaign Classic v7 and v8, documented as HTTP POST operations. All operations target the single SOAP router endpoint at /nl/jsp/soaprouter.jsp and are differentiated by the SOAPAction header. Provides programmatic access to session management, data querying, record persistence, delivery management, workflow control, subscription management, and real-time transactional event ingestion.
layout: capability
name: Adobe Campaign Classic API
operations:
- description: Adobe Campaign Authenticate and Create a Session
  method: POST
  name: sessionlogon
  path: /nl/jsp/soaprouter.jsp/xtk-session/Logon
- description: Adobe Campaign Terminate a Session
  method: POST
  name: sessionlogout
  path: /nl/jsp/soaprouter.jsp/xtk-session/Logout
- description: Adobe Campaign Execute a Query
  method: POST
  name: executequery
  path: /nl/jsp/soaprouter.jsp/xtk-queryDef/ExecuteQuery
- description: Adobe Campaign Write Data Records
  method: POST
  name: sessionwrite
  path: /nl/jsp/soaprouter.jsp/xtk-session/Write
- description: Adobe Campaign Write Multiple Data Records
  method: POST
  name: sessionwritecollection
  path: /nl/jsp/soaprouter.jsp/xtk-session/WriteCollection
- description: Adobe Campaign Prepare and Start a Delivery
  method: POST
  name: deliveryprepareandstart
  path: /nl/jsp/soaprouter.jsp/nms-delivery/PrepareAndStart
- description: Adobe Campaign Submit a Delivery
  method: POST
  name: submitdelivery
  path: /nl/jsp/soaprouter.jsp/nms-delivery/SubmitDelivery
- description: Adobe Campaign Start a Workflow
  method: POST
  name: workflowstart
  path: /nl/jsp/soaprouter.jsp/xtk-workflow/Start
- description: Adobe Campaign Stop a Workflow
  method: POST
  name: workflowstop
  path: /nl/jsp/soaprouter.jsp/xtk-workflow/Stop
- description: Adobe Campaign Post an Event Signal to a Workflow
  method: POST
  name: workflowpostevent
  path: /nl/jsp/soaprouter.jsp/xtk-workflow/PostEvent
- description: Adobe Campaign Subscribe a Recipient to a Service
  method: POST
  name: subscribe
  path: /nl/jsp/soaprouter.jsp/nms-subscription/Subscribe
- description: Adobe Campaign Unsubscribe a Recipient from a Service
  method: POST
  name: unsubscribe
  path: /nl/jsp/soaprouter.jsp/nms-subscription/Unsubscribe
- description: Adobe Campaign Push a Real-time Transactional Event
  method: POST
  name: pushevent
  path: /nl/jsp/soaprouter.jsp/nms-rtEvent/PushEvent
- description: Adobe Campaign Push Batch Real-time Events
  method: POST
  name: pushevents
  path: /nl/jsp/soaprouter.jsp/nms-batchEvent/PushEvents
personas: []
provider_name: Adobe Campaign
provider_slug: adobe-campaign
search_terms:
- adobe campaign subscribe a recipient to a service
- adobe campaign push a real-time transactional event
- adobe campaign prepare and start a delivery
- adobe campaign submit a delivery
- workflowpostevent
- adobe campaign execute a query
- workflowstart
- campaign
- adobe campaign start a workflow
- adobe campaign post an event signal to a workflow
- deliveryprepareandstart
- sessionlogout
- adobe campaign authenticate and create a session
- unsubscribe
- adobe campaign terminate a session
- marketing automation
- subscribe
- email marketing
- submitdelivery
- api
- sessionwritecollection
- multi-channel marketing
- workflowstop
- executequery
- adobe
- sessionlogon
- sessionwrite
- adobe campaign unsubscribe a recipient from a service
- adobe campaign write data records
- pushevent
- adobe campaign stop a workflow
- adobe campaign push batch real-time events
- campaign management
- customer experience
- adobe campaign write multiple data records
- pushevents
slug: adobe-campaign-capability
source_filename: adobe-campaign-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Campaign Classic API\n  description: SOAP-based API for Adobe Campaign Classic v7 and v8, documented as HTTP POST operations. All operations target\n    the single SOAP router endpoint at /nl/jsp/soaprouter.jsp and are differentiated by the SOAPAction header. Provides programmatic\n    access to session management, data querying, record persistence, delivery management, workflow control, subscription management,\n    and real-time transactional event ingestion.\n  tags:\n  - Adobe\n  - Campaign\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: adobe-campaign\n    baseUri: https://YOUR_INSTANCE.campaign.adobe.com\n    description: Adobe Campaign Classic API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Security-Token\n      value: '{{ADOBE_CAMPAIGN_TOKEN}}'\n    resources:\n    - name: nl-jsp-soaprouter-jsp-xtk-session-logon\n\
  \      path: /nl/jsp/soaprouter.jsp/xtk-session/Logon\n      operations:\n      - name: sessionlogon\n        method: POST\n        description: Adobe Campaign Authenticate and Create a Session\n        inputParameters:\n        - name: SOAPAction\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nl-jsp-soaprouter-jsp-xtk-session-logout\n      path: /nl/jsp/soaprouter.jsp/xtk-session/Logout\n      operations:\n      - name: sessionlogout\n        method: POST\n        description: Adobe Campaign Terminate a Session\n        inputParameters:\n        - name: SOAPAction\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nl-jsp-soaprouter-jsp-xtk-querydef-executequery\n \
  \     path: /nl/jsp/soaprouter.jsp/xtk-queryDef/ExecuteQuery\n      operations:\n      - name: executequery\n        method: POST\n        description: Adobe Campaign Execute a Query\n        inputParameters:\n        - name: SOAPAction\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nl-jsp-soaprouter-jsp-xtk-session-write\n      path: /nl/jsp/soaprouter.jsp/xtk-session/Write\n      operations:\n      - name: sessionwrite\n        method: POST\n        description: Adobe Campaign Write Data Records\n        inputParameters:\n        - name: SOAPAction\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nl-jsp-soaprouter-jsp-xtk-session-writecollectio\n      path: /nl/jsp/soaprouter.jsp/xtk-session/WriteCollection\n\
  \      operations:\n      - name: sessionwritecollection\n        method: POST\n        description: Adobe Campaign Write Multiple Data Records\n        inputParameters:\n        - name: SOAPAction\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nl-jsp-soaprouter-jsp-nms-delivery-prepareandsta\n      path: /nl/jsp/soaprouter.jsp/nms-delivery/PrepareAndStart\n      operations:\n      - name: deliveryprepareandstart\n        method: POST\n        description: Adobe Campaign Prepare and Start a Delivery\n        inputParameters:\n        - name: SOAPAction\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nl-jsp-soaprouter-jsp-nms-delivery-submitdeliver\n      path: /nl/jsp/soaprouter.jsp/nms-delivery/SubmitDelivery\n\
  \      operations:\n      - name: submitdelivery\n        method: POST\n        description: Adobe Campaign Submit a Delivery\n        inputParameters:\n        - name: SOAPAction\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nl-jsp-soaprouter-jsp-xtk-workflow-start\n      path: /nl/jsp/soaprouter.jsp/xtk-workflow/Start\n      operations:\n      - name: workflowstart\n        method: POST\n        description: Adobe Campaign Start a Workflow\n        inputParameters:\n        - name: SOAPAction\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nl-jsp-soaprouter-jsp-xtk-workflow-stop\n      path: /nl/jsp/soaprouter.jsp/xtk-workflow/Stop\n      operations:\n      -\
  \ name: workflowstop\n        method: POST\n        description: Adobe Campaign Stop a Workflow\n        inputParameters:\n        - name: SOAPAction\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nl-jsp-soaprouter-jsp-xtk-workflow-postevent\n      path: /nl/jsp/soaprouter.jsp/xtk-workflow/PostEvent\n      operations:\n      - name: workflowpostevent\n        method: POST\n        description: Adobe Campaign Post an Event Signal to a Workflow\n        inputParameters:\n        - name: SOAPAction\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nl-jsp-soaprouter-jsp-nms-subscription-subscribe\n      path: /nl/jsp/soaprouter.jsp/nms-subscription/Subscribe\n      operations:\n\
  \      - name: subscribe\n        method: POST\n        description: Adobe Campaign Subscribe a Recipient to a Service\n        inputParameters:\n        - name: SOAPAction\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nl-jsp-soaprouter-jsp-nms-subscription-unsubscri\n      path: /nl/jsp/soaprouter.jsp/nms-subscription/Unsubscribe\n      operations:\n      - name: unsubscribe\n        method: POST\n        description: Adobe Campaign Unsubscribe a Recipient from a Service\n        inputParameters:\n        - name: SOAPAction\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nl-jsp-soaprouter-jsp-nms-rtevent-pushevent\n      path: /nl/jsp/soaprouter.jsp/nms-rtEvent/PushEvent\n\
  \      operations:\n      - name: pushevent\n        method: POST\n        description: Adobe Campaign Push a Real-time Transactional Event\n        inputParameters:\n        - name: SOAPAction\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nl-jsp-soaprouter-jsp-nms-batchevent-pushevents\n      path: /nl/jsp/soaprouter.jsp/nms-batchEvent/PushEvents\n      operations:\n      - name: pushevents\n        method: POST\n        description: Adobe Campaign Push Batch Real-time Events\n        inputParameters:\n        - name: SOAPAction\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: adobe-campaign-rest\n    description: REST\
  \ adapter for Adobe Campaign Classic API.\n    resources:\n    - path: /nl/jsp/soaprouter.jsp/xtk-session/Logon\n      name: sessionlogon\n      operations:\n      - method: POST\n        name: sessionlogon\n        description: Adobe Campaign Authenticate and Create a Session\n        call: adobe-campaign.sessionlogon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nl/jsp/soaprouter.jsp/xtk-session/Logout\n      name: sessionlogout\n      operations:\n      - method: POST\n        name: sessionlogout\n        description: Adobe Campaign Terminate a Session\n        call: adobe-campaign.sessionlogout\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nl/jsp/soaprouter.jsp/xtk-queryDef/ExecuteQuery\n      name: executequery\n      operations:\n      - method: POST\n        name: executequery\n        description: Adobe Campaign Execute a Query\n        call: adobe-campaign.executequery\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /nl/jsp/soaprouter.jsp/xtk-session/Write\n      name: sessionwrite\n      operations:\n      - method: POST\n        name: sessionwrite\n        description: Adobe Campaign Write Data Records\n        call: adobe-campaign.sessionwrite\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nl/jsp/soaprouter.jsp/xtk-session/WriteCollection\n      name: sessionwritecollection\n      operations:\n      - method: POST\n        name: sessionwritecollection\n        description: Adobe Campaign Write Multiple Data Records\n        call: adobe-campaign.sessionwritecollection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nl/jsp/soaprouter.jsp/nms-delivery/PrepareAndStart\n      name: deliveryprepareandstart\n      operations:\n      - method: POST\n        name: deliveryprepareandstart\n        description: Adobe Campaign Prepare and Start a Delivery\n        call:\
  \ adobe-campaign.deliveryprepareandstart\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nl/jsp/soaprouter.jsp/nms-delivery/SubmitDelivery\n      name: submitdelivery\n      operations:\n      - method: POST\n        name: submitdelivery\n        description: Adobe Campaign Submit a Delivery\n        call: adobe-campaign.submitdelivery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nl/jsp/soaprouter.jsp/xtk-workflow/Start\n      name: workflowstart\n      operations:\n      - method: POST\n        name: workflowstart\n        description: Adobe Campaign Start a Workflow\n        call: adobe-campaign.workflowstart\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nl/jsp/soaprouter.jsp/xtk-workflow/Stop\n      name: workflowstop\n      operations:\n      - method: POST\n        name: workflowstop\n        description: Adobe Campaign Stop a Workflow\n        call: adobe-campaign.workflowstop\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nl/jsp/soaprouter.jsp/xtk-workflow/PostEvent\n      name: workflowpostevent\n      operations:\n      - method: POST\n        name: workflowpostevent\n        description: Adobe Campaign Post an Event Signal to a Workflow\n        call: adobe-campaign.workflowpostevent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nl/jsp/soaprouter.jsp/nms-subscription/Subscribe\n      name: subscribe\n      operations:\n      - method: POST\n        name: subscribe\n        description: Adobe Campaign Subscribe a Recipient to a Service\n        call: adobe-campaign.subscribe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nl/jsp/soaprouter.jsp/nms-subscription/Unsubscribe\n      name: unsubscribe\n      operations:\n      - method: POST\n        name: unsubscribe\n        description: Adobe Campaign Unsubscribe a Recipient from a Service\n\
  \        call: adobe-campaign.unsubscribe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nl/jsp/soaprouter.jsp/nms-rtEvent/PushEvent\n      name: pushevent\n      operations:\n      - method: POST\n        name: pushevent\n        description: Adobe Campaign Push a Real-time Transactional Event\n        call: adobe-campaign.pushevent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nl/jsp/soaprouter.jsp/nms-batchEvent/PushEvents\n      name: pushevents\n      operations:\n      - method: POST\n        name: pushevents\n        description: Adobe Campaign Push Batch Real-time Events\n        call: adobe-campaign.pushevents\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: adobe-campaign-mcp\n    transport: http\n    description: MCP adapter for Adobe Campaign Classic API for AI agent use.\n    tools:\n    - name: sessionlogon\n      description:\
  \ Adobe Campaign Authenticate and Create a Session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-campaign.sessionlogon\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sessionlogout\n      description: Adobe Campaign Terminate a Session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-campaign.sessionlogout\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: executequery\n      description: Adobe Campaign Execute a Query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-campaign.executequery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sessionwrite\n      description: Adobe Campaign Write Data Records\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n    \
  \  call: adobe-campaign.sessionwrite\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sessionwritecollection\n      description: Adobe Campaign Write Multiple Data Records\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-campaign.sessionwritecollection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deliveryprepareandstart\n      description: Adobe Campaign Prepare and Start a Delivery\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-campaign.deliveryprepareandstart\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submitdelivery\n      description: Adobe Campaign Submit a Delivery\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-campaign.submitdelivery\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: workflowstart\n      description: Adobe Campaign Start a Workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-campaign.workflowstart\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: workflowstop\n      description: Adobe Campaign Stop a Workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-campaign.workflowstop\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: workflowpostevent\n      description: Adobe Campaign Post an Event Signal to a Workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-campaign.workflowpostevent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: subscribe\n      description: Adobe Campaign Subscribe a Recipient to a Service\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-campaign.subscribe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unsubscribe\n      description: Adobe Campaign Unsubscribe a Recipient from a Service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-campaign.unsubscribe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pushevent\n      description: Adobe Campaign Push a Real-time Transactional Event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-campaign.pushevent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pushevents\n      description: Adobe Campaign Push Batch Real-time Events\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-campaign.pushevents\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ADOBE_CAMPAIGN_TOKEN: ADOBE_CAMPAIGN_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-campaign/refs/heads/main/capabilities/adobe-campaign-capability.yaml
tags:
- Adobe
- Campaign
- API
tools:
- description: Adobe Campaign Authenticate and Create a Session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sessionlogon
- description: Adobe Campaign Terminate a Session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sessionlogout
- description: Adobe Campaign Execute a Query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executequery
- description: Adobe Campaign Write Data Records
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sessionwrite
- description: Adobe Campaign Write Multiple Data Records
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sessionwritecollection
- description: Adobe Campaign Prepare and Start a Delivery
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deliveryprepareandstart
- description: Adobe Campaign Submit a Delivery
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitdelivery
- description: Adobe Campaign Start a Workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: workflowstart
- description: Adobe Campaign Stop a Workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: workflowstop
- description: Adobe Campaign Post an Event Signal to a Workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: workflowpostevent
- description: Adobe Campaign Subscribe a Recipient to a Service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: subscribe
- description: Adobe Campaign Unsubscribe a Recipient from a Service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: unsubscribe
- description: Adobe Campaign Push a Real-time Transactional Event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pushevent
- description: Adobe Campaign Push Batch Real-time Events
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pushevents
---
