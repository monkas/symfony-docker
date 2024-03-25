# symfony-docker-api

Ce projet contient un environnement Docker paramétré pour les projets Symfony avec les outils suivants
* php8.3
* mariadb
* nginx-alpine
* redis
* adminer

## Création .env file
* Créez un fichier .env à la racine du projet
* Copiez l'ensemble des paramètres présents dans .env.dist dans votre fichier .env et adaptez ces paramètres selon vos besoins

## Installation symfony et api-platform
Si symfony est déjà présent dans le projet passez à l'étape suivante, sinon à la racine du projet lancez les commandes ci-dessous :
* php /usr/local/bin/composer create-project symfony/skeleton app
* cd app
* php /usr/local/bin/composer req api

## Installation environnement docker (php, mariadb, nginx, adminer, redis)
Vérifiez dans un premier temps que les ports utilisés par les différents outils de développement sont disponibles, ensuite à la racine du projet lancez les commandes suivantes :
* sudo docker compose build --no-cache
* sudo docker compose up -d

## Accès à l'application
* Pour accèder à l'application : http://localhost
* Pour accèder à l'api : http://localhost/api
* Pour accèder à adminer : http://localhost:8080




