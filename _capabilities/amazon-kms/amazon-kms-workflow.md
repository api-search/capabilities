---
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
- cryptography
- amazon kms
- aws
- crypto decrypt
- Administrator
- crypto generate data key
- unified workflow for amazon kms resource management
- workflow
- manages resources and configurations
- key management
- gets a list of all kms keys in the caller's aws account and region.
- integrates api into applications
- creates a unique customer managed kms key in your aws account and region.
- returns a unique symmetric data key for use outside of kms.
- security
- Developer
- keys list keys
- crypto encrypt
- keys describe key
- decrypts ciphertext that was encrypted by a kms key.
- provides detailed information about a kms key.
- encryption
- data protection
- encrypts plaintext of up to 4,096 bytes using a kms key.
- keys create key
slug: amazon-kms-workflow
tags:
- Amazon KMS
- AWS
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
