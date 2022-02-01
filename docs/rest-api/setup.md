# Setup AshLog

## Generate and set environment variables

Regardless where you are going to deploy AshLog, you will need to set some environment variables.

You can easily do that by creating a .env file with the following content:

```
DJANGO_SECRET_KEY=''
DJANGO_DEBUG='TRUE'
DJANGO_SETTINGS_MODULE='main.settings'
FIELD_ENCRYPTION_KEY=''
```

`DJANGO_SECRET_KEY` and `FIELD_ENCRYPTION_KEY` content should be two keys generated as follows:

```
# You can run the following command only inside the cloned repository
python manage.py shell
```

```python
from django.core.management.utils import get_random_secret_key

# Generate DJANGO_SECRET_KEY
get_random_secret_key()
```
```python
import os
import base64

new_key = base64.urlsafe_b64encode(os.urandom(32))

# Generate FIELD_ENCRYPTION_KEY
print(new_key)
```

## Deploy Locally

The first thing you need to do is cloning the git repository:

```
git clone https://github.com/ashlog-rest/ashlog
```

It is recommended to use a virtual environment, you can create is as follows:

```
python -m venv .venv \
source .venv/bin/activate
```

Install all the required dependencies:

```
pip install -r requirements.txt
```

And then run the development server:

```
pip manage.py runserver
```

You can now access the web dashboard on [http://localhost:8000](http://localhost:8000).

## Deploy Docker Container

The repository is provided with a Dockerfile that can be used to deploy AshLog in a container.

Once you have cloned the repository, you just need to run the following command:

```
docker-compose up --build
```

## Deploy on Heroku

The repository is provided with a Procfile and it is already set to be deployed on Heroku.

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/ashlog-rest/ashlog)