---
categories: []
consumed_apis: []
description: API for managing Oracle Database services in Oracle Cloud Infrastructure (OCI). Provides management of DB Systems, Autonomous Databases, Exadata infrastructure, database backups, Data Guard associations, database homes, and related cloud database resources.
layout: capability
name: Oracle Database Oracle Cloud Infrastructure Database API
operations:
- description: Oracle Database List Autonomous Databases
  method: GET
  name: listautonomousdatabases
  path: /autonomousDatabases
- description: Oracle Database Create an Autonomous Database
  method: POST
  name: createautonomousdatabase
  path: /autonomousDatabases
- description: Oracle Database Get an Autonomous Database
  method: GET
  name: getautonomousdatabase
  path: /autonomousDatabases/{autonomousDatabaseId}
- description: Oracle Database Update an Autonomous Database
  method: PUT
  name: updateautonomousdatabase
  path: /autonomousDatabases/{autonomousDatabaseId}
- description: Oracle Database Delete an Autonomous Database
  method: DELETE
  name: deleteautonomousdatabase
  path: /autonomousDatabases/{autonomousDatabaseId}
- description: Oracle Database Start an Autonomous Database
  method: POST
  name: startautonomousdatabase
  path: /autonomousDatabases/{autonomousDatabaseId}/actions/start
- description: Oracle Database Stop an Autonomous Database
  method: POST
  name: stopautonomousdatabase
  path: /autonomousDatabases/{autonomousDatabaseId}/actions/stop
- description: Oracle Database Restart an Autonomous Database
  method: POST
  name: restartautonomousdatabase
  path: /autonomousDatabases/{autonomousDatabaseId}/actions/restart
- description: Oracle Database Generate database wallet
  method: POST
  name: generateautonomousdatabasewallet
  path: /autonomousDatabases/{autonomousDatabaseId}/actions/generateWallet
- description: Oracle Database List Autonomous Database backups
  method: GET
  name: listautonomousdatabasebackups
  path: /autonomousDatabaseBackups
- description: Oracle Database Create an Autonomous Database backup
  method: POST
  name: createautonomousdatabasebackup
  path: /autonomousDatabaseBackups
- description: Oracle Database List DB Systems
  method: GET
  name: listdbsystems
  path: /dbSystems
- description: Oracle Database Launch a DB System
  method: POST
  name: launchdbsystem
  path: /dbSystems
- description: Oracle Database Get a DB System
  method: GET
  name: getdbsystem
  path: /dbSystems/{dbSystemId}
- description: Oracle Database Update a DB System
  method: PUT
  name: updatedbsystem
  path: /dbSystems/{dbSystemId}
- description: Oracle Database Terminate a DB System
  method: DELETE
  name: terminatedbsystem
  path: /dbSystems/{dbSystemId}
- description: Oracle Database List databases
  method: GET
  name: listdatabases
  path: /databases
- description: Oracle Database Create a database
  method: POST
  name: createdatabase
  path: /databases
- description: Oracle Database Get a database
  method: GET
  name: getdatabase
  path: /databases/{databaseId}
- description: Oracle Database Update a database
  method: PUT
  name: updatedatabase
  path: /databases/{databaseId}
- description: Oracle Database Delete a database
  method: DELETE
  name: deletedatabase
  path: /databases/{databaseId}
- description: Oracle Database List Database Homes
  method: GET
  name: listdbhomes
  path: /dbHomes
- description: Oracle Database Create a Database Home
  method: POST
  name: createdbhome
  path: /dbHomes
- description: Oracle Database Get a Database Home
  method: GET
  name: getdbhome
  path: /dbHomes/{dbHomeId}
- description: Oracle Database Delete a Database Home
  method: DELETE
  name: deletedbhome
  path: /dbHomes/{dbHomeId}
- description: Oracle Database List database backups
  method: GET
  name: listbackups
  path: /backups
- description: Oracle Database Create a database backup
  method: POST
  name: createbackup
  path: /backups
- description: Oracle Database Get a database backup
  method: GET
  name: getbackup
  path: /backups/{backupId}
- description: Oracle Database Delete a database backup
  method: DELETE
  name: deletebackup
  path: /backups/{backupId}
