---
categories: []
consumed_apis: []
description: '# Welcome to Imentiv AI Imentiv AI is an advanced Emotion AI platform that leverages deep learning to analyze human emotions across multiple media formats, including video, audio, images, and text. By interpreting facial expressions, vocal tones, and linguistic cues, it provides detailed emotional insights to support use cases such as content creation, marketing optimization, education, mental health assessments, and more. Imentiv AI offers a suite of Emotion Recognition APIs that allow developers and businesses to seamlessly integrate advanced emotion analysis into their applications, enablin'
layout: capability
name: Welcome to Imentiv AI
operations:
- description: Upload Video
  method: POST
  name: upload-video-v2-videos-post
  path: /v2/videos
- description: List Videos
  method: GET
  name: list-videos-v1-videos-get
  path: /v1/videos
- description: Get Video Emotion Insights
  method: GET
  name: get-video-emotion-insights-v1-videos-video-id-ge
  path: /v1/videos/{video_id}
- description: Delete Video
  method: DELETE
  name: delete-video-v1-videos-video-id-delete
  path: /v1/videos/{video_id}
- description: Reprocess Video
  method: PUT
  name: reprocess-video-v1-videos-video-id-put
  path: /v1/videos/{video_id}
- description: Get Video Multimodal Insights
  method: GET
  name: get-video-multimodal-insights-v2-videos-video-id
  path: /v2/videos/{video_id}/multimodal-analytics
- description: Get Average Emotions
  method: GET
  name: get-average-emotions-v2-videos-video-id-emotions
  path: /v2/videos/{video_id}/emotions/average
- description: Get Annotated Video
  method: GET
  name: get-annotated-video-v2-videos-video-id-annotated
  path: /v2/videos/{video_id}/annotated_video
- description: Get Valence Arousal
  method: GET
  name: get-valence-arousal-v1-videos-video-id-valence-a
  path: /v1/videos/{video_id}/valence_arousal
- description: Get Multiple Frame
  method: GET
  name: get-multiple-frame-v1-videos-video-id-frames-get
  path: /v1/videos/{video_id}/frames
- description: Get Single Frame
  method: GET
  name: get-single-frame-v1-videos-video-id-frames-frame
  path: /v1/videos/{video_id}/frames/{frame_id}
- description: Retrieve Domination Emotion For A Specific Frame
  method: GET
  name: retrieve-domination-emotion-for-a-specific-frame
  path: /v1/videos/{video_id}/frames/{frame_id}/dominant_emotion
- description: Retrieve Emotion Intensity
  method: GET
  name: retrieve-emotion-intensity-v1-videos-video-id-fr
  path: /v1/videos/{video_id}/frames/{frame_id}/valence_arousal
- description: Update Emotion Per Frame
  method: PUT
  name: update-emotion-per-frame-v1-videos-video-id-fram
  path: /v1/videos/{video_id}/frames/{frame_id}/faces/{face_id}/emotions
- description: Edit Face Note
  method: PUT
  name: edit-face-note-v1-videos-video-id-frames-frame-i
  path: /v1/videos/{video_id}/frames/{frame_id}/faces/{face_id}/note
- description: Update Multiple Faces
  method: PUT
  name: update-multiple-faces-v1-videos-video-id-frames-
  path: /v1/videos/{video_id}/frames/faces
- description: Merge Face
  method: PUT
  name: merge-face-v1-videos-video-id-faces-put
  path: /v1/videos/{video_id}/faces
- description: Delete Faces
  method: DELETE
  name: delete-faces-v1-videos-video-id-faces-delete
  path: /v1/videos/{video_id}/faces
- description: Update Faces Names
  method: PUT
  name: update-faces-names-v1-videos-video-id-faces-name
  path: /v1/videos/{video_id}/faces/names
- description: Process Highlight
  method: POST
  name: process-highlight-v1-videos-highlights-post
  path: /v1/videos/highlights
- description: Fetch Highlight Video
  method: GET
  name: fetch-highlight-video-v1-videos-video-id-highlig
  path: /v1/videos/{video_id}/highlights
- description: Update Highlight Video
  method: PUT
  name: update-highlight-video-v1-videos-video-id-highli
  path: /v1/videos/{video_id}/highlights
- description: Download Highlight Video
  method: GET
  name: download-highlight-video-v1-videos-video-id-high
  path: /v1/videos/{video_id}/highlight_video
- description: Edit Title Or Description By Id
  method: PUT
  name: edit-title-or-description-by-id-v1-videos-video-
  path: /v1/videos/{video_id}/metadata
- description: Generate Video Emotion Analysis Report
  method: POST
  name: generate-video-emotion-analysis-report-v1-videos
  path: /v1/videos/{video_id}/report
- description: Download Video Emotion Analysis Report
  method: GET
  name: download-video-emotion-analysis-report-v1-videos
  path: /v1/videos/{video_id}/report
