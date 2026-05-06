---
categories: []
consumed_apis: []
description: API for the Paradox conversational AI recruiting platform powered by Olivia. Provides endpoints for managing candidates, users, interview scheduling, locations, company data, reporting, and candidate attributes. Paradox automates candidate screening, interview scheduling, and hiring workflows through chat, SMS, and mobile-driven experiences.
layout: capability
name: Paradox API
operations:
- description: Paradox Get OAuth 2.0 access token
  method: POST
  name: getauthtoken
  path: /auth/token
- description: Paradox Verify JWT token
  method: POST
  name: verifyjwt
  path: /verify-jwt
- description: Paradox Get candidates
  method: GET
  name: getcandidates
  path: /candidates
- description: Paradox Create candidate
  method: POST
  name: createcandidate
  path: /candidates
- description: Paradox Get single candidate
  method: GET
  name: getcandidate
  path: /candidates/{id}
- description: Paradox Update candidate
  method: PUT
  name: updatecandidate
  path: /candidates/{id}
- description: Paradox Delete candidate
  method: DELETE
  name: deletecandidate
  path: /candidates/{id}
- description: Paradox Unsubscribe candidate
  method: PUT
  name: unsubscribecandidate
  path: /candidates/unsubscribe
- description: Paradox Send candidate message
  method: POST
  name: sendcandidatemessage
  path: /candidates/send_message
- description: Paradox Send standard background check
  method: POST
  name: sendbackgroundcheckstandard
  path: /candidates/background_check/standard
- description: Paradox Send Checkr background check
  method: POST
  name: sendbackgroundcheckcheckr
  path: /candidates/background_check/checkr
- description: Paradox Send First Advantage background check
  method: POST
  name: sendbackgroundcheckfirstadvantage
  path: /candidates/background_check/firstadvance
- description: Paradox Get candidate attributes
  method: GET
  name: getcandidateattributes
  path: /candidate/attributes/{oid}
- description: Paradox Patch candidate attributes
  method: PATCH
  name: patchcandidateattributes
  path: /candidate/attributes
- description: Paradox Update candidate attributes
  method: PUT
  name: updatecandidateattributes
  path: /candidate/attributes
- description: Paradox Get users
  method: GET
  name: getusers
  path: /users
- description: Paradox Create user
  method: POST
  name: createuser
  path: /users
- description: Paradox Get single user
  method: GET
  name: getuser
  path: /users/{oid}
- description: Paradox Update user
  method: PUT
  name: updateuser
  path: /users/{oid}
- description: Paradox Delete user
  method: DELETE
  name: deleteuser
  path: /users/{oid}
- description: Paradox Deactivate user
  method: POST
  name: deactivateuser
  path: /users/{oid}/deactivate
- description: Paradox Reactivate user
  method: POST
  name: reactivateuser
  path: /users/{oid}/reactivate
- description: Paradox Get user roles
  method: GET
  name: getuserroles
  path: /users/roles
- description: Paradox Get user by employee ID
  method: GET
  name: getuserbyemployeeid
  path: /users/employees/{employee_id}
- description: Paradox Update user by employee ID
  method: PUT
  name: updateuserbyemployeeid
  path: /users/employees/{employee_id}
- description: Paradox Delete user by employee ID
  method: DELETE
  name: deleteuserbyemployeeid
  path: /users/employees/{employee_id}
- description: Paradox Get user location permissions
  method: GET
  name: getuserlocationpermissions
  path: /users/{oid}/permissions/locations
- description: Paradox Add user location permission
  method: PUT
  name: adduserlocationpermission
  path: /users/{oid}/permissions/locations
- description: Paradox Delete user location permission
  method: DELETE
  name: deleteuserlocationpermission
  path: /users/{oid}/permissions/locations
- description: Paradox Get multiparty interviewers
  method: GET
  name: getmultipartyinterviewers
  path: /scheduling/multiparty-interviewers
- description: Paradox Get interview settings
  method: GET
  name: getinterviewsettings
  path: /scheduling/interview-settings
