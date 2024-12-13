---
title: Request person deletion
excerpt: >
  This endpoint allows for removal of a tracked person from all projects within
  an account.


  To identify the person, you must provide **exactly one** of the following:

  * `email`

  * `username`

  * `person_id`


  These correspond to the values transmitted in the original occurrences (see
  the docs for [Create item](ref:create-item)) and can also be found by viewing
  any tracked person via the [People Tracking](doc:person-tracking) page in any
  project.


  Requests for person deletion are asynchronous.  The returned value will
  include an `id` property that can be used to check the status of the deletion
  process, e.g.

  ```

  {
    "err": 0,
    "result": {
      "id": 3
    }
  }

  ```
api:
  file: Usersjyowelloasrollbar-api-new.json
  operationId: delete-a-person
hidden: false
---