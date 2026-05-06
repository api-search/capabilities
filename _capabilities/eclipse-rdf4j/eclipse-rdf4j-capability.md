---
categories: []
consumed_apis: []
description: REST API for the Eclipse RDF4J Server. Provides endpoints to list and manage RDF repositories, configure them, query and update their contents using SPARQL, manage namespaces, transactions, contexts and statements, and import/export RDF data in standard serialization formats. The Eclipse RDF4J Server is a Java server application that exposes this protocol over HTTP.
layout: capability
name: RDF4J Server REST API
operations:
- description: Get protocol version
  method: GET
  name: getprotocolversion
  path: /protocol
- description: List repositories
  method: GET
  name: listrepositories
  path: /repositories
- description: Query repository (SPARQL)
  method: GET
  name: queryrepository
  path: /repositories/{repositoryID}
- description: SPARQL query or update
  method: POST
  name: postqueryorupdate
  path: /repositories/{repositoryID}
- description: Create or configure repository
  method: PUT
  name: createrepository
  path: /repositories/{repositoryID}
- description: Delete repository
  method: DELETE
  name: deleterepository
  path: /repositories/{repositoryID}
- description: Get statements
  method: GET
  name: getstatements
  path: /repositories/{repositoryID}/statements
- description: Add or update statements
  method: POST
  name: addstatements
  path: /repositories/{repositoryID}/statements
- description: Replace statements
  method: PUT
  name: replacestatements
  path: /repositories/{repositoryID}/statements
- description: Remove statements
  method: DELETE
  name: removestatements
  path: /repositories/{repositoryID}/statements
- description: Get repository size
  method: GET
  name: getrepositorysize
  path: /repositories/{repositoryID}/size
- description: List contexts
  method: GET
  name: listcontexts
  path: /repositories/{repositoryID}/contexts
- description: List namespaces
  method: GET
  name: listnamespaces
  path: /repositories/{repositoryID}/namespaces
- description: Clear namespaces
  method: DELETE
  name: clearnamespaces
  path: /repositories/{repositoryID}/namespaces
- description: Get namespace
  method: GET
  name: getnamespace
  path: /repositories/{repositoryID}/namespaces/{prefix}
- description: Set namespace
  method: PUT
  name: setnamespace
  path: /repositories/{repositoryID}/namespaces/{prefix}
- description: Delete namespace
  method: DELETE
  name: deletenamespace
  path: /repositories/{repositoryID}/namespaces/{prefix}
- description: Begin transaction
  method: POST
  name: begintransaction
  path: /repositories/{repositoryID}/transactions
- description: Execute transaction action
  method: PUT
  name: executetransactionaction
  path: /repositories/{repositoryID}/transactions/{transactionID}
- description: Rollback transaction
  method: DELETE
  name: rollbacktransaction
  path: /repositories/{repositoryID}/transactions/{transactionID}