- description: Paradox Get job location rooms
  method: GET
  name: getjoblocationrooms
  path: /scheduling/job-location-rooms
- description: Paradox Send interview alerts
  method: PUT
  name: sendinterviewalerts
  path: /scheduling/send-interview-alerts
- description: Paradox Get interview history
  method: GET
  name: getinterviewhistory
  path: /scheduling/interview-history
- description: Paradox Schedule shortlist review
  method: POST
  name: sendschedulingcommunication
  path: /scheduling/communication
- description: Paradox Get locations
  method: GET
  name: getlocations
  path: /company/locations
- description: Paradox Create location
  method: POST
  name: createlocation
  path: /location
- description: Paradox Get single location
  method: GET
  name: getlocation
  path: /location/{id}
- description: Paradox Update location
  method: PUT
  name: updatelocation
  path: /location/{id}
- description: Paradox Delete location
  method: DELETE
  name: deletelocation
  path: /location/{id}
- description: Paradox Get location by job location code
  method: GET
  name: getlocationbycode
  path: /location/code/{job_loc_code}
- description: Paradox Update location by job location code
  method: PUT
  name: updatelocationbycode
  path: /location/code/{job_loc_code}
- description: Paradox Get location areas
  method: GET
  name: getlocationareas
  path: /location/{location_id}/areas
- description: Paradox Create location area
  method: POST
  name: createlocationarea
  path: /location/{location_id}/areas
- description: Paradox Get single location area
  method: GET
  name: getlocationarea
  path: /location/{location_id}/areas/{area_id}
- description: Paradox Update location area
  method: PUT
  name: updatelocationarea
  path: /location/{location_id}/areas/{area_id}
- description: Paradox Delete location area
  method: DELETE
  name: deletelocationarea
  path: /location/{location_id}/areas/{area_id}
- description: Paradox Get location rooms
  method: GET
  name: getlocationrooms
  path: /location/{location_id}/rooms
- description: Paradox Create location room
  method: POST
  name: createlocationroom
  path: /location/{location_id}/rooms
- description: Paradox Get single location room
  method: GET
  name: getlocationroom
  path: /location/{location_id}/rooms/{room_id}
- description: Paradox Update location room
  method: PUT
  name: updatelocationroom
  path: /location/{location_id}/rooms/{room_id}
- description: Paradox Delete location room
  method: DELETE
  name: deletelocationroom
  path: /location/{location_id}/rooms/{room_id}
- description: Paradox Get company conversations
  method: GET
  name: getcompanyconversations
  path: /company/conversations
- description: Paradox Get company groups
  method: GET
  name: getcompanygroups
  path: /company/groups
- description: Paradox Get company schools and areas
  method: GET
  name: getcompanyschoolareas
  path: /company/school_areas
- description: Paradox Get AI assistant
  method: GET
  name: getcompanyaiassistant
  path: /company/ai
- description: Paradox Get report list
  method: GET
  name: getreports
  path: /reporting/reports
- description: Paradox Create report
  method: POST
  name: createreport
  path: /reporting/reports
- description: Paradox Get single report
  method: GET
  name: getreport
  path: /reporting/reports/{id}
