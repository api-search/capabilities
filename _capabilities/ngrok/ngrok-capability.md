---
categories: []
consumed_apis: []
description: The ngrok API provides programmatic access to all of ngrok's resources. The API is REST-ish. It follows most of the conventions of a REST API but diverges slightly when the REST model does not fit well. The API listens only on port 443 to help avoid any accidental unencrypted requests. All API access requires an API key.
layout: capability
name: Ngrok API
operations:
- description: Ngrok Create Abuse Report
  method: POST
  name: createabusereport
  path: /abuse_reports
- description: Ngrok Get Abuse Report
  method: GET
  name: getabusereport
  path: /abuse_reports/{id}
- description: Ngrok Create Agent Ingress
  method: POST
  name: createagentingress
  path: /agent_ingresses
- description: Ngrok List Agent Ingresses
  method: GET
  name: listagentingresses
  path: /agent_ingresses
- description: Ngrok Get Agent Ingress
  method: GET
  name: getagentingress
  path: /agent_ingresses/{id}
- description: Ngrok Update Agent Ingress
  method: PATCH
  name: updateagentingress
  path: /agent_ingresses/{id}
- description: Ngrok Delete Agent Ingress
  method: DELETE
  name: deleteagentingress
  path: /agent_ingresses/{id}
- description: Ngrok Create API Key
  method: POST
  name: createapikey
  path: /api_keys
- description: Ngrok List API Keys
  method: GET
  name: listapikeys
  path: /api_keys
- description: Ngrok Get API Key
  method: GET
  name: getapikey
  path: /api_keys/{id}
- description: Ngrok Update API Key
  method: PATCH
  name: updateapikey
  path: /api_keys/{id}
- description: Ngrok Delete API Key
  method: DELETE
  name: deleteapikey
  path: /api_keys/{id}
- description: Ngrok Create Certificate Authority
  method: POST
  name: createcertificateauthority
  path: /certificate_authorities
- description: Ngrok List Certificate Authorities
  method: GET
  name: listcertificateauthorities
  path: /certificate_authorities
- description: Ngrok Get Certificate Authority
  method: GET
  name: getcertificateauthority
  path: /certificate_authorities/{id}
- description: Ngrok Update Certificate Authority
  method: PATCH
  name: updatecertificateauthority
  path: /certificate_authorities/{id}
- description: Ngrok Delete Certificate Authority
  method: DELETE
  name: deletecertificateauthority
  path: /certificate_authorities/{id}
- description: Ngrok Create Credential
  method: POST
  name: createcredential
  path: /credentials
- description: Ngrok List Credentials
  method: GET
  name: listcredentials
  path: /credentials
- description: Ngrok Get Credential
  method: GET
  name: getcredential
  path: /credentials/{id}
- description: Ngrok Update Credential
  method: PATCH
  name: updatecredential
  path: /credentials/{id}
- description: Ngrok Delete Credential
  method: DELETE
  name: deletecredential
  path: /credentials/{id}
- description: Ngrok Create Endpoint
  method: POST
  name: createendpoint
  path: /endpoints
- description: Ngrok List Endpoints
  method: GET
  name: listendpoints
  path: /endpoints
- description: Ngrok Get Endpoint
  method: GET
  name: getendpoint
  path: /endpoints/{id}
- description: Ngrok Update Endpoint
  method: PATCH
  name: updateendpoint
  path: /endpoints/{id}
- description: Ngrok Delete Endpoint
  method: DELETE
  name: deleteendpoint
  path: /endpoints/{id}
- description: Ngrok Create Event Destination
  method: POST
  name: createeventdestination
  path: /event_destinations
- description: Ngrok List Event Destinations
  method: GET
  name: listeventdestinations
  path: /event_destinations
- description: Ngrok Get Event Destination
  method: GET
  name: geteventdestination
  path: /event_destinations/{id}
- description: Ngrok Update Event Destination
  method: PATCH
  name: updateeventdestination
  path: /event_destinations/{id}
- description: Ngrok Delete Event Destination
  method: DELETE
  name: deleteeventdestination
  path: /event_destinations/{id}
- description: Ngrok Create Event Subscription
  method: POST
  name: createeventsubscription
  path: /event_subscriptions
