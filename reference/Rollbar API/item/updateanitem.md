---
title: Update an item
excerpt: >
  Used to modify an item's state. Currently supports:

  * setting the status, level, title, assigned user

  * when resolving, setting the "resolved in version"

  * snoozing / unsnoozing an item (only available for paid accounts)

  * setting the item owner to a team (only available for Advanced and Enterprise
  accounts)


  Example -

  ```curl

  curl -X PATCH 'https://api.rollbar.com/api/1/item/275123456' \
    --header "Content-Type: application/json" \
    --data '{"status": "resolved", "resolved_in_version": "aabbcc1"}'
    ```
api:
  file: rollbar-api-new.json
  operationId: update-an-item
hidden: false
---