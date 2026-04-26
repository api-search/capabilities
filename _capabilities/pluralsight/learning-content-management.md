---
consumed_apis:
- pluralsight-content-catalog
- pluralsight-content-slug
- pluralsight-course-catalog
- pluralsight-public-course-catalog
- pluralsight-channels
- pluralsight-learning-paths
- pluralsight-programs
- pluralsight-labs
- pluralsight-tags
description: Unified workflow for L&D managers and content administrators to browse, organize, and manage learning content across courses, channels, learning paths, programs, labs, and tags. Combines content catalog, course catalog, public catalog, channels, learning paths, programs, labs, content slugs, and tags APIs.
layout: capability
name: Pluralsight Learning Content Management
operations:
- description: Query the general content catalog
  method: POST
  name: query-content-catalog
  path: /v1/content-catalog
- description: Resolve content slugs to internal identifiers
  method: POST
  name: query-content-slugs
  path: /v1/content-slugs
- description: Query the course catalog
  method: POST
  name: query-course-catalog
  path: /v1/course-catalog
- description: Retrieve the full public course catalog
  method: GET
  name: get-public-course-catalog
  path: /v1/public-courses
- description: Query and manage content channels
  method: POST
  name: manage-channels
  path: /v1/channels
- description: Query learning path catalog data
  method: POST
  name: query-learning-paths
  path: /v1/learning-paths
- description: Query the program catalog
  method: POST
  name: query-programs
  path: /v1/programs
- description: Query lab catalog and activity data
  method: POST
  name: query-labs
  path: /v1/labs
- description: Query content tags and taxonomy data
  method: POST
  name: query-tags
  path: /v1/tags
personas: []
provider_name: Pluralsight
provider_slug: pluralsight
search_terms:
- query and manage content channels
- public course catalog accessible without authentication
- query content tags and taxonomy data used to categorize and organize learning content.
- query programs
- query the general content catalog
- query tags
- engineering metrics
- query content catalog
- content management
- learning content
- course catalog with titles, descriptions, authors, and metadata
- query learning path catalog data including structured sequences of courses and content organized around specific skills and roles.
- learning
- resolve content slugs to internal identifiers
- content tags and taxonomy for categorization
- structured sequences of courses organized around skills and roles
- channels
- general content catalog including videos, guides, and interactive courses
- query content slugs
- query and manage content channels including creating channels, managing members and groups, organizing content sections, and tracking channel progress.
- query the general content catalog including videos, guides, interactive courses, and other content types.
- query lab catalog and lab activity data for hands-on learning experiences and practical exercises.
- courses
- manage channels
- query lab catalog and activity data
- structured learning programs and curriculum offerings
- retrieve the full public course catalog including course ids, titles, durations, release dates, and retirement status.
- query labs
- technology
- query the program catalog
- video training
- pluralsight
- skills assessment
- query the course catalog
- query learning path catalog data
- content channels for organizing and curating learning content
- hands-on labs and practical exercises
- query course catalog information including titles, descriptions, authors, duration, release dates, and retirement status.
- learning paths
- get public course catalog
- education
- query the program catalog including structured learning programs and curriculum offerings.
- resolve content slugs to internal identifiers for content lookup by human-readable url slugs.
- query course catalog
- retrieve the full public course catalog
- query learning paths
- query content tags and taxonomy data
slug: learning-content-management
tags:
- Pluralsight
- Learning Content
- Content Management
- Courses
- Channels
- Learning Paths
tools:
- description: Query the general content catalog including videos, guides, interactive courses, and other content types.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-content-catalog
- description: Resolve content slugs to internal identifiers for content lookup by human-readable URL slugs.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-content-slugs
- description: Query course catalog information including titles, descriptions, authors, duration, release dates, and retirement status.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-course-catalog
- description: Retrieve the full public course catalog including course IDs, titles, durations, release dates, and retirement status.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-public-course-catalog
- description: Query and manage content channels including creating channels, managing members and groups, organizing content sections, and tracking channel progress.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: manage-channels
- description: Query learning path catalog data including structured sequences of courses and content organized around specific skills and roles.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-learning-paths
- description: Query the program catalog including structured learning programs and curriculum offerings.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-programs
- description: Query lab catalog and lab activity data for hands-on learning experiences and practical exercises.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-labs
- description: Query content tags and taxonomy data used to categorize and organize learning content.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-tags
---
