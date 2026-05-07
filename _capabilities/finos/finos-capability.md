---
categories: []
consumed_apis: []
description: This document refers to Symphony API calls to send and receive messages and content. They need the on-premise Agent installed to perform decryption/encryption of content. - sessionToken and keyManagerToken can be obtained by calling the authenticationAPI on the symphony back end and the key manager respectively. Refer to the methods described in authenticatorAPI.yaml. - Actions are defined to be atomic, ie will succeed in their entirety or fail and have changed nothing. - If it returns a 40X status then it will have sent no message to any stream even if a request to some subset of the requeste
layout: capability
name: Agent API
operations:
- description: Checks health status
  method: GET
  name: v3health
  path: /v3/health
- description: Checks health status of services and users
  method: GET
  name: v3extendedhealth
  path: /v3/health/extended
- description: Import messages from other systems into Symphony.
  method: POST
  name: post-v4-message-import
  path: /v4/message/import
- description: Post a message to multiple existing streams.
  method: POST
  name: post-v4-message-blast
  path: /v4/message/blast
- description: Get a message by ID
  method: GET
  name: get-v1-message-id
  path: /v1/message/{id}
- description: Search messages
  method: GET
  name: get-v1-message-search
  path: /v1/message/search
- description: Search messages
  method: POST
  name: post-v1-message-search
  path: /v1/message/search
- description: Download an attachment.
  method: GET
  name: get-v1-stream-sid-attachment
  path: /v1/stream/{sid}/attachment
- description: Get messages from an existing stream.
  method: GET
  name: get-v4-stream-sid-message
  path: /v4/stream/{sid}/message
- description: Post a message to one existing stream.
  method: POST
  name: post-v4-stream-sid-message-create
  path: /v4/stream/{sid}/message/create
- description: Update an existing message.
  method: POST
  name: post-v4-stream-sid-message-mid-update
  path: /v4/stream/{sid}/message/{mid}/update
- description: PROVISIONAL - Share a piece of content into Symphony
  method: POST
  name: post-v3-stream-sid-share
  path: /v3/stream/{sid}/share
- description: Test endpoint, returns input.
  method: POST
  name: post-v1-util-echo
  path: /v1/util/echo
- description: List signals for the requesting user. This includes signals that the user has created and public signals to which they subscribed.
  method: GET
  name: get-v1-signals-list
  path: /v1/signals/list
- description: Get details of the requested signal.
  method: GET
  name: get-v1-signals-id-get
  path: /v1/signals/{id}/get
- description: Create a signal.
  method: POST
  name: post-v1-signals-create
  path: /v1/signals/create
- description: Update a signal.
  method: POST
  name: post-v1-signals-id-update
  path: /v1/signals/{id}/update
- description: Delete a signal.
  method: POST
  name: post-v1-signals-id-delete
  path: /v1/signals/{id}/delete
- description: Subscribe to a Signal.
  method: POST
  name: post-v1-signals-id-subscribe
  path: /v1/signals/{id}/subscribe
- description: Unsubscribe to a Signal.
  method: POST
  name: post-v1-signals-id-unsubscribe
  path: /v1/signals/{id}/unsubscribe
- description: Get the subscribers of a signal
  method: GET
  name: get-v1-signals-id-subscribers
  path: /v1/signals/{id}/subscribers
- description: Get information about the Agent
  method: GET
  name: get-v1-info
  path: /v1/info
- description: Get all policies
  method: GET
  name: get-v1-dlp-policies
  path: /v1/dlp/policies
- description: Creates a policy
  method: POST
  name: post-v1-dlp-policies
  path: /v1/dlp/policies
- description: Get a policy
  method: GET
  name: get-v1-dlp-policies-policyid
  path: /v1/dlp/policies/{policyId}
- description: Updates a policy. Cannot be used for creation.
  method: PUT
  name: put-v1-dlp-policies-policyid
  path: /v1/dlp/policies/{policyId}
- description: Delete a policy
  method: DELETE
  name: delete-v1-dlp-policies-policyid
  path: /v1/dlp/policies/{policyId}
- description: Enables a policy.
  method: POST
  name: post-v1-dlp-policies-policyid-enable
  path: /v1/dlp/policies/{policyId}/enable
- description: Disables a policy.
  method: POST
  name: post-v1-dlp-policies-policyid-disable
  path: /v1/dlp/policies/{policyId}/disable
