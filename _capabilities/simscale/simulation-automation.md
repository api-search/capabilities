---
api_specs:
- filename: simscale-openapi.yml
  format: yaml
  label: simscale
  slug: simscale
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/simscale/refs/heads/main/openapi/simscale-openapi.yml
categories: []
consumed_apis:
- simscale
description: 'Workflow capability for automated engineering simulation using SimScale. Covers the complete simulation pipeline: project setup, CAD geometry upload, mesh generation, simulation configuration, execution, and results retrieval for CFD, FEA, and thermal workflows.'
layout: capability
name: SimScale Simulation Automation
operations:
- description: List all simulation projects.
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a new simulation project.
  method: POST
  name: create-project
  path: /v1/projects
- description: Get project details.
  method: GET
  name: get-project
  path: /v1/projects/{id}
- description: Update project metadata.
  method: PUT
  name: update-project
  path: /v1/projects/{id}
- description: Delete a project.
  method: DELETE
  name: delete-project
  path: /v1/projects/{id}
- description: Create upload storage and get presigned URL.
  method: POST
  name: create-storage
  path: /v1/storage
- description: List geometries in a project.
  method: GET
  name: list-geometries
  path: /v1/projects/{id}/geometries
- description: Import a CAD geometry file.
  method: POST
  name: import-geometry
  path: /v1/projects/{id}/geometries
- description: Get geometry import status and details.
  method: GET
  name: get-geometry
  path: /v1/projects/{proj_id}/geometries/{id}
- description: List all simulations in a project.
  method: GET
  name: list-simulations
  path: /v1/projects/{id}/simulations
- description: Create a new simulation specification.
  method: POST
  name: create-simulation
  path: /v1/projects/{id}/simulations
- description: Get simulation specification and status.
  method: GET
  name: get-simulation
  path: /v1/projects/{proj_id}/simulations/{id}
- description: List mesh operations in a project.
  method: GET
  name: list-mesh-operations
  path: /v1/projects/{id}/mesh-operations
- description: Create a mesh generation operation.
  method: POST
  name: create-mesh-operation
  path: /v1/projects/{id}/mesh-operations
- description: Trigger mesh generation execution.
  method: POST
  name: start-mesh-operation
  path: /v1/projects/{proj_id}/mesh-operations/{id}/start
- description: List all runs for a simulation.
  method: GET
  name: list-simulation-runs
  path: /v1/projects/{proj_id}/simulations/{sim_id}/runs
- description: Create and start a new simulation run.
  method: POST
  name: create-simulation-run
  path: /v1/projects/{proj_id}/simulations/{sim_id}/runs
- description: Get simulation run status and progress.
  method: GET
  name: get-simulation-run
  path: /v1/projects/{proj_id}/simulations/{sim_id}/runs/{id}
- description: Get completed simulation results and download links.
  method: GET
  name: get-simulation-results
  path: /v1/projects/{proj_id}/simulations/{sim_id}/runs/{id}/results
