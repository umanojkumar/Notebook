openapi: 3.0.0
info:
  title: Octane Academy
  version: 1.0.0
  description: ''
servers:
  - url: '{{url}}'
paths:
  /authentication/sign_in:
    parameters: []
    post:
      summary: Sign in with client_id and secret
      responses: 
        '200':
          description: OK
        '401':
          description: Login Failed
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                client_id:
                  type: string
                client_secret:
                  type: string
  /authentication/sign_out:
    parameters: []
    post:
      summary: Sign-out
      responses: 
        '200':
          description: OK
        '401':
          description: Login Failed
  /api/shared_spaces/{shared_space}/workspaces/{workspace}/epics:
    get:
      summary: Get all epics
      parameters:
        - name: shared_space
          in: path
          required: true
          schema:
            type: string
        - name: workspace
          in: path
          required: true
          schema:
            type: string
        - name: fields
          in: query
          required: false
          example: name,description
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: true
          schema:
            type: string
      responses:
        '200':
          description: Successful retrieval of epics
          content:
            application/json:
              schema:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: string
                    name:
                      type: string
                    description:
                      type: string
        '400':
          description: Bad request
        '401':
          description: Unauthorized

  /api/shared_spaces/{shared_space}/workspaces/{workspace}/features:
    get:
      summary: Get all features
      parameters:
        - name: shared_space
          in: path
          required: true
          schema:
            type: string
        - name: workspace
          in: path
          required: true
          schema:
            type: string
        - name: fields
          in: query
          required: false
          example: name,description
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: true
          schema:
            type: string
      responses:
        '200':
          description: Successful retrieval of features
          content:
            application/json:
              schema:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: string
                    name:
                      type: string
                    description:
                      type: string
        '400':
          description: Bad request
        '401':
          description: Unauthorized

  /api/shared_spaces/{shared_space}/workspaces/{workspace}/stories:
    get:
      summary: Get all user stories
      parameters:
        - name: shared_space
          in: path
          required: true
          schema:
            type: string
        - name: workspace
          in: path
          required: true
          schema:
            type: string
        - name: fields
          in: query
          required: false
          example: test
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: true
          schema:
            type: string
      responses:
        '200':
          description: Successful retrieval of user stories
          content:
            application/json:
              schema:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: string
                    name:
                      type: string
                    description:
                      type: string
        '400':
          description: Bad request
        '401':
          description: Unauthorized

  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/quality_stories:
    parameters: []
    get:
      summary: Get all quality stories
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/defects:
    parameters: []
    get:
      summary: Get all defects
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/defects/{{defect_id}}:
    parameters: []
    get:
      summary: Get defect by Id
      parameters:
        - name: fields
          in: query
          required: false
          example: analysis_udf
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/tasks:
    parameters: []
    get:
      summary: Get all tasks
      parameters:
        - name: fields
          in: query
          required: false
          example: name
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/work_items:
    parameters: []
    get:
      summary: Get all work items by subtype
      parameters:
        - name: fields
          in: query
          required: false
          example: subtype, name, phase
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/tests/{{manual_test_id}}/script:
    parameters: []
    get:
      summary: Get test script
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/manual_tests:
    parameters: []
    get:
      summary: Get all manual tests
      parameters:
        - name: fields
          in: query
          required: false
          example: name,description, covered_requirement
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/tests/{{gherkin_test_id}}/script:
    parameters: []
    get:
      summary: Get gherkin test script
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/gherkin_tests:
    parameters: []
    get:
      summary: Get all gherkin tests
      parameters:
        - name: fields
          in: query
          required: false
          example: name,description
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/automated_tests:
    parameters: []
    get:
      summary: Get all automated tests
      parameters:
        - name: fields
          in: query
          required: false
          example: name,description
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/test_suite_link_to_tests:
    parameters: []
    get:
      summary: Get all tests within a test suite
      parameters:
        - name: fields
          in: query
          required: false
          example: test_suite,test
          schema:
            type: string
        - name: query
          in: query
          required: false
          example: '"test_suite EQ {id EQ {{test_suite_id}}}"'
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/test_suites:
    parameters: []
    get:
      summary: Get all test suites
      parameters:
        - name: fields
          in: query
          required: false
          example: name,description
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/test_versions:
    parameters: []
    get:
      summary: Get all test version with all system fields
      parameters:
        - name: fields
          in: query
          required: false
          example: >-
            client_lock_stamp,comment,creation_time,creator,id,is_external,last_modified,name,releases,script,test,version_stamp
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/tests:
    parameters: []
    get:
      summary: Get all tests
      parameters:
        - name: fields
          in: query
          required: false
          example: subtype, name
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/application_modules:
    parameters: []
    get:
      summary: Delete all application modules by parents name
      parameters:
        - name: query
          in: query
          required: false
          example: '"parent EQ {name EQ ^Procure to Pay *^}"'
          schema:
            type: string
        - name: fields
          in: query
          required: false
          example: name,description
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/releases:
    parameters: []
    get:
      summary: Get all releases
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/sprints:
    parameters: []
    get:
      summary: Get all sprints
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/milestones:
    parameters: []
    get:
      summary: Get all milestones
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/planning_info:
    parameters: []
    get:
      summary: Get all objectives
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/programs:
    parameters: []
    get:
      summary: Get all programs
      parameters:
        - name: fields
          in: query
          required: false
          example: client_lock_stamp,creation_time,id,last_modified,name,version_stamp
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/processes:
    parameters: []
    get:
      summary: Get all processes
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
        - name: HPECLIENTTYPE
          in: header
          required: false
          example: HPE_MQM_UI
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/suite_run:
    parameters: []
    get:
      summary: Get all suite runs
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/manual_runs:
    parameters: []
    get:
      summary: Get all manual runs
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/automated_runs:
    parameters: []
    get:
      summary: Get all automated runs
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/gherkin_automated_runs:
    parameters: []
    get:
      summary: Get all gherkin auto runs
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/run_steps:
    parameters: []
    get:
      summary: Get all run steps of a manual run
      parameters:
        - name: query
          in: query
          required: false
          example: '"run EQ {id EQ ^7005^}"'
          schema:
            type: string
        - name: fields
          in: query
          required: false
          example: description,result
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/runs:
    parameters: []
    get:
      summary: Get all runs
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/ci_servers:
    parameters: []
    get:
      summary: Get all ci servers
      parameters:
        - name: fields
          in: query
          required: false
          example: name
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/ci_servers/configured:
    parameters: []
    get:
      summary: Get all ci server connected
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/pipelines:
    parameters: []
    get:
      summary: Get all pipelines
      parameters:
        - name: fields
          in: query
          required: false
          example: name,author,creation_time,ci_server
          schema:
            type: string
        - name: limit
          in: query
          required: false
          example: '100'
          schema:
            type: integer
        - name: order_by
          in: query
          required: false
          example: id
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/ci_jobs:
    parameters: []
    get:
      summary: Get ci_jobs id
      parameters:
        - name: fields
          in: query
          required: false
          example: name
          schema:
            type: string
        - name: HPECLIENTTYPE
          in: header
          required: false
          example: HPE_MQM_UI
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/ci_builds/2001:
    parameters: []
    get:
      summary: Get a single ci_build
      parameters:
        - name: fields
          in: query
          required: false
          example: name,pipeline_node,status
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/scm_commits:
    parameters: []
    get:
      summary: Get all scm commits
      parameters:
        - name: query
          in: query
          required: false
          example: '"stories EQ {id EQ 6062}"'
          schema:
            type: string
        - name: fields
          in: query
          required: false
          example: ci_build
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
      requestBody:
        content:
          application/json:
            schema:
              type: object
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/scm_repositories/7001:
    parameters: []
    get:
      summary: Get all scm repositories
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
        - name: HPECLIENTTYPE
          in: header
          required: false
          example: HPE_MQM_UI
          schema:
            type: string
      responses: {}
      requestBody:
        content:
          application/json:
            schema:
              type: object
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/scm_commits/5003:
    parameters: []
    get:
      summary: Get single scm commit
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
        - name: HPECLIENTTYPE
          in: header
          required: false
          example: HPE_MQM_UI
          schema:
            type: string
      responses: {}
      requestBody:
        content:
          application/json:
            schema:
              type: object
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/test-results/10113:
    parameters: []
    get:
      summary: Get pushed test status
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/issues:
    parameters: []
    get:
      summary: Get all vulnerabilities
      parameters:
        - name: fields
          in: query
          required: false
          example: >-
            line,state,id,severity,tool_name,package,remote_id,primary_location_full,analysis,commits,category
          schema:
            type: string
        - name: limit
          in: query
          required: false
          example: '30'
          schema:
            type: integer
        - name: offset
          in: query
          required: false
          example: '0'
          schema:
            type: integer
        - name: order_by
          in: query
          required: false
          example: id
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
        - name: hpeclienttype
          in: header
          required: false
          example: HPE_MQM_UI
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/requirement_folders:
    parameters: []
    get:
      summary: Get all requirement folders
      parameters:
        - name: fields
          in: query
          required: false
          example: name
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/requirement_documents:
    parameters: []
    get:
      summary: Get all requirement documents
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/requirements:
    parameters: []
    get:
      summary: Get all requirements (including requirement_root)
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/comments:
    parameters: []
    get:
      summary: Get all comments on all entities
      parameters:
        - name: fields
          in: query
          required: false
          example: owner_work_item,text,author
          schema:
            type: string
        - name: order_by
          in: query
          required: false
          example: author
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/attachments:
    parameters: []
    get:
      summary: Get all attachments
      parameters:
        - name: fields
          in: query
          required: false
          example: name
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/taxonomy_nodes:
    parameters: []
    get:
      summary: Read all Taxonomy Nodes
      parameters:
        - name: fields
          in: query
          required: false
          example: >-
            activity_level,user_activation_status,author,category,client_lock_stamp,creation_time,id,last_modified,name,subtype,version_stamp
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/roles:
    parameters: []
    get:
      summary: Get all roles
      parameters:
        - name: fields
          in: query
          required: false
          example: name
          schema:
            type: string
        - name: order_by
          in: query
          required: false
          example: name
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspace_roles:
    parameters: []
    get:
      summary: Get all workspace roles
      parameters:
        - name: fields
          in: query
          required: false
          example: role
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/workspace_users:
    parameters: []
    get:
      summary: Get all workspace users
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/users:
    parameters: []
    get:
      summary: Get all shared space users
      parameters:
        - name: fields
          in: query
          required: false
          example: full_name
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/list_nodes:
    parameters: []
    get:
      summary: Get all items from list_nodes
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/history_logs:
    parameters: []
    get:
      summary: Get all items from history_logs
      parameters:
        - name: fields
          in: query
          required: false
          example: >-
            id,user_name,timestamp,user_id,action,entity_type,entity_id,entity_physical_id,session_id,request_id,change_set
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces:
    parameters: []
    get:
      summary: Get all workspaces
      parameters:
        - name: fields
          in: query
          required: false
          example: name
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/business_rules:
    parameters: []
    get:
      summary: Get all business rules
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
        - name: HPECLIENTTYPE
          in: header
          required: false
          example: IT_PRIVATE
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/external-entity-actions:
    parameters: []
    get:
      summary: Get all external-entity-actions
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
        - name: HPECLIENTTYPE
          in: header
          required: false
          example: IT_PRIVATE
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/background_tasks:
    parameters: []
    get:
      summary: get background tasks status
      parameters:
        - name: fetch_single_entity
          in: query
          required: false
          example: 'true'
          schema:
            type: boolean
        - name: fields
          in: query
          required: false
          example: >-
            creation_time,client_lock_stamp,has_attachments,attachments,version_stamp,author,end_time,workspace_id,result,start_time,followed_by_me,app_key,task_type,last_modified,max_wait_time,status
          schema:
            type: string
        - name: offset
          in: query
          required: false
          example: '0'
          schema:
            type: integer
        - name: query
          in: query
          required: false
          example: '"(id=''85011'')"'
          schema:
            type: string
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
        - name: hpeclienttype
          in: header
          required: false
          example: IT_PRIVATE
          schema:
            type: string
      responses: {}
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                document_type:
                  type: string
                timezone:
                  type: string
                  format: uri
                file_name:
                  type: string
                report_entries:
                  type: array
                  items:
                    type: object
                    properties:
                      entity_name:
                        type: string
                      subtypes:
                        type: array
                        items:
                          type: string
                      fields:
                        type: array
                        items:
                          type: string
                      include_attachments:
                        type: string
                      order_by:
                        nullable: true
                      filter:
                        type: string
                purpose:
                  type: string
                is_export_for_create_import:
                  type: boolean
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/attachments/123009:
    parameters: []
    get:
      summary: get excel file for export
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
        - name: Content-Type
          in: header
          required: false
          example: application/octet-stream
          schema:
            type: string
      responses: {}
  /api/shared_spaces/{{shared_space}}/workspaces/{{workspace}}/attachments/3002/Requirement_AK_DEMO.pdf:
    parameters: []
    get:
      summary: Export requirement as document Copy
      parameters:
        - name: ALM-OCTANE-TECH-PREVIEW
          in: header
          required: false
          example: '{{tech_preview_flag}}'
          schema:
            type: string
        - name: hpeclienttype
          in: header
          required: false
          example: IT_PRIVATE
          schema:
            type: string
      responses: {}
      requestBody:
        content:
          application/json:
            schema:
              type: object