- description: Get all dictionary metadatas
  method: GET
  name: get-v1-dlp-dictionaries
  path: /v1/dlp/dictionaries
- description: Create a dictionary
  method: POST
  name: post-v1-dlp-dictionaries
  path: /v1/dlp/dictionaries
- description: Get dictionary metadata
  method: GET
  name: get-v1-dlp-dictionaries-dictid
  path: /v1/dlp/dictionaries/{dictId}
- description: Updates a dictionary
  method: PUT
  name: put-v1-dlp-dictionaries-dictid
  path: /v1/dlp/dictionaries/{dictId}
- description: Delete a dictionary
  method: DELETE
  name: delete-v1-dlp-dictionaries-dictid
  path: /v1/dlp/dictionaries/{dictId}
- description: Downloads Base 64 encoded dictionary content.
  method: GET
  name: get-v1-dlp-dictionaries-dictid-data-download
  path: /v1/dlp/dictionaries/{dictId}/data/download
- description: Override dictionary content with provided content.
  method: POST
  name: post-v1-dlp-dictionaries-dictid-data-upload
  path: /v1/dlp/dictionaries/{dictId}/data/upload
- description: Get violations as a result of policy enforcement on messages.
  method: GET
  name: get-v1-dlp-violations-message
  path: /v1/dlp/violations/message
- description: Get violations as a result of policy enforcement on streams.
  method: GET
  name: get-v1-dlp-violations-stream
  path: /v1/dlp/violations/stream
- description: Get violations as a result of policy enforcement on signals.
  method: GET
  name: get-v1-dlp-violations-signal
  path: /v1/dlp/violations/signal
- description: Get all policies
  method: GET
  name: get-v3-dlp-policies
  path: /v3/dlp/policies
- description: Creates a policy
  method: POST
  name: post-v3-dlp-policies
  path: /v3/dlp/policies
- description: Get a policy
  method: GET
  name: get-v3-dlp-policies-policyid
  path: /v3/dlp/policies/{policyId}
- description: Updates a policy. Cannot be used for creation.
  method: POST
  name: post-v3-dlp-policies-policyid-update
  path: /v3/dlp/policies/{policyId}/update
- description: Delete a policy
  method: POST
  name: post-v3-dlp-policies-policyid-delete
  path: /v3/dlp/policies/{policyId}/delete
- description: Enables a policy.
  method: POST
  name: post-v3-dlp-policies-policyid-enable
  path: /v3/dlp/policies/{policyId}/enable
- description: Disables a policy.
  method: POST
  name: post-v3-dlp-policies-policyid-disable
  path: /v3/dlp/policies/{policyId}/disable
- description: Get violations as a result of policy enforcement on messages.
  method: GET
  name: get-v3-dlp-violations-message
  path: /v3/dlp/violations/message
- description: Get violations as a result of policy enforcement on streams.
  method: GET
  name: get-v3-dlp-violations-stream
  path: /v3/dlp/violations/stream
- description: Get violations as a result of policy enforcement on signals.
  method: GET
  name: get-v3-dlp-violations-signal
  path: /v3/dlp/violations/signal
- description: Get attachments that were sent as part of messages that were flagged by the DLP System.
  method: GET
  name: get-v3-dlp-violation-attachment
  path: /v3/dlp/violation/attachment
- description: Get a list of actions performed by a privileged account acting as privileged user given a period of time.
  method: GET
  name: get-v1-audittrail-privilegeduser
  path: /v1/audittrail/privilegeduser
- description: Returns the list of active datafeeds of the user.
  method: GET
  name: listdatafeed
  path: /v5/datafeeds
- description: Create a new real time feed of messages and events.
  method: POST
  name: createdatafeed
  path: /v5/datafeeds
- description: Delete the specified real time message / event stream ("datafeed").
  method: DELETE
  name: deletedatafeed
  path: /v5/datafeeds/{datafeedId}
- description: Read the specified real time message / event stream ("datafeed").
  method: POST
  name: readdatafeed
  path: /v5/datafeeds/{datafeedId}/read
- description: Creates and Reads a real time feed of messages and events of your pod (Datahose)
  method: POST
  name: readevents
  path: /v5/events/read
