---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Medical Device Connectivity
operations: []
personas: []
provider_name: Baxter International
provider_slug: baxter-international
search_terms:
- healthcare
- connected health
- infusion pumps
- medical devices
- patient monitoring
slug: medical-device-connectivity
source_filename: medical-device-connectivity.yaml
source_heading: Capability Spec
source_yaml: "capability:\n  name: Baxter DeviceBridge Medical Device Connectivity\n  description: >-\n    Baxter's DeviceBridge platform capabilities for connecting medical devices\n    to hospital IT systems, EMRs, and clinical data repositories using\n    HL7 FHIR and proprietary connectivity standards.\n  categories:\n    - name: Device Data Transfer\n      description: Secure transfer of clinical data from Baxter medical devices to hospital systems.\n      operations:\n        - name: Get Device Data\n          description: Retrieve latest clinical readings from a connected Baxter device.\n        - name: Stream Device Observations\n          description: Subscribe to real-time data stream from a medical device.\n        - name: Get Device Status\n          description: Retrieve operational status and alarm state of a connected device.\n    - name: Infusion Pump Integration\n      description: Infusion therapy data integration for smart pump documentation.\n      operations:\n     \
  \   - name: Get Infusion Record\n          description: Retrieve completed infusion record for EMR documentation.\n        - name: Submit BCMA Verification\n          description: Submit barcode medication administration verification data.\n        - name: Get Drug Library\n          description: Retrieve the current drug library configuration for a pump.\n        - name: Update Drug Library\n          description: Push updated drug library to connected infusion pumps.\n    - name: EMR Integration\n      description: Electronic medical record integration for automated clinical documentation.\n      operations:\n        - name: Post Observation to EMR\n          description: Automatically post device reading as an observation to the EMR via FHIR.\n        - name: Get Patient ADT\n          description: Retrieve patient admission, discharge, transfer events from EMR.\n    - name: Patient Monitoring\n      description: Vital signs and patient monitoring device integration.\n      operations:\n\
  \        - name: Get Vital Signs\n          description: Retrieve vital signs data (HR, SpO2, BP, RR, temperature) from bedside monitor.\n        - name: Get Alarm History\n          description: Retrieve alarm and alert history for a connected monitoring device.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/baxter-international/refs/heads/main/capabilities/medical-device-connectivity.yaml
tags: []
tools: []
---
