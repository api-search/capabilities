---
categories: []
consumed_apis: []
description: The Cloud KMS API enables creating and managing cryptographic keys, key rings, and crypto key versions, and performing encrypt, decrypt, sign, and verify operations.
layout: capability
name: Google Cloud KMS API
operations:
- description: Google Cloud KMS List key rings
  method: GET
  name: listkeyrings
  path: /projects/{projectId}/locations/{location}/keyRings
- description: Google Cloud KMS Create a key ring
  method: POST
  name: createkeyring
  path: /projects/{projectId}/locations/{location}/keyRings
- description: Google Cloud KMS Get a key ring
  method: GET
  name: getkeyring
  path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}
- description: Google Cloud KMS List crypto keys
  method: GET
  name: listcryptokeys
  path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys
- description: Google Cloud KMS Create a crypto key
  method: POST
  name: createcryptokey
  path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys
- description: Google Cloud KMS Get a crypto key
  method: GET
  name: getcryptokey
  path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys/{cryptoKeyId}
- description: Google Cloud KMS Update a crypto key
  method: PATCH
  name: updatecryptokey
  path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys/{cryptoKeyId}
- description: Google Cloud KMS Encrypt data
  method: POST
  name: encrypt
  path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys/{cryptoKeyId}:encrypt
- description: Google Cloud KMS Decrypt data
  method: POST
  name: decrypt
  path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys/{cryptoKeyId}:decrypt
