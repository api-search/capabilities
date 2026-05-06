---
categories: []
consumed_apis: []
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
- blockchain
- create a peer node
- invite an aws account to join a blockchain network as a member
- list networks
- peer nodes
- amazon
- distributed ledger
- network members
- Blockchain Architect
- create a member
- list blockchain networks
- create member
- list nodes
- create blockchain network
- create a blockchain network
- list all amazon managed blockchain networks
- create a peer node to participate in a blockchain network
- invite network member
- create node
- ethereum
- create a new hyperledger fabric or ethereum blockchain network
- list all members of a blockchain network
- hyperledger fabric
- Blockchain Developer
- list all peer nodes in a blockchain network
- list peer nodes
- create network
- list members
- create peer node
- blockchain networks
- list network members
slug: blockchain-network-operations
source_filename: blockchain-network-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Managed Blockchain - Network Operations\n  description: Workflow capability for blockchain architects and developers to create and manage Hyperledger Fabric and Ethereum\n    networks, members, peer nodes, and proposals on Amazon Managed Blockchain.\n  tags:\n  - Amazon\n  - Blockchain\n  - Hyperledger Fabric\n  - Ethereum\n  - Distributed Ledger\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: managed-blockchain\n    baseUri: https://managedblockchain.amazonaws.com\n    description: Amazon Managed Blockchain REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: AWS4-HMAC-SHA256 {{AWS_ACCESS_KEY_ID}}\n      placement: header\n    resources:\n    - name: networks\n      path: /networks\n\
  \      description: Manage blockchain networks\n      operations:\n      - name: list-networks\n        method: GET\n        description: List blockchain networks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-network\n        method: POST\n        description: Create a blockchain network\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: members\n      path: /networks/{networkId}/members\n      description: Manage network members\n      operations:\n      - name: list-members\n        method: GET\n        description: List network members\n        inputParameters:\n        - name: networkId\n          in: path\n          type: string\n          required: true\n          description: Network ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: create-member\n        method: POST\n        description: Create a network member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nodes\n      path: /networks/{networkId}/nodes\n      description: Manage peer nodes\n      operations:\n      - name: list-nodes\n        method: GET\n        description: List nodes in a network\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-node\n        method: POST\n        description: Create a peer node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: blockchain-api\n    description: Unified REST API for Amazon Managed Blockchain operations.\n    resources:\n    - path: /v1/networks\n     \
  \ name: networks\n      description: Blockchain networks\n      operations:\n      - method: GET\n        name: list-networks\n        description: List blockchain networks\n        call: managed-blockchain.list-networks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-network\n        description: Create a blockchain network\n        call: managed-blockchain.create-network\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/networks/{id}/members\n      name: members\n      description: Network members\n      operations:\n      - method: GET\n        name: list-members\n        description: List members\n        call: managed-blockchain.list-members\n        with:\n          networkId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-member\n        description: Create a member\n        call: managed-blockchain.create-member\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/networks/{id}/nodes\n      name: nodes\n      description: Peer nodes\n      operations:\n      - method: GET\n        name: list-nodes\n        description: List peer nodes\n        call: managed-blockchain.list-nodes\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-node\n        description: Create a peer node\n        call: managed-blockchain.create-node\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: blockchain-mcp\n    transport: http\n    description: MCP server for AI-assisted blockchain network operations.\n    tools:\n    - name: list-blockchain-networks\n      description: List all Amazon Managed Blockchain networks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: managed-blockchain.list-networks\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-blockchain-network\n      description: Create a new Hyperledger Fabric or Ethereum blockchain network\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: managed-blockchain.create-network\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-network-members\n      description: List all members of a blockchain network\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: managed-blockchain.list-members\n      with:\n        networkId: tools.networkId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: invite-network-member\n      description: Invite an AWS account to join a blockchain network as a member\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: managed-blockchain.create-member\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-peer-nodes\n      description: List all peer nodes in a blockchain network\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: managed-blockchain.list-nodes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-peer-node\n      description: Create a peer node to participate in a blockchain network\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: managed-blockchain.create-node\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
