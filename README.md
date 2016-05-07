# django-compose

You'll need to create a data volume for postgres:

    mkdir data
    docker create -v /data --name pgdata ubuntu

You can then start up all the containers with:

    docker-compose up -d --build

Your first time running Django you will need to create a super user.  Start with opening a shell to it

    docker exec -it djangocompose_web_1 bash

Then run

    python manage.py createsuperuser

 When ever the database needs to be migrated (including the first run).  Open and shell and run:

    python manage.py migrate