---
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
- list members
- create member
- create a peer node to participate in a blockchain network
- create peer node
- ethereum
- create a peer node
- list network members
- create network
- hyperledger fabric
- list networks
- list blockchain networks
- create a new hyperledger fabric or ethereum blockchain network
- list all amazon managed blockchain networks
- network members
- invite network member
- invite an aws account to join a blockchain network as a member
- create blockchain network
- Blockchain Architect
- distributed ledger
- list peer nodes
- blockchain
- amazon
- Blockchain Developer
- create a member
- aws
- create node
- peer nodes
- list nodes
- create a blockchain network
- list all members of a blockchain network
- list all peer nodes in a blockchain network
- blockchain networks
slug: blockchain-network-operations
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
