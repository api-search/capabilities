---
categories: []
consumed_apis: []
description: Workflow capability for music industry analytics using the Songstats Enterprise API. Provides streaming performance monitoring, audience insights, catalog management, and playlist tracking for artists, tracks, record labels, and collaborators across Spotify, Apple Music, Amazon Music, Deezer, TikTok, and 40,000+ radio stations. Used by A&R teams, label executives, artist managers, and music data analysts.
layout: capability
name: Songstats Music Analytics
operations:
- description: Get basic information about an artist
  method: GET
  name: get-artist-info
  path: /v1/artists
- description: Get current streaming stats for an artist
  method: GET
  name: get-artist-stats
  path: /v1/artists
- description: Get historical streaming stats for an artist
  method: GET
  name: get-artist-historic-stats
  path: /v1/artists
- description: Get audience demographics for an artist
  method: GET
  name: get-artist-audience
  path: /v1/artists
- description: Get detailed audience insights for an artist by country
  method: GET
  name: get-artist-audience-details
  path: /v1/artists
- description: Get full track catalog for an artist
  method: GET
  name: get-artist-catalog
  path: /v1/artists
- description: Get top performing tracks for an artist
  method: GET
  name: get-artist-top-tracks
  path: /v1/artists
- description: Get top playlists featuring an artist
  method: GET
  name: get-artist-top-playlists
  path: /v1/artists
- description: Search for artists by name
  method: GET
  name: search-artists
  path: /v1/artists
- description: Get basic information about a track
  method: GET
  name: get-track-info
  path: /v1/tracks
- description: Get current streaming stats for a track
  method: GET
  name: get-track-stats
  path: /v1/tracks
- description: Get historical streaming stats for a track
  method: GET
  name: get-track-historic-stats
  path: /v1/tracks
- description: Search for tracks by title or artist
  method: GET
  name: search-tracks
  path: /v1/tracks
- description: Get basic information about a record label
  method: GET
  name: get-label-info
  path: /v1/labels
- description: Get current streaming stats for a record label
  method: GET
  name: get-label-stats
  path: /v1/labels
- description: Get track catalog for a record label
  method: GET
  name: get-label-catalog
  path: /v1/labels
- description: Search for record labels by name
  method: GET
  name: search-labels
  path: /v1/labels
