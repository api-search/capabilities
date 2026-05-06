---
categories: []
consumed_apis: []
description: The Import.io API (v2.0) provides programmatic access to create, manage, and run web data extractors, retrieve crawl run results, and manage reports. Everything available in the Import.io UI can be accomplished via the API, including scheduling extractions, managing data pipelines, and exporting data in JSON, CSV, or Excel formats. Authenticated extraction is supported for data behind login screens. Authentication is performed by passing your API key as the `_apikey` query parameter on every request. You can find your API key in the Import.io dashboard under User Settings.
layout: capability
name: Import.io API
operations:
- description: Get current user
  method: GET
  name: getcurrentuser
  path: /users/current
- description: Get current user subscription
  method: GET
  name: getcurrentusersubscription
  path: /users/current/subscription
- description: List extractors
  method: GET
  name: listextractors
  path: /extractors/
- description: Get extractor
  method: GET
  name: getextractor
  path: /extractors/{extractorId}
- description: Archive extractor
  method: DELETE
  name: deleteextractor
  path: /extractors/{extractorId}
- description: Get extractor inputs
  method: GET
  name: getextractorinputs
  path: /extractors/{extractorId}/inputs
- description: Update extractor inputs
  method: PUT
  name: updateextractorinputs
  path: /extractors/{extractorId}/inputs
- description: Start extractor
  method: POST
  name: startextractor
  path: /extractors/{extractorId}/start
- description: Stop extractor
  method: POST
  name: stopextractor
  path: /extractors/{extractorId}/stop
- description: Duplicate extractor
  method: POST
  name: duplicateextractor
  path: /extractors/{extractorId}/duplicate
- description: Update extractor credentials
  method: POST
  name: updateextractorcredentials
  path: /extractors/{extractorId}/credentials
- description: List crawl runs
  method: GET
  name: listcrawlruns
  path: /crawlruns/
- description: Get crawl run
  method: GET
  name: getcrawlrun
  path: /crawlruns/{crawlrunId}
- description: Get crawl run results file
  method: GET
  name: getcrawlrunfile
  path: /crawlruns/{crawlrunId}/{fileType}
- description: List reports
  method: GET
  name: listreports
  path: /reports/
- description: Get report
  method: GET
  name: getreport
  path: /reports/{reportId}
- description: Delete report
  method: DELETE
  name: deletereport
  path: /reports/{reportId}
- description: Start report
  method: POST
  name: startreport
  path: /reports/{reportId}/start
- description: List report runs for a report
  method: GET
  name: listreportrunsforreport
  path: /reports/{reportId}/reportruns
- description: List report runs
  method: GET
  name: listreportruns
  path: /reportruns/
- description: Get report run
  method: GET
  name: getreportrun
  path: /reportruns/{reportRunId}
- description: Get report run results file
  method: GET
  name: getreportrunfile
  path: /reportruns/{reportRunId}/{fileType}
