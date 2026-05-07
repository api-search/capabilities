---
categories: []
consumed_apis: []
description: Postmark makes sending and receiving email incredibly easy. The Account-level API allows users to configure all Servers, Domains, and Sender Signatures associated with an Account.
layout: capability
name: Postmark Account API
operations:
- description: Postmark Get a Server
  method: GET
  name: getserverinformation
  path: /servers/{serverid}
- description: Postmark Edit a Server
  method: PUT
  name: editserverinformation
  path: /servers/{serverid}
- description: Postmark Delete a Server
  method: DELETE
  name: deleteserver
  path: /servers/{serverid}
- description: Postmark List servers
  method: GET
  name: listservers
  path: /servers
- description: Postmark Create a Server
  method: POST
  name: createserver
  path: /servers
- description: Postmark List Sender Signatures
  method: GET
  name: listsendersignatures
  path: /senders
- description: Postmark Create a Sender Signature
  method: POST
  name: createsendersignature
  path: /senders
- description: Postmark Get a Sender Signature
  method: GET
  name: getsendersignature
  path: /senders/{signatureid}
- description: Postmark Update a Sender Signature
  method: PUT
  name: editsendersignature
  path: /senders/{signatureid}
- description: Postmark Delete a Sender Signature
  method: DELETE
  name: deletesendersignature
  path: /senders/{signatureid}
- description: Postmark Resend Signature Confirmation Email
  method: POST
  name: resendsendersignatureconfirmationemail
  path: /senders/{signatureid}/resend
- description: Postmark Request DNS Verification for SPF
  method: POST
  name: requestspfverificationforsendersignature
  path: /senders/{signatureid}/verifyspf
- description: Postmark Request a new DKIM Key
  method: POST
  name: requestnewdkimkeyforsendersignature
  path: /senders/{signatureid}/requestnewdkim
- description: Postmark List Domains
  method: GET
  name: listdomains
  path: /domains
- description: Postmark Create a Domain
  method: POST
  name: createdomain
  path: /domains
- description: Postmark Get a Domain
  method: GET
  name: getdomain
  path: /domains/{domainid}
- description: Postmark Update a Domain
  method: PUT
  name: editdomain
  path: /domains/{domainid}
- description: Postmark Delete a Domain
  method: DELETE
  name: deletedomain
  path: /domains/{domainid}
- description: Postmark Request DNS Verification for DKIM
  method: PUT
  name: requestdkimverificationfordomain
  path: /domains/{domainid}/verifydkim
- description: Postmark Request DNS Verification for Return-Path
  method: PUT
  name: requestreturnpathverificationfordomain
  path: /domains/{domainid}/verifyreturnpath
- description: Postmark Request DNS Verification for SPF
  method: POST
  name: requestspfverificationfordomain
  path: /domains/{domainid}/verifyspf
- description: Postmark Rotate DKIM Key
  method: POST
  name: rotatedkimkeyfordomain
  path: /domains/{domainid}/rotatedkim
- description: Postmark Push templates from one server to another
  method: PUT
  name: pushtemplates
  path: /templates/push
