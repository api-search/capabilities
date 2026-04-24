---
consumed_apis:
- rekognition
description: Unified computer vision workflows combining image analysis, facial recognition, content moderation, and identity verification capabilities for developers and security teams.
layout: capability
name: Amazon Rekognition Computer Vision Workflows
operations:
- description: Detect objects, scenes, and concepts in an image
  method: POST
  name: detect-labels
  path: /v1/analyze/labels
- description: Detect faces and analyze facial attributes
  method: POST
  name: detect-faces
  path: /v1/analyze/faces
- description: Detect and extract text from an image
  method: POST
  name: detect-text
  path: /v1/analyze/text
- description: Detect unsafe or explicit content in an image
  method: POST
  name: detect-inappropriate-content
  path: /v1/moderation/labels
- description: Compare a face in a source image with a target image
  method: POST
  name: compare-faces
  path: /v1/identity/compare
- description: Search for matching faces in a collection using an image
  method: POST
  name: search-by-image
  path: /v1/identity/search
- description: Create a face liveness verification session
  method: POST
  name: create-session
  path: /v1/liveness/sessions
- description: Get the results of a face liveness session
  method: GET
  name: get-results
  path: /v1/liveness/sessions/{session_id}/results
- description: Identify celebrities in an image
  method: POST
  name: recognize
  path: /v1/celebrities
- description: List all face collections
  method: GET
  name: list
  path: /v1/collections
- description: Create a new face collection
  method: POST
  name: create
  path: /v1/collections
- description: Index faces into a collection
  method: POST
  name: index
  path: /v1/collections/{collection_id}/faces
- description: Start asynchronous label detection in a video
  method: POST
  name: start
  path: /v1/videos/labels
- description: Get the results of a video label detection job
  method: GET
  name: get-results
  path: /v1/videos/labels/{job_id}
personas: []
provider_name: Amazon Rekognition
provider_slug: amazon-rekognition
search_terms:
- synchronous analysis of images for labels, faces, text, and moderation
- recognize
- detect and extract printed and handwritten text from an image
- create a face liveness verification session
- manage face collections
- search for matching faces in a collection using an image
- create face collection
- get the confidence score and status from a face liveness verification session
- search face collections for matching identities
- get the results of a video label detection job
- face liveness verification for fraud prevention
- detect custom labels in an image using a trained amazon rekognition custom labels model
- security teams using facial recognition and liveness detection for identity verification and fraud prevention.
- asynchronous label detection in stored videos
- asynchronous analysis of stored and streaming video
- detect unsafe or explicit content in an image
- start asynchronous label detection in a video
- identity verification
- image analysis
- computer vision
- detect labels and objects in images
- create a new face collection for storing and indexing face data
- create liveness session
- detect and extract text from an image
- deep learning
- detect faces and analyze facial attributes
- recognize celebrities
- detect objects, scenes, and concepts in an image using amazon rekognition
- detect faces
- celebrity recognition in images
- index
- get results
- get video label detection results
- object detection
- moderate image content
- Security Engineer
- create session
- search faces by image
- detect explicit, inappropriate, or violent content in an image for content moderation
- face liveness
- detect faces in an image and return facial attributes including age range, emotions, and smile
- amazon rekognition
- facial recognition
- face comparison, collection search, and liveness detection for user identity
- extract text from images
- start asynchronous detection of labels in a video stored in amazon s3
- detect text in image
- content moderation for inappropriate imagery
- content moderation
- detect image labels
- unified computer vision, identity verification, and content moderation workflows
- detect labels
- index faces in collection
- detect custom labels
- machine learning
- index faces into a collection
- identify celebrities in an image and return names and reference urls
- search a face collection for faces matching a provided image
- search by image
- start
- create a face liveness verification session to confirm a user is physically present
- manage faces in a collection
- video analysis
- developers building apps with computer vision features such as image search, face login, and text extraction.
- get liveness results
- Content Moderator
- custom labels
- trust and safety teams moderating user-generated content for inappropriate or explicit imagery.
- detect text
- list face collections
- compare a face in a source image with a target image
- detect and analyze facial attributes
- compare faces for identity verification
- index faces from an image into a face collection for future searching
- identify celebrities in an image
- compare faces
- text detection
- start video label detection
- create a new face collection
- retrieve face liveness session results
- compare a face in a source image with faces in a target image for identity verification
- Application Developer
- list
- list all face collections
- aws
- get the results of an asynchronous video label detection job
- detect inappropriate content
- get the results of a face liveness session
- celebrity recognition
- create
- list all face collections in the aws account
- detect objects, scenes, and concepts in an image
slug: computer-vision-workflows
tags:
- Amazon Rekognition
- Computer Vision
- Identity Verification
- Content Moderation
- Facial Recognition
tools:
- description: Detect objects, scenes, and concepts in an image using Amazon Rekognition
  hints:
    openWorld: true
    readOnly: true
  name: detect-image-labels
- description: Detect faces in an image and return facial attributes including age range, emotions, and smile
  hints:
    openWorld: true
    readOnly: true
  name: detect-faces
- description: Compare a face in a source image with faces in a target image for identity verification
  hints:
    openWorld: true
    readOnly: true
  name: compare-faces
- description: Detect and extract printed and handwritten text from an image
  hints:
    openWorld: true
    readOnly: true
  name: detect-text-in-image
- description: Detect explicit, inappropriate, or violent content in an image for content moderation
  hints:
    openWorld: true
    readOnly: true
  name: moderate-image-content
- description: Identify celebrities in an image and return names and reference URLs
  hints:
    openWorld: true
    readOnly: true
  name: recognize-celebrities
- description: Detect custom labels in an image using a trained Amazon Rekognition Custom Labels model
  hints:
    openWorld: true
    readOnly: true
  name: detect-custom-labels
- description: Create a new face collection for storing and indexing face data
  hints:
    openWorld: false
    readOnly: false
  name: create-face-collection
- description: List all face collections in the AWS account
  hints:
    openWorld: false
    readOnly: true
  name: list-face-collections
- description: Index faces from an image into a face collection for future searching
  hints:
    openWorld: false
    readOnly: false
  name: index-faces-in-collection
- description: Search a face collection for faces matching a provided image
  hints:
    openWorld: false
    readOnly: true
  name: search-faces-by-image
- description: Create a face liveness verification session to confirm a user is physically present
  hints:
    openWorld: false
    readOnly: false
  name: create-liveness-session
- description: Get the confidence score and status from a face liveness verification session
  hints:
    openWorld: false
    readOnly: true
  name: get-liveness-results
- description: Start asynchronous detection of labels in a video stored in Amazon S3
  hints:
    openWorld: false
    readOnly: false
  name: start-video-label-detection
- description: Get the results of an asynchronous video label detection job
  hints:
    openWorld: false
    readOnly: true
  name: get-video-label-detection-results
---