personas: []
provider_name: Eclipse RDF4J
provider_slug: eclipse-rdf4j
search_terms:
- queryrepository
- clear namespaces
- get namespace
- rollbacktransaction
- linked data
- listrepositories
- getnamespace
- getstatements
- java
- createrepository
- get statements
- eclipse foundation
- removestatements
- list contexts
- list repositories
- add or update statements
- triple store
- addstatements
- begin transaction
- execute transaction action
- listnamespaces
- getrepositorysize
- set namespace
- deleterepository
- query repository (sparql)
- open source
- create or configure repository
- clearnamespaces
- replacestatements
- get protocol version
- get repository size
- deletenamespace
- remove statements
- list namespaces
- getprotocolversion
- api
- sparql query or update
- rollback transaction
- listcontexts
- replace statements
- rdf4j
- sparql
- eclipse
- delete namespace
- rdf
- postqueryorupdate
- setnamespace
- semantic web
- begintransaction
- delete repository
- executetransactionaction
slug: eclipse-rdf4j-capability
source_filename: eclipse-rdf4j-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: RDF4J Server REST API\n  description: REST API for the Eclipse RDF4J Server. Provides endpoints to list and manage RDF repositories, configure them,\n    query and update their contents using SPARQL, manage namespaces, transactions, contexts and statements, and import/export\n    RDF data in standard serialization formats. The Eclipse RDF4J Server is a Java server application that exposes this protocol\n    over HTTP.\n  tags:\n  - Eclipse\n  - Rdf4j\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: eclipse-rdf4j\n    baseUri: http://localhost:8080/rdf4j-server\n    description: RDF4J Server REST API HTTP API.\n    resources:\n    - name: protocol\n      path: /protocol\n      operations:\n      - name: getprotocolversion\n        method: GET\n        description: Get protocol version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n    - name: repositories\n      path: /repositories\n      operations:\n      - name: listrepositories\n        method: GET\n        description: List repositories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repositoryid\n      path: /repositories/{repositoryID}\n      operations:\n      - name: queryrepository\n        method: GET\n        description: Query repository (SPARQL)\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: SPARQL query string.\n        - name: queryLn\n          in: query\n          type: string\n        - name: infer\n          in: query\n          type: boolean\n        - name: default-graph-uri\n          in: query\n          type: array\n        - name: named-graph-uri\n          in: query\n          type: array\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postqueryorupdate\n        method: POST\n        description: SPARQL query or update\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrepository\n        method: PUT\n        description: Create or configure repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterepository\n        method: DELETE\n        description: Delete repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repositoryid-statements\n      path: /repositories/{repositoryID}/statements\n      operations:\n      - name: getstatements\n        method: GET\n        description:\
  \ Get statements\n        inputParameters:\n        - name: subj\n          in: query\n          type: string\n        - name: pred\n          in: query\n          type: string\n        - name: obj\n          in: query\n          type: string\n        - name: context\n          in: query\n          type: array\n        - name: infer\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addstatements\n        method: POST\n        description: Add or update statements\n        inputParameters:\n        - name: context\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacestatements\n        method: PUT\n        description: Replace statements\n        inputParameters:\n        - name: context\n          in: query\n   \
  \       type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removestatements\n        method: DELETE\n        description: Remove statements\n        inputParameters:\n        - name: subj\n          in: query\n          type: string\n        - name: pred\n          in: query\n          type: string\n        - name: obj\n          in: query\n          type: string\n        - name: context\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repositoryid-size\n      path: /repositories/{repositoryID}/size\n      operations:\n      - name: getrepositorysize\n        method: GET\n        description: Get repository size\n        inputParameters:\n        - name: context\n          in: query\n          type: array\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repositoryid-contexts\n      path: /repositories/{repositoryID}/contexts\n      operations:\n      - name: listcontexts\n        method: GET\n        description: List contexts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repositoryid-namespaces\n      path: /repositories/{repositoryID}/namespaces\n      operations:\n      - name: listnamespaces\n        method: GET\n        description: List namespaces\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: clearnamespaces\n        method: DELETE\n        description: Clear namespaces\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repositoryid-namespaces-prefix\n\
  \      path: /repositories/{repositoryID}/namespaces/{prefix}\n      operations:\n      - name: getnamespace\n        method: GET\n        description: Get namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setnamespace\n        method: PUT\n        description: Set namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenamespace\n        method: DELETE\n        description: Delete namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repositoryid-transactions\n      path: /repositories/{repositoryID}/transactions\n      operations:\n      - name: begintransaction\n        method: POST\n        description: Begin transaction\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: repositories-repositoryid-transactions-transacti\n      path: /repositories/{repositoryID}/transactions/{transactionID}\n      operations:\n      - name: executetransactionaction\n        method: PUT\n        description: Execute transaction action\n        inputParameters:\n        - name: action\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: rollbacktransaction\n        method: DELETE\n        description: Rollback transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: eclipse-rdf4j-rest\n    description: REST adapter for RDF4J Server REST API.\n    resources:\n    - path: /protocol\n      name: getprotocolversion\n\
  \      operations:\n      - method: GET\n        name: getprotocolversion\n        description: Get protocol version\n        call: eclipse-rdf4j.getprotocolversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories\n      name: listrepositories\n      operations:\n      - method: GET\n        name: listrepositories\n        description: List repositories\n        call: eclipse-rdf4j.listrepositories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}\n      name: queryrepository\n      operations:\n      - method: GET\n        name: queryrepository\n        description: Query repository (SPARQL)\n        call: eclipse-rdf4j.queryrepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}\n      name: postqueryorupdate\n      operations:\n      - method: POST\n        name: postqueryorupdate\n        description:\
  \ SPARQL query or update\n        call: eclipse-rdf4j.postqueryorupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}\n      name: createrepository\n      operations:\n      - method: PUT\n        name: createrepository\n        description: Create or configure repository\n        call: eclipse-rdf4j.createrepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}\n      name: deleterepository\n      operations:\n      - method: DELETE\n        name: deleterepository\n        description: Delete repository\n        call: eclipse-rdf4j.deleterepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}/statements\n      name: getstatements\n      operations:\n      - method: GET\n        name: getstatements\n        description: Get statements\n        call: eclipse-rdf4j.getstatements\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}/statements\n      name: addstatements\n      operations:\n      - method: POST\n        name: addstatements\n        description: Add or update statements\n        call: eclipse-rdf4j.addstatements\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}/statements\n      name: replacestatements\n      operations:\n      - method: PUT\n        name: replacestatements\n        description: Replace statements\n        call: eclipse-rdf4j.replacestatements\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}/statements\n      name: removestatements\n      operations:\n      - method: DELETE\n        name: removestatements\n        description: Remove statements\n        call: eclipse-rdf4j.removestatements\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /repositories/{repositoryID}/size\n      name: getrepositorysize\n      operations:\n      - method: GET\n        name: getrepositorysize\n        description: Get repository size\n        call: eclipse-rdf4j.getrepositorysize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}/contexts\n      name: listcontexts\n      operations:\n      - method: GET\n        name: listcontexts\n        description: List contexts\n        call: eclipse-rdf4j.listcontexts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}/namespaces\n      name: listnamespaces\n      operations:\n      - method: GET\n        name: listnamespaces\n        description: List namespaces\n        call: eclipse-rdf4j.listnamespaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}/namespaces\n    \
  \  name: clearnamespaces\n      operations:\n      - method: DELETE\n        name: clearnamespaces\n        description: Clear namespaces\n        call: eclipse-rdf4j.clearnamespaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}/namespaces/{prefix}\n      name: getnamespace\n      operations:\n      - method: GET\n        name: getnamespace\n        description: Get namespace\n        call: eclipse-rdf4j.getnamespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}/namespaces/{prefix}\n      name: setnamespace\n      operations:\n      - method: PUT\n        name: setnamespace\n        description: Set namespace\n        call: eclipse-rdf4j.setnamespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}/namespaces/{prefix}\n      name: deletenamespace\n      operations:\n      - method:\
  \ DELETE\n        name: deletenamespace\n        description: Delete namespace\n        call: eclipse-rdf4j.deletenamespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}/transactions\n      name: begintransaction\n      operations:\n      - method: POST\n        name: begintransaction\n        description: Begin transaction\n        call: eclipse-rdf4j.begintransaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}/transactions/{transactionID}\n      name: executetransactionaction\n      operations:\n      - method: PUT\n        name: executetransactionaction\n        description: Execute transaction action\n        call: eclipse-rdf4j.executetransactionaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repositoryID}/transactions/{transactionID}\n      name: rollbacktransaction\n      operations:\n\
  \      - method: DELETE\n        name: rollbacktransaction\n        description: Rollback transaction\n        call: eclipse-rdf4j.rollbacktransaction\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: eclipse-rdf4j-mcp\n    transport: http\n    description: MCP adapter for RDF4J Server REST API for AI agent use.\n    tools:\n    - name: getprotocolversion\n      description: Get protocol version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eclipse-rdf4j.getprotocolversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrepositories\n      description: List repositories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eclipse-rdf4j.listrepositories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: queryrepository\n      description: Query\
  \ repository (SPARQL)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eclipse-rdf4j.queryrepository\n      with:\n        query: tools.query\n        queryLn: tools.queryLn\n        infer: tools.infer\n        default-graph-uri: tools.default-graph-uri\n        named-graph-uri: tools.named-graph-uri\n      inputParameters:\n      - name: query\n        type: string\n        description: SPARQL query string.\n        required: true\n      - name: queryLn\n        type: string\n        description: queryLn\n      - name: infer\n        type: boolean\n        description: infer\n      - name: default-graph-uri\n        type: array\n        description: default-graph-uri\n      - name: named-graph-uri\n        type: array\n        description: named-graph-uri\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postqueryorupdate\n      description: SPARQL query or update\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: eclipse-rdf4j.postqueryorupdate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrepository\n      description: Create or configure repository\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: eclipse-rdf4j.createrepository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterepository\n      description: Delete repository\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: eclipse-rdf4j.deleterepository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstatements\n      description: Get statements\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eclipse-rdf4j.getstatements\n      with:\n        subj: tools.subj\n        pred: tools.pred\n        obj:\
  \ tools.obj\n        context: tools.context\n        infer: tools.infer\n      inputParameters:\n      - name: subj\n        type: string\n        description: subj\n      - name: pred\n        type: string\n        description: pred\n      - name: obj\n        type: string\n        description: obj\n      - name: context\n        type: array\n        description: context\n      - name: infer\n        type: boolean\n        description: infer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addstatements\n      description: Add or update statements\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eclipse-rdf4j.addstatements\n      with:\n        context: tools.context\n      inputParameters:\n      - name: context\n        type: array\n        description: context\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacestatements\n      description: Replace statements\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: eclipse-rdf4j.replacestatements\n      with:\n        context: tools.context\n      inputParameters:\n      - name: context\n        type: array\n        description: context\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removestatements\n      description: Remove statements\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: eclipse-rdf4j.removestatements\n      with:\n        subj: tools.subj\n        pred: tools.pred\n        obj: tools.obj\n        context: tools.context\n      inputParameters:\n      - name: subj\n        type: string\n        description: subj\n      - name: pred\n        type: string\n        description: pred\n      - name: obj\n        type: string\n        description: obj\n      - name: context\n        type: array\n        description: context\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getrepositorysize\n      description: Get repository size\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eclipse-rdf4j.getrepositorysize\n      with:\n        context: tools.context\n      inputParameters:\n      - name: context\n        type: array\n        description: context\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontexts\n      description: List contexts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eclipse-rdf4j.listcontexts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnamespaces\n      description: List namespaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eclipse-rdf4j.listnamespaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ clearnamespaces\n      description: Clear namespaces\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: eclipse-rdf4j.clearnamespaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnamespace\n      description: Get namespace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eclipse-rdf4j.getnamespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setnamespace\n      description: Set namespace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: eclipse-rdf4j.setnamespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenamespace\n      description: Delete namespace\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: eclipse-rdf4j.deletenamespace\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: begintransaction\n      description: Begin transaction\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eclipse-rdf4j.begintransaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: executetransactionaction\n      description: Execute transaction action\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: eclipse-rdf4j.executetransactionaction\n      with:\n        action: tools.action\n      inputParameters:\n      - name: action\n        type: string\n        description: action\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: rollbacktransaction\n      description: Rollback transaction\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: eclipse-rdf4j.rollbacktransaction\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/eclipse-rdf4j/refs/heads/main/capabilities/eclipse-rdf4j-capability.yaml
tags:
- Eclipse
- Rdf4j
- API
tools:
- description: Get protocol version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprotocolversion
- description: List repositories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrepositories
- description: Query repository (SPARQL)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: queryrepository
- description: SPARQL query or update
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postqueryorupdate
- description: Create or configure repository
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createrepository
- description: Delete repository
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterepository
- description: Get statements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatements
- description: Add or update statements
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addstatements
- description: Replace statements
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacestatements
- description: Remove statements
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removestatements
- description: Get repository size
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrepositorysize
- description: List contexts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontexts
- description: List namespaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespaces
- description: Clear namespaces
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: clearnamespaces
- description: Get namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnamespace
- description: Set namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setnamespace
- description: Delete namespace
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenamespace
- description: Begin transaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: begintransaction
- description: Execute transaction action
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: executetransactionaction
- description: Rollback transaction
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: rollbacktransaction
---
