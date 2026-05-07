---
categories: []
consumed_apis: []
description: The CDISC Library API is a REST API that delivers CDISC standards metadata to software applications that automate standards-based processes. It uses linked data to provide access to SDTM, ADaM, and other clinical data standards. Responses are available in JSON, XML, ODM, CSV, and Excel formats. Access requires a CDISC Library account and an API key obtained from the CDISC Library API Management (APIM) Developer Portal.
layout: capability
name: CDISC Library API
operations:
- description: List all CDISC standards products
  method: GET
  name: listproducts
  path: /mdr/products
- description: List all SDTM standard versions
  method: GET
  name: listsdtmversions
  path: /mdr/sdtm
- description: Get SDTM standard by version
  method: GET
  name: getsdtmversion
  path: /mdr/sdtm/{version}
- description: List SDTM domain classes for a version
  method: GET
  name: listsdtmclasses
  path: /mdr/sdtm/{version}/classes
- description: List SDTM datasets (domains) for a version
  method: GET
  name: listsdtmdatasets
  path: /mdr/sdtm/{version}/datasets
- description: Get SDTM dataset (domain) specification
  method: GET
  name: getsdtmdataset
  path: /mdr/sdtm/{version}/datasets/{dataset}
- description: List all ADaM standard versions
  method: GET
  name: listadamversions
  path: /mdr/adam
- description: Get ADaM standard by version
  method: GET
  name: getadamversion
  path: /mdr/adam/{version}
- description: List all CDASH standard versions
  method: GET
  name: listcdashversions
  path: /mdr/cdash
- description: List CDISC Biomedical Concepts
  method: GET
  name: listbiomedicalconcepts
  path: /cosmos/v2/bc
- description: Get a specific Biomedical Concept
  method: GET
  name: getbiomedicalconcept
  path: /cosmos/v2/bc/{conceptId}
- description: List CDISC controlled terminology packages
  method: GET
  name: listterminologypackages
  path: /mdr/ct
- description: List codelists in a terminology package
  method: GET
  name: listcodelists
  path: /mdr/ct/{packageDate}/codelists
