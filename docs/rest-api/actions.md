# Trigger actions

When a new log is created, you can trigger server-side functions by passing action's name and arguments to the HTTP request.

## Actions

These are the avaliable actions and their arguments:


|Comment|Action Name|Arguments|
|---|---|---|
|Send a Discord message.|`send_discord`|`channel_id`: required|
|Send a `POST` request.|`send_post_requst`|`data`: optional; `headers`: optional|
|Send a Telegram message.|`send_telegram`|`chat_id`: required|

## Example: send Telegram message

For example, you can send a Telegram message containing the event as follows:

```python
import requests

headers = {'Authentication': f'Bearer {token}'}

data = {
  'project': project_id,
  'event': 'Hello World!',
  'actions': [
    {
      'action': 'send_telegram',
      'args': {
        'chat_id': chat_id,
      },
    },
  ],
}

requests.post(
  'http://localhost:8000/api/log/',
  json=data,
  headers=headers,
)
```