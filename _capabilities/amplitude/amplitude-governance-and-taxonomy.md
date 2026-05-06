---
categories: []
consumed_apis: []
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
- amplitude update a user property
- amplitude update an event category
- scim provisioning and privacy compliance. for it admins and compliance teams.
- runs experiments and feature flags
- amplitude get a user property
- analytics
- amplitude create an event property
- taxonomy api getEventProperty
- updateEventProperty
- createAnnotation
- taxonomy api updateEventCategory
- user profile api getUserProfile
- identity management
- privacy compliance
- getEventType
- updateEventType
- listEventTypes
- amplitude create an event category
- deleteEventCategory
- chart annotations api updateAnnotation
- amplitude delete an event type
- createEventProperty
- taxonomy api getEventCategory
- taxonomy api updateEventProperty
- taxonomy api deleteUserProperty
- getEventProperty
- getAnnotation
- updateAnnotation
- manage and evaluate a/b experiments and feature flags. for product managers.
- amplitude list all user properties
- analyzes data and manages cohorts
- ingests and exports event data
- taxonomy api deleteEventCategory
- user behavior
- amplitude create a user property
- taxonomy api getEventType
- amplitude list all event types
- amplitude get an event category
- taxonomy api createUserProperty
- chart annotations api createAnnotation
- getUserProperty
- amplitude update an event property
- listUserProperties
- amplitude get an annotation
- taxonomy api updateEventType
- manage event schemas and chart annotations. for data governance teams.
- amplitude create an event type
- taxonomy api listEventTypes
- feature flags
- export raw event data and manage behavioral cohorts. for data analysts.
- amplitude get a user profile
- listAnnotations
- taxonomy api updateUserProperty
- taxonomy
- amplitude list all annotations
- taxonomy api listEventProperties
- updateUserProperty
- taxonomy api getUserProperty
- a/b testing
- updateEventCategory
- amplitude delete an annotation
- listEventProperties
- amplitude delete a user property
- experimentation
- amplitude delete an event property
- amplitude list all event properties
- data governance
- amplitude list all event categories
- amplitude
- amplitude get an event type
- chart annotations api listAnnotations
- taxonomy api listEventCategories
- createEventType
- chart annotations api deleteAnnotation
- taxonomy api createEventProperty
- amplitude update an event type
- taxonomy api createEventType
- getUserProfile
- taxonomy api deleteEventProperty
- deleteUserProperty
- deleteAnnotation
- createUserProperty
- chart annotations api getAnnotation
- unified workflow for sending events and identifying users. for data engineers.
- deleteEventType
- amplitude get an event property
- amplitude create an annotation
- deleteEventProperty
- getEventCategory
- amplitude update an annotation
- createEventCategory
- listEventCategories
- taxonomy api createEventCategory
- product analytics
- taxonomy api deleteEventType
- amplitude delete an event category
- taxonomy api listUserProperties
- manages privacy and compliance
slug: amplitude-governance-and-taxonomy
source_filename: amplitude-governance-and-taxonomy.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amplitude Governance and Taxonomy\n  description: Manage event schemas and chart annotations. For data governance teams.\n  tags:\n  - Amplitude\n  - Taxonomy\n  - Data Governance\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AMPLITUDE_API_KEY: AMPLITUDE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: chart-annotations-api\n    baseUri: https://amplitude.com\n    description: The Amplitude Chart Annotations API enables developers to programmatically create, retrieve, update, and\n      delete annotations on Amplitude charts. Annotations mark significant events such as product releases, marketing campaigns,\n      or incidents on timeline-based charts. This API allows teams to automate annotation management as part of their deployment\n      or release pipelines, ensuring that important context is always visible alongside analytics data.\n    resources:\n    - name: annotations\n\
  \      path: /annotations\n      description: Annotations operations\n      operations:\n      - name: listAnnotations\n        method: GET\n        description: Amplitude List All Annotations\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createAnnotation\n        method: POST\n        description: Amplitude Create an Annotation\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getAnnotation\n        method: GET\n        description: Amplitude Get an Annotation\n        inputParameters:\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ updateAnnotation\n        method: PUT\n        description: Amplitude Update an Annotation\n        inputParameters:\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteAnnotation\n        method: DELETE\n        description: Amplitude Delete an Annotation\n        inputParameters:\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    authentication:\n      type: basic\n      username: '{{AMPLITUDE_API_KEY}}'\n      password: '{{AMPLITUDE_SECRET_KEY}}'\n  - type: http\n    namespace: taxonomy-api\n    baseUri: https://amplitude.com\n    description: The Amplitude Taxonomy API\
  \ provides programmatic management of your analytics tracking plan. It supports\n      creating, reading, updating, and deleting event categories, event types, event properties, and user properties. This\n      API is essential for data governance workflows, enabling teams to maintain a consistent and well-organized event taxonomy\n      across their instrumentation without needing to use the Amplitude UI directly.\n    resources:\n    - name: event-categories\n      path: /event-categories\n      description: Event Categories operations\n      operations:\n      - name: listEventCategories\n        method: GET\n        description: Amplitude List All Event Categories\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createEventCategory\n        method: POST\n        description: Amplitude Create an Event Category\n        inputParameters: []\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getEventCategory\n        method: GET\n        description: Amplitude Get an Event Category\n        inputParameters:\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateEventCategory\n        method: PUT\n        description: Amplitude Update an Event Category\n        inputParameters:\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteEventCategory\n        method: DELETE\n        description: Amplitude Delete an Event Category\n        inputParameters:\n\
  \        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-types\n      path: /event-types\n      description: Event Types operations\n      operations:\n      - name: listEventTypes\n        method: GET\n        description: Amplitude List All Event Types\n        inputParameters:\n        - name: showDeleted\n          in: query\n          type: boolean\n          required: false\n          description: When true, include deleted event types in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createEventType\n        method: POST\n        description: Amplitude Create an Event Type\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n      - name: getEventType\n        method: GET\n        description: Amplitude Get an Event Type\n        inputParameters:\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateEventType\n        method: PUT\n        description: Amplitude Update an Event Type\n        inputParameters:\n        - name: param\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteEventType\n        method: DELETE\n        description: Amplitude Delete an Event Type\n        inputParameters:\n        - name: param\n          in: query\n \
  \         type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-properties\n      path: /event-properties\n      description: Event Properties operations\n      operations:\n      - name: listEventProperties\n        method: GET\n        description: Amplitude List All Event Properties\n        inputParameters:\n        - name: event_type\n          in: query\n          type: string\n          required: true\n          description: The event type to list properties for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createEventProperty\n        method: POST\n        description: Amplitude Create an Event Property\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: getEventProperty\n        method: GET\n        description: Amplitude Get an Event Property\n        inputParameters:\n        - name: event_property\n          in: path\n          type: string\n          required: true\n          description: The name of the event property.\n        - name: event_type\n          in: query\n          type: string\n          required: true\n          description: The event type the property belongs to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateEventProperty\n        method: PUT\n        description: Amplitude Update an Event Property\n        inputParameters:\n        - name: event_property\n          in: path\n          type: string\n          required: true\n          description: The name of the event property to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: deleteEventProperty\n        method: DELETE\n        description: Amplitude Delete an Event Property\n        inputParameters:\n        - name: event_property\n          in: path\n          type: string\n          required: true\n          description: The name of the event property to delete.\n        - name: event_type\n          in: query\n          type: string\n          required: true\n          description: The event type the property belongs to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-properties\n      path: /user-properties\n      description: User Properties operations\n      operations:\n      - name: listUserProperties\n        method: GET\n        description: Amplitude List All User Properties\n        inputParameters:\n        - name: showDeleted\n          in: query\n          type: boolean\n          required:\
  \ false\n          description: When true, include deleted user properties in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createUserProperty\n        method: POST\n        description: Amplitude Create a User Property\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUserProperty\n        method: GET\n        description: Amplitude Get a User Property\n        inputParameters:\n        - name: user_property\n          in: path\n          type: string\n          required: true\n          description: The name of the user property.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateUserProperty\n        method: PUT\n        description: Amplitude Update a User\
  \ Property\n        inputParameters:\n        - name: user_property\n          in: path\n          type: string\n          required: true\n          description: The name of the user property to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteUserProperty\n        method: DELETE\n        description: Amplitude Delete a User Property\n        inputParameters:\n        - name: user_property\n          in: path\n          type: string\n          required: true\n          description: The name of the user property to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    authentication:\n      type: basic\n      username: '{{AMPLITUDE_API_KEY}}'\n      password: '{{AMPLITUDE_SECRET_KEY}}'\n  - type: http\n    namespace: user-profile-api\n    baseUri: https://profile-api.amplitude.com\n    description:\
  \ The Amplitude User Profile API serves user profiles that include user properties, computed user properties,\n      a list of cohort IDs the user belongs to, and personalized recommendations. It enables real-time access to enriched\n      user data for powering personalization engines, in-app experiences, and targeted content delivery. This API is particularly\n      useful for retrieving recommendation results generated by Amplitude's machine learning models.\n    resources:\n    - name: profiles\n      path: /profiles\n      description: Profiles operations\n      operations:\n      - name: getUserProfile\n        method: GET\n        description: Amplitude Get a User Profile\n        inputParameters:\n        - name: user_id\n          in: query\n          type: string\n          required: true\n          description: The user_id of the user whose profile to retrieve.\n        - name: comp_id\n          in: query\n          type: integer\n          required: false\n          description:\
  \ The computed property ID or recommendation ID to retrieve specific computed results for the user.\n        - name: get_recs\n          in: query\n          type: boolean\n          required: false\n          description: When true, include personalized recommendations in the response.\n        - name: rec_id\n          in: query\n          type: string\n          required: false\n          description: The recommendation model ID to retrieve specific recommendation results.\n        - name: rec_type\n          in: query\n          type: string\n          required: false\n          description: The type of recommendation to retrieve.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of recommendation results to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    authentication:\n      type: apikey\n      key: Authorization\n\
  \      value: '{{AMPLITUDE_API_KEY}}'\n      placement: header\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: amplitude-governance-and-taxonomy-api\n    description: REST API for Amplitude Governance and Taxonomy\n    resources:\n    - path: /v1/annotations\n      name: annotations\n      operations:\n      - method: GET\n        name: listAnnotations\n        description: Amplitude List All Annotations\n        call: chart-annotations-api.listAnnotations\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/annotations\n      name: annotations\n      operations:\n      - method: POST\n        name: createAnnotation\n        description: Amplitude Create an Annotation\n        call: chart-annotations-api.createAnnotation\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/annotations\n      name: annotations\n      operations:\n      - method: GET\n        name:\
  \ getAnnotation\n        description: Amplitude Get an Annotation\n        call: chart-annotations-api.getAnnotation\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/annotations\n      name: annotations\n      operations:\n      - method: PUT\n        name: updateAnnotation\n        description: Amplitude Update an Annotation\n        call: chart-annotations-api.updateAnnotation\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/annotations\n      name: annotations\n      operations:\n      - method: DELETE\n        name: deleteAnnotation\n        description: Amplitude Delete an Annotation\n        call: chart-annotations-api.deleteAnnotation\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-categories\n      name: event-categories\n      operations:\n      - method: GET\n        name: listEventCategories\n\
  \        description: Amplitude List All Event Categories\n        call: taxonomy-api.listEventCategories\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-categories\n      name: event-categories\n      operations:\n      - method: POST\n        name: createEventCategory\n        description: Amplitude Create an Event Category\n        call: taxonomy-api.createEventCategory\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-categories\n      name: event-categories\n      operations:\n      - method: GET\n        name: getEventCategory\n        description: Amplitude Get an Event Category\n        call: taxonomy-api.getEventCategory\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-categories\n      name: event-categories\n      operations:\n      - method: PUT\n        name: updateEventCategory\n\
  \        description: Amplitude Update an Event Category\n        call: taxonomy-api.updateEventCategory\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-categories\n      name: event-categories\n      operations:\n      - method: DELETE\n        name: deleteEventCategory\n        description: Amplitude Delete an Event Category\n        call: taxonomy-api.deleteEventCategory\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-types\n      name: event-types\n      operations:\n      - method: GET\n        name: listEventTypes\n        description: Amplitude List All Event Types\n        call: taxonomy-api.listEventTypes\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-types\n      name: event-types\n      operations:\n      - method: POST\n        name: createEventType\n        description: Amplitude\
  \ Create an Event Type\n        call: taxonomy-api.createEventType\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-types\n      name: event-types\n      operations:\n      - method: GET\n        name: getEventType\n        description: Amplitude Get an Event Type\n        call: taxonomy-api.getEventType\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-types\n      name: event-types\n      operations:\n      - method: PUT\n        name: updateEventType\n        description: Amplitude Update an Event Type\n        call: taxonomy-api.updateEventType\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-types\n      name: event-types\n      operations:\n      - method: DELETE\n        name: deleteEventType\n        description: Amplitude Delete an Event Type\n        call: taxonomy-api.deleteEventType\n\
  \        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-properties\n      name: event-properties\n      operations:\n      - method: GET\n        name: listEventProperties\n        description: Amplitude List All Event Properties\n        call: taxonomy-api.listEventProperties\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-properties\n      name: event-properties\n      operations:\n      - method: POST\n        name: createEventProperty\n        description: Amplitude Create an Event Property\n        call: taxonomy-api.createEventProperty\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-properties\n      name: event-properties\n      operations:\n      - method: GET\n        name: getEventProperty\n        description: Amplitude Get an Event Property\n        call: taxonomy-api.getEventProperty\n\
  \        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-properties\n      name: event-properties\n      operations:\n      - method: PUT\n        name: updateEventProperty\n        description: Amplitude Update an Event Property\n        call: taxonomy-api.updateEventProperty\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-properties\n      name: event-properties\n      operations:\n      - method: DELETE\n        name: deleteEventProperty\n        description: Amplitude Delete an Event Property\n        call: taxonomy-api.deleteEventProperty\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-properties\n      name: user-properties\n      operations:\n      - method: GET\n        name: listUserProperties\n        description: Amplitude List All User Properties\n        call: taxonomy-api.listUserProperties\n\
  \        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-properties\n      name: user-properties\n      operations:\n      - method: POST\n        name: createUserProperty\n        description: Amplitude Create a User Property\n        call: taxonomy-api.createUserProperty\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-properties\n      name: user-properties\n      operations:\n      - method: GET\n        name: getUserProperty\n        description: Amplitude Get a User Property\n        call: taxonomy-api.getUserProperty\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-properties\n      name: user-properties\n      operations:\n      - method: PUT\n        name: updateUserProperty\n        description: Amplitude Update a User Property\n        call: taxonomy-api.updateUserProperty\n        with: {}\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-properties\n      name: user-properties\n      operations:\n      - method: DELETE\n        name: deleteUserProperty\n        description: Amplitude Delete a User Property\n        call: taxonomy-api.deleteUserProperty\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/profiles\n      name: profiles\n      operations:\n      - method: GET\n        name: getUserProfile\n        description: Amplitude Get a User Profile\n        call: user-profile-api.getUserProfile\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: amplitude-governance-and-taxonomy-mcp\n    transport: http\n    description: MCP for Amplitude Governance and Taxonomy\n    tools:\n    - name: chart-annotations-api-listAnnotations\n      description: Amplitude List All Annotations\n   \
  \   hints:\n        readOnly: true\n      call: chart-annotations-api.listAnnotations\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: chart-annotations-api-createAnnotation\n      description: Amplitude Create an Annotation\n      hints:\n        readOnly: false\n      call: chart-annotations-api.createAnnotation\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: chart-annotations-api-getAnnotation\n      description: Amplitude Get an Annotation\n      hints:\n        readOnly: true\n      call: chart-annotations-api.getAnnotation\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: chart-annotations-api-updateAnnotation\n      description: Amplitude Update an Annotation\n      hints:\n        readOnly: false\n      call: chart-annotations-api.updateAnnotation\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: chart-annotations-api-deleteAnnotation\n      description: Amplitude Delete an Annotation\n      hints:\n        readOnly: false\n      call: chart-annotations-api.deleteAnnotation\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-listEventCategories\n      description: Amplitude List All Event Categories\n      hints:\n        readOnly: true\n      call: taxonomy-api.listEventCategories\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-createEventCategory\n      description: Amplitude Create an Event Category\n      hints:\n        readOnly: false\n      call: taxonomy-api.createEventCategory\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-getEventCategory\n      description: Amplitude Get an Event Category\n      hints:\n        readOnly: true\n      call: taxonomy-api.getEventCategory\n      with:\
  \ {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-updateEventCategory\n      description: Amplitude Update an Event Category\n      hints:\n        readOnly: false\n      call: taxonomy-api.updateEventCategory\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-deleteEventCategory\n      description: Amplitude Delete an Event Category\n      hints:\n        readOnly: false\n      call: taxonomy-api.deleteEventCategory\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-listEventTypes\n      description: Amplitude List All Event Types\n      hints:\n        readOnly: true\n      call: taxonomy-api.listEventTypes\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-createEventType\n      description: Amplitude Create an Event Type\n      hints:\n        readOnly: false\n\
  \      call: taxonomy-api.createEventType\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-getEventType\n      description: Amplitude Get an Event Type\n      hints:\n        readOnly: true\n      call: taxonomy-api.getEventType\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-updateEventType\n      description: Amplitude Update an Event Type\n      hints:\n        readOnly: false\n      call: taxonomy-api.updateEventType\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-deleteEventType\n      description: Amplitude Delete an Event Type\n      hints:\n        readOnly: false\n      call: taxonomy-api.deleteEventType\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-listEventProperties\n      description: Amplitude List All Event Properties\n      hints:\n\
  \        readOnly: true\n      call: taxonomy-api.listEventProperties\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-createEventProperty\n      description: Amplitude Create an Event Property\n      hints:\n        readOnly: false\n      call: taxonomy-api.createEventProperty\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-getEventProperty\n      description: Amplitude Get an Event Property\n      hints:\n        readOnly: true\n      call: taxonomy-api.getEventProperty\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-updateEventProperty\n      description: Amplitude Update an Event Property\n      hints:\n        readOnly: false\n      call: taxonomy-api.updateEventProperty\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-deleteEventProperty\n\
  \      description: Amplitude Delete an Event Property\n      hints:\n        readOnly: false\n      call: taxonomy-api.deleteEventProperty\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-listUserProperties\n      description: Amplitude List All User Properties\n      hints:\n        readOnly: true\n      call: taxonomy-api.listUserProperties\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-createUserProperty\n      description: Amplitude Create a User Property\n      hints:\n        readOnly: false\n      call: taxonomy-api.createUserProperty\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-getUserProperty\n      description: Amplitude Get a User Property\n      hints:\n        readOnly: true\n      call: taxonomy-api.getUserProperty\n      with: {}\n      outputParameters:\n      - type: object\n      \
  \  mapping: $.\n    - name: taxonomy-api-updateUserProperty\n      description: Amplitude Update a User Property\n      hints:\n        readOnly: false\n      call: taxonomy-api.updateUserProperty\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomy-api-deleteUserProperty\n      description: Amplitude Delete a User Property\n      hints:\n        readOnly: false\n      call: taxonomy-api.deleteUserProperty\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: user-profile-api-getUserProfile\n      description: Amplitude Get a User Profile\n      hints:\n        readOnly: true\n      call: user-profile-api.getUserProfile\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
