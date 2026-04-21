---
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
- detect language
- categorize
- open source
- language detection
- NLP Engineer
- tokenize text into words and punctuation
- machine learning
- java
- uses opennlp apis to add language processing capabilities to applications
- parse sentence structure
- split text into individual sentences
- text analysis
- chunk phrases
- tokenize text
- named entity recognition
- sentence boundary detection
- parse
- lemmatize
- list models
- detect sentences
- tokenize
- nlp
- tag pos
- apache
- document categorization
- split text into sentences
- find named entities
- Data Scientist
- end-to-end nlp processing pipeline
- classify a document into predefined categories
- list available models
- integrates opennlp into custom nlp pipelines and applications
- phrase chunking
- detect the language of input text
- reduce tokens to their base/lemma forms
- find entities
- uses nlp pipeline for text analysis and feature extraction
- apache opennlp
- identify noun phrases, verb phrases, and other chunks
- chunk
- full syntactic parsing
- parse sentence
- text processing
- part-of-speech tagging
- find named entities (persons, locations, organizations) in text
- information extraction
- detect document language
- tag parts of speech
- Application Developer
- tokenization
- chunk text into phrases
- build a full parse tree for a sentence
- list all available nlp models
- assign pos tags to each token in tokenized text
- natural language processing
- categorize document
- model management
slug: nlp-pipeline-workflow
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
