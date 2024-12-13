---
title: Get a user
excerpt: >
  Get user details for a given account


  Returns basic information about the user, as relevant to the account your
  access token is for. This is the same information available on the "Members"
  page in the Rollbar UI.


  # Sample Response

  ```json

  {
    "err": 0,
    "result": {
        "id": 14,
        "username": "brian",
        "email": "brian@rollbar.com",
        "email_enabled": 1
    }
  }

  ```
api:
  file: Usersjyowelloasrollbar-api-new.json
  operationId: get-a-user
hidden: false
---