personas: []
provider_name: Google Cloud KMS
provider_slug: google-cloud-kms
search_terms:
- google cloud kms list crypto keys
- cryptography
- getkeyring
- key management
- encrypt
- google cloud kms create a crypto key
- encryption
- cloud
- google cloud kms create a key ring
- google
- security
- listkeyrings
- google cloud kms update a crypto key
- google cloud kms get a crypto key
- createkeyring
- decrypt
- google cloud kms encrypt data
- api
- google cloud kms list key rings
- updatecryptokey
- kms
- google cloud kms get a key ring
- listcryptokeys
- createcryptokey
- google cloud
- google cloud kms decrypt data
- getcryptokey
slug: google-cloud-kms-capability
source_filename: google-cloud-kms-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud KMS API\n  description: The Cloud KMS API enables creating and managing cryptographic keys, key rings, and crypto key versions, and\n    performing encrypt, decrypt, sign, and verify operations.\n  tags:\n  - Google\n  - Cloud\n  - Kms\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-kms\n    baseUri: https://cloudkms.googleapis.com/v1\n    description: Google Cloud KMS API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_KMS_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations-location-keyrings\n      path: /projects/{projectId}/locations/{location}/keyRings\n      operations:\n      - name: listkeyrings\n        method: GET\n        description: Google Cloud KMS List key rings\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n\
  \        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createkeyring\n        method: POST\n        description: Google Cloud KMS Create a key ring\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: keyRingId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-keyrings-k\n      path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}\n\
  \      operations:\n      - name: getkeyring\n        method: GET\n        description: Google Cloud KMS Get a key ring\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: keyRingId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-keyrings-k\n      path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys\n      operations:\n      - name: listcryptokeys\n        method: GET\n        description: Google Cloud KMS List crypto keys\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in:\
  \ path\n          type: string\n          required: true\n        - name: keyRingId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcryptokey\n        method: POST\n        description: Google Cloud KMS Create a crypto key\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: keyRingId\n          in: path\n          type: string\n          required: true\n        - name: cryptoKeyId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-keyrings-k\n\
  \      path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys/{cryptoKeyId}\n      operations:\n      - name: getcryptokey\n        method: GET\n        description: Google Cloud KMS Get a crypto key\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: keyRingId\n          in: path\n          type: string\n          required: true\n        - name: cryptoKeyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecryptokey\n        method: PATCH\n        description: Google Cloud KMS Update a crypto key\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n\
  \        - name: location\n          in: path\n          type: string\n          required: true\n        - name: keyRingId\n          in: path\n          type: string\n          required: true\n        - name: cryptoKeyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-keyrings-k\n      path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys/{cryptoKeyId}:encrypt\n      operations:\n      - name: encrypt\n        method: POST\n        description: Google Cloud KMS Encrypt data\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: keyRingId\n          in: path\n          type: string\n \
  \         required: true\n        - name: cryptoKeyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-keyrings-k\n      path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys/{cryptoKeyId}:decrypt\n      operations:\n      - name: decrypt\n        method: POST\n        description: Google Cloud KMS Decrypt data\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: keyRingId\n          in: path\n          type: string\n          required: true\n        - name: cryptoKeyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-kms-rest\n    description: REST adapter for Google Cloud KMS API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/keyRings\n      name: listkeyrings\n      operations:\n      - method: GET\n        name: listkeyrings\n        description: Google Cloud KMS List key rings\n        call: google-cloud-kms.listkeyrings\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/keyRings\n      name: createkeyring\n      operations:\n      - method: POST\n        name: createkeyring\n        description: Google Cloud KMS Create a key ring\n        call: google-cloud-kms.createkeyring\n        with:\n          projectId: rest.projectId\n          location: rest.location\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}\n      name: getkeyring\n      operations:\n      - method: GET\n        name: getkeyring\n        description: Google Cloud KMS Get a key ring\n        call: google-cloud-kms.getkeyring\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          keyRingId: rest.keyRingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys\n      name: listcryptokeys\n      operations:\n      - method: GET\n        name: listcryptokeys\n        description: Google Cloud KMS List crypto keys\n        call: google-cloud-kms.listcryptokeys\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          keyRingId: rest.keyRingId\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys\n      name: createcryptokey\n      operations:\n      - method: POST\n        name: createcryptokey\n        description: Google Cloud KMS Create a crypto key\n        call: google-cloud-kms.createcryptokey\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          keyRingId: rest.keyRingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys/{cryptoKeyId}\n      name: getcryptokey\n      operations:\n      - method: GET\n        name: getcryptokey\n        description: Google Cloud KMS Get a crypto key\n        call: google-cloud-kms.getcryptokey\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          keyRingId: rest.keyRingId\n          cryptoKeyId: rest.cryptoKeyId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys/{cryptoKeyId}\n      name: updatecryptokey\n      operations:\n      - method: PATCH\n        name: updatecryptokey\n        description: Google Cloud KMS Update a crypto key\n        call: google-cloud-kms.updatecryptokey\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          keyRingId: rest.keyRingId\n          cryptoKeyId: rest.cryptoKeyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys/{cryptoKeyId}:encrypt\n      name: encrypt\n      operations:\n      - method: POST\n        name: encrypt\n        description: Google Cloud KMS Encrypt data\n        call: google-cloud-kms.encrypt\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          keyRingId: rest.keyRingId\n\
  \          cryptoKeyId: rest.cryptoKeyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/keyRings/{keyRingId}/cryptoKeys/{cryptoKeyId}:decrypt\n      name: decrypt\n      operations:\n      - method: POST\n        name: decrypt\n        description: Google Cloud KMS Decrypt data\n        call: google-cloud-kms.decrypt\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          keyRingId: rest.keyRingId\n          cryptoKeyId: rest.cryptoKeyId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-kms-mcp\n    transport: http\n    description: MCP adapter for Google Cloud KMS API for AI agent use.\n    tools:\n    - name: listkeyrings\n      description: Google Cloud KMS List key rings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-kms.listkeyrings\n\
  \      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createkeyring\n      description: Google Cloud KMS Create a key ring\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-kms.createkeyring\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        keyRingId: tools.keyRingId\n      inputParameters:\n      - name: projectId\n    \
  \    type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: keyRingId\n        type: string\n        description: keyRingId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getkeyring\n      description: Google Cloud KMS Get a key ring\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-kms.getkeyring\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        keyRingId: tools.keyRingId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: keyRingId\n        type: string\n        description: keyRingId\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcryptokeys\n      description: Google Cloud KMS List crypto keys\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-kms.listcryptokeys\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        keyRingId: tools.keyRingId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: keyRingId\n        type: string\n        description: keyRingId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcryptokey\n      description: Google Cloud KMS Create a crypto key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ google-cloud-kms.createcryptokey\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        keyRingId: tools.keyRingId\n        cryptoKeyId: tools.cryptoKeyId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: keyRingId\n        type: string\n        description: keyRingId\n        required: true\n      - name: cryptoKeyId\n        type: string\n        description: cryptoKeyId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcryptokey\n      description: Google Cloud KMS Get a crypto key\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-kms.getcryptokey\n      with:\n        projectId: tools.projectId\n        location: tools.location\n\
  \        keyRingId: tools.keyRingId\n        cryptoKeyId: tools.cryptoKeyId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: keyRingId\n        type: string\n        description: keyRingId\n        required: true\n      - name: cryptoKeyId\n        type: string\n        description: cryptoKeyId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecryptokey\n      description: Google Cloud KMS Update a crypto key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-kms.updatecryptokey\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        keyRingId: tools.keyRingId\n        cryptoKeyId: tools.cryptoKeyId\n      inputParameters:\n      -\
  \ name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: keyRingId\n        type: string\n        description: keyRingId\n        required: true\n      - name: cryptoKeyId\n        type: string\n        description: cryptoKeyId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: encrypt\n      description: Google Cloud KMS Encrypt data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-kms.encrypt\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        keyRingId: tools.keyRingId\n        cryptoKeyId: tools.cryptoKeyId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type:\
  \ string\n        description: location\n        required: true\n      - name: keyRingId\n        type: string\n        description: keyRingId\n        required: true\n      - name: cryptoKeyId\n        type: string\n        description: cryptoKeyId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: decrypt\n      description: Google Cloud KMS Decrypt data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-kms.decrypt\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        keyRingId: tools.keyRingId\n        cryptoKeyId: tools.cryptoKeyId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: keyRingId\n        type: string\n        description:\
  \ keyRingId\n        required: true\n      - name: cryptoKeyId\n        type: string\n        description: cryptoKeyId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_KMS_TOKEN: GOOGLE_CLOUD_KMS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-kms/refs/heads/main/capabilities/google-cloud-kms-capability.yaml
tags:
- Google
- Cloud
- Kms
- API
tools:
- description: Google Cloud KMS List key rings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listkeyrings
- description: Google Cloud KMS Create a key ring
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createkeyring
- description: Google Cloud KMS Get a key ring
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getkeyring
- description: Google Cloud KMS List crypto keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcryptokeys
- description: Google Cloud KMS Create a crypto key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcryptokey
- description: Google Cloud KMS Get a crypto key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcryptokey
- description: Google Cloud KMS Update a crypto key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecryptokey
- description: Google Cloud KMS Encrypt data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: encrypt
- description: Google Cloud KMS Decrypt data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: decrypt
---
