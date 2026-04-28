---
categories:
- machine-learning
consumed_apis:
- hf-inference
- hf-providers
- hf-tgi
description: Unified workflow for running AI/ML inference across Hugging Face APIs, combining the Inference API, Inference Providers, and Text Generation Inference for NLP, vision, audio, and multimodal tasks. Used by ML engineers and AI application developers.
layout: capability
name: Hugging Face Model Inference
operations:
- description: Run inference on a model via the Inference API
  method: POST
  name: run-inference
  path: /v1/inference/{model_id}
- description: Generate text using the Inference API
  method: POST
  name: text-generation
  path: /v1/text-generation/{model_id}
- description: Create chat completion via providers
  method: POST
  name: chat-completion
  path: /v1/chat/completions
- description: Create text completion via providers
  method: POST
  name: text-completion
  path: /v1/completions
- description: Create text embeddings
  method: POST
  name: create-embeddings
  path: /v1/embeddings
- description: Generate images from text
  method: POST
  name: generate-image
  path: /v1/images/generations
- description: Classify text into categories
  method: POST
  name: classify-text
  path: /v1/classification/{model_id}
- description: Summarize text content
  method: POST
  name: summarize
  path: /v1/summarization/{model_id}
- description: Translate text between languages
  method: POST
  name: translate
  path: /v1/translation/{model_id}
personas: []
provider_name: Hugging Face
provider_slug: hugging-face
search_terms:
- generate text
- transcribe audio to text using automatic speech recognition.
- generate text using the inference api
- create text completion via multi-provider api.
- providers generate image
- summarize text content.
- openai-compatible chat completions
- transcribe audio via multi-provider api.
- classify text into predefined categories.
- translate text between languages.
- chat completion
- text generation
- text completions
- zero shot classify
- generate text using a language model via the inference api.
- extract feature vectors from text for embeddings.
- classify images into categories.
- classify text into categories
- create chat completion via openai-compatible multi-provider api.
- text classification
- classify text
- summarize text
- providers text completion
- create chat completions using tgi openai-compatible messages api.
- generate text with a specific model
- text embeddings
- list provider models
- fill in masked tokens in text.
- translate text
- transcribe speech
- answer question
- compute similarity between sentences.
- text translation
- inference
- generate images from text
- generate images from text prompts.
- text completion
- hugging face
- generate image
- translate
- generate images via multi-provider api.
- tgi generate
- run inference on any hugging face model by model id.
- create text embeddings
- tokenize input text and return token ids.
- tgi server info
- machine learning
- ai
- compute similarity
- tgi chat completions
- generate text using the tgi native endpoint.
- answer questions based on provided context.
- classify image
- image generation
- run inference on a model via the inference api
- detect objects
- text summarization
- detect objects in images.
- translate text between languages
- classify text without predefined training labels.
- providers chat completion
- create text embeddings via multi-provider api.
- providers create embeddings
- fill mask
- list models available across all inference providers.
- convert text to speech via multi-provider api.
- providers text to speech
- create embeddings
- run inference
- create chat completion via providers
- providers transcribe
- run inference on any model
- summarize text content
- summarize
- extract features
- tgi tokenize
- create text completion via providers
- get tgi server information and deployed model details.
slug: model-inference
tags:
- Hugging Face
- Machine Learning
- Inference
- AI
- Text Generation
tools:
- description: Run inference on any Hugging Face model by model ID.
  hints:
    openWorld: true
    readOnly: true
  name: run-inference
- description: Generate text using a language model via the Inference API.
  hints:
    openWorld: true
    readOnly: true
  name: generate-text
- description: Classify text into predefined categories.
  hints:
    openWorld: true
    readOnly: true
  name: classify-text
- description: Answer questions based on provided context.
  hints:
    openWorld: true
    readOnly: true
  name: answer-question
- description: Summarize text content.
  hints:
    openWorld: true
    readOnly: true
  name: summarize-text
- description: Translate text between languages.
  hints:
    openWorld: true
    readOnly: true
  name: translate-text
- description: Fill in masked tokens in text.
  hints:
    openWorld: true
    readOnly: true
  name: fill-mask
- description: Extract feature vectors from text for embeddings.
  hints:
    openWorld: true
    readOnly: true
  name: extract-features
- description: Classify images into categories.
  hints:
    openWorld: true
    readOnly: true
  name: classify-image
- description: Detect objects in images.
  hints:
    openWorld: true
    readOnly: true
  name: detect-objects
- description: Transcribe audio to text using automatic speech recognition.
  hints:
    openWorld: true
    readOnly: true
  name: transcribe-speech
- description: Generate images from text prompts.
  hints:
    openWorld: true
    readOnly: true
  name: generate-image
- description: Classify text without predefined training labels.
  hints:
    openWorld: true
    readOnly: true
  name: zero-shot-classify
- description: Compute similarity between sentences.
  hints:
    openWorld: true
    readOnly: true
  name: compute-similarity
- description: Create chat completion via OpenAI-compatible multi-provider API.
  hints:
    openWorld: true
    readOnly: true
  name: providers-chat-completion
- description: Create text completion via multi-provider API.
  hints:
    openWorld: true
    readOnly: true
  name: providers-text-completion
- description: Create text embeddings via multi-provider API.
  hints:
    openWorld: true
    readOnly: true
  name: providers-create-embeddings
- description: Generate images via multi-provider API.
  hints:
    openWorld: true
    readOnly: true
  name: providers-generate-image
- description: Transcribe audio via multi-provider API.
  hints:
    openWorld: true
    readOnly: true
  name: providers-transcribe
- description: Convert text to speech via multi-provider API.
  hints:
    openWorld: true
    readOnly: true
  name: providers-text-to-speech
- description: Generate text using the TGI native endpoint.
  hints:
    openWorld: true
    readOnly: true
  name: tgi-generate
- description: Create chat completions using TGI OpenAI-compatible Messages API.
  hints:
    openWorld: true
    readOnly: true
  name: tgi-chat-completions
- description: Tokenize input text and return token IDs.
  hints:
    readOnly: true
  name: tgi-tokenize
- description: Get TGI server information and deployed model details.
  hints:
    readOnly: true
  name: tgi-server-info
- description: List models available across all inference providers.
  hints:
    readOnly: true
  name: list-provider-models
---
