---
categories: []
consumed_apis: []
description: Encompass Developer Connect is a REST API platform from ICE Mortgage Technology that allows developers to programmatically configure, customize, and administer loan information and resources for Encompass clients. The platform exposes APIs across loan manufacturing, loan pipeline management, product and pricing, compliance, documents and eFolder, loan data extracts, and loan folders. Authentication is handled with OAuth 2.0, and supports User Impersonation, API User (ISV Partner), Federated SAML SSO, and Multi-Factor Authentication.
layout: capability
name: Encompass Developer Connect API
operations:
- description: Encompass Developer Connect Issue an OAuth 2.0 access token
  method: POST
  name: issueaccesstoken
  path: /oauth2/v1/token
- description: Encompass Developer Connect Search the loan pipeline
  method: POST
  name: searchloanpipeline
  path: /loanPipeline
- description: Encompass Developer Connect Create a new loan
  method: POST
  name: createloan
  path: /loans
- description: Encompass Developer Connect Retrieve a loan
  method: GET
  name: getloan
  path: /loans/{loanId}
- description: Encompass Developer Connect Update a loan
  method: PATCH
  name: updateloan
  path: /loans/{loanId}
- description: Encompass Developer Connect Delete a loan
  method: DELETE
  name: deleteloan
  path: /loans/{loanId}