personas: []
provider_name: FINOS
provider_slug: finos
search_terms:
- get v3 dlp violations signal
- post v3 stream sid share
- put v1 dlp policies policyid
- api
- get v1 dlp violations message
- get v3 dlp policies
- enables a policy.
- get information about the agent
- download an attachment.
- read the specified real time message / event stream ("datafeed").
- get v1 dlp violations signal
- get v1 dlp dictionaries dictid data download
- get all policies
- get v3 dlp violations stream
- post v3 dlp policies policyid update
- post v1 dlp dictionaries dictid data upload
- get v1 dlp violations stream
- get v1 dlp policies
- get v1 dlp dictionaries
- delete a dictionary
- post v1 dlp policies policyid disable
- get v1 info
- get v3 dlp policies policyid
- post v3 dlp policies policyid delete
- unsubscribe to a signal.
- delete a signal.
- get attachments that were sent as part of messages that were flagged by the dlp system.
- get violations as a result of policy enforcement on streams.
- updates a dictionary
- returns the list of active datafeeds of the user.
- post v3 dlp policies policyid enable
- get v3 dlp violation attachment
- get details of the requested signal.
- get a policy
- get v1 audittrail privilegeduser
- listdatafeed
- financial services
- post v1 dlp dictionaries
- delete v1 dlp policies policyid
- get v4 stream sid message
- post v1 dlp policies policyid enable
- update an existing message.
- create a signal.
- get v3 dlp violations message
- get messages from an existing stream.
- test endpoint, returns input.
- post v4 message import
- delete a policy
- get v1 message id
- get a message by id
- get v1 signals id get
- post v1 signals id unsubscribe
- readdatafeed
- subscribe to a signal.
- createdatafeed
- v3health
- post v1 signals create
- list signals for the requesting user. this includes signals that the user has created and public signals to which they subscribed.
- post v3 dlp policies policyid disable
- get v1 signals list
- get v1 signals id subscribers
- downloads base 64 encoded dictionary content.
- provisional - share a piece of content into symphony
- post a message to multiple existing streams.
- deletedatafeed
- finos
- create a dictionary
- post v1 signals id update
- post v1 dlp policies
- put v1 dlp dictionaries dictid
- updates a policy. cannot be used for creation.
- checks health status
- post v4 message blast
- get v1 dlp dictionaries dictid
- get a list of actions performed by a privileged account acting as privileged user given a period of time.
- get dictionary metadata
- checks health status of services and users
- post v3 dlp policies
- get v1 stream sid attachment
- get all dictionary metadatas
- creates and reads a real time feed of messages and events of your pod (datahose)
- post v1 message search
- post v1 util echo
- linux foundation
- open source
- delete the specified real time message / event stream ("datafeed").
- fintech
- import messages from other systems into symphony.
- creates a policy
- get the subscribers of a signal
- create a new real time feed of messages and events.
- delete v1 dlp dictionaries dictid
- update a signal.
- get violations as a result of policy enforcement on messages.
- post v1 signals id delete
- search messages
- get violations as a result of policy enforcement on signals.
- get v1 message search
- disables a policy.
- v3extendedhealth
- post v4 stream sid message create
- post v1 signals id subscribe
- readevents
- post v4 stream sid message mid update
- override dictionary content with provided content.
- get v1 dlp policies policyid
- post a message to one existing stream.
slug: finos-capability
source_filename: finos-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Agent API\n  description: This document refers to Symphony API calls to send and receive messages and content. They need the on-premise\n    Agent installed to perform decryption/encryption of content. - sessionToken and keyManagerToken can be obtained by calling\n    the authenticationAPI on the symphony back end and the key manager respectively. Refer to the methods described in authenticatorAPI.yaml.\n    - Actions are defined to be atomic, ie will succeed in their entirety or fail and have changed nothing. - If it returns\n    a 40X status then it will have sent no message to any stream even if a request to some subset of the requeste\n  tags:\n  - Finos\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: finos\n    baseUri: youragentURL.symphony.com/agent\n    description: Agent API HTTP API.\n    resources:\n    - name: v3-health\n      path: /v3/health\n      operations:\n\
  \      - name: v3health\n        method: GET\n        description: Checks health status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-health-extended\n      path: /v3/health/extended\n      operations:\n      - name: v3extendedhealth\n        method: GET\n        description: Checks health status of services and users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-message-import\n      path: /v4/message/import\n      operations:\n      - name: post-v4-message-import\n        method: POST\n        description: Import messages from other systems into Symphony.\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n   \
  \       type: string\n          description: Key Manager authentication token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-message-blast\n      path: /v4/message/blast\n      operations:\n      - name: post-v4-message-blast\n        method: POST\n        description: Post a message to multiple existing streams.\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Authorization token used to make delegated calls.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-message-id\n      path: /v1/message/{id}\n      operations:\n      - name: get-v1-message-id\n        method:\
  \ GET\n        description: Get a message by ID\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Message ID as a URL-safe string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-message-search\n      path: /v1/message/search\n      operations:\n      - name: get-v1-message-search\n        method: GET\n        description: Search messages\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: The search query. See above for the query\
  \ syntax.\n        - name: skip\n          in: query\n          type: integer\n          description: No. of results to skip.\n        - name: limit\n          in: query\n          type: integer\n          description: Max no. of results to return. If no value is provided, 50 is the default.\n        - name: scope\n          in: query\n          type: string\n          description: Describes where content should be searched for that query. It can exclusively apply to Symphony content\n            or to one Connector.\n        - name: sortDir\n          in: query\n          type: string\n          description: 'Messages sort direction : ASC or DESC (default to DESC)'\n        - name: tier\n          in: query\n          type: string\n          description: 'Target search tier : hot, warm or all (default to hot)'\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n\
  \          in: header\n          type: string\n          description: Key Manager authentication token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-v1-message-search\n        method: POST\n        description: Search messages\n        inputParameters:\n        - name: skip\n          in: query\n          type: integer\n          description: No. of results to skip.\n        - name: limit\n          in: query\n          type: integer\n          description: Max no. of results to return. If no value is provided, 50 is the default.\n        - name: scope\n          in: query\n          type: string\n          description: Describes where content should be searched for that query. It can exclusively apply to Symphony content\n            or to one Connector.\n        - name: sortDir\n          in: query\n          type: string\n          description: 'Messages sort direction : ASC or DESC\
  \ (default to DESC)'\n        - name: tier\n          in: query\n          type: string\n          description: 'Target search tier : hot, warm or all (default to hot)'\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-stream-sid-attachment\n      path: /v1/stream/{sid}/attachment\n      operations:\n      - name: get-v1-stream-sid-attachment\n        method: GET\n        description: Download an attachment.\n        inputParameters:\n        - name: sid\n          in: path\n          type: string\n          required: true\n          description: Stream ID\n        - name: fileId\n          in: query\n    \
  \      type: string\n          required: true\n          description: The attachment ID (Base64-encoded)\n        - name: messageId\n          in: query\n          type: string\n          required: true\n          description: The ID of the message containing the attachment\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-stream-sid-message\n      path: /v4/stream/{sid}/message\n      operations:\n      - name: get-v4-stream-sid-message\n        method: GET\n        description: Get messages from an existing stream.\n        inputParameters:\n        - name: sid\n          in: path\n          type: string\n\
  \          required: true\n          description: Stream ID\n        - name: since\n          in: query\n          type: integer\n          required: true\n          description: Timestamp of first required message. This is a long integer value representing milliseconds since Jan\n            1 1970\n        - name: until\n          in: query\n          type: integer\n          description: Timestamp of last required message. This is a long integer value representing milliseconds since Jan\n            1 1970\n        - name: skip\n          in: query\n          type: integer\n          description: No. of messages to skip.\n        - name: limit\n          in: query\n          type: integer\n          description: Max No. of messages to return. If no value is provided, 50 is the default. The maximum supported value\n            is 500.\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n\
  \        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-stream-sid-message-create\n      path: /v4/stream/{sid}/message/create\n      operations:\n      - name: post-v4-stream-sid-message-create\n        method: POST\n        description: Post a message to one existing stream.\n        inputParameters:\n        - name: sid\n          in: path\n          type: string\n          required: true\n          description: Stream ID\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Authorization token used to make delegated calls.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-stream-sid-message-mid-update\n      path: /v4/stream/{sid}/message/{mid}/update\n      operations:\n      - name: post-v4-stream-sid-message-mid-update\n        method: POST\n        description: Update an existing message.\n        inputParameters:\n        - name: sid\n          in: path\n          type: string\n          required: true\n          description: Stream ID\n        - name: mid\n          in: path\n          type: string\n          required: true\n          description: ID of the message to be updated\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Authorization token used to make delegated calls.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v3-stream-sid-share\n      path: /v3/stream/{sid}/share\n      operations:\n      - name: post-v3-stream-sid-share\n        method: POST\n        description: PROVISIONAL - Share a piece of content into Symphony\n        inputParameters:\n        - name: sid\n          in: path\n          type: string\n          required: true\n          description: Stream ID\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-util-echo\n      path: /v1/util/echo\n      operations:\n      - name: post-v1-util-echo\n        method: POST\n      \
  \  description: Test endpoint, returns input.\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-signals-list\n      path: /v1/signals/list\n      operations:\n      - name: get-v1-signals-list\n        method: GET\n        description: List signals for the requesting user. This includes signals that the user has created and public signals\n          to which they subscribed.\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n\
  \          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: skip\n          in: query\n          type: integer\n          description: No. of signals to skip.\n        - name: limit\n          in: query\n          type: integer\n          description: Max no. of signals to return. If no value is provided, 50 is the default. The maximum supported value\n            is 500.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-signals-id-get\n      path: /v1/signals/{id}/get\n      operations:\n      - name: get-v1-signals-id-get\n        method: GET\n        description: Get details of the requested signal.\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n\
  \          type: string\n          description: Key Manager authentication token.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the signal to display.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-signals-create\n      path: /v1/signals/create\n      operations:\n      - name: post-v1-signals-create\n        method: POST\n        description: Create a signal.\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-signals-id-update\n\
  \      path: /v1/signals/{id}/update\n      operations:\n      - name: post-v1-signals-id-update\n        method: POST\n        description: Update a signal.\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The id of the signal.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-signals-id-delete\n      path: /v1/signals/{id}/delete\n      operations:\n      - name: post-v1-signals-id-delete\n        method: POST\n        description: Delete a signal.\n        inputParameters:\n        - name: sessionToken\n          in:\
  \ header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The id of the signal.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-signals-id-subscribe\n      path: /v1/signals/{id}/subscribe\n      operations:\n      - name: post-v1-signals-id-subscribe\n        method: POST\n        description: Subscribe to a Signal.\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description:\
  \ Key Manager authentication token.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The id of the signal.\n        - name: pushed\n          in: query\n          type: boolean\n          description: Prevent the user to unsubscribe (only for bulk subscription)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-signals-id-unsubscribe\n      path: /v1/signals/{id}/unsubscribe\n      operations:\n      - name: post-v1-signals-id-unsubscribe\n        method: POST\n        description: Unsubscribe to a Signal.\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name:\
  \ id\n          in: path\n          type: string\n          required: true\n          description: The id of the signal.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-signals-id-subscribers\n      path: /v1/signals/{id}/subscribers\n      operations:\n      - name: get-v1-signals-id-subscribers\n        method: GET\n        description: Get the subscribers of a signal\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The id of the signal.\n        - name: skip\n          in: query\n          type: integer\n       \
  \   description: No. of results to skip.\n        - name: limit\n          in: query\n          type: integer\n          description: Max No. of subscribers to return. If no value is provided, 100 is the default.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-info\n      path: /v1/info\n      operations:\n      - name: get-v1-info\n        method: GET\n        description: Get information about the Agent\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-dlp-policies\n      path: /v1/dlp/policies\n      operations:\n      - name: get-v1-dlp-policies\n        method: GET\n        description: Get all policies\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name:\
  \ keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: page\n          in: query\n          type: integer\n          description: Optional parameter to specify which page to return (default is 0)\n        - name: limit\n          in: query\n          type: integer\n          description: Optional parameter to specify the number of result to return per page, default is 50. Maximum is 50.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-v1-dlp-policies\n        method: POST\n        description: Creates a policy\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication\
  \ token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-dlp-policies-policyid\n      path: /v1/dlp/policies/{policyId}\n      operations:\n      - name: get-v1-dlp-policies-policyid\n        method: GET\n        description: Get a policy\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: policyId\n          in: path\n          type: string\n          required: true\n          description: Unique dictionary identifier.\n        - name: policyVersion\n          in: query\n          type: string\n          description: Optional parameter, if set to be valid policy version number, will return policy with specified policyVersion.\n\
  \            Otherwise, return the latest policy.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-v1-dlp-policies-policyid\n        method: PUT\n        description: Updates a policy. Cannot be used for creation.\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: policyId\n          in: path\n          type: string\n          required: true\n          description: Unique dictionary identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-v1-dlp-policies-policyid\n        method: DELETE\n        description:\
  \ Delete a policy\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: policyId\n          in: path\n          type: string\n          required: true\n          description: Unique dictionary identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-dlp-policies-policyid-enable\n      path: /v1/dlp/policies/{policyId}/enable\n      operations:\n      - name: post-v1-dlp-policies-policyid-enable\n        method: POST\n        description: Enables a policy.\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session\
  \ authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: policyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-dlp-policies-policyid-disable\n      path: /v1/dlp/policies/{policyId}/disable\n      operations:\n      - name: post-v1-dlp-policies-policyid-disable\n        method: POST\n        description: Disables a policy.\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: policyId\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-dlp-dictionaries\n      path: /v1/dlp/dictionaries\n      operations:\n      - name: get-v1-dlp-dictionaries\n        method: GET\n        description: Get all dictionary metadatas\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: page\n          in: query\n          type: integer\n          description: Optional parameter to specify which page to return (default is 0)\n        - name: limit\n          in: query\n          type: integer\n          description: Optional parameter to specify the number of result to return per page, default is\
  \ 50. Maximum is 50.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-v1-dlp-dictionaries\n        method: POST\n        description: Create a dictionary\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-dlp-dictionaries-dictid\n      path: /v1/dlp/dictionaries/{dictId}\n      operations:\n      - name: get-v1-dlp-dictionaries-dictid\n        method: GET\n        description: Get dictionary metadata\n        inputParameters:\n        - name: sessionToken\n          in: header\n       \
  \   type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: dictId\n          in: path\n          type: string\n          required: true\n          description: Unique dictionary identifier\n        - name: dictVersion\n          in: query\n          type: string\n          description: If set to be valid dictionary version number, will return dictionary metadata with specified version.\n            Otherwise, return the latest dictionary metadata.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-v1-dlp-dictionaries-dictid\n        method: PUT\n        description: Updates a dictionary\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required:\
  \ true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: dictId\n          in: path\n          type: string\n          required: true\n          description: Unique dictionary identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-v1-dlp-dictionaries-dictid\n        method: DELETE\n        description: Delete a dictionary\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: dictId\n          in: path\n          type: string\n          required: true\n\
  \          description: Unique dictionary identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-dlp-dictionaries-dictid-data-download\n      path: /v1/dlp/dictionaries/{dictId}/data/download\n      operations:\n      - name: get-v1-dlp-dictionaries-dictid-data-download\n        method: GET\n        description: Downloads Base 64 encoded dictionary content.\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: dictId\n          in: path\n          type: string\n          required: true\n          description: Unique dictionary identifier\n        - name: dictVersion\n          in: query\n          type: string\n\
  \          description: If set to be valid dictionary version number, will return dictionary with specified version. Otherwise,\n            return the latest dictionary.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-dlp-dictionaries-dictid-data-upload\n      path: /v1/dlp/dictionaries/{dictId}/data/upload\n      operations:\n      - name: post-v1-dlp-dictionaries-dictid-data-upload\n        method: POST\n        description: Override dictionary content with provided content.\n        inputParameters:\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        - name: dictId\n          in: path\n          type: string\n          required: true\n       \
  \   description: Unique dictionary identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-dlp-violations-message\n      path: /v1/dlp/violations/message\n      operations:\n      - name: get-v1-dlp-violations-message\n        method: GET\n        description: Get violations as a result of policy enforcement on messages.\n        inputParameters:\n        - name: startTime\n          in: query\n          type: integer\n          required: true\n          description: Timestamp of the first required violation. This is a long integer value representing milliseconds since\n            Jan 1 1970\n        - name: endTime\n          in: query\n          type: integer\n          description: Timestamp of the last required violation. This is a long integer value representing milliseconds since\n            Jan 1 1970 If unspecified, it will default to current tim\n        - name: next\n         \
  \ in: query\n          type: string\n          description: Offset of the next chunk of violations. Value is null for the first request.\n        - name: limit\n          in: query\n          type: integer\n          description: Max No. of violations to return. If no value is provided, 50 is the default. The maximum supported\n            value is 500.\n        - name: sessionToken\n          in: header\n          type: string\n          required: true\n          description: Session authentication token.\n        - name: keyManagerToken\n          in: header\n          type: string\n          description: Key Manager authentication token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-dlp-violations-stream\n      path: /v1/dlp/violations/stream\n      operations:\n      - name: get-v1-dlp-violations-stream\n        method: GET\n        description: Get violations as a result of policy enforcement\
  \ on streams.\n        inputParameters:\n        - name: startTime\n          in: query\n          type: integer\n          required: true\n          description: Timestamp of the first required violation. This is a long integer value representing milliseconds since\n            Jan 1 1970\n        - name: endTime\n          in: query\n          type: integer\n          description: Timestamp of the last required violation. This is a long integer value representing milliseconds since\n            Jan 1 1970 If unspecified, it will default to current tim\n        - name: next\n          in: query\n          type: string\n          description: Offset of the next chunk of violations. Value is null for the first request.\n      \n\n# --- truncated at 32 KB (104 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/finos/refs/heads/main/capabilities/finos-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/finos/refs/heads/main/capabilities/finos-capability.yaml
