---
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
- taxonomy api createUserProperty
- amplitude update an event property
- amplitude delete a user property
- chart annotations api createAnnotation
- manages privacy and compliance
- amplitude list all annotations
- listEventTypes
- amplitude create an event category
- analytics
- amplitude get an event type
- listEventCategories
- getUserProfile
- amplitude get a user property
- taxonomy api deleteEventType
- deleteEventType
- getEventType
- export raw event data and manage behavioral cohorts. for data analysts.
- updateEventType
- manage event schemas and chart annotations. for data governance teams.
- amplitude delete an event type
- taxonomy api getEventProperty
- taxonomy api listEventProperties
- amplitude list all event properties
- deleteEventProperty
- user profile api getUserProfile
- amplitude list all event categories
- feature flags
- amplitude
- taxonomy api getUserProperty
- taxonomy api getEventCategory
- createEventType
- product analytics
- createUserProperty
- deleteAnnotation
- taxonomy api createEventType
- amplitude create an event property
- analyzes data and manages cohorts
- taxonomy api updateEventProperty
- listUserProperties
- a/b testing
- amplitude get an event category
- taxonomy api updateUserProperty
- taxonomy api listEventCategories
- chart annotations api deleteAnnotation
- listAnnotations
- amplitude list all user properties
- amplitude list all event types
- amplitude update an event category
- taxonomy api getEventType
- amplitude get an annotation
- data governance
- taxonomy api listUserProperties
- chart annotations api listAnnotations
- taxonomy api createEventCategory
- listEventProperties
- updateAnnotation
- amplitude update an annotation
- ingests and exports event data
- taxonomy api listEventTypes
- amplitude get an event property
- amplitude update a user property
- taxonomy api createEventProperty
- taxonomy api deleteEventProperty
- getAnnotation
- amplitude delete an event property
- createEventCategory
- getUserProperty
- privacy compliance
- updateEventCategory
- amplitude create an annotation
- updateEventProperty
- chart annotations api getAnnotation
- user behavior
- runs experiments and feature flags
- amplitude delete an event category
- taxonomy api updateEventCategory
- amplitude create an event type
- taxonomy
- experimentation
- getEventProperty
- deleteUserProperty
- updateUserProperty
- taxonomy api deleteUserProperty
- identity management
- manage and evaluate a/b experiments and feature flags. for product managers.
- deleteEventCategory
- createAnnotation
- amplitude create a user property
- unified workflow for sending events and identifying users. for data engineers.
- amplitude delete an annotation
- getEventCategory
- chart annotations api updateAnnotation
- createEventProperty
- amplitude get a user profile
- taxonomy api deleteEventCategory
- taxonomy api updateEventType
- amplitude update an event type
- scim provisioning and privacy compliance. for it admins and compliance teams.
slug: amplitude-governance-and-taxonomy
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
