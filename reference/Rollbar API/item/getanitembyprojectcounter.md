---
title: Get an item (by project counter)
excerpt: >
  `counter` must be an item counter for an item in the project. The counter can
  be found in URLs like `https://rollbar.com/myaccount/myproject/items/456/`
  (456 is the counter).


  The success response is a 301 redirect like this:


  ```

  HTTP/1.1 301 Moved Permanently

  Location: /api/1/item/272505123


  {
    "err": 0,
    "result": {
      "itemId": 272505123,
      "path": "/api/1/item/272505123",
      "uri": "/api/1/item/272505123"
    }
  }

  ```
api:
  file: Usersjyowelloasrollbar-api-new.json
  operationId: get-an-item-by-project-counter
hidden: false
---