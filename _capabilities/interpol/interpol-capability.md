---
categories: []
consumed_apis: []
description: Interpol Red, Yellow and UN Notices API
layout: capability
name: Interpol Notices API
operations:
- description: Get Red Notices
  method: GET
  name: get-notices-v1-red
  path: /notices/v1/red
- description: Get Red Notice Details
  method: GET
  name: get-notices-v1-red-noticeid
  path: /notices/v1/red/{noticeID}
- description: Get Red Notice Images
  method: GET
  name: get-notices-v1-red-noticeid-images
  path: /notices/v1/red/{noticeID}/images
- description: Get Yellow Notices
  method: GET
  name: get-notices-v1-yellow
  path: /notices/v1/yellow
- description: Get Yellow Notice Details
  method: GET
  name: get-notices-v1-yellow-noticeid
  path: /notices/v1/yellow/{noticeID}
- description: Get Yellow Notice Images
  method: GET
  name: get-notices-v1-yellow-noticeid-images
  path: /notices/v1/yellow/{noticeID}/images
- description: Get UN Notices
  method: GET
  name: get-notices-v1-un
  path: /notices/v1/un
- description: Get UN Notice Details
  method: GET
  name: get-notices-v1-un-noticetype-noticeid
  path: /notices/v1/un/{noticeType}/{noticeID}
- description: Get UN Notice Images
  method: GET
  name: get-notices-v1-un-noticetype-noticeid-images
  path: /notices/v1/un/{noticeType}/{noticeID}/images
