# Django Lab

This is a project that creates a simple dockerized web application using Django, Gunicorn, Nginx and Postgres as microservices.

## Installation

1. To run the app clone the repository into the host machine/VM and run the following command:

    $ docker-compose up -d --build

2. Docker-compose creates 3 docker containers on a custom bridge network:
    - The web app served with Gunicorn internally on port 8000
    - Nginx that exposes the web app on port 8001
    - Postgres database on the default port to store our web app information

3. To make the web app fully functional we need to migrate the DB to postgres using the following command:

    $ docker-compose exec web python manage.py migrate --noinput

4. The web app is up and running. To see the app go to http://localhost:8001