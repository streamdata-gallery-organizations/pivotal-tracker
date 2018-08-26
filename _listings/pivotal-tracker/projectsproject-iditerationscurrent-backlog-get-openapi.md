---
swagger: "2.0"
x-collection-name: Pivotal Tracker
x-complete: 0
info:
  title: Pivotal Tracker Get Projects Project Iterations Current Backlog
  description: Retrieves iterations from the "current" and "backlog" groups, with
    stories.
  version: 1.0.0
host: www.pivotaltracker.com
basePath: /services/v3/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /tokens/active:
    get:
      summary: Get Tokens Active
      description: Returns an API token associated with the user. This method requires
        HTTP Basic authentication.
      operationId: getTokensActive
      x-api-path-slug: tokensactive-get
      responses:
        200:
          description: OK
      tags:
      - Tokens
      - Active
    post:
      summary: Post Tokens Active
      description: Returns an API token associated with the user.
      operationId: postTokensActive
      x-api-path-slug: tokensactive-post
      parameters:
      - in: query
        name: password
        description: The users password
      - in: query
        name: username
        description: The users name
      responses:
        200:
          description: OK
      tags:
      - Tokens
      - Active
  /activities:
    get:
      summary: Get Activities
      description: Retrieves the recent activity of all your projects.
      operationId: getActivities
      x-api-path-slug: activities-get
      parameters:
      - in: query
        name: limit
        description: Limits the number of activity feed items
      - in: query
        name: newer_than_version
        description: Restricts the activity feed to only those items that have a greater
          than supplied version
      - in: query
        name: occurred_since_date
        description: 'Restricts the activity feed to only those items that occurred
          after a supplied date (example format: 2009/12/18 21:00:00 UTC)'
      responses:
        200:
          description: OK
      tags:
      - Activities
  /projects/{PROJECT_ID}/activities:
    get:
      summary: Get Projects Project Activities
      description: Retrieves the recent activity of a specific project.
      operationId: getProjectsProjectActivities
      x-api-path-slug: projectsproject-idactivities-get
      parameters:
      - in: query
        name: limit
        description: Limits the number of activity feed items
      - in: query
        name: occurred_since_date
        description: 'Restricts the activity feed to only those items that occurred
          after a supplied date (example format: 2009/12/18 21:00:00 UTC)'
      - in: path
        name: PROJECT_ID
        description: The ID of the project to retrieve the activity for
      responses:
        200:
          description: OK
      tags:
      - Projects
      - PROJECT
      - ID
      - Activities
  /projects/{PROJECT_ID}:
    get:
      summary: Get Projects Project
      description: Retrieves information about a project.
      operationId: getProjectsProject
      x-api-path-slug: projectsproject-id-get
      parameters:
      - in: path
        name: PROJECT_ID
        description: The ID of the project to retrieve
      responses:
        200:
          description: OK
      tags:
      - Projects
      - PROJECT
      - ID
  /projects:
    get:
      summary: Get Projects
      description: Retrieves all of the user's projects.
      operationId: getProjects
      x-api-path-slug: projects-get
      responses:
        200:
          description: OK
      tags:
      - Projects
    post:
      summary: Post Projects
      description: Adds a new project.
      operationId: postProjects
      x-api-path-slug: projects-post
      responses:
        200:
          description: OK
      tags:
      - Projects
  /projects/{PROJECT_ID}/memberships:
    get:
      summary: Get Projects Project Memberships
      description: Retrieves all memberships for a project.
      operationId: getProjectsProjectMemberships
      x-api-path-slug: projectsproject-idmemberships-get
      parameters:
      - in: path
        name: PROJECT_ID
        description: The ID of the project
      responses:
        200:
          description: OK
      tags:
      - Projects
      - PROJECT
      - ID
      - Memberships
    post:
      summary: Post Projects Project Memberships
      description: Adds a new membership to a project.
      operationId: postProjectsProjectMemberships
      x-api-path-slug: projectsproject-idmemberships-post
      parameters:
      - in: path
        name: PROJECT_ID
        description: The ID of the project
      responses:
        200:
          description: OK
      tags:
      - Projects
      - PROJECT
      - ID
      - Memberships
  /projects/{PROJECT_ID}/memberships/{MEMBERSHIP_ID}:
    get:
      summary: Get Projects Project Memberships Membership
      description: Retrieves information about a single membership.
      operationId: getProjectsProjectMembershipsMembership
      x-api-path-slug: projectsproject-idmembershipsmembership-id-get
      parameters:
      - in: path
        name: MEMBERSHIP_ID
        description: The ID of the membership
      - in: path
        name: PROJECT_ID
        description: The ID of the project
      responses:
        200:
          description: OK
      tags:
      - Projects
      - PROJECT
      - ID
      - Memberships
      - MEMBERSHIP
      - ID
    delete:
      summary: Delete Projects Project Memberships Membership
      description: Delete projects project memberships membership.
      operationId: deleteProjectsProjectMembershipsMembership
      x-api-path-slug: projectsproject-idmembershipsmembership-id-delete
      parameters:
      - in: path
        name: MEMBERSHIP_ID
        description: The ID of the membership
      - in: path
        name: PROJECT_ID
        description: The ID of the project
      responses:
        200:
          description: OK
      tags:
      - Projects
      - PROJECT
      - ID
      - Memberships
      - MEMBERSHIP
      - ID
  /projects/{PROJECT_ID}/iterations:
    get:
      summary: Get Projects Project Iterations
      description: Retrieves all iterations, with stories.
      operationId: getProjectsProjectIterations
      x-api-path-slug: projectsproject-iditerations-get
      parameters:
      - in: path
        name: PROJECT_ID
        description: The ID of the project
      responses:
        200:
          description: OK
      tags:
      - Projects
      - PROJECT
      - ID
      - Iterations
  /projects/{PROJECT_ID}/iterations/done:
    get:
      summary: Get Projects Project Iterations Done
      description: Retrieves iterations from the "done" group, with stories.
      operationId: getProjectsProjectIterationsDone
      x-api-path-slug: projectsproject-iditerationsdone-get
      parameters:
      - in: query
        name: limit
        description: Controls the maximum number of iterations returned
      - in: query
        name: offset
        description: Controls the number of iterations to skip from the beginning
          of the result
      - in: path
        name: PROJECT_ID
        description: The ID of the project
      responses:
        200:
          description: OK
      tags:
      - Projects
      - PROJECT
      - ID
      - Iterations
      - Done
  /projects/{PROJECT_ID}/iterations/current:
    get:
      summary: Get Projects Project Iterations Current
      description: Retrieves iterations from the "current" group, with stories.
      operationId: getProjectsProjectIterationsCurrent
      x-api-path-slug: projectsproject-iditerationscurrent-get
      parameters:
      - in: path
        name: PROJECT_ID
        description: The ID of the project
      responses:
        200:
          description: OK
      tags:
      - Projects
      - PROJECT
      - ID
      - Iterations
      - Current
  /projects/{PROJECT_ID}/iterations/backlog:
    get:
      summary: Get Projects Project Iterations Backlog
      description: Retrieves iterations from the "backlog" group, with stories.
      operationId: getProjectsProjectIterationsBacklog
      x-api-path-slug: projectsproject-iditerationsbacklog-get
      parameters:
      - in: query
        name: limit
        description: Controls the maximum number of iterations returned
      - in: query
        name: offset
        description: Controls the number of iterations to skip from the beginning
          of the result
      - in: path
        name: PROJECT_ID
        description: The ID of the project
      responses:
        200:
          description: OK
      tags:
      - Projects
      - PROJECT
      - ID
      - Iterations
      - Backlog
  /projects/{PROJECT_ID}/iterations/current_backlog:
    get:
      summary: Get Projects Project Iterations Current Backlog
      description: Retrieves iterations from the "current" and "backlog" groups, with
        stories.
      operationId: getProjectsProjectIterationsCurrentBacklog
      x-api-path-slug: projectsproject-iditerationscurrent-backlog-get
      parameters:
      - in: query
        name: limit
        description: Controls the maximum number of iterations returned
      - in: query
        name: offset
        description: Controls the number of iterations to skip from the beginning
          of the result
      - in: path
        name: PROJECT_ID
        description: The ID of the project
      responses:
        200:
          description: OK
      tags:
      - Projects
      - PROJECT
      - ID
      - Iterations
      - Current
      - Backlog
x-streamrank:
  polling_total_time_average: "0"
  polling_size_download_average: "0"
  streaming_total_time_average: "0"
  streaming_size_download_average: "0"
  change_yes: "0"
  change_no: "0"
  time_percentage: "0"
  size_percentage: "0"
  change_percentage: "200"
  last_run: ~
  days_run: "0"
  minute_run: "0"
---