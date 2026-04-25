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
- crypto decrypt
- creates a unique customer managed kms key in your aws account and region.
- Administrator
- unified workflow for amazon kms resource management
- encrypts plaintext of up to 4,096 bytes using a kms key.
- workflow
- keys create key
- decrypts ciphertext that was encrypted by a kms key.
- keys list keys
- gets a list of all kms keys in the caller's aws account and region.
- security
- data protection
- integrates api into applications
- key management
- manages resources and configurations
- amazon kms
- provides detailed information about a kms key.
- keys describe key
- crypto generate data key
- cryptography
- encryption
- aws
- crypto encrypt
- returns a unique symmetric data key for use outside of kms.
- Developer
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
