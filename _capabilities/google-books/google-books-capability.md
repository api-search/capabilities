---
categories: []
consumed_apis: []
description: The Google Books API allows you to perform full-text searches and retrieve book information, viewability, and eBook availability. You can also manage personal bookshelves, access volume metadata, and work with user library data.
layout: capability
name: Google Books API
operations:
- description: Search for volumes
  method: GET
  name: listvolumes
  path: /volumes
- description: Get a volume
  method: GET
  name: getvolume
  path: /volumes/{volumeId}
- description: List bookshelves
  method: GET
  name: listbookshelves
  path: /users/{userId}/bookshelves
- description: Get a bookshelf
  method: GET
  name: getbookshelf
  path: /users/{userId}/bookshelves/{shelf}
- description: List volumes in a bookshelf
  method: GET
  name: listbookshelfvolumes
  path: /users/{userId}/bookshelves/{shelf}/volumes
- description: List my bookshelves
  method: GET
  name: listmybookshelves
  path: /mylibrary/bookshelves
- description: Add volume to bookshelf
  method: POST
  name: addvolumetobookshelf
  path: /mylibrary/bookshelves/{shelf}/addVolume
- description: Remove volume from bookshelf
  method: POST
  name: removevolumefrombookshelf
  path: /mylibrary/bookshelves/{shelf}/removeVolume