personas: []
provider_name: Postmark
provider_slug: postmark
search_terms:
- postmark request a new dkim key
- deletedomain
- postmark update a sender signature
- requestdkimverificationfordomain
- getsendersignature
- listsendersignatures
- requestspfverificationforsendersignature
- api
- editserverinformation
- postmark list servers
- listservers
- postmark get a domain
- requestnewdkimkeyforsendersignature
- postmark delete a domain
- postmark request dns verification for return-path
- postmark rotate dkim key
- createsendersignature
- postmark request dns verification for spf
- getdomain
- rotatedkimkeyfordomain
- deliverability
- postmark delete a sender signature
- requestreturnpathverificationfordomain
- emails
- requestspfverificationfordomain
- deleteserver
- editsendersignature
- postmark update a domain
- postmark
- deletesendersignature
- editdomain
- postmark resend signature confirmation email
- getserverinformation
- postmark get a sender signature
- postmark create a domain
- postmark create a server
- postmark create a sender signature
- postmark get a server
- resendsendersignatureconfirmationemail
- createserver
- postmark delete a server
- postmark request dns verification for dkim
- postmark push templates from one server to another
- pushtemplates
- postmark edit a server
- listdomains
- messaging
- smtp
- postmark list sender signatures
- transactional email
- createdomain
- postmark list domains
slug: postmark-capability
source_filename: postmark-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Postmark Account API\n  description: Postmark makes sending and receiving email incredibly easy. The Account-level API allows users to configure\n    all Servers, Domains, and Sender Signatures associated with an Account.\n  tags:\n  - Postmark\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: postmark\n    baseUri: //api.postmarkapp.com\n    description: Postmark Account API HTTP API.\n    resources:\n    - name: servers-serverid\n      path: /servers/{serverid}\n      operations:\n      - name: getserverinformation\n        method: GET\n        description: Postmark Get a Server\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: serverid\n          in: path\n       \
  \   type: integer\n          required: true\n          description: The ID of the Server to get.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editserverinformation\n        method: PUT\n        description: Postmark Edit a Server\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: serverid\n          in: path\n          type: integer\n          required: true\n          description: The ID of the Server to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteserver\n        method: DELETE\n        description: Postmark Delete a Server\n        inputParameters:\n        - name: X-Postmark-Account-Token\n\
  \          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: serverid\n          in: path\n          type: integer\n          required: true\n          description: The ID of the Server that should be deleted.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: servers\n      path: /servers\n      operations:\n      - name: listservers\n        method: GET\n        description: Postmark List servers\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: count\n          in: query\n          type: integer\n          required: true\n          description: Number of servers to return\
  \ per request.\n        - name: offset\n          in: query\n          type: integer\n          required: true\n          description: Number of servers to skip.\n        - name: name\n          in: query\n          type: string\n          description: Filter by a specific server name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createserver\n        method: POST\n        description: Postmark Create a Server\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: senders\n      path: /senders\n      operations:\n      - name: listsendersignatures\n        method: GET\n    \
  \    description: Postmark List Sender Signatures\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: count\n          in: query\n          type: integer\n          required: true\n          description: Number of records to return per request. Max 500.\n        - name: offset\n          in: query\n          type: integer\n          required: true\n          description: Number of records to skip\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsendersignature\n        method: POST\n        description: Postmark Create a Sender Signature\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description:\
  \ The token associated with the Account on which this request will operate.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: senders-signatureid\n      path: /senders/{signatureid}\n      operations:\n      - name: getsendersignature\n        method: GET\n        description: Postmark Get a Sender Signature\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: signatureid\n          in: path\n          type: integer\n          required: true\n          description: The ID for the Sender Signature that should be retrieved.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editsendersignature\n        method: PUT\n\
  \        description: Postmark Update a Sender Signature\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: signatureid\n          in: path\n          type: integer\n          required: true\n          description: The ID for the Sender Signature that should be modified by the request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesendersignature\n        method: DELETE\n        description: Postmark Delete a Sender Signature\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: signatureid\n\
  \          in: path\n          type: integer\n          required: true\n          description: The ID for the Sender Signature that should be deleted by the request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: senders-signatureid-resend\n      path: /senders/{signatureid}/resend\n      operations:\n      - name: resendsendersignatureconfirmationemail\n        method: POST\n        description: Postmark Resend Signature Confirmation Email\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: signatureid\n          in: path\n          type: integer\n          required: true\n          description: The ID for the Sender Signature that should have its confirmation email resent.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: senders-signatureid-verifyspf\n      path: /senders/{signatureid}/verifyspf\n      operations:\n      - name: requestspfverificationforsendersignature\n        method: POST\n        description: Postmark Request DNS Verification for SPF\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: signatureid\n          in: path\n          type: integer\n          required: true\n          description: The ID for the Sender Signature for which SPF DNS records should be verified.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: senders-signatureid-requestnewdkim\n      path: /senders/{signatureid}/requestnewdkim\n\
  \      operations:\n      - name: requestnewdkimkeyforsendersignature\n        method: POST\n        description: Postmark Request a new DKIM Key\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: signatureid\n          in: path\n          type: integer\n          required: true\n          description: The ID for the Sender Signature for which a new DKIM Key should be generated.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domains\n      path: /domains\n      operations:\n      - name: listdomains\n        method: GET\n        description: Postmark List Domains\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required:\
  \ true\n          description: The token associated with the Account on which this request will operate.\n        - name: count\n          in: query\n          type: integer\n          required: true\n          description: Number of records to return per request. Max 500.\n        - name: offset\n          in: query\n          type: integer\n          required: true\n          description: Number of records to skip\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdomain\n        method: POST\n        description: Postmark Create a Domain\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: domains-domainid\n      path: /domains/{domainid}\n      operations:\n      - name: getdomain\n        method: GET\n        description: Postmark Get a Domain\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: domainid\n          in: path\n          type: integer\n          required: true\n          description: The ID for the Domain that should be retrieved.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editdomain\n        method: PUT\n        description: Postmark Update a Domain\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account\
  \ on which this request will operate.\n        - name: domainid\n          in: path\n          type: integer\n          required: true\n          description: The ID for the Domain that should be modified by the request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedomain\n        method: DELETE\n        description: Postmark Delete a Domain\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: domainid\n          in: path\n          type: integer\n          required: true\n          description: The ID for the Domain that should be deleted by the request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: domains-domainid-verifydkim\n      path: /domains/{domainid}/verifydkim\n      operations:\n      - name: requestdkimverificationfordomain\n        method: PUT\n        description: Postmark Request DNS Verification for DKIM\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: domainid\n          in: path\n          type: integer\n          required: true\n          description: The ID for the Domain for which DKIM DNS records should be verified.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domains-domainid-verifyreturnpath\n      path: /domains/{domainid}/verifyreturnpath\n      operations:\n      - name: requestreturnpathverificationfordomain\n        method: PUT\n        description:\
  \ Postmark Request DNS Verification for Return-Path\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: domainid\n          in: path\n          type: integer\n          required: true\n          description: The ID for the Domain for which Return-Path DNS records should be verified.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domains-domainid-verifyspf\n      path: /domains/{domainid}/verifyspf\n      operations:\n      - name: requestspfverificationfordomain\n        method: POST\n        description: Postmark Request DNS Verification for SPF\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n         \
  \ description: The token associated with the Account on which this request will operate.\n        - name: domainid\n          in: path\n          type: integer\n          required: true\n          description: The ID for the Domain for which SPF DNS records should be verified.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domains-domainid-rotatedkim\n      path: /domains/{domainid}/rotatedkim\n      operations:\n      - name: rotatedkimkeyfordomain\n        method: POST\n        description: Postmark Rotate DKIM Key\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        - name: domainid\n          in: path\n          type: integer\n          required: true\n          description: The ID for the Sender Signature\
  \ for which a new DKIM Key should be generated.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates-push\n      path: /templates/push\n      operations:\n      - name: pushtemplates\n        method: PUT\n        description: Postmark Push templates from one server to another\n        inputParameters:\n        - name: X-Postmark-Account-Token\n          in: header\n          type: string\n          required: true\n          description: The token associated with the Account on which this request will operate.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: postmark-rest\n    description: REST adapter for Postmark Account API.\n    resources:\n    - path: /servers/{serverid}\n      name: getserverinformation\n      operations:\n      - method: GET\n     \
  \   name: getserverinformation\n        description: Postmark Get a Server\n        call: postmark.getserverinformation\n        with:\n          serverid: rest.serverid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /servers/{serverid}\n      name: editserverinformation\n      operations:\n      - method: PUT\n        name: editserverinformation\n        description: Postmark Edit a Server\n        call: postmark.editserverinformation\n        with:\n          serverid: rest.serverid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /servers/{serverid}\n      name: deleteserver\n      operations:\n      - method: DELETE\n        name: deleteserver\n        description: Postmark Delete a Server\n        call: postmark.deleteserver\n        with:\n          serverid: rest.serverid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /servers\n      name: listservers\n      operations:\n\
  \      - method: GET\n        name: listservers\n        description: Postmark List servers\n        call: postmark.listservers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /servers\n      name: createserver\n      operations:\n      - method: POST\n        name: createserver\n        description: Postmark Create a Server\n        call: postmark.createserver\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /senders\n      name: listsendersignatures\n      operations:\n      - method: GET\n        name: listsendersignatures\n        description: Postmark List Sender Signatures\n        call: postmark.listsendersignatures\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /senders\n      name: createsendersignature\n      operations:\n      - method: POST\n        name: createsendersignature\n        description: Postmark Create a Sender Signature\n        call: postmark.createsendersignature\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /senders/{signatureid}\n      name: getsendersignature\n      operations:\n      - method: GET\n        name: getsendersignature\n        description: Postmark Get a Sender Signature\n        call: postmark.getsendersignature\n        with:\n          signatureid: rest.signatureid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /senders/{signatureid}\n      name: editsendersignature\n      operations:\n      - method: PUT\n        name: editsendersignature\n        description: Postmark Update a Sender Signature\n        call: postmark.editsendersignature\n        with:\n          signatureid: rest.signatureid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /senders/{signatureid}\n      name: deletesendersignature\n      operations:\n      - method: DELETE\n        name: deletesendersignature\n        description: Postmark\
  \ Delete a Sender Signature\n        call: postmark.deletesendersignature\n        with:\n          signatureid: rest.signatureid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /senders/{signatureid}/resend\n      name: resendsendersignatureconfirmationemail\n      operations:\n      - method: POST\n        name: resendsendersignatureconfirmationemail\n        description: Postmark Resend Signature Confirmation Email\n        call: postmark.resendsendersignatureconfirmationemail\n        with:\n          signatureid: rest.signatureid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /senders/{signatureid}/verifyspf\n      name: requestspfverificationforsendersignature\n      operations:\n      - method: POST\n        name: requestspfverificationforsendersignature\n        description: Postmark Request DNS Verification for SPF\n        call: postmark.requestspfverificationforsendersignature\n        with:\n   \
  \       signatureid: rest.signatureid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /senders/{signatureid}/requestnewdkim\n      name: requestnewdkimkeyforsendersignature\n      operations:\n      - method: POST\n        name: requestnewdkimkeyforsendersignature\n        description: Postmark Request a new DKIM Key\n        call: postmark.requestnewdkimkeyforsendersignature\n        with:\n          signatureid: rest.signatureid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains\n      name: listdomains\n      operations:\n      - method: GET\n        name: listdomains\n        description: Postmark List Domains\n        call: postmark.listdomains\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains\n      name: createdomain\n      operations:\n      - method: POST\n        name: createdomain\n        description: Postmark Create a Domain\n        call: postmark.createdomain\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains/{domainid}\n      name: getdomain\n      operations:\n      - method: GET\n        name: getdomain\n        description: Postmark Get a Domain\n        call: postmark.getdomain\n        with:\n          domainid: rest.domainid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains/{domainid}\n      name: editdomain\n      operations:\n      - method: PUT\n        name: editdomain\n        description: Postmark Update a Domain\n        call: postmark.editdomain\n        with:\n          domainid: rest.domainid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains/{domainid}\n      name: deletedomain\n      operations:\n      - method: DELETE\n        name: deletedomain\n        description: Postmark Delete a Domain\n        call: postmark.deletedomain\n        with:\n          domainid: rest.domainid\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /domains/{domainid}/verifydkim\n      name: requestdkimverificationfordomain\n      operations:\n      - method: PUT\n        name: requestdkimverificationfordomain\n        description: Postmark Request DNS Verification for DKIM\n        call: postmark.requestdkimverificationfordomain\n        with:\n          domainid: rest.domainid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains/{domainid}/verifyreturnpath\n      name: requestreturnpathverificationfordomain\n      operations:\n      - method: PUT\n        name: requestreturnpathverificationfordomain\n        description: Postmark Request DNS Verification for Return-Path\n        call: postmark.requestreturnpathverificationfordomain\n        with:\n          domainid: rest.domainid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains/{domainid}/verifyspf\n      name: requestspfverificationfordomain\n\
  \      operations:\n      - method: POST\n        name: requestspfverificationfordomain\n        description: Postmark Request DNS Verification for SPF\n        call: postmark.requestspfverificationfordomain\n        with:\n          domainid: rest.domainid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains/{domainid}/rotatedkim\n      name: rotatedkimkeyfordomain\n      operations:\n      - method: POST\n        name: rotatedkimkeyfordomain\n        description: Postmark Rotate DKIM Key\n        call: postmark.rotatedkimkeyfordomain\n        with:\n          domainid: rest.domainid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /templates/push\n      name: pushtemplates\n      operations:\n      - method: PUT\n        name: pushtemplates\n        description: Postmark Push templates from one server to another\n        call: postmark.pushtemplates\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: postmark-mcp\n    transport: http\n    description: MCP adapter for Postmark Account API for AI agent use.\n    tools:\n    - name: getserverinformation\n      description: Postmark Get a Server\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: postmark.getserverinformation\n      with:\n        serverid: tools.serverid\n      inputParameters:\n      - name: serverid\n        type: integer\n        description: The ID of the Server to get.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: editserverinformation\n      description: Postmark Edit a Server\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: postmark.editserverinformation\n      with:\n        serverid: tools.serverid\n      inputParameters:\n      - name: serverid\n        type: integer\n      \
  \  description: The ID of the Server to update.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteserver\n      description: Postmark Delete a Server\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: postmark.deleteserver\n      with:\n        serverid: tools.serverid\n      inputParameters:\n      - name: serverid\n        type: integer\n        description: The ID of the Server that should be deleted.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listservers\n      description: Postmark List servers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: postmark.listservers\n      with:\n        count: tools.count\n        offset: tools.offset\n        name: tools.name\n      inputParameters:\n      - name: count\n        type: integer\n        description: Number\
  \ of servers to return per request.\n        required: true\n      - name: offset\n        type: integer\n        description: Number of servers to skip.\n        required: true\n      - name: name\n        type: string\n        description: Filter by a specific server name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createserver\n      description: Postmark Create a Server\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: postmark.createserver\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsendersignatures\n      description: Postmark List Sender Signatures\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: postmark.listsendersignatures\n      with:\n        count: tools.count\n        offset: tools.offset\n      inputParameters:\n      - name: count\n        type: integer\n        description: Number\
  \ of records to return per request. Max 500.\n        required: true\n      - name: offset\n        type: integer\n        description: Number of records to skip\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsendersignature\n      description: Postmark Create a Sender Signature\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: postmark.createsendersignature\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsendersignature\n      description: Postmark Get a Sender Signature\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: postmark.getsendersignature\n      with:\n        signatureid: tools.signatureid\n      inputParameters:\n      - name: signatureid\n        type: integer\n        description: The ID for the Sender Signature that should be retrieved.\n        required: true\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: editsendersignature\n      description: Postmark Update a Sender Signature\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: postmark.editsendersignature\n      with:\n        signatureid: tools.signatureid\n      inputParameters:\n      - name: signatureid\n        type: integer\n        description: The ID for the Sender Signature that should be modified by the request.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesendersignature\n      description: Postmark Delete a Sender Signature\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: postmark.deletesendersignature\n      with:\n        signatureid: tools.signatureid\n      inputParameters:\n      - name: signatureid\n        type: integer\n        description: The ID for the Sender\
  \ Signature that should be deleted by the request.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resendsendersignatureconfirmationemail\n      description: Postmark Resend Signature Confirmation Email\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: postmark.resendsendersignatureconfirmationemail\n      with:\n        signatureid: tools.signatureid\n      inputParameters:\n      - name: signatureid\n        type: integer\n        description: The ID for the Sender Signature that should have its confirmation email resent.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: requestspfverificationforsendersignature\n      description: Postmark Request DNS Verification for SPF\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: postmark.requestspfverificationforsendersignature\n\
  \      with:\n        signatureid: tools.signatureid\n      inputParameters:\n      - name: signatureid\n        type: integer\n        description: The ID for the Sender Signature for which SPF DNS records should be verified.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: requestnewdkimkeyforsendersignature\n      description: Postmark Request a new DKIM Key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: postmark.requestnewdkimkeyforsendersignature\n      with:\n        signatureid: tools.signatureid\n      inputParameters:\n      - name: signatureid\n        type: integer\n        description: The ID for the Sender Signature for which a new DKIM Key should be generated.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdomains\n      description: Postmark List Domains\n      hints:\n        readOnly: true\n  \
  \      destructive: false\n        idempotent: true\n      call: postmark.listdomains\n      with:\n        count: tools.count\n        offset: tools.offset\n      inputParameters:\n      - name: count\n        type: integer\n        description: Number of records to return per request. Max 500.\n        required: true\n      - name: offset\n        type: integer\n        description: Number of records to skip\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdomain\n      description: Postmark Create a Domain\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: postmark.createdomain\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdomain\n      description: Postmark Get a Domain\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: postmark.getdomain\n      with:\n        domainid: tools.domainid\n\
  \      inputParameters:\n      - name: domainid\n        type: integer\n        description: The ID for the Domain that should be retrieved.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: editdomain\n      description: Postmark Update a Domain\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: postmark.editdomain\n      with:\n        domainid: tools.domainid\n      inputParameters:\n      - name: domainid\n        type: integer\n        description: The ID for the Domain that should be modified by the request.\n        required: true\n      outputParameters:\n      - type: object\n\n\n# --- truncated at 32 KB (34 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/postmark/refs/heads/main/capabilities/postmark-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/postmark/refs/heads/main/capabilities/postmark-capability.yaml
