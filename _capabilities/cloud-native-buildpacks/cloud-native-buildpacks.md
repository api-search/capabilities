---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Cloud Native Buildpacks
operations: []
personas: []
provider_name: Cloud Native Buildpacks
provider_slug: cloud-native-buildpacks
search_terms:
- buildpacks
- open source
- images
- platform
- containers
- reproducible builds
- cncf
- oci
slug: cloud-native-buildpacks
source_filename: cloud-native-buildpacks.yaml
source_heading: Capability Spec
source_yaml: "# Naftiko capabilities profile for Cloud Native Buildpacks.\n# Capabilities describe high-level workflows the CNB lifecycle, pack\n# CLI, kpack, and the buildpack registry support.\nprovider: cloud-native-buildpacks\nname: Cloud Native Buildpacks\ndescription: >-\n  Cloud Native Buildpacks transform application source code into OCI\n  images. These capabilities cover detecting, building, exporting,\n  rebasing, and distributing CNB artifacts through pack, kpack, and\n  the buildpack registry.\ncapabilities:\n  - id: cnb.lifecycle.detect\n    name: Detect buildpacks\n    description: >-\n      Run the detect phase to determine which buildpacks in a builder\n      apply to a source directory.\n    api: cloud-native-buildpacks:lifecycle\n    inputs:\n      - app-dir\n      - builder\n      - platform-api\n    outputs:\n      - build-plan\n      - selected-buildpacks\n\n  - id: cnb.lifecycle.build\n    name: Build image\n    description: >-\n      Run the full lifecycle (detect,\
  \ restore, build, export) to\n      produce a runnable OCI image.\n    api: cloud-native-buildpacks:pack-cli\n    inputs:\n      - app-dir\n      - builder\n      - run-image\n      - tag\n      - env\n      - cache-image\n    outputs:\n      - image-reference\n      - digest\n\n  - id: cnb.lifecycle.rebase\n    name: Rebase image\n    description: >-\n      Swap the run image of an existing CNB-built image without\n      rebuilding application layers.\n    api: cloud-native-buildpacks:lifecycle\n    inputs:\n      - image-reference\n      - run-image\n    outputs:\n      - new-digest\n\n  - id: cnb.builder.create\n    name: Create builder\n    description: >-\n      Create a CNB builder image from a TOML config that lists\n      buildpacks, the lifecycle, and the run image.\n    api: cloud-native-buildpacks:pack-cli\n    inputs:\n      - builder-config\n      - tag\n    outputs:\n      - builder-image-reference\n\n  - id: cnb.buildpack.package\n    name: Package buildpack\n    description:\
  \ Package a buildpack as an OCI artifact for distribution.\n    api: cloud-native-buildpacks:pack-cli\n    inputs:\n      - buildpack-dir\n      - tag\n      - format\n    outputs:\n      - package-reference\n\n  - id: cnb.kpack.image.declare\n    name: Declare kpack Image\n    description: >-\n      Declare an Image custom resource so kpack continuously rebuilds\n      the OCI image when source or buildpacks change.\n    api: cloud-native-buildpacks:kpack\n    inputs:\n      - source\n      - builder-ref\n      - tag\n      - service-account\n    outputs:\n      - image-resource\n\n  - id: cnb.registry.search\n    name: Search registry\n    description: Search the buildpack registry for published buildpacks.\n    api: cloud-native-buildpacks:registry\n    inputs:\n      - query\n    outputs:\n      - results\n\n  - id: cnb.registry.get\n    name: Get registry entry\n    description: Retrieve metadata for a published buildpack by ID and version.\n    api: cloud-native-buildpacks:registry\n\
  \    inputs:\n      - id\n      - version\n    outputs:\n      - entry\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cloud-native-buildpacks/refs/heads/main/capabilities/cloud-native-buildpacks.yaml
tags: []
tools: []
---
