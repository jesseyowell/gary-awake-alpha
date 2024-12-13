---
title: List invitations to a team
excerpt: >
  Returns all invites ever sent for the team–pending, accepted, rejected, and
  canceled.


  # Example response

  ```

  {
    "err": 0,
    "result": [
      {
        "id": 71328,
        "from_user_id": 5325,
        "team_id": 272686,
        "to_email": "gilfoyle@pidepiper.com",
        "status": "pending",
        "date_created": 1519946545,
        "date_redeemed": null
      }
    ]
  }

  ```
api:
  file: rollbar-api-new.json
  operationId: list-invitations-to-a-team
hidden: false
---