- description: Upload Audio
  method: POST
  name: upload-audio-v2-audios-post
  path: /v2/audios
- description: List Audios
  method: GET
  name: list-audios-v1-audios-get
  path: /v1/audios
- description: Get Audio Emotion Insights
  method: GET
  name: get-audio-emotion-insights-v1-audios-audio-id-ge
  path: /v1/audios/{audio_id}
- description: Reprocess Audio
  method: PUT
  name: reprocess-audio-v1-audios-audio-id-put
  path: /v1/audios/{audio_id}
- description: Delete An Audio
  method: DELETE
  name: delete-an-audio-v1-audios-audio-id-delete
  path: /v1/audios/{audio_id}
- description: Get Audio Multimodal Insights
  method: GET
  name: get-audio-multimodal-insights-v2-audios-audio-id
  path: /v2/audios/{audio_id}/multimodal-analytics
- description: Delete Audio Segment
  method: DELETE
  name: delete-audio-segment-v1-audios-audio-id-segment-
  path: /v1/audios/{audio_id}/{segment_index}
- description: Update Audio Transcripts Segments
  method: PUT
  name: update-audio-transcripts-segments-v1-audios-audi
  path: /v1/audios/{audio_id}/transcript
- description: Update Speaker Names
  method: PUT
  name: update-speaker-names-v1-audios-audio-id-speakers
  path: /v1/audios/{audio_id}/speakers/names
- description: Edit Title Or Description
  method: PUT
  name: edit-title-or-description-v1-audios-audio-id-met
  path: /v1/audios/{audio_id}/metadata
- description: Download Audio Emotion Report
  method: GET
  name: download-audio-emotion-report-v1-audios-audio-id
  path: /v1/audios/{audio_id}/report
- description: Upload Text
  method: POST
  name: upload-text-v2-texts-post
  path: /v2/texts
- description: List Texts
  method: GET
  name: list-texts-v1-texts-get
  path: /v1/texts
- description: Get Text Emotion Insights
  method: GET
  name: get-text-emotion-insights-v1-texts-text-id-get
  path: /v1/texts/{text_id}
- description: Delete Text
  method: DELETE
  name: delete-text-v1-texts-text-id-delete
  path: /v1/texts/{text_id}
- description: Reprocess Text
  method: PUT
  name: reprocess-text-v1-texts-text-id-put
  path: /v1/texts/{text_id}
- description: Upload Image
  method: POST
  name: upload-image-v2-images-post
  path: /v2/images
- description: List Images
  method: GET
  name: list-images-v1-images-get
  path: /v1/images
- description: Get Image Emotion Analysis
  method: GET
  name: get-image-emotion-analysis-v1-images-image-id-ge
  path: /v1/images/{image_id}
- description: Delete Image
  method: DELETE
  name: delete-image-v1-images-image-id-delete
  path: /v1/images/{image_id}
- description: Reprocess Image
  method: PUT
  name: reprocess-image-v1-images-image-id-put
  path: /v1/images/{image_id}
- description: Send Image
  method: GET
  name: send-image-v1-images-image-id-annotated-image-ge
  path: /v1/images/{image_id}/annotated_image
- description: Add Note To Specific Face
  method: PUT
  name: add-note-to-specific-face-v1-images-image-id-fac
  path: /v1/images/{image_id}/faces/{face_id}/note
- description: Edit Image Metadata
  method: PUT
  name: edit-image-metadata-v1-images-image-id-metadata-
  path: /v1/images/{image_id}/metadata
- description: Download Image Emotion Report
  method: GET
  name: download-image-emotion-report-v1-images-image-id
  path: /v1/images/{image_id}/report
- description: Generate Pdf Report
  method: GET
  name: generate-pdf-report-v2-reports-pdf-media-id-get
  path: /v2/reports/pdf/{media_id}
- description: Edit Text
  method: PUT
  name: edit-text-v1-texts-text-id-emotions-put
  path: /v1/texts/{text_id}/emotions
- description: Download Text Emotion Report
  method: GET
  name: download-text-emotion-report-v1-texts-text-id-re
  path: /v1/texts/{text_id}/report
- description: Replace Audio Transcript
  method: PUT
  name: replace-audio-transcript-v1-audios-audio-id-tran
  path: /v1/audios/{audio_id}/transcript/replace
- description: Send message to AI Insights
  method: POST
  name: chat-ai-insights-v2-media-type-media-id-ai-insig
  path: /v2/{media_type}/{media_id}/ai-insights
- description: Get AI Insights conversation history
  method: GET
  name: get-ai-insights-history-v2-media-type-media-id-a
  path: /v2/{media_type}/{media_id}/ai-insights
- description: Update Speaker Face Match
  method: PUT
  name: update-speaker-face-match-v2-videos-video-id-spe
  path: /v2/videos/{video_id}/speaker-face-match
