---
categories: []
consumed_apis:
- managed-blockchain
description: Workflow capability for blockchain architects and developers to create and manage Hyperledger Fabric and Ethereum networks, members, peer nodes, and proposals on Amazon Managed Blockchain.
layout: capability
name: Amazon Managed Blockchain - Network Operations
operations:
- description: List blockchain networks
  method: GET
  name: list-networks
  path: /v1/networks
- description: Create a blockchain network
  method: POST
  name: create-network
  path: /v1/networks
- description: List members
  method: GET
  name: list-members
  path: /v1/networks/{id}/members
- description: Create a member
  method: POST
  name: create-member
  path: /v1/networks/{id}/members
- description: List peer nodes
  method: GET
  name: list-nodes
  path: /v1/networks/{id}/nodes
- description: Create a peer node
  method: POST
  name: create-node
  path: /v1/networks/{id}/nodes
personas: []
provider_name: Amazon Managed Blockchain
provider_slug: amazon-managed-blockchain
search_terms:
- create a member
- list all amazon managed blockchain networks
- list all members of a blockchain network
- blockchain networks
- Blockchain Architect
- hyperledger fabric
- list networks
- create peer node
- list blockchain networks
- create a blockchain network
- create blockchain network
- list members
- Blockchain Developer
- create member
- list peer nodes
- list network members
- amazon
- distributed ledger
- list nodes
- ethereum
- list all peer nodes in a blockchain network
- aws
- peer nodes
- invite network member
- blockchain
- create a peer node
- create a peer node to participate in a blockchain network
- create network
- network members
- create node
- create a new hyperledger fabric or ethereum blockchain network
- invite an aws account to join a blockchain network as a member
slug: blockchain-network-operations
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Managed Blockchain - Network Operations\"\n  description: \"Workflow capability for blockchain architects and developers to create and manage Hyperledger Fabric and Ethereum networks, members, peer nodes, and proposals on Amazon Managed Blockchain.\"\n  tags:\n    - Amazon\n    - Blockchain\n    - Hyperledger Fabric\n    - Ethereum\n    - Distributed Ledger\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: managed-blockchain\n      location: ./shared/managed-blockchain.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: blockchain-api\n      description: \"Unified REST API for Amazon Managed Blockchain operations.\"\n      resources:\n        - path: /v1/networks\n          name: networks\n\
  \          description: \"Blockchain networks\"\n          operations:\n            - method: GET\n              name: list-networks\n              description: \"List blockchain networks\"\n              call: \"managed-blockchain.list-networks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-network\n              description: \"Create a blockchain network\"\n              call: \"managed-blockchain.create-network\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/networks/{id}/members\n          name: members\n          description: \"Network members\"\n          operations:\n            - method: GET\n              name: list-members\n              description: \"List members\"\n              call: \"managed-blockchain.list-members\"\n              with:\n                networkId: \"rest.id\"\n        \
  \      outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-member\n              description: \"Create a member\"\n              call: \"managed-blockchain.create-member\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/networks/{id}/nodes\n          name: nodes\n          description: \"Peer nodes\"\n          operations:\n            - method: GET\n              name: list-nodes\n              description: \"List peer nodes\"\n              call: \"managed-blockchain.list-nodes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-node\n              description: \"Create a peer node\"\n              call: \"managed-blockchain.create-node\"\n              outputParameters:\n                - type: object\n                \
  \  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: blockchain-mcp\n      transport: http\n      description: \"MCP server for AI-assisted blockchain network operations.\"\n      tools:\n        - name: list-blockchain-networks\n          description: \"List all Amazon Managed Blockchain networks\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"managed-blockchain.list-networks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-blockchain-network\n          description: \"Create a new Hyperledger Fabric or Ethereum blockchain network\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"managed-blockchain.create-network\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-network-members\n \
  \         description: \"List all members of a blockchain network\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"managed-blockchain.list-members\"\n          with:\n            networkId: \"tools.networkId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: invite-network-member\n          description: \"Invite an AWS account to join a blockchain network as a member\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"managed-blockchain.create-member\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-peer-nodes\n          description: \"List all peer nodes in a blockchain network\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"managed-blockchain.list-nodes\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-peer-node\n          description: \"Create a peer node to participate in a blockchain network\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"managed-blockchain.create-node\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-managed-blockchain/refs/heads/main/capabilities/blockchain-network-operations.yaml
tags:
- Amazon
- Blockchain
- Hyperledger Fabric
- Ethereum
- Distributed Ledger
tools:
- description: List all Amazon Managed Blockchain networks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-blockchain-networks
- description: Create a new Hyperledger Fabric or Ethereum blockchain network
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-blockchain-network
- description: List all members of a blockchain network
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-network-members
- description: Invite an AWS account to join a blockchain network as a member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invite-network-member
- description: List all peer nodes in a blockchain network
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-peer-nodes
- description: Create a peer node to participate in a blockchain network
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-peer-node
---
