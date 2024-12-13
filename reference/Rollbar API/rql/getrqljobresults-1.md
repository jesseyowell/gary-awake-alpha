---
title: Get RQL job results
excerpt: |
  # Response
  The response will be a RQL job result resource, example:
  ```json
  {
    "err" 0,
    "result": {
      "job_id": 123,  // job id
      "result": {
        "rows": [{...}],
        "selectionColumns": [...],
        "columns": [...],
        "errors": [],
        "warnings": [],
        "rowcount": 1,
        "executionTime": 123
      },
      "job": {...} // A RQL job resource if expand=job is set in the query string
    }
  }```
api:
  file: dupe-rollbar-api.json
  operationId: get-rql-job-results
hidden: false
---