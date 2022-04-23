# Django Polling App

This application is using docker-compose to deploy 3 primary components
- webapp
- Postgres db
- Postgres admin IDE

## Django web application
This app uses Django 4

docs: https://docs.djangoproject.com/en/4.0/

### Setup
python 3 is required (3.8+)

#### install pip (pip3 on linux)
_linux_
```
sudo apt-get install pip3
```
#### install required packages
```
pip3 install -r requirements.txt
```
#### launch containers and application
```
docker-compose up
```
Include the `-d` flag with your docker-compose command to run the containers headless.

The Django application will be hosted at `http://localhost:8000`

The Django admin interface will be hosted at: `http://localhost:8000/admin`

The default username/password for the admin interface will be `admin`/`admin`.

## Postgres database
The postgres database is hosted in a docker container on the default port `5432`.

The default database name, username, and password will be `postgres`.

### Installing the CLI to access posgres 

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

_NOTE_: If you need to restart your containers, you will see cert errors in the IDE logs if a browser tab is left open. Close browser tags and log in whenever the container is restarted.

