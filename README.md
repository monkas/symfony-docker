# symfony-docker-api

Ce projet contient un environnement Docker paramétré pour les projets Symfony avec les outils suivants
* php8.3
* mysql8.2
* nginx-alpine
* adminer

## Installation symfony et api-platform
À la racine du projet lancez les commandes suivantes :
* php /usr/local/bin/composer create-project symfony/skeleton app
* cd app
* php /usr/local/bin/composer req api
* cd ..
* sudo docker-compose build --no-cache
* sudo docker-compose up -d

## Accès à l'application
* Pour accèder à l'application : localhost:3000
* Pour accèder à l'api : localhost:3000/api
* Pour accèder à adminer : localhost:3001 les identifiants de connexion par default (A modifier) sont les suivants 
* * server : mysql
* * login : root
* * password : db_user_root_pass

## Personnalisation
Vous pouveVous pouvez personnaliser autant que vous le souhaitez les ports de sortie des différentes applications