- description: Ngrok List Event Subscriptions
  method: GET
  name: listeventsubscriptions
  path: /event_subscriptions
- description: Ngrok Get Event Subscription
  method: GET
  name: geteventsubscription
  path: /event_subscriptions/{id}
- description: Ngrok Update Event Subscription
  method: PATCH
  name: updateeventsubscription
  path: /event_subscriptions/{id}
- description: Ngrok Delete Event Subscription
  method: DELETE
  name: deleteeventsubscription
  path: /event_subscriptions/{id}
- description: Ngrok Create IP Policy
  method: POST
  name: createippolicy
  path: /ip_policies
- description: Ngrok List IP Policies
  method: GET
  name: listippolicies
  path: /ip_policies
- description: Ngrok Get IP Policy
  method: GET
  name: getippolicy
  path: /ip_policies/{id}
- description: Ngrok Update IP Policy
  method: PATCH
  name: updateippolicy
  path: /ip_policies/{id}
- description: Ngrok Delete IP Policy
  method: DELETE
  name: deleteippolicy
  path: /ip_policies/{id}
- description: Ngrok Create IP Policy Rule
  method: POST
  name: createippolicyrule
  path: /ip_policy_rules
- description: Ngrok List IP Policy Rules
  method: GET
  name: listippolicyrules
  path: /ip_policy_rules
- description: Ngrok Get IP Policy Rule
  method: GET
  name: getippolicyrule
  path: /ip_policy_rules/{id}
- description: Ngrok Update IP Policy Rule
  method: PATCH
  name: updateippolicyrule
  path: /ip_policy_rules/{id}
- description: Ngrok Delete IP Policy Rule
  method: DELETE
  name: deleteippolicyrule
  path: /ip_policy_rules/{id}
- description: Ngrok Create IP Restriction
  method: POST
  name: createiprestriction
  path: /ip_restrictions
- description: Ngrok List IP Restrictions
  method: GET
  name: listiprestrictions
  path: /ip_restrictions
- description: Ngrok Get IP Restriction
  method: GET
  name: getiprestriction
  path: /ip_restrictions/{id}
- description: Ngrok Update IP Restriction
  method: PATCH
  name: updateiprestriction
  path: /ip_restrictions/{id}
- description: Ngrok Delete IP Restriction
  method: DELETE
  name: deleteiprestriction
  path: /ip_restrictions/{id}
- description: Ngrok Create Reserved Address
  method: POST
  name: createreservedaddr
  path: /reserved_addrs
- description: Ngrok List Reserved Addresses
  method: GET
  name: listreservedaddrs
  path: /reserved_addrs
- description: Ngrok Get Reserved Address
  method: GET
  name: getreservedaddr
  path: /reserved_addrs/{id}
- description: Ngrok Update Reserved Address
  method: PATCH
  name: updatereservedaddr
  path: /reserved_addrs/{id}
- description: Ngrok Delete Reserved Address
  method: DELETE
  name: deletereservedaddr
  path: /reserved_addrs/{id}
- description: Ngrok Create Reserved Domain
  method: POST
  name: createreserveddomain
  path: /reserved_domains
- description: Ngrok List Reserved Domains
  method: GET
  name: listreserveddomains
  path: /reserved_domains
- description: Ngrok Get Reserved Domain
  method: GET
  name: getreserveddomain
  path: /reserved_domains/{id}
