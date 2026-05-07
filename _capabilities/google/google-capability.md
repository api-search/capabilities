---
categories: []
consumed_apis: []
description: API for retrieving Bookshelf and Volume resources from Google Books
layout: capability
name: Google Books API
operations:
- description: Google List Volumes
  method: GET
  name: listvolumes
  path: /volumes
- description: Google Get Volume
  method: GET
  name: getvolume
  path: /volumes/{volumeId}
- description: Google List Bookshelves
  method: GET
  name: listbookshelves
  path: /users/{userId}/bookshelves
- description: Google Get Bookshelf
  method: GET
  name: getbookshelf
  path: /users/{userId}/bookshelves/{shelf}
- description: Google List Bookshelf Volumes
  method: GET
  name: listbookshelfvolumes
  path: /users/{userId}/bookshelves/{shelf}/volumes
- description: Google List My Bookshelves
  method: GET
  name: listmybookshelves
  path: /mylibrary/bookshelves
- description: Google Get My Bookshelf
  method: GET
  name: getmybookshelf
  path: /mylibrary/bookshelves/{shelf}
- description: Google Add Volume to Bookshelf
  method: POST
  name: addvolumetobookshelf
  path: /mylibrary/bookshelves/{shelf}/addVolume
- description: Google Clear Volumes from Bookshelf
  method: POST
  name: clearvolumesfrombookshelf
  path: /mylibrary/bookshelves/{shelf}/clearVolumes
- description: Google Move Volume in Bookshelf
  method: POST
  name: movevolumeinbookshelf
  path: /mylibrary/bookshelves/{shelf}/moveVolume
- description: Google Remove Volume from Bookshelf
  method: POST
  name: removevolumefrombookshelf
  path: /mylibrary/bookshelves/{shelf}/removeVolume
- description: Google List My Bookshelf Volumes
  method: GET
  name: listmybookshelfvolumes
  path: /mylibrary/bookshelves/{shelf}/volumes