personas: []
provider_name: Songstats
provider_slug: songstats
search_terms:
- tracks
- get basic information about a record label
- artists
- get artist info
- get basic information about a track
- search for record labels by name
- get artist historic stats
- playlists
- analytics
- get artist audience details
- get artist audience
- get label catalog
- get historical streaming stats for an artist over a date range
- get top playlists featuring an artist
- record label analytics and data
- get historical streaming stats for a track
- get current streaming stats for a track
- get label info
- get artist stats
- get audience demographics for an artist
- music
- labels
- get current streaming stats for an artist across platforms
- get basic information about an artist
- search labels
- search for music artists by name
- get basic information about a music artist by songstats id or spotify id
- search for music tracks by title or artist name
- get the full track catalog for a record label
- track analytics and data
- get track stats
- search tracks
- get current streaming stats for a record label
- search artists
- get detailed audience insights for an artist by country
- artist analytics and data
- get current streaming stats for an artist
- get track info
- search for tracks by title or artist
- get artist top tracks
- songstats
- search for artists by name
- get track catalog for a record label
- get historical streaming stats for a track over a date range
- get label stats
- get track historic stats
- streaming
- get artist top playlists
- get detailed audience demographics for an artist in a specific country
- get artist catalog
- get full track catalog for an artist
- get historical streaming stats for an artist
- get top performing tracks for an artist
slug: music-analytics
source_filename: music-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Songstats Music Analytics\n  description: Workflow capability for music industry analytics using the Songstats Enterprise API. Provides streaming performance\n    monitoring, audience insights, catalog management, and playlist tracking for artists, tracks, record labels, and collaborators\n    across Spotify, Apple Music, Amazon Music, Deezer, TikTok, and 40,000+ radio stations. Used by A&R teams, label executives,\n    artist managers, and music data analysts.\n  tags:\n  - Songstats\n  - Music\n  - Analytics\n  - Streaming\n  - Artists\n  - Tracks\n  - Labels\n  - Playlists\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SONGSTATS_API_KEY: SONGSTATS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: songstats\n    baseUri: https://api.songstats.com/enterprise/v1\n    description: Songstats Enterprise API v1\n    authentication:\n      type: apikey\n      key: apikey\n      value:\
  \ '{{SONGSTATS_API_KEY}}'\n      placement: header\n    resources:\n    - name: artists\n      path: /artists\n      description: Music artist data and analytics\n      operations:\n      - name: get-artist-info\n        method: GET\n        description: Get basic information about an artist\n        inputParameters:\n        - name: songstats_artist_id\n          in: query\n          type: string\n          required: false\n          description: Songstats artist ID\n        - name: spotify_artist_id\n          in: query\n          type: string\n          required: false\n          description: Spotify artist ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-artist-stats\n        method: GET\n        description: Get current streaming stats for an artist\n        inputParameters:\n        - name: songstats_artist_id\n          in: query\n          type: string\n          required: true\n\
  \          description: Songstats artist ID\n        - name: source\n          in: query\n          type: string\n          required: false\n          description: Streaming platform source filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-artist-historic-stats\n        method: GET\n        description: Get historical streaming stats for an artist\n        inputParameters:\n        - name: songstats_artist_id\n          in: query\n          type: string\n          required: true\n          description: Songstats artist ID\n        - name: source\n          in: query\n          type: string\n          required: false\n          description: Streaming platform source filter\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Start date (YYYY-MM-DD)\n        - name: end_date\n          in: query\n          type: string\n\
  \          required: false\n          description: End date (YYYY-MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-artist-audience\n        method: GET\n        description: Get audience data for an artist\n        inputParameters:\n        - name: songstats_artist_id\n          in: query\n          type: string\n          required: true\n          description: Songstats artist ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-artist-audience-details\n        method: GET\n        description: Get detailed audience insights for an artist by country\n        inputParameters:\n        - name: songstats_artist_id\n          in: query\n          type: string\n          required: true\n          description: Songstats artist ID\n        - name: country_code\n          in: query\n          type:\
  \ string\n          required: true\n          description: ISO 3166-1 alpha-2 country code\n        - name: source\n          in: query\n          type: string\n          required: false\n          description: Platform source filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-artist-catalog\n        method: GET\n        description: Get track catalog of an artist\n        inputParameters:\n        - name: songstats_artist_id\n          in: query\n          type: string\n          required: true\n          description: Songstats artist ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-artist-top-tracks\n        method: GET\n        description: Get top tracks of an artist\n        inputParameters:\n        - name: songstats_artist_id\n          in: query\n          type: string\n        \
  \  required: true\n          description: Songstats artist ID\n        - name: source\n          in: query\n          type: string\n          required: false\n          description: Platform source filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-artist-top-playlists\n        method: GET\n        description: Get top playlists featuring an artist\n        inputParameters:\n        - name: songstats_artist_id\n          in: query\n          type: string\n          required: true\n          description: Songstats artist ID\n        - name: source\n          in: query\n          type: string\n          required: false\n          description: Platform source filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-artists\n        method: GET\n        description: Search for artists by name\n\
  \        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tracks\n      path: /tracks\n      description: Music track data and analytics\n      operations:\n      - name: get-track-info\n        method: GET\n        description: Get basic information about a track\n        inputParameters:\n        - name: songstats_track_id\n          in: query\n          type: string\n          required: false\n          description: Songstats track ID\n        - name: isrc\n          in: query\n          type: string\n          required: false\n          description: ISRC code\n        - name: spotify_track_id\n          in: query\n          type: string\n          required: false\n          description: Spotify track ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-track-stats\n        method: GET\n        description: Get current stats for a track\n        inputParameters:\n        - name: songstats_track_id\n          in: query\n          type: string\n          required: true\n          description: Songstats track ID\n        - name: source\n          in: query\n          type: string\n          required: false\n          description: Platform source filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-track-historic-stats\n        method: GET\n        description: Get historical stats for a track\n        inputParameters:\n        - name: songstats_track_id\n          in: query\n          type: string\n          required: true\n          description: Songstats track ID\n        - name: source\n          in: query\n          type: string\n          required:\
  \ false\n          description: Platform source filter\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Start date (YYYY-MM-DD)\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: End date (YYYY-MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-tracks\n        method: GET\n        description: Search for tracks by title or artist\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: labels\n      path: /labels\n      description: Record label data and analytics\n      operations:\n      - name: get-label-info\n\
  \        method: GET\n        description: Get basic information about a record label\n        inputParameters:\n        - name: songstats_label_id\n          in: query\n          type: string\n          required: false\n          description: Songstats label ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-label-stats\n        method: GET\n        description: Get current stats for a record label\n        inputParameters:\n        - name: songstats_label_id\n          in: query\n          type: string\n          required: true\n          description: Songstats label ID\n        - name: source\n          in: query\n          type: string\n          required: false\n          description: Platform source filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-label-catalog\n        method: GET\n\
  \        description: Get track catalog of a record label\n        inputParameters:\n        - name: songstats_label_id\n          in: query\n          type: string\n          required: true\n          description: Songstats label ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-labels\n        method: GET\n        description: Search for record labels by name\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: songstats-music-analytics-api\n    description: Unified REST API for music industry analytics with Songstats.\n    resources:\n    - path: /v1/artists\n      name: artists\n      description: Artist\
  \ analytics and data\n      operations:\n      - method: GET\n        name: get-artist-info\n        description: Get basic information about an artist\n        call: songstats.get-artist-info\n        with:\n          songstats_artist_id: rest.songstats_artist_id\n          spotify_artist_id: rest.spotify_artist_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-artist-stats\n        description: Get current streaming stats for an artist\n        call: songstats.get-artist-stats\n        with:\n          songstats_artist_id: rest.songstats_artist_id\n          source: rest.source\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-artist-historic-stats\n        description: Get historical streaming stats for an artist\n        call: songstats.get-artist-historic-stats\n        with:\n          songstats_artist_id: rest.songstats_artist_id\n          source: rest.source\n\
  \          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-artist-audience\n        description: Get audience demographics for an artist\n        call: songstats.get-artist-audience\n        with:\n          songstats_artist_id: rest.songstats_artist_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-artist-audience-details\n        description: Get detailed audience insights for an artist by country\n        call: songstats.get-artist-audience-details\n        with:\n          songstats_artist_id: rest.songstats_artist_id\n          country_code: rest.country_code\n          source: rest.source\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-artist-catalog\n        description: Get full track catalog for an artist\n        call:\
  \ songstats.get-artist-catalog\n        with:\n          songstats_artist_id: rest.songstats_artist_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-artist-top-tracks\n        description: Get top performing tracks for an artist\n        call: songstats.get-artist-top-tracks\n        with:\n          songstats_artist_id: rest.songstats_artist_id\n          source: rest.source\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-artist-top-playlists\n        description: Get top playlists featuring an artist\n        call: songstats.get-artist-top-playlists\n        with:\n          songstats_artist_id: rest.songstats_artist_id\n          source: rest.source\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: search-artists\n        description: Search for artists by name\n        call: songstats.search-artists\n\
  \        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tracks\n      name: tracks\n      description: Track analytics and data\n      operations:\n      - method: GET\n        name: get-track-info\n        description: Get basic information about a track\n        call: songstats.get-track-info\n        with:\n          songstats_track_id: rest.songstats_track_id\n          isrc: rest.isrc\n          spotify_track_id: rest.spotify_track_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-track-stats\n        description: Get current streaming stats for a track\n        call: songstats.get-track-stats\n        with:\n          songstats_track_id: rest.songstats_track_id\n          source: rest.source\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-track-historic-stats\n        description:\
  \ Get historical streaming stats for a track\n        call: songstats.get-track-historic-stats\n        with:\n          songstats_track_id: rest.songstats_track_id\n          source: rest.source\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: search-tracks\n        description: Search for tracks by title or artist\n        call: songstats.search-tracks\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/labels\n      name: labels\n      description: Record label analytics and data\n      operations:\n      - method: GET\n        name: get-label-info\n        description: Get basic information about a record label\n        call: songstats.get-label-info\n        with:\n          songstats_label_id: rest.songstats_label_id\n        outputParameters:\n        - type: object\n    \
  \      mapping: $.\n      - method: GET\n        name: get-label-stats\n        description: Get current streaming stats for a record label\n        call: songstats.get-label-stats\n        with:\n          songstats_label_id: rest.songstats_label_id\n          source: rest.source\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-label-catalog\n        description: Get track catalog for a record label\n        call: songstats.get-label-catalog\n        with:\n          songstats_label_id: rest.songstats_label_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: search-labels\n        description: Search for record labels by name\n        call: songstats.search-labels\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: songstats-music-analytics-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted music industry analytics with Songstats.\n    tools:\n    - name: get-artist-info\n      description: Get basic information about a music artist by Songstats ID or Spotify ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: songstats.get-artist-info\n      with:\n        songstats_artist_id: tools.songstats_artist_id\n        spotify_artist_id: tools.spotify_artist_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-artist-stats\n      description: Get current streaming stats for an artist across platforms\n      hints:\n        readOnly: true\n        idempotent: true\n      call: songstats.get-artist-stats\n      with:\n        songstats_artist_id: tools.songstats_artist_id\n        source: tools.source\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-artist-historic-stats\n      description: Get historical streaming stats for an artist\
  \ over a date range\n      hints:\n        readOnly: true\n        idempotent: true\n      call: songstats.get-artist-historic-stats\n      with:\n        songstats_artist_id: tools.songstats_artist_id\n        source: tools.source\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-artist-audience-details\n      description: Get detailed audience demographics for an artist in a specific country\n      hints:\n        readOnly: true\n        idempotent: true\n      call: songstats.get-artist-audience-details\n      with:\n        songstats_artist_id: tools.songstats_artist_id\n        country_code: tools.country_code\n        source: tools.source\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-artist-top-tracks\n      description: Get top performing tracks for an artist\n      hints:\n        readOnly: true\n        idempotent: true\n      call:\
  \ songstats.get-artist-top-tracks\n      with:\n        songstats_artist_id: tools.songstats_artist_id\n        source: tools.source\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-artist-top-playlists\n      description: Get top playlists featuring an artist\n      hints:\n        readOnly: true\n        idempotent: true\n      call: songstats.get-artist-top-playlists\n      with:\n        songstats_artist_id: tools.songstats_artist_id\n        source: tools.source\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-artists\n      description: Search for music artists by name\n      hints:\n        readOnly: true\n        idempotent: true\n      call: songstats.search-artists\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-track-stats\n      description: Get current streaming stats for a track\n      hints:\n        readOnly: true\n        idempotent:\
  \ true\n      call: songstats.get-track-stats\n      with:\n        songstats_track_id: tools.songstats_track_id\n        source: tools.source\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-track-historic-stats\n      description: Get historical streaming stats for a track over a date range\n      hints:\n        readOnly: true\n        idempotent: true\n      call: songstats.get-track-historic-stats\n      with:\n        songstats_track_id: tools.songstats_track_id\n        source: tools.source\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-tracks\n      description: Search for music tracks by title or artist name\n      hints:\n        readOnly: true\n        idempotent: true\n      call: songstats.search-tracks\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-label-stats\n\
  \      description: Get current streaming stats for a record label\n      hints:\n        readOnly: true\n        idempotent: true\n      call: songstats.get-label-stats\n      with:\n        songstats_label_id: tools.songstats_label_id\n        source: tools.source\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-label-catalog\n      description: Get the full track catalog for a record label\n      hints:\n        readOnly: true\n        idempotent: true\n      call: songstats.get-label-catalog\n      with:\n        songstats_label_id: tools.songstats_label_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-labels\n      description: Search for record labels by name\n      hints:\n        readOnly: true\n        idempotent: true\n      call: songstats.search-labels\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/songstats/refs/heads/main/capabilities/music-analytics.yaml
tags:
- Songstats
- Music
- Analytics
- Streaming
- Artists
- Tracks
- Labels
- Playlists
tools:
- description: Get basic information about a music artist by Songstats ID or Spotify ID
  hints:
    idempotent: true
    readOnly: true
  name: get-artist-info
- description: Get current streaming stats for an artist across platforms
  hints:
    idempotent: true
    readOnly: true
  name: get-artist-stats
- description: Get historical streaming stats for an artist over a date range
  hints:
    idempotent: true
    readOnly: true
  name: get-artist-historic-stats
- description: Get detailed audience demographics for an artist in a specific country
  hints:
    idempotent: true
    readOnly: true
  name: get-artist-audience-details
- description: Get top performing tracks for an artist
  hints:
    idempotent: true
    readOnly: true
  name: get-artist-top-tracks
- description: Get top playlists featuring an artist
  hints:
    idempotent: true
    readOnly: true
  name: get-artist-top-playlists
- description: Search for music artists by name
  hints:
    idempotent: true
    readOnly: true
  name: search-artists
- description: Get current streaming stats for a track
  hints:
    idempotent: true
    readOnly: true
  name: get-track-stats
- description: Get historical streaming stats for a track over a date range
  hints:
    idempotent: true
    readOnly: true
  name: get-track-historic-stats
- description: Search for music tracks by title or artist name
  hints:
    idempotent: true
    readOnly: true
  name: search-tracks
- description: Get current streaming stats for a record label
  hints:
    idempotent: true
    readOnly: true
  name: get-label-stats
- description: Get the full track catalog for a record label
  hints:
    idempotent: true
    readOnly: true
  name: get-label-catalog
- description: Search for record labels by name
  hints:
    idempotent: true
    readOnly: true
  name: search-labels
---