personas: []
provider_name: ngrok
provider_slug: ngrok
search_terms:
- ngrok get agent ingress
- ngrok delete api key
- createabusereport
- updatereservedaddr
- listeventsubscriptions
- listiprestrictions
- getcredential
- ngrok delete endpoint
- ngrok create endpoint
- ngrok list endpoints
- ngrok get ip policy
- ngrok get event subscription
- ngrok get reserved domain
- ngrok delete ip policy rule
- getapikey
- deleteiprestriction
- deletecertificateauthority
- ngrok delete ip restriction
- ngrok
- updateippolicyrule
- api
- ngrok create certificate authority
- updateapikey
- ngrok update credential
- deletecredential
- deleteapikey
- servers
- createendpoint
- ngrok get certificate authority
- createagentingress
- listippolicies
- updateiprestriction
- ngrok update ip restriction
- ngrok list ip restrictions
- listendpoints
- updateagentingress
- compute
- ngrok create event subscription
- developer tools
- getabusereport
- ngrok delete event subscription
- updateippolicy
- getippolicyrule
- ngrok update event destination
- ngrok create ip policy
- listcredentials
- ngrok list event destinations
- ngrok get endpoint
- ngrok update ip policy rule
- listippolicyrules
- ngrok list event subscriptions
- ngrok get event destination
- ngrok get ip policy rule
- ngrok delete ip policy
- ngrok update ip policy
- ngrok create abuse report
- ngrok list ip policies
- ngrok create credential
- geteventsubscription
- ngrok update certificate authority
- ngrok delete certificate authority
- deleteendpoint
- updateeventsubscription
- ngrok get reserved address
- listapikeys
- createreservedaddr
- ngrok delete reserved address
- listreserveddomains
- createcertificateauthority
- ngrok get ip restriction
- updatecredential
- createreserveddomain
- deleteippolicy
- updateeventdestination
- deleteeventsubscription
- getcertificateauthority
- ngrok create event destination
- ngrok list reserved addresses
- ngrok update agent ingress
- deleteippolicyrule
- getreserveddomain
- getagentingress
- ngrok create reserved domain
- ingress
- ngrok update endpoint
- ngrok list api keys
- ai gateway
- ngrok list credentials
- updatecertificateauthority
- tunnels
- createiprestriction
- ngrok update api key
- api gateway
- ngrok list certificate authorities
- deleteeventdestination
- ngrok get api key
- ngrok list agent ingresses
- createcredential
- ngrok create reserved address
- geteventdestination
- ngrok update reserved address
- ngrok delete agent ingress
- gateways
- ngrok list reserved domains
- deleteagentingress
- listagentingresses
- ngrok get credential
- updateendpoint
- ngrok get abuse report
- getiprestriction
- ngrok create ip restriction
- ngrok delete event destination
- listcertificateauthorities
- deletereservedaddr
- ngrok create agent ingress
- ngrok create api key
- listeventdestinations
- createeventdestination
- getippolicy
- createippolicy
- ngrok update event subscription
- ngrok create ip policy rule
- ngrok list ip policy rules
- listreservedaddrs
- platform
- getreservedaddr
- createapikey
- createippolicyrule
- getendpoint
- ngrok delete credential
- proxies
- createeventsubscription
slug: ngrok-capability
source_filename: ngrok-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ngrok API\n  description: The ngrok API provides programmatic access to all of ngrok's resources. The API is REST-ish. It follows most\n    of the conventions of a REST API but diverges slightly when the REST model does not fit well. The API listens only on\n    port 443 to help avoid any accidental unencrypted requests. All API access requires an API key.\n  tags:\n  - Ngrok\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ngrok\n    baseUri: https://api.ngrok.com\n    description: Ngrok API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{NGROK_TOKEN}}'\n    resources:\n    - name: abuse-reports\n      path: /abuse_reports\n      operations:\n      - name: createabusereport\n        method: POST\n        description: Ngrok Create Abuse Report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: abuse-reports-id\n      path: /abuse_reports/{id}\n      operations:\n      - name: getabusereport\n        method: GET\n        description: Ngrok Get Abuse Report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agent-ingresses\n      path: /agent_ingresses\n      operations:\n      - name: createagentingress\n        method: POST\n        description: Ngrok Create Agent Ingress\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listagentingresses\n        method: GET\n        description: Ngrok List Agent Ingresses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agent-ingresses-id\n      path: /agent_ingresses/{id}\n      operations:\n      - name: getagentingress\n        method:\
  \ GET\n        description: Ngrok Get Agent Ingress\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateagentingress\n        method: PATCH\n        description: Ngrok Update Agent Ingress\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteagentingress\n        method: DELETE\n        description: Ngrok Delete Agent Ingress\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-keys\n      path: /api_keys\n      operations:\n      - name: createapikey\n        method: POST\n        description: Ngrok Create API Key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listapikeys\n        method: GET\n        description:\
  \ Ngrok List API Keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-keys-id\n      path: /api_keys/{id}\n      operations:\n      - name: getapikey\n        method: GET\n        description: Ngrok Get API Key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapikey\n        method: PATCH\n        description: Ngrok Update API Key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapikey\n        method: DELETE\n        description: Ngrok Delete API Key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificate-authorities\n      path: /certificate_authorities\n      operations:\n      - name: createcertificateauthority\n\
  \        method: POST\n        description: Ngrok Create Certificate Authority\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listcertificateauthorities\n        method: GET\n        description: Ngrok List Certificate Authorities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificate-authorities-id\n      path: /certificate_authorities/{id}\n      operations:\n      - name: getcertificateauthority\n        method: GET\n        description: Ngrok Get Certificate Authority\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecertificateauthority\n        method: PATCH\n        description: Ngrok Update Certificate Authority\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: deletecertificateauthority\n        method: DELETE\n        description: Ngrok Delete Certificate Authority\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credentials\n      path: /credentials\n      operations:\n      - name: createcredential\n        method: POST\n        description: Ngrok Create Credential\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listcredentials\n        method: GET\n        description: Ngrok List Credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credentials-id\n      path: /credentials/{id}\n      operations:\n      - name: getcredential\n        method: GET\n        description: Ngrok Get Credential\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecredential\n        method: PATCH\n        description: Ngrok Update Credential\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecredential\n        method: DELETE\n        description: Ngrok Delete Credential\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoints\n      path: /endpoints\n      operations:\n      - name: createendpoint\n        method: POST\n        description: Ngrok Create Endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listendpoints\n        method: GET\n        description: Ngrok List Endpoints\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: endpoints-id\n      path: /endpoints/{id}\n      operations:\n      - name: getendpoint\n        method: GET\n        description: Ngrok Get Endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateendpoint\n        method: PATCH\n        description: Ngrok Update Endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteendpoint\n        method: DELETE\n        description: Ngrok Delete Endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-destinations\n      path: /event_destinations\n      operations:\n      - name: createeventdestination\n        method: POST\n        description: Ngrok Create Event Destination\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listeventdestinations\n        method: GET\n        description: Ngrok List Event Destinations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-destinations-id\n      path: /event_destinations/{id}\n      operations:\n      - name: geteventdestination\n        method: GET\n        description: Ngrok Get Event Destination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateeventdestination\n        method: PATCH\n        description: Ngrok Update Event Destination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteeventdestination\n        method: DELETE\n      \
  \  description: Ngrok Delete Event Destination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-subscriptions\n      path: /event_subscriptions\n      operations:\n      - name: createeventsubscription\n        method: POST\n        description: Ngrok Create Event Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listeventsubscriptions\n        method: GET\n        description: Ngrok List Event Subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-subscriptions-id\n      path: /event_subscriptions/{id}\n      operations:\n      - name: geteventsubscription\n        method: GET\n        description: Ngrok Get Event Subscription\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: updateeventsubscription\n        method: PATCH\n        description: Ngrok Update Event Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteeventsubscription\n        method: DELETE\n        description: Ngrok Delete Event Subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ip-policies\n      path: /ip_policies\n      operations:\n      - name: createippolicy\n        method: POST\n        description: Ngrok Create IP Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listippolicies\n        method: GET\n        description: Ngrok List IP Policies\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: ip-policies-id\n      path: /ip_policies/{id}\n      operations:\n      - name: getippolicy\n        method: GET\n        description: Ngrok Get IP Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateippolicy\n        method: PATCH\n        description: Ngrok Update IP Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteippolicy\n        method: DELETE\n        description: Ngrok Delete IP Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ip-policy-rules\n      path: /ip_policy_rules\n      operations:\n      - name: createippolicyrule\n        method: POST\n        description: Ngrok Create IP Policy Rule\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listippolicyrules\n        method: GET\n        description: Ngrok List IP Policy Rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ip-policy-rules-id\n      path: /ip_policy_rules/{id}\n      operations:\n      - name: getippolicyrule\n        method: GET\n        description: Ngrok Get IP Policy Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateippolicyrule\n        method: PATCH\n        description: Ngrok Update IP Policy Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteippolicyrule\n        method: DELETE\n        description: Ngrok Delete IP Policy\
  \ Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ip-restrictions\n      path: /ip_restrictions\n      operations:\n      - name: createiprestriction\n        method: POST\n        description: Ngrok Create IP Restriction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listiprestrictions\n        method: GET\n        description: Ngrok List IP Restrictions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ip-restrictions-id\n      path: /ip_restrictions/{id}\n      operations:\n      - name: getiprestriction\n        method: GET\n        description: Ngrok Get IP Restriction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ updateiprestriction\n        method: PATCH\n        description: Ngrok Update IP Restriction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteiprestriction\n        method: DELETE\n        description: Ngrok Delete IP Restriction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reserved-addrs\n      path: /reserved_addrs\n      operations:\n      - name: createreservedaddr\n        method: POST\n        description: Ngrok Create Reserved Address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listreservedaddrs\n        method: GET\n        description: Ngrok List Reserved Addresses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: reserved-addrs-id\n      path: /reserved_addrs/{id}\n      operations:\n      - name: getreservedaddr\n        method: GET\n        description: Ngrok Get Reserved Address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatereservedaddr\n        method: PATCH\n        description: Ngrok Update Reserved Address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletereservedaddr\n        method: DELETE\n        description: Ngrok Delete Reserved Address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reserved-domains\n      path: /reserved_domains\n      operations:\n      - name: createreserveddomain\n        method: POST\n        description: Ngrok Create Reserved Domain\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listreserveddomains\n        method: GET\n        description: Ngrok List Reserved Domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reserved-domains-id\n      path: /reserved_domains/{id}\n      operations:\n      - name: getreserveddomain\n        method: GET\n        description: Ngrok Get Reserved Domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ngrok-rest\n    description: REST adapter for Ngrok API.\n    resources:\n    - path: /abuse_reports\n      name: createabusereport\n      operations:\n      - method: POST\n        name: createabusereport\n        description: Ngrok Create Abuse Report\n        call: ngrok.createabusereport\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /abuse_reports/{id}\n      name: getabusereport\n      operations:\n      - method: GET\n        name: getabusereport\n        description: Ngrok Get Abuse Report\n        call: ngrok.getabusereport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agent_ingresses\n      name: createagentingress\n      operations:\n      - method: POST\n        name: createagentingress\n        description: Ngrok Create Agent Ingress\n        call: ngrok.createagentingress\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agent_ingresses\n      name: listagentingresses\n      operations:\n      - method: GET\n        name: listagentingresses\n        description: Ngrok List Agent Ingresses\n        call: ngrok.listagentingresses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agent_ingresses/{id}\n    \
  \  name: getagentingress\n      operations:\n      - method: GET\n        name: getagentingress\n        description: Ngrok Get Agent Ingress\n        call: ngrok.getagentingress\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agent_ingresses/{id}\n      name: updateagentingress\n      operations:\n      - method: PATCH\n        name: updateagentingress\n        description: Ngrok Update Agent Ingress\n        call: ngrok.updateagentingress\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agent_ingresses/{id}\n      name: deleteagentingress\n      operations:\n      - method: DELETE\n        name: deleteagentingress\n        description: Ngrok Delete Agent Ingress\n        call: ngrok.deleteagentingress\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api_keys\n      name: createapikey\n      operations:\n      - method: POST\n        name: createapikey\n        description:\
  \ Ngrok Create API Key\n        call: ngrok.createapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api_keys\n      name: listapikeys\n      operations:\n      - method: GET\n        name: listapikeys\n        description: Ngrok List API Keys\n        call: ngrok.listapikeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api_keys/{id}\n      name: getapikey\n      operations:\n      - method: GET\n        name: getapikey\n        description: Ngrok Get API Key\n        call: ngrok.getapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api_keys/{id}\n      name: updateapikey\n      operations:\n      - method: PATCH\n        name: updateapikey\n        description: Ngrok Update API Key\n        call: ngrok.updateapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api_keys/{id}\n      name: deleteapikey\n      operations:\n\
  \      - method: DELETE\n        name: deleteapikey\n        description: Ngrok Delete API Key\n        call: ngrok.deleteapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /certificate_authorities\n      name: createcertificateauthority\n      operations:\n      - method: POST\n        name: createcertificateauthority\n        description: Ngrok Create Certificate Authority\n        call: ngrok.createcertificateauthority\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /certificate_authorities\n      name: listcertificateauthorities\n      operations:\n      - method: GET\n        name: listcertificateauthorities\n        description: Ngrok List Certificate Authorities\n        call: ngrok.listcertificateauthorities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /certificate_authorities/{id}\n      name: getcertificateauthority\n      operations:\n      - method: GET\n\
  \        name: getcertificateauthority\n        description: Ngrok Get Certificate Authority\n        call: ngrok.getcertificateauthority\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /certificate_authorities/{id}\n      name: updatecertificateauthority\n      operations:\n      - method: PATCH\n        name: updatecertificateauthority\n        description: Ngrok Update Certificate Authority\n        call: ngrok.updatecertificateauthority\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /certificate_authorities/{id}\n      name: deletecertificateauthority\n      operations:\n      - method: DELETE\n        name: deletecertificateauthority\n        description: Ngrok Delete Certificate Authority\n        call: ngrok.deletecertificateauthority\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /credentials\n      name: createcredential\n      operations:\n      - method: POST\n\
  \        name: createcredential\n        description: Ngrok Create Credential\n        call: ngrok.createcredential\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /credentials\n      name: listcredentials\n      operations:\n      - method: GET\n        name: listcredentials\n        description: Ngrok List Credentials\n        call: ngrok.listcredentials\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /credentials/{id}\n      name: getcredential\n      operations:\n      - method: GET\n        name: getcredential\n        description: Ngrok Get Credential\n        call: ngrok.getcredential\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /credentials/{id}\n      name: updatecredential\n      operations:\n      - method: PATCH\n        name: updatecredential\n        description: Ngrok Update Credential\n        call: ngrok.updatecredential\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n    - path: /credentials/{id}\n      name: deletecredential\n      operations:\n      - method: DELETE\n        name: deletecredential\n        description: Ngrok Delete Credential\n        call: ngrok.deletecredential\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoints\n      name: createendpoint\n      operations:\n      - method: POST\n        name: createendpoint\n        description: Ngrok Create Endpoint\n        call: ngrok.createendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoints\n      name: listendpoints\n      operations:\n      - method: GET\n        name: listendpoints\n        description: Ngrok List Endpoints\n        call: ngrok.listendpoints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoints/{id}\n      name: getendpoint\n      operations:\n      - method: GET\n        name: getendpoint\n\
  \        description: Ngrok Get Endpoint\n        call: ngrok.getendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoints/{id}\n      name: updateendpoint\n      operations:\n      - method: PATCH\n        name: updateendpoint\n        description: Ngrok Update Endpoint\n        call: ngrok.updateendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoints/{id}\n      name: deleteendpoint\n      operations:\n      - method: DELETE\n        name: deleteendpoint\n        description: Ngrok Delete Endpoint\n        call: ngrok.deleteendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event_destinations\n      name: createeventdestination\n      operations:\n      - method: POST\n        name: createeventdestination\n        description: Ngrok Create Event Destination\n        call: ngrok.createeventdestination\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /event_destinations\n      name: listeventdestinations\n      operations:\n      - method: GET\n        name: listeventdestinations\n        description: Ngrok List Event Destinations\n        call: ngrok.listeventdestinations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event_destinations/{id}\n      name: geteventdestination\n      operations:\n      - method: GET\n        name: geteventdestination\n        description: Ngrok Get Event Destination\n        call: ngrok.geteventdestination\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event_destinations/{id}\n      name: updateeventdestination\n      operations:\n      - method: PATCH\n        name: updateeventdestination\n        description: Ngrok Update Event Destination\n        call: ngrok.updateeventdestination\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event_destinations/{id}\n\
  \      name: deleteeventdestination\n      operations:\n      - method: DELETE\n        name: deleteeventdestination\n        description: Ngrok Delete Event Destination\n        call: ngrok.deleteeventdestination\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event_subscriptions\n      name: createeventsubscription\n      operations:\n      - method: POST\n        name: createeventsubscription\n        description: Ngrok Create Event Subscription\n        call: ngrok.createeventsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event_subscriptions\n      name: listeventsubscriptions\n      operations:\n      - method: GET\n        name: listeventsubscriptions\n        description: Ngrok List Event Subscriptions\n        call: ngrok.listeventsubscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event_subscriptions/{id}\n      name: geteventsubscription\n\
  \      operations:\n      - method: GET\n        name: geteventsubscription\n        description: Ngrok Get Event Subscription\n        call: ngrok.geteventsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event_subscriptions/{id}\n      name: updateeventsubscription\n      operations:\n      - method: PATCH\n        name: updateeventsubscription\n        description: Ngrok Update Event Subscription\n        call: ngrok.updateeventsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event_subscriptions/{id}\n      name: deleteeventsubscription\n      operations:\n      - method: DELETE\n        name: deleteeventsubscription\n        description: Ngrok Delete Event Subscription\n        call: ngrok.deleteeventsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ip_policies\n      name: createippolicy\n      operations:\n      - method: POST\n\
  \        name: createippolicy\n        description: Ngrok Create IP Policy\n        call: ngrok.createippolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ip_policies\n      name: listippolicies\n      operations:\n      - method: GET\n        name: listippolicies\n        description: Ngrok List IP Policies\n        call: ngrok.listippolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ip_policies/{id}\n      name: getippolicy\n      operations:\n      - method: GET\n        name: getippolicy\n        description: Ngrok Get IP Policy\n        call: ngrok.getippolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ip_policies/{id}\n      name: updateippolicy\n      operations:\n      - method: PATCH\n        name: updateippolicy\n        description: Ngrok Update IP Policy\n        call: ngrok.updateippolicy\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /ip_policies/{id}\n      name: deleteippolicy\n      operations:\n      - method: DELETE\n        name: deleteippolicy\n        description: Ngrok Delete IP Policy\n        call: ngrok.deleteippolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ip_policy_rules\n      name: createippolicyrule\n      operations:\n      - method: POST\n        name: createippolicyrule\n        description: Ngrok Create IP Policy Rule\n        call: ngrok.createippolicyrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ip_policy_rules\n      name: listippolicyrules\n      operations:\n      - method: GET\n        name: listippolicyrules\n        description: Ngrok List IP Policy Rules\n        call: ngrok.listippolicyrules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ip_policy_rules/{id}\n      name: getippolicyrule\n      operations:\n      - method:\
  \ GET\n        name: getippolicyrule\n        description: Ngrok Get IP Policy Rule\n        call: ngrok.getippolicyrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ip_policy_rules/{id}\n      name: updateippolicyrule\n      operations:\n      - method: PATCH\n        name: updateippolicyrule\n        description: Ngrok Update IP Policy Rule\n        call: ngrok.updateippolicyrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ip_policy_rules/{id}\n      name: deleteippolicyrule\n      operations:\n      - method: DELETE\n        name: deleteippolicyrule\n        description: Ngrok Delete IP Policy Rule\n        call: ngrok.deleteippolicyrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ip_restrictions\n      name: createiprestriction\n      operations:\n      - method: POST\n        name: createiprestriction\n        description: Ngrok Create IP Restriction\n\
  \        call: ngrok.createiprestriction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ip_restrictions\n      name: listiprestrictions\n      operations:\n      - method: GET\n        name: listiprestrictions\n        description: Ngrok List IP Restrictions\n        call: ngrok.listiprestrictions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ip_restrictions/{id}\n      name: getiprestriction\n      operations:\n      - method: GET\n        name: getiprestriction\n        description: Ngrok Get IP Restriction\n        call: ngrok.getiprestriction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ip_restrictions/{id}\n      name: updateiprestriction\n      operations:\n      - method: PATCH\n        name: updateiprestriction\n        description: Ngrok Update IP Restriction\n        call: ngrok.updateiprestriction\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /ip_restrictions/{id}\n      name: deleteiprestriction\n      operations:\n      - method: DELETE\n        name: deleteiprestriction\n        description: Ngrok Delete IP Restriction\n        call: ngrok.deleteiprestriction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reserved_addrs\n      name: createreservedaddr\n      operations:\n      - method: POST\n        name: createreservedaddr\n        description: Ngrok Create Reserved Address\n        call: ngrok.createreservedaddr\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reserved_addrs\n      name: listreservedaddrs\n      operations:\n      - method: GET\n        name: listreservedaddrs\n        description: Ngrok List Reserved Addresses\n        call: ngrok.listreservedaddrs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reserved_addrs/{id}\n      name: getreservedaddr\n  \
  \    operations:\n      - method: GET\n        name: getreservedaddr\n        description: Ngrok Get Reserved Address\n        call: ngrok.getreservedaddr\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reserved_addrs/{id}\n      name: updatereservedaddr\n      operations:\n      - method: PATCH\n        name: updatereservedaddr\n        description: Ngrok Update Reserved Address\n        call: ngrok.updatereservedaddr\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reserved_addrs/{id}\n      name: deletereservedaddr\n      operations:\n      - method: DELETE\n        name: deletereservedaddr\n        description: Ngrok Delete Reserved Address\n        call: ngrok.deletereservedaddr\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\n\n# --- truncated at 32 KB (48 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/ngrok/refs/heads/main/capabilities/ngrok-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ngrok/refs/heads/main/capabilities/ngrok-capability.yaml
