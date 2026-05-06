---
categories: []
consumed_apis: []
description: Unified workflow capability for Amazon KMS combining resource management and operations.
layout: capability
name: Amazon KMS Workflow
operations: []
personas: []
provider_name: Amazon KMS
provider_slug: amazon-kms
search_terms:
- Administrator
- aws
- keys list keys
- cryptography
- workflow
- key management
- Developer
- gets a list of all kms keys in the caller's aws account and region.
- crypto encrypt
- returns a unique symmetric data key for use outside of kms.
- data protection
- creates a unique customer managed kms key in your aws account and region.
- decrypts ciphertext that was encrypted by a kms key.
- integrates api into applications
- encryption
- crypto decrypt
- security
- crypto generate data key
- keys create key
- manages resources and configurations
- amazon kms
- unified workflow for amazon kms resource management
- encrypts plaintext of up to 4,096 bytes using a kms key.
- keys describe key
- provides detailed information about a kms key.
slug: amazon-kms-workflow
source_filename: amazon-kms-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon KMS Workflow\n  description: Unified workflow capability for Amazon KMS combining resource management and operations.\n  tags:\n  - Amazon KMS\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: kms\n    baseUri: https://kms.us-east-1.amazonaws.com\n    description: Amazon KMS service.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: keys\n      path: /keys\n      description: KMS cryptographic key management\n      operations:\n      - name: createkey\n        method: POST\n        description: Creates a unique customer managed KMS key in your AWS account and Region.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: listkeys\n        method: GET\n        description: Gets a list of all KMS keys in the caller's AWS account and Region.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describekey\n        method: GET\n        description: Provides detailed information about a KMS key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crypto\n      path: /keys/{KeyId}\n      description: Encryption, decryption, and signing operations\n      operations:\n      - name: encrypt\n        method: POST\n        description: Encrypts plaintext of up to 4,096 bytes using a KMS key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: decrypt\n        method: POST\n\
  \        description: Decrypts ciphertext that was encrypted by a KMS key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: generatedatakey\n        method: POST\n        description: Returns a unique symmetric data key for use outside of KMS.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: kms-api\n    description: REST API for Amazon KMS workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: kms-mcp\n    transport: http\n    description: MCP server for Amazon KMS.\n    tools:\n    - name: keys-create-key\n      description: Creates a unique customer managed KMS key in your AWS account and Region.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: kms.createkey\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: keys-list-keys\n      description: Gets a list of all KMS keys in the caller's AWS account and Region.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kms.listkeys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: keys-describe-key\n      description: Provides detailed information about a KMS key.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kms.describekey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: crypto-encrypt\n      description: Encrypts plaintext of up to 4,096 bytes using a KMS key.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: kms.encrypt\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: crypto-decrypt\n      description: Decrypts ciphertext that was encrypted by a KMS key.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: kms.decrypt\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: crypto-generate-data-key\n      description: Returns a unique symmetric data key for use outside of KMS.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: kms.generatedatakey\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-kms/refs/heads/main/capabilities/amazon-kms-workflow.yaml
tags:
- Amazon KMS
- Workflow
tools:
- description: Creates a unique customer managed KMS key in your AWS account and Region.
  hints:
    idempotent: false
    readOnly: false
  name: keys-create-key
- description: Gets a list of all KMS keys in the caller's AWS account and Region.
  hints:
    idempotent: true
    readOnly: true
  name: keys-list-keys
- description: Provides detailed information about a KMS key.
  hints:
    idempotent: true
    readOnly: true
  name: keys-describe-key
- description: Encrypts plaintext of up to 4,096 bytes using a KMS key.
  hints:
    idempotent: false
    readOnly: false
  name: crypto-encrypt
- description: Decrypts ciphertext that was encrypted by a KMS key.
  hints:
    idempotent: false
    readOnly: false
  name: crypto-decrypt
- description: Returns a unique symmetric data key for use outside of KMS.
  hints:
    idempotent: false
    readOnly: false
  name: crypto-generate-data-key
---
