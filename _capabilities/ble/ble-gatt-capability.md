---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Ble Gatt Capability
operations: []
personas: []
provider_name: BLE
provider_slug: ble
search_terms:
- iot
- embedded
- wireless
- ble
- bluetooth
- standards
- protocols
slug: ble-gatt-capability
source_filename: ble-gatt-capability.yaml
source_heading: Capability Spec
source_yaml: "name: Bluetooth Low Energy (BLE) GATT Capability\ndescription: >-\n  Naftiko capability definition for Bluetooth Low Energy GATT interactions,\n  documenting service discovery, characteristic read/write/notify, and\n  advertising data interpretation.\nversion: 1.0.0\nspecification:\n  name: Bluetooth Core Specification\n  version: \"6.0\"\n  url: https://www.bluetooth.com/specifications/specs/core60/\n  governance: https://www.bluetooth.com/about-us/membership/\n  conformance: https://www.bluetooth.com/develop-with-bluetooth/qualification-listing/\ncapabilities:\n  - name: discoverServices\n    description: Discover all GATT services exposed by a connected BLE peripheral\n    layer: GATT\n    operation: Service Discovery\n    reference: \"Bluetooth Core Spec Vol 3, Part G, Section 4.4\"\n  - name: discoverCharacteristics\n    description: Discover characteristics within a specific GATT service\n    layer: GATT\n    operation: Characteristic Discovery\n  - name: readCharacteristic\n\
  \    description: Read the current value of a GATT characteristic\n    layer: GATT\n    operation: Characteristic Value Read\n    properties: [\"Read\"]\n  - name: writeCharacteristic\n    description: Write a value to a GATT characteristic\n    layer: GATT\n    operation: Characteristic Value Write\n    properties: [\"Write\", \"Write Without Response\"]\n  - name: enableNotifications\n    description: Enable characteristic value notifications via CCCD descriptor\n    layer: GATT\n    operation: Notifications\n    properties: [\"Notify\"]\n  - name: enableIndications\n    description: Enable characteristic value indications (acknowledged notifications)\n    layer: GATT\n    operation: Indications\n    properties: [\"Indicate\"]\n  - name: scanAdvertising\n    description: Scan for BLE advertising packets from nearby devices\n    layer: GAP\n    operation: Scanning\n    advertisingTypes: [\"ADV_IND\", \"ADV_NONCONN_IND\", \"ADV_SCAN_IND\"]\n  - name: connect\n    description: Establish\
  \ a BLE connection with a peripheral device\n    layer: GAP\n    operation: Connection Establishment\nimplementations:\n  - name: Apple Core Bluetooth\n    platform: iOS/macOS\n    url: https://developer.apple.com/documentation/corebluetooth\n  - name: Android Bluetooth API\n    platform: Android\n    url: https://developer.android.com/guide/topics/connectivity/bluetooth/ble-overview\n  - name: Web Bluetooth API\n    platform: Browser (Chrome/Edge)\n    url: https://developer.chrome.com/docs/capabilities/bluetooth\n  - name: Zephyr BT Stack\n    platform: RTOS/Embedded\n    url: https://docs.zephyrproject.org/latest/connectivity/bluetooth/index.html\n  - name: nRF Connect SDK\n    platform: Nordic nRF52/53\n    url: https://developer.nordicsemi.com/nRF_Connect_SDK/doc/latest/nrf/index.html\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ble/refs/heads/main/capabilities/ble-gatt-capability.yaml
tags: []
tools: []
---
