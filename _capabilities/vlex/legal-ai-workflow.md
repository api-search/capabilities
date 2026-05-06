---
categories: []
consumed_apis: []
description: Workflow capability for legal professionals and legaltech developers using vLex AI APIs. Combines legal document search, classification, key phrase extraction, citation detection, and text anonymization into a unified interface for document review, legal research, and privacy compliance workflows. Targeted at lawyers, paralegals, compliance teams, and legaltech application developers.
layout: capability
name: vLex Legal AI Workflow
operations:
- description: Semantic search across 100M+ legal documents.
  method: POST
  name: search-documents
  path: /v1/search
- description: Get a full legal document by vLex ID.
  method: GET
  name: get-document
  path: /v1/documents/{document_id}
- description: Classify legal text into practice areas.
  method: POST
  name: classify-document
  path: /v1/classify
- description: Extract key legal phrases from text.
  method: POST
  name: extract-key-phrases
  path: /v1/key-phrases
- description: Detect legal citations using vCite.
  method: POST
  name: detect-citations
  path: /v1/citations
- description: Anonymize PII in legal text.
  method: POST
  name: anonymize-text
  path: /v1/anonymize
- description: Extract named entities without modifying text.
  method: POST
  name: extract-entities
  path: /v1/anonymize/entities
personas: []
provider_name: vLex
provider_slug: vlex
search_terms:
- legal tech
- detect and parse legal citations in text using vcite. supports citation formats from 20+ jurisdictions. returns structured citation data with links to referenced documents.
- get legal document
- extract named entities without modifying text.
- key phrase extraction.
- citation detection
- extract document entities
- anonymize personally identifiable information (pii) in a legal document. replaces names, organizations, and other sensitive entities with tokens. pre-trained on legal corpora for high accuracy.
- detect legal citations using vcite.
- natural language processing
- search the vlex legal corpus.
- get document
- classify legal text into practice areas.
- vlex
- extract key legal phrases from text.
- get a full legal document by vlex id.
- semantic search across 100m+ legal documents.
- retrieve the full text and metadata of a legal document by its vlex id.
- identify all named entities (persons, organizations, locations, dates) in a legal text without modifying it. useful for document review and entity mapping.
- text anonymization.
- compliance
- legal text classification.
- anonymize text
- case law
- ai
- legal citation detection.
- detect citations
- search documents
- classify a legal text into practice areas (e.g. employment law, contract law, ip) using vlex's icenet algorithm. returns confidence-ranked classifications.
- named entity extraction.
- anonymize legal document
- anonymize pii in legal text.
- detect legal citations
- search legal documents
- extract legal key phrases
- extract key legal phrases, terms of art, and important concepts from a legal document.
- legal research
- extract key phrases
- classify legal text
- classification
- classify document
- extract entities
- legal document retrieval.
- search the vlex corpus of 100+ million legal documents across global jurisdictions. supports natural language queries. filter by jurisdiction (e.g. us, gb), document type (case_law, statute), and date range.
- privacy
- nlp
- anonymization
slug: legal-ai-workflow
source_filename: legal-ai-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: vLex Legal AI Workflow\n  description: Workflow capability for legal professionals and legaltech developers using vLex AI APIs. Combines legal document\n    search, classification, key phrase extraction, citation detection, and text anonymization into a unified interface for\n    document review, legal research, and privacy compliance workflows. Targeted at lawyers, paralegals, compliance teams,\n    and legaltech application developers.\n  tags:\n  - vLex\n  - AI\n  - Anonymization\n  - Case Law\n  - Citation Detection\n  - Classification\n  - Compliance\n  - Legal Research\n  - Legal Tech\n  - NLP\n  - Privacy\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VLEX_API_KEY: VLEX_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: vlex-anonymization\n    baseUri: https://api.vlex.com\n    description: vLex Iceberg text anonymization API.\n    authentication:\n      type: apikey\n \
  \     key: Ocp-Apim-Subscription-Key\n      value: '{{VLEX_API_KEY}}'\n      placement: header\n    resources:\n    - name: anonymize\n      path: /v1/anonymize\n      description: Anonymize PII in legal text.\n      operations:\n      - name: anonymize-text\n        method: POST\n        description: Replace identified PII entities with tokens in the input text.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            text: '{{tools.text}}'\n            mode: '{{tools.mode}}'\n            replacement_token: '{{tools.replacement_token}}'\n    - name: entities\n      path: /v1/anonymize/entities\n      description: Extract named entities without replacing them.\n      operations:\n      - name: extract-entities\n        method: POST\n        description: Identify and return all named entities in the input text.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            text: '{{tools.text}}'\n  - type: http\n    namespace: vlex-research\n    baseUri: https://api.vlex.com\n    description: vLex Iceberg legal research API.\n    authentication:\n      type: apikey\n      key: Ocp-Apim-Subscription-Key\n      value: '{{VLEX_API_KEY}}'\n      placement: header\n    resources:\n    - name: search\n      path: /v1/search\n      description: Legal document search.\n      operations:\n      - name: search-documents\n        method: POST\n        description: Search the vLex corpus for legal documents.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            jurisdiction: '{{tools.jurisdiction}}'\n            document_type: '{{tools.document_type}}'\n   \
  \ - name: document\n      path: /v1/documents/{document_id}\n      description: Individual legal document retrieval.\n      operations:\n      - name: get-document\n        method: GET\n        description: Get a full legal document by vLex ID.\n        inputParameters:\n        - name: document_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: classify\n      path: /v1/classify\n      description: Legal document classification.\n      operations:\n      - name: classify-document\n        method: POST\n        description: Classify a legal text into practice areas.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            text: '{{tools.text}}'\n    - name: key-phrases\n      path: /v1/key-phrases\n\
  \      description: Legal key phrase extraction.\n      operations:\n      - name: extract-key-phrases\n        method: POST\n        description: Extract key legal phrases from text.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            text: '{{tools.text}}'\n    - name: citations\n      path: /v1/citations\n      description: Legal citation detection.\n      operations:\n      - name: detect-citations\n        method: POST\n        description: Detect and parse legal citations using vCite.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            text: '{{tools.text}}'\n            jurisdiction: '{{tools.jurisdiction}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vlex-legal-api\n    description:\
  \ Unified REST API for vLex legal AI workflows.\n    resources:\n    - path: /v1/search\n      name: search\n      description: Search the vLex legal corpus.\n      operations:\n      - method: POST\n        name: search-documents\n        description: Semantic search across 100M+ legal documents.\n        call: vlex-research.search-documents\n        with:\n          query: rest.query\n          jurisdiction: rest.jurisdiction\n          document_type: rest.document_type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents/{document_id}\n      name: document\n      description: Legal document retrieval.\n      operations:\n      - method: GET\n        name: get-document\n        description: Get a full legal document by vLex ID.\n        call: vlex-research.get-document\n        with:\n          document_id: rest.document_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/classify\n      name: classify\n\
  \      description: Legal text classification.\n      operations:\n      - method: POST\n        name: classify-document\n        description: Classify legal text into practice areas.\n        call: vlex-research.classify-document\n        with:\n          text: rest.text\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/key-phrases\n      name: key-phrases\n      description: Key phrase extraction.\n      operations:\n      - method: POST\n        name: extract-key-phrases\n        description: Extract key legal phrases from text.\n        call: vlex-research.extract-key-phrases\n        with:\n          text: rest.text\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/citations\n      name: citations\n      description: Legal citation detection.\n      operations:\n      - method: POST\n        name: detect-citations\n        description: Detect legal citations using vCite.\n        call: vlex-research.detect-citations\n\
  \        with:\n          text: rest.text\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/anonymize\n      name: anonymize\n      description: Text anonymization.\n      operations:\n      - method: POST\n        name: anonymize-text\n        description: Anonymize PII in legal text.\n        call: vlex-anonymization.anonymize-text\n        with:\n          text: rest.text\n          mode: rest.mode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/anonymize/entities\n      name: entities\n      description: Named entity extraction.\n      operations:\n      - method: POST\n        name: extract-entities\n        description: Extract named entities without modifying text.\n        call: vlex-anonymization.extract-entities\n        with:\n          text: rest.text\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vlex-legal-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted legal research, document review, and privacy compliance.\n    tools:\n    - name: search-legal-documents\n      description: Search the vLex corpus of 100+ million legal documents across global jurisdictions. Supports natural language\n        queries. Filter by jurisdiction (e.g. US, GB), document type (case_law, statute), and date range.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vlex-research.search-documents\n      with:\n        query: tools.query\n        jurisdiction: tools.jurisdiction\n        document_type: tools.document_type\n        date_from: tools.date_from\n        date_to: tools.date_to\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-legal-document\n      description: Retrieve the full text and metadata of a legal document by its vLex ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vlex-research.get-document\n     \
  \ with:\n        document_id: tools.document_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: classify-legal-text\n      description: Classify a legal text into practice areas (e.g. Employment Law, Contract Law, IP) using vLex's IceNet algorithm.\n        Returns confidence-ranked classifications.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vlex-research.classify-document\n      with:\n        text: tools.text\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: extract-legal-key-phrases\n      description: Extract key legal phrases, terms of art, and important concepts from a legal document.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vlex-research.extract-key-phrases\n      with:\n        text: tools.text\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: detect-legal-citations\n      description: Detect and parse legal citations\
  \ in text using vCite. Supports citation formats from 20+ jurisdictions.\n        Returns structured citation data with links to referenced documents.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vlex-research.detect-citations\n      with:\n        text: tools.text\n        jurisdiction: tools.jurisdiction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: anonymize-legal-document\n      description: Anonymize personally identifiable information (PII) in a legal document. Replaces names, organizations,\n        and other sensitive entities with tokens. Pre-trained on legal corpora for high accuracy.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: vlex-anonymization.anonymize-text\n      with:\n        text: tools.text\n        mode: tools.mode\n        replacement_token: tools.replacement_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: extract-document-entities\n\
  \      description: Identify all named entities (persons, organizations, locations, dates) in a legal text without modifying\n        it. Useful for document review and entity mapping.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vlex-anonymization.extract-entities\n      with:\n        text: tools.text\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vlex/refs/heads/main/capabilities/legal-ai-workflow.yaml