personas: []
provider_name: Google
provider_slug: google
search_terms:
- google move volume in bookshelf
- listvolumes
- google clear volumes from bookshelf
- listmybookshelfvolumes
- api
- platform
- listmybookshelves
- google
- addvolumetobookshelf
- google list bookshelf volumes
- google add volume to bookshelf
- getvolume
- google list my bookshelves
- t1
- getmybookshelf
- listbookshelves
- google list volumes
- listbookshelfvolumes
- google get bookshelf
- google get my bookshelf
- removevolumefrombookshelf
- cloud
- clearvolumesfrombookshelf
- movevolumeinbookshelf
- google remove volume from bookshelf
- google get volume
- google list my bookshelf volumes
- getbookshelf
- search
- developer
- google list bookshelves
- advertising
slug: google-capability
source_filename: google-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Books API\n  description: API for retrieving Bookshelf and Volume resources from Google Books\n  tags:\n  - Google\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google\n    baseUri: https://www.googleapis.com/books/v1\n    description: Google Books API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_TOKEN}}'\n    resources:\n    - name: volumes\n      path: /volumes\n      operations:\n      - name: listvolumes\n        method: GET\n        description: Google List Volumes\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Full-text search query string\n        - name: download\n          in: query\n          type: string\n          description: Restrict to volumes by download availability\n        - name: filter\n          in: query\n        \
  \  type: string\n          description: Filter search results\n        - name: langRestrict\n          in: query\n          type: string\n          description: Restrict results to books with this language code\n        - name: libraryRestrict\n          in: query\n          type: string\n          description: Restrict search to this user's library\n        - name: maxResults\n          in: query\n          type: integer\n          description: Maximum number of results to return (0 to 40)\n        - name: orderBy\n          in: query\n          type: string\n          description: Sort search results\n        - name: partner\n          in: query\n          type: string\n          description: Restrict and brand results for partner ID\n        - name: printType\n          in: query\n          type: string\n          description: Restrict to books or magazines\n        - name: projection\n          in: query\n          type: string\n          description: Restrict information returned\
  \ to a set of selected fields\n        - name: showPreorders\n          in: query\n          type: boolean\n          description: Set to true to show books available for preorder\n        - name: source\n          in: query\n          type: string\n          description: String to identify the originator of this request\n        - name: startIndex\n          in: query\n          type: integer\n          description: Index of the first result to return (starts at 0)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: volumes-volumeid\n      path: /volumes/{volumeId}\n      operations:\n      - name: getvolume\n        method: GET\n        description: Google Get Volume\n        inputParameters:\n        - name: volumeId\n          in: path\n          type: string\n          required: true\n          description: ID of volume to retrieve\n        - name: partner\n          in: query\n          type:\
  \ string\n          description: Brand results for partner ID\n        - name: projection\n          in: query\n          type: string\n          description: Restrict information returned to a set of selected fields\n        - name: source\n          in: query\n          type: string\n          description: String to identify the originator of this request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-bookshelves\n      path: /users/{userId}/bookshelves\n      operations:\n      - name: listbookshelves\n        method: GET\n        description: Google List Bookshelves\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: ID of user for whom to retrieve bookshelves\n        - name: source\n          in: query\n          type: string\n          description: String to identify the originator of\
  \ this request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-bookshelves-shelf\n      path: /users/{userId}/bookshelves/{shelf}\n      operations:\n      - name: getbookshelf\n        method: GET\n        description: Google Get Bookshelf\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: ID of user for whom to retrieve bookshelves\n        - name: shelf\n          in: path\n          type: string\n          required: true\n          description: ID of bookshelf to retrieve\n        - name: source\n          in: query\n          type: string\n          description: String to identify the originator of this request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-bookshelves-shelf-volumes\n\
  \      path: /users/{userId}/bookshelves/{shelf}/volumes\n      operations:\n      - name: listbookshelfvolumes\n        method: GET\n        description: Google List Bookshelf Volumes\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: ID of user for whom to retrieve bookshelf volumes\n        - name: shelf\n          in: path\n          type: string\n          required: true\n          description: ID of bookshelf to retrieve volumes\n        - name: maxResults\n          in: query\n          type: integer\n          description: Maximum number of results to return\n        - name: showPreorders\n          in: query\n          type: boolean\n          description: Set to true to show pre-ordered books\n        - name: source\n          in: query\n          type: string\n          description: String to identify the originator of this request\n        - name: startIndex\n          in: query\n \
  \         type: integer\n          description: Index of the first element to return (starts at 0)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mylibrary-bookshelves\n      path: /mylibrary/bookshelves\n      operations:\n      - name: listmybookshelves\n        method: GET\n        description: Google List My Bookshelves\n        inputParameters:\n        - name: source\n          in: query\n          type: string\n          description: String to identify the originator of this request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mylibrary-bookshelves-shelf\n      path: /mylibrary/bookshelves/{shelf}\n      operations:\n      - name: getmybookshelf\n        method: GET\n        description: Google Get My Bookshelf\n        inputParameters:\n        - name: shelf\n          in: path\n          type:\
  \ string\n          required: true\n          description: ID of bookshelf to retrieve\n        - name: source\n          in: query\n          type: string\n          description: String to identify the originator of this request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mylibrary-bookshelves-shelf-addvolume\n      path: /mylibrary/bookshelves/{shelf}/addVolume\n      operations:\n      - name: addvolumetobookshelf\n        method: POST\n        description: Google Add Volume to Bookshelf\n        inputParameters:\n        - name: shelf\n          in: path\n          type: string\n          required: true\n          description: ID of bookshelf to which to add a volume\n        - name: volumeId\n          in: query\n          type: string\n          required: true\n          description: ID of volume to add\n        - name: source\n          in: query\n          type: string\n          description:\
  \ String to identify the originator of this request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mylibrary-bookshelves-shelf-clearvolumes\n      path: /mylibrary/bookshelves/{shelf}/clearVolumes\n      operations:\n      - name: clearvolumesfrombookshelf\n        method: POST\n        description: Google Clear Volumes from Bookshelf\n        inputParameters:\n        - name: shelf\n          in: path\n          type: string\n          required: true\n          description: ID of bookshelf from which to remove all volumes\n        - name: source\n          in: query\n          type: string\n          description: String to identify the originator of this request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mylibrary-bookshelves-shelf-movevolume\n      path: /mylibrary/bookshelves/{shelf}/moveVolume\n\
  \      operations:\n      - name: movevolumeinbookshelf\n        method: POST\n        description: Google Move Volume in Bookshelf\n        inputParameters:\n        - name: shelf\n          in: path\n          type: string\n          required: true\n          description: ID of bookshelf with the volume\n        - name: volumeId\n          in: query\n          type: string\n          required: true\n          description: ID of volume to move\n        - name: volumePosition\n          in: query\n          type: integer\n          required: true\n          description: Position on shelf to move the item (0 puts the item before the current first item, 1 puts it between\n            the first and the second and so on)\n        - name: source\n          in: query\n          type: string\n          description: String to identify the originator of this request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \   - name: mylibrary-bookshelves-shelf-removevolume\n      path: /mylibrary/bookshelves/{shelf}/removeVolume\n      operations:\n      - name: removevolumefrombookshelf\n        method: POST\n        description: Google Remove Volume from Bookshelf\n        inputParameters:\n        - name: shelf\n          in: path\n          type: string\n          required: true\n          description: ID of bookshelf from which to remove a volume\n        - name: volumeId\n          in: query\n          type: string\n          required: true\n          description: ID of volume to remove\n        - name: source\n          in: query\n          type: string\n          description: String to identify the originator of this request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mylibrary-bookshelves-shelf-volumes\n      path: /mylibrary/bookshelves/{shelf}/volumes\n      operations:\n      - name: listmybookshelfvolumes\n\
  \        method: GET\n        description: Google List My Bookshelf Volumes\n        inputParameters:\n        - name: shelf\n          in: path\n          type: string\n          required: true\n          description: The bookshelf ID or name to retrieve volumes for\n        - name: maxResults\n          in: query\n          type: integer\n          description: Maximum number of results to return\n        - name: projection\n          in: query\n          type: string\n          description: Restrict information returned to a set of selected fields\n        - name: q\n          in: query\n          type: string\n          description: Full-text search query string in this bookshelf\n        - name: showPreorders\n          in: query\n          type: boolean\n          description: Set to true to show pre-ordered books\n        - name: source\n          in: query\n          type: string\n          description: String to identify the originator of this request\n        - name: startIndex\n\
  \          in: query\n          type: integer\n          description: Index of the first element to return (starts at 0)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-rest\n    description: REST adapter for Google Books API.\n    resources:\n    - path: /volumes\n      name: listvolumes\n      operations:\n      - method: GET\n        name: listvolumes\n        description: Google List Volumes\n        call: google.listvolumes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /volumes/{volumeId}\n      name: getvolume\n      operations:\n      - method: GET\n        name: getvolume\n        description: Google Get Volume\n        call: google.getvolume\n        with:\n          volumeId: rest.volumeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/bookshelves\n\
  \      name: listbookshelves\n      operations:\n      - method: GET\n        name: listbookshelves\n        description: Google List Bookshelves\n        call: google.listbookshelves\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/bookshelves/{shelf}\n      name: getbookshelf\n      operations:\n      - method: GET\n        name: getbookshelf\n        description: Google Get Bookshelf\n        call: google.getbookshelf\n        with:\n          userId: rest.userId\n          shelf: rest.shelf\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/bookshelves/{shelf}/volumes\n      name: listbookshelfvolumes\n      operations:\n      - method: GET\n        name: listbookshelfvolumes\n        description: Google List Bookshelf Volumes\n        call: google.listbookshelfvolumes\n        with:\n          userId: rest.userId\n          shelf:\
  \ rest.shelf\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mylibrary/bookshelves\n      name: listmybookshelves\n      operations:\n      - method: GET\n        name: listmybookshelves\n        description: Google List My Bookshelves\n        call: google.listmybookshelves\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mylibrary/bookshelves/{shelf}\n      name: getmybookshelf\n      operations:\n      - method: GET\n        name: getmybookshelf\n        description: Google Get My Bookshelf\n        call: google.getmybookshelf\n        with:\n          shelf: rest.shelf\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mylibrary/bookshelves/{shelf}/addVolume\n      name: addvolumetobookshelf\n      operations:\n      - method: POST\n        name: addvolumetobookshelf\n        description: Google Add Volume to Bookshelf\n        call: google.addvolumetobookshelf\n    \
  \    with:\n          shelf: rest.shelf\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mylibrary/bookshelves/{shelf}/clearVolumes\n      name: clearvolumesfrombookshelf\n      operations:\n      - method: POST\n        name: clearvolumesfrombookshelf\n        description: Google Clear Volumes from Bookshelf\n        call: google.clearvolumesfrombookshelf\n        with:\n          shelf: rest.shelf\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mylibrary/bookshelves/{shelf}/moveVolume\n      name: movevolumeinbookshelf\n      operations:\n      - method: POST\n        name: movevolumeinbookshelf\n        description: Google Move Volume in Bookshelf\n        call: google.movevolumeinbookshelf\n        with:\n          shelf: rest.shelf\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mylibrary/bookshelves/{shelf}/removeVolume\n      name: removevolumefrombookshelf\n  \
  \    operations:\n      - method: POST\n        name: removevolumefrombookshelf\n        description: Google Remove Volume from Bookshelf\n        call: google.removevolumefrombookshelf\n        with:\n          shelf: rest.shelf\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mylibrary/bookshelves/{shelf}/volumes\n      name: listmybookshelfvolumes\n      operations:\n      - method: GET\n        name: listmybookshelfvolumes\n        description: Google List My Bookshelf Volumes\n        call: google.listmybookshelfvolumes\n        with:\n          shelf: rest.shelf\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-mcp\n    transport: http\n    description: MCP adapter for Google Books API for AI agent use.\n    tools:\n    - name: listvolumes\n      description: Google List Volumes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: google.listvolumes\n      with:\n        q: tools.q\n        download: tools.download\n        filter: tools.filter\n        langRestrict: tools.langRestrict\n        libraryRestrict: tools.libraryRestrict\n        maxResults: tools.maxResults\n        orderBy: tools.orderBy\n        partner: tools.partner\n        printType: tools.printType\n        projection: tools.projection\n        showPreorders: tools.showPreorders\n        source: tools.source\n        startIndex: tools.startIndex\n      inputParameters:\n      - name: q\n        type: string\n        description: Full-text search query string\n        required: true\n      - name: download\n        type: string\n        description: Restrict to volumes by download availability\n      - name: filter\n        type: string\n        description: Filter search results\n      - name: langRestrict\n        type: string\n        description: Restrict results to books with this language code\n      - name: libraryRestrict\n\
  \        type: string\n        description: Restrict search to this user's library\n      - name: maxResults\n        type: integer\n        description: Maximum number of results to return (0 to 40)\n      - name: orderBy\n        type: string\n        description: Sort search results\n      - name: partner\n        type: string\n        description: Restrict and brand results for partner ID\n      - name: printType\n        type: string\n        description: Restrict to books or magazines\n      - name: projection\n        type: string\n        description: Restrict information returned to a set of selected fields\n      - name: showPreorders\n        type: boolean\n        description: Set to true to show books available for preorder\n      - name: source\n        type: string\n        description: String to identify the originator of this request\n      - name: startIndex\n        type: integer\n        description: Index of the first result to return (starts at 0)\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getvolume\n      description: Google Get Volume\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google.getvolume\n      with:\n        volumeId: tools.volumeId\n        partner: tools.partner\n        projection: tools.projection\n        source: tools.source\n      inputParameters:\n      - name: volumeId\n        type: string\n        description: ID of volume to retrieve\n        required: true\n      - name: partner\n        type: string\n        description: Brand results for partner ID\n      - name: projection\n        type: string\n        description: Restrict information returned to a set of selected fields\n      - name: source\n        type: string\n        description: String to identify the originator of this request\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbookshelves\n      description: Google List Bookshelves\n   \
  \   hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google.listbookshelves\n      with:\n        userId: tools.userId\n        source: tools.source\n      inputParameters:\n      - name: userId\n        type: string\n        description: ID of user for whom to retrieve bookshelves\n        required: true\n      - name: source\n        type: string\n        description: String to identify the originator of this request\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbookshelf\n      description: Google Get Bookshelf\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google.getbookshelf\n      with:\n        userId: tools.userId\n        shelf: tools.shelf\n        source: tools.source\n      inputParameters:\n      - name: userId\n        type: string\n        description: ID of user for whom to retrieve bookshelves\n        required: true\n      -\
  \ name: shelf\n        type: string\n        description: ID of bookshelf to retrieve\n        required: true\n      - name: source\n        type: string\n        description: String to identify the originator of this request\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbookshelfvolumes\n      description: Google List Bookshelf Volumes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google.listbookshelfvolumes\n      with:\n        userId: tools.userId\n        shelf: tools.shelf\n        maxResults: tools.maxResults\n        showPreorders: tools.showPreorders\n        source: tools.source\n        startIndex: tools.startIndex\n      inputParameters:\n      - name: userId\n        type: string\n        description: ID of user for whom to retrieve bookshelf volumes\n        required: true\n      - name: shelf\n        type: string\n        description: ID of bookshelf to retrieve volumes\n \
  \       required: true\n      - name: maxResults\n        type: integer\n        description: Maximum number of results to return\n      - name: showPreorders\n        type: boolean\n        description: Set to true to show pre-ordered books\n      - name: source\n        type: string\n        description: String to identify the originator of this request\n      - name: startIndex\n        type: integer\n        description: Index of the first element to return (starts at 0)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmybookshelves\n      description: Google List My Bookshelves\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google.listmybookshelves\n      with:\n        source: tools.source\n      inputParameters:\n      - name: source\n        type: string\n        description: String to identify the originator of this request\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getmybookshelf\n      description: Google Get My Bookshelf\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google.getmybookshelf\n      with:\n        shelf: tools.shelf\n        source: tools.source\n      inputParameters:\n      - name: shelf\n        type: string\n        description: ID of bookshelf to retrieve\n        required: true\n      - name: source\n        type: string\n        description: String to identify the originator of this request\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addvolumetobookshelf\n      description: Google Add Volume to Bookshelf\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google.addvolumetobookshelf\n      with:\n        shelf: tools.shelf\n        volumeId: tools.volumeId\n        source: tools.source\n      inputParameters:\n      - name: shelf\n        type: string\n      \
  \  description: ID of bookshelf to which to add a volume\n        required: true\n      - name: volumeId\n        type: string\n        description: ID of volume to add\n        required: true\n      - name: source\n        type: string\n        description: String to identify the originator of this request\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clearvolumesfrombookshelf\n      description: Google Clear Volumes from Bookshelf\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google.clearvolumesfrombookshelf\n      with:\n        shelf: tools.shelf\n        source: tools.source\n      inputParameters:\n      - name: shelf\n        type: string\n        description: ID of bookshelf from which to remove all volumes\n        required: true\n      - name: source\n        type: string\n        description: String to identify the originator of this request\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: movevolumeinbookshelf\n      description: Google Move Volume in Bookshelf\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google.movevolumeinbookshelf\n      with:\n        shelf: tools.shelf\n        volumeId: tools.volumeId\n        volumePosition: tools.volumePosition\n        source: tools.source\n      inputParameters:\n      - name: shelf\n        type: string\n        description: ID of bookshelf with the volume\n        required: true\n      - name: volumeId\n        type: string\n        description: ID of volume to move\n        required: true\n      - name: volumePosition\n        type: integer\n        description: Position on shelf to move the item (0 puts the item before the current first item, 1 puts it between\n          the first and the second and so on)\n        required: true\n      - name: source\n        type: string\n        description: String to identify the originator\
  \ of this request\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removevolumefrombookshelf\n      description: Google Remove Volume from Bookshelf\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google.removevolumefrombookshelf\n      with:\n        shelf: tools.shelf\n        volumeId: tools.volumeId\n        source: tools.source\n      inputParameters:\n      - name: shelf\n        type: string\n        description: ID of bookshelf from which to remove a volume\n        required: true\n      - name: volumeId\n        type: string\n        description: ID of volume to remove\n        required: true\n      - name: source\n        type: string\n        description: String to identify the originator of this request\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmybookshelfvolumes\n      description: Google List My Bookshelf Volumes\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: google.listmybookshelfvolumes\n      with:\n        shelf: tools.shelf\n        maxResults: tools.maxResults\n        projection: tools.projection\n        q: tools.q\n        showPreorders: tools.showPreorders\n        source: tools.source\n        startIndex: tools.startIndex\n      inputParameters:\n      - name: shelf\n        type: string\n        description: The bookshelf ID or name to retrieve volumes for\n        required: true\n      - name: maxResults\n        type: integer\n        description: Maximum number of results to return\n      - name: projection\n        type: string\n        description: Restrict information returned to a set of selected fields\n      - name: q\n        type: string\n        description: Full-text search query string in this bookshelf\n      - name: showPreorders\n        type: boolean\n        description: Set to true to show pre-ordered books\n      - name: source\n     \
  \   type: string\n        description: String to identify the originator of this request\n      - name: startIndex\n        type: integer\n        description: Index of the first element to return (starts at 0)\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_TOKEN: GOOGLE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google/refs/heads/main/capabilities/google-capability.yaml
tags:
- Google
- API
tools:
- description: Google List Volumes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvolumes
- description: Google Get Volume
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvolume
- description: Google List Bookshelves
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbookshelves
- description: Google Get Bookshelf
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbookshelf
- description: Google List Bookshelf Volumes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbookshelfvolumes
- description: Google List My Bookshelves
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmybookshelves
- description: Google Get My Bookshelf
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmybookshelf
- description: Google Add Volume to Bookshelf
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addvolumetobookshelf
- description: Google Clear Volumes from Bookshelf
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: clearvolumesfrombookshelf
- description: Google Move Volume in Bookshelf
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: movevolumeinbookshelf
- description: Google Remove Volume from Bookshelf
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: removevolumefrombookshelf
- description: Google List My Bookshelf Volumes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmybookshelfvolumes
---
