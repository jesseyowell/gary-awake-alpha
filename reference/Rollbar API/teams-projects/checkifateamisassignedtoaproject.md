---
title: Check if a team is assigned to a project
excerpt: >
  Returns `200` if the team is assigned to a project, `404` if the team is not
  assigned to the project.


  # Example responses


  ```json

  {
    "err": 0,
    "result": {
      "team_id": 272686,
      "project_id": 165090
    }
  }

  ```


  ```json

  {
    "err": 1,
    "message": "Project is not in this Team."
  }

  ```
api:
  file: Usersjyowelloasrollbar-api-new.json
  operationId: check-if-a-team-is-assigned-to-a-project
hidden: false
---