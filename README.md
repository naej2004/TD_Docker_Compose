# 🚀 Installation de WordPress avec Docker Compose

Ce projet a pour objectif de déployer un **blog WordPress** avec une base de données **MySQL**, le tout orchestré par **Docker Compose**.  
Il permet d’installer facilement et rapidement WordPress sur n’importe quelle machine sans configuration manuelle.

---

## 🧱 Technologies utilisées

- 🐳 **Docker** : Conteneurisation des services
- 📦 **Docker Compose** : Orchestration multi-conteneurs
- 📝 **WordPress** : CMS (Content Management System)
- 🛢️ **MySQL** : Système de gestion de base de données relationnelle

---

## 📂 Structure du projet

Le projet repose sur un seul fichier central : `docker-compose.yaml`.  
Ce fichier définit deux services **interconnectés** :

### 1. `db` – Service MySQL
- Utilise l'image officielle `mysql:latest`
- Conteneur nommé `td_mysql_docker`
- Stockage persistant grâce au volume `db_data`
- Variables d’environnement définies :
  - `MYSQL_ROOT_PASSWORD` : Mot de passe root
  - `MYSQL_DATABASE` : Nom de la base de données WordPress
  - `MYSQL_USER` / `MYSQL_PASSWORD` : Identifiants personnalisés pour WordPress

### 2. `wordpress` – Service WordPress
- Utilise l'image officielle `wordpress:latest`
- Conteneur nommé `td_wordpress_docker`
- Dépend du service `db` (grâce à `depends_on`)
- Accessible à l'adresse `http://localhost:8090` (port mappé)
- Variables d’environnement utilisées pour la connexion MySQL :
  - `WORDPRESS_DB_HOST`
  - `WORDPRESS_DB_USER`
  - `WORDPRESS_DB_PASSWORD`
  - `WORDPRESS_DB_NAME`

---

## 🔧 Étapes d'installation

> Avant de commencer, assurez-vous que **Docker** est bien installé sur votre machine.

**Cloner le projet** :
  - Lancer un terminal
  - git clone https://github.com/naej2004/TD_Docker_Compose.git
  - cd TD_Docker_Compose
  - cd wordpress-docker
  - docker compose up -d