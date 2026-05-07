---
categories: []
consumed_apis: []
description: The Google Classroom API manages courses, coursework, student submissions, announcements, materials, rosters, topics, invitations, guardians, and integrations with third-party add-ons for educational workflows.
layout: capability
name: Google Classroom API
operations:
- description: Google Classroom List courses
  method: GET
  name: listcourses
  path: /v1/courses
- description: Google Classroom Create course
  method: POST
  name: createcourse
  path: /v1/courses
- description: Google Classroom Get course
  method: GET
  name: getcourse
  path: /v1/courses/{id}
- description: Google Classroom Update course
  method: PUT
  name: updatecourse
  path: /v1/courses/{id}
- description: Google Classroom Patch course
  method: PATCH
  name: patchcourse
  path: /v1/courses/{id}
- description: Google Classroom Delete course
  method: DELETE
  name: deletecourse
  path: /v1/courses/{id}
- description: Google Classroom List course work
  method: GET
  name: listcoursework
  path: /v1/courses/{courseId}/courseWork
- description: Google Classroom Create course work
  method: POST
  name: createcoursework
  path: /v1/courses/{courseId}/courseWork
- description: Google Classroom Get course work
  method: GET
  name: getcoursework
  path: /v1/courses/{courseId}/courseWork/{id}
- description: Google Classroom Patch course work
  method: PATCH
  name: patchcoursework
  path: /v1/courses/{courseId}/courseWork/{id}
- description: Google Classroom Delete course work
  method: DELETE
  name: deletecoursework
  path: /v1/courses/{courseId}/courseWork/{id}
- description: Google Classroom List student submissions
  method: GET
  name: liststudentsubmissions
  path: /v1/courses/{courseId}/courseWork/{courseWorkId}/studentSubmissions
- description: Google Classroom List students
  method: GET
  name: liststudents
  path: /v1/courses/{courseId}/students
- description: Google Classroom Add student
  method: POST
  name: addstudent
  path: /v1/courses/{courseId}/students
- description: Google Classroom List teachers
  method: GET
  name: listteachers
  path: /v1/courses/{courseId}/teachers
- description: Google Classroom Add teacher
  method: POST
  name: addteacher
  path: /v1/courses/{courseId}/teachers
- description: Google Classroom List announcements
  method: GET
  name: listannouncements
  path: /v1/courses/{courseId}/announcements
- description: Google Classroom Create announcement
  method: POST
  name: createannouncement
  path: /v1/courses/{courseId}/announcements
- description: Google Classroom List topics
  method: GET
  name: listtopics
  path: /v1/courses/{courseId}/topics
- description: Google Classroom Create topic
  method: POST
  name: createtopic
  path: /v1/courses/{courseId}/topics
- description: Google Classroom List invitations
  method: GET
  name: listinvitations
  path: /v1/invitations
- description: Google Classroom Create invitation
  method: POST
  name: createinvitation
  path: /v1/invitations
- description: Google Classroom Get user profile
  method: GET
  name: getuserprofile
  path: /v1/userProfiles/{userId}