tags:
- Postmark
- API
tools:
- description: Postmark Get a Server
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getserverinformation
- description: Postmark Edit a Server
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: editserverinformation
- description: Postmark Delete a Server
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteserver
- description: Postmark List servers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservers
- description: Postmark Create a Server
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createserver
- description: Postmark List Sender Signatures
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsendersignatures
- description: Postmark Create a Sender Signature
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsendersignature
- description: Postmark Get a Sender Signature
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsendersignature
- description: Postmark Update a Sender Signature
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: editsendersignature
- description: Postmark Delete a Sender Signature
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesendersignature
- description: Postmark Resend Signature Confirmation Email
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resendsendersignatureconfirmationemail
- description: Postmark Request DNS Verification for SPF
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: requestspfverificationforsendersignature
- description: Postmark Request a new DKIM Key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: requestnewdkimkeyforsendersignature
- description: Postmark List Domains
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdomains
- description: Postmark Create a Domain
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdomain
- description: Postmark Get a Domain
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdomain
- description: Postmark Update a Domain
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: editdomain
- description: Postmark Delete a Domain
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedomain
- description: Postmark Request DNS Verification for DKIM
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: requestdkimverificationfordomain
- description: Postmark Request DNS Verification for Return-Path
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: requestreturnpathverificationfordomain
- description: Postmark Request DNS Verification for SPF
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: requestspfverificationfordomain
- description: Postmark Rotate DKIM Key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rotatedkimkeyfordomain
- description: Postmark Push templates from one server to another
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: pushtemplates
---
