---
categories: []
consumed_apis: []
description: API for Caterpillar-to-dealer data transfer
layout: capability
name: CAT Caterpillar Telematics API
operations:
- description: CAT Get fleet snapshot
  method: GET
  name: get-pagenumber
  path: /{pageNumber}
- description: CAT Get equipment snapshot
  method: GET
  name: get-equipment-makemodelserial-make-model-serialn
  path: /equipment/makeModelSerial/{make}/{model}/{serialNumber}
- description: CAT Get fault codes
  method: GET
  name: get-equipment-makemodelserial-make-model-serialn
  path: /equipment/makeModelSerial/{make}/{model}/{serialNumber}/faults/{startDateUTC}/{endDateUTC}/{pageNumber}
- description: Get location data
  method: GET
  name: get-equipment-makemodelserial-make-model-serialn
  path: /equipment/makeModelSerial/{make}/{model}/{serialNumber}/locations/{startDateUTC}/{endDateUTC}/{pageNumber}
- description: CAT Get switch status
  method: GET
  name: get-equipment-makemodelserial-make-model-serialn
  path: /equipment/makeModelSerial/{make}/{model}/{serialNumber}/switchStatus/{startDateUTC}/{endDateUTC}/{pageNumber}
- description: CAT Get fuel remaining ratio
  method: GET
  name: get-equipment-makemodelserial-make-model-serialn
  path: /equipment/makeModelSerial/{make}/{model}/{serialNumber}/fuelRemainingRatio/{startDateUTC}/{endDateUTC}/{pageNumber}
