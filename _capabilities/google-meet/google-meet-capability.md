---
categories: []
consumed_apis: []
description: The Google Meet REST API enables creating and managing meeting spaces, retrieving conference records with participant and session details, and accessing meeting recordings and transcripts.
layout: capability
name: Google Meet API
operations:
- description: Google Meet Create meeting space
  method: POST
  name: createspace
  path: /v2/spaces
- description: Google Meet Get meeting space
  method: GET
  name: getspace
  path: /v2/{name}
- description: Google Meet Update meeting space
  method: PATCH
  name: updatespace
  path: /v2/{name}
- description: Google Meet End active conference
  method: POST
  name: endactiveconference
  path: /v2/{name}:endActiveConference
- description: Google Meet List conference records
  method: GET
  name: listconferencerecords
  path: /v2/conferenceRecords
- description: Google Meet Get conference record
  method: GET
  name: getconferencerecord
  path: /v2/conferenceRecords/{conferenceRecordId}
- description: Google Meet List participants
  method: GET
  name: listparticipants
  path: /v2/conferenceRecords/{conferenceRecordId}/participants
- description: Google Meet Get participant
  method: GET
  name: getparticipant
  path: /v2/conferenceRecords/{conferenceRecordId}/participants/{participantId}
- description: Google Meet List recordings
  method: GET
  name: listrecordings
  path: /v2/conferenceRecords/{conferenceRecordId}/recordings
- description: Google Meet List transcripts
  method: GET
  name: listtranscripts
  path: /v2/conferenceRecords/{conferenceRecordId}/transcripts
- description: Google Meet List transcript entries
  method: GET
  name: listtranscriptentries
  path: /v2/conferenceRecords/{conferenceRecordId}/transcripts/{transcriptId}/entries
