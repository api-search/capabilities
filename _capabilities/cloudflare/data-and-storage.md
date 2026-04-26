---
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
- hyperdrive delete config
- execute sql query on a d1 database.
- hyperdrive create config
- database
- serverless
- list keys in a kv namespace.
- delete a kv value.
- list hyperdrive configs
- r2 get bucket
- create a hyperdrive configuration.
- cloud
- kv delete value
- kv namespace management.
- list buckets
- list hyperdrive configs.
- web performance
- delete an r2 bucket.
- hyperdrive list configs
- list hyperdrive configurations.
- delete a hyperdrive configuration.
- ai gateway
- list r2 storage buckets.
- edge computing
- d1 database management.
- r2 create bucket
- dns
- r2 list objects
- cdn
- platform
- d1 create database
- ddos protection
- d1 delete database
- artificial intelligence
- edge
- api gateway
- list kv namespaces
- list kv namespaces.
- create a d1 database.
- create a kv namespace.
- containers
- d1 list databases
- storage
- security
- real-time communication
- list r2 buckets.
- r2 bucket management.
- create an r2 bucket.
- kv list namespaces
- list d1 databases.
- kv read value
- r2 delete bucket
- kv write value
- list objects in an r2 bucket.
- object storage
- cloudflare
- write a kv value.
- list databases
- delete a d1 database.
- kv create namespace
- get r2 bucket details.
- kv list keys
- read a kv value.
- hyperdrive configuration management.
- data
- r2 list buckets
- d1 query database
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
