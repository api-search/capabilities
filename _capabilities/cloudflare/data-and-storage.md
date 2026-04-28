---
categories:
- object-storage
consumed_apis:
- cloudflare-r2
- cloudflare-d1
- cloudflare-kv
- cloudflare-hyperdrive
description: Unified data and storage management combining R2 object storage, D1 serverless SQL, KV key-value store, and Hyperdrive database acceleration. Used by developers building data-driven applications on Cloudflare's edge.
layout: capability
name: Cloudflare Data and Storage
operations:
- description: List R2 buckets.
  method: GET
  name: list-buckets
  path: /v1/buckets
- description: List D1 databases.
  method: GET
  name: list-databases
  path: /v1/databases
- description: List KV namespaces.
  method: GET
  name: list-kv-namespaces
  path: /v1/kv-namespaces
- description: List Hyperdrive configs.
  method: GET
  name: list-hyperdrive-configs
  path: /v1/hyperdrive-configs
personas: []
provider_name: Cloudflare
provider_slug: cloudflare
search_terms:
- r2 list buckets
- hyperdrive list configs
- delete a d1 database.
- delete an r2 bucket.
- d1 list databases
- r2 delete bucket
- create a d1 database.
- delete a kv value.
- storage
- kv write value
- d1 database management.
- edge
- list hyperdrive configs.
- hyperdrive delete config
- platform
- real-time communication
- get r2 bucket details.
- r2 get bucket
- d1 create database
- list buckets
- d1 query database
- list kv namespaces.
- edge computing
- kv read value
- write a kv value.
- hyperdrive configuration management.
- api gateway
- kv namespace management.
- list hyperdrive configurations.
- kv list keys
- containers
- data
- delete a hyperdrive configuration.
- web performance
- read a kv value.
- execute sql query on a d1 database.
- security
- kv create namespace
- kv delete value
- ai gateway
- cdn
- ddos protection
- serverless
- artificial intelligence
- list databases
- cloudflare
- list hyperdrive configs
- create a hyperdrive configuration.
- r2 create bucket
- r2 list objects
- list objects in an r2 bucket.
- list r2 storage buckets.
- d1 delete database
- list keys in a kv namespace.
- create a kv namespace.
- list kv namespaces
- kv list namespaces
- cloud
- database
- dns
- create an r2 bucket.
- object storage
- r2 bucket management.
- list d1 databases.
- hyperdrive create config
- list r2 buckets.
slug: data-and-storage
tags:
- Cloudflare
- Storage
- Database
- Data
tools:
- description: List R2 storage buckets.
  hints:
    openWorld: true
    readOnly: true
  name: r2-list-buckets
- description: Create an R2 bucket.
  hints:
    readOnly: false
  name: r2-create-bucket
- description: Get R2 bucket details.
  hints:
    readOnly: true
  name: r2-get-bucket
- description: List objects in an R2 bucket.
  hints:
    readOnly: true
  name: r2-list-objects
- description: Delete an R2 bucket.
  hints:
    destructive: true
    idempotent: true
  name: r2-delete-bucket
- description: List D1 databases.
  hints:
    openWorld: true
    readOnly: true
  name: d1-list-databases
- description: Create a D1 database.
  hints:
    readOnly: false
  name: d1-create-database
- description: Execute SQL query on a D1 database.
  hints:
    readOnly: false
  name: d1-query-database
- description: Delete a D1 database.
  hints:
    destructive: true
    idempotent: true
  name: d1-delete-database
- description: List KV namespaces.
  hints:
    openWorld: true
    readOnly: true
  name: kv-list-namespaces
- description: Create a KV namespace.
  hints:
    readOnly: false
  name: kv-create-namespace
- description: List keys in a KV namespace.
  hints:
    readOnly: true
  name: kv-list-keys
- description: Read a KV value.
  hints:
    readOnly: true
  name: kv-read-value
- description: Write a KV value.
  hints:
    idempotent: true
    readOnly: false
  name: kv-write-value
- description: Delete a KV value.
  hints:
    destructive: true
    idempotent: true
  name: kv-delete-value
- description: List Hyperdrive configurations.
  hints:
    openWorld: true
    readOnly: true
  name: hyperdrive-list-configs
- description: Create a Hyperdrive configuration.
  hints:
    readOnly: false
  name: hyperdrive-create-config
- description: Delete a Hyperdrive configuration.
  hints:
    destructive: true
    idempotent: true
  name: hyperdrive-delete-config
---