personas: []
provider_name: Google Meet
provider_slug: google-meet
search_terms:
- meetings
- meet
- google meet list recordings
- google workspace
- getparticipant
- listtranscriptentries
- listconferencerecords
- google
- google meet list conference records
- listparticipants
- updatespace
- google meet list transcript entries
- getconferencerecord
- recordings
- google meet get participant
- endactiveconference
- api
- google meet end active conference
- getspace
- transcripts
- video conferencing
- google meet get conference record
- google meet create meeting space
- listrecordings
- google meet update meeting space
- listtranscripts
- google meet list participants
- google meet list transcripts
- google meet get meeting space
- createspace
slug: google-meet-capability
source_filename: google-meet-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Meet API\n  description: The Google Meet REST API enables creating and managing meeting spaces, retrieving conference records with participant\n    and session details, and accessing meeting recordings and transcripts.\n  tags:\n  - Google\n  - Meet\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-meet\n    baseUri: https://meet.googleapis.com\n    description: Google Meet API HTTP API.\n    resources:\n    - name: v2-spaces\n      path: /v2/spaces\n      operations:\n      - name: createspace\n        method: POST\n        description: Google Meet Create meeting space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-name\n      path: /v2/{name}\n      operations:\n      - name: getspace\n        method: GET\n        description: Google Meet Get meeting space\n\
  \        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: 'Format: spaces/{space}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatespace\n        method: PATCH\n        description: Google Meet Update meeting space\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: 'Format: spaces/{space}'\n        - name: updateMask\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-name-endactiveconference\n      path: /v2/{name}:endActiveConference\n      operations:\n      - name: endactiveconference\n        method: POST\n        description: Google Meet End active conference\n        inputParameters:\n\
  \        - name: name\n          in: path\n          type: string\n          required: true\n          description: 'Format: spaces/{space}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-conferencerecords\n      path: /v2/conferenceRecords\n      operations:\n      - name: listconferencerecords\n        method: GET\n        description: Google Meet List conference records\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-conferencerecords-conferencerecordid\n      path: /v2/conferenceRecords/{conferenceRecordId}\n      operations:\n      - name: getconferencerecord\n\
  \        method: GET\n        description: Google Meet Get conference record\n        inputParameters:\n        - name: conferenceRecordId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-conferencerecords-conferencerecordid-particip\n      path: /v2/conferenceRecords/{conferenceRecordId}/participants\n      operations:\n      - name: listparticipants\n        method: GET\n        description: Google Meet List participants\n        inputParameters:\n        - name: conferenceRecordId\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: v2-conferencerecords-conferencerecordid-particip\n      path: /v2/conferenceRecords/{conferenceRecordId}/participants/{participantId}\n      operations:\n      - name: getparticipant\n        method: GET\n        description: Google Meet Get participant\n        inputParameters:\n        - name: conferenceRecordId\n          in: path\n          type: string\n          required: true\n        - name: participantId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-conferencerecords-conferencerecordid-recordin\n      path: /v2/conferenceRecords/{conferenceRecordId}/recordings\n      operations:\n      - name: listrecordings\n        method: GET\n        description: Google Meet List recordings\n        inputParameters:\n        - name: conferenceRecordId\n          in: path\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-conferencerecords-conferencerecordid-transcri\n      path: /v2/conferenceRecords/{conferenceRecordId}/transcripts\n      operations:\n      - name: listtranscripts\n        method: GET\n        description: Google Meet List transcripts\n        inputParameters:\n        - name: conferenceRecordId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-conferencerecords-conferencerecordid-transcri\n      path: /v2/conferenceRecords/{conferenceRecordId}/transcripts/{transcriptId}/entries\n      operations:\n      - name: listtranscriptentries\n        method: GET\n        description: Google Meet List transcript entries\n        inputParameters:\n        - name: conferenceRecordId\n          in:\
  \ path\n          type: string\n          required: true\n        - name: transcriptId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-meet-rest\n    description: REST adapter for Google Meet API.\n    resources:\n    - path: /v2/spaces\n      name: createspace\n      operations:\n      - method: POST\n        name: createspace\n        description: Google Meet Create meeting space\n        call: google-meet.createspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}\n      name: getspace\n      operations:\n      - method: GET\n        name: getspace\n        description: Google Meet Get meeting space\n        call: google-meet.getspace\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v2/{name}\n      name: updatespace\n      operations:\n      - method: PATCH\n        name: updatespace\n        description: Google Meet Update meeting space\n        call: google-meet.updatespace\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}:endActiveConference\n      name: endactiveconference\n      operations:\n      - method: POST\n        name: endactiveconference\n        description: Google Meet End active conference\n        call: google-meet.endactiveconference\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/conferenceRecords\n      name: listconferencerecords\n      operations:\n      - method: GET\n        name: listconferencerecords\n        description: Google Meet List conference records\n        call: google-meet.listconferencerecords\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v2/conferenceRecords/{conferenceRecordId}\n      name: getconferencerecord\n      operations:\n      - method: GET\n        name: getconferencerecord\n        description: Google Meet Get conference record\n        call: google-meet.getconferencerecord\n        with:\n          conferenceRecordId: rest.conferenceRecordId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/conferenceRecords/{conferenceRecordId}/participants\n      name: listparticipants\n      operations:\n      - method: GET\n        name: listparticipants\n        description: Google Meet List participants\n        call: google-meet.listparticipants\n        with:\n          conferenceRecordId: rest.conferenceRecordId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/conferenceRecords/{conferenceRecordId}/participants/{participantId}\n      name: getparticipant\n      operations:\n\
  \      - method: GET\n        name: getparticipant\n        description: Google Meet Get participant\n        call: google-meet.getparticipant\n        with:\n          conferenceRecordId: rest.conferenceRecordId\n          participantId: rest.participantId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/conferenceRecords/{conferenceRecordId}/recordings\n      name: listrecordings\n      operations:\n      - method: GET\n        name: listrecordings\n        description: Google Meet List recordings\n        call: google-meet.listrecordings\n        with:\n          conferenceRecordId: rest.conferenceRecordId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/conferenceRecords/{conferenceRecordId}/transcripts\n      name: listtranscripts\n      operations:\n      - method: GET\n        name: listtranscripts\n        description: Google Meet List transcripts\n        call: google-meet.listtranscripts\n   \
  \     with:\n          conferenceRecordId: rest.conferenceRecordId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/conferenceRecords/{conferenceRecordId}/transcripts/{transcriptId}/entries\n      name: listtranscriptentries\n      operations:\n      - method: GET\n        name: listtranscriptentries\n        description: Google Meet List transcript entries\n        call: google-meet.listtranscriptentries\n        with:\n          conferenceRecordId: rest.conferenceRecordId\n          transcriptId: rest.transcriptId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-meet-mcp\n    transport: http\n    description: MCP adapter for Google Meet API for AI agent use.\n    tools:\n    - name: createspace\n      description: Google Meet Create meeting space\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-meet.createspace\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getspace\n      description: Google Meet Get meeting space\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-meet.getspace\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: 'Format: spaces/{space}'\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatespace\n      description: Google Meet Update meeting space\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-meet.updatespace\n      with:\n        name: tools.name\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: name\n        type: string\n        description: 'Format: spaces/{space}'\n        required: true\n      - name: updateMask\n        type: string\n        description:\
  \ updateMask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: endactiveconference\n      description: Google Meet End active conference\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-meet.endactiveconference\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: 'Format: spaces/{space}'\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listconferencerecords\n      description: Google Meet List conference records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-meet.listconferencerecords\n      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        filter: tools.filter\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: pageSize\n  \
  \    - name: pageToken\n        type: string\n        description: pageToken\n      - name: filter\n        type: string\n        description: filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconferencerecord\n      description: Google Meet Get conference record\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-meet.getconferencerecord\n      with:\n        conferenceRecordId: tools.conferenceRecordId\n      inputParameters:\n      - name: conferenceRecordId\n        type: string\n        description: conferenceRecordId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listparticipants\n      description: Google Meet List participants\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-meet.listparticipants\n      with:\n        conferenceRecordId: tools.conferenceRecordId\n\
  \        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: conferenceRecordId\n        type: string\n        description: conferenceRecordId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getparticipant\n      description: Google Meet Get participant\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-meet.getparticipant\n      with:\n        conferenceRecordId: tools.conferenceRecordId\n        participantId: tools.participantId\n      inputParameters:\n      - name: conferenceRecordId\n        type: string\n        description: conferenceRecordId\n        required: true\n      - name: participantId\n        type: string\n        description: participantId\n       \
  \ required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrecordings\n      description: Google Meet List recordings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-meet.listrecordings\n      with:\n        conferenceRecordId: tools.conferenceRecordId\n      inputParameters:\n      - name: conferenceRecordId\n        type: string\n        description: conferenceRecordId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtranscripts\n      description: Google Meet List transcripts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-meet.listtranscripts\n      with:\n        conferenceRecordId: tools.conferenceRecordId\n      inputParameters:\n      - name: conferenceRecordId\n        type: string\n        description: conferenceRecordId\n        required: true\n  \
  \    outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtranscriptentries\n      description: Google Meet List transcript entries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-meet.listtranscriptentries\n      with:\n        conferenceRecordId: tools.conferenceRecordId\n        transcriptId: tools.transcriptId\n      inputParameters:\n      - name: conferenceRecordId\n        type: string\n        description: conferenceRecordId\n        required: true\n      - name: transcriptId\n        type: string\n        description: transcriptId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-meet/refs/heads/main/capabilities/google-meet-capability.yaml
tags:
- Google
- Meet
- API
tools:
- description: Google Meet Create meeting space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createspace
- description: Google Meet Get meeting space
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getspace
- description: Google Meet Update meeting space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatespace
- description: Google Meet End active conference
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: endactiveconference
- description: Google Meet List conference records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconferencerecords
- description: Google Meet Get conference record
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconferencerecord
- description: Google Meet List participants
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listparticipants
- description: Google Meet Get participant
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getparticipant
- description: Google Meet List recordings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrecordings
- description: Google Meet List transcripts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtranscripts
- description: Google Meet List transcript entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtranscriptentries
---
