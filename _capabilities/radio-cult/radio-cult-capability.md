---
categories: []
consumed_apis: []
description: Power your online radio station website with the Radio Cult API. Manage artists, schedules, media, playlists, recordings, and live streaming metadata.
layout: capability
name: Radio Cult API
operations:
- description: Retrieve all artists
  method: GET
  name: get-api-station-stationid-artists
  path: /api/station/{stationId}/artists
- description: Create an artist
  method: POST
  name: post-api-station-stationid-artists
  path: /api/station/{stationId}/artists
- description: Fetch artist by ID or slug
  method: GET
  name: get-api-station-stationid-artists-artistid
  path: /api/station/{stationId}/artists/{artistId}
- description: Get an artist's scheduled events
  method: GET
  name: get-api-station-stationid-artists-artistid-sched
  path: /api/station/{stationId}/artists/{artistId}/schedule
- description: Get events in a date range
  method: GET
  name: get-api-station-stationid-schedule
  path: /api/station/{stationId}/schedule
- description: Current live broadcast status and metadata
  method: GET
  name: get-api-station-stationid-schedule-live
  path: /api/station/{stationId}/schedule/live
- description: Retrieve all media tracks
  method: GET
  name: get-api-station-stationid-media-track
  path: /api/station/{stationId}/media/track
- description: Upload an MP3 track
  method: POST
  name: post-api-station-stationid-media-track
  path: /api/station/{stationId}/media/track
- description: Get a signed download URL for a track
  method: GET
  name: get-api-station-stationid-media-track-trackid-do
  path: /api/station/{stationId}/media/track/{trackId}/download-url
- description: Tag a media track
  method: PUT
  name: put-api-station-stationid-media-track-trackid-ta
  path: /api/station/{stationId}/media/track/{trackId}/tag/{tagId}
- description: Upload a track to Soundcloud
  method: POST
  name: post-api-station-stationid-media-track-trackid-u
  path: /api/station/{stationId}/media/track/{trackId}/upload/soundcloud
- description: Retrieve all playlists
  method: GET
  name: get-api-station-stationid-media-playlist
  path: /api/station/{stationId}/media/playlist
- description: Add an entry to a playlist
  method: POST
  name: post-api-station-stationid-media-playlist-playli
  path: /api/station/{stationId}/media/playlist/{playlistId}/entry
- description: Clear all entries from a playlist
  method: DELETE
  name: delete-api-station-stationid-media-playlist-play
  path: /api/station/{stationId}/media/playlist/{playlistId}/entries
- description: Retrieve all tags
  method: GET
  name: get-api-station-stationid-media-tag
  path: /api/station/{stationId}/media/tag
- description: Retrieve recordings
  method: GET
  name: get-api-station-stationid-media-recording
  path: /api/station/{stationId}/media/recording
- description: Get a signed download URL for a recording
  method: GET
  name: get-api-station-stationid-media-recording-record
  path: /api/station/{stationId}/media/recording/{recordingId}/download-url
- description: Recent track playback history
  method: GET
  name: get-api-station-stationid-streaming-history-late
  path: /api/station/{stationId}/streaming/history/latest-results
