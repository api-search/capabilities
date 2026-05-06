---
categories: []
consumed_apis: []
description: The most powerful and legal way to display lyrics on your website or in your application. Musixmatch lyrics API is a robust service that permits you to search and retrieve lyrics in the simplest possible way.
layout: capability
name: Musixmatch API
operations:
- description: GET /album.tracks.get
  method: GET
  name: get-album-tracks-get
  path: /album.tracks.get
- description: GET /album.get
  method: GET
  name: get-album-get
  path: /album.get
- description: GET /artist.related.get
  method: GET
  name: get-artist-related-get
  path: /artist.related.get
- description: GET /artist.albums.get
  method: GET
  name: get-artist-albums-get
  path: /artist.albums.get
- description: GET /artist.search
  method: GET
  name: get-artist-search
  path: /artist.search
- description: GET /artist.get
  method: GET
  name: get-artist-get
  path: /artist.get
- description: GET /matcher.subtitle.get
  method: GET
  name: get-matcher-subtitle-get
  path: /matcher.subtitle.get
- description: GET /matcher.track.get
  method: GET
  name: get-matcher-track-get
  path: /matcher.track.get
- description: GET /matcher.lyrics.get
  method: GET
  name: get-matcher-lyrics-get
  path: /matcher.lyrics.get
- description: GET /track.snippet.get
  method: GET
  name: get-track-snippet-get
  path: /track.snippet.get
- description: GET /track.lyrics.get
  method: GET
  name: get-track-lyrics-get
  path: /track.lyrics.get
- description: GET /track.subtitle.get
  method: GET
  name: get-track-subtitle-get
  path: /track.subtitle.get
- description: GET /track.get
  method: GET
  name: get-track-get
  path: /track.get
- description: GET /track.search
  method: GET
  name: get-track-search
  path: /track.search
- description: GET /chart.tracks.get
  method: GET
  name: get-chart-tracks-get
  path: /chart.tracks.get
- description: GET /chart.artists.get
  method: GET
  name: get-chart-artists-get
  path: /chart.artists.get
