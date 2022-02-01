# Web Dashboard

## Default dashboard

AshLog can work without a dashboard. In fact you can manage your projects and logs throught the REST API.

However it comes by default with a lightweight webapp built using Bootstrap. No further configuration is required, it will be automatically accessible.

## Custom dashboard

AshLog is built on top of Django, so you can extend it by creating your own application and style the user interface as you like.

Moreover, you are not forced to use Django. You can create your own dashboard (even a native client) and talk to the server by using the apis as stated in the [documentation](/rest-api/endpoint).