---
title: List all environments
excerpt: |
  Returns all environments in the project, in pages of 20.

  A successful response looks like:
  ```
  {
    'err': 0
    'result': {
      'page': 1,
      'environments': [
        // where each environment has the shape:
        {
          'id': 1,
          'project_id': 123,
          'environment': 'production',
          // visibility of the environment in the app (can either be 1 or 0)
          'visible': 1
        },
        ...
      ]
    }
  }
  ```
api:
  file: Usersjyowelloasrollbar-api-new.json
  operationId: list-all-environments
hidden: false
---