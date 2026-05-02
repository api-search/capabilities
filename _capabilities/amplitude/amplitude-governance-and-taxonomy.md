---
categories: []
consumed_apis:
- chart-annotations-api
- taxonomy-api
- user-profile-api
description: Manage event schemas and chart annotations. For data governance teams.
layout: capability
name: Amplitude Governance and Taxonomy
operations:
- description: Amplitude List All Annotations
  method: GET
  name: listAnnotations
  path: /v1/annotations
- description: Amplitude Create an Annotation
  method: POST
  name: createAnnotation
  path: /v1/annotations
- description: Amplitude Get an Annotation
  method: GET
  name: getAnnotation
  path: /v1/annotations
- description: Amplitude Update an Annotation
  method: PUT
  name: updateAnnotation
  path: /v1/annotations
- description: Amplitude Delete an Annotation
  method: DELETE
  name: deleteAnnotation
  path: /v1/annotations
- description: Amplitude List All Event Categories
  method: GET
  name: listEventCategories
  path: /v1/event-categories
- description: Amplitude Create an Event Category
  method: POST
  name: createEventCategory
  path: /v1/event-categories
- description: Amplitude Get an Event Category
  method: GET
  name: getEventCategory
  path: /v1/event-categories
- description: Amplitude Update an Event Category
  method: PUT
  name: updateEventCategory
  path: /v1/event-categories
- description: Amplitude Delete an Event Category
  method: DELETE
  name: deleteEventCategory
  path: /v1/event-categories
- description: Amplitude List All Event Types
  method: GET
  name: listEventTypes
  path: /v1/event-types
- description: Amplitude Create an Event Type
  method: POST
  name: createEventType
  path: /v1/event-types
- description: Amplitude Get an Event Type
  method: GET
  name: getEventType
  path: /v1/event-types
- description: Amplitude Update an Event Type
  method: PUT
  name: updateEventType
  path: /v1/event-types
- description: Amplitude Delete an Event Type
  method: DELETE
  name: deleteEventType
  path: /v1/event-types
- description: Amplitude List All Event Properties
  method: GET
  name: listEventProperties
  path: /v1/event-properties
- description: Amplitude Create an Event Property
  method: POST
  name: createEventProperty
  path: /v1/event-properties
- description: Amplitude Get an Event Property
  method: GET
  name: getEventProperty
  path: /v1/event-properties
- description: Amplitude Update an Event Property
  method: PUT
  name: updateEventProperty
  path: /v1/event-properties
- description: Amplitude Delete an Event Property
  method: DELETE
  name: deleteEventProperty
  path: /v1/event-properties
- description: Amplitude List All User Properties
  method: GET
  name: listUserProperties
  path: /v1/user-properties
- description: Amplitude Create a User Property
  method: POST
  name: createUserProperty
  path: /v1/user-properties
- description: Amplitude Get a User Property
  method: GET
  name: getUserProperty
  path: /v1/user-properties
- description: Amplitude Update a User Property
  method: PUT
  name: updateUserProperty
  path: /v1/user-properties
- description: Amplitude Delete a User Property
  method: DELETE
  name: deleteUserProperty
  path: /v1/user-properties
- description: Amplitude Get a User Profile
  method: GET
  name: getUserProfile
  path: /v1/profiles
