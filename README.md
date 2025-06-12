# Installation de WordPress avec Docker Compose

Ce projet déploie un blog WordPress avec sa base de données MySQL, via Docker Compose.

## Services utilisés

- WordPress (CMS)
- MySQL (Base de données)

## Étapes

1. Clonez le projet
2. Lancez `docker-compose up -d`
3. Accédez à `http://localhost:8080`

## Fichier docker-compose.yaml

Il contient deux services :
- `db` : base de données MySQL
- `wordpress` : application WordPress connectée à la BDD

## Auteur

KOUASSI KOUAME JEAN-ELIE