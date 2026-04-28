---
categories: []
consumed_apis:
- appium
description: Workflow capability for mobile app test automation using Appium. Combines session management, element interaction, device control, and screenshot capture into a unified automation workflow for QA engineers and test automation engineers testing iOS, Android, and cross-platform mobile applications.
layout: capability
name: Appium Mobile Test Automation
operations:
- description: Starts a new mobile automation session
  method: POST
  name: start-session
  path: /v1/sessions
- description: Finds a UI element by locator strategy
  method: POST
  name: find-element
  path: /v1/elements
- description: Captures the current device screen
  method: GET
  name: capture-screenshot
  path: /v1/screenshots
- description: Installs an app on the test device
  method: POST
  name: install-app
  path: /v1/apps
- description: Launches or activates an installed app
  method: POST
  name: launch-app
  path: /v1/apps
- description: Checks Appium server availability
  method: GET
  name: check-server
  path: /v1/server/status
personas: []
provider_name: Appium
provider_slug: appium
search_terms:
- simulating user input including taps, swipes, and text entry
- installs a mobile app (.apk or .ipa) on the test device from a local path or url
- openjs foundation
- capture screenshot
- find ui element
- device-level operations including app lifecycle and device state
- takes a screenshot of the current mobile app screen for visual inspection or debugging
- capture screen
- launch mobile app
- engineer building automated test frameworks and ci/cd pipelines for mobile apps
- installs an app on the test device
- launches or activates an installed app
- start automation session
- open source
- finds a ui element by locator strategy
- qa
- cross-platform
- check server
- start session
- finds a ui element in the current app screen using a locator strategy (accessibility id, xpath, id, class name)
- find element
- install mobile app
- automation session lifecycle management
- end-to-end mobile app test automation combining session management, element interaction, device control, and visual capture
- launch app
- checks appium server availability
- appium
- screen capture for visual testing
- webdriver
- quality assurance professional writing and running mobile app tests
- starts a new mobile automation session
- app installation and lifecycle management
- ends an appium automation session and releases device resources
- starts a new appium automation session for a mobile app with platform capabilities (platformname, devicename, app path, etc.)
- test automation
- check appium server
- install app
- checks whether the appium server is running and ready to accept connections
- end automation session
- ios
- Test Automation Engineer
- mobile testing
- ui element discovery and interaction
- appium server health check
- android
- captures the current device screen
- QA Engineer
- automated testing of mobile and web applications
- launches or brings to foreground a mobile app by package name (android) or bundle id (ios)
slug: mobile-test-automation
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Appium Mobile Test Automation\n  description: >-\n    Workflow capability for mobile app test automation using Appium. Combines session\n    management, element interaction, device control, and screenshot capture into a\n    unified automation workflow for QA engineers and test automation engineers\n    testing iOS, Android, and cross-platform mobile applications.\n  tags:\n    - Appium\n    - Mobile Testing\n    - Test Automation\n    - Android\n    - iOS\n    - QA\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      APPIUM_HOST: APPIUM_HOST\n\ncapability:\n  consumes:\n    - import: appium\n      location: ./shared/appium-server.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: mobile-automation-api\n      description: Unified REST API for mobile app test automation workflows.\n      resources:\n        - path: /v1/sessions\n          name: sessions\n    \
  \      description: Automation session lifecycle management\n          operations:\n            - method: POST\n              name: start-session\n              description: Starts a new mobile automation session\n              call: \"appium.create-session\"\n              with:\n                capabilities: \"rest.capabilities\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/elements\n          name: elements\n          description: UI element discovery and interaction\n          operations:\n            - method: POST\n              name: find-element\n              description: Finds a UI element by locator strategy\n              call: \"appium.find-element\"\n              with:\n                sessionId: \"rest.sessionId\"\n                using: \"rest.using\"\n                value: \"rest.value\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n\
  \        - path: /v1/screenshots\n          name: screenshots\n          description: Screen capture for visual testing\n          operations:\n            - method: GET\n              name: capture-screenshot\n              description: Captures the current device screen\n              call: \"appium.get-screenshot\"\n              with:\n                sessionId: \"rest.sessionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/apps\n          name: apps\n          description: App installation and lifecycle management\n          operations:\n            - method: POST\n              name: install-app\n              description: Installs an app on the test device\n              call: \"appium.install-app\"\n              with:\n                sessionId: \"rest.sessionId\"\n                appPath: \"rest.appPath\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n            - method: POST\n              name: launch-app\n              description: Launches or activates an installed app\n              call: \"appium.activate-app\"\n              with:\n                sessionId: \"rest.sessionId\"\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/server/status\n          name: server-status\n          description: Appium server health check\n          operations:\n            - method: GET\n              name: check-server\n              description: Checks Appium server availability\n              call: \"appium.get-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: mobile-automation-mcp\n      transport: http\n      description: MCP server for AI-assisted mobile app test automation.\n      tools:\n        - name: start-automation-session\n\
  \          description: Starts a new Appium automation session for a mobile app with platform capabilities (platformName, deviceName, app path, etc.)\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"appium.create-session\"\n          with:\n            capabilities: \"tools.capabilities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: end-automation-session\n          description: Ends an Appium automation session and releases device resources\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"appium.delete-session\"\n          with:\n            sessionId: \"tools.sessionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-ui-element\n          description: Finds a UI element in the current app screen using a locator strategy (accessibility id, xpath, id, class name)\n\
  \          hints:\n            readOnly: true\n            idempotent: true\n          call: \"appium.find-element\"\n          with:\n            sessionId: \"tools.sessionId\"\n            using: \"tools.using\"\n            value: \"tools.value\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: capture-screen\n          description: Takes a screenshot of the current mobile app screen for visual inspection or debugging\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"appium.get-screenshot\"\n          with:\n            sessionId: \"tools.sessionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: install-mobile-app\n          description: Installs a mobile app (.apk or .ipa) on the test device from a local path or URL\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"appium.install-app\"\
  \n          with:\n            sessionId: \"tools.sessionId\"\n            appPath: \"tools.appPath\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: launch-mobile-app\n          description: Launches or brings to foreground a mobile app by package name (Android) or bundle ID (iOS)\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"appium.activate-app\"\n          with:\n            sessionId: \"tools.sessionId\"\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-appium-server\n          description: Checks whether the Appium server is running and ready to accept connections\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"appium.get-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/appium/refs/heads/main/capabilities/mobile-test-automation.yaml
tags:
- Appium
- Mobile Testing
- Test Automation
- Android
- iOS
- QA
tools:
- description: Starts a new Appium automation session for a mobile app with platform capabilities (platformName, deviceName, app path, etc.)
  hints:
    destructive: false
    readOnly: false
  name: start-automation-session
- description: Ends an Appium automation session and releases device resources
  hints:
    destructive: true
    readOnly: false
  name: end-automation-session
- description: Finds a UI element in the current app screen using a locator strategy (accessibility id, xpath, id, class name)
  hints:
    idempotent: true
    readOnly: true
  name: find-ui-element
- description: Takes a screenshot of the current mobile app screen for visual inspection or debugging
  hints:
    idempotent: true
    readOnly: true
  name: capture-screen
- description: Installs a mobile app (.apk or .ipa) on the test device from a local path or URL
  hints:
    destructive: false
    readOnly: false
  name: install-mobile-app
- description: Launches or brings to foreground a mobile app by package name (Android) or bundle ID (iOS)
  hints:
    destructive: false
    readOnly: false
  name: launch-mobile-app
- description: Checks whether the Appium server is running and ready to accept connections
  hints:
    idempotent: true
    readOnly: true
  name: check-appium-server
---