personas: []
provider_name: Amplitude
provider_slug: amplitude
search_terms:
- amplitude list all event types
- deleteUserProperty
- taxonomy api listUserProperties
- privacy compliance
- taxonomy api deleteEventProperty
- amplitude delete an event property
- taxonomy api updateEventCategory
- manage and evaluate a/b experiments and feature flags. for product managers.
- taxonomy api createEventCategory
- amplitude get an event category
- amplitude update an event category
- chart annotations api deleteAnnotation
- amplitude update an event type
- chart annotations api getAnnotation
- listEventCategories
- listAnnotations
- taxonomy api listEventCategories
- updateEventType
- taxonomy api deleteUserProperty
- deleteAnnotation
- updateEventCategory
- scim provisioning and privacy compliance. for it admins and compliance teams.
- deleteEventProperty
- getEventProperty
- taxonomy api updateEventType
- taxonomy api getUserProperty
- amplitude list all annotations
- data governance
- createUserProperty
- amplitude
- runs experiments and feature flags
- user profile api getUserProfile
- analytics
- chart annotations api createAnnotation
- a/b testing
- amplitude update an annotation
- user behavior
- getAnnotation
- taxonomy
- unified workflow for sending events and identifying users. for data engineers.
- amplitude list all event categories
- createEventType
- amplitude update an event property
- chart annotations api updateAnnotation
- createEventProperty
- amplitude create an annotation
- createAnnotation
- taxonomy api createEventProperty
- taxonomy api listEventTypes
- getUserProfile
- taxonomy api getEventType
- taxonomy api deleteEventType
- taxonomy api createUserProperty
- amplitude create an event type
- ingests and exports event data
- getEventType
- updateEventProperty
- amplitude get a user property
- amplitude delete an annotation
- chart annotations api listAnnotations
- manage event schemas and chart annotations. for data governance teams.
- amplitude create an event category
- amplitude create an event property
- listUserProperties
- amplitude update a user property
- identity management
- taxonomy api listEventProperties
- taxonomy api updateUserProperty
- export raw event data and manage behavioral cohorts. for data analysts.
- feature flags
- updateAnnotation
- amplitude get an event property
- getUserProperty
- analyzes data and manages cohorts
- createEventCategory
- updateUserProperty
- experimentation
- taxonomy api createEventType
- amplitude delete an event type
- amplitude list all event properties
- deleteEventType
- amplitude get a user profile
- listEventProperties
- product analytics
- taxonomy api deleteEventCategory
- deleteEventCategory
- taxonomy api getEventCategory
- amplitude delete an event category
- taxonomy api getEventProperty
- amplitude delete a user property
- listEventTypes
- amplitude get an event type
- amplitude get an annotation
- amplitude list all user properties
- taxonomy api updateEventProperty
- amplitude create a user property
- manages privacy and compliance
- getEventCategory
slug: amplitude-governance-and-taxonomy
source_filename: amplitude-governance-and-taxonomy.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amplitude Governance and Taxonomy\n  description: Manage event schemas and chart annotations. For data governance teams.\n  tags:\n  - Amplitude\n  - Taxonomy\n  - Data Governance\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AMPLITUDE_API_KEY: AMPLITUDE_API_KEY\ncapability:\n  consumes:\n  - import: chart-annotations-api\n    location: ./shared/chart-annotations-api.yaml\n  - import: taxonomy-api\n    location: ./shared/taxonomy-api.yaml\n  - import: user-profile-api\n    location: ./shared/user-profile-api.yaml\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: amplitude-governance-and-taxonomy-api\n    description: REST API for Amplitude Governance and Taxonomy\n    resources:\n    - path: /v1/annotations\n      name: annotations\n      operations:\n      - method: GET\n        name: listAnnotations\n        description: Amplitude List All Annotations\n        call: chart-annotations-api.listAnnotations\n\
  \        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/annotations\n      name: annotations\n      operations:\n      - method: POST\n        name: createAnnotation\n        description: Amplitude Create an Annotation\n        call: chart-annotations-api.createAnnotation\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/annotations\n      name: annotations\n      operations:\n      - method: GET\n        name: getAnnotation\n        description: Amplitude Get an Annotation\n        call: chart-annotations-api.getAnnotation\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/annotations\n      name: annotations\n      operations:\n      - method: PUT\n        name: updateAnnotation\n        description: Amplitude Update an Annotation\n        call: chart-annotations-api.updateAnnotation\n        with: {}\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/annotations\n      name: annotations\n      operations:\n      - method: DELETE\n        name: deleteAnnotation\n        description: Amplitude Delete an Annotation\n        call: chart-annotations-api.deleteAnnotation\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-categories\n      name: event-categories\n      operations:\n      - method: GET\n        name: listEventCategories\n        description: Amplitude List All Event Categories\n        call: taxonomy-api.listEventCategories\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-categories\n      name: event-categories\n      operations:\n      - method: POST\n        name: createEventCategory\n        description: Amplitude Create an Event Category\n        call: taxonomy-api.createEventCategory\n        with: {}\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/event-categories\n      name: event-categories\n      operations:\n      - method: GET\n        name: getEventCategory\n        description: Amplitude Get an Event Category\n        call: taxonomy-api.getEventCategory\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-categories\n      name: event-categories\n      operations:\n      - method: PUT\n        name: updateEventCategory\n        description: Amplitude Update an Event Category\n        call: taxonomy-api.updateEventCategory\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-categories\n      name: event-categories\n      operations:\n      - method: DELETE\n        name: deleteEventCategory\n        description: Amplitude Delete an Event Category\n        call: taxonomy-api.deleteEventCategory\n        with: {}\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/event-types\n      name: event-types\n      operations:\n      - method: GET\n        name: listEventTypes\n        description: Amplitude List All Event Types\n        call: taxonomy-api.listEventTypes\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-types\n      name: event-types\n      operations:\n      - method: POST\n        name: createEventType\n        description: Amplitude Create an Event Type\n        call: taxonomy-api.createEventType\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-types\n      name: event-types\n      operations:\n      - method: GET\n        name: getEventType\n        description: Amplitude Get an Event Type\n        call: taxonomy-api.getEventType\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-types\n\
  \      name: event-types\n      operations:\n      - method: PUT\n        name: updateEventType\n        description: Amplitude Update an Event Type\n        call: taxonomy-api.updateEventType\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-types\n      name: event-types\n      operations:\n      - method: DELETE\n        name: deleteEventType\n        description: Amplitude Delete an Event Type\n        call: taxonomy-api.deleteEventType\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-properties\n      name: event-properties\n      operations:\n      - method: GET\n        name: listEventProperties\n        description: Amplitude List All Event Properties\n        call: taxonomy-api.listEventProperties\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-properties\n      name: event-properties\n\
  \      operations:\n      - method: POST\n        name: createEventProperty\n        description: Amplitude Create an Event Property\n        call: taxonomy-api.createEventProperty\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-properties\n      name: event-properties\n      operations:\n      - method: GET\n        name: getEventProperty\n        description: Amplitude Get an Event Property\n        call: taxonomy-api.getEventProperty\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-properties\n      name: event-properties\n      operations:\n      - method: PUT\n        name: updateEventProperty\n        description: Amplitude Update an Event Property\n        call: taxonomy-api.updateEventProperty\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-properties\n      name: event-properties\n\
  \      operations:\n      - method: DELETE\n        name: deleteEventProperty\n        description: Amplitude Delete an Event Property\n        call: taxonomy-api.deleteEventProperty\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-properties\n      name: user-properties\n      operations:\n      - method: GET\n        name: listUserProperties\n        description: Amplitude List All User Properties\n        call: taxonomy-api.listUserProperties\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-properties\n      name: user-properties\n      operations:\n      - method: POST\n        name: createUserProperty\n        description: Amplitude Create a User Property\n        call: taxonomy-api.createUserProperty\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-properties\n      name: user-properties\n\
  \      operations:\n      - method: GET\n        name: getUserProperty\n        description: Amplitude Get a User Property\n        call: taxonomy-api.getUserProperty\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-properties\n      name: user-properties\n      operations:\n      - method: PUT\n        name: updateUserProperty\n        description: Amplitude Update a User Property\n        call: taxonomy-api.updateUserProperty\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-properties\n      name: user-properties\n      operations:\n      - method: DELETE\n        name: deleteUserProperty\n        description: Amplitude Delete a User Property\n        call: taxonomy-api.deleteUserProperty\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/profiles\n      name: profiles\n      operations:\n      - method:\
  \ GET\n        name: getUserProfile\n        description: Amplitude Get a User Profile\n        call: user-profile-api.getUserProfile\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: amplitude-governance-and-taxonomy-mcp\n    transport: http\n    description: MCP for Amplitude Governance and Taxonomy\n    tools:\n    - name: chart-annotations-api-listAnnotations\n      description: Amplitude List All Annotations\n      hints:\n        readOnly: true\n      call: chart-annotations-api.listAnnotations\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: chart-annotations-api-createAnnotation\n      description: Amplitude Create an Annotation\n      hints:\n        readOnly: false\n      call: chart-annotations-api.createAnnotation\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: chart-annotations-api-getAnnotation\n\
  \      description: Amplitude Get an Annotation\n      hints:\n        readOnly: true\n      call: chart-annotations-api.getAnnotation\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: chart-annotations-api-updateAnnotation\n      description: Amplitude Update an Annotation\n      hints:\n        readOnly: false\n      call: chart-annotations-api.updateAnnotation\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: chart-annotations-api-deleteAnnotation\n      description: Amplitude Delete an Annotation\n      hints:\n        readOnly: false\n      call: chart-annotations-api.deleteAnnotation\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-listEventCategories\n      description: Amplitude List All Event Categories\n      hints:\n        readOnly: true\n      call: taxonomy-api.listEventCategories\n      with: {}\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: taxonomy-api-createEventCategory\n      description: Amplitude Create an Event Category\n      hints:\n        readOnly: false\n      call: taxonomy-api.createEventCategory\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-getEventCategory\n      description: Amplitude Get an Event Category\n      hints:\n        readOnly: true\n      call: taxonomy-api.getEventCategory\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-updateEventCategory\n      description: Amplitude Update an Event Category\n      hints:\n        readOnly: false\n      call: taxonomy-api.updateEventCategory\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-deleteEventCategory\n      description: Amplitude Delete an Event Category\n      hints:\n        readOnly: false\n      call: taxonomy-api.deleteEventCategory\n\
  \      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-listEventTypes\n      description: Amplitude List All Event Types\n      hints:\n        readOnly: true\n      call: taxonomy-api.listEventTypes\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-createEventType\n      description: Amplitude Create an Event Type\n      hints:\n        readOnly: false\n      call: taxonomy-api.createEventType\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-getEventType\n      description: Amplitude Get an Event Type\n      hints:\n        readOnly: true\n      call: taxonomy-api.getEventType\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-updateEventType\n      description: Amplitude Update an Event Type\n      hints:\n        readOnly: false\n      call: taxonomy-api.updateEventType\n\
  \      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-deleteEventType\n      description: Amplitude Delete an Event Type\n      hints:\n        readOnly: false\n      call: taxonomy-api.deleteEventType\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-listEventProperties\n      description: Amplitude List All Event Properties\n      hints:\n        readOnly: true\n      call: taxonomy-api.listEventProperties\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-createEventProperty\n      description: Amplitude Create an Event Property\n      hints:\n        readOnly: false\n      call: taxonomy-api.createEventProperty\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-getEventProperty\n      description: Amplitude Get an Event Property\n      hints:\n       \
  \ readOnly: true\n      call: taxonomy-api.getEventProperty\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-updateEventProperty\n      description: Amplitude Update an Event Property\n      hints:\n        readOnly: false\n      call: taxonomy-api.updateEventProperty\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-deleteEventProperty\n      description: Amplitude Delete an Event Property\n      hints:\n        readOnly: false\n      call: taxonomy-api.deleteEventProperty\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-listUserProperties\n      description: Amplitude List All User Properties\n      hints:\n        readOnly: true\n      call: taxonomy-api.listUserProperties\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-createUserProperty\n  \
  \    description: Amplitude Create a User Property\n      hints:\n        readOnly: false\n      call: taxonomy-api.createUserProperty\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-getUserProperty\n      description: Amplitude Get a User Property\n      hints:\n        readOnly: true\n      call: taxonomy-api.getUserProperty\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-updateUserProperty\n      description: Amplitude Update a User Property\n      hints:\n        readOnly: false\n      call: taxonomy-api.updateUserProperty\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-deleteUserProperty\n      description: Amplitude Delete a User Property\n      hints:\n        readOnly: false\n      call: taxonomy-api.deleteUserProperty\n      with: {}\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: user-profile-api-getUserProfile\n      description: Amplitude Get a User Profile\n      hints:\n        readOnly: true\n      call: user-profile-api.getUserProfile\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amplitude/refs/heads/main/capabilities/amplitude-governance-and-taxonomy.yaml