tags:
- Ngrok
- API
tools:
- description: Ngrok Create Abuse Report
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createabusereport
- description: Ngrok Get Abuse Report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getabusereport
- description: Ngrok Create Agent Ingress
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createagentingress
- description: Ngrok List Agent Ingresses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listagentingresses
- description: Ngrok Get Agent Ingress
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getagentingress
- description: Ngrok Update Agent Ingress
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateagentingress
- description: Ngrok Delete Agent Ingress
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteagentingress
- description: Ngrok Create API Key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapikey
- description: Ngrok List API Keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapikeys
- description: Ngrok Get API Key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapikey
- description: Ngrok Update API Key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateapikey
- description: Ngrok Delete API Key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapikey
- description: Ngrok Create Certificate Authority
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcertificateauthority
- description: Ngrok List Certificate Authorities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcertificateauthorities
- description: Ngrok Get Certificate Authority
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcertificateauthority
- description: Ngrok Update Certificate Authority
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecertificateauthority
- description: Ngrok Delete Certificate Authority
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecertificateauthority
- description: Ngrok Create Credential
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcredential
- description: Ngrok List Credentials
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcredentials
- description: Ngrok Get Credential
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcredential
- description: Ngrok Update Credential
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecredential
- description: Ngrok Delete Credential
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecredential
- description: Ngrok Create Endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createendpoint
- description: Ngrok List Endpoints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listendpoints
- description: Ngrok Get Endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getendpoint
- description: Ngrok Update Endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateendpoint
- description: Ngrok Delete Endpoint
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteendpoint
- description: Ngrok Create Event Destination
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createeventdestination
- description: Ngrok List Event Destinations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listeventdestinations
- description: Ngrok Get Event Destination
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteventdestination
- description: Ngrok Update Event Destination
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateeventdestination
- description: Ngrok Delete Event Destination
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteeventdestination
- description: Ngrok Create Event Subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createeventsubscription
- description: Ngrok List Event Subscriptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listeventsubscriptions
- description: Ngrok Get Event Subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteventsubscription
- description: Ngrok Update Event Subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateeventsubscription
- description: Ngrok Delete Event Subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteeventsubscription
- description: Ngrok Create IP Policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createippolicy
- description: Ngrok List IP Policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listippolicies
- description: Ngrok Get IP Policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getippolicy
- description: Ngrok Update IP Policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateippolicy
- description: Ngrok Delete IP Policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteippolicy
- description: Ngrok Create IP Policy Rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createippolicyrule
- description: Ngrok List IP Policy Rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listippolicyrules
- description: Ngrok Get IP Policy Rule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getippolicyrule
- description: Ngrok Update IP Policy Rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateippolicyrule
- description: Ngrok Delete IP Policy Rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteippolicyrule
- description: Ngrok Create IP Restriction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createiprestriction
- description: Ngrok List IP Restrictions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listiprestrictions
- description: Ngrok Get IP Restriction
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getiprestriction
- description: Ngrok Update IP Restriction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateiprestriction
- description: Ngrok Delete IP Restriction
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteiprestriction
- description: Ngrok Create Reserved Address
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createreservedaddr
- description: Ngrok List Reserved Addresses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreservedaddrs
- description: Ngrok Get Reserved Address
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreservedaddr
- description: Ngrok Update Reserved Address
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatereservedaddr
- description: Ngrok Delete Reserved Address
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletereservedaddr
- description: Ngrok Create Reserved Domain
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createreserveddomain
- description: Ngrok List Reserved Domains
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreserveddomains
- description: Ngrok Get Reserved Domain
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreserveddomain
---
