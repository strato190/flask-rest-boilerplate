# Gotham

Gotham is boilerplate to build RESTful applications.

> This is a end result of building REST APIs with Python for over 4 years. I've
tried to combine all best practices and use all the good things Flask and Flask
community offers

## Structure
This boilerplate is built with API First development principles in mind. Gotham 
is a [Connexion](https://github.com/zalando/connexion) application that uses 
awesome [Swagger](https://swagger.io/specification/) to easily define and 
document API, and provides a layer between API definition and implementation.
Connexion uses Flask as an engine, so, in theory this is actually a Flask app,
and supports all plugins available for Flask.

### Python version
**Python 3.5.x**

### Components
- Flask-SQLAlchemy - ORM
- Flask-Marshmallow - Serialize DB models into json
- Flask-Script - For local development
- Py.test - for testing

## Using boilerplate
To use it in your project, simple clone repo, change git origin, and rename it 
to desirable project name:

```bash
git clone git@github.com:AnteTechnologies/gotham.git <your-project-name>
git remote set-url origin <git-url-of-new-project-repo>
```

>Note: there are some components that named `gotham`. Ultimately rename them too,
for example: database name, swagger api.yaml title etc. 


## How to run
To run project locally, assuming you have virtualenv and virtualenvwrapper

```bash
mkvirtualenv gotham
pip install -r requirements.txt
python manage.py runserver
```

Also, boilerplate includes all necessary Docker configuration to run it locally,
and also in production environment. To run it with Docker:

```base
docker volume create postgres_data
docker-compose up
```

This will pull and start Postgres container for database, and start current state of
application in separate container and application will be available at 
[localhost:8090](http://localhost:8090)

## Testing
Py.test is used for testing instead of default testing library. To run tests

```bash
py.test
```

To run with coverage
```bash
py.test --cov=app
```
