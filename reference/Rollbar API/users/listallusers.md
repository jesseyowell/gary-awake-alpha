---
title: List all users
excerpt: |
  List all users who are members of an account
  #Response Format
  ```json
  {
    "err": 0,
    "result": {
      "users": [
      {
        "username": "brianr",
        "id": 1,
        "email": "brian@rollbar.com"
      },
      {
        "username": "coryvirok",
        "id": 2,
        "email": "cory@rollbar.com"
      }
      ]
    }
  }
  ```
api:
  file: Usersjyowelloasrollbar-api-new.json
  operationId: list-all-users
hidden: false
---