personas: []
provider_name: SimScale
provider_slug: simscale
search_terms:
- engineering
- get mesh operation
- create mesh operation
- create and start a new simulation computation run.
- cfd
- list mesh operations in a project.
- list all simulations defined within a project.
- list all mesh generation operations in a project.
- create storage
- create and start a new simulation run.
- get geometry
- list simulations
- list simulation runs
- simulation setup and management.
- list mesh operations
- get simulation results
- single simulation operations.
- mesh generation operations.
- simulation project lifecycle management.
- check the status of a mesh generation operation.
- delete a simulation project and all associated data.
- get project
- simulation results retrieval.
- list all simulations in a project.
- start mesh operation
- get simulation
- create simulation run
- retrieve results and download links for a completed simulation run.
- create a new simulation specification.
- list all simulation projects.
- single geometry operations.
- create a new engineering simulation project in simscale.
- simulation
- get project details.
- update project metadata.
- check the status and progress of a simulation run.
- file storage for geometry uploads.
- create a mesh generation operation.
- single simulation run status.
- get simulation run status and progress.
- cad geometry management.
- update project
- cae
- get completed simulation results and download links.
- trigger the execution of a mesh generation operation.
- delete project
- create simulation
- import geometry
- trigger mesh generation execution.
- import a cad geometry file (step, iges, stl, parasolid) into a project.
- list all runs for a simulation.
- get simulation run
- list all cae simulation projects in the simscale account.
- delete a project.
- cloud simulation
- check the import status of a cad geometry file.
- list all cad geometries imported into a project.
- list projects
- import a cad geometry file.
- start mesh generation.
- create project
- single project operations.
- get simulation specification and status.
- list all execution runs for a simulation.
- simulation automation
- create a new simulation project.
- create a new cfd, fea, or thermal simulation for a geometry.
- create upload storage and get presigned url.
- create a file storage location for uploading a cad geometry file.
- fea
- list geometries in a project.
- get the full specification and validation status of a simulation.
- get details of a specific simulation project.
- create a mesh generation operation for a cad geometry.
- list geometries
- get geometry import status and details.
- simulation execution runs.
slug: simulation-automation
source_filename: simulation-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SimScale Simulation Automation\"\n  description: \"Workflow capability for automated engineering simulation using SimScale. Covers the complete simulation pipeline: project setup, CAD geometry upload, mesh generation, simulation configuration, execution, and results retrieval for CFD, FEA, and thermal workflows.\"\n  tags:\n  - CAE\n  - CFD\n  - FEA\n  - Simulation Automation\n  - Engineering\n  - Cloud Simulation\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SIMSCALE_API_KEY: SIMSCALE_API_KEY\n\ncapability:\n  consumes:\n    - import: simscale\n      location: ./shared/simscale.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: simulation-automation-api\n      description: \"Unified REST API for automated engineering simulation workflows on SimScale.\"\n      resources:\n        - path: /v1/projects\n          name: projects\n          description:\
  \ \"Simulation project lifecycle management.\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List all simulation projects.\"\n              call: \"simscale.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: \"Create a new simulation project.\"\n              call: \"simscale.create-project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{id}\n          name: project\n          description: \"Single project operations.\"\n          operations:\n            - method: GET\n              name: get-project\n              description: \"Get project details.\"\n              call: \"simscale.get-project\"\n              with:\n                project_id: \"rest.id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-project\n              description: \"Update project metadata.\"\n              call: \"simscale.update-project\"\n              with:\n                project_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-project\n              description: \"Delete a project.\"\n              call: \"simscale.delete-project\"\n              with:\n                project_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/storage\n          name: storage\n          description: \"File storage for geometry uploads.\"\n          operations:\n            - method: POST\n              name: create-storage\n              description: \"Create upload storage and get presigned URL.\"\
  \n              call: \"simscale.create-storage\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{id}/geometries\n          name: geometries\n          description: \"CAD geometry management.\"\n          operations:\n            - method: GET\n              name: list-geometries\n              description: \"List geometries in a project.\"\n              call: \"simscale.list-geometries\"\n              with:\n                project_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: import-geometry\n              description: \"Import a CAD geometry file.\"\n              call: \"simscale.import-geometry\"\n              with:\n                project_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{proj_id}/geometries/{id}\n\
  \          name: geometry\n          description: \"Single geometry operations.\"\n          operations:\n            - method: GET\n              name: get-geometry\n              description: \"Get geometry import status and details.\"\n              call: \"simscale.get-geometry\"\n              with:\n                project_id: \"rest.proj_id\"\n                geometry_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{id}/simulations\n          name: simulations\n          description: \"Simulation setup and management.\"\n          operations:\n            - method: GET\n              name: list-simulations\n              description: \"List all simulations in a project.\"\n              call: \"simscale.list-simulations\"\n              with:\n                project_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \            - method: POST\n              name: create-simulation\n              description: \"Create a new simulation specification.\"\n              call: \"simscale.create-simulation\"\n              with:\n                project_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{proj_id}/simulations/{id}\n          name: simulation\n          description: \"Single simulation operations.\"\n          operations:\n            - method: GET\n              name: get-simulation\n              description: \"Get simulation specification and status.\"\n              call: \"simscale.get-simulation\"\n              with:\n                project_id: \"rest.proj_id\"\n                simulation_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{id}/mesh-operations\n          name: mesh-operations\n\
  \          description: \"Mesh generation operations.\"\n          operations:\n            - method: GET\n              name: list-mesh-operations\n              description: \"List mesh operations in a project.\"\n              call: \"simscale.list-mesh-operations\"\n              with:\n                project_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-mesh-operation\n              description: \"Create a mesh generation operation.\"\n              call: \"simscale.create-mesh-operation\"\n              with:\n                project_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{proj_id}/mesh-operations/{id}/start\n          name: start-mesh\n          description: \"Start mesh generation.\"\n          operations:\n            - method: POST\n            \
  \  name: start-mesh-operation\n              description: \"Trigger mesh generation execution.\"\n              call: \"simscale.start-mesh-operation\"\n              with:\n                project_id: \"rest.proj_id\"\n                mesh_operation_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{proj_id}/simulations/{sim_id}/runs\n          name: simulation-runs\n          description: \"Simulation execution runs.\"\n          operations:\n            - method: GET\n              name: list-simulation-runs\n              description: \"List all runs for a simulation.\"\n              call: \"simscale.list-simulation-runs\"\n              with:\n                project_id: \"rest.proj_id\"\n                simulation_id: \"rest.sim_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-simulation-run\n\
  \              description: \"Create and start a new simulation run.\"\n              call: \"simscale.create-simulation-run\"\n              with:\n                project_id: \"rest.proj_id\"\n                simulation_id: \"rest.sim_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{proj_id}/simulations/{sim_id}/runs/{id}\n          name: simulation-run\n          description: \"Single simulation run status.\"\n          operations:\n            - method: GET\n              name: get-simulation-run\n              description: \"Get simulation run status and progress.\"\n              call: \"simscale.get-simulation-run\"\n              with:\n                project_id: \"rest.proj_id\"\n                simulation_id: \"rest.sim_id\"\n                run_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{proj_id}/simulations/{sim_id}/runs/{id}/results\n\
  \          name: results\n          description: \"Simulation results retrieval.\"\n          operations:\n            - method: GET\n              name: get-simulation-results\n              description: \"Get completed simulation results and download links.\"\n              call: \"simscale.get-simulation-results\"\n              with:\n                project_id: \"rest.proj_id\"\n                simulation_id: \"rest.sim_id\"\n                run_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: simulation-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted engineering simulation automation on SimScale.\"\n      tools:\n        - name: list-projects\n          description: \"List all CAE simulation projects in the SimScale account.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"simscale.list-projects\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-project\n          description: \"Create a new engineering simulation project in SimScale.\"\n          hints:\n            readOnly: false\n          call: \"simscale.create-project\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-project\n          description: \"Get details of a specific simulation project.\"\n          hints:\n            readOnly: true\n          call: \"simscale.get-project\"\n          with:\n            project_id: \"tools.project_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-project\n          description: \"Delete a simulation project and all associated data.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"simscale.delete-project\"\n    \
  \      with:\n            project_id: \"tools.project_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-storage\n          description: \"Create a file storage location for uploading a CAD geometry file.\"\n          hints:\n            readOnly: false\n          call: \"simscale.create-storage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-geometries\n          description: \"List all CAD geometries imported into a project.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"simscale.list-geometries\"\n          with:\n            project_id: \"tools.project_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: import-geometry\n          description: \"Import a CAD geometry file (STEP, IGES, STL, Parasolid) into a project.\"\n          hints:\n            readOnly:\
  \ false\n          call: \"simscale.import-geometry\"\n          with:\n            project_id: \"tools.project_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-geometry\n          description: \"Check the import status of a CAD geometry file.\"\n          hints:\n            readOnly: true\n          call: \"simscale.get-geometry\"\n          with:\n            project_id: \"tools.project_id\"\n            geometry_id: \"tools.geometry_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-simulations\n          description: \"List all simulations defined within a project.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"simscale.list-simulations\"\n          with:\n            project_id: \"tools.project_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-simulation\n\
  \          description: \"Create a new CFD, FEA, or thermal simulation for a geometry.\"\n          hints:\n            readOnly: false\n          call: \"simscale.create-simulation\"\n          with:\n            project_id: \"tools.project_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-simulation\n          description: \"Get the full specification and validation status of a simulation.\"\n          hints:\n            readOnly: true\n          call: \"simscale.get-simulation\"\n          with:\n            project_id: \"tools.project_id\"\n            simulation_id: \"tools.simulation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-mesh-operations\n          description: \"List all mesh generation operations in a project.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"simscale.list-mesh-operations\"\n \
  \         with:\n            project_id: \"tools.project_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-mesh-operation\n          description: \"Create a mesh generation operation for a CAD geometry.\"\n          hints:\n            readOnly: false\n          call: \"simscale.create-mesh-operation\"\n          with:\n            project_id: \"tools.project_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-mesh-operation\n          description: \"Check the status of a mesh generation operation.\"\n          hints:\n            readOnly: true\n          call: \"simscale.get-mesh-operation\"\n          with:\n            project_id: \"tools.project_id\"\n            mesh_operation_id: \"tools.mesh_operation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-mesh-operation\n          description:\
  \ \"Trigger the execution of a mesh generation operation.\"\n          hints:\n            readOnly: false\n          call: \"simscale.start-mesh-operation\"\n          with:\n            project_id: \"tools.project_id\"\n            mesh_operation_id: \"tools.mesh_operation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-simulation-runs\n          description: \"List all execution runs for a simulation.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"simscale.list-simulation-runs\"\n          with:\n            project_id: \"tools.project_id\"\n            simulation_id: \"tools.simulation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-simulation-run\n          description: \"Create and start a new simulation computation run.\"\n          hints:\n            readOnly: false\n          call: \"simscale.create-simulation-run\"\
  \n          with:\n            project_id: \"tools.project_id\"\n            simulation_id: \"tools.simulation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-simulation-run\n          description: \"Check the status and progress of a simulation run.\"\n          hints:\n            readOnly: true\n          call: \"simscale.get-simulation-run\"\n          with:\n            project_id: \"tools.project_id\"\n            simulation_id: \"tools.simulation_id\"\n            run_id: \"tools.run_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-simulation-results\n          description: \"Retrieve results and download links for a completed simulation run.\"\n          hints:\n            readOnly: true\n          call: \"simscale.get-simulation-results\"\n          with:\n            project_id: \"tools.project_id\"\n            simulation_id: \"tools.simulation_id\"\
  \n            run_id: \"tools.run_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/simscale/refs/heads/main/capabilities/simulation-automation.yaml
