---
categories: []
consumed_apis: []
description: The Quay API provides programmatic access to the Quay container image registry. Developers can manage repositories, organizations, users, robot accounts, teams, builds, build triggers, tags, manifests, vulnerability scans, and access permissions. The API supports the full lifecycle of container image distribution including image push and pull workflows, automated build configuration via integrations with source code repositories, security scanning of stored images, and fine-grained access control via OAuth tokens and robot account credentials. The API is available against Quay.io hosted servic
layout: capability
name: Quay Container Registry API
operations:
- description: List repositories
  method: GET
  name: listrepos
  path: /repository
- description: Create a new repository
  method: POST
  name: createrepo
  path: /repository
- description: Get repository details
  method: GET
  name: getrepo
  path: /repository/{repository}
- description: Delete repository
  method: DELETE
  name: deleterepo
  path: /repository/{repository}
- description: List repository tags
  method: GET
  name: listrepotags
  path: /repository/{repository}/tag/
- description: Create or update a tag
  method: PUT
  name: changetag
  path: /repository/{repository}/tag/{tag}
- description: Delete a tag
  method: DELETE
  name: deletetag
  path: /repository/{repository}/tag/{tag}
- description: Get manifest by digest
  method: GET
  name: getmanifest
  path: /repository/{repository}/manifest/{manifestref}
- description: Get vulnerability scan results for a manifest
  method: GET
  name: getmanifestsecurity
  path: /repository/{repository}/manifest/{manifestref}/security
- description: List builds for a repository
  method: GET
  name: listrepobuilds
  path: /repository/{repository}/build/
- description: Request a new build
  method: POST
  name: requestrepobuild
  path: /repository/{repository}/build/
- description: Get organization details
  method: GET
  name: getorganization
  path: /organization/{orgname}
- description: Create or update a team
  method: PUT
  name: updateorganizationteam
  path: /organization/{orgname}/team/{teamname}
- description: Create a robot account
  method: PUT
  name: createorgrobot
  path: /organization/{orgname}/robots/{robot_shortname}
- description: Get authenticated user
  method: GET
  name: getloggedinuser
  path: /user/
- description: Set user repository permission
  method: PUT
  name: changeuserpermissions
  path: /repository/{repository}/permissions/user/{username}
