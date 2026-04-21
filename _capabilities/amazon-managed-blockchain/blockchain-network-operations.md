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
- create a peer node
- create peer node
- aws
- invite network member
- create a new hyperledger fabric or ethereum blockchain network
- list all members of a blockchain network
- Blockchain Developer
- create blockchain network
- list all amazon managed blockchain networks
- list blockchain networks
- invite an aws account to join a blockchain network as a member
- list nodes
- ethereum
- list members
- list all peer nodes in a blockchain network
- list networks
- create a peer node to participate in a blockchain network
- create member
- hyperledger fabric
- create a blockchain network
- Blockchain Architect
- amazon
- blockchain networks
- peer nodes
- list network members
- list peer nodes
- blockchain
- create network
- create node
- create a member
- network members
- distributed ledger
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