personas: []
provider_name: Radio Cult
provider_slug: radio-cult
search_terms:
- retrieve all media tracks
- streaming
- retrieve all tags
- get api station stationid schedule live
- get api station stationid media track
- get api station stationid media track trackid do
- put api station stationid media track trackid ta
- get api station stationid media playlist
- post api station stationid artists
- get api station stationid schedule
- upload an mp3 track
- upload a track to soundcloud
- get api station stationid media tag
- api
- get a signed download url for a track
- get api station stationid artists artistid sched
- retrieve recordings
- get api station stationid streaming history late
- tag a media track
- create an artist
- get api station stationid artists artistid
- retrieve all artists
- get an artist's scheduled events
- clear all entries from a playlist
- add an entry to a playlist
- post api station stationid media track
- audio
- get api station stationid artists
- music
- cult
- post api station stationid media track trackid u
- post api station stationid media playlist playli
- recent track playback history
- radio
- get events in a date range
- fetch artist by id or slug
- get a signed download url for a recording
- retrieve all playlists
- broadcasting
- current live broadcast status and metadata
- delete api station stationid media playlist play
- get api station stationid media recording
- get api station stationid media recording record
slug: radio-cult-capability
source_filename: radio-cult-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Radio Cult API\n  description: Power your online radio station website with the Radio Cult API. Manage artists, schedules, media, playlists,\n    recordings, and live streaming metadata.\n  tags:\n  - Radio\n  - Cult\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: radio-cult\n    baseUri: https://api.radiocult.fm\n    description: Radio Cult API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{RADIO_CULT_TOKEN}}'\n    resources:\n    - name: api-station-stationid-artists\n      path: /api/station/{stationId}/artists\n      operations:\n      - name: get-api-station-stationid-artists\n        method: GET\n        description: Retrieve all artists\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: post-api-station-stationid-artists\n        method: POST\n        description: Create an artist\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-station-stationid-artists-artistid\n      path: /api/station/{stationId}/artists/{artistId}\n      operations:\n      - name: get-api-station-stationid-artists-artistid\n        method: GET\n        description: Fetch artist by ID or slug\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        - name: artistId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: api-station-stationid-artists-artistid-schedule\n      path: /api/station/{stationId}/artists/{artistId}/schedule\n      operations:\n      - name: get-api-station-stationid-artists-artistid-sched\n        method: GET\n        description: Get an artist's scheduled events\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        - name: artistId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-station-stationid-schedule\n      path: /api/station/{stationId}/schedule\n      operations:\n      - name: get-api-station-stationid-schedule\n        method: GET\n        description: Get events in a date range\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n         \
  \ required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-station-stationid-schedule-live\n      path: /api/station/{stationId}/schedule/live\n      operations:\n      - name: get-api-station-stationid-schedule-live\n        method: GET\n        description: Current live broadcast status and metadata\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-station-stationid-media-track\n      path: /api/station/{stationId}/media/track\n      operations:\n      - name: get-api-station-stationid-media-track\n        method: GET\n        description: Retrieve all media tracks\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n        \
  \  required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-station-stationid-media-track\n        method: POST\n        description: Upload an MP3 track\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-station-stationid-media-track-trackid-downlo\n      path: /api/station/{stationId}/media/track/{trackId}/download-url\n      operations:\n      - name: get-api-station-stationid-media-track-trackid-do\n        method: GET\n        description: Get a signed download URL for a track\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        - name: trackId\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-station-stationid-media-track-trackid-tag-ta\n      path: /api/station/{stationId}/media/track/{trackId}/tag/{tagId}\n      operations:\n      - name: put-api-station-stationid-media-track-trackid-ta\n        method: PUT\n        description: Tag a media track\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        - name: trackId\n          in: path\n          type: string\n          required: true\n        - name: tagId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-station-stationid-media-track-trackid-upload\n      path: /api/station/{stationId}/media/track/{trackId}/upload/soundcloud\n\
  \      operations:\n      - name: post-api-station-stationid-media-track-trackid-u\n        method: POST\n        description: Upload a track to Soundcloud\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        - name: trackId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-station-stationid-media-playlist\n      path: /api/station/{stationId}/media/playlist\n      operations:\n      - name: get-api-station-stationid-media-playlist\n        method: GET\n        description: Retrieve all playlists\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: api-station-stationid-media-playlist-playlistid-\n      path: /api/station/{stationId}/media/playlist/{playlistId}/entry\n      operations:\n      - name: post-api-station-stationid-media-playlist-playli\n        method: POST\n        description: Add an entry to a playlist\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        - name: playlistId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-station-stationid-media-playlist-playlistid-\n      path: /api/station/{stationId}/media/playlist/{playlistId}/entries\n      operations:\n      - name: delete-api-station-stationid-media-playlist-play\n        method: DELETE\n        description: Clear all entries from a playlist\n        inputParameters:\n        - name: stationId\n          in:\
  \ path\n          type: string\n          required: true\n        - name: playlistId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-station-stationid-media-tag\n      path: /api/station/{stationId}/media/tag\n      operations:\n      - name: get-api-station-stationid-media-tag\n        method: GET\n        description: Retrieve all tags\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-station-stationid-media-recording\n      path: /api/station/{stationId}/media/recording\n      operations:\n      - name: get-api-station-stationid-media-recording\n        method: GET\n        description: Retrieve recordings\n\
  \        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-station-stationid-media-recording-recordingi\n      path: /api/station/{stationId}/media/recording/{recordingId}/download-url\n      operations:\n      - name: get-api-station-stationid-media-recording-record\n        method: GET\n        description: Get a signed download URL for a recording\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        - name: recordingId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-station-stationid-streaming-history-latest-r\n      path: /api/station/{stationId}/streaming/history/latest-results\n\
  \      operations:\n      - name: get-api-station-stationid-streaming-history-late\n        method: GET\n        description: Recent track playback history\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: radio-cult-rest\n    description: REST adapter for Radio Cult API.\n    resources:\n    - path: /api/station/{stationId}/artists\n      name: get-api-station-stationid-artists\n      operations:\n      - method: GET\n        name: get-api-station-stationid-artists\n        description: Retrieve all artists\n        call: radio-cult.get-api-station-stationid-artists\n        with:\n          stationId: rest.stationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/artists\n\
  \      name: post-api-station-stationid-artists\n      operations:\n      - method: POST\n        name: post-api-station-stationid-artists\n        description: Create an artist\n        call: radio-cult.post-api-station-stationid-artists\n        with:\n          stationId: rest.stationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/artists/{artistId}\n      name: get-api-station-stationid-artists-artistid\n      operations:\n      - method: GET\n        name: get-api-station-stationid-artists-artistid\n        description: Fetch artist by ID or slug\n        call: radio-cult.get-api-station-stationid-artists-artistid\n        with:\n          stationId: rest.stationId\n          artistId: rest.artistId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/artists/{artistId}/schedule\n      name: get-api-station-stationid-artists-artistid-sched\n      operations:\n\
  \      - method: GET\n        name: get-api-station-stationid-artists-artistid-sched\n        description: Get an artist's scheduled events\n        call: radio-cult.get-api-station-stationid-artists-artistid-sched\n        with:\n          stationId: rest.stationId\n          artistId: rest.artistId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/schedule\n      name: get-api-station-stationid-schedule\n      operations:\n      - method: GET\n        name: get-api-station-stationid-schedule\n        description: Get events in a date range\n        call: radio-cult.get-api-station-stationid-schedule\n        with:\n          stationId: rest.stationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/schedule/live\n      name: get-api-station-stationid-schedule-live\n      operations:\n      - method: GET\n        name: get-api-station-stationid-schedule-live\n \
  \       description: Current live broadcast status and metadata\n        call: radio-cult.get-api-station-stationid-schedule-live\n        with:\n          stationId: rest.stationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/media/track\n      name: get-api-station-stationid-media-track\n      operations:\n      - method: GET\n        name: get-api-station-stationid-media-track\n        description: Retrieve all media tracks\n        call: radio-cult.get-api-station-stationid-media-track\n        with:\n          stationId: rest.stationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/media/track\n      name: post-api-station-stationid-media-track\n      operations:\n      - method: POST\n        name: post-api-station-stationid-media-track\n        description: Upload an MP3 track\n        call: radio-cult.post-api-station-stationid-media-track\n      \
  \  with:\n          stationId: rest.stationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/media/track/{trackId}/download-url\n      name: get-api-station-stationid-media-track-trackid-do\n      operations:\n      - method: GET\n        name: get-api-station-stationid-media-track-trackid-do\n        description: Get a signed download URL for a track\n        call: radio-cult.get-api-station-stationid-media-track-trackid-do\n        with:\n          stationId: rest.stationId\n          trackId: rest.trackId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/media/track/{trackId}/tag/{tagId}\n      name: put-api-station-stationid-media-track-trackid-ta\n      operations:\n      - method: PUT\n        name: put-api-station-stationid-media-track-trackid-ta\n        description: Tag a media track\n        call: radio-cult.put-api-station-stationid-media-track-trackid-ta\n\
  \        with:\n          stationId: rest.stationId\n          trackId: rest.trackId\n          tagId: rest.tagId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/media/track/{trackId}/upload/soundcloud\n      name: post-api-station-stationid-media-track-trackid-u\n      operations:\n      - method: POST\n        name: post-api-station-stationid-media-track-trackid-u\n        description: Upload a track to Soundcloud\n        call: radio-cult.post-api-station-stationid-media-track-trackid-u\n        with:\n          stationId: rest.stationId\n          trackId: rest.trackId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/media/playlist\n      name: get-api-station-stationid-media-playlist\n      operations:\n      - method: GET\n        name: get-api-station-stationid-media-playlist\n        description: Retrieve all playlists\n        call: radio-cult.get-api-station-stationid-media-playlist\n\
  \        with:\n          stationId: rest.stationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/media/playlist/{playlistId}/entry\n      name: post-api-station-stationid-media-playlist-playli\n      operations:\n      - method: POST\n        name: post-api-station-stationid-media-playlist-playli\n        description: Add an entry to a playlist\n        call: radio-cult.post-api-station-stationid-media-playlist-playli\n        with:\n          stationId: rest.stationId\n          playlistId: rest.playlistId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/media/playlist/{playlistId}/entries\n      name: delete-api-station-stationid-media-playlist-play\n      operations:\n      - method: DELETE\n        name: delete-api-station-stationid-media-playlist-play\n        description: Clear all entries from a playlist\n        call: radio-cult.delete-api-station-stationid-media-playlist-play\n\
  \        with:\n          stationId: rest.stationId\n          playlistId: rest.playlistId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/media/tag\n      name: get-api-station-stationid-media-tag\n      operations:\n      - method: GET\n        name: get-api-station-stationid-media-tag\n        description: Retrieve all tags\n        call: radio-cult.get-api-station-stationid-media-tag\n        with:\n          stationId: rest.stationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/media/recording\n      name: get-api-station-stationid-media-recording\n      operations:\n      - method: GET\n        name: get-api-station-stationid-media-recording\n        description: Retrieve recordings\n        call: radio-cult.get-api-station-stationid-media-recording\n        with:\n          stationId: rest.stationId\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /api/station/{stationId}/media/recording/{recordingId}/download-url\n      name: get-api-station-stationid-media-recording-record\n      operations:\n      - method: GET\n        name: get-api-station-stationid-media-recording-record\n        description: Get a signed download URL for a recording\n        call: radio-cult.get-api-station-stationid-media-recording-record\n        with:\n          stationId: rest.stationId\n          recordingId: rest.recordingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/station/{stationId}/streaming/history/latest-results\n      name: get-api-station-stationid-streaming-history-late\n      operations:\n      - method: GET\n        name: get-api-station-stationid-streaming-history-late\n        description: Recent track playback history\n        call: radio-cult.get-api-station-stationid-streaming-history-late\n        with:\n          stationId: rest.stationId\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: radio-cult-mcp\n    transport: http\n    description: MCP adapter for Radio Cult API for AI agent use.\n    tools:\n    - name: get-api-station-stationid-artists\n      description: Retrieve all artists\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-cult.get-api-station-stationid-artists\n      with:\n        stationId: tools.stationId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-api-station-stationid-artists\n      description: Create an artist\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: radio-cult.post-api-station-stationid-artists\n      with:\n        stationId: tools.stationId\n\
  \      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-station-stationid-artists-artistid\n      description: Fetch artist by ID or slug\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-cult.get-api-station-stationid-artists-artistid\n      with:\n        stationId: tools.stationId\n        artistId: tools.artistId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      - name: artistId\n        type: string\n        description: artistId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-station-stationid-artists-artistid-sched\n      description: Get an artist's scheduled events\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: radio-cult.get-api-station-stationid-artists-artistid-sched\n      with:\n        stationId: tools.stationId\n        artistId: tools.artistId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      - name: artistId\n        type: string\n        description: artistId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-station-stationid-schedule\n      description: Get events in a date range\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-cult.get-api-station-stationid-schedule\n      with:\n        stationId: tools.stationId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-station-stationid-schedule-live\n\
  \      description: Current live broadcast status and metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-cult.get-api-station-stationid-schedule-live\n      with:\n        stationId: tools.stationId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-station-stationid-media-track\n      description: Retrieve all media tracks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-cult.get-api-station-stationid-media-track\n      with:\n        stationId: tools.stationId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-api-station-stationid-media-track\n\
  \      description: Upload an MP3 track\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: radio-cult.post-api-station-stationid-media-track\n      with:\n        stationId: tools.stationId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-station-stationid-media-track-trackid-do\n      description: Get a signed download URL for a track\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-cult.get-api-station-stationid-media-track-trackid-do\n      with:\n        stationId: tools.stationId\n        trackId: tools.trackId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      - name: trackId\n        type: string\n        description:\
  \ trackId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-api-station-stationid-media-track-trackid-ta\n      description: Tag a media track\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: radio-cult.put-api-station-stationid-media-track-trackid-ta\n      with:\n        stationId: tools.stationId\n        trackId: tools.trackId\n        tagId: tools.tagId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      - name: trackId\n        type: string\n        description: trackId\n        required: true\n      - name: tagId\n        type: string\n        description: tagId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-api-station-stationid-media-track-trackid-u\n      description: Upload a track to Soundcloud\n      hints:\n       \
  \ readOnly: false\n        destructive: false\n        idempotent: false\n      call: radio-cult.post-api-station-stationid-media-track-trackid-u\n      with:\n        stationId: tools.stationId\n        trackId: tools.trackId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      - name: trackId\n        type: string\n        description: trackId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-station-stationid-media-playlist\n      description: Retrieve all playlists\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-cult.get-api-station-stationid-media-playlist\n      with:\n        stationId: tools.stationId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: post-api-station-stationid-media-playlist-playli\n      description: Add an entry to a playlist\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: radio-cult.post-api-station-stationid-media-playlist-playli\n      with:\n        stationId: tools.stationId\n        playlistId: tools.playlistId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      - name: playlistId\n        type: string\n        description: playlistId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-api-station-stationid-media-playlist-play\n      description: Clear all entries from a playlist\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: radio-cult.delete-api-station-stationid-media-playlist-play\n      with:\n        stationId: tools.stationId\n\
  \        playlistId: tools.playlistId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      - name: playlistId\n        type: string\n        description: playlistId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-station-stationid-media-tag\n      description: Retrieve all tags\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-cult.get-api-station-stationid-media-tag\n      with:\n        stationId: tools.stationId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-station-stationid-media-recording\n      description: Retrieve recordings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: radio-cult.get-api-station-stationid-media-recording\n      with:\n        stationId: tools.stationId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-station-stationid-media-recording-record\n      description: Get a signed download URL for a recording\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-cult.get-api-station-stationid-media-recording-record\n      with:\n        stationId: tools.stationId\n        recordingId: tools.recordingId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      - name: recordingId\n        type: string\n        description: recordingId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: get-api-station-stationid-streaming-history-late\n      description: Recent track playback history\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-cult.get-api-station-stationid-streaming-history-late\n      with:\n        stationId: tools.stationId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    RADIO_CULT_TOKEN: RADIO_CULT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/radio-cult/refs/heads/main/capabilities/radio-cult-capability.yaml
