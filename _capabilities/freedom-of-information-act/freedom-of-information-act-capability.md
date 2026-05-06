---
categories: []
consumed_apis: []
description: Public APIs published by FOIA.gov, including the Agency Components API (Drupal JSON:API) for browsing federal agencies and their FOIA components, and the Annual Report XML API for retrieving an agency's FOIA annual report. A separate Agency API specification defines how the FOIA.gov portal submits requests to participating agencies.
layout: capability
name: Freedom of Information Act (FOIA) API
operations:
- description: List agency components
  method: GET
  name: listagencycomponents
  path: /api/agency_components
- description: Get agency component
  method: GET
  name: getagencycomponent
  path: /api/agency_components/{id}
- description: Get an agency component's request form
  method: GET
  name: getagencycomponentrequestform
  path: /api/agency_components/{id}/request_form
- description: Get an agency annual FOIA report
  method: GET
  name: getannualreportxml
  path: /api/annual-report-xml/{agencyAbbreviation}/{year}
- description: Submit a FOIA request to an agency component
  method: POST
  name: submitagencyrequest
  path: /components/{id}/requests/
personas: []
provider_name: Freedom of Information Act
provider_slug: freedom-of-information-act
search_terms:
- freedom
- getagencycomponentrequestform
- submit a foia request to an agency component
- federal government
- transparency
- act
- information
- listagencycomponents
- get an agency annual foia report
- api
- list agency components
- get an agency component's request form
- getannualreportxml
- of
- submitagencyrequest
- get agency component
- foia
- getagencycomponent
slug: freedom-of-information-act-capability
source_filename: freedom-of-information-act-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Freedom of Information Act (FOIA) API\n  description: Public APIs published by FOIA.gov, including the Agency Components API (Drupal JSON:API) for browsing federal\n    agencies and their FOIA components, and the Annual Report XML API for retrieving an agency's FOIA annual report. A separate\n    Agency API specification defines how the FOIA.gov portal submits requests to participating agencies.\n  tags:\n  - Freedom\n  - Of\n  - Information\n  - Act\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: freedom-of-information-act\n    baseUri: https://api.foia.gov\n    description: Freedom of Information Act (FOIA) API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{FREEDOM_OF_INFORMATION_ACT_TOKEN}}'\n    resources:\n    - name: api-agency-components\n      path: /api/agency_components\n      operations:\n     \
  \ - name: listagencycomponents\n        method: GET\n        description: List agency components\n        inputParameters:\n        - name: fields[agency_component]\n          in: query\n          type: string\n          description: Sparse fieldset for agency_component.\n        - name: fields[agency]\n          in: query\n          type: string\n          description: Sparse fieldset for agency.\n        - name: include\n          in: query\n          type: string\n          description: Related resources to include (e.g., agency).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agency-components-id\n      path: /api/agency_components/{id}\n      operations:\n      - name: getagencycomponent\n        method: GET\n        description: Get agency component\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agency-components-id-request-form\n      path: /api/agency_components/{id}/request_form\n      operations:\n      - name: getagencycomponentrequestform\n        method: GET\n        description: Get an agency component's request form\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-annual-report-xml-agencyabbreviation-year\n      path: /api/annual-report-xml/{agencyAbbreviation}/{year}\n      operations:\n      - name: getannualreportxml\n        method: GET\n        description: Get an agency annual FOIA report\n        inputParameters:\n        - name: agencyAbbreviation\n          in: path\n          type: string\n          required: true\n        - name: year\n\
  \          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: components-id-requests\n      path: /components/{id}/requests/\n      operations:\n      - name: submitagencyrequest\n        method: POST\n        description: Submit a FOIA request to an agency component\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier for the agency component.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: freedom-of-information-act-rest\n    description: REST adapter for Freedom of Information Act (FOIA) API.\n    resources:\n    - path: /api/agency_components\n      name: listagencycomponents\n      operations:\n\
  \      - method: GET\n        name: listagencycomponents\n        description: List agency components\n        call: freedom-of-information-act.listagencycomponents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/agency_components/{id}\n      name: getagencycomponent\n      operations:\n      - method: GET\n        name: getagencycomponent\n        description: Get agency component\n        call: freedom-of-information-act.getagencycomponent\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/agency_components/{id}/request_form\n      name: getagencycomponentrequestform\n      operations:\n      - method: GET\n        name: getagencycomponentrequestform\n        description: Get an agency component's request form\n        call: freedom-of-information-act.getagencycomponentrequestform\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /api/annual-report-xml/{agencyAbbreviation}/{year}\n      name: getannualreportxml\n      operations:\n      - method: GET\n        name: getannualreportxml\n        description: Get an agency annual FOIA report\n        call: freedom-of-information-act.getannualreportxml\n        with:\n          agencyAbbreviation: rest.agencyAbbreviation\n          year: rest.year\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /components/{id}/requests/\n      name: submitagencyrequest\n      operations:\n      - method: POST\n        name: submitagencyrequest\n        description: Submit a FOIA request to an agency component\n        call: freedom-of-information-act.submitagencyrequest\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: freedom-of-information-act-mcp\n    transport: http\n    description: MCP adapter for\
  \ Freedom of Information Act (FOIA) API for AI agent use.\n    tools:\n    - name: listagencycomponents\n      description: List agency components\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: freedom-of-information-act.listagencycomponents\n      with:\n        fields[agency_component]: tools.fields[agency_component]\n        fields[agency]: tools.fields[agency]\n        include: tools.include\n      inputParameters:\n      - name: fields[agency_component]\n        type: string\n        description: Sparse fieldset for agency_component.\n      - name: fields[agency]\n        type: string\n        description: Sparse fieldset for agency.\n      - name: include\n        type: string\n        description: Related resources to include (e.g., agency).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getagencycomponent\n      description: Get agency component\n      hints:\n        readOnly: true\n  \
  \      destructive: false\n        idempotent: true\n      call: freedom-of-information-act.getagencycomponent\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getagencycomponentrequestform\n      description: Get an agency component's request form\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: freedom-of-information-act.getagencycomponentrequestform\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getannualreportxml\n      description: Get an agency annual FOIA report\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: freedom-of-information-act.getannualreportxml\n\
  \      with:\n        agencyAbbreviation: tools.agencyAbbreviation\n        year: tools.year\n      inputParameters:\n      - name: agencyAbbreviation\n        type: string\n        description: agencyAbbreviation\n        required: true\n      - name: year\n        type: integer\n        description: year\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submitagencyrequest\n      description: Submit a FOIA request to an agency component\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: freedom-of-information-act.submitagencyrequest\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: Unique identifier for the agency component.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FREEDOM_OF_INFORMATION_ACT_TOKEN: FREEDOM_OF_INFORMATION_ACT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/freedom-of-information-act/refs/heads/main/capabilities/freedom-of-information-act-capability.yaml
tags:
- Freedom
- Of
- Information
- Act
- API
tools:
- description: List agency components
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listagencycomponents
- description: Get agency component
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getagencycomponent
- description: Get an agency component's request form
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getagencycomponentrequestform
- description: Get an agency annual FOIA report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getannualreportxml
- description: Submit a FOIA request to an agency component
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitagencyrequest
---
