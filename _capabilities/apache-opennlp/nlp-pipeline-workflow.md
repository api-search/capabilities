---
categories: []
consumed_apis:
- opennlp
description: End-to-end NLP processing workflow combining language detection, sentence detection, tokenization, POS tagging, NER, chunking, and parsing for comprehensive text analysis.
layout: capability
name: Apache OpenNLP NLP Pipeline Workflow
operations:
- description: Detect document language
  method: POST
  name: detect-language
  path: /v1/language
- description: Split text into sentences
  method: POST
  name: detect-sentences
  path: /v1/sentences
- description: Tokenize text
  method: POST
  name: tokenize
  path: /v1/tokens
- description: Find named entities
  method: POST
  name: find-entities
  path: /v1/entities
- description: Tag parts of speech
  method: POST
  name: tag-pos
  path: /v1/pos
- description: Chunk text into phrases
  method: POST
  name: chunk
  path: /v1/chunks
- description: Parse sentence structure
  method: POST
  name: parse
  path: /v1/parse
- description: Categorize document
  method: POST
  name: categorize
  path: /v1/categories
- description: List available models
  method: GET
  name: list-models
  path: /v1/models
personas: []
provider_name: Apache OpenNLP
provider_slug: apache-opennlp
search_terms:
- phrase chunking
- split text into sentences
- detect language
- parse sentence
- Application Developer
- tag parts of speech
- find named entities (persons, locations, organizations) in text
- uses opennlp apis to add language processing capabilities to applications
- text processing
- java
- tokenize text into words and punctuation
- full syntactic parsing
- tag pos
- text analysis
- categorize document
- end-to-end nlp processing pipeline
- sentence boundary detection
- model management
- identify noun phrases, verb phrases, and other chunks
- language detection
- tokenize
- machine learning
- nlp
- apache opennlp
- apache
- list models
- assign pos tags to each token in tokenized text
- reduce tokens to their base/lemma forms
- integrates opennlp into custom nlp pipelines and applications
- open source
- chunk phrases
- named entity recognition
- tokenization
- Data Scientist
- information extraction
- split text into individual sentences
- NLP Engineer
- chunk
- tokenize text
- categorize
- natural language processing
- find named entities
- build a full parse tree for a sentence
- lemmatize
- find entities
- list available models
- list all available nlp models
- parse
- classify a document into predefined categories
- detect the language of input text
- document categorization
- parse sentence structure
- part-of-speech tagging
- chunk text into phrases
- detect document language
- uses nlp pipeline for text analysis and feature extraction
- detect sentences
slug: nlp-pipeline-workflow
source_filename: nlp-pipeline-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apache OpenNLP NLP Pipeline Workflow\"\n  description: \"End-to-end NLP processing workflow combining language detection, sentence detection, tokenization, POS tagging, NER, chunking, and parsing for comprehensive text analysis.\"\n  tags:\n    - Apache OpenNLP\n    - Natural Language Processing\n    - Text Analysis\n    - Information Extraction\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      OPENNLP_API_KEY: OPENNLP_API_KEY\n\ncapability:\n  consumes:\n    - import: opennlp\n      location: ./shared/opennlp-tools.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: nlp-pipeline-api\n      description: \"Unified REST API for NLP text processing pipeline.\"\n      resources:\n        - path: /v1/language\n          name: language-detection\n          description: \"Language detection\"\n          operations:\n            - method: POST\n              name:\
  \ detect-language\n              description: \"Detect document language\"\n              call: \"opennlp.detectLanguage\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sentences\n          name: sentence-detection\n          description: \"Sentence boundary detection\"\n          operations:\n            - method: POST\n              name: detect-sentences\n              description: \"Split text into sentences\"\n              call: \"opennlp.detectSentences\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tokens\n          name: tokenization\n          description: \"Tokenization\"\n          operations:\n            - method: POST\n              name: tokenize\n              description: \"Tokenize text\"\n              call: \"opennlp.tokenize\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/entities\n          name: named-entities\n          description: \"Named entity recognition\"\n          operations:\n            - method: POST\n              name: find-entities\n              description: \"Find named entities\"\n              call: \"opennlp.findNamedEntities\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pos\n          name: pos-tags\n          description: \"Part-of-speech tagging\"\n          operations:\n            - method: POST\n              name: tag-pos\n              description: \"Tag parts of speech\"\n              call: \"opennlp.tagPartsOfSpeech\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/chunks\n          name: chunks\n          description: \"Phrase chunking\"\n          operations:\n            - method: POST\n              name: chunk\n              description: \"\
  Chunk text into phrases\"\n              call: \"opennlp.chunkText\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/parse\n          name: parse-tree\n          description: \"Full syntactic parsing\"\n          operations:\n            - method: POST\n              name: parse\n              description: \"Parse sentence structure\"\n              call: \"opennlp.parseText\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/categories\n          name: categories\n          description: \"Document categorization\"\n          operations:\n            - method: POST\n              name: categorize\n              description: \"Categorize document\"\n              call: \"opennlp.categorizeDocument\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models\n          name: models\n\
  \          description: \"Model management\"\n          operations:\n            - method: GET\n              name: list-models\n              description: \"List available models\"\n              call: \"opennlp.listModels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: nlp-pipeline-mcp\n      transport: http\n      description: \"MCP server for AI-assisted NLP text processing.\"\n      tools:\n        - name: detect-language\n          description: \"Detect the language of input text\"\n          hints:\n            readOnly: true\n          call: \"opennlp.detectLanguage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: detect-sentences\n          description: \"Split text into individual sentences\"\n          hints:\n            readOnly: true\n          call: \"opennlp.detectSentences\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: tokenize\n          description: \"Tokenize text into words and punctuation\"\n          hints:\n            readOnly: true\n          call: \"opennlp.tokenize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-named-entities\n          description: \"Find named entities (persons, locations, organizations) in text\"\n          hints:\n            readOnly: true\n          call: \"opennlp.findNamedEntities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: tag-parts-of-speech\n          description: \"Assign POS tags to each token in tokenized text\"\n          hints:\n            readOnly: true\n          call: \"opennlp.tagPartsOfSpeech\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lemmatize\n          description: \"Reduce tokens to their\
  \ base/lemma forms\"\n          hints:\n            readOnly: true\n          call: \"opennlp.lemmatize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: chunk-phrases\n          description: \"Identify noun phrases, verb phrases, and other chunks\"\n          hints:\n            readOnly: true\n          call: \"opennlp.chunkText\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: parse-sentence\n          description: \"Build a full parse tree for a sentence\"\n          hints:\n            readOnly: true\n          call: \"opennlp.parseText\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: categorize-document\n          description: \"Classify a document into predefined categories\"\n          hints:\n            readOnly: true\n          call: \"opennlp.categorizeDocument\"\n          outputParameters:\n           \
  \ - type: object\n              mapping: \"$.\"\n        - name: list-models\n          description: \"List all available NLP models\"\n          hints:\n            readOnly: true\n          call: \"opennlp.listModels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-opennlp/refs/heads/main/capabilities/nlp-pipeline-workflow.yaml
tags:
- Apache OpenNLP
- Natural Language Processing
- Text Analysis
- Information Extraction
tools:
- description: Detect the language of input text
  hints:
    readOnly: true
  name: detect-language
- description: Split text into individual sentences
  hints:
    readOnly: true
  name: detect-sentences
- description: Tokenize text into words and punctuation
  hints:
    readOnly: true
  name: tokenize
- description: Find named entities (persons, locations, organizations) in text
  hints:
    readOnly: true
  name: find-named-entities
- description: Assign POS tags to each token in tokenized text
  hints:
    readOnly: true
  name: tag-parts-of-speech
- description: Reduce tokens to their base/lemma forms
  hints:
    readOnly: true
  name: lemmatize
- description: Identify noun phrases, verb phrases, and other chunks
  hints:
    readOnly: true
  name: chunk-phrases
- description: Build a full parse tree for a sentence
  hints:
    readOnly: true
  name: parse-sentence
- description: Classify a document into predefined categories
  hints:
    readOnly: true
  name: categorize-document
- description: List all available NLP models
  hints:
    readOnly: true
  name: list-models
---