- description: Oracle Database List Data Guard associations
  method: GET
  name: listdataguardassociations
  path: /dataGuardAssociations
- description: Oracle Database List pluggable databases
  method: GET
  name: listpluggabledatabases
  path: /pluggableDatabases
- description: Oracle Database Create a pluggable database
  method: POST
  name: createpluggabledatabase
  path: /pluggableDatabases
- description: Oracle Database Get a pluggable database
  method: GET
  name: getpluggabledatabase
  path: /pluggableDatabases/{pluggableDatabaseId}
- description: Oracle Database Update a pluggable database
  method: PUT
  name: updatepluggabledatabase
  path: /pluggableDatabases/{pluggableDatabaseId}
- description: Oracle Database Delete a pluggable database
  method: DELETE
  name: deletepluggabledatabase
  path: /pluggableDatabases/{pluggableDatabaseId}
personas: []
provider_name: Oracle Database
provider_slug: oracle-database
search_terms:
- deleteautonomousdatabase
- api
- getbackup
- oracle database delete a pluggable database
- listpluggabledatabases
- oracle database get a database home
- oracle database create a database
- deletepluggabledatabase
- getdbsystem
- listdataguardassociations
- oracle database list data guard associations
- launchdbsystem
- sql
- getautonomousdatabase
- oracle database stop an autonomous database
- getdbhome
- getpluggabledatabase
- oracle database list databases
- oracle database create an autonomous database backup
- oracle database list db systems
- updatepluggabledatabase
- oracle database create an autonomous database
- updateautonomousdatabase
- updatedatabase
- oracle database delete a database home
- startautonomousdatabase
- oracle database list pluggable databases
- createautonomousdatabasebackup
- oracle database generate database wallet
- oracle database terminate a db system
- oracle database delete a database backup
- oracle database list autonomous databases
- enterprise
- listdbsystems
- oracle database start an autonomous database
- cloud
- oracle database get a pluggable database
- oracle database create a database backup
- rest api
- oracle database get a db system
- getdatabase
- createpluggabledatabase
- oracle database launch a db system
- restartautonomousdatabase
- oracle database list database homes
- oracle database create a database home
- terminatedbsystem
- listbackups
- oracle database create a pluggable database
- oracle database delete a database
- oracle database list autonomous database backups
- generateautonomousdatabasewallet
- database
- updatedbsystem
- listdatabases
- oracle database update a database
- listautonomousdatabases
- oracle database get an autonomous database
- oracle database update a pluggable database
- oracle database get a database
- oracle database get a database backup
- createdbhome
- oracle
- oracle database restart an autonomous database
- oracle database delete an autonomous database
- listautonomousdatabasebackups
- createdatabase
- oracle database list database backups
- deletedatabase
- createbackup
- stopautonomousdatabase
- oracle database update a db system
- listdbhomes
- createautonomousdatabase
- oracle database update an autonomous database
- deletedbhome
- deletebackup
slug: oracle-database-capability
source_filename: oracle-database-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle Database Oracle Cloud Infrastructure Database API\n  description: API for managing Oracle Database services in Oracle Cloud Infrastructure (OCI). Provides management of DB Systems,\n    Autonomous Databases, Exadata infrastructure, database backups, Data Guard associations, database homes, and related cloud\n    database resources.\n  tags:\n  - Oracle\n  - Database\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: oracle-database\n    baseUri: https://database.us-ashburn-1.oraclecloud.com/20160918\n    description: Oracle Database Oracle Cloud Infrastructure Database API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ORACLE_DATABASE_TOKEN}}'\n    resources:\n    - name: autonomousdatabases\n      path: /autonomousDatabases\n      operations:\n      - name: listautonomousdatabases\n        method: GET\n        description: Oracle Database List\
  \ Autonomous Databases\n        inputParameters:\n        - name: displayName\n          in: query\n          type: string\n          description: Filter by display name\n        - name: lifecycleState\n          in: query\n          type: string\n          description: Filter by lifecycle state\n        - name: dbWorkload\n          in: query\n          type: string\n          description: Filter by workload type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createautonomousdatabase\n        method: POST\n        description: Oracle Database Create an Autonomous Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: autonomousdatabases-autonomousdatabaseid\n      path: /autonomousDatabases/{autonomousDatabaseId}\n      operations:\n      - name: getautonomousdatabase\n        method: GET\n        description:\
  \ Oracle Database Get an Autonomous Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateautonomousdatabase\n        method: PUT\n        description: Oracle Database Update an Autonomous Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteautonomousdatabase\n        method: DELETE\n        description: Oracle Database Delete an Autonomous Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: autonomousdatabases-autonomousdatabaseid-actions\n      path: /autonomousDatabases/{autonomousDatabaseId}/actions/start\n      operations:\n      - name: startautonomousdatabase\n        method: POST\n        description: Oracle Database Start an Autonomous Database\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: autonomousdatabases-autonomousdatabaseid-actions\n      path: /autonomousDatabases/{autonomousDatabaseId}/actions/stop\n      operations:\n      - name: stopautonomousdatabase\n        method: POST\n        description: Oracle Database Stop an Autonomous Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: autonomousdatabases-autonomousdatabaseid-actions\n      path: /autonomousDatabases/{autonomousDatabaseId}/actions/restart\n      operations:\n      - name: restartautonomousdatabase\n        method: POST\n        description: Oracle Database Restart an Autonomous Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: autonomousdatabases-autonomousdatabaseid-actions\n      path: /autonomousDatabases/{autonomousDatabaseId}/actions/generateWallet\n\
  \      operations:\n      - name: generateautonomousdatabasewallet\n        method: POST\n        description: Oracle Database Generate database wallet\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: autonomousdatabasebackups\n      path: /autonomousDatabaseBackups\n      operations:\n      - name: listautonomousdatabasebackups\n        method: GET\n        description: Oracle Database List Autonomous Database backups\n        inputParameters:\n        - name: autonomousDatabaseId\n          in: query\n          type: string\n          description: The Autonomous Database OCID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createautonomousdatabasebackup\n        method: POST\n        description: Oracle Database Create an Autonomous Database backup\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: dbsystems\n      path: /dbSystems\n      operations:\n      - name: listdbsystems\n        method: GET\n        description: Oracle Database List DB Systems\n        inputParameters:\n        - name: displayName\n          in: query\n          type: string\n        - name: lifecycleState\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: launchdbsystem\n        method: POST\n        description: Oracle Database Launch a DB System\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbsystems-dbsystemid\n      path: /dbSystems/{dbSystemId}\n      operations:\n      - name: getdbsystem\n        method: GET\n        description: Oracle Database Get a DB System\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedbsystem\n        method: PUT\n        description: Oracle Database Update a DB System\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: terminatedbsystem\n        method: DELETE\n        description: Oracle Database Terminate a DB System\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: databases\n      path: /databases\n      operations:\n      - name: listdatabases\n        method: GET\n        description: Oracle Database List databases\n        inputParameters:\n        - name: dbHomeId\n          in: query\n          type: string\n        - name: systemId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n      - name: createdatabase\n        method: POST\n        description: Oracle Database Create a database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: databases-databaseid\n      path: /databases/{databaseId}\n      operations:\n      - name: getdatabase\n        method: GET\n        description: Oracle Database Get a database\n        inputParameters:\n        - name: databaseId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedatabase\n        method: PUT\n        description: Oracle Database Update a database\n        inputParameters:\n        - name: databaseId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deletedatabase\n        method: DELETE\n        description: Oracle Database Delete a database\n        inputParameters:\n        - name: databaseId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbhomes\n      path: /dbHomes\n      operations:\n      - name: listdbhomes\n        method: GET\n        description: Oracle Database List Database Homes\n        inputParameters:\n        - name: dbSystemId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdbhome\n        method: POST\n        description: Oracle Database Create a Database Home\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: dbhomes-dbhomeid\n      path: /dbHomes/{dbHomeId}\n      operations:\n      - name: getdbhome\n        method: GET\n        description: Oracle Database Get a Database Home\n        inputParameters:\n        - name: dbHomeId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedbhome\n        method: DELETE\n        description: Oracle Database Delete a Database Home\n        inputParameters:\n        - name: dbHomeId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: backups\n      path: /backups\n      operations:\n      - name: listbackups\n        method: GET\n        description: Oracle\
  \ Database List database backups\n        inputParameters:\n        - name: databaseId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbackup\n        method: POST\n        description: Oracle Database Create a database backup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: backups-backupid\n      path: /backups/{backupId}\n      operations:\n      - name: getbackup\n        method: GET\n        description: Oracle Database Get a database backup\n        inputParameters:\n        - name: backupId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebackup\n        method: DELETE\n        description:\
  \ Oracle Database Delete a database backup\n        inputParameters:\n        - name: backupId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dataguardassociations\n      path: /dataGuardAssociations\n      operations:\n      - name: listdataguardassociations\n        method: GET\n        description: Oracle Database List Data Guard associations\n        inputParameters:\n        - name: databaseId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pluggabledatabases\n      path: /pluggableDatabases\n      operations:\n      - name: listpluggabledatabases\n        method: GET\n        description: Oracle Database List pluggable databases\n        inputParameters:\n   \
  \     - name: databaseId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpluggabledatabase\n        method: POST\n        description: Oracle Database Create a pluggable database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pluggabledatabases-pluggabledatabaseid\n      path: /pluggableDatabases/{pluggableDatabaseId}\n      operations:\n      - name: getpluggabledatabase\n        method: GET\n        description: Oracle Database Get a pluggable database\n        inputParameters:\n        - name: pluggableDatabaseId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepluggabledatabase\n  \
  \      method: PUT\n        description: Oracle Database Update a pluggable database\n        inputParameters:\n        - name: pluggableDatabaseId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepluggabledatabase\n        method: DELETE\n        description: Oracle Database Delete a pluggable database\n        inputParameters:\n        - name: pluggableDatabaseId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oracle-database-rest\n    description: REST adapter for Oracle Database Oracle Cloud Infrastructure Database API.\n    resources:\n    - path: /autonomousDatabases\n      name: listautonomousdatabases\n   \
  \   operations:\n      - method: GET\n        name: listautonomousdatabases\n        description: Oracle Database List Autonomous Databases\n        call: oracle-database.listautonomousdatabases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /autonomousDatabases\n      name: createautonomousdatabase\n      operations:\n      - method: POST\n        name: createautonomousdatabase\n        description: Oracle Database Create an Autonomous Database\n        call: oracle-database.createautonomousdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /autonomousDatabases/{autonomousDatabaseId}\n      name: getautonomousdatabase\n      operations:\n      - method: GET\n        name: getautonomousdatabase\n        description: Oracle Database Get an Autonomous Database\n        call: oracle-database.getautonomousdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /autonomousDatabases/{autonomousDatabaseId}\n\
  \      name: updateautonomousdatabase\n      operations:\n      - method: PUT\n        name: updateautonomousdatabase\n        description: Oracle Database Update an Autonomous Database\n        call: oracle-database.updateautonomousdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /autonomousDatabases/{autonomousDatabaseId}\n      name: deleteautonomousdatabase\n      operations:\n      - method: DELETE\n        name: deleteautonomousdatabase\n        description: Oracle Database Delete an Autonomous Database\n        call: oracle-database.deleteautonomousdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /autonomousDatabases/{autonomousDatabaseId}/actions/start\n      name: startautonomousdatabase\n      operations:\n      - method: POST\n        name: startautonomousdatabase\n        description: Oracle Database Start an Autonomous Database\n        call: oracle-database.startautonomousdatabase\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /autonomousDatabases/{autonomousDatabaseId}/actions/stop\n      name: stopautonomousdatabase\n      operations:\n      - method: POST\n        name: stopautonomousdatabase\n        description: Oracle Database Stop an Autonomous Database\n        call: oracle-database.stopautonomousdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /autonomousDatabases/{autonomousDatabaseId}/actions/restart\n      name: restartautonomousdatabase\n      operations:\n      - method: POST\n        name: restartautonomousdatabase\n        description: Oracle Database Restart an Autonomous Database\n        call: oracle-database.restartautonomousdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /autonomousDatabases/{autonomousDatabaseId}/actions/generateWallet\n      name: generateautonomousdatabasewallet\n      operations:\n      -\
  \ method: POST\n        name: generateautonomousdatabasewallet\n        description: Oracle Database Generate database wallet\n        call: oracle-database.generateautonomousdatabasewallet\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /autonomousDatabaseBackups\n      name: listautonomousdatabasebackups\n      operations:\n      - method: GET\n        name: listautonomousdatabasebackups\n        description: Oracle Database List Autonomous Database backups\n        call: oracle-database.listautonomousdatabasebackups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /autonomousDatabaseBackups\n      name: createautonomousdatabasebackup\n      operations:\n      - method: POST\n        name: createautonomousdatabasebackup\n        description: Oracle Database Create an Autonomous Database backup\n        call: oracle-database.createautonomousdatabasebackup\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /dbSystems\n      name: listdbsystems\n      operations:\n      - method: GET\n        name: listdbsystems\n        description: Oracle Database List DB Systems\n        call: oracle-database.listdbsystems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbSystems\n      name: launchdbsystem\n      operations:\n      - method: POST\n        name: launchdbsystem\n        description: Oracle Database Launch a DB System\n        call: oracle-database.launchdbsystem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbSystems/{dbSystemId}\n      name: getdbsystem\n      operations:\n      - method: GET\n        name: getdbsystem\n        description: Oracle Database Get a DB System\n        call: oracle-database.getdbsystem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbSystems/{dbSystemId}\n      name: updatedbsystem\n      operations:\n\
  \      - method: PUT\n        name: updatedbsystem\n        description: Oracle Database Update a DB System\n        call: oracle-database.updatedbsystem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbSystems/{dbSystemId}\n      name: terminatedbsystem\n      operations:\n      - method: DELETE\n        name: terminatedbsystem\n        description: Oracle Database Terminate a DB System\n        call: oracle-database.terminatedbsystem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases\n      name: listdatabases\n      operations:\n      - method: GET\n        name: listdatabases\n        description: Oracle Database List databases\n        call: oracle-database.listdatabases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases\n      name: createdatabase\n      operations:\n      - method: POST\n        name: createdatabase\n        description: Oracle Database\
  \ Create a database\n        call: oracle-database.createdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases/{databaseId}\n      name: getdatabase\n      operations:\n      - method: GET\n        name: getdatabase\n        description: Oracle Database Get a database\n        call: oracle-database.getdatabase\n        with:\n          databaseId: rest.databaseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases/{databaseId}\n      name: updatedatabase\n      operations:\n      - method: PUT\n        name: updatedatabase\n        description: Oracle Database Update a database\n        call: oracle-database.updatedatabase\n        with:\n          databaseId: rest.databaseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases/{databaseId}\n      name: deletedatabase\n      operations:\n      - method: DELETE\n        name: deletedatabase\n  \
  \      description: Oracle Database Delete a database\n        call: oracle-database.deletedatabase\n        with:\n          databaseId: rest.databaseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbHomes\n      name: listdbhomes\n      operations:\n      - method: GET\n        name: listdbhomes\n        description: Oracle Database List Database Homes\n        call: oracle-database.listdbhomes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbHomes\n      name: createdbhome\n      operations:\n      - method: POST\n        name: createdbhome\n        description: Oracle Database Create a Database Home\n        call: oracle-database.createdbhome\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbHomes/{dbHomeId}\n      name: getdbhome\n      operations:\n      - method: GET\n        name: getdbhome\n        description: Oracle Database Get a Database Home\n      \
  \  call: oracle-database.getdbhome\n        with:\n          dbHomeId: rest.dbHomeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbHomes/{dbHomeId}\n      name: deletedbhome\n      operations:\n      - method: DELETE\n        name: deletedbhome\n        description: Oracle Database Delete a Database Home\n        call: oracle-database.deletedbhome\n        with:\n          dbHomeId: rest.dbHomeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /backups\n      name: listbackups\n      operations:\n      - method: GET\n        name: listbackups\n        description: Oracle Database List database backups\n        call: oracle-database.listbackups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /backups\n      name: createbackup\n      operations:\n      - method: POST\n        name: createbackup\n        description: Oracle Database Create a database backup\n        call:\
  \ oracle-database.createbackup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /backups/{backupId}\n      name: getbackup\n      operations:\n      - method: GET\n        name: getbackup\n        description: Oracle Database Get a database backup\n        call: oracle-database.getbackup\n        with:\n          backupId: rest.backupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /backups/{backupId}\n      name: deletebackup\n      operations:\n      - method: DELETE\n        name: deletebackup\n        description: Oracle Database Delete a database backup\n        call: oracle-database.deletebackup\n        with:\n          backupId: rest.backupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dataGuardAssociations\n      name: listdataguardassociations\n      operations:\n      - method: GET\n        name: listdataguardassociations\n        description: Oracle Database\
  \ List Data Guard associations\n        call: oracle-database.listdataguardassociations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pluggableDatabases\n      name: listpluggabledatabases\n      operations:\n      - method: GET\n        name: listpluggabledatabases\n        description: Oracle Database List pluggable databases\n        call: oracle-database.listpluggabledatabases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pluggableDatabases\n      name: createpluggabledatabase\n      operations:\n      - method: POST\n        name: createpluggabledatabase\n        description: Oracle Database Create a pluggable database\n        call: oracle-database.createpluggabledatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pluggableDatabases/{pluggableDatabaseId}\n      name: getpluggabledatabase\n      operations:\n      - method: GET\n        name: getpluggabledatabase\n\
  \        description: Oracle Database Get a pluggable database\n        call: oracle-database.getpluggabledatabase\n        with:\n          pluggableDatabaseId: rest.pluggableDatabaseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pluggableDatabases/{pluggableDatabaseId}\n      name: updatepluggabledatabase\n      operations:\n      - method: PUT\n        name: updatepluggabledatabase\n        description: Oracle Database Update a pluggable database\n        call: oracle-database.updatepluggabledatabase\n        with:\n          pluggableDatabaseId: rest.pluggableDatabaseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pluggableDatabases/{pluggableDatabaseId}\n      name: deletepluggabledatabase\n      operations:\n      - method: DELETE\n        name: deletepluggabledatabase\n        description: Oracle Database Delete a pluggable database\n        call: oracle-database.deletepluggabledatabase\n    \
  \    with:\n          pluggableDatabaseId: rest.pluggableDatabaseId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: oracle-database-mcp\n    transport: http\n    description: MCP adapter for Oracle Database Oracle Cloud Infrastructure Database API for AI agent use.\n    tools:\n    - name: listautonomousdatabases\n      description: Oracle Database List Autonomous Databases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-database.listautonomousdatabases\n      with:\n        displayName: tools.displayName\n        lifecycleState: tools.lifecycleState\n        dbWorkload: tools.dbWorkload\n      inputParameters:\n      - name: displayName\n        type: string\n        description: Filter by display name\n      - name: lifecycleState\n        type: string\n        description: Filter by lifecycle state\n      - name: dbWorkload\n        type: string\n\
  \        description: Filter by workload type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createautonomousdatabase\n      description: Oracle Database Create an Autonomous Database\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-database.createautonomousdatabase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getautonomousdatabase\n      description: Oracle Database Get an Autonomous Database\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-database.getautonomousdatabase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateautonomousdatabase\n      description: Oracle Database Update an Autonomous Database\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: oracle-database.updateautonomousdatabase\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteautonomousdatabase\n      description: Oracle Database Delete an Autonomous Database\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: oracle-database.deleteautonomousdatabase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startautonomousdatabase\n      description: Oracle Database Start an Autonomous Database\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-database.startautonomousdatabase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stopautonomousdatabase\n      description: Oracle Database Stop an Autonomous Database\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-database.stopautonomousdatabase\n      outputParameters:\n      - type: object\n      \
  \  mapping: $.\n    - name: restartautonomousdatabase\n      description: Oracle Database Restart an Autonomous Database\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-database.restartautonomousdatabase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generateautonomousdatabasewallet\n      description: Oracle Database Generate database wallet\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-database.generateautonomousdatabasewallet\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listautonomousdatabasebackups\n      description: Oracle Database List Autonomous Database backups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-database.listautonomousdatabasebackups\n      with:\n        autonomousDatabaseId: tools.autonomousDatabaseId\n\
  \      inputParameters:\n      - name: autonomousDatabaseId\n        type: string\n        description: The Autonomous Database OCID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createautonomousdatabasebackup\n      description: Oracle Database Create an Autonomous Database backup\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-database.createautonomousdatabasebackup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdbsystems\n      description: Oracle Database List DB Systems\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-database.listdbsystems\n      with:\n        displayName: tools.displayName\n        lifecycleState: tools.lifecycleState\n      inputParameters:\n      - name: displayName\n        type: string\n        description: displayName\n      - name: lifecycleState\n        type:\
  \ string\n        description: lifecycleState\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: launchdbsystem\n      description: Oracle Database Launch a DB System\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-database.launchdbsystem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdbsystem\n      description: Oracle Database Get a DB System\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-database.getdbsystem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatedbsystem\n      description: Oracle Database Update a DB System\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: oracle-database.updatedbsystem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: terminatedbsystem\n\
  \      description: Oracle Database Terminate a DB System\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: oracle-database.terminatedbsystem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdatabases\n      description: Oracle Database List databases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-database.listdatabases\n      with:\n        dbHomeId: tools.dbHomeId\n        systemId: tools.systemId\n      inputParameters:\n      - name: dbHomeId\n        type: string\n        description: dbHomeId\n      - name: systemId\n        type: string\n        description: systemId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdatabase\n      description: Oracle Database Create a database\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-database.createdatabase\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdatabase\n      description: Oracle Database Get a database\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-database.getdatabase\n      with:\n        databaseId: tools.databaseId\n      inputParameters:\n      - name: databaseId\n        type: string\n        description: databaseId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatedatabase\n      description: Oracle Database Update a database\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      cal\n\n# --- truncated at 32 KB (38 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/oracle-database/refs/heads/main/capabilities/oracle-database-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-database/refs/heads/main/capabilities/oracle-database-capability.yaml