tags:
- vLex
- AI
- Anonymization
- Case Law
- Citation Detection
- Classification
- Compliance
- Legal Research
- Legal Tech
- NLP
- Privacy
tools:
- description: Search the vLex corpus of 100+ million legal documents across global jurisdictions. Supports natural language queries. Filter by jurisdiction (e.g. US, GB), document type (case_law, statute), and date range.
  hints:
    idempotent: true
    readOnly: true
  name: search-legal-documents
- description: Retrieve the full text and metadata of a legal document by its vLex ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-legal-document
- description: Classify a legal text into practice areas (e.g. Employment Law, Contract Law, IP) using vLex's IceNet algorithm. Returns confidence-ranked classifications.
  hints:
    idempotent: true
    readOnly: true
  name: classify-legal-text
- description: Extract key legal phrases, terms of art, and important concepts from a legal document.
  hints:
    idempotent: true
    readOnly: true
  name: extract-legal-key-phrases
- description: Detect and parse legal citations in text using vCite. Supports citation formats from 20+ jurisdictions. Returns structured citation data with links to referenced documents.
  hints:
    idempotent: true
    readOnly: true
  name: detect-legal-citations
- description: Anonymize personally identifiable information (PII) in a legal document. Replaces names, organizations, and other sensitive entities with tokens. Pre-trained on legal corpora for high accuracy.
  hints:
    idempotent: true
    readOnly: false
  name: anonymize-legal-document
- description: Identify all named entities (persons, organizations, locations, dates) in a legal text without modifying it. Useful for document review and entity mapping.
  hints:
    idempotent: true
    readOnly: true
  name: extract-document-entities
---