tags:
- Amplitude
- Taxonomy
- Data Governance
tools:
- description: Amplitude List All Annotations
  hints:
    readOnly: true
  name: chart-annotations-api-listAnnotations
- description: Amplitude Create an Annotation
  hints:
    readOnly: false
  name: chart-annotations-api-createAnnotation
- description: Amplitude Get an Annotation
  hints:
    readOnly: true
  name: chart-annotations-api-getAnnotation
- description: Amplitude Update an Annotation
  hints:
    readOnly: false
  name: chart-annotations-api-updateAnnotation
- description: Amplitude Delete an Annotation
  hints:
    readOnly: false
  name: chart-annotations-api-deleteAnnotation
- description: Amplitude List All Event Categories
  hints:
    readOnly: true
  name: taxonomy-api-listEventCategories
- description: Amplitude Create an Event Category
  hints:
    readOnly: false
  name: taxonomy-api-createEventCategory
- description: Amplitude Get an Event Category
  hints:
    readOnly: true
  name: taxonomy-api-getEventCategory
- description: Amplitude Update an Event Category
  hints:
    readOnly: false
  name: taxonomy-api-updateEventCategory
- description: Amplitude Delete an Event Category
  hints:
    readOnly: false
  name: taxonomy-api-deleteEventCategory