- description: Trigger Speaker Face Match
  method: POST
  name: trigger-speaker-face-match-v2-videos-video-id-sp
  path: /v2/videos/{video_id}/speaker-face-match
- description: Trigger Personality Analysis
  method: POST
  name: trigger-personality-analysis-v2-videos-video-id-
  path: /v2/videos/{video_id}/personality/analyze
personas: []
provider_name: Imentiv AI
provider_slug: imentiv-ai
search_terms:
- list texts v1 texts get
- reprocess image v1 images image id put
- delete faces
- reprocess audio v1 audios audio id put
- get ai insights conversation history
- list videos
- delete text
- upload image v2 images post
- emotion detection
- list audios
- get annotated video
- get single frame
- edit image metadata v1 images image id metadata
- get audio emotion insights
- trigger speaker face match v2 videos video id sp
- api
- send message to ai insights
- get text emotion insights
- edit title or description v1 audios audio id met
- reprocess video
- delete image
- upload video v2 videos post
- process highlight v1 videos highlights post
- download image emotion report v1 images image id
- get average emotions v2 videos video id emotions
- delete text v1 texts text id delete
- download highlight video v1 videos video id high
- reprocess image
- edit title or description by id
- generate video emotion analysis report v1 videos
- reprocess video v1 videos video id put
- edit title or description
- delete video v1 videos video id delete
- get image emotion analysis v1 images image id ge
- reprocess text v1 texts text id put
- get ai insights history v2 media type media id a
- get single frame v1 videos video id frames frame
- process highlight
- reprocess text
- get audio emotion insights v1 audios audio id ge
- download text emotion report v1 texts text id re
- send image v1 images image id annotated image ge
- generate pdf report v2 reports pdf media id get
- trigger personality analysis
- edit image metadata
- update speaker face match v2 videos video id spe
- ai
- get annotated video v2 videos video id annotated
- trigger speaker face match
- get video multimodal insights v2 videos video id
- replace audio transcript v1 audios audio id tran
- retrieve emotion intensity
- merge face
- get audio multimodal insights
- imentiv
- upload video
- edit text v1 texts text id emotions put
- list texts
- fetch highlight video v1 videos video id highlig
- update multiple faces v1 videos video id frames
- get valence arousal v1 videos video id valence a
- get audio multimodal insights v2 audios audio id
- update audio transcripts segments
- edit face note
- update highlight video
- update multiple faces
- delete faces v1 videos video id faces delete
- upload audio v2 audios post
- edit text
- replace audio transcript
- update faces names v1 videos video id faces name
- delete an audio
- delete video
- get image emotion analysis
- update emotion per frame v1 videos video id fram
- artificial intelligence
- update speaker names v1 audios audio id speakers
- upload text
- machine learning
- get average emotions
- upload audio
- list audios v1 audios get
- update faces names
- get text emotion insights v1 texts text id get
- delete audio segment
- get video emotion insights
- update speaker face match
- list images
- delete an audio v1 audios audio id delete
- get multiple frame v1 videos video id frames get
- trigger personality analysis v2 videos video id
- get video multimodal insights
- add note to specific face v1 images image id fac
- download video emotion analysis report
- download text emotion report
- video analysis
- merge face v1 videos video id faces put
- get video emotion insights v1 videos video id ge
- fetch highlight video
- delete audio segment v1 audios audio id segment
- upload image
- download highlight video
- edit face note v1 videos video id frames frame i
- retrieve domination emotion for a specific frame
- reprocess audio
- download audio emotion report
- update audio transcripts segments v1 audios audi
- add note to specific face
- update highlight video v1 videos video id highli
- list videos v1 videos get
- delete image v1 images image id delete
- download video emotion analysis report v1 videos
- download audio emotion report v1 audios audio id
- upload text v2 texts post
- retrieve emotion intensity v1 videos video id fr
- update emotion per frame
- get multiple frame
- download image emotion report
- send image
- get valence arousal
- generate pdf report
- update speaker names
- edit title or description by id v1 videos video
- list images v1 images get
- chat ai insights v2 media type media id ai insig
- generate video emotion analysis report
slug: imentiv-ai-capability
source_filename: imentiv-ai-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Welcome to Imentiv AI\n  description: '# Welcome to Imentiv AI Imentiv AI is an advanced Emotion AI platform that leverages deep learning to analyze\n    human emotions across multiple media formats, including video, audio, images, and text. By interpreting facial expressions,\n    vocal tones, and linguistic cues, it provides detailed emotional insights to support use cases such as content creation,\n    marketing optimization, education, mental health assessments, and more. Imentiv AI offers a suite of Emotion Recognition\n    APIs that allow developers and businesses to seamlessly integrate advanced emotion analysis into their applications, enablin'\n  tags:\n  - Imentiv\n  - Ai\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: imentiv-ai\n    baseUri: https://api.example.com\n    description: Welcome to Imentiv AI HTTP API.\n    authentication:\n      type: apikey\n\
  \      in: header\n      name: X-API-Key\n      value: '{{IMENTIV_AI_TOKEN}}'\n    resources:\n    - name: v2-videos\n      path: /v2/videos\n      operations:\n      - name: upload-video-v2-videos-post\n        method: POST\n        description: Upload Video\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos\n      path: /v1/videos\n      operations:\n      - name: list-videos-v1-videos-get\n        method: GET\n        description: List Videos\n        inputParameters:\n        - name: offset_video_id\n          in: query\n          type: string\n          description: The ID of the reference video from which to paginate forward/backward\n        - name: page_size\n          in: query\n          type: integer\n          description: 'Number of results to return (default: 10)'\n        - name: direction\n          in: query\n          type: string\n          description: 'Pagination direction:\
  \ forward (default) or backward'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-video-id\n      path: /v1/videos/{video_id}\n      operations:\n      - name: get-video-emotion-insights-v1-videos-video-id-ge\n        method: GET\n        description: Get Video Emotion Insights\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique ID of the video to be fetched\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-video-v1-videos-video-id-delete\n        method: DELETE\n        description: Delete Video\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique ID of the video to be deleted.\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reprocess-video-v1-videos-video-id-put\n        method: PUT\n        description: Reprocess Video\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the video to reprocess\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-videos-video-id-multimodal-analytics\n      path: /v2/videos/{video_id}/multimodal-analytics\n      operations:\n      - name: get-video-multimodal-insights-v2-videos-video-id\n        method: GET\n        description: Get Video Multimodal Insights\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique ID of the video\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-videos-video-id-emotions-average\n      path: /v2/videos/{video_id}/emotions/average\n      operations:\n      - name: get-average-emotions-v2-videos-video-id-emotions\n        method: GET\n        description: Get Average Emotions\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique video ID of the video for which average emotions are to be calculated\n        - name: face_id\n          in: query\n          type: integer\n          description: Optional face ID to calculate average emotions for a specific face\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-videos-video-id-annotated-video\n      path: /v2/videos/{video_id}/annotated_video\n      operations:\n\
  \      - name: get-annotated-video-v2-videos-video-id-annotated\n        method: GET\n        description: Get Annotated Video\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique video ID of the video\n        - name: callback_url\n          in: query\n          type: string\n          description: Optional callback URL to notify when annotated video generation is complete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-video-id-valence-arousal\n      path: /v1/videos/{video_id}/valence_arousal\n      operations:\n      - name: get-valence-arousal-v1-videos-video-id-valence-a\n        method: GET\n        description: Get Valence Arousal\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The\
  \ unique video ID of the video whose emotion intensity is to be fetched\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-video-id-frames\n      path: /v1/videos/{video_id}/frames\n      operations:\n      - name: get-multiple-frame-v1-videos-video-id-frames-get\n        method: GET\n        description: Get Multiple Frame\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique video ID of the video for which the frames to be fetched\n        - name: start_frame\n          in: query\n          type: string\n          description: The frame number from which retrieval should begin. Defaults to the start of the video if not provided.\n        - name: length\n          in: query\n          type: string\n          description: The number of frames to retrieve, starting from 'start_frame'. If\
  \ omitted, all available frames will\n            be returned.\n        - name: face_ids\n          in: query\n          type: string\n          description: Optional comma-separated list of face IDs (e.g., '1,2,3')\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-video-id-frames-frame-id\n      path: /v1/videos/{video_id}/frames/{frame_id}\n      operations:\n      - name: get-single-frame-v1-videos-video-id-frames-frame\n        method: GET\n        description: Get Single Frame\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique video ID of the video for which the frame to be fetched.\n        - name: frame_id\n          in: path\n          type: string\n          required: true\n          description: The unique frame ID of the frame to be fetched.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-video-id-frames-frame-id-dominant-emot\n      path: /v1/videos/{video_id}/frames/{frame_id}/dominant_emotion\n      operations:\n      - name: retrieve-domination-emotion-for-a-specific-frame\n        method: GET\n        description: Retrieve Domination Emotion For A Specific Frame\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the video from which the frame’s dominant emotion is to be fetched.\n        - name: frame_id\n          in: path\n          type: string\n          required: true\n          description: The unique id of the frame from which the dominant emotion is to be fetched.\n        - name: face_id\n          in: query\n          type: string\n          description: The id of the face whose dominant emotion is to be retrieved. If not provided,\
  \ the dominant emotion\n            for the entire frame will be returned.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-video-id-frames-frame-id-valence-arous\n      path: /v1/videos/{video_id}/frames/{frame_id}/valence_arousal\n      operations:\n      - name: retrieve-emotion-intensity-v1-videos-video-id-fr\n        method: GET\n        description: Retrieve Emotion Intensity\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique video ID of the video for which the frame's valence, arousal, and intensity are to be fetched.\n        - name: frame_id\n          in: path\n          type: string\n          required: true\n          description: The unique frame ID of the frame from which to fetch the valence, arousal, and intensity.\n        - name: face_id\n          in: query\n    \
  \      type: string\n          description: The ID of the face whose valence, arousal, and intensity are to be retrieved. If not provided, these\n            values for the entire frame will be returned.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-video-id-frames-frame-id-faces-face-id\n      path: /v1/videos/{video_id}/frames/{frame_id}/faces/{face_id}/emotions\n      operations:\n      - name: update-emotion-per-frame-v1-videos-video-id-fram\n        method: PUT\n        description: Update Emotion Per Frame\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique video ID of the video.\n        - name: frame_id\n          in: path\n          type: string\n          required: true\n          description: The unique frame ID of the frame.\n        - name: face_id\n          in: path\n\
  \          type: string\n          required: true\n          description: The unique face ID of the face in the frame.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-video-id-frames-frame-id-faces-face-id\n      path: /v1/videos/{video_id}/frames/{frame_id}/faces/{face_id}/note\n      operations:\n      - name: edit-face-note-v1-videos-video-id-frames-frame-i\n        method: PUT\n        description: Edit Face Note\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique video id of the video.\n        - name: frame_id\n          in: path\n          type: string\n          required: true\n          description: The unique id of the frame inside the video.\n        - name: face_id\n          in: path\n          type: string\n          required: true\n          description: The unique id\
  \ of the face inside the frame. Use '0' to add a note to the entire frame instead of a\n            specific face.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-video-id-frames-faces\n      path: /v1/videos/{video_id}/frames/faces\n      operations:\n      - name: update-multiple-faces-v1-videos-video-id-frames-\n        method: PUT\n        description: Update Multiple Faces\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique video ID of the video in which face ID to be changed\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-video-id-faces\n      path: /v1/videos/{video_id}/faces\n      operations:\n      - name: merge-face-v1-videos-video-id-faces-put\n        method: PUT\n    \
  \    description: Merge Face\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique video ID of the video.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-faces-v1-videos-video-id-faces-delete\n        method: DELETE\n        description: Delete Faces\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the video from which faces will be deleted.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-video-id-faces-names\n      path: /v1/videos/{video_id}/faces/names\n      operations:\n      - name: update-faces-names-v1-videos-video-id-faces-name\n        method: PUT\n      \
  \  description: Update Faces Names\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique video ID of the video.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-highlights\n      path: /v1/videos/highlights\n      operations:\n      - name: process-highlight-v1-videos-highlights-post\n        method: POST\n        description: Process Highlight\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-video-id-highlights\n      path: /v1/videos/{video_id}/highlights\n      operations:\n      - name: fetch-highlight-video-v1-videos-video-id-highlig\n        method: GET\n        description: Fetch Highlight Video\n        inputParameters:\n        - name: video_id\n          in: path\n          type:\
  \ string\n          required: true\n          description: The video id to get the highlight video url\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-highlight-video-v1-videos-video-id-highli\n        method: PUT\n        description: Update Highlight Video\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique video id of the video for which the update highlight video to be edited.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-video-id-highlight-video\n      path: /v1/videos/{video_id}/highlight_video\n      operations:\n      - name: download-highlight-video-v1-videos-video-id-high\n        method: GET\n        description: Download Highlight Video\n        inputParameters:\n     \
  \   - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The video id to download the highlight video.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-video-id-metadata\n      path: /v1/videos/{video_id}/metadata\n      operations:\n      - name: edit-title-or-description-by-id-v1-videos-video-\n        method: PUT\n        description: Edit Title Or Description By Id\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: Provide the video ID to edit or title and description of the audio\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-videos-video-id-report\n      path: /v1/videos/{video_id}/report\n      operations:\n      - name: generate-video-emotion-analysis-report-v1-videos\n\
  \        method: POST\n        description: Generate Video Emotion Analysis Report\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: The unique video ID of the video whose analysis report is to be generated.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: download-video-emotion-analysis-report-v1-videos\n        method: GET\n        description: Download Video Emotion Analysis Report\n        inputParameters:\n        - name: video_id\n          in: path\n          type: string\n          required: true\n          description: Provide the video ID to download analysis\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-audios\n      path: /v2/audios\n      operations:\n      - name: upload-audio-v2-audios-post\n\
  \        method: POST\n        description: Upload Audio\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-audios\n      path: /v1/audios\n      operations:\n      - name: list-audios-v1-audios-get\n        method: GET\n        description: List Audios\n        inputParameters:\n        - name: offset_audio_id\n          in: query\n          type: string\n          description: The ID of the reference audio from which to paginate forward/backward\n        - name: page_size\n          in: query\n          type: integer\n          description: 'Number of results to return (default: 20, max: 100)'\n        - name: direction\n          in: query\n          type: string\n          description: 'Pagination direction: forward (default) or backward'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-audios-audio-id\n\
  \      path: /v1/audios/{audio_id}\n      operations:\n      - name: get-audio-emotion-insights-v1-audios-audio-id-ge\n        method: GET\n        description: Get Audio Emotion Insights\n        inputParameters:\n        - name: audio_id\n          in: path\n          type: string\n          required: true\n          description: The unique ID of the uploaded audio\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reprocess-audio-v1-audios-audio-id-put\n        method: PUT\n        description: Reprocess Audio\n        inputParameters:\n        - name: audio_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the audio to reprocess\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-an-audio-v1-audios-audio-id-delete\n        method:\
  \ DELETE\n        description: Delete An Audio\n        inputParameters:\n        - name: audio_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the audio to be deleted\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-audios-audio-id-multimodal-analytics\n      path: /v2/audios/{audio_id}/multimodal-analytics\n      operations:\n      - name: get-audio-multimodal-insights-v2-audios-audio-id\n        method: GET\n        description: Get Audio Multimodal Insights\n        inputParameters:\n        - name: audio_id\n          in: path\n          type: string\n          required: true\n          description: The unique ID of the audio\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-audios-audio-id-segment-index\n      path: /v1/audios/{audio_id}/{segment_index}\n\
  \      operations:\n      - name: delete-audio-segment-v1-audios-audio-id-segment-\n        method: DELETE\n        description: Delete Audio Segment\n        inputParameters:\n        - name: audio_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the audio file\n        - name: segment_index\n          in: path\n          type: integer\n          required: true\n          description: The index of the segment to delete (0-based indexing)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-audios-audio-id-transcript\n      path: /v1/audios/{audio_id}/transcript\n      operations:\n      - name: update-audio-transcripts-segments-v1-audios-audi\n        method: PUT\n        description: Update Audio Transcripts Segments\n        inputParameters:\n        - name: audio_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Unique identifier of the audio file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-audios-audio-id-speakers-names\n      path: /v1/audios/{audio_id}/speakers/names\n      operations:\n      - name: update-speaker-names-v1-audios-audio-id-speakers\n        method: PUT\n        description: Update Speaker Names\n        inputParameters:\n        - name: audio_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the audio file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-audios-audio-id-metadata\n      path: /v1/audios/{audio_id}/metadata\n      operations:\n      - name: edit-title-or-description-v1-audios-audio-id-met\n        method: PUT\n        description: Edit Title Or Description\n        inputParameters:\n\
  \        - name: audio_id\n          in: path\n          type: string\n          required: true\n          description: Provide the audio ID to edit the title or description of the audio\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-audios-audio-id-report\n      path: /v1/audios/{audio_id}/report\n      operations:\n      - name: download-audio-emotion-report-v1-audios-audio-id\n        method: GET\n        description: Download Audio Emotion Report\n        inputParameters:\n        - name: audio_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the audio file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-texts\n      path: /v2/texts\n      operations:\n      - name: upload-text-v2-texts-post\n        method: POST\n        description:\
  \ Upload Text\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-texts\n      path: /v1/texts\n      operations:\n      - name: list-texts-v1-texts-get\n        method: GET\n        description: List Texts\n        inputParameters:\n        - name: start_after\n          in: query\n          type: string\n          description: The ID of the reference text from which to paginate forward/backward\n        - name: page_size\n          in: query\n          type: integer\n          description: 'Number of results to return (default: 10)'\n        - name: direction\n          in: query\n          type: string\n          description: 'Pagination direction: forward (default) or backward'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-texts-text-id\n      path: /v1/texts/{text_id}\n      operations:\n      -\
  \ name: get-text-emotion-insights-v1-texts-text-id-get\n        method: GET\n        description: Get Text Emotion Insights\n        inputParameters:\n        - name: text_id\n          in: path\n          type: string\n          required: true\n          description: The unique ID of the text.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-text-v1-texts-text-id-delete\n        method: DELETE\n        description: Delete Text\n        inputParameters:\n        - name: text_id\n          in: path\n          type: string\n          required: true\n          description: The unique text ID of the text.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reprocess-text-v1-texts-text-id-put\n        method: PUT\n        description: Reprocess Text\n        inputParameters:\n        - name: text_id\n  \
  \        in: path\n          type: string\n          required: true\n          description: The unique ID of the text.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-images\n      path: /v2/images\n      operations:\n      - name: upload-image-v2-images-post\n        method: POST\n        description: Upload Image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-images\n      path: /v1/images\n      operations:\n      - name: list-images-v1-images-get\n        method: GET\n        description: List Images\n        inputParameters:\n        - name: start_after\n          in: query\n          type: string\n          description: ID of the last image from the previous page. Fetches results after this ID.\n        - name: page_size\n          in: query\n          type: integer\n          description: Number\
  \ of results to return per page. The default is 10.\n        - name: direction\n          in: query\n          type: string\n          description: 'Pagination direction: ''forward'' or ''backward''. Default is ''forward'''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-images-image-id\n      path: /v1/images/{image_id}\n      operations:\n      - name: get-image-emotion-analysis-v1-images-image-id-ge\n        method: GET\n        description: Get Image Emotion Analysis\n        inputParameters:\n        - name: image_id\n          in: path\n          type: string\n          required: true\n          description: Unique ID of the image to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-image-v1-images-image-id-delete\n        method: DELETE\n        description: Delete Image\n     \
  \   inputParameters:\n        - name: image_id\n          in: path\n          type: string\n          required: true\n          description: Unique ID of the image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reprocess-image-v1-images-image-id-put\n        method: PUT\n        description: Reprocess Image\n        inputParameters:\n        - name: image_id\n          in: path\n          type: string\n          required: true\n          description: The unique image ID of the image.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-images-image-id-annotated-image\n      path: /v1/images/{image_id}/annotated_image\n      operations:\n      - name: send-image-v1-images-image-id-annotated-image-ge\n        method: GET\n        description: Send Image\n        inputParameters:\n        - name: image_id\n\
  \          in: path\n          type: string\n          required: true\n          description: Unique ID of the image.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-images-image-id-faces-face-id-note\n      path: /v1/images/{image_id}/faces/{face_id}/note\n      operations:\n      - name: add-note-to-specific-face-v1-images-image-id-fac\n        method: PUT\n        description: Add Note To Specific Face\n        inputParameters:\n        - name: image_id\n          in: path\n          type: string\n          required: true\n          description: The unique image ID of the image\n        - name: face_id\n          in: path\n          type: string\n          required: true\n          description: Unique ID of the face within the image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-images-image-id-metadata\n\
  \      path: /v1/images/{image_id}/metadata\n      operations:\n      - name: edit-image-metadata-v1-images-image-id-metadata-\n        method: PUT\n        description: Edit Image Metadata\n        inputParameters:\n        - name: image_id\n          in: path\n          type: string\n          required: true\n          description: Provide the image ID to edit the title or description of the image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-images-image-id-report\n      path: /v1/images/{image_id}/report\n      operations:\n      - name: download-image-emotion-report-v1-images-image-id\n        method: GET\n        description: Download Image Emotion Report\n        inputParameters:\n        - name: image_id\n          in: path\n          type: string\n          required: true\n          description: Unique ID of the image\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n    - name: v2-reports-pdf-media-id\n      path: /v2/reports/pdf/{media_id}\n      operations:\n      - name: generate-pdf-report-v2-reports-pdf-media-id-get\n        method: GET\n        description: Generate Pdf Report\n        inputParameters:\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the media\n        - name: media_type\n          in: query\n          type: string\n          required: true\n          description: 'Type: Only ''video'' is allowed at present'\n        - name: callback_url\n          in: query\n          type: string\n          description: Callback URL for completion notification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-texts-text-id-emotions\n      path: /v1/texts/{text_id}/emotions\n      operations:\n\
  \      - name: edit-text-v1-texts-text-id-emotions-put\n        method: PUT\n        description: Edit Text\n        inputParameters:\n        - name: text_id\n          in: path\n          type: string\n          required: true\n          description: The unique text ID of the text.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-texts-text-id-report\n      path: /v1/texts/{text_id}/report\n      operations:\n      - name: download-text-emotion-report-v1-texts-text-id-re\n        method: GET\n        description: Download Text Emotion Report\n        inputParameters:\n        - name: text_id\n          in: path\n          type: string\n          required: true\n          description: The unique ID of the text.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-audios-audio-id-transcript-replace\n    \
  \  path: /v1/audios/{audio_id}/transcript/replace\n      operations:\n      - name: replace-audio-transcript-v1-audios-audio-id-tran\n        method: PUT\n        description: Replace Audio Transcript\n        inputParameters:\n        - name: audio_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the audio file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-media-type-media-id-ai-insights\n      path: /v2/{media_type}/{media_id}/ai-insights\n      operations:\n      - name: chat-ai-insights-v2-media-type-media-id-ai-insig\n        me\n\n# --- truncated at 32 KB (94 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/imentiv-ai/refs/heads/main/capabilities/imentiv-ai-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/imentiv-ai/refs/heads/main/capabilities/imentiv-ai-capability.yaml
tags:
- Imentiv
- Ai
- API
tools:
- description: Upload Video
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: upload-video-v2-videos-post
- description: List Videos
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-videos-v1-videos-get
- description: Get Video Emotion Insights
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-video-emotion-insights-v1-videos-video-id-ge
- description: Delete Video
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-video-v1-videos-video-id-delete
- description: Reprocess Video
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: reprocess-video-v1-videos-video-id-put
- description: Get Video Multimodal Insights
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-video-multimodal-insights-v2-videos-video-id
- description: Get Average Emotions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-average-emotions-v2-videos-video-id-emotions
- description: Get Annotated Video
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-annotated-video-v2-videos-video-id-annotated
- description: Get Valence Arousal
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-valence-arousal-v1-videos-video-id-valence-a
- description: Get Multiple Frame
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-multiple-frame-v1-videos-video-id-frames-get
- description: Get Single Frame
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-single-frame-v1-videos-video-id-frames-frame
- description: Retrieve Domination Emotion For A Specific Frame
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrieve-domination-emotion-for-a-specific-frame
- description: Retrieve Emotion Intensity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrieve-emotion-intensity-v1-videos-video-id-fr
- description: Update Emotion Per Frame
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-emotion-per-frame-v1-videos-video-id-fram
- description: Edit Face Note
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: edit-face-note-v1-videos-video-id-frames-frame-i
- description: Update Multiple Faces
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-multiple-faces-v1-videos-video-id-frames-
- description: Merge Face
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: merge-face-v1-videos-video-id-faces-put
- description: Delete Faces
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-faces-v1-videos-video-id-faces-delete
- description: Update Faces Names
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-faces-names-v1-videos-video-id-faces-name
- description: Process Highlight
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: process-highlight-v1-videos-highlights-post
- description: Fetch Highlight Video
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-highlight-video-v1-videos-video-id-highlig
- description: Update Highlight Video
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-highlight-video-v1-videos-video-id-highli
- description: Download Highlight Video
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: download-highlight-video-v1-videos-video-id-high
- description: Edit Title Or Description By Id
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: edit-title-or-description-by-id-v1-videos-video-
- description: Generate Video Emotion Analysis Report
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generate-video-emotion-analysis-report-v1-videos
- description: Download Video Emotion Analysis Report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: download-video-emotion-analysis-report-v1-videos
- description: Upload Audio
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: upload-audio-v2-audios-post
- description: List Audios
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-audios-v1-audios-get
- description: Get Audio Emotion Insights
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-audio-emotion-insights-v1-audios-audio-id-ge
- description: Reprocess Audio
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: reprocess-audio-v1-audios-audio-id-put
- description: Delete An Audio
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-an-audio-v1-audios-audio-id-delete
- description: Get Audio Multimodal Insights
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-audio-multimodal-insights-v2-audios-audio-id
- description: Delete Audio Segment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-audio-segment-v1-audios-audio-id-segment-
- description: Update Audio Transcripts Segments
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-audio-transcripts-segments-v1-audios-audi
- description: Update Speaker Names
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-speaker-names-v1-audios-audio-id-speakers
- description: Edit Title Or Description
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: edit-title-or-description-v1-audios-audio-id-met
- description: Download Audio Emotion Report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: download-audio-emotion-report-v1-audios-audio-id
- description: Upload Text
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: upload-text-v2-texts-post
- description: List Texts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-texts-v1-texts-get
- description: Get Text Emotion Insights
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-text-emotion-insights-v1-texts-text-id-get
- description: Delete Text
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-text-v1-texts-text-id-delete
- description: Reprocess Text
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: reprocess-text-v1-texts-text-id-put
- description: Upload Image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: upload-image-v2-images-post
- description: List Images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-images-v1-images-get
- description: Get Image Emotion Analysis
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-image-emotion-analysis-v1-images-image-id-ge
- description: Delete Image
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-image-v1-images-image-id-delete
- description: Reprocess Image
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: reprocess-image-v1-images-image-id-put
- description: Send Image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: send-image-v1-images-image-id-annotated-image-ge
- description: Add Note To Specific Face
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: add-note-to-specific-face-v1-images-image-id-fac
- description: Edit Image Metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: edit-image-metadata-v1-images-image-id-metadata-
- description: Download Image Emotion Report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: download-image-emotion-report-v1-images-image-id
- description: Generate Pdf Report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: generate-pdf-report-v2-reports-pdf-media-id-get
- description: Edit Text
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: edit-text-v1-texts-text-id-emotions-put
- description: Download Text Emotion Report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: download-text-emotion-report-v1-texts-text-id-re
- description: Replace Audio Transcript
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replace-audio-transcript-v1-audios-audio-id-tran
- description: Send message to AI Insights
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: chat-ai-insights-v2-media-type-media-id-ai-insig
- description: Get AI Insights conversation history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-ai-insights-history-v2-media-type-media-id-a
- description: Update Speaker Face Match
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-speaker-face-match-v2-videos-video-id-spe
- description: Trigger Speaker Face Match
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: trigger-speaker-face-match-v2-videos-video-id-sp
- description: Trigger Personality Analysis
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: trigger-personality-analysis-v2-videos-video-id-
---