personas: []
provider_name: Paradox
provider_slug: paradox
search_terms:
- paradox reactivate user
- paradox create candidate
- adduserlocationpermission
- updatelocationroom
- paradox add user location permission
- paradox deactivate user
- updatecandidate
- paradox get oauth 2.0 access token
- getcompanygroups
- paradox
- paradox send candidate message
- paradox patch candidate attributes
- paradox get location rooms
- updatecandidateattributes
- verifyjwt
- hiring automation
- paradox update location by job location code
- paradox get ai assistant
- api
- getinterviewsettings
- paradox get interview history
- getuser
- paradox get single user
- getlocationrooms
- getcompanyconversations
- paradox update candidate
- getcandidateattributes
- reactivateuser
- updateuser
- paradox get locations
- updatelocationarea
- conversational ai
- deleteuser
- createuser
- updatelocation
- paradox delete user
- paradox get candidates
- getlocationareas
- updatelocationbycode
- paradox get user by employee id
- updateuserbyemployeeid
- createlocationroom
- sms
- getusers
- createlocation
- getauthtoken
- paradox get company conversations
- paradox send interview alerts
- deletecandidate
- paradox send first advantage background check
- paradox get multiparty interviewers
- deletelocationarea
- paradox delete location area
- paradox create report
- paradox update location area
- paradox create location area
- sendschedulingcommunication
- paradox send checkr background check
- getlocations
- getlocationarea
- getreports
- deletelocation
- paradox get candidate attributes
- getlocationroom
- deleteuserlocationpermission
- getinterviewhistory
- paradox get company groups
- unsubscribecandidate
- getlocationbycode
- paradox verify jwt token
- getcandidates
- paradox update candidate attributes
- createlocationarea
- getmultipartyinterviewers
- paradox update user
- paradox delete location room
- paradox delete candidate
- sendbackgroundcheckstandard
- createreport
- getjoblocationrooms
- candidate screening
- getlocation
- artificial intelligence
- paradox create user
- deactivateuser
- paradox get interview settings
- getcandidate
- paradox get single location area
- hr technology
- paradox get report list
- paradox update location
- getcompanyaiassistant
- sendcandidatemessage
- paradox delete location
- getcompanyschoolareas
- getuserlocationpermissions
- getuserbyemployeeid
- getreport
- deleteuserbyemployeeid
- paradox unsubscribe candidate
- patchcandidateattributes
- paradox delete user by employee id
- recruiting
- paradox get single location room
- paradox create location room
- paradox get single candidate
- paradox get user location permissions
- paradox get location areas
- getuserroles
- interview scheduling
- sendbackgroundcheckcheckr
- deletelocationroom
- chatbot
- paradox get job location rooms
- sendinterviewalerts
- paradox get user roles
- paradox update user by employee id
- paradox get single location
- paradox update location room
- paradox get users
- paradox get single report
- createcandidate
- paradox send standard background check
- paradox get company schools and areas
- talent acquisition
- paradox create location
- paradox get location by job location code
- sendbackgroundcheckfirstadvantage
- paradox schedule shortlist review
- paradox delete user location permission
slug: paradox-capability
source_filename: paradox-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Paradox API\n  description: API for the Paradox conversational AI recruiting platform powered by Olivia. Provides endpoints for managing\n    candidates, users, interview scheduling, locations, company data, reporting, and candidate attributes. Paradox automates\n    candidate screening, interview scheduling, and hiring workflows through chat, SMS, and mobile-driven experiences.\n  tags:\n  - Paradox\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: paradox\n    baseUri: https://api.paradox.ai/api/v1/public\n    description: Paradox API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PARADOX_TOKEN}}'\n    resources:\n    - name: auth-token\n      path: /auth/token\n      operations:\n      - name: getauthtoken\n        method: POST\n        description: Paradox Get OAuth 2.0 access token\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: verify-jwt\n      path: /verify-jwt\n      operations:\n      - name: verifyjwt\n        method: POST\n        description: Paradox Verify JWT token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidates\n      path: /candidates\n      operations:\n      - name: getcandidates\n        method: GET\n        description: Paradox Get candidates\n        inputParameters:\n        - name: start_date\n          in: query\n          type: string\n          description: Filter candidates created after this date (ISO 8601)\n        - name: end_date\n          in: query\n          type: string\n          description: Filter candidates created before this date (ISO 8601)\n        - name: created_start_date\n          in: query\n          type: string\n          description: Filter by candidate creation start date\n        -\
  \ name: start_keyword\n          in: query\n          type: string\n          description: Search keyword filter\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of results to return (max 50)\n        - name: offset\n          in: query\n          type: integer\n          description: Number of results to skip for pagination\n        - name: page\n          in: query\n          type: integer\n          description: Page number for pagination\n        - name: status\n          in: query\n          type: string\n          description: Filter by candidate status\n        - name: group_name\n          in: query\n          type: string\n          description: Filter by group name\n        - name: location_id\n          in: query\n          type: string\n          description: Filter by location identifier\n        - name: source\n          in: query\n          type: string\n          description: Filter by candidate source\n       \
  \ - name: conversation\n          in: query\n          type: boolean\n          description: Include conversation data\n        - name: interviews\n          in: query\n          type: boolean\n          description: Include interview data\n        - name: note\n          in: query\n          type: boolean\n          description: Include candidate notes\n        - name: profile_id\n          in: query\n          type: string\n          description: Filter by profile identifier\n        - name: include_attributes\n          in: query\n          type: boolean\n          description: Include candidate attribute data in response\n        - name: candidate_journey_status\n          in: query\n          type: string\n          description: Filter by candidate journey status\n        - name: job_loc_code\n          in: query\n          type: string\n          description: Filter by job location code\n        - name: job_req_id\n          in: query\n          type: string\n          description:\
  \ Filter by job requisition ID\n        - name: ex_id\n          in: query\n          type: string\n          description: Filter by external candidate identifier\n        - name: email\n          in: query\n          type: string\n          description: Filter by candidate email\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcandidate\n        method: POST\n        description: Paradox Create candidate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidates-id\n      path: /candidates/{id}\n      operations:\n      - name: getcandidate\n        method: GET\n        description: Paradox Get single candidate\n        inputParameters:\n        - name: conversation\n          in: query\n          type: boolean\n          description: Include conversation history\n        - name: note\n          in:\
  \ query\n          type: boolean\n          description: Include candidate notes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecandidate\n        method: PUT\n        description: Paradox Update candidate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecandidate\n        method: DELETE\n        description: Paradox Delete candidate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidates-unsubscribe\n      path: /candidates/unsubscribe\n      operations:\n      - name: unsubscribecandidate\n        method: PUT\n        description: Paradox Unsubscribe candidate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ candidates-send-message\n      path: /candidates/send_message\n      operations:\n      - name: sendcandidatemessage\n        method: POST\n        description: Paradox Send candidate message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidates-background-check-standard\n      path: /candidates/background_check/standard\n      operations:\n      - name: sendbackgroundcheckstandard\n        method: POST\n        description: Paradox Send standard background check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidates-background-check-checkr\n      path: /candidates/background_check/checkr\n      operations:\n      - name: sendbackgroundcheckcheckr\n        method: POST\n        description: Paradox Send Checkr background check\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: candidates-background-check-firstadvance\n      path: /candidates/background_check/firstadvance\n      operations:\n      - name: sendbackgroundcheckfirstadvantage\n        method: POST\n        description: Paradox Send First Advantage background check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-attributes-oid\n      path: /candidate/attributes/{oid}\n      operations:\n      - name: getcandidateattributes\n        method: GET\n        description: Paradox Get candidate attributes\n        inputParameters:\n        - name: oid\n          in: path\n          type: string\n          required: true\n          description: Candidate OID or external OID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-attributes\n\
  \      path: /candidate/attributes\n      operations:\n      - name: patchcandidateattributes\n        method: PATCH\n        description: Paradox Patch candidate attributes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecandidateattributes\n        method: PUT\n        description: Paradox Update candidate attributes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: getusers\n        method: GET\n        description: Paradox Get users\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of results to return\n        - name: page\n          in: query\n          type: integer\n          description: Page number for pagination\n        - name: include_campus_permission\n\
  \          in: query\n          type: boolean\n          description: Include campus permission data in response\n        - name: external_role_id\n          in: query\n          type: string\n          description: Filter by external role identifier\n        - name: location_id\n          in: query\n          type: string\n          description: Filter by location identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: Paradox Create user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-oid\n      path: /users/{oid}\n      operations:\n      - name: getuser\n        method: GET\n        description: Paradox Get single user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: updateuser\n        method: PUT\n        description: Paradox Update user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Paradox Delete user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-oid-deactivate\n      path: /users/{oid}/deactivate\n      operations:\n      - name: deactivateuser\n        method: POST\n        description: Paradox Deactivate user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-oid-reactivate\n      path: /users/{oid}/reactivate\n      operations:\n      - name: reactivateuser\n        method: POST\n        description: Paradox Reactivate user\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: users-roles\n      path: /users/roles\n      operations:\n      - name: getuserroles\n        method: GET\n        description: Paradox Get user roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-employees-employee-id\n      path: /users/employees/{employee_id}\n      operations:\n      - name: getuserbyemployeeid\n        method: GET\n        description: Paradox Get user by employee ID\n        inputParameters:\n        - name: employee_id\n          in: path\n          type: string\n          required: true\n          description: Employee identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuserbyemployeeid\n        method: PUT\n        description: Paradox Update user by employee ID\n        inputParameters:\n\
  \        - name: employee_id\n          in: path\n          type: string\n          required: true\n          description: Employee identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuserbyemployeeid\n        method: DELETE\n        description: Paradox Delete user by employee ID\n        inputParameters:\n        - name: employee_id\n          in: path\n          type: string\n          required: true\n          description: Employee identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-oid-permissions-locations\n      path: /users/{oid}/permissions/locations\n      operations:\n      - name: getuserlocationpermissions\n        method: GET\n        description: Paradox Get user location permissions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: adduserlocationpermission\n        method: PUT\n        description: Paradox Add user location permission\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuserlocationpermission\n        method: DELETE\n        description: Paradox Delete user location permission\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduling-multiparty-interviewers\n      path: /scheduling/multiparty-interviewers\n      operations:\n      - name: getmultipartyinterviewers\n        method: GET\n        description: Paradox Get multiparty interviewers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduling-interview-settings\n      path: /scheduling/interview-settings\n\
  \      operations:\n      - name: getinterviewsettings\n        method: GET\n        description: Paradox Get interview settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduling-job-location-rooms\n      path: /scheduling/job-location-rooms\n      operations:\n      - name: getjoblocationrooms\n        method: GET\n        description: Paradox Get job location rooms\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduling-send-interview-alerts\n      path: /scheduling/send-interview-alerts\n      operations:\n      - name: sendinterviewalerts\n        method: PUT\n        description: Paradox Send interview alerts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduling-interview-history\n      path:\
  \ /scheduling/interview-history\n      operations:\n      - name: getinterviewhistory\n        method: GET\n        description: Paradox Get interview history\n        inputParameters:\n        - name: candidate_id\n          in: query\n          type: string\n          description: Filter by candidate identifier\n        - name: start_date\n          in: query\n          type: string\n          description: Filter by start date\n        - name: end_date\n          in: query\n          type: string\n          description: Filter by end date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduling-communication\n      path: /scheduling/communication\n      operations:\n      - name: sendschedulingcommunication\n        method: POST\n        description: Paradox Schedule shortlist review\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n    - name: company-locations\n      path: /company/locations\n      operations:\n      - name: getlocations\n        method: GET\n        description: Paradox Get locations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: location\n      path: /location\n      operations:\n      - name: createlocation\n        method: POST\n        description: Paradox Create location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: location-id\n      path: /location/{id}\n      operations:\n      - name: getlocation\n        method: GET\n        description: Paradox Get single location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelocation\n        method: PUT\n        description: Paradox Update location\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelocation\n        method: DELETE\n        description: Paradox Delete location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: location-code-job-loc-code\n      path: /location/code/{job_loc_code}\n      operations:\n      - name: getlocationbycode\n        method: GET\n        description: Paradox Get location by job location code\n        inputParameters:\n        - name: job_loc_code\n          in: path\n          type: string\n          required: true\n          description: Job location code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelocationbycode\n        method: PUT\n        description: Paradox Update location by job location code\n     \
  \   inputParameters:\n        - name: job_loc_code\n          in: path\n          type: string\n          required: true\n          description: Job location code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: location-location-id-areas\n      path: /location/{location_id}/areas\n      operations:\n      - name: getlocationareas\n        method: GET\n        description: Paradox Get location areas\n        inputParameters:\n        - name: location_id\n          in: path\n          type: string\n          required: true\n          description: Location identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlocationarea\n        method: POST\n        description: Paradox Create location area\n        inputParameters:\n        - name: location_id\n          in: path\n          type: string\n  \
  \        required: true\n          description: Location identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: location-location-id-areas-area-id\n      path: /location/{location_id}/areas/{area_id}\n      operations:\n      - name: getlocationarea\n        method: GET\n        description: Paradox Get single location area\n        inputParameters:\n        - name: location_id\n          in: path\n          type: string\n          required: true\n          description: Location identifier\n        - name: area_id\n          in: path\n          type: string\n          required: true\n          description: Area identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelocationarea\n        method: PUT\n        description: Paradox Update location area\n        inputParameters:\n        - name:\
  \ location_id\n          in: path\n          type: string\n          required: true\n          description: Location identifier\n        - name: area_id\n          in: path\n          type: string\n          required: true\n          description: Area identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelocationarea\n        method: DELETE\n        description: Paradox Delete location area\n        inputParameters:\n        - name: location_id\n          in: path\n          type: string\n          required: true\n          description: Location identifier\n        - name: area_id\n          in: path\n          type: string\n          required: true\n          description: Area identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: location-location-id-rooms\n      path: /location/{location_id}/rooms\n\
  \      operations:\n      - name: getlocationrooms\n        method: GET\n        description: Paradox Get location rooms\n        inputParameters:\n        - name: location_id\n          in: path\n          type: string\n          required: true\n          description: Location identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlocationroom\n        method: POST\n        description: Paradox Create location room\n        inputParameters:\n        - name: location_id\n          in: path\n          type: string\n          required: true\n          description: Location identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: location-location-id-rooms-room-id\n      path: /location/{location_id}/rooms/{room_id}\n      operations:\n      - name: getlocationroom\n        method: GET\n      \
  \  description: Paradox Get single location room\n        inputParameters:\n        - name: location_id\n          in: path\n          type: string\n          required: true\n          description: Location identifier\n        - name: room_id\n          in: path\n          type: string\n          required: true\n          description: Room identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelocationroom\n        method: PUT\n        description: Paradox Update location room\n        inputParameters:\n        - name: location_id\n          in: path\n          type: string\n          required: true\n          description: Location identifier\n        - name: room_id\n          in: path\n          type: string\n          required: true\n          description: Room identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: deletelocationroom\n        method: DELETE\n        description: Paradox Delete location room\n        inputParameters:\n        - name: location_id\n          in: path\n          type: string\n          required: true\n          description: Location identifier\n        - name: room_id\n          in: path\n          type: string\n          required: true\n          description: Room identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: company-conversations\n      path: /company/conversations\n      operations:\n      - name: getcompanyconversations\n        method: GET\n        description: Paradox Get company conversations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: company-groups\n      path: /company/groups\n      operations:\n      - name: getcompanygroups\n\
  \        method: GET\n        description: Paradox Get company groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: company-school-areas\n      path: /company/school_areas\n      operations:\n      - name: getcompanyschoolareas\n        method: GET\n        description: Paradox Get company schools and areas\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: company-ai\n      path: /company/ai\n      operations:\n      - name: getcompanyaiassistant\n        method: GET\n        description: Paradox Get AI assistant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reporting-reports\n      path: /reporting/reports\n      operations:\n      - name: getreports\n        method: GET\n        description: Paradox Get report\
  \ list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createreport\n        method: POST\n        description: Paradox Create report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reporting-reports-id\n      path: /reporting/reports/{id}\n      operations:\n      - name: getreport\n        method: GET\n        description: Paradox Get single report\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Report identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: paradox-rest\n    description: REST adapter for Paradox API.\n    resources:\n    - path: /auth/token\n      name: getauthtoken\n\
  \      operations:\n      - method: POST\n        name: getauthtoken\n        description: Paradox Get OAuth 2.0 access token\n        call: paradox.getauthtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /verify-jwt\n      name: verifyjwt\n      operations:\n      - method: POST\n        name: verifyjwt\n        description: Paradox Verify JWT token\n        call: paradox.verifyjwt\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates\n      name: getcandidates\n      operations:\n      - method: GET\n        name: getcandidates\n        description: Paradox Get candidates\n        call: paradox.getcandidates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates\n      name: createcandidate\n      operations:\n      - method: POST\n        name: createcandidate\n        description: Paradox Create candidate\n        call: paradox.createcandidate\n     \
  \   outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates/{id}\n      name: getcandidate\n      operations:\n      - method: GET\n        name: getcandidate\n        description: Paradox Get single candidate\n        call: paradox.getcandidate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates/{id}\n      name: updatecandidate\n      operations:\n      - method: PUT\n        name: updatecandidate\n        description: Paradox Update candidate\n        call: paradox.updatecandidate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates/{id}\n      name: deletecandidate\n      operations:\n      - method: DELETE\n        name: deletecandidate\n        description: Paradox Delete candidate\n        call: paradox.deletecandidate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates/unsubscribe\n      name: unsubscribecandidate\n\
  \      operations:\n      - method: PUT\n        name: unsubscribecandidate\n        description: Paradox Unsubscribe candidate\n        call: paradox.unsubscribecandidate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates/send_message\n      name: sendcandidatemessage\n      operations:\n      - method: POST\n        name: sendcandidatemessage\n        description: Paradox Send candidate message\n        call: paradox.sendcandidatemessage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates/background_check/standard\n      name: sendbackgroundcheckstandard\n      operations:\n      - method: POST\n        name: sendbackgroundcheckstandard\n        description: Paradox Send standard background check\n        call: paradox.sendbackgroundcheckstandard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates/background_check/checkr\n      name: sendbackgroundcheckcheckr\n\
  \      operations:\n      - method: POST\n        name: sendbackgroundcheckcheckr\n        description: Paradox Send Checkr background check\n        call: paradox.sendbackgroundcheckcheckr\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates/background_check/firstadvance\n      name: sendbackgroundcheckfirstadvantage\n      operations:\n      - method: POST\n        name: sendbackgroundcheckfirstadvantage\n        description: Paradox Send First Advantage background check\n        call: paradox.sendbackgroundcheckfirstadvantage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidate/attributes/{oid}\n      name: getcandidateattributes\n      operations:\n      - method: GET\n        name: getcandidateattributes\n        description: Paradox Get candidate attributes\n        call: paradox.getcandidateattributes\n        with:\n          oid: rest.oid\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /candidate/attributes\n      name: patchcandidateattributes\n      operations:\n      - method: PATCH\n        name: patchcandidateattributes\n        description: Paradox Patch candidate attributes\n        call: paradox.patchcandidateattributes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidate/attributes\n      name: updatecandidateattributes\n      operations:\n      - method: PUT\n        name: updatecandidateattributes\n        description: Paradox Update candidate attributes\n        call: paradox.updatecandidateattributes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: getusers\n      operations:\n      - method: GET\n        name: getusers\n        description: Paradox Get users\n        call: paradox.getusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: createuser\n      operations:\n\
  \      - method: POST\n        name: createuser\n        description: Paradox Create user\n        call: paradox.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{oid}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Paradox Get single user\n        call: paradox.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{oid}\n      name: updateuser\n      operations:\n      - method: PUT\n        name: updateuser\n        description: Paradox Update user\n        call: paradox.updateuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{oid}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: Paradox Delete user\n        call: paradox.deleteuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /users/{oid}/deactivate\n      name: deactivateuser\n      operations:\n      - method: POST\n        name: deactivateuser\n        description: Paradox Deactivate user\n        call: paradox.deactivateuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{oid}/reactivate\n      name: reactivateuser\n      operations:\n      - method: POST\n        name: reactivateuser\n        description: Paradox Reactivate user\n        call: paradox.reactivateuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/roles\n      name: getuserroles\n      operations:\n      - method: GET\n        name: getuserroles\n        description: Paradox Get user roles\n        call: paradox.getuserroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/employees/{employee_id}\n      name: getuserbyemployeeid\n      operations:\n      - method: GET\n        name: getuserbyemployeeid\n\
  \        description: Paradox Get user by employee ID\n        call: paradox.getuserbyemployeeid\n        with:\n          employee_id: rest.employee_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/employees/{employee_id}\n      name: updateuserbyemployeeid\n      operations:\n      - method: PUT\n        name: updateuserbyemployeeid\n        description: Paradox Update user by employee ID\n        call: paradox.updateuserbyemployeeid\n        with:\n          employee_id: rest.employee_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/employees/{employee_id}\n      name: deleteuserbyemployeeid\n      operations:\n      - method: DELETE\n        name: deleteuserbyemployeeid\n        description: Paradox Delete user by employee ID\n\n\n# --- truncated at 32 KB (66 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/paradox/refs/heads/main/capabilities/paradox-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/paradox/refs/heads/main/capabilities/paradox-capability.yaml
