# Django Polling App

This application is using docker-compose to deploy 3 primary components
- [webapp](#django-web-application)
- [Postgres db](#postgres-database)
- [Postgres admin IDE](#postgres-admin-ide-pgadmin)

## Django web application
This app uses Django 4

docs: https://docs.djangoproject.com/en/4.0/

### Setup
python 3 is required (3.8+)

#### install pip (pip3 on linux)
_linux_
```bash
sudo apt-get install pip3
```
#### install required packages
```bash
pip3 install -r requirements.txt
```
#### launch containers and application
```bash
docker-compose up
```
Include the `-d` flag with your docker-compose command to run the containers headless.

The Django application will be hosted at `http://localhost:8000`

The Django admin interface will be hosted at: `http://localhost:8000/admin`

The default username/password for the admin interface will be `admin`/`admin`.

### Running tests
I like to connect to the docker container and run tests from there.
```bash
docker exec -it <containerId> /bin/bash
python manage.py test polls
```

### Seeing test coverage
This application uses the `coverage` utility. For getting test coverage for our polls app:

```bash
coverage run --source='.' manage.py test polls
coverage report
```

The above will run all the `tests_*.py` files in the `polls` app.
## Postgres database
The postgres database is hosted in a docker container on the default port `5432`.

The default database name, username, and password will be `postgres`.

### Installing the CLI to access Postgres 

_linux_

```bash
$ sudo apt-get install postgresql
```

## Postgres Admin IDE (pgAdmin)

This application also sets up a handy Postgres GUI admin tool.

docs: https://www.pgadmin.org/

default username: `admin@admin.com`

default password: `root`

### use the IDE
browse to `http://localhost:5050`

_NOTE_: If you need to restart your containers, you will see cert errors in the IDE logs if a browser tab is left open. Close browser tabs and log in whenever the container is restarted.