tags:
- Oracle
- Database
- API
tools:
- description: Oracle Database List Autonomous Databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listautonomousdatabases
- description: Oracle Database Create an Autonomous Database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createautonomousdatabase
- description: Oracle Database Get an Autonomous Database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getautonomousdatabase
- description: Oracle Database Update an Autonomous Database
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateautonomousdatabase
- description: Oracle Database Delete an Autonomous Database
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteautonomousdatabase
- description: Oracle Database Start an Autonomous Database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startautonomousdatabase
- description: Oracle Database Stop an Autonomous Database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stopautonomousdatabase
- description: Oracle Database Restart an Autonomous Database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restartautonomousdatabase
- description: Oracle Database Generate database wallet
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateautonomousdatabasewallet
- description: Oracle Database List Autonomous Database backups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listautonomousdatabasebackups
- description: Oracle Database Create an Autonomous Database backup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createautonomousdatabasebackup
- description: Oracle Database List DB Systems
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdbsystems
- description: Oracle Database Launch a DB System
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: launchdbsystem
- description: Oracle Database Get a DB System
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdbsystem
- description: Oracle Database Update a DB System
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedbsystem
- description: Oracle Database Terminate a DB System
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: terminatedbsystem
- description: Oracle Database List databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatabases
- description: Oracle Database Create a database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdatabase
- description: Oracle Database Get a database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatabase
- description: Oracle Database Update a database
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedatabase
- description: Oracle Database Delete a database
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedatabase
- description: Oracle Database List Database Homes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdbhomes
- description: Oracle Database Create a Database Home
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdbhome
- description: Oracle Database Get a Database Home
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdbhome
- description: Oracle Database Delete a Database Home
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedbhome
- description: Oracle Database List database backups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbackups
- description: Oracle Database Create a database backup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbackup
- description: Oracle Database Get a database backup
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbackup
- description: Oracle Database Delete a database backup
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebackup
- description: Oracle Database List Data Guard associations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdataguardassociations
- description: Oracle Database List pluggable databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpluggabledatabases
- description: Oracle Database Create a pluggable database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpluggabledatabase
- description: Oracle Database Get a pluggable database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpluggabledatabase
- description: Oracle Database Update a pluggable database
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepluggabledatabase
- description: Oracle Database Delete a pluggable database
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepluggabledatabase
---
