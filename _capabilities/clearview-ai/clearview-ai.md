---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Clearview Ai
operations: []
personas: []
provider_name: Clearview AI
provider_slug: clearview-ai
search_terms:
- biometrics
- identity
- law enforcement
- investigations
- surveillance
- facial recognition
slug: clearview-ai
source_filename: clearview-ai.yaml
source_heading: Capability Spec
source_yaml: "# Naftiko capabilities profile for Clearview AI.\n# These are descriptive workflow capabilities derived from publicly\n# stated Clearview AI product surfaces. Public API documentation\n# does not exist; these capabilities are not bound to public OpenAPI\n# operations and serve as a reference taxonomy for vetted integrators.\nprovider: clearview-ai\nname: Clearview AI\ndescription: >-\n  Clearview AI provides facial recognition and identity matching\n  services to vetted government, law enforcement, and financial\n  customers. These capabilities describe high-level workflows the\n  platform supports.\ncapabilities:\n  - id: clearview-ai.search.face\n    name: Search by face\n    description: Submit a probe image and retrieve candidate matches with source URLs.\n    inputs:\n      - probe-image\n    outputs:\n      - matches\n      - score\n      - source-url\n\n  - id: clearview-ai.investigation.create\n    name: Create investigation\n    description: Open a case to group probe\
  \ submissions and findings.\n    inputs:\n      - case-number\n      - agency\n      - investigator\n    outputs:\n      - investigation-id\n\n  - id: clearview-ai.investigation.append-finding\n    name: Append finding to investigation\n    description: Attach a face-match result to an open investigation.\n    inputs:\n      - investigation-id\n      - match-id\n      - notes\n    outputs:\n      - finding-id\n\n  - id: clearview-ai.user.list\n    name: List authorized users\n    description: Enumerate vetted users authorized to query the platform.\n    inputs:\n      - agency\n    outputs:\n      - users\n\n  - id: clearview-ai.audit.list\n    name: List audit events\n    description: Retrieve audit-log events for an agency, user, or case.\n    inputs:\n      - agency\n      - user\n      - case-number\n      - from\n      - to\n    outputs:\n      - events\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/clearview-ai/refs/heads/main/capabilities/clearview-ai.yaml
tags: []
tools: []
---
