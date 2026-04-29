---
categories: []
consumed_apis: []
description: Workflow capability for managing and monitoring Apache BookKeeper clusters, including bookie health checks, ledger inspection, and auto-recovery operations.
layout: capability
name: Bookkeeper Cluster Management
operations: []
personas: []
provider_name: Apache BookKeeper
provider_slug: apache-bookkeeper
search_terms:
- distributed systems
- storage
- streaming
- open source
- apache
- log storage
slug: bookkeeper-cluster-management
source_filename: bookkeeper-cluster-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  title: Apache BookKeeper Cluster Management\n  description: >-\n    Workflow capability for managing and monitoring Apache BookKeeper clusters, including\n    bookie health checks, ledger inspection, and auto-recovery operations.\n  version: 4.16.0\n  contact:\n    name: Apache BookKeeper Community\n    url: https://bookkeeper.apache.org/\n\nservers:\n  rest:\n    url: http://localhost:8080\n    port: 8080\n  mcp:\n    port: 9090\n\ntools:\n  - name: check-cluster-health\n    description: Check the health of a BookKeeper cluster by verifying heartbeat, bookie state, and cluster info.\n    operations:\n      - $ref: shared/bookkeeper-admin.yaml#/operations/getHeartbeat\n      - $ref: shared/bookkeeper-admin.yaml#/operations/getBookieState\n      - $ref: shared/bookkeeper-admin.yaml#/operations/getClusterInfo\n\n  - name: inspect-ledgers\n    description: List and inspect ledgers stored on a bookie node.\n    operations:\n      - $ref: shared/bookkeeper-admin.yaml#/operations/listLedgers\n\
  \      - $ref: shared/bookkeeper-admin.yaml#/operations/getLedgerMetadata\n\n  - name: monitor-replication\n    description: Monitor under-replication status and identify which bookies hold under-replicated ledgers.\n    operations:\n      - $ref: shared/bookkeeper-admin.yaml#/operations/listUnderReplicatedLedgers\n      - $ref: shared/bookkeeper-admin.yaml#/operations/whoIsAuditor\n\n  - name: trigger-recovery\n    description: Trigger an audit to initiate auto-recovery of under-replicated ledgers.\n    operations:\n      - $ref: shared/bookkeeper-admin.yaml#/operations/triggerAudit\n\n  - name: view-configuration\n    description: Retrieve the current server configuration of a bookie.\n    operations:\n      - $ref: shared/bookkeeper-admin.yaml#/operations/getServerConfig\n\n  - name: view-metrics\n    description: Retrieve Prometheus-format metrics from a bookie node.\n    operations:\n      - $ref: shared/bookkeeper-admin.yaml#/operations/getMetrics\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-bookkeeper/refs/heads/main/capabilities/bookkeeper-cluster-management.yaml
tags: []
tools: []
---