personas: []
provider_name: Musixmatch
provider_slug: musixmatch
search_terms:
- get /artist.related.get
- get /track.search
- get track get
- musixmatch
- get track lyrics get
- get /track.get
- get /artist.albums.get
- get /track.subtitle.get
- get /album.get
- get chart tracks get
- get chart artists get
- get matcher track get
- get matcher subtitle get
- get /matcher.subtitle.get
- get album get
- get /track.lyrics.get
- get /album.tracks.get
- music
- get /artist.search
- api
- get track snippet get
- translations
- get artist albums get
- get track search
- get album tracks get
- get artist related get
- get track subtitle get
- get /track.snippet.get
- get /chart.artists.get
- get /artist.get
- get /matcher.lyrics.get
- lyrics
- get matcher lyrics get
- get artist search
- get /matcher.track.get
- get /chart.tracks.get
- get artist get
slug: musixmatch-capability
source_filename: musixmatch-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Musixmatch API\n  description: The most powerful and legal way to display lyrics on your website or in your application. Musixmatch lyrics\n    API is a robust service that permits you to search and retrieve lyrics in the simplest possible way.\n  tags:\n  - Musixmatch\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: musixmatch\n    baseUri: https://api.musixmatch.com/ws/1.1\n    description: Musixmatch API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: apikey\n      value: '{{MUSIXMATCH_TOKEN}}'\n    resources:\n    - name: album-tracks-get\n      path: /album.tracks.get\n      operations:\n      - name: get-album-tracks-get\n        method: GET\n        description: GET /album.tracks.get\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: 'output format: json, jsonp,\
  \ xml.'\n        - name: callback\n          in: query\n          type: string\n          description: jsonp callback\n        - name: album_id\n          in: query\n          type: string\n          required: true\n          description: The musiXmatch album id\n        - name: f_has_lyrics\n          in: query\n          type: string\n          description: When set, filter only contents with lyrics\n        - name: page\n          in: query\n          type: number\n          description: Define the page number for paginated results\n        - name: page_size\n          in: query\n          type: number\n          description: Define the page size for paginated results.Range is 1 to 100.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: album-get\n      path: /album.get\n      operations:\n      - name: get-album-get\n        method: GET\n        description: GET /album.get\n        inputParameters:\n\
  \        - name: format\n          in: query\n          type: string\n          description: 'output format: json, jsonp, xml.'\n        - name: callback\n          in: query\n          type: string\n          description: jsonp callback\n        - name: album_id\n          in: query\n          type: string\n          required: true\n          description: The musiXmatch album id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: artist-related-get\n      path: /artist.related.get\n      operations:\n      - name: get-artist-related-get\n        method: GET\n        description: GET /artist.related.get\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: 'output format: json, jsonp, xml.'\n        - name: callback\n          in: query\n          type: string\n          description: jsonp callback\n        - name: artist_id\n        \
  \  in: query\n          type: string\n          required: true\n          description: The musiXmatch artist id\n        - name: page_size\n          in: query\n          type: number\n          description: Define the page size for paginated results.Range is 1 to 100.\n        - name: page\n          in: query\n          type: number\n          description: Define the page number for paginated results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: artist-albums-get\n      path: /artist.albums.get\n      operations:\n      - name: get-artist-albums-get\n        method: GET\n        description: GET /artist.albums.get\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: 'output format: json, jsonp, xml.'\n        - name: callback\n          in: query\n          type: string\n          description: jsonp callback\n        - name: artist_id\n\
  \          in: query\n          type: string\n          required: true\n          description: The musiXmatch artist id\n        - name: s_release_date\n          in: query\n          type: string\n          description: Sort by release date (asc|desc)\n        - name: g_album_name\n          in: query\n          type: string\n          description: Group by Album Name\n        - name: page_size\n          in: query\n          type: number\n          description: Define the page size for paginated results.Range is 1 to 100.\n        - name: page\n          in: query\n          type: number\n          description: Define the page number for paginated results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: artist-search\n      path: /artist.search\n      operations:\n      - name: get-artist-search\n        method: GET\n        description: GET /artist.search\n        inputParameters:\n        - name:\
  \ format\n          in: query\n          type: string\n          description: 'output format: json, jsonp, xml.'\n        - name: callback\n          in: query\n          type: string\n          description: jsonp callback\n        - name: q_artist\n          in: query\n          type: string\n          description: The song artist\n        - name: f_artist_id\n          in: query\n          type: number\n          description: When set, filter by this artist id\n        - name: page\n          in: query\n          type: number\n          description: Define the page number for paginated results\n        - name: page_size\n          in: query\n          type: number\n          description: Define the page size for paginated results.Range is 1 to 100.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: artist-get\n      path: /artist.get\n      operations:\n      - name: get-artist-get\n        method:\
  \ GET\n        description: GET /artist.get\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: 'output format: json, jsonp, xml.'\n        - name: callback\n          in: query\n          type: string\n          description: jsonp callback\n        - name: artist_id\n          in: query\n          type: string\n          required: true\n          description: The musiXmatch artist id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: matcher-subtitle-get\n      path: /matcher.subtitle.get\n      operations:\n      - name: get-matcher-subtitle-get\n        method: GET\n        description: GET /matcher.subtitle.get\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: 'output format: json, jsonp, xml.'\n        - name: callback\n          in: query\n          type: string\n\
  \          description: jsonp callback\n        - name: q_track\n          in: query\n          type: string\n          description: The song title\n        - name: q_artist\n          in: query\n          type: string\n          description: The song artist\n        - name: f_subtitle_length\n          in: query\n          type: number\n          description: Filter by subtitle length in seconds\n        - name: f_subtitle_length_max_deviation\n          in: query\n          type: number\n          description: Max deviation for a subtitle length in seconds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: matcher-track-get\n      path: /matcher.track.get\n      operations:\n      - name: get-matcher-track-get\n        method: GET\n        description: GET /matcher.track.get\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: 'output\
  \ format: json, jsonp, xml.'\n        - name: callback\n          in: query\n          type: string\n          description: jsonp callback\n        - name: q_artist\n          in: query\n          type: string\n          description: The song artist\n        - name: q_track\n          in: query\n          type: string\n          description: The song title\n        - name: f_has_lyrics\n          in: query\n          type: number\n          description: When set, filter only contents with lyrics\n        - name: f_has_subtitle\n          in: query\n          type: number\n          description: When set, filter only contents with subtitles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: matcher-lyrics-get\n      path: /matcher.lyrics.get\n      operations:\n      - name: get-matcher-lyrics-get\n        method: GET\n        description: GET /matcher.lyrics.get\n        inputParameters:\n        -\
  \ name: format\n          in: query\n          type: string\n          description: 'output format: json, jsonp, xml.'\n        - name: callback\n          in: query\n          type: string\n          description: jsonp callback\n        - name: q_track\n          in: query\n          type: string\n          description: The song title\n        - name: q_artist\n          in: query\n          type: string\n          description: The song artist\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: track-snippet-get\n      path: /track.snippet.get\n      operations:\n      - name: get-track-snippet-get\n        method: GET\n        description: GET /track.snippet.get\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: 'output format: json, jsonp, xml.'\n        - name: callback\n          in: query\n          type: string\n          description:\
  \ jsonp callback\n        - name: track_id\n          in: query\n          type: string\n          required: true\n          description: The musiXmatch track id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: track-lyrics-get\n      path: /track.lyrics.get\n      operations:\n      - name: get-track-lyrics-get\n        method: GET\n        description: GET /track.lyrics.get\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: 'output format: json, jsonp, xml.'\n        - name: callback\n          in: query\n          type: string\n          description: jsonp callback\n        - name: track_id\n          in: query\n          type: string\n          required: true\n          description: The musiXmatch track id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: track-subtitle-get\n      path: /track.subtitle.get\n      operations:\n      - name: get-track-subtitle-get\n        method: GET\n        description: GET /track.subtitle.get\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: 'output format: json, jsonp, xml.'\n        - name: callback\n          in: query\n          type: string\n          description: jsonp callback\n        - name: track_id\n          in: query\n          type: string\n          required: true\n          description: The musiXmatch track id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: track-get\n      path: /track.get\n      operations:\n      - name: get-track-get\n        method: GET\n        description: GET /track.get\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description:\
  \ 'output format: json, jsonp, xml.'\n        - name: callback\n          in: query\n          type: string\n          description: jsonp callback\n        - name: track_id\n          in: query\n          type: string\n          required: true\n          description: The musiXmatch track id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: track-search\n      path: /track.search\n      operations:\n      - name: get-track-search\n        method: GET\n        description: GET /track.search\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: 'output format: json, jsonp, xml.'\n        - name: callback\n          in: query\n          type: string\n          description: jsonp callback\n        - name: q_track\n          in: query\n          type: string\n          description: The song title\n        - name: q_artist\n          in: query\n\
  \          type: string\n          description: The song artist\n        - name: q_lyrics\n          in: query\n          type: string\n          description: Any word in the lyrics\n        - name: f_artist_id\n          in: query\n          type: number\n          description: When set, filter by this artist id\n        - name: f_music_genre_id\n          in: query\n          type: number\n          description: When set, filter by this music category id\n        - name: f_lyrics_language\n          in: query\n          type: number\n          description: Filter by the lyrics language (en,it,..)\n        - name: f_has_lyrics\n          in: query\n          type: number\n          description: When set, filter only contents with lyrics\n        - name: s_artist_rating\n          in: query\n          type: string\n          description: Sort by our popularity index for artists (asc|desc)\n        - name: s_track_rating\n          in: query\n          type: string\n          description:\
  \ Sort by our popularity index for tracks (asc|desc)\n        - name: quorum_factor\n          in: query\n          type: number\n          description: Search only a part of the given query string.Allowed range is (0.1 0.9)\n        - name: page_size\n          in: query\n          type: number\n          description: Define the page size for paginated results.Range is 1 to 100.\n        - name: page\n          in: query\n          type: number\n          description: Define the page number for paginated results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: chart-tracks-get\n      path: /chart.tracks.get\n      operations:\n      - name: get-chart-tracks-get\n        method: GET\n        description: GET /chart.tracks.get\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: 'output format: json, jsonp, xml.'\n        - name: callback\n\
  \          in: query\n          type: string\n          description: jsonp callback\n        - name: page\n          in: query\n          type: number\n          description: Define the page number for paginated results\n        - name: page_size\n          in: query\n          type: number\n          description: Define the page size for paginated results.Range is 1 to 100.\n        - name: country\n          in: query\n          type: string\n          description: A valid ISO 3166 country code\n        - name: f_has_lyrics\n          in: query\n          type: string\n          description: When set, filter only contents with lyrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: chart-artists-get\n      path: /chart.artists.get\n      operations:\n      - name: get-chart-artists-get\n        method: GET\n        description: GET /chart.artists.get\n        inputParameters:\n        - name: format\n\
  \          in: query\n          type: string\n          description: 'output format: json, jsonp, xml.'\n        - name: callback\n          in: query\n          type: string\n          description: jsonp callback\n        - name: page\n          in: query\n          type: number\n          description: Define the page number for paginated results\n        - name: page_size\n          in: query\n          type: number\n          description: Define the page size for paginated results.Range is 1 to 100.\n        - name: country\n          in: query\n          type: string\n          description: A valid ISO 3166 country code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: musixmatch-rest\n    description: REST adapter for Musixmatch API.\n    resources:\n    - path: /album.tracks.get\n      name: get-album-tracks-get\n      operations:\n      - method:\
  \ GET\n        name: get-album-tracks-get\n        description: GET /album.tracks.get\n        call: musixmatch.get-album-tracks-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /album.get\n      name: get-album-get\n      operations:\n      - method: GET\n        name: get-album-get\n        description: GET /album.get\n        call: musixmatch.get-album-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /artist.related.get\n      name: get-artist-related-get\n      operations:\n      - method: GET\n        name: get-artist-related-get\n        description: GET /artist.related.get\n        call: musixmatch.get-artist-related-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /artist.albums.get\n      name: get-artist-albums-get\n      operations:\n      - method: GET\n        name: get-artist-albums-get\n        description: GET /artist.albums.get\n        call: musixmatch.get-artist-albums-get\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /artist.search\n      name: get-artist-search\n      operations:\n      - method: GET\n        name: get-artist-search\n        description: GET /artist.search\n        call: musixmatch.get-artist-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /artist.get\n      name: get-artist-get\n      operations:\n      - method: GET\n        name: get-artist-get\n        description: GET /artist.get\n        call: musixmatch.get-artist-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /matcher.subtitle.get\n      name: get-matcher-subtitle-get\n      operations:\n      - method: GET\n        name: get-matcher-subtitle-get\n        description: GET /matcher.subtitle.get\n        call: musixmatch.get-matcher-subtitle-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /matcher.track.get\n\
  \      name: get-matcher-track-get\n      operations:\n      - method: GET\n        name: get-matcher-track-get\n        description: GET /matcher.track.get\n        call: musixmatch.get-matcher-track-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /matcher.lyrics.get\n      name: get-matcher-lyrics-get\n      operations:\n      - method: GET\n        name: get-matcher-lyrics-get\n        description: GET /matcher.lyrics.get\n        call: musixmatch.get-matcher-lyrics-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /track.snippet.get\n      name: get-track-snippet-get\n      operations:\n      - method: GET\n        name: get-track-snippet-get\n        description: GET /track.snippet.get\n        call: musixmatch.get-track-snippet-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /track.lyrics.get\n      name: get-track-lyrics-get\n      operations:\n      - method:\
  \ GET\n        name: get-track-lyrics-get\n        description: GET /track.lyrics.get\n        call: musixmatch.get-track-lyrics-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /track.subtitle.get\n      name: get-track-subtitle-get\n      operations:\n      - method: GET\n        name: get-track-subtitle-get\n        description: GET /track.subtitle.get\n        call: musixmatch.get-track-subtitle-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /track.get\n      name: get-track-get\n      operations:\n      - method: GET\n        name: get-track-get\n        description: GET /track.get\n        call: musixmatch.get-track-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /track.search\n      name: get-track-search\n      operations:\n      - method: GET\n        name: get-track-search\n        description: GET /track.search\n        call: musixmatch.get-track-search\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /chart.tracks.get\n      name: get-chart-tracks-get\n      operations:\n      - method: GET\n        name: get-chart-tracks-get\n        description: GET /chart.tracks.get\n        call: musixmatch.get-chart-tracks-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /chart.artists.get\n      name: get-chart-artists-get\n      operations:\n      - method: GET\n        name: get-chart-artists-get\n        description: GET /chart.artists.get\n        call: musixmatch.get-chart-artists-get\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: musixmatch-mcp\n    transport: http\n    description: MCP adapter for Musixmatch API for AI agent use.\n    tools:\n    - name: get-album-tracks-get\n      description: GET /album.tracks.get\n      hints:\n        readOnly: true\n        destructive: false\n   \
  \     idempotent: true\n      call: musixmatch.get-album-tracks-get\n      with:\n        format: tools.format\n        callback: tools.callback\n        album_id: tools.album_id\n        f_has_lyrics: tools.f_has_lyrics\n        page: tools.page\n        page_size: tools.page_size\n      inputParameters:\n      - name: format\n        type: string\n        description: 'output format: json, jsonp, xml.'\n      - name: callback\n        type: string\n        description: jsonp callback\n      - name: album_id\n        type: string\n        description: The musiXmatch album id\n        required: true\n      - name: f_has_lyrics\n        type: string\n        description: When set, filter only contents with lyrics\n      - name: page\n        type: number\n        description: Define the page number for paginated results\n      - name: page_size\n        type: number\n        description: Define the page size for paginated results.Range is 1 to 100.\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-album-get\n      description: GET /album.get\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: musixmatch.get-album-get\n      with:\n        format: tools.format\n        callback: tools.callback\n        album_id: tools.album_id\n      inputParameters:\n      - name: format\n        type: string\n        description: 'output format: json, jsonp, xml.'\n      - name: callback\n        type: string\n        description: jsonp callback\n      - name: album_id\n        type: string\n        description: The musiXmatch album id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-artist-related-get\n      description: GET /artist.related.get\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: musixmatch.get-artist-related-get\n      with:\n        format: tools.format\n        callback:\
  \ tools.callback\n        artist_id: tools.artist_id\n        page_size: tools.page_size\n        page: tools.page\n      inputParameters:\n      - name: format\n        type: string\n        description: 'output format: json, jsonp, xml.'\n      - name: callback\n        type: string\n        description: jsonp callback\n      - name: artist_id\n        type: string\n        description: The musiXmatch artist id\n        required: true\n      - name: page_size\n        type: number\n        description: Define the page size for paginated results.Range is 1 to 100.\n      - name: page\n        type: number\n        description: Define the page number for paginated results\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-artist-albums-get\n      description: GET /artist.albums.get\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: musixmatch.get-artist-albums-get\n      with:\n        format: tools.format\n\
  \        callback: tools.callback\n        artist_id: tools.artist_id\n        s_release_date: tools.s_release_date\n        g_album_name: tools.g_album_name\n        page_size: tools.page_size\n        page: tools.page\n      inputParameters:\n      - name: format\n        type: string\n        description: 'output format: json, jsonp, xml.'\n      - name: callback\n        type: string\n        description: jsonp callback\n      - name: artist_id\n        type: string\n        description: The musiXmatch artist id\n        required: true\n      - name: s_release_date\n        type: string\n        description: Sort by release date (asc|desc)\n      - name: g_album_name\n        type: string\n        description: Group by Album Name\n      - name: page_size\n        type: number\n        description: Define the page size for paginated results.Range is 1 to 100.\n      - name: page\n        type: number\n        description: Define the page number for paginated results\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-artist-search\n      description: GET /artist.search\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: musixmatch.get-artist-search\n      with:\n        format: tools.format\n        callback: tools.callback\n        q_artist: tools.q_artist\n        f_artist_id: tools.f_artist_id\n        page: tools.page\n        page_size: tools.page_size\n      inputParameters:\n      - name: format\n        type: string\n        description: 'output format: json, jsonp, xml.'\n      - name: callback\n        type: string\n        description: jsonp callback\n      - name: q_artist\n        type: string\n        description: The song artist\n      - name: f_artist_id\n        type: number\n        description: When set, filter by this artist id\n      - name: page\n        type: number\n        description: Define the page number for paginated results\n      - name: page_size\n      \
  \  type: number\n        description: Define the page size for paginated results.Range is 1 to 100.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-artist-get\n      description: GET /artist.get\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: musixmatch.get-artist-get\n      with:\n        format: tools.format\n        callback: tools.callback\n        artist_id: tools.artist_id\n      inputParameters:\n      - name: format\n        type: string\n        description: 'output format: json, jsonp, xml.'\n      - name: callback\n        type: string\n        description: jsonp callback\n      - name: artist_id\n        type: string\n        description: The musiXmatch artist id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-matcher-subtitle-get\n      description: GET /matcher.subtitle.get\n      hints:\n        readOnly: true\n      \
  \  destructive: false\n        idempotent: true\n      call: musixmatch.get-matcher-subtitle-get\n      with:\n        format: tools.format\n        callback: tools.callback\n        q_track: tools.q_track\n        q_artist: tools.q_artist\n        f_subtitle_length: tools.f_subtitle_length\n        f_subtitle_length_max_deviation: tools.f_subtitle_length_max_deviation\n      inputParameters:\n      - name: format\n        type: string\n        description: 'output format: json, jsonp, xml.'\n      - name: callback\n        type: string\n        description: jsonp callback\n      - name: q_track\n        type: string\n        description: The song title\n      - name: q_artist\n        type: string\n        description: The song artist\n      - name: f_subtitle_length\n        type: number\n        description: Filter by subtitle length in seconds\n      - name: f_subtitle_length_max_deviation\n        type: number\n        description: Max deviation for a subtitle length in seconds\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-matcher-track-get\n      description: GET /matcher.track.get\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: musixmatch.get-matcher-track-get\n      with:\n        format: tools.format\n        callback: tools.callback\n        q_artist: tools.q_artist\n        q_track: tools.q_track\n        f_has_lyrics: tools.f_has_lyrics\n        f_has_subtitle: tools.f_has_subtitle\n      inputParameters:\n      - name: format\n        type: string\n        description: 'output format: json, jsonp, xml.'\n      - name: callback\n        type: string\n        description: jsonp callback\n      - name: q_artist\n        type: string\n        description: The song artist\n      - name: q_track\n        type: string\n        description: The song title\n      - name: f_has_lyrics\n        type: number\n        description: When set, filter only contents with lyrics\n\
  \      - name: f_has_subtitle\n        type: number\n        description: When set, filter only contents with subtitles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-matcher-lyrics-get\n      description: GET /matcher.lyrics.get\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: musixmatch.get-matcher-lyrics-get\n      with:\n        format: tools.format\n        callback: tools.callback\n        q_track: tools.q_track\n        q_artist: tools.q_artist\n      inputParameters:\n      - name: format\n        type: string\n        description: 'output format: json, jsonp, xml.'\n      - name: callback\n        type: string\n        description: jsonp callback\n      - name: q_track\n        type: string\n        description: The song title\n      - name: q_artist\n        type: string\n        description: The song artist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-track-snippet-get\n      description: GET /track.snippet.get\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: musixmatch.get-track-snippet-get\n      with:\n        format: tools.format\n        callback: tools.callback\n        track_id: tools.track_id\n      inputParameters:\n      - name: format\n        type: string\n        description: 'output format: json, jsonp, xml.'\n      - name: callback\n        type: string\n        description: jsonp callback\n      - name: track_id\n        type: string\n        description: The musiXmatch track id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-track-lyrics-get\n      description: GET /track.lyrics.get\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: musixmatch.get-track-lyrics-get\n      with:\n        format: tools.format\n        callback: tools.callback\n\
  \        track_id: tools.track_id\n      inputParameters:\n      - name: format\n        type: string\n        description: 'output format: json, jsonp, xml.'\n      - name: callback\n        type: string\n        description: jsonp callback\n      - name: track_id\n        type: string\n        description: The musiXmatch track id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-track-subtitle-get\n      description: GET /track.subtitle.get\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: musixmatch.get-track-subtitle-get\n      with:\n        format: tools.format\n        callback: tools.callback\n        track_id: tools.track_id\n      inputParameters:\n      - name: format\n        type: string\n        description: 'output format: json, jsonp, xml.'\n      - name: callback\n        type: string\n        description: jsonp callback\n      - name: track_id\n        type:\
  \ string\n        description: The musiXmatch track id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-track-get\n      description: GET /track.get\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: musixmatch.get-track-get\n      with:\n        format: tools.format\n        callback: tools.callback\n        track_id: tools.track_id\n      inputParameters:\n      - name: format\n        type: string\n        description: 'output format: json, jsonp, xml.'\n      - name: callback\n        type: string\n        description: jsonp callback\n      - name: track_id\n        type: string\n        description: The musiXmatch track id\n        required: true\n      outputParame\n\n# --- truncated at 32 KB (36 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/musixmatch/refs/heads/main/capabilities/musixmatch-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/musixmatch/refs/heads/main/capabilities/musixmatch-capability.yaml
tags:
- Musixmatch
- API
tools:
- description: GET /album.tracks.get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-album-tracks-get
- description: GET /album.get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-album-get
- description: GET /artist.related.get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-artist-related-get
- description: GET /artist.albums.get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-artist-albums-get
- description: GET /artist.search
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-artist-search
- description: GET /artist.get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-artist-get
- description: GET /matcher.subtitle.get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-matcher-subtitle-get
- description: GET /matcher.track.get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-matcher-track-get
- description: GET /matcher.lyrics.get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-matcher-lyrics-get
- description: GET /track.snippet.get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-track-snippet-get
- description: GET /track.lyrics.get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-track-lyrics-get
- description: GET /track.subtitle.get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-track-subtitle-get
- description: GET /track.get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-track-get
- description: GET /track.search
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-track-search
- description: GET /chart.tracks.get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-chart-tracks-get
- description: GET /chart.artists.get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-chart-artists-get
---