tags:
- Finos
- API
tools:
- description: Checks health status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: v3health
- description: Checks health status of services and users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: v3extendedhealth
- description: Import messages from other systems into Symphony.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v4-message-import
- description: Post a message to multiple existing streams.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v4-message-blast
- description: Get a message by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-message-id
- description: Search messages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-message-search
- description: Search messages
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-message-search
- description: Download an attachment.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-stream-sid-attachment
- description: Get messages from an existing stream.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v4-stream-sid-message
- description: Post a message to one existing stream.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v4-stream-sid-message-create
- description: Update an existing message.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v4-stream-sid-message-mid-update
- description: PROVISIONAL - Share a piece of content into Symphony
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v3-stream-sid-share
- description: Test endpoint, returns input.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-util-echo
- description: List signals for the requesting user. This includes signals that the user has created and public signals to which they subscribed.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-signals-list
- description: Get details of the requested signal.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-signals-id-get
- description: Create a signal.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-signals-create
- description: Update a signal.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-signals-id-update
- description: Delete a signal.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-signals-id-delete
- description: Subscribe to a Signal.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-signals-id-subscribe
- description: Unsubscribe to a Signal.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-signals-id-unsubscribe
- description: Get the subscribers of a signal
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-signals-id-subscribers
- description: Get information about the Agent
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-info
- description: Get all policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-dlp-policies
- description: Creates a policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-dlp-policies
- description: Get a policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-dlp-policies-policyid
- description: Updates a policy. Cannot be used for creation.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-v1-dlp-policies-policyid
- description: Delete a policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-dlp-policies-policyid
- description: Enables a policy.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-dlp-policies-policyid-enable
- description: Disables a policy.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-dlp-policies-policyid-disable
- description: Get all dictionary metadatas
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-dlp-dictionaries
- description: Create a dictionary
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-dlp-dictionaries
- description: Get dictionary metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-dlp-dictionaries-dictid
- description: Updates a dictionary
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-v1-dlp-dictionaries-dictid
- description: Delete a dictionary
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-dlp-dictionaries-dictid
- description: Downloads Base 64 encoded dictionary content.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-dlp-dictionaries-dictid-data-download
- description: Override dictionary content with provided content.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-dlp-dictionaries-dictid-data-upload
- description: Get violations as a result of policy enforcement on messages.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-dlp-violations-message
- description: Get violations as a result of policy enforcement on streams.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-dlp-violations-stream
- description: Get violations as a result of policy enforcement on signals.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-dlp-violations-signal
- description: Get all policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v3-dlp-policies
- description: Creates a policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v3-dlp-policies
- description: Get a policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v3-dlp-policies-policyid
- description: Updates a policy. Cannot be used for creation.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v3-dlp-policies-policyid-update
- description: Delete a policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v3-dlp-policies-policyid-delete
- description: Enables a policy.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v3-dlp-policies-policyid-enable
- description: Disables a policy.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v3-dlp-policies-policyid-disable
- description: Get violations as a result of policy enforcement on messages.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v3-dlp-violations-message
- description: Get violations as a result of policy enforcement on streams.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v3-dlp-violations-stream
- description: Get violations as a result of policy enforcement on signals.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v3-dlp-violations-signal
- description: Get attachments that were sent as part of messages that were flagged by the DLP System.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v3-dlp-violation-attachment
- description: Get a list of actions performed by a privileged account acting as privileged user given a period of time.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-audittrail-privilegeduser
- description: Returns the list of active datafeeds of the user.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatafeed
- description: Create a new real time feed of messages and events.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdatafeed
- description: Delete the specified real time message / event stream ("datafeed").
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedatafeed
- description: Read the specified real time message / event stream ("datafeed").
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: readdatafeed
- description: Creates and Reads a real time feed of messages and events of your pod (Datahose)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: readevents
---