personas: []
provider_name: Encompass Developer Connect
provider_slug: encompass-developer-connect
search_terms:
- encompass developer connect issue an oauth 2.0 access token
- mortgage
- encompass developer connect search the loan pipeline
- loan origination
- connect
- api
- updateloan
- searchloanpipeline
- encompass developer connect update a loan
- lending
- encompass developer connect delete a loan
- ice mortgage technology
- issueaccesstoken
- deleteloan
- encompass developer connect retrieve a loan
- rest api
- createloan
- getloan
- developer
- encompass
- encompass developer connect create a new loan
slug: encompass-developer-connect-capability
source_filename: encompass-developer-connect-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Encompass Developer Connect API\n  description: Encompass Developer Connect is a REST API platform from ICE Mortgage Technology that allows developers to programmatically\n    configure, customize, and administer loan information and resources for Encompass clients. The platform exposes APIs across\n    loan manufacturing, loan pipeline management, product and pricing, compliance, documents and eFolder, loan data extracts,\n    and loan folders. Authentication is handled with OAuth 2.0, and supports User Impersonation, API User (ISV Partner), Federated\n    SAML SSO, and Multi-Factor Authentication.\n  tags:\n  - Encompass\n  - Developer\n  - Connect\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: encompass-developer-connect\n    baseUri: https://api.elliemae.com/encompass/v3\n    description: Encompass Developer Connect API HTTP API.\n    authentication:\n      type:\
  \ bearer\n      token: '{{ENCOMPASS_DEVELOPER_CONNECT_TOKEN}}'\n    resources:\n    - name: oauth2-v1-token\n      path: /oauth2/v1/token\n      operations:\n      - name: issueaccesstoken\n        method: POST\n        description: Encompass Developer Connect Issue an OAuth 2.0 access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loanpipeline\n      path: /loanPipeline\n      operations:\n      - name: searchloanpipeline\n        method: POST\n        description: Encompass Developer Connect Search the loan pipeline\n        inputParameters:\n        - name: cursorType\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loans\n      path: /loans\n      operations:\n      - name: createloan\n\
  \        method: POST\n        description: Encompass Developer Connect Create a new loan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loans-loanid\n      path: /loans/{loanId}\n      operations:\n      - name: getloan\n        method: GET\n        description: Encompass Developer Connect Retrieve a loan\n        inputParameters:\n        - name: loanId\n          in: path\n          type: string\n          required: true\n        - name: entities\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateloan\n        method: PATCH\n        description: Encompass Developer Connect Update a loan\n        inputParameters:\n        - name: loanId\n          in: path\n          type: string\n          required: true\n        - name: appendData\n          in: query\n\
  \          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteloan\n        method: DELETE\n        description: Encompass Developer Connect Delete a loan\n        inputParameters:\n        - name: loanId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: encompass-developer-connect-rest\n    description: REST adapter for Encompass Developer Connect API.\n    resources:\n    - path: /oauth2/v1/token\n      name: issueaccesstoken\n      operations:\n      - method: POST\n        name: issueaccesstoken\n        description: Encompass Developer Connect Issue an OAuth 2.0 access token\n        call: encompass-developer-connect.issueaccesstoken\n        outputParameters:\n      \
  \  - type: object\n          mapping: $.\n    - path: /loanPipeline\n      name: searchloanpipeline\n      operations:\n      - method: POST\n        name: searchloanpipeline\n        description: Encompass Developer Connect Search the loan pipeline\n        call: encompass-developer-connect.searchloanpipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /loans\n      name: createloan\n      operations:\n      - method: POST\n        name: createloan\n        description: Encompass Developer Connect Create a new loan\n        call: encompass-developer-connect.createloan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /loans/{loanId}\n      name: getloan\n      operations:\n      - method: GET\n        name: getloan\n        description: Encompass Developer Connect Retrieve a loan\n        call: encompass-developer-connect.getloan\n        with:\n          loanId: rest.loanId\n        outputParameters:\n  \
  \      - type: object\n          mapping: $.\n    - path: /loans/{loanId}\n      name: updateloan\n      operations:\n      - method: PATCH\n        name: updateloan\n        description: Encompass Developer Connect Update a loan\n        call: encompass-developer-connect.updateloan\n        with:\n          loanId: rest.loanId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /loans/{loanId}\n      name: deleteloan\n      operations:\n      - method: DELETE\n        name: deleteloan\n        description: Encompass Developer Connect Delete a loan\n        call: encompass-developer-connect.deleteloan\n        with:\n          loanId: rest.loanId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: encompass-developer-connect-mcp\n    transport: http\n    description: MCP adapter for Encompass Developer Connect API for AI agent use.\n    tools:\n    - name: issueaccesstoken\n      description:\
  \ Encompass Developer Connect Issue an OAuth 2.0 access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: encompass-developer-connect.issueaccesstoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchloanpipeline\n      description: Encompass Developer Connect Search the loan pipeline\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: encompass-developer-connect.searchloanpipeline\n      with:\n        cursorType: tools.cursorType\n        limit: tools.limit\n      inputParameters:\n      - name: cursorType\n        type: string\n        description: cursorType\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createloan\n      description: Encompass Developer Connect Create a new loan\n      hints:\n        readOnly: false\n    \
  \    destructive: false\n        idempotent: false\n      call: encompass-developer-connect.createloan\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getloan\n      description: Encompass Developer Connect Retrieve a loan\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: encompass-developer-connect.getloan\n      with:\n        loanId: tools.loanId\n        entities: tools.entities\n      inputParameters:\n      - name: loanId\n        type: string\n        description: loanId\n        required: true\n      - name: entities\n        type: string\n        description: entities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateloan\n      description: Encompass Developer Connect Update a loan\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: encompass-developer-connect.updateloan\n      with:\n        loanId:\
  \ tools.loanId\n        appendData: tools.appendData\n      inputParameters:\n      - name: loanId\n        type: string\n        description: loanId\n        required: true\n      - name: appendData\n        type: boolean\n        description: appendData\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteloan\n      description: Encompass Developer Connect Delete a loan\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: encompass-developer-connect.deleteloan\n      with:\n        loanId: tools.loanId\n      inputParameters:\n      - name: loanId\n        type: string\n        description: loanId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ENCOMPASS_DEVELOPER_CONNECT_TOKEN: ENCOMPASS_DEVELOPER_CONNECT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/encompass-developer-connect/refs/heads/main/capabilities/encompass-developer-connect-capability.yaml
tags:
- Encompass
- Developer
- Connect
- API
tools:
- description: Encompass Developer Connect Issue an OAuth 2.0 access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: issueaccesstoken
- description: Encompass Developer Connect Search the loan pipeline
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchloanpipeline
- description: Encompass Developer Connect Create a new loan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createloan
- description: Encompass Developer Connect Retrieve a loan
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getloan
- description: Encompass Developer Connect Update a loan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateloan
- description: Encompass Developer Connect Delete a loan
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteloan
---
