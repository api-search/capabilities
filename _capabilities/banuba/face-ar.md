---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Face Ar
operations: []
personas: []
provider_name: Banuba
provider_slug: banuba
search_terms:
- facial
- beauty
- face recognition
- video
- augmented reality
- ar
- sdk
slug: face-ar
source_filename: face-ar.yaml
source_heading: Capability Spec
source_yaml: "name: Face AR & Beauty Filters\ndescription: >-\n  Naftiko capability for Banuba Face AR SDK: real-time augmented reality face effects,\n  beauty filters, virtual try-on, and background segmentation across mobile, web, and\n  desktop platforms.\nversion: '1.0'\nprovider: Banuba\ncategory: Augmented Reality\ntags:\n  - AR\n  - Augmented Reality\n  - Beauty Filters\n  - Face Tracking\n  - Virtual Try-On\n  - Video Processing\nhumanURL: https://docs.banuba.com/far-sdk/\nactions:\n  - name: Apply Face AR Effect\n    description: Apply a real-time AR effect (mask, filter, accessory) to a live camera feed or video.\n    inputs:\n      - name: videoFrame\n        type: MediaFrame\n        required: true\n      - name: effectId\n        type: string\n        required: true\n    outputs:\n      - name: processedFrame\n        type: MediaFrame\n  - name: Apply Beauty Filter\n    description: Apply skin smoothing, face reshaping, and makeup filters to a video frame.\n    inputs:\n   \
  \   - name: videoFrame\n        type: MediaFrame\n        required: true\n      - name: beautySettings\n        type: BeautySettings\n        required: true\n    outputs:\n      - name: processedFrame\n        type: MediaFrame\n  - name: Segment Background\n    description: Remove or replace the background in a video frame using face segmentation.\n    inputs:\n      - name: videoFrame\n        type: MediaFrame\n        required: true\n      - name: backgroundImage\n        type: MediaFrame\n        required: false\n    outputs:\n      - name: processedFrame\n        type: MediaFrame\n  - name: Virtual Try-On\n    description: Overlay virtual makeup, glasses, or accessories on a detected face.\n    inputs:\n      - name: videoFrame\n        type: MediaFrame\n        required: true\n      - name: productId\n        type: string\n        required: true\n    outputs:\n      - name: processedFrame\n        type: MediaFrame\n  - name: Face Liveness Check\n    description: Verify that a detected\
  \ face is live and not a spoof attempt.\n    inputs:\n      - name: videoFrame\n        type: MediaFrame\n        required: true\n    outputs:\n      - name: isLive\n        type: boolean\n      - name: confidence\n        type: number\nplatforms:\n  - iOS\n  - Android\n  - Web (HTML5)\n  - Windows\n  - macOS\n  - Unity\n  - Flutter\n  - React Native\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/banuba/refs/heads/main/capabilities/face-ar.yaml
tags: []
tools: []
---
