---
categories: []
consumed_apis:
- kms
description: Unified workflow capability for Amazon KMS combining resource management and operations.
layout: capability
name: Amazon KMS Workflow
operations: []
personas: []
provider_name: Amazon KMS
provider_slug: amazon-kms
search_terms:
- crypto encrypt
- encryption
- provides detailed information about a kms key.
- workflow
- key management
- crypto decrypt
- manages resources and configurations
- crypto generate data key
- creates a unique customer managed kms key in your aws account and region.
- data protection
- aws
- returns a unique symmetric data key for use outside of kms.
- security
- keys list keys
- decrypts ciphertext that was encrypted by a kms key.
- unified workflow for amazon kms resource management
- integrates api into applications
- gets a list of all kms keys in the caller's aws account and region.
- Developer
- cryptography
- keys describe key
- amazon kms
- keys create key
- encrypts plaintext of up to 4,096 bytes using a kms key.
- Administrator
slug: amazon-kms-workflow
source_filename: amazon-kms-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon KMS Workflow\n  description: Unified workflow capability for Amazon KMS combining resource management and operations.\n  tags:\n  - Amazon KMS\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - import: kms\n    location: ./shared/kms.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: kms-api\n    description: REST API for Amazon KMS workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: kms-mcp\n    transport: http\n    description: MCP server for Amazon KMS.\n    tools:\n    - name: keys-create-key\n      description: Creates a unique customer managed KMS key in your AWS account and Region.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: kms.createkey\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: keys-list-keys\n      description: Gets a list of all KMS keys in the caller's AWS account and Region.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kms.listkeys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: keys-describe-key\n      description: Provides detailed information about a KMS key.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kms.describekey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: crypto-encrypt\n      description: Encrypts plaintext of up to 4,096 bytes using a KMS key.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: kms.encrypt\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: crypto-decrypt\n      description: Decrypts ciphertext that was encrypted by a KMS key.\n      hints:\n        readOnly: false\n        idempotent: false\n\
  \      call: kms.decrypt\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: crypto-generate-data-key\n      description: Returns a unique symmetric data key for use outside of KMS.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: kms.generatedatakey\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
