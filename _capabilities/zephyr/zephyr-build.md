---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Zephyr Build
operations: []
personas: []
provider_name: Zephyr Project
provider_slug: zephyr
search_terms:
- edge
- linux foundation
- iot
- open source
- embedded
- rtos
slug: zephyr-build
source_filename: zephyr-build.yaml
source_heading: Capability Spec
source_yaml: "name: Zephyr Build and Flash Capability\ndescription: >-\n  Capability composition that walks a developer through initializing a\n  Zephyr workspace with west, building a sample for a target board, and\n  flashing the resulting binary onto hardware. Captures the canonical\n  developer workflow rather than a REST API surface.\napi: zephyr\nversion: '1.0.0'\noperations:\n  - id: westInit\n    summary: Initialize a Zephyr workspace from the manifest\n    command: west init -m https://github.com/zephyrproject-rtos/zephyr --mr main workspace\n  - id: westUpdate\n    summary: Fetch and check out all manifest repositories\n    command: west update\n  - id: westBuild\n    summary: Build a sample for a target board\n    command: west build -p auto -b {board} samples/hello_world\n  - id: westFlash\n    summary: Flash the built artifact onto the connected board\n    command: west flash\n  - id: westDebug\n    summary: Launch a debug session against the running target\n    command: west\
  \ debug\nworkflow:\n  - step: westInit\n  - step: westUpdate\n  - step: westBuild\n    inputs:\n      board: nrf52840dk/nrf52840\n  - step: westFlash\n  - step: westDebug\n    optional: true\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zephyr/refs/heads/main/capabilities/zephyr-build.yaml
tags: []
tools: []
---