tags:
- Radio
- Cult
- API
tools:
- description: Retrieve all artists
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-station-stationid-artists
- description: Create an artist
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-station-stationid-artists
- description: Fetch artist by ID or slug
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-station-stationid-artists-artistid
- description: Get an artist's scheduled events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-station-stationid-artists-artistid-sched
- description: Get events in a date range
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-station-stationid-schedule
- description: Current live broadcast status and metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-station-stationid-schedule-live
- description: Retrieve all media tracks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-station-stationid-media-track
- description: Upload an MP3 track
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-station-stationid-media-track
- description: Get a signed download URL for a track
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-station-stationid-media-track-trackid-do
- description: Tag a media track
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-api-station-stationid-media-track-trackid-ta
- description: Upload a track to Soundcloud
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-station-stationid-media-track-trackid-u
- description: Retrieve all playlists
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-station-stationid-media-playlist
- description: Add an entry to a playlist
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-station-stationid-media-playlist-playli
- description: Clear all entries from a playlist
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-station-stationid-media-playlist-play
- description: Retrieve all tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-station-stationid-media-tag
- description: Retrieve recordings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-station-stationid-media-recording
- description: Get a signed download URL for a recording
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-station-stationid-media-recording-record
- description: Recent track playback history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-station-stationid-streaming-history-late
---