personas: []
provider_name: cdisc
provider_slug: cdisc
search_terms:
- listbiomedicalconcepts
- cdisc
- listcdashversions
- getbiomedicalconcept
- list cdisc controlled terminology packages
- getsdtmdataset
- list all cdash standard versions
- api
- list cdisc biomedical concepts
- get adam standard by version
- list all cdisc standards products
- getsdtmversion
- listsdtmversions
- get a specific biomedical concept
- list sdtm datasets (domains) for a version
- get sdtm standard by version
- list sdtm domain classes for a version
- list codelists in a terminology package
- listproducts
- list all adam standard versions
- listcodelists
- get sdtm dataset (domain) specification
- listterminologypackages
- listadamversions
- list all sdtm standard versions
- getadamversion
- listsdtmdatasets
- listsdtmclasses
slug: cdisc-capability
source_filename: cdisc-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: CDISC Library API\n  description: The CDISC Library API is a REST API that delivers CDISC standards metadata to software applications that automate\n    standards-based processes. It uses linked data to provide access to SDTM, ADaM, and other clinical data standards. Responses\n    are available in JSON, XML, ODM, CSV, and Excel formats. Access requires a CDISC Library account and an API key obtained\n    from the CDISC Library API Management (APIM) Developer Portal.\n  tags:\n  - Cdisc\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: cdisc\n    baseUri: https://library.cdisc.org/api\n    description: CDISC Library API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: api-key\n      value: '{{CDISC_TOKEN}}'\n    resources:\n    - name: mdr-products\n      path: /mdr/products\n      operations:\n      - name: listproducts\n        method:\
  \ GET\n        description: List all CDISC standards products\n        inputParameters:\n        - name: Accept\n          in: header\n          type: string\n          description: Response format (application/json, application/xml, text/csv)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mdr-sdtm\n      path: /mdr/sdtm\n      operations:\n      - name: listsdtmversions\n        method: GET\n        description: List all SDTM standard versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mdr-sdtm-version\n      path: /mdr/sdtm/{version}\n      operations:\n      - name: getsdtmversion\n        method: GET\n        description: Get SDTM standard by version\n        inputParameters:\n        - name: version\n          in: path\n          type: string\n          required: true\n          description: SDTM\
  \ version string (e.g., 3-3, 3-4, 2-0)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mdr-sdtm-version-classes\n      path: /mdr/sdtm/{version}/classes\n      operations:\n      - name: listsdtmclasses\n        method: GET\n        description: List SDTM domain classes for a version\n        inputParameters:\n        - name: version\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mdr-sdtm-version-datasets\n      path: /mdr/sdtm/{version}/datasets\n      operations:\n      - name: listsdtmdatasets\n        method: GET\n        description: List SDTM datasets (domains) for a version\n        inputParameters:\n        - name: version\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mdr-sdtm-version-datasets-dataset\n      path: /mdr/sdtm/{version}/datasets/{dataset}\n      operations:\n      - name: getsdtmdataset\n        method: GET\n        description: Get SDTM dataset (domain) specification\n        inputParameters:\n        - name: version\n          in: path\n          type: string\n          required: true\n        - name: dataset\n          in: path\n          type: string\n          required: true\n          description: SDTM domain abbreviation (e.g., AE, CM, DM)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mdr-adam\n      path: /mdr/adam\n      operations:\n      - name: listadamversions\n        method: GET\n        description: List all ADaM standard versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: mdr-adam-version\n      path: /mdr/adam/{version}\n      operations:\n      - name: getadamversion\n        method: GET\n        description: Get ADaM standard by version\n        inputParameters:\n        - name: version\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mdr-cdash\n      path: /mdr/cdash\n      operations:\n      - name: listcdashversions\n        method: GET\n        description: List all CDASH standard versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cosmos-v2-bc\n      path: /cosmos/v2/bc\n      operations:\n      - name: listbiomedicalconcepts\n        method: GET\n        description: List CDISC Biomedical Concepts\n        inputParameters:\n        - name: packageDate\n\
  \          in: query\n          type: string\n          description: Filter BCs by package release date (YYYY-MM-DD)\n        - name: page\n          in: query\n          type: integer\n        - name: pageSize\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cosmos-v2-bc-conceptid\n      path: /cosmos/v2/bc/{conceptId}\n      operations:\n      - name: getbiomedicalconcept\n        method: GET\n        description: Get a specific Biomedical Concept\n        inputParameters:\n        - name: conceptId\n          in: path\n          type: string\n          required: true\n          description: Biomedical Concept identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mdr-ct\n      path: /mdr/ct\n      operations:\n      - name: listterminologypackages\n    \
  \    method: GET\n        description: List CDISC controlled terminology packages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mdr-ct-packagedate-codelists\n      path: /mdr/ct/{packageDate}/codelists\n      operations:\n      - name: listcodelists\n        method: GET\n        description: List codelists in a terminology package\n        inputParameters:\n        - name: packageDate\n          in: path\n          type: string\n          required: true\n          description: Terminology package date (e.g., 2023-12-15)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cdisc-rest\n    description: REST adapter for CDISC Library API.\n    resources:\n    - path: /mdr/products\n      name: listproducts\n      operations:\n      - method: GET\n        name: listproducts\n\
  \        description: List all CDISC standards products\n        call: cdisc.listproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mdr/sdtm\n      name: listsdtmversions\n      operations:\n      - method: GET\n        name: listsdtmversions\n        description: List all SDTM standard versions\n        call: cdisc.listsdtmversions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mdr/sdtm/{version}\n      name: getsdtmversion\n      operations:\n      - method: GET\n        name: getsdtmversion\n        description: Get SDTM standard by version\n        call: cdisc.getsdtmversion\n        with:\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mdr/sdtm/{version}/classes\n      name: listsdtmclasses\n      operations:\n      - method: GET\n        name: listsdtmclasses\n        description: List SDTM domain classes for a version\n \
  \       call: cdisc.listsdtmclasses\n        with:\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mdr/sdtm/{version}/datasets\n      name: listsdtmdatasets\n      operations:\n      - method: GET\n        name: listsdtmdatasets\n        description: List SDTM datasets (domains) for a version\n        call: cdisc.listsdtmdatasets\n        with:\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mdr/sdtm/{version}/datasets/{dataset}\n      name: getsdtmdataset\n      operations:\n      - method: GET\n        name: getsdtmdataset\n        description: Get SDTM dataset (domain) specification\n        call: cdisc.getsdtmdataset\n        with:\n          version: rest.version\n          dataset: rest.dataset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mdr/adam\n      name: listadamversions\n      operations:\n\
  \      - method: GET\n        name: listadamversions\n        description: List all ADaM standard versions\n        call: cdisc.listadamversions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mdr/adam/{version}\n      name: getadamversion\n      operations:\n      - method: GET\n        name: getadamversion\n        description: Get ADaM standard by version\n        call: cdisc.getadamversion\n        with:\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mdr/cdash\n      name: listcdashversions\n      operations:\n      - method: GET\n        name: listcdashversions\n        description: List all CDASH standard versions\n        call: cdisc.listcdashversions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cosmos/v2/bc\n      name: listbiomedicalconcepts\n      operations:\n      - method: GET\n        name: listbiomedicalconcepts\n  \
  \      description: List CDISC Biomedical Concepts\n        call: cdisc.listbiomedicalconcepts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cosmos/v2/bc/{conceptId}\n      name: getbiomedicalconcept\n      operations:\n      - method: GET\n        name: getbiomedicalconcept\n        description: Get a specific Biomedical Concept\n        call: cdisc.getbiomedicalconcept\n        with:\n          conceptId: rest.conceptId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mdr/ct\n      name: listterminologypackages\n      operations:\n      - method: GET\n        name: listterminologypackages\n        description: List CDISC controlled terminology packages\n        call: cdisc.listterminologypackages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mdr/ct/{packageDate}/codelists\n      name: listcodelists\n      operations:\n      - method: GET\n        name: listcodelists\n\
  \        description: List codelists in a terminology package\n        call: cdisc.listcodelists\n        with:\n          packageDate: rest.packageDate\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cdisc-mcp\n    transport: http\n    description: MCP adapter for CDISC Library API for AI agent use.\n    tools:\n    - name: listproducts\n      description: List all CDISC standards products\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cdisc.listproducts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsdtmversions\n      description: List all SDTM standard versions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cdisc.listsdtmversions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsdtmversion\n      description: Get SDTM standard\
  \ by version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cdisc.getsdtmversion\n      with:\n        version: tools.version\n      inputParameters:\n      - name: version\n        type: string\n        description: SDTM version string (e.g., 3-3, 3-4, 2-0)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsdtmclasses\n      description: List SDTM domain classes for a version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cdisc.listsdtmclasses\n      with:\n        version: tools.version\n      inputParameters:\n      - name: version\n        type: string\n        description: version\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsdtmdatasets\n      description: List SDTM datasets (domains) for a version\n      hints:\n        readOnly: true\n       \
  \ destructive: false\n        idempotent: true\n      call: cdisc.listsdtmdatasets\n      with:\n        version: tools.version\n      inputParameters:\n      - name: version\n        type: string\n        description: version\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsdtmdataset\n      description: Get SDTM dataset (domain) specification\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cdisc.getsdtmdataset\n      with:\n        version: tools.version\n        dataset: tools.dataset\n      inputParameters:\n      - name: version\n        type: string\n        description: version\n        required: true\n      - name: dataset\n        type: string\n        description: SDTM domain abbreviation (e.g., AE, CM, DM)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listadamversions\n      description: List all ADaM\
  \ standard versions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cdisc.listadamversions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getadamversion\n      description: Get ADaM standard by version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cdisc.getadamversion\n      with:\n        version: tools.version\n      inputParameters:\n      - name: version\n        type: string\n        description: version\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcdashversions\n      description: List all CDASH standard versions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cdisc.listcdashversions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbiomedicalconcepts\n      description: List CDISC\
  \ Biomedical Concepts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cdisc.listbiomedicalconcepts\n      with:\n        packageDate: tools.packageDate\n        page: tools.page\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: packageDate\n        type: string\n        description: Filter BCs by package release date (YYYY-MM-DD)\n      - name: page\n        type: integer\n        description: page\n      - name: pageSize\n        type: integer\n        description: pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbiomedicalconcept\n      description: Get a specific Biomedical Concept\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cdisc.getbiomedicalconcept\n      with:\n        conceptId: tools.conceptId\n      inputParameters:\n      - name: conceptId\n        type: string\n        description: Biomedical\
  \ Concept identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listterminologypackages\n      description: List CDISC controlled terminology packages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cdisc.listterminologypackages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcodelists\n      description: List codelists in a terminology package\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cdisc.listcodelists\n      with:\n        packageDate: tools.packageDate\n      inputParameters:\n      - name: packageDate\n        type: string\n        description: Terminology package date (e.g., 2023-12-15)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CDISC_TOKEN: CDISC_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cdisc/refs/heads/main/capabilities/cdisc-capability.yaml
tags:
- Cdisc
- API
tools:
- description: List all CDISC standards products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproducts
- description: List all SDTM standard versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsdtmversions
- description: Get SDTM standard by version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsdtmversion
- description: List SDTM domain classes for a version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsdtmclasses
- description: List SDTM datasets (domains) for a version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsdtmdatasets
- description: Get SDTM dataset (domain) specification
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsdtmdataset
- description: List all ADaM standard versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listadamversions
- description: Get ADaM standard by version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getadamversion
- description: List all CDASH standard versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcdashversions
- description: List CDISC Biomedical Concepts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbiomedicalconcepts
- description: Get a specific Biomedical Concept
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbiomedicalconcept
- description: List CDISC controlled terminology packages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listterminologypackages
- description: List codelists in a terminology package
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcodelists
---
