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
- r2 get bucket
- list keys in a kv namespace.
- edge computing
- object storage
- database
- cloud
- create an r2 bucket.
- list buckets
- list hyperdrive configs.
- r2 list objects
- create a hyperdrive configuration.
- containers
- kv list namespaces
- real-time communication
- list hyperdrive configs
- create a d1 database.
- delete a hyperdrive configuration.
- kv read value
- ai gateway
- r2 delete bucket
- data
- dns
- list kv namespaces
- list d1 databases.
- d1 delete database
- hyperdrive list configs
- storage
- create a kv namespace.
- r2 create bucket
- delete a kv value.
- kv delete value
- security
- platform
- hyperdrive configuration management.
- read a kv value.
- cloudflare
- d1 create database
- edge
- list databases
- api gateway
- kv create namespace
- get r2 bucket details.
- list hyperdrive configurations.
- r2 list buckets
- kv list keys
- list objects in an r2 bucket.
- delete a d1 database.
- kv write value
- cdn
- ddos protection
- d1 database management.
- delete an r2 bucket.
- execute sql query on a d1 database.
- kv namespace management.
- serverless
- artificial intelligence
- write a kv value.
- r2 bucket management.
- hyperdrive create config
- web performance
- list kv namespaces.
- list r2 buckets.
- d1 query database
- d1 list databases
- list r2 storage buckets.
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
