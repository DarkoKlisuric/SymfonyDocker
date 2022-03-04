## Symfony Docker

Repository for running Symfony 6+ into Docker.

### Installation
#### Clone the repository
```
git clone https://github.com/DarkoKlisuric/SymfonyDocker.git
```

#### Build docker images and run the containers
```
cd docker

docker-compose build

docker-compose up -d
```

#### Create .env file in application:
```
cd application

cp .env.example .env
```

#### Install packages inside backend container:
```
docker exec -it php bash

cd application

composer install
```

#### Open in browser
```
http://localhost:8080/
```

#### Database connection (after installing doctrine or something else)
````
Get IP of database container:

docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' database

-------------------------------------------------------------------------------------------------

In .env file paste ip of container with user and password from docker-compose:

DATABASE_URL=mysql://user:password@{IP-of-database-container}}:3306/app
````