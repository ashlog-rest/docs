# API Endpoints

AshLog comes with several endpoints for authentication, logging and project management.

## Authentication

Comment|Method|Url|Parameters|
---|---|---|---|
Obtain an access and refresh token.|`POST`|`/auth/token/`|`username`: required; `password`: required|
Refresh the access token.|`POST`|`/auth/token/refresh/`|`refresh`: required|

## Project management

Comment|Method|Url|Parameters|
---|---|---|---|
List projects.|`GET`|`/api/project/`|-|
Create a new project.|`POST`|`/api/project/`|`name`: required|
Edit a project.|`PUT`|`/api/project/<int:project_id>/`|`name`: required|
Delete a project.|`PUT`|`/api/project/<int:project_id>/`|-|

## Logs management

Comment|Method|Url|Parameters|
---|---|---|---|
List logs.|`GET`|`/project/<int:project_id>/log/`|-|
New log.|`POST`|`/api/log/`|`project`: required; `event`: required; `actions`: optional|

For more information about the `actions` parameter, see the [Trigger actions](/docs/backend/actions) docs.