personas: []
provider_name: Import.io
provider_slug: import-io
search_terms:
- getcrawlrun
- getreport
- deletereport
- start report
- getcurrentuser
- data integration
- list extractors
- getcrawlrunfile
- get report run
- startextractor
- get report
- list report runs
- get current user subscription
- duplicateextractor
- list report runs for a report
- data extraction
- io
- get crawl run results file
- listreportrunsforreport
- start extractor
- get report run results file
- list reports
- web scraping
- import
- getreportrunfile
- getextractor
- deleteextractor
- data aggregation
- list crawl runs
- duplicate extractor
- stopextractor
- api
- updateextractorcredentials
- pricing intelligence
- getcurrentusersubscription
- getextractorinputs
- get crawl run
- startreport
- get current user
- stop extractor
- update extractor inputs
- listcrawlruns
- listreports
- listreportruns
- get extractor
- delete report
- update extractor credentials
- updateextractorinputs
- listextractors
- archive extractor
- getreportrun
- get extractor inputs
slug: import-io-capability
source_filename: import-io-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Import.io API\n  description: The Import.io API (v2.0) provides programmatic access to create, manage, and run web data extractors, retrieve\n    crawl run results, and manage reports. Everything available in the Import.io UI can be accomplished via the API, including\n    scheduling extractions, managing data pipelines, and exporting data in JSON, CSV, or Excel formats. Authenticated extraction\n    is supported for data behind login screens. Authentication is performed by passing your API key as the `_apikey` query\n    parameter on every request. You can find your API key in the Import.io dashboard under User Settings.\n  tags:\n  - Import\n  - Io\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: import-io\n    baseUri: https://api.import.io\n    description: Import.io API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: _apikey\n   \
  \   value: '{{IMPORT_IO_TOKEN}}'\n    resources:\n    - name: users-current\n      path: /users/current\n      operations:\n      - name: getcurrentuser\n        method: GET\n        description: Get current user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-current-subscription\n      path: /users/current/subscription\n      operations:\n      - name: getcurrentusersubscription\n        method: GET\n        description: Get current user subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extractors\n      path: /extractors/\n      operations:\n      - name: listextractors\n        method: GET\n        description: List extractors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extractors-extractorid\n\
  \      path: /extractors/{extractorId}\n      operations:\n      - name: getextractor\n        method: GET\n        description: Get extractor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteextractor\n        method: DELETE\n        description: Archive extractor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extractors-extractorid-inputs\n      path: /extractors/{extractorId}/inputs\n      operations:\n      - name: getextractorinputs\n        method: GET\n        description: Get extractor inputs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateextractorinputs\n        method: PUT\n        description: Update extractor inputs\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: extractors-extractorid-start\n      path: /extractors/{extractorId}/start\n      operations:\n      - name: startextractor\n        method: POST\n        description: Start extractor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extractors-extractorid-stop\n      path: /extractors/{extractorId}/stop\n      operations:\n      - name: stopextractor\n        method: POST\n        description: Stop extractor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extractors-extractorid-duplicate\n      path: /extractors/{extractorId}/duplicate\n      operations:\n      - name: duplicateextractor\n        method: POST\n        description: Duplicate extractor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n    - name: extractors-extractorid-credentials\n      path: /extractors/{extractorId}/credentials\n      operations:\n      - name: updateextractorcredentials\n        method: POST\n        description: Update extractor credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crawlruns\n      path: /crawlruns/\n      operations:\n      - name: listcrawlruns\n        method: GET\n        description: List crawl runs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crawlruns-crawlrunid\n      path: /crawlruns/{crawlrunId}\n      operations:\n      - name: getcrawlrun\n        method: GET\n        description: Get crawl run\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crawlruns-crawlrunid-filetype\n\
  \      path: /crawlruns/{crawlrunId}/{fileType}\n      operations:\n      - name: getcrawlrunfile\n        method: GET\n        description: Get crawl run results file\n        inputParameters:\n        - name: fileType\n          in: path\n          type: string\n          required: true\n          description: The file type to download.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /reports/\n      operations:\n      - name: listreports\n        method: GET\n        description: List reports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports-reportid\n      path: /reports/{reportId}\n      operations:\n      - name: getreport\n        method: GET\n        description: Get report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: deletereport\n        method: DELETE\n        description: Delete report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports-reportid-start\n      path: /reports/{reportId}/start\n      operations:\n      - name: startreport\n        method: POST\n        description: Start report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports-reportid-reportruns\n      path: /reports/{reportId}/reportruns\n      operations:\n      - name: listreportrunsforreport\n        method: GET\n        description: List report runs for a report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reportruns\n      path: /reportruns/\n      operations:\n      - name: listreportruns\n      \
  \  method: GET\n        description: List report runs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reportruns-reportrunid\n      path: /reportruns/{reportRunId}\n      operations:\n      - name: getreportrun\n        method: GET\n        description: Get report run\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reportruns-reportrunid-filetype\n      path: /reportruns/{reportRunId}/{fileType}\n      operations:\n      - name: getreportrunfile\n        method: GET\n        description: Get report run results file\n        inputParameters:\n        - name: fileType\n          in: path\n          type: string\n          required: true\n          description: The file type to download.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: import-io-rest\n    description: REST adapter for Import.io API.\n    resources:\n    - path: /users/current\n      name: getcurrentuser\n      operations:\n      - method: GET\n        name: getcurrentuser\n        description: Get current user\n        call: import-io.getcurrentuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/current/subscription\n      name: getcurrentusersubscription\n      operations:\n      - method: GET\n        name: getcurrentusersubscription\n        description: Get current user subscription\n        call: import-io.getcurrentusersubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /extractors/\n      name: listextractors\n      operations:\n      - method: GET\n        name: listextractors\n        description: List extractors\n        call: import-io.listextractors\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n    - path: /extractors/{extractorId}\n      name: getextractor\n      operations:\n      - method: GET\n        name: getextractor\n        description: Get extractor\n        call: import-io.getextractor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /extractors/{extractorId}\n      name: deleteextractor\n      operations:\n      - method: DELETE\n        name: deleteextractor\n        description: Archive extractor\n        call: import-io.deleteextractor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /extractors/{extractorId}/inputs\n      name: getextractorinputs\n      operations:\n      - method: GET\n        name: getextractorinputs\n        description: Get extractor inputs\n        call: import-io.getextractorinputs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /extractors/{extractorId}/inputs\n      name: updateextractorinputs\n\
  \      operations:\n      - method: PUT\n        name: updateextractorinputs\n        description: Update extractor inputs\n        call: import-io.updateextractorinputs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /extractors/{extractorId}/start\n      name: startextractor\n      operations:\n      - method: POST\n        name: startextractor\n        description: Start extractor\n        call: import-io.startextractor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /extractors/{extractorId}/stop\n      name: stopextractor\n      operations:\n      - method: POST\n        name: stopextractor\n        description: Stop extractor\n        call: import-io.stopextractor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /extractors/{extractorId}/duplicate\n      name: duplicateextractor\n      operations:\n      - method: POST\n        name: duplicateextractor\n        description:\
  \ Duplicate extractor\n        call: import-io.duplicateextractor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /extractors/{extractorId}/credentials\n      name: updateextractorcredentials\n      operations:\n      - method: POST\n        name: updateextractorcredentials\n        description: Update extractor credentials\n        call: import-io.updateextractorcredentials\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /crawlruns/\n      name: listcrawlruns\n      operations:\n      - method: GET\n        name: listcrawlruns\n        description: List crawl runs\n        call: import-io.listcrawlruns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /crawlruns/{crawlrunId}\n      name: getcrawlrun\n      operations:\n      - method: GET\n        name: getcrawlrun\n        description: Get crawl run\n        call: import-io.getcrawlrun\n        outputParameters:\n      \
  \  - type: object\n          mapping: $.\n    - path: /crawlruns/{crawlrunId}/{fileType}\n      name: getcrawlrunfile\n      operations:\n      - method: GET\n        name: getcrawlrunfile\n        description: Get crawl run results file\n        call: import-io.getcrawlrunfile\n        with:\n          fileType: rest.fileType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reports/\n      name: listreports\n      operations:\n      - method: GET\n        name: listreports\n        description: List reports\n        call: import-io.listreports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reports/{reportId}\n      name: getreport\n      operations:\n      - method: GET\n        name: getreport\n        description: Get report\n        call: import-io.getreport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reports/{reportId}\n      name: deletereport\n      operations:\n\
  \      - method: DELETE\n        name: deletereport\n        description: Delete report\n        call: import-io.deletereport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reports/{reportId}/start\n      name: startreport\n      operations:\n      - method: POST\n        name: startreport\n        description: Start report\n        call: import-io.startreport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reports/{reportId}/reportruns\n      name: listreportrunsforreport\n      operations:\n      - method: GET\n        name: listreportrunsforreport\n        description: List report runs for a report\n        call: import-io.listreportrunsforreport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reportruns/\n      name: listreportruns\n      operations:\n      - method: GET\n        name: listreportruns\n        description: List report runs\n        call: import-io.listreportruns\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reportruns/{reportRunId}\n      name: getreportrun\n      operations:\n      - method: GET\n        name: getreportrun\n        description: Get report run\n        call: import-io.getreportrun\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reportruns/{reportRunId}/{fileType}\n      name: getreportrunfile\n      operations:\n      - method: GET\n        name: getreportrunfile\n        description: Get report run results file\n        call: import-io.getreportrunfile\n        with:\n          fileType: rest.fileType\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: import-io-mcp\n    transport: http\n    description: MCP adapter for Import.io API for AI agent use.\n    tools:\n    - name: getcurrentuser\n      description: Get current user\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: import-io.getcurrentuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcurrentusersubscription\n      description: Get current user subscription\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: import-io.getcurrentusersubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listextractors\n      description: List extractors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: import-io.listextractors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getextractor\n      description: Get extractor\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: import-io.getextractor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteextractor\n      description:\
  \ Archive extractor\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: import-io.deleteextractor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getextractorinputs\n      description: Get extractor inputs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: import-io.getextractorinputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateextractorinputs\n      description: Update extractor inputs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: import-io.updateextractorinputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startextractor\n      description: Start extractor\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: import-io.startextractor\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: stopextractor\n      description: Stop extractor\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: import-io.stopextractor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: duplicateextractor\n      description: Duplicate extractor\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: import-io.duplicateextractor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateextractorcredentials\n      description: Update extractor credentials\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: import-io.updateextractorcredentials\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcrawlruns\n      description: List crawl runs\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: import-io.listcrawlruns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcrawlrun\n      description: Get crawl run\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: import-io.getcrawlrun\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcrawlrunfile\n      description: Get crawl run results file\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: import-io.getcrawlrunfile\n      with:\n        fileType: tools.fileType\n      inputParameters:\n      - name: fileType\n        type: string\n        description: The file type to download.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listreports\n      description: List reports\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: import-io.listreports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getreport\n      description: Get report\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: import-io.getreport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletereport\n      description: Delete report\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: import-io.deletereport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startreport\n      description: Start report\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: import-io.startreport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listreportrunsforreport\n      description: List report runs for a report\n      hints:\n        readOnly: true\n     \
  \   destructive: false\n        idempotent: true\n      call: import-io.listreportrunsforreport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listreportruns\n      description: List report runs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: import-io.listreportruns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getreportrun\n      description: Get report run\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: import-io.getreportrun\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getreportrunfile\n      description: Get report run results file\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: import-io.getreportrunfile\n      with:\n        fileType: tools.fileType\n      inputParameters:\n      - name: fileType\n        type:\
  \ string\n        description: The file type to download.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    IMPORT_IO_TOKEN: IMPORT_IO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/import-io/refs/heads/main/capabilities/import-io-capability.yaml
tags:
- Import
- Io
- API
tools:
- description: Get current user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentuser
- description: Get current user subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentusersubscription
- description: List extractors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listextractors
- description: Get extractor
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getextractor
- description: Archive extractor
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteextractor
- description: Get extractor inputs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getextractorinputs
- description: Update extractor inputs
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateextractorinputs
- description: Start extractor
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startextractor
- description: Stop extractor
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stopextractor
- description: Duplicate extractor
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: duplicateextractor
- description: Update extractor credentials
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateextractorcredentials
- description: List crawl runs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcrawlruns
- description: Get crawl run
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcrawlrun
- description: Get crawl run results file
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcrawlrunfile
- description: List reports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreports
- description: Get report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreport
- description: Delete report
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletereport
- description: Start report
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startreport
- description: List report runs for a report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreportrunsforreport
- description: List report runs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreportruns
- description: Get report run
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreportrun
- description: Get report run results file
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreportrunfile
---