- description: Amplitude List All Event Types
  hints:
    readOnly: true
  name: taxonomy-api-listEventTypes
- description: Amplitude Create an Event Type
  hints:
    readOnly: false
  name: taxonomy-api-createEventType
- description: Amplitude Get an Event Type
  hints:
    readOnly: true
  name: taxonomy-api-getEventType
- description: Amplitude Update an Event Type
  hints:
    readOnly: false
  name: taxonomy-api-updateEventType
- description: Amplitude Delete an Event Type
  hints:
    readOnly: false
  name: taxonomy-api-deleteEventType
- description: Amplitude List All Event Properties
  hints:
    readOnly: true
  name: taxonomy-api-listEventProperties
- description: Amplitude Create an Event Property
  hints:
    readOnly: false
  name: taxonomy-api-createEventProperty
- description: Amplitude Get an Event Property
  hints:
    readOnly: true
  name: taxonomy-api-getEventProperty
- description: Amplitude Update an Event Property
  hints:
    readOnly: false
  name: taxonomy-api-updateEventProperty
- description: Amplitude Delete an Event Property
  hints:
    readOnly: false
  name: taxonomy-api-deleteEventProperty
- description: Amplitude List All User Properties
  hints:
    readOnly: true
  name: taxonomy-api-listUserProperties
- description: Amplitude Create a User Property
  hints:
    readOnly: false
  name: taxonomy-api-createUserProperty
- description: Amplitude Get a User Property
  hints:
    readOnly: true
  name: taxonomy-api-getUserProperty
- description: Amplitude Update a User Property
  hints:
    readOnly: false
  name: taxonomy-api-updateUserProperty
- description: Amplitude Delete a User Property
  hints:
    readOnly: false
  name: taxonomy-api-deleteUserProperty
- description: Amplitude Get a User Profile
  hints:
    readOnly: true
  name: user-profile-api-getUserProfile
---
