---
title: List all RQL jobs
excerpt: >
  If you use a project access token, all rql jobs for that project will be
  returned. If you use an account access token, all rql jobs for the account
  will be returned.

  # Response

  ```json

  {
    "err" 0,
    "result": [
      { ... }, // RQL job resource
        ...
    ]
  }

  ```
api:
  file: rollbar-api-new.json
  operationId: list-all-rql-jobs
hidden: false
---