tags:
- Paradox
- API
tools:
- description: Paradox Get OAuth 2.0 access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getauthtoken
- description: Paradox Verify JWT token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: verifyjwt
- description: Paradox Get candidates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcandidates
- description: Paradox Create candidate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcandidate
- description: Paradox Get single candidate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcandidate
- description: Paradox Update candidate
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecandidate
- description: Paradox Delete candidate
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecandidate
- description: Paradox Unsubscribe candidate
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: unsubscribecandidate
- description: Paradox Send candidate message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendcandidatemessage
- description: Paradox Send standard background check
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendbackgroundcheckstandard
- description: Paradox Send Checkr background check
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendbackgroundcheckcheckr
- description: Paradox Send First Advantage background check
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendbackgroundcheckfirstadvantage
- description: Paradox Get candidate attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcandidateattributes
- description: Paradox Patch candidate attributes
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchcandidateattributes
- description: Paradox Update candidate attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecandidateattributes
- description: Paradox Get users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getusers
- description: Paradox Create user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Paradox Get single user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Paradox Update user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateuser
- description: Paradox Delete user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: Paradox Deactivate user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deactivateuser
- description: Paradox Reactivate user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: reactivateuser
- description: Paradox Get user roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserroles
- description: Paradox Get user by employee ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserbyemployeeid
- description: Paradox Update user by employee ID
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateuserbyemployeeid
- description: Paradox Delete user by employee ID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuserbyemployeeid
- description: Paradox Get user location permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserlocationpermissions
- description: Paradox Add user location permission
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: adduserlocationpermission
- description: Paradox Delete user location permission
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuserlocationpermission
- description: Paradox Get multiparty interviewers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmultipartyinterviewers
- description: Paradox Get interview settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinterviewsettings
- description: Paradox Get job location rooms
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjoblocationrooms
- description: Paradox Send interview alerts
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: sendinterviewalerts
- description: Paradox Get interview history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinterviewhistory
- description: Paradox Schedule shortlist review
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendschedulingcommunication
- description: Paradox Get locations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocations
- description: Paradox Create location
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlocation
- description: Paradox Get single location
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocation
- description: Paradox Update location
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatelocation
- description: Paradox Delete location
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelocation
- description: Paradox Get location by job location code
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocationbycode
- description: Paradox Update location by job location code
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatelocationbycode
- description: Paradox Get location areas
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocationareas
- description: Paradox Create location area
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlocationarea
- description: Paradox Get single location area
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocationarea
- description: Paradox Update location area
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatelocationarea
- description: Paradox Delete location area
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelocationarea
- description: Paradox Get location rooms
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocationrooms
- description: Paradox Create location room
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlocationroom
- description: Paradox Get single location room
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocationroom
- description: Paradox Update location room
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatelocationroom
- description: Paradox Delete location room
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelocationroom
- description: Paradox Get company conversations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompanyconversations
- description: Paradox Get company groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompanygroups
- description: Paradox Get company schools and areas
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompanyschoolareas
- description: Paradox Get AI assistant
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompanyaiassistant
- description: Paradox Get report list
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreports
- description: Paradox Create report
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createreport
- description: Paradox Get single report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreport
---