personas: []
provider_name: Google Classroom
provider_slug: google-classroom
search_terms:
- google classroom get course
- courses
- listinvitations
- createcourse
- createtopic
- google classroom list topics
- listannouncements
- google classroom get user profile
- addteacher
- google classroom create course work
- google classroom patch course work
- getcoursework
- api
- google classroom delete course
- google classroom update course
- liststudentsubmissions
- listteachers
- addstudent
- updatecourse
- google classroom create announcement
- google classroom create invitation
- google classroom list teachers
- google classroom delete course work
- patchcourse
- google
- getcourse
- deletecourse
- google classroom list course work
- createannouncement
- google classroom patch course
- google classroom list courses
- google classroom list students
- google classroom get course work
- classroom
- google classroom list student submissions
- listcourses
- deletecoursework
- createcoursework
- google classroom list invitations
- createinvitation
- google classroom add student
- patchcoursework
- education
- google workspace
- listtopics
- getuserprofile
- assignments
- liststudents
- google classroom create course
- google classroom add teacher
- google classroom list announcements
- google classroom create topic
- listcoursework
- students
slug: google-classroom-capability
source_filename: google-classroom-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Classroom API\n  description: The Google Classroom API manages courses, coursework, student submissions, announcements, materials, rosters,\n    topics, invitations, guardians, and integrations with third-party add-ons for educational workflows.\n  tags:\n  - Google\n  - Classroom\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-classroom\n    baseUri: https://classroom.googleapis.com\n    description: Google Classroom API HTTP API.\n    resources:\n    - name: v1-courses\n      path: /v1/courses\n      operations:\n      - name: listcourses\n        method: GET\n        description: Google Classroom List courses\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: studentId\n          in: query\n          type: string\n \
  \       - name: teacherId\n          in: query\n          type: string\n        - name: courseStates\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcourse\n        method: POST\n        description: Google Classroom Create course\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-courses-id\n      path: /v1/courses/{id}\n      operations:\n      - name: getcourse\n        method: GET\n        description: Google Classroom Get course\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecourse\n        method: PUT\n        description: Google Classroom\
  \ Update course\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchcourse\n        method: PATCH\n        description: Google Classroom Patch course\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: updateMask\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecourse\n        method: DELETE\n        description: Google Classroom Delete course\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: v1-courses-courseid-coursework\n      path: /v1/courses/{courseId}/courseWork\n      operations:\n      - name: listcoursework\n        method: GET\n        description: Google Classroom List course work\n        inputParameters:\n        - name: courseId\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcoursework\n        method: POST\n        description: Google Classroom Create course work\n        inputParameters:\n        - name: courseId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ v1-courses-courseid-coursework-id\n      path: /v1/courses/{courseId}/courseWork/{id}\n      operations:\n      - name: getcoursework\n        method: GET\n        description: Google Classroom Get course work\n        inputParameters:\n        - name: courseId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchcoursework\n        method: PATCH\n        description: Google Classroom Patch course work\n        inputParameters:\n        - name: courseId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: updateMask\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deletecoursework\n        method: DELETE\n        description: Google Classroom Delete course work\n        inputParameters:\n        - name: courseId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-courses-courseid-coursework-courseworkid-stud\n      path: /v1/courses/{courseId}/courseWork/{courseWorkId}/studentSubmissions\n      operations:\n      - name: liststudentsubmissions\n        method: GET\n        description: Google Classroom List student submissions\n        inputParameters:\n        - name: courseId\n          in: path\n          type: string\n          required: true\n        - name: courseWorkId\n          in: path\n          type: string\n\
  \          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-courses-courseid-students\n      path: /v1/courses/{courseId}/students\n      operations:\n      - name: liststudents\n        method: GET\n        description: Google Classroom List students\n        inputParameters:\n        - name: courseId\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addstudent\n        method: POST\n        description: Google Classroom Add student\n \
  \       inputParameters:\n        - name: courseId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-courses-courseid-teachers\n      path: /v1/courses/{courseId}/teachers\n      operations:\n      - name: listteachers\n        method: GET\n        description: Google Classroom List teachers\n        inputParameters:\n        - name: courseId\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addteacher\n        method: POST\n        description: Google Classroom Add teacher\n        inputParameters:\n        - name: courseId\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-courses-courseid-announcements\n      path: /v1/courses/{courseId}/announcements\n      operations:\n      - name: listannouncements\n        method: GET\n        description: Google Classroom List announcements\n        inputParameters:\n        - name: courseId\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createannouncement\n        method: POST\n        description: Google Classroom Create announcement\n        inputParameters:\n        - name: courseId\n          in:\
  \ path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-courses-courseid-topics\n      path: /v1/courses/{courseId}/topics\n      operations:\n      - name: listtopics\n        method: GET\n        description: Google Classroom List topics\n        inputParameters:\n        - name: courseId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtopic\n        method: POST\n        description: Google Classroom Create topic\n        inputParameters:\n        - name: courseId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-invitations\n\
  \      path: /v1/invitations\n      operations:\n      - name: listinvitations\n        method: GET\n        description: Google Classroom List invitations\n        inputParameters:\n        - name: courseId\n          in: query\n          type: string\n        - name: userId\n          in: query\n          type: string\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createinvitation\n        method: POST\n        description: Google Classroom Create invitation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-userprofiles-userid\n      path: /v1/userProfiles/{userId}\n      operations:\n      - name: getuserprofile\n        method: GET\n        description: Google\
  \ Classroom Get user profile\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-classroom-rest\n    description: REST adapter for Google Classroom API.\n    resources:\n    - path: /v1/courses\n      name: listcourses\n      operations:\n      - method: GET\n        name: listcourses\n        description: Google Classroom List courses\n        call: google-classroom.listcourses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses\n      name: createcourse\n      operations:\n      - method: POST\n        name: createcourse\n        description: Google Classroom Create course\n        call: google-classroom.createcourse\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/courses/{id}\n      name: getcourse\n      operations:\n      - method: GET\n        name: getcourse\n        description: Google Classroom Get course\n        call: google-classroom.getcourse\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{id}\n      name: updatecourse\n      operations:\n      - method: PUT\n        name: updatecourse\n        description: Google Classroom Update course\n        call: google-classroom.updatecourse\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{id}\n      name: patchcourse\n      operations:\n      - method: PATCH\n        name: patchcourse\n        description: Google Classroom Patch course\n        call: google-classroom.patchcourse\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/courses/{id}\n      name: deletecourse\n      operations:\n      - method: DELETE\n        name: deletecourse\n        description: Google Classroom Delete course\n        call: google-classroom.deletecourse\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/courseWork\n      name: listcoursework\n      operations:\n      - method: GET\n        name: listcoursework\n        description: Google Classroom List course work\n        call: google-classroom.listcoursework\n        with:\n          courseId: rest.courseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/courseWork\n      name: createcoursework\n      operations:\n      - method: POST\n        name: createcoursework\n        description: Google Classroom Create course work\n        call: google-classroom.createcoursework\n        with:\n          courseId: rest.courseId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/courseWork/{id}\n      name: getcoursework\n      operations:\n      - method: GET\n        name: getcoursework\n        description: Google Classroom Get course work\n        call: google-classroom.getcoursework\n        with:\n          courseId: rest.courseId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/courseWork/{id}\n      name: patchcoursework\n      operations:\n      - method: PATCH\n        name: patchcoursework\n        description: Google Classroom Patch course work\n        call: google-classroom.patchcoursework\n        with:\n          courseId: rest.courseId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/courseWork/{id}\n      name: deletecoursework\n      operations:\n      - method: DELETE\n\
  \        name: deletecoursework\n        description: Google Classroom Delete course work\n        call: google-classroom.deletecoursework\n        with:\n          courseId: rest.courseId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/courseWork/{courseWorkId}/studentSubmissions\n      name: liststudentsubmissions\n      operations:\n      - method: GET\n        name: liststudentsubmissions\n        description: Google Classroom List student submissions\n        call: google-classroom.liststudentsubmissions\n        with:\n          courseId: rest.courseId\n          courseWorkId: rest.courseWorkId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/students\n      name: liststudents\n      operations:\n      - method: GET\n        name: liststudents\n        description: Google Classroom List students\n        call: google-classroom.liststudents\n\
  \        with:\n          courseId: rest.courseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/students\n      name: addstudent\n      operations:\n      - method: POST\n        name: addstudent\n        description: Google Classroom Add student\n        call: google-classroom.addstudent\n        with:\n          courseId: rest.courseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/teachers\n      name: listteachers\n      operations:\n      - method: GET\n        name: listteachers\n        description: Google Classroom List teachers\n        call: google-classroom.listteachers\n        with:\n          courseId: rest.courseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/teachers\n      name: addteacher\n      operations:\n      - method: POST\n        name: addteacher\n        description: Google\
  \ Classroom Add teacher\n        call: google-classroom.addteacher\n        with:\n          courseId: rest.courseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/announcements\n      name: listannouncements\n      operations:\n      - method: GET\n        name: listannouncements\n        description: Google Classroom List announcements\n        call: google-classroom.listannouncements\n        with:\n          courseId: rest.courseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/announcements\n      name: createannouncement\n      operations:\n      - method: POST\n        name: createannouncement\n        description: Google Classroom Create announcement\n        call: google-classroom.createannouncement\n        with:\n          courseId: rest.courseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/topics\n\
  \      name: listtopics\n      operations:\n      - method: GET\n        name: listtopics\n        description: Google Classroom List topics\n        call: google-classroom.listtopics\n        with:\n          courseId: rest.courseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/topics\n      name: createtopic\n      operations:\n      - method: POST\n        name: createtopic\n        description: Google Classroom Create topic\n        call: google-classroom.createtopic\n        with:\n          courseId: rest.courseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invitations\n      name: listinvitations\n      operations:\n      - method: GET\n        name: listinvitations\n        description: Google Classroom List invitations\n        call: google-classroom.listinvitations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invitations\n\
  \      name: createinvitation\n      operations:\n      - method: POST\n        name: createinvitation\n        description: Google Classroom Create invitation\n        call: google-classroom.createinvitation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/userProfiles/{userId}\n      name: getuserprofile\n      operations:\n      - method: GET\n        name: getuserprofile\n        description: Google Classroom Get user profile\n        call: google-classroom.getuserprofile\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-classroom-mcp\n    transport: http\n    description: MCP adapter for Google Classroom API for AI agent use.\n    tools:\n    - name: listcourses\n      description: Google Classroom List courses\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-classroom.listcourses\n\
  \      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        studentId: tools.studentId\n        teacherId: tools.teacherId\n        courseStates: tools.courseStates\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: studentId\n        type: string\n        description: studentId\n      - name: teacherId\n        type: string\n        description: teacherId\n      - name: courseStates\n        type: array\n        description: courseStates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcourse\n      description: Google Classroom Create course\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-classroom.createcourse\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcourse\n     \
  \ description: Google Classroom Get course\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-classroom.getcourse\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecourse\n      description: Google Classroom Update course\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-classroom.updatecourse\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchcourse\n      description: Google Classroom Patch course\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ google-classroom.patchcourse\n      with:\n        id: tools.id\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      - name: updateMask\n        type: string\n        description: updateMask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecourse\n      description: Google Classroom Delete course\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-classroom.deletecourse\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcoursework\n      description: Google Classroom List course work\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-classroom.listcoursework\n\
  \      with:\n        courseId: tools.courseId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: courseId\n        type: string\n        description: courseId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcoursework\n      description: Google Classroom Create course work\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-classroom.createcoursework\n      with:\n        courseId: tools.courseId\n      inputParameters:\n      - name: courseId\n        type: string\n        description: courseId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcoursework\n      description: Google Classroom Get\
  \ course work\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-classroom.getcoursework\n      with:\n        courseId: tools.courseId\n        id: tools.id\n      inputParameters:\n      - name: courseId\n        type: string\n        description: courseId\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchcoursework\n      description: Google Classroom Patch course work\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-classroom.patchcoursework\n      with:\n        courseId: tools.courseId\n        id: tools.id\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: courseId\n        type: string\n        description: courseId\n        required: true\n      - name: id\n        type: string\n \
  \       description: id\n        required: true\n      - name: updateMask\n        type: string\n        description: updateMask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecoursework\n      description: Google Classroom Delete course work\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-classroom.deletecoursework\n      with:\n        courseId: tools.courseId\n        id: tools.id\n      inputParameters:\n      - name: courseId\n        type: string\n        description: courseId\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liststudentsubmissions\n      description: Google Classroom List student submissions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-classroom.liststudentsubmissions\n\
  \      with:\n        courseId: tools.courseId\n        courseWorkId: tools.courseWorkId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: courseId\n        type: string\n        description: courseId\n        required: true\n      - name: courseWorkId\n        type: string\n        description: courseWorkId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liststudents\n      description: Google Classroom List students\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-classroom.liststudents\n      with:\n        courseId: tools.courseId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: courseId\n   \
  \     type: string\n        description: courseId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addstudent\n      description: Google Classroom Add student\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-classroom.addstudent\n      with:\n        courseId: tools.courseId\n      inputParameters:\n      - name: courseId\n        type: string\n        description: courseId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listteachers\n      description: Google Classroom List teachers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-classroom.listteachers\n      with:\n        courseId: tools.courseId\n\
  \        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: courseId\n        type: string\n        description: courseId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addteacher\n      description: Google Classroom Add teacher\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-classroom.addteacher\n      with:\n        courseId: tools.courseId\n      inputParameters:\n      - name: courseId\n        type: string\n        description: courseId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listannouncements\n      description: Google Classroom List announcements\n      hints:\n        readOnly: true\n     \
  \   destructive: false\n        idempotent: true\n      call: google-classroom.listannouncements\n      with:\n        courseId: tools.courseId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: courseId\n        type: string\n        description: courseId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createannouncement\n      description: Google Classroom Create announcement\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-classroom.createannouncement\n      with:\n        courseId: tools.courseId\n      inputParameters:\n      - name: courseId\n        type: string\n        description: courseId\n        required: true\n      outputParameters:\n     \
  \ - type: object\n        mapping: $.\n    - name: listtopics\n      description: Google Classroom List topics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-classroom.listtopics\n      with:\n        courseId: tools.courseId\n      inputParameters:\n      - name: courseId\n        type: string\n        description: courseId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtopic\n      description: Google Classroom Create topic\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-classroom.createtopic\n      with:\n        courseId: tools.courseId\n      inputParameters:\n      - name: courseId\n        type: string\n        description: courseId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinvitations\n      description: Google Classroom\
  \ List invitations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-classroom.listinvitations\n      with:\n        courseId: tools.courseId\n        userId: tools.userId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: courseId\n        type: string\n        description: courseId\n      - name: userId\n        type: string\n        description: userId\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createinvitation\n      description: Google Classroom Create invitation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-classroom.createinvitation\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: getuserprofile\n      description: Google Classroom Get user profile\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-classroom.getuserprofile\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-classroom/refs/heads/main/capabilities/google-classroom-capability.yaml
tags:
- Google
- Classroom
- API
tools:
- description: Google Classroom List courses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcourses
- description: Google Classroom Create course
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcourse
- description: Google Classroom Get course
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcourse
- description: Google Classroom Update course
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecourse
- description: Google Classroom Patch course
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchcourse
- description: Google Classroom Delete course
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecourse
- description: Google Classroom List course work
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcoursework
- description: Google Classroom Create course work
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcoursework
- description: Google Classroom Get course work
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcoursework
- description: Google Classroom Patch course work
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchcoursework
- description: Google Classroom Delete course work
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecoursework
- description: Google Classroom List student submissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststudentsubmissions
- description: Google Classroom List students
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststudents
- description: Google Classroom Add student
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addstudent
- description: Google Classroom List teachers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listteachers
- description: Google Classroom Add teacher
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addteacher
- description: Google Classroom List announcements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listannouncements
- description: Google Classroom Create announcement
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createannouncement
- description: Google Classroom List topics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtopics
- description: Google Classroom Create topic
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtopic
- description: Google Classroom List invitations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinvitations
- description: Google Classroom Create invitation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinvitation
- description: Google Classroom Get user profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserprofile
---
