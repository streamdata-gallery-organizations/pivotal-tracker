---
swagger: "2.0"
x-collection-name: Pivotal Tracker
x-complete: 0
info:
  title: Pivotal Tracker Get Projects Project Activities
  description: Retrieves the recent activity of a specific project.
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
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---