personas: []
provider_name: Quay
provider_slug: quay
search_terms:
- get authenticated user
- getrepo
- containers
- container images
- getmanifestsecurity
- delete repository
- red hat
- api
- getmanifest
- list repository tags
- quay
- deletetag
- deleterepo
- listrepotags
- createrepo
- registry
- get vulnerability scan results for a manifest
- changetag
- list builds for a repository
- listrepobuilds
- create or update a tag
- get organization details
- request a new build
- requestrepobuild
- create a new repository
- security scanning
- getloggedinuser
- updateorganizationteam
- create a robot account
- create or update a team
- get repository details
- listrepos
- createorgrobot
- changeuserpermissions
- get manifest by digest
- list repositories
- delete a tag
- getorganization
- set user repository permission
slug: quay-capability
source_filename: quay-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Quay Container Registry API\n  description: The Quay API provides programmatic access to the Quay container image registry. Developers can manage repositories,\n    organizations, users, robot accounts, teams, builds, build triggers, tags, manifests, vulnerability scans, and access\n    permissions. The API supports the full lifecycle of container image distribution including image push and pull workflows,\n    automated build configuration via integrations with source code repositories, security scanning of stored images, and\n    fine-grained access control via OAuth tokens and robot account credentials. The API is available against Quay.io hosted\n    servic\n  tags:\n  - Quay\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: quay\n    baseUri: https://quay.io/api/v1\n    description: Quay Container Registry API HTTP API.\n    authentication:\n      type: bearer\n \
  \     token: '{{QUAY_TOKEN}}'\n    resources:\n    - name: repository\n      path: /repository\n      operations:\n      - name: listrepos\n        method: GET\n        description: List repositories\n        inputParameters:\n        - name: namespace\n          in: query\n          type: string\n        - name: public\n          in: query\n          type: boolean\n        - name: starred\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrepo\n        method: POST\n        description: Create a new repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repository-repository\n      path: /repository/{repository}\n      operations:\n      - name: getrepo\n        method: GET\n        description: Get repository details\n        inputParameters:\n    \
  \    - name: repository\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterepo\n        method: DELETE\n        description: Delete repository\n        inputParameters:\n        - name: repository\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repository-repository-tag\n      path: /repository/{repository}/tag/\n      operations:\n      - name: listrepotags\n        method: GET\n        description: List repository tags\n        inputParameters:\n        - name: repository\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: repository-repository-tag-tag\n      path: /repository/{repository}/tag/{tag}\n      operations:\n      - name: changetag\n        method: PUT\n        description: Create or update a tag\n        inputParameters:\n        - name: repository\n          in: path\n          type: string\n          required: true\n        - name: tag\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetag\n        method: DELETE\n        description: Delete a tag\n        inputParameters:\n        - name: repository\n          in: path\n          type: string\n          required: true\n        - name: tag\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repository-repository-manifest-manifestref\n\
  \      path: /repository/{repository}/manifest/{manifestref}\n      operations:\n      - name: getmanifest\n        method: GET\n        description: Get manifest by digest\n        inputParameters:\n        - name: repository\n          in: path\n          type: string\n          required: true\n        - name: manifestref\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repository-repository-manifest-manifestref-secur\n      path: /repository/{repository}/manifest/{manifestref}/security\n      operations:\n      - name: getmanifestsecurity\n        method: GET\n        description: Get vulnerability scan results for a manifest\n        inputParameters:\n        - name: repository\n          in: path\n          type: string\n          required: true\n        - name: manifestref\n          in: path\n          type: string\n   \
  \       required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repository-repository-build\n      path: /repository/{repository}/build/\n      operations:\n      - name: listrepobuilds\n        method: GET\n        description: List builds for a repository\n        inputParameters:\n        - name: repository\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: requestrepobuild\n        method: POST\n        description: Request a new build\n        inputParameters:\n        - name: repository\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-orgname\n      path:\
  \ /organization/{orgname}\n      operations:\n      - name: getorganization\n        method: GET\n        description: Get organization details\n        inputParameters:\n        - name: orgname\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-orgname-team-teamname\n      path: /organization/{orgname}/team/{teamname}\n      operations:\n      - name: updateorganizationteam\n        method: PUT\n        description: Create or update a team\n        inputParameters:\n        - name: orgname\n          in: path\n          type: string\n          required: true\n        - name: teamname\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-orgname-robots-robot-shortname\n\
  \      path: /organization/{orgname}/robots/{robot_shortname}\n      operations:\n      - name: createorgrobot\n        method: PUT\n        description: Create a robot account\n        inputParameters:\n        - name: orgname\n          in: path\n          type: string\n          required: true\n        - name: robot_shortname\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user\n      path: /user/\n      operations:\n      - name: getloggedinuser\n        method: GET\n        description: Get authenticated user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repository-repository-permissions-user-username\n      path: /repository/{repository}/permissions/user/{username}\n      operations:\n      - name: changeuserpermissions\n      \
  \  method: PUT\n        description: Set user repository permission\n        inputParameters:\n        - name: repository\n          in: path\n          type: string\n          required: true\n        - name: username\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: quay-rest\n    description: REST adapter for Quay Container Registry API.\n    resources:\n    - path: /repository\n      name: listrepos\n      operations:\n      - method: GET\n        name: listrepos\n        description: List repositories\n        call: quay.listrepos\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repository\n      name: createrepo\n      operations:\n      - method: POST\n        name: createrepo\n        description: Create a new repository\n        call: quay.createrepo\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repository/{repository}\n      name: getrepo\n      operations:\n      - method: GET\n        name: getrepo\n        description: Get repository details\n        call: quay.getrepo\n        with:\n          repository: rest.repository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repository/{repository}\n      name: deleterepo\n      operations:\n      - method: DELETE\n        name: deleterepo\n        description: Delete repository\n        call: quay.deleterepo\n        with:\n          repository: rest.repository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repository/{repository}/tag/\n      name: listrepotags\n      operations:\n      - method: GET\n        name: listrepotags\n        description: List repository tags\n        call: quay.listrepotags\n        with:\n          repository: rest.repository\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repository/{repository}/tag/{tag}\n      name: changetag\n      operations:\n      - method: PUT\n        name: changetag\n        description: Create or update a tag\n        call: quay.changetag\n        with:\n          repository: rest.repository\n          tag: rest.tag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repository/{repository}/tag/{tag}\n      name: deletetag\n      operations:\n      - method: DELETE\n        name: deletetag\n        description: Delete a tag\n        call: quay.deletetag\n        with:\n          repository: rest.repository\n          tag: rest.tag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repository/{repository}/manifest/{manifestref}\n      name: getmanifest\n      operations:\n      - method: GET\n        name: getmanifest\n        description: Get manifest by digest\n        call:\
  \ quay.getmanifest\n        with:\n          repository: rest.repository\n          manifestref: rest.manifestref\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repository/{repository}/manifest/{manifestref}/security\n      name: getmanifestsecurity\n      operations:\n      - method: GET\n        name: getmanifestsecurity\n        description: Get vulnerability scan results for a manifest\n        call: quay.getmanifestsecurity\n        with:\n          repository: rest.repository\n          manifestref: rest.manifestref\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repository/{repository}/build/\n      name: listrepobuilds\n      operations:\n      - method: GET\n        name: listrepobuilds\n        description: List builds for a repository\n        call: quay.listrepobuilds\n        with:\n          repository: rest.repository\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /repository/{repository}/build/\n      name: requestrepobuild\n      operations:\n      - method: POST\n        name: requestrepobuild\n        description: Request a new build\n        call: quay.requestrepobuild\n        with:\n          repository: rest.repository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{orgname}\n      name: getorganization\n      operations:\n      - method: GET\n        name: getorganization\n        description: Get organization details\n        call: quay.getorganization\n        with:\n          orgname: rest.orgname\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{orgname}/team/{teamname}\n      name: updateorganizationteam\n      operations:\n      - method: PUT\n        name: updateorganizationteam\n        description: Create or update a team\n        call: quay.updateorganizationteam\n        with:\n          orgname: rest.orgname\n\
  \          teamname: rest.teamname\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{orgname}/robots/{robot_shortname}\n      name: createorgrobot\n      operations:\n      - method: PUT\n        name: createorgrobot\n        description: Create a robot account\n        call: quay.createorgrobot\n        with:\n          orgname: rest.orgname\n          robot_shortname: rest.robot_shortname\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user/\n      name: getloggedinuser\n      operations:\n      - method: GET\n        name: getloggedinuser\n        description: Get authenticated user\n        call: quay.getloggedinuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repository/{repository}/permissions/user/{username}\n      name: changeuserpermissions\n      operations:\n      - method: PUT\n        name: changeuserpermissions\n        description: Set user\
  \ repository permission\n        call: quay.changeuserpermissions\n        with:\n          repository: rest.repository\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: quay-mcp\n    transport: http\n    description: MCP adapter for Quay Container Registry API for AI agent use.\n    tools:\n    - name: listrepos\n      description: List repositories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quay.listrepos\n      with:\n        namespace: tools.namespace\n        public: tools.public\n        starred: tools.starred\n      inputParameters:\n      - name: namespace\n        type: string\n        description: namespace\n      - name: public\n        type: boolean\n        description: public\n      - name: starred\n        type: boolean\n        description: starred\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: createrepo\n      description: Create a new repository\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: quay.createrepo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrepo\n      description: Get repository details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quay.getrepo\n      with:\n        repository: tools.repository\n      inputParameters:\n      - name: repository\n        type: string\n        description: repository\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterepo\n      description: Delete repository\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: quay.deleterepo\n      with:\n        repository: tools.repository\n      inputParameters:\n      - name: repository\n        type: string\n\
  \        description: repository\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrepotags\n      description: List repository tags\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quay.listrepotags\n      with:\n        repository: tools.repository\n      inputParameters:\n      - name: repository\n        type: string\n        description: repository\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: changetag\n      description: Create or update a tag\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: quay.changetag\n      with:\n        repository: tools.repository\n        tag: tools.tag\n      inputParameters:\n      - name: repository\n        type: string\n        description: repository\n        required: true\n      - name: tag\n        type: string\n   \
  \     description: tag\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetag\n      description: Delete a tag\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: quay.deletetag\n      with:\n        repository: tools.repository\n        tag: tools.tag\n      inputParameters:\n      - name: repository\n        type: string\n        description: repository\n        required: true\n      - name: tag\n        type: string\n        description: tag\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmanifest\n      description: Get manifest by digest\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quay.getmanifest\n      with:\n        repository: tools.repository\n        manifestref: tools.manifestref\n      inputParameters:\n      - name: repository\n        type:\
  \ string\n        description: repository\n        required: true\n      - name: manifestref\n        type: string\n        description: manifestref\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmanifestsecurity\n      description: Get vulnerability scan results for a manifest\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quay.getmanifestsecurity\n      with:\n        repository: tools.repository\n        manifestref: tools.manifestref\n      inputParameters:\n      - name: repository\n        type: string\n        description: repository\n        required: true\n      - name: manifestref\n        type: string\n        description: manifestref\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrepobuilds\n      description: List builds for a repository\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: quay.listrepobuilds\n      with:\n        repository: tools.repository\n      inputParameters:\n      - name: repository\n        type: string\n        description: repository\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: requestrepobuild\n      description: Request a new build\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: quay.requestrepobuild\n      with:\n        repository: tools.repository\n      inputParameters:\n      - name: repository\n        type: string\n        description: repository\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorganization\n      description: Get organization details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quay.getorganization\n      with:\n        orgname: tools.orgname\n\
  \      inputParameters:\n      - name: orgname\n        type: string\n        description: orgname\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateorganizationteam\n      description: Create or update a team\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: quay.updateorganizationteam\n      with:\n        orgname: tools.orgname\n        teamname: tools.teamname\n      inputParameters:\n      - name: orgname\n        type: string\n        description: orgname\n        required: true\n      - name: teamname\n        type: string\n        description: teamname\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorgrobot\n      description: Create a robot account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: quay.createorgrobot\n      with:\n        orgname:\
  \ tools.orgname\n        robot_shortname: tools.robot_shortname\n      inputParameters:\n      - name: orgname\n        type: string\n        description: orgname\n        required: true\n      - name: robot_shortname\n        type: string\n        description: robot_shortname\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getloggedinuser\n      description: Get authenticated user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quay.getloggedinuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: changeuserpermissions\n      description: Set user repository permission\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: quay.changeuserpermissions\n      with:\n        repository: tools.repository\n        username: tools.username\n      inputParameters:\n      - name: repository\n        type:\
  \ string\n        description: repository\n        required: true\n      - name: username\n        type: string\n        description: username\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    QUAY_TOKEN: QUAY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/quay/refs/heads/main/capabilities/quay-capability.yaml
tags:
- Quay
- API
tools:
- description: List repositories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrepos
- description: Create a new repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrepo
- description: Get repository details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrepo
- description: Delete repository
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterepo
- description: List repository tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrepotags
- description: Create or update a tag
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: changetag
- description: Delete a tag
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetag
- description: Get manifest by digest
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmanifest
- description: Get vulnerability scan results for a manifest
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmanifestsecurity
- description: List builds for a repository
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrepobuilds
- description: Request a new build
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: requestrepobuild
- description: Get organization details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganization
- description: Create or update a team
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateorganizationteam
- description: Create a robot account
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createorgrobot
- description: Get authenticated user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getloggedinuser
- description: Set user repository permission
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: changeuserpermissions
---