personas: []
provider_name: CAT
provider_slug: cat
search_terms:
- cat get fuel remaining ratio
- construction
- get pagenumber
- telematics
- mining
- manufacturing
- heavy equipment
- cat get switch status
- get location data
- cat get fleet snapshot
- cat get fault codes
- cat
- api
- cat get equipment snapshot
- engines
- equipment
- get equipment makemodelserial make model serialn
- locomotives
slug: cat-capability
source_filename: cat-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: CAT Caterpillar Telematics API\n  description: API for Caterpillar-to-dealer data transfer\n  tags:\n  - Cat\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: cat\n    baseUri: https://services.cat.com/telematics/iso15143\n    description: CAT Caterpillar Telematics API HTTP API.\n    resources:\n    - name: pagenumber\n      path: /{pageNumber}\n      operations:\n      - name: get-pagenumber\n        method: GET\n        description: CAT Get fleet snapshot\n        inputParameters:\n        - name: pageNumber\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment-makemodelserial-make-model-serialnumbe\n      path: /equipment/makeModelSerial/{make}/{model}/{serialNumber}\n      operations:\n      - name:\
  \ get-equipment-makemodelserial-make-model-serialn\n        method: GET\n        description: CAT Get equipment snapshot\n        inputParameters:\n        - name: make\n          in: path\n          type: string\n          required: true\n        - name: model\n          in: path\n          type: string\n          required: true\n        - name: serialNumber\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment-makemodelserial-make-model-serialnumbe\n      path: /equipment/makeModelSerial/{make}/{model}/{serialNumber}/faults/{startDateUTC}/{endDateUTC}/{pageNumber}\n      operations:\n      - name: get-equipment-makemodelserial-make-model-serialn\n        method: GET\n        description: CAT Get fault codes\n        inputParameters:\n        - name: make\n          in: path\n          type: string\n          required: true\n\
  \        - name: model\n          in: path\n          type: string\n          required: true\n        - name: serialNumber\n          in: path\n          type: string\n          required: true\n        - name: startDateUTC\n          in: path\n          type: string\n          required: true\n        - name: endDateUTC\n          in: path\n          type: string\n          required: true\n        - name: pageNumber\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment-makemodelserial-make-model-serialnumbe\n      path: /equipment/makeModelSerial/{make}/{model}/{serialNumber}/locations/{startDateUTC}/{endDateUTC}/{pageNumber}\n      operations:\n      - name: get-equipment-makemodelserial-make-model-serialn\n        method: GET\n        description: Get location data\n        inputParameters:\n        - name: make\n      \
  \    in: path\n          type: string\n          required: true\n        - name: model\n          in: path\n          type: string\n          required: true\n        - name: serialNumber\n          in: path\n          type: string\n          required: true\n        - name: startDateUTC\n          in: path\n          type: string\n          required: true\n        - name: endDateUTC\n          in: path\n          type: string\n          required: true\n        - name: pageNumber\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment-makemodelserial-make-model-serialnumbe\n      path: /equipment/makeModelSerial/{make}/{model}/{serialNumber}/switchStatus/{startDateUTC}/{endDateUTC}/{pageNumber}\n      operations:\n      - name: get-equipment-makemodelserial-make-model-serialn\n        method: GET\n        description: CAT Get\
  \ switch status\n        inputParameters:\n        - name: make\n          in: path\n          type: string\n          required: true\n        - name: model\n          in: path\n          type: string\n          required: true\n        - name: serialNumber\n          in: path\n          type: string\n          required: true\n        - name: startDateUTC\n          in: path\n          type: string\n          required: true\n        - name: endDateUTC\n          in: path\n          type: string\n          required: true\n        - name: pageNumber\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment-makemodelserial-make-model-serialnumbe\n      path: /equipment/makeModelSerial/{make}/{model}/{serialNumber}/fuelRemainingRatio/{startDateUTC}/{endDateUTC}/{pageNumber}\n      operations:\n      - name: get-equipment-makemodelserial-make-model-serialn\n\
  \        method: GET\n        description: CAT Get fuel remaining ratio\n        inputParameters:\n        - name: make\n          in: path\n          type: string\n          required: true\n        - name: model\n          in: path\n          type: string\n          required: true\n        - name: serialNumber\n          in: path\n          type: string\n          required: true\n        - name: startDateUTC\n          in: path\n          type: string\n          required: true\n        - name: endDateUTC\n          in: path\n          type: string\n          required: true\n        - name: pageNumber\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cat-rest\n    description: REST adapter for CAT Caterpillar Telematics API.\n    resources:\n    - path: /{pageNumber}\n      name: get-pagenumber\n\
  \      operations:\n      - method: GET\n        name: get-pagenumber\n        description: CAT Get fleet snapshot\n        call: cat.get-pagenumber\n        with:\n          pageNumber: rest.pageNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /equipment/makeModelSerial/{make}/{model}/{serialNumber}\n      name: get-equipment-makemodelserial-make-model-serialn\n      operations:\n      - method: GET\n        name: get-equipment-makemodelserial-make-model-serialn\n        description: CAT Get equipment snapshot\n        call: cat.get-equipment-makemodelserial-make-model-serialn\n        with:\n          make: rest.make\n          model: rest.model\n          serialNumber: rest.serialNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /equipment/makeModelSerial/{make}/{model}/{serialNumber}/faults/{startDateUTC}/{endDateUTC}/{pageNumber}\n      name: get-equipment-makemodelserial-make-model-serialn\n\
  \      operations:\n      - method: GET\n        name: get-equipment-makemodelserial-make-model-serialn\n        description: CAT Get fault codes\n        call: cat.get-equipment-makemodelserial-make-model-serialn\n        with:\n          make: rest.make\n          model: rest.model\n          serialNumber: rest.serialNumber\n          startDateUTC: rest.startDateUTC\n          endDateUTC: rest.endDateUTC\n          pageNumber: rest.pageNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /equipment/makeModelSerial/{make}/{model}/{serialNumber}/locations/{startDateUTC}/{endDateUTC}/{pageNumber}\n      name: get-equipment-makemodelserial-make-model-serialn\n      operations:\n      - method: GET\n        name: get-equipment-makemodelserial-make-model-serialn\n        description: Get location data\n        call: cat.get-equipment-makemodelserial-make-model-serialn\n        with:\n          make: rest.make\n          model: rest.model\n         \
  \ serialNumber: rest.serialNumber\n          startDateUTC: rest.startDateUTC\n          endDateUTC: rest.endDateUTC\n          pageNumber: rest.pageNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /equipment/makeModelSerial/{make}/{model}/{serialNumber}/switchStatus/{startDateUTC}/{endDateUTC}/{pageNumber}\n      name: get-equipment-makemodelserial-make-model-serialn\n      operations:\n      - method: GET\n        name: get-equipment-makemodelserial-make-model-serialn\n        description: CAT Get switch status\n        call: cat.get-equipment-makemodelserial-make-model-serialn\n        with:\n          make: rest.make\n          model: rest.model\n          serialNumber: rest.serialNumber\n          startDateUTC: rest.startDateUTC\n          endDateUTC: rest.endDateUTC\n          pageNumber: rest.pageNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /equipment/makeModelSerial/{make}/{model}/{serialNumber}/fuelRemainingRatio/{startDateUTC}/{endDateUTC}/{pageNumber}\n\
  \      name: get-equipment-makemodelserial-make-model-serialn\n      operations:\n      - method: GET\n        name: get-equipment-makemodelserial-make-model-serialn\n        description: CAT Get fuel remaining ratio\n        call: cat.get-equipment-makemodelserial-make-model-serialn\n        with:\n          make: rest.make\n          model: rest.model\n          serialNumber: rest.serialNumber\n          startDateUTC: rest.startDateUTC\n          endDateUTC: rest.endDateUTC\n          pageNumber: rest.pageNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cat-mcp\n    transport: http\n    description: MCP adapter for CAT Caterpillar Telematics API for AI agent use.\n    tools:\n    - name: get-pagenumber\n      description: CAT Get fleet snapshot\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cat.get-pagenumber\n      with:\n        pageNumber: tools.pageNumber\n\
  \      inputParameters:\n      - name: pageNumber\n        type: integer\n        description: pageNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-equipment-makemodelserial-make-model-serialn\n      description: CAT Get equipment snapshot\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cat.get-equipment-makemodelserial-make-model-serialn\n      with:\n        make: tools.make\n        model: tools.model\n        serialNumber: tools.serialNumber\n      inputParameters:\n      - name: make\n        type: string\n        description: make\n        required: true\n      - name: model\n        type: string\n        description: model\n        required: true\n      - name: serialNumber\n        type: string\n        description: serialNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-equipment-makemodelserial-make-model-serialn\n\
  \      description: CAT Get fault codes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cat.get-equipment-makemodelserial-make-model-serialn\n      with:\n        make: tools.make\n        model: tools.model\n        serialNumber: tools.serialNumber\n        startDateUTC: tools.startDateUTC\n        endDateUTC: tools.endDateUTC\n        pageNumber: tools.pageNumber\n      inputParameters:\n      - name: make\n        type: string\n        description: make\n        required: true\n      - name: model\n        type: string\n        description: model\n        required: true\n      - name: serialNumber\n        type: string\n        description: serialNumber\n        required: true\n      - name: startDateUTC\n        type: string\n        description: startDateUTC\n        required: true\n      - name: endDateUTC\n        type: string\n        description: endDateUTC\n        required: true\n      - name: pageNumber\n        type:\
  \ integer\n        description: pageNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-equipment-makemodelserial-make-model-serialn\n      description: Get location data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cat.get-equipment-makemodelserial-make-model-serialn\n      with:\n        make: tools.make\n        model: tools.model\n        serialNumber: tools.serialNumber\n        startDateUTC: tools.startDateUTC\n        endDateUTC: tools.endDateUTC\n        pageNumber: tools.pageNumber\n      inputParameters:\n      - name: make\n        type: string\n        description: make\n        required: true\n      - name: model\n        type: string\n        description: model\n        required: true\n      - name: serialNumber\n        type: string\n        description: serialNumber\n        required: true\n      - name: startDateUTC\n        type: string\n       \
  \ description: startDateUTC\n        required: true\n      - name: endDateUTC\n        type: string\n        description: endDateUTC\n        required: true\n      - name: pageNumber\n        type: integer\n        description: pageNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-equipment-makemodelserial-make-model-serialn\n      description: CAT Get switch status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cat.get-equipment-makemodelserial-make-model-serialn\n      with:\n        make: tools.make\n        model: tools.model\n        serialNumber: tools.serialNumber\n        startDateUTC: tools.startDateUTC\n        endDateUTC: tools.endDateUTC\n        pageNumber: tools.pageNumber\n      inputParameters:\n      - name: make\n        type: string\n        description: make\n        required: true\n      - name: model\n        type: string\n        description:\
  \ model\n        required: true\n      - name: serialNumber\n        type: string\n        description: serialNumber\n        required: true\n      - name: startDateUTC\n        type: string\n        description: startDateUTC\n        required: true\n      - name: endDateUTC\n        type: string\n        description: endDateUTC\n        required: true\n      - name: pageNumber\n        type: integer\n        description: pageNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-equipment-makemodelserial-make-model-serialn\n      description: CAT Get fuel remaining ratio\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cat.get-equipment-makemodelserial-make-model-serialn\n      with:\n        make: tools.make\n        model: tools.model\n        serialNumber: tools.serialNumber\n        startDateUTC: tools.startDateUTC\n        endDateUTC: tools.endDateUTC\n        pageNumber:\
  \ tools.pageNumber\n      inputParameters:\n      - name: make\n        type: string\n        description: make\n        required: true\n      - name: model\n        type: string\n        description: model\n        required: true\n      - name: serialNumber\n        type: string\n        description: serialNumber\n        required: true\n      - name: startDateUTC\n        type: string\n        description: startDateUTC\n        required: true\n      - name: endDateUTC\n        type: string\n        description: endDateUTC\n        required: true\n      - name: pageNumber\n        type: integer\n        description: pageNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cat/refs/heads/main/capabilities/cat-capability.yaml
tags:
- Cat
- API
tools:
- description: CAT Get fleet snapshot
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-pagenumber
- description: CAT Get equipment snapshot
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-equipment-makemodelserial-make-model-serialn
- description: CAT Get fault codes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-equipment-makemodelserial-make-model-serialn
- description: Get location data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-equipment-makemodelserial-make-model-serialn
- description: CAT Get switch status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-equipment-makemodelserial-make-model-serialn
- description: CAT Get fuel remaining ratio
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-equipment-makemodelserial-make-model-serialn
---