tags:
- CAE
- CFD
- FEA
- Simulation Automation
- Engineering
- Cloud Simulation
tools:
- description: List all CAE simulation projects in the SimScale account.
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: Create a new engineering simulation project in SimScale.
  hints:
    readOnly: false
  name: create-project
- description: Get details of a specific simulation project.
  hints:
    readOnly: true
  name: get-project
- description: Delete a simulation project and all associated data.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-project
- description: Create a file storage location for uploading a CAD geometry file.
  hints:
    readOnly: false
  name: create-storage
- description: List all CAD geometries imported into a project.
  hints:
    openWorld: true
    readOnly: true
  name: list-geometries
- description: Import a CAD geometry file (STEP, IGES, STL, Parasolid) into a project.
  hints:
    readOnly: false
  name: import-geometry
- description: Check the import status of a CAD geometry file.
  hints:
    readOnly: true
  name: get-geometry
- description: List all simulations defined within a project.
  hints:
    openWorld: true
    readOnly: true
  name: list-simulations
- description: Create a new CFD, FEA, or thermal simulation for a geometry.
  hints:
    readOnly: false
  name: create-simulation
- description: Get the full specification and validation status of a simulation.
  hints:
    readOnly: true
  name: get-simulation
- description: List all mesh generation operations in a project.
  hints:
    openWorld: true
    readOnly: true
  name: list-mesh-operations
- description: Create a mesh generation operation for a CAD geometry.
  hints:
    readOnly: false
  name: create-mesh-operation
- description: Check the status of a mesh generation operation.
  hints:
    readOnly: true
  name: get-mesh-operation
- description: Trigger the execution of a mesh generation operation.
  hints:
    readOnly: false
  name: start-mesh-operation
- description: List all execution runs for a simulation.
  hints:
    openWorld: true
    readOnly: true
  name: list-simulation-runs
- description: Create and start a new simulation computation run.
  hints:
    readOnly: false
  name: create-simulation-run
- description: Check the status and progress of a simulation run.
  hints:
    readOnly: true
  name: get-simulation-run
- description: Retrieve results and download links for a completed simulation run.
  hints:
    readOnly: true
  name: get-simulation-results
---