personas: []
provider_name: Interpol
provider_slug: interpol
search_terms:
- get notices v1 un noticetype noticeid
- get un notice images
- notices
- get red notices
- api
- interpol
- get red notice images
- get notices v1 yellow noticeid images
- get yellow notice images
- get notices v1 un noticetype noticeid images
- international
- get notices v1 red noticeid images
- law enforcement
- get notices v1 red noticeid
- get un notices
- get yellow notice details
- get notices v1 red
- get notices v1 yellow
- get red notice details
- get un notice details
- get notices v1 yellow noticeid
- police
- federal government
- get yellow notices
- get notices v1 un
slug: interpol-capability
source_filename: interpol-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Interpol Notices API\n  description: Interpol Red, Yellow and UN Notices API\n  tags:\n  - Interpol\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: interpol\n    baseUri: https://ws-public.interpol.int\n    description: Interpol Notices API HTTP API.\n    resources:\n    - name: notices-v1-red\n      path: /notices/v1/red\n      operations:\n      - name: get-notices-v1-red\n        method: GET\n        description: Get Red Notices\n        inputParameters:\n        - name: forename\n          in: query\n          type: string\n          description: First name\n        - name: name\n          in: query\n          type: string\n          description: Last name\n        - name: nationality\n          in: query\n          type: string\n          description: Two digit country code\n        - name: ageMax\n          in: query\n          type: integer\n          description:\
  \ maximum age\n        - name: ageMin\n          in: query\n          type: integer\n          description: minimum age\n        - name: freeText\n          in: query\n          type: string\n          description: Free text query\n        - name: sexId\n          in: query\n          type: string\n          description: Free text query\n        - name: arrestWarrantCountryId\n          in: query\n          type: string\n          description: Two digit country code\n        - name: page\n          in: query\n          type: integer\n          description: pagination - starts with 1\n        - name: resultPerPage\n          in: query\n          type: integer\n          description: resultPerPage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notices-v1-red-noticeid\n      path: /notices/v1/red/{noticeID}\n      operations:\n      - name: get-notices-v1-red-noticeid\n        method: GET\n      \
  \  description: Get Red Notice Details\n        inputParameters:\n        - name: noticeID\n          in: path\n          type: string\n          required: true\n          description: Notice ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notices-v1-red-noticeid-images\n      path: /notices/v1/red/{noticeID}/images\n      operations:\n      - name: get-notices-v1-red-noticeid-images\n        method: GET\n        description: Get Red Notice Images\n        inputParameters:\n        - name: noticeID\n          in: path\n          type: string\n          required: true\n          description: Notice ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notices-v1-yellow\n      path: /notices/v1/yellow\n      operations:\n      - name: get-notices-v1-yellow\n        method: GET\n        description: Get Yellow\
  \ Notices\n        inputParameters:\n        - name: forename\n          in: query\n          type: string\n          description: First name\n        - name: name\n          in: query\n          type: string\n          description: Last name\n        - name: nationality\n          in: query\n          type: string\n          description: Two digit country code\n        - name: ageMax\n          in: query\n          type: integer\n          description: maximum age\n        - name: ageMin\n          in: query\n          type: integer\n          description: minimum age\n        - name: freeText\n          in: query\n          type: string\n          description: Free text query\n        - name: sexId\n          in: query\n          type: string\n          description: Free text query\n        - name: page\n          in: query\n          type: integer\n          description: pagination - starts with 1\n        - name: resultPerPage\n          in: query\n          type: integer\n       \
  \   description: resultPerPage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notices-v1-yellow-noticeid\n      path: /notices/v1/yellow/{noticeID}\n      operations:\n      - name: get-notices-v1-yellow-noticeid\n        method: GET\n        description: Get Yellow Notice Details\n        inputParameters:\n        - name: noticeID\n          in: path\n          type: string\n          required: true\n          description: Notice ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notices-v1-yellow-noticeid-images\n      path: /notices/v1/yellow/{noticeID}/images\n      operations:\n      - name: get-notices-v1-yellow-noticeid-images\n        method: GET\n        description: Get Yellow Notice Images\n        inputParameters:\n        - name: noticeID\n          in: path\n          type: string\n       \
  \   required: true\n          description: Notice ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notices-v1-un\n      path: /notices/v1/un\n      operations:\n      - name: get-notices-v1-un\n        method: GET\n        description: Get UN Notices\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Last name\n        - name: unReference\n          in: query\n          type: string\n          description: UN-Referenz\n        - name: unResolution\n          in: query\n          type: integer\n          description: UN-Resolution\n        - name: page\n          in: query\n          type: integer\n          description: pagination - starts with 1\n        - name: resultPerPage\n          in: query\n          type: integer\n          description: resultPerPage\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: notices-v1-un-noticetype-noticeid\n      path: /notices/v1/un/{noticeType}/{noticeID}\n      operations:\n      - name: get-notices-v1-un-noticetype-noticeid\n        method: GET\n        description: Get UN Notice Details\n        inputParameters:\n        - name: noticeID\n          in: path\n          type: string\n          required: true\n          description: Notice ID\n        - name: noticeType\n          in: path\n          type: string\n          required: true\n          description: Notice Type (either 'persons' or 'entities')\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notices-v1-un-noticetype-noticeid-images\n      path: /notices/v1/un/{noticeType}/{noticeID}/images\n      operations:\n      - name: get-notices-v1-un-noticetype-noticeid-images\n        method: GET\n        description: Get UN Notice Images\n  \
  \      inputParameters:\n        - name: noticeID\n          in: path\n          type: string\n          required: true\n          description: Notice ID\n        - name: noticeType\n          in: path\n          type: string\n          required: true\n          description: Notice Type (either 'persons' or 'entities')\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: interpol-rest\n    description: REST adapter for Interpol Notices API.\n    resources:\n    - path: /notices/v1/red\n      name: get-notices-v1-red\n      operations:\n      - method: GET\n        name: get-notices-v1-red\n        description: Get Red Notices\n        call: interpol.get-notices-v1-red\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /notices/v1/red/{noticeID}\n      name: get-notices-v1-red-noticeid\n      operations:\n      - method:\
  \ GET\n        name: get-notices-v1-red-noticeid\n        description: Get Red Notice Details\n        call: interpol.get-notices-v1-red-noticeid\n        with:\n          noticeID: rest.noticeID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /notices/v1/red/{noticeID}/images\n      name: get-notices-v1-red-noticeid-images\n      operations:\n      - method: GET\n        name: get-notices-v1-red-noticeid-images\n        description: Get Red Notice Images\n        call: interpol.get-notices-v1-red-noticeid-images\n        with:\n          noticeID: rest.noticeID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /notices/v1/yellow\n      name: get-notices-v1-yellow\n      operations:\n      - method: GET\n        name: get-notices-v1-yellow\n        description: Get Yellow Notices\n        call: interpol.get-notices-v1-yellow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /notices/v1/yellow/{noticeID}\n      name: get-notices-v1-yellow-noticeid\n      operations:\n      - method: GET\n        name: get-notices-v1-yellow-noticeid\n        description: Get Yellow Notice Details\n        call: interpol.get-notices-v1-yellow-noticeid\n        with:\n          noticeID: rest.noticeID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /notices/v1/yellow/{noticeID}/images\n      name: get-notices-v1-yellow-noticeid-images\n      operations:\n      - method: GET\n        name: get-notices-v1-yellow-noticeid-images\n        description: Get Yellow Notice Images\n        call: interpol.get-notices-v1-yellow-noticeid-images\n        with:\n          noticeID: rest.noticeID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /notices/v1/un\n      name: get-notices-v1-un\n      operations:\n      - method: GET\n        name: get-notices-v1-un\n        description: Get UN Notices\n        call:\
  \ interpol.get-notices-v1-un\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /notices/v1/un/{noticeType}/{noticeID}\n      name: get-notices-v1-un-noticetype-noticeid\n      operations:\n      - method: GET\n        name: get-notices-v1-un-noticetype-noticeid\n        description: Get UN Notice Details\n        call: interpol.get-notices-v1-un-noticetype-noticeid\n        with:\n          noticeID: rest.noticeID\n          noticeType: rest.noticeType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /notices/v1/un/{noticeType}/{noticeID}/images\n      name: get-notices-v1-un-noticetype-noticeid-images\n      operations:\n      - method: GET\n        name: get-notices-v1-un-noticetype-noticeid-images\n        description: Get UN Notice Images\n        call: interpol.get-notices-v1-un-noticetype-noticeid-images\n        with:\n          noticeID: rest.noticeID\n          noticeType: rest.noticeType\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: interpol-mcp\n    transport: http\n    description: MCP adapter for Interpol Notices API for AI agent use.\n    tools:\n    - name: get-notices-v1-red\n      description: Get Red Notices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: interpol.get-notices-v1-red\n      with:\n        forename: tools.forename\n        name: tools.name\n        nationality: tools.nationality\n        ageMax: tools.ageMax\n        ageMin: tools.ageMin\n        freeText: tools.freeText\n        sexId: tools.sexId\n        arrestWarrantCountryId: tools.arrestWarrantCountryId\n        page: tools.page\n        resultPerPage: tools.resultPerPage\n      inputParameters:\n      - name: forename\n        type: string\n        description: First name\n      - name: name\n        type: string\n        description: Last name\n      - name: nationality\n        type:\
  \ string\n        description: Two digit country code\n      - name: ageMax\n        type: integer\n        description: maximum age\n      - name: ageMin\n        type: integer\n        description: minimum age\n      - name: freeText\n        type: string\n        description: Free text query\n      - name: sexId\n        type: string\n        description: Free text query\n      - name: arrestWarrantCountryId\n        type: string\n        description: Two digit country code\n      - name: page\n        type: integer\n        description: pagination - starts with 1\n      - name: resultPerPage\n        type: integer\n        description: resultPerPage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-notices-v1-red-noticeid\n      description: Get Red Notice Details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: interpol.get-notices-v1-red-noticeid\n      with:\n        noticeID: tools.noticeID\n\
  \      inputParameters:\n      - name: noticeID\n        type: string\n        description: Notice ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-notices-v1-red-noticeid-images\n      description: Get Red Notice Images\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: interpol.get-notices-v1-red-noticeid-images\n      with:\n        noticeID: tools.noticeID\n      inputParameters:\n      - name: noticeID\n        type: string\n        description: Notice ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-notices-v1-yellow\n      description: Get Yellow Notices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: interpol.get-notices-v1-yellow\n      with:\n        forename: tools.forename\n        name: tools.name\n        nationality: tools.nationality\n \
  \       ageMax: tools.ageMax\n        ageMin: tools.ageMin\n        freeText: tools.freeText\n        sexId: tools.sexId\n        page: tools.page\n        resultPerPage: tools.resultPerPage\n      inputParameters:\n      - name: forename\n        type: string\n        description: First name\n      - name: name\n        type: string\n        description: Last name\n      - name: nationality\n        type: string\n        description: Two digit country code\n      - name: ageMax\n        type: integer\n        description: maximum age\n      - name: ageMin\n        type: integer\n        description: minimum age\n      - name: freeText\n        type: string\n        description: Free text query\n      - name: sexId\n        type: string\n        description: Free text query\n      - name: page\n        type: integer\n        description: pagination - starts with 1\n      - name: resultPerPage\n        type: integer\n        description: resultPerPage\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-notices-v1-yellow-noticeid\n      description: Get Yellow Notice Details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: interpol.get-notices-v1-yellow-noticeid\n      with:\n        noticeID: tools.noticeID\n      inputParameters:\n      - name: noticeID\n        type: string\n        description: Notice ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-notices-v1-yellow-noticeid-images\n      description: Get Yellow Notice Images\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: interpol.get-notices-v1-yellow-noticeid-images\n      with:\n        noticeID: tools.noticeID\n      inputParameters:\n      - name: noticeID\n        type: string\n        description: Notice ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: get-notices-v1-un\n      description: Get UN Notices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: interpol.get-notices-v1-un\n      with:\n        name: tools.name\n        unReference: tools.unReference\n        unResolution: tools.unResolution\n        page: tools.page\n        resultPerPage: tools.resultPerPage\n      inputParameters:\n      - name: name\n        type: string\n        description: Last name\n      - name: unReference\n        type: string\n        description: UN-Referenz\n      - name: unResolution\n        type: integer\n        description: UN-Resolution\n      - name: page\n        type: integer\n        description: pagination - starts with 1\n      - name: resultPerPage\n        type: integer\n        description: resultPerPage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-notices-v1-un-noticetype-noticeid\n      description: Get UN Notice Details\n   \
  \   hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: interpol.get-notices-v1-un-noticetype-noticeid\n      with:\n        noticeID: tools.noticeID\n        noticeType: tools.noticeType\n      inputParameters:\n      - name: noticeID\n        type: string\n        description: Notice ID\n        required: true\n      - name: noticeType\n        type: string\n        description: Notice Type (either 'persons' or 'entities')\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-notices-v1-un-noticetype-noticeid-images\n      description: Get UN Notice Images\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: interpol.get-notices-v1-un-noticetype-noticeid-images\n      with:\n        noticeID: tools.noticeID\n        noticeType: tools.noticeType\n      inputParameters:\n      - name: noticeID\n        type: string\n        description:\
  \ Notice ID\n        required: true\n      - name: noticeType\n        type: string\n        description: Notice Type (either 'persons' or 'entities')\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/interpol/refs/heads/main/capabilities/interpol-capability.yaml
tags:
- Interpol
- API
tools:
- description: Get Red Notices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-notices-v1-red
- description: Get Red Notice Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-notices-v1-red-noticeid
- description: Get Red Notice Images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-notices-v1-red-noticeid-images
- description: Get Yellow Notices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-notices-v1-yellow
- description: Get Yellow Notice Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-notices-v1-yellow-noticeid
- description: Get Yellow Notice Images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-notices-v1-yellow-noticeid-images
- description: Get UN Notices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-notices-v1-un
- description: Get UN Notice Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-notices-v1-un-noticetype-noticeid
- description: Get UN Notice Images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-notices-v1-un-noticetype-noticeid-images
---