personas: []
provider_name: Google Books
provider_slug: google-books
search_terms:
- remove volume from bookshelf
- list volumes in a bookshelf
- listvolumes
- api
- publishing
- listmybookshelves
- list my bookshelves
- google
- addvolumetobookshelf
- get a bookshelf
- getvolume
- ebooks
- library
- listbookshelves
- list bookshelves
- get a volume
- listbookshelfvolumes
- search for volumes
- removevolumefrombookshelf
- reading
- getbookshelf
- add volume to bookshelf
- search
- books
slug: google-books-capability
source_filename: google-books-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Books API\n  description: The Google Books API allows you to perform full-text searches and retrieve book information, viewability, and\n    eBook availability. You can also manage personal bookshelves, access volume metadata, and work with user library data.\n  tags:\n  - Google\n  - Books\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-books\n    baseUri: https://www.googleapis.com/books/v1\n    description: Google Books API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_BOOKS_TOKEN}}'\n    resources:\n    - name: volumes\n      path: /volumes\n      operations:\n      - name: listvolumes\n        method: GET\n        description: Search for volumes\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Full-text search query string.\n    \
  \    - name: maxResults\n          in: query\n          type: integer\n        - name: startIndex\n          in: query\n          type: integer\n        - name: orderBy\n          in: query\n          type: string\n        - name: printType\n          in: query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        - name: langRestrict\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: volumes-volumeid\n      path: /volumes/{volumeId}\n      operations:\n      - name: getvolume\n        method: GET\n        description: Get a volume\n        inputParameters:\n        - name: volumeId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-bookshelves\n\
  \      path: /users/{userId}/bookshelves\n      operations:\n      - name: listbookshelves\n        method: GET\n        description: List bookshelves\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-bookshelves-shelf\n      path: /users/{userId}/bookshelves/{shelf}\n      operations:\n      - name: getbookshelf\n        method: GET\n        description: Get a bookshelf\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: shelf\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-bookshelves-shelf-volumes\n      path:\
  \ /users/{userId}/bookshelves/{shelf}/volumes\n      operations:\n      - name: listbookshelfvolumes\n        method: GET\n        description: List volumes in a bookshelf\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: shelf\n          in: path\n          type: string\n          required: true\n        - name: maxResults\n          in: query\n          type: integer\n        - name: startIndex\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mylibrary-bookshelves\n      path: /mylibrary/bookshelves\n      operations:\n      - name: listmybookshelves\n        method: GET\n        description: List my bookshelves\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mylibrary-bookshelves-shelf-addvolume\n\
  \      path: /mylibrary/bookshelves/{shelf}/addVolume\n      operations:\n      - name: addvolumetobookshelf\n        method: POST\n        description: Add volume to bookshelf\n        inputParameters:\n        - name: shelf\n          in: path\n          type: string\n          required: true\n        - name: volumeId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mylibrary-bookshelves-shelf-removevolume\n      path: /mylibrary/bookshelves/{shelf}/removeVolume\n      operations:\n      - name: removevolumefrombookshelf\n        method: POST\n        description: Remove volume from bookshelf\n        inputParameters:\n        - name: shelf\n          in: path\n          type: string\n          required: true\n        - name: volumeId\n          in: query\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-books-rest\n    description: REST adapter for Google Books API.\n    resources:\n    - path: /volumes\n      name: listvolumes\n      operations:\n      - method: GET\n        name: listvolumes\n        description: Search for volumes\n        call: google-books.listvolumes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /volumes/{volumeId}\n      name: getvolume\n      operations:\n      - method: GET\n        name: getvolume\n        description: Get a volume\n        call: google-books.getvolume\n        with:\n          volumeId: rest.volumeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/bookshelves\n      name: listbookshelves\n      operations:\n      - method: GET\n        name: listbookshelves\n        description:\
  \ List bookshelves\n        call: google-books.listbookshelves\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/bookshelves/{shelf}\n      name: getbookshelf\n      operations:\n      - method: GET\n        name: getbookshelf\n        description: Get a bookshelf\n        call: google-books.getbookshelf\n        with:\n          userId: rest.userId\n          shelf: rest.shelf\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/bookshelves/{shelf}/volumes\n      name: listbookshelfvolumes\n      operations:\n      - method: GET\n        name: listbookshelfvolumes\n        description: List volumes in a bookshelf\n        call: google-books.listbookshelfvolumes\n        with:\n          userId: rest.userId\n          shelf: rest.shelf\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mylibrary/bookshelves\n\
  \      name: listmybookshelves\n      operations:\n      - method: GET\n        name: listmybookshelves\n        description: List my bookshelves\n        call: google-books.listmybookshelves\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mylibrary/bookshelves/{shelf}/addVolume\n      name: addvolumetobookshelf\n      operations:\n      - method: POST\n        name: addvolumetobookshelf\n        description: Add volume to bookshelf\n        call: google-books.addvolumetobookshelf\n        with:\n          shelf: rest.shelf\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mylibrary/bookshelves/{shelf}/removeVolume\n      name: removevolumefrombookshelf\n      operations:\n      - method: POST\n        name: removevolumefrombookshelf\n        description: Remove volume from bookshelf\n        call: google-books.removevolumefrombookshelf\n        with:\n          shelf: rest.shelf\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-books-mcp\n    transport: http\n    description: MCP adapter for Google Books API for AI agent use.\n    tools:\n    - name: listvolumes\n      description: Search for volumes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-books.listvolumes\n      with:\n        q: tools.q\n        maxResults: tools.maxResults\n        startIndex: tools.startIndex\n        orderBy: tools.orderBy\n        printType: tools.printType\n        filter: tools.filter\n        langRestrict: tools.langRestrict\n      inputParameters:\n      - name: q\n        type: string\n        description: Full-text search query string.\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: startIndex\n        type: integer\n        description: startIndex\n      - name: orderBy\n        type: string\n\
  \        description: orderBy\n      - name: printType\n        type: string\n        description: printType\n      - name: filter\n        type: string\n        description: filter\n      - name: langRestrict\n        type: string\n        description: langRestrict\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvolume\n      description: Get a volume\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-books.getvolume\n      with:\n        volumeId: tools.volumeId\n      inputParameters:\n      - name: volumeId\n        type: string\n        description: volumeId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbookshelves\n      description: List bookshelves\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-books.listbookshelves\n      with:\n        userId: tools.userId\n\
  \      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbookshelf\n      description: Get a bookshelf\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-books.getbookshelf\n      with:\n        userId: tools.userId\n        shelf: tools.shelf\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: shelf\n        type: string\n        description: shelf\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbookshelfvolumes\n      description: List volumes in a bookshelf\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-books.listbookshelfvolumes\n      with:\n        userId: tools.userId\n\
  \        shelf: tools.shelf\n        maxResults: tools.maxResults\n        startIndex: tools.startIndex\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: shelf\n        type: string\n        description: shelf\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: startIndex\n        type: integer\n        description: startIndex\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmybookshelves\n      description: List my bookshelves\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-books.listmybookshelves\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addvolumetobookshelf\n      description: Add volume to bookshelf\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: google-books.addvolumetobookshelf\n      with:\n        shelf: tools.shelf\n        volumeId: tools.volumeId\n      inputParameters:\n      - name: shelf\n        type: string\n        description: shelf\n        required: true\n      - name: volumeId\n        type: string\n        description: volumeId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removevolumefrombookshelf\n      description: Remove volume from bookshelf\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-books.removevolumefrombookshelf\n      with:\n        shelf: tools.shelf\n        volumeId: tools.volumeId\n      inputParameters:\n      - name: shelf\n        type: string\n        description: shelf\n        required: true\n      - name: volumeId\n        type: string\n        description: volumeId\n        required: true\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_BOOKS_TOKEN: GOOGLE_BOOKS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-books/refs/heads/main/capabilities/google-books-capability.yaml
tags:
- Google
- Books
- API
tools:
- description: Search for volumes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvolumes
- description: Get a volume
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvolume
- description: List bookshelves
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbookshelves
- description: Get a bookshelf
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbookshelf
- description: List volumes in a bookshelf
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbookshelfvolumes
- description: List my bookshelves
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmybookshelves
- description: Add volume to bookshelf
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addvolumetobookshelf
- description: Remove volume from bookshelf
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: removevolumefrombookshelf
---
