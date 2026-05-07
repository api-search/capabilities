---
categories: []
consumed_apis: []
description: Kroki provides a unified HTTP API for generating diagrams from textual descriptions. It supports over 20 diagram types including PlantUML, Mermaid, GraphViz, BlockDiag, BPMN, C4, Structurizr, Excalidraw, Vega, WaveDrom, and more. Diagrams can be submitted as GET requests with the source encoded in the URL or as POST requests with the source in the request body.
layout: capability
name: Kroki Diagram API
operations:
- description: Get Service Health
  method: GET
  name: gethealth
  path: /
- description: Get Diagram via GET
  method: GET
  name: getdiagramget
  path: /{diagram_type}/{output_format}/{encoded_diagram}
- description: Post Diagram for Rendering
  method: POST
  name: postdiagram
  path: /{diagram_type}/{output_format}
personas: []
provider_name: UML
provider_slug: uml
search_terms:
- diagrams
- standards
- get diagram via get
- postdiagram
- uml
- software architecture
- design
- gethealth
- post diagram for rendering
- getdiagramget
- api
- get service health
- modeling
slug: uml-capability
source_filename: uml-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Kroki Diagram API\n  description: Kroki provides a unified HTTP API for generating diagrams from textual descriptions. It supports over 20 diagram\n    types including PlantUML, Mermaid, GraphViz, BlockDiag, BPMN, C4, Structurizr, Excalidraw, Vega, WaveDrom, and more. Diagrams\n    can be submitted as GET requests with the source encoded in the URL or as POST requests with the source in the request\n    body.\n  tags:\n  - Uml\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: uml\n    baseUri: https://kroki.io\n    description: Kroki Diagram API HTTP API.\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: gethealth\n        method: GET\n        description: Get Service Health\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: diagram-type-output-format-encoded-diagram\n\
  \      path: /{diagram_type}/{output_format}/{encoded_diagram}\n      operations:\n      - name: getdiagramget\n        method: GET\n        description: Get Diagram via GET\n        inputParameters:\n        - name: diagram_type\n          in: path\n          type: string\n          required: true\n          description: 'The type of diagram to generate. Supported types: plantuml, mermaid, graphviz, blockdiag, seqdiag,\n            actdiag, nwdiag, packetdiag, rackdiag, bpmn, bytefield, c4pla'\n        - name: output_format\n          in: path\n          type: string\n          required: true\n          description: 'Output format for the diagram. Supported formats: svg, png, jpeg, pdf (availability depends on diagram\n            type)'\n        - name: encoded_diagram\n          in: path\n          type: string\n          required: true\n          description: Deflate + base64url encoded diagram source text\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: diagram-type-output-format\n      path: /{diagram_type}/{output_format}\n      operations:\n      - name: postdiagram\n        method: POST\n        description: Post Diagram for Rendering\n        inputParameters:\n        - name: diagram_type\n          in: path\n          type: string\n          required: true\n          description: 'The type of diagram to generate. Supported types: plantuml, mermaid, graphviz, blockdiag, seqdiag,\n            actdiag, nwdiag, bpmn, c4plantuml, d2, ditaa, erd, excalidraw'\n        - name: output_format\n          in: path\n          type: string\n          required: true\n          description: Output format for the diagram (svg, png, jpeg, pdf)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: uml-rest\n    description: REST adapter for Kroki Diagram API.\n\
  \    resources:\n    - path: /\n      name: gethealth\n      operations:\n      - method: GET\n        name: gethealth\n        description: Get Service Health\n        call: uml.gethealth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{diagram_type}/{output_format}/{encoded_diagram}\n      name: getdiagramget\n      operations:\n      - method: GET\n        name: getdiagramget\n        description: Get Diagram via GET\n        call: uml.getdiagramget\n        with:\n          diagram_type: rest.diagram_type\n          output_format: rest.output_format\n          encoded_diagram: rest.encoded_diagram\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{diagram_type}/{output_format}\n      name: postdiagram\n      operations:\n      - method: POST\n        name: postdiagram\n        description: Post Diagram for Rendering\n        call: uml.postdiagram\n        with:\n          diagram_type: rest.diagram_type\n\
  \          output_format: rest.output_format\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: uml-mcp\n    transport: http\n    description: MCP adapter for Kroki Diagram API for AI agent use.\n    tools:\n    - name: gethealth\n      description: Get Service Health\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: uml.gethealth\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdiagramget\n      description: Get Diagram via GET\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: uml.getdiagramget\n      with:\n        diagram_type: tools.diagram_type\n        output_format: tools.output_format\n        encoded_diagram: tools.encoded_diagram\n      inputParameters:\n      - name: diagram_type\n        type: string\n        description: 'The type of diagram to generate. Supported\
  \ types: plantuml, mermaid, graphviz, blockdiag, seqdiag, actdiag,\n          nwdiag, packetdiag, rackdiag, bpmn, bytefield, c4pla'\n        required: true\n      - name: output_format\n        type: string\n        description: 'Output format for the diagram. Supported formats: svg, png, jpeg, pdf (availability depends on diagram\n          type)'\n        required: true\n      - name: encoded_diagram\n        type: string\n        description: Deflate + base64url encoded diagram source text\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postdiagram\n      description: Post Diagram for Rendering\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: uml.postdiagram\n      with:\n        diagram_type: tools.diagram_type\n        output_format: tools.output_format\n      inputParameters:\n      - name: diagram_type\n        type: string\n        description: 'The type of diagram\
  \ to generate. Supported types: plantuml, mermaid, graphviz, blockdiag, seqdiag, actdiag,\n          nwdiag, bpmn, c4plantuml, d2, ditaa, erd, excalidraw'\n        required: true\n      - name: output_format\n        type: string\n        description: Output format for the diagram (svg, png, jpeg, pdf)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/uml/refs/heads/main/capabilities/uml-capability.yaml
tags:
- Uml
- API
tools:
- description: Get Service Health
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealth
- description: Get Diagram via GET
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdiagramget
- description: Post Diagram for Rendering
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postdiagram
---
