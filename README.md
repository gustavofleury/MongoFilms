Docker Django MongoDB
=============

## Run
```bash
$ git clone git@github.com:gustavofleury/MongoFilms.git
$ docker-compose up
```

Now you can access the Cinema Review Web application at <https://127.0.0.1:8000> 
and the  database Mongo Express at <https://127.0.0.1:8081>.
The MongoDB server is accessible at 127.0.0.1:27017.

A project to get you started with Docker and Django. This is made to
serve as an example for you to hack on, so I don't claim that this is the
correct way to setup a system with Django and Docker. Thus, I advice to also
look at other projects.

Stack and version numbers used:

| Name                  | Version  |
|-----------------------|----------|
| Django                | 2.2.11   |
| django-crispy-forms   | 1.9.0    |
| django-import-export  | 2.0.2    |
| djongo                | 1.3.1    |
| pymongo               | 3.10.1   |
| sqlparse              | 0.2.4    |



## Folder structure

```
/code# tree -L 1 --dirsfirst
.
├── CRUD
├── cinema_rating_review
├── homescreen
├── user
├── Dockerfile
├── README.md
├── docker-compose.yml
├── manage.py
└── requirements.txt
```

## Setting up

### Docker and Django
Example of [Docker-Compose with Django](https://docs.docker.com/compose/django/).

## Djongo
Example of configuration of Django to access MongoDB using [Djongo](https://djongo.readthedocs.io/docs/get-started/).

## Troubleshooting
Sometimes the Django/Djongo does not update the value of HOST and
always try to open the MongoDB server in the local host. To solve this problem is possible
create a TCP IP PORT FORWARD between the Django and MongoDB servers. For this
install SSH in Django Server and SSHD in MongoDB server. After setup the SSH server on
MongoDB container (hostname “mongo”), start the port forward with:

/code# ssh -L 127.0.0.1:27107:mongo:27107 mongo

