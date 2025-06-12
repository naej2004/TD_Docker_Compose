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
- Accessible à l'adresse `http://localhost:8090:80` (port mappé)
- Variables d’environnement utilisées pour la connexion MySQL :
  - `WORDPRESS_DB_HOST`
  - `WORDPRESS_DB_USER`
  - `WORDPRESS_DB_PASSWORD`
  - `WORDPRESS_DB_NAME`

---

## 🔧 Étapes d'installation

> Avant de commencer, assurez-vous que **Docker** est bien installé sur votre machine et lancer un terminal.

### 1. Cloner le projet

- git clone https://github.com/naej2004/TD_Docker_Compose.git
- cd TD_Docker_Compose
- cd wordpress-docker

### 2. Démarrer les services

docker compose up -d

### 3. Accéder à WordPress

Ouvrir votre navigateur et aller à : http://localhost:8090

### 4. Configurer WordPress

Complétez les informations demandées (titre du site, identifiants, etc.).
Votre blog est prêt à l’usage ! 🎉

## 🧪 Vérifications

> Assurez-vous qu'un terminal est lancé et que vous êtes dans le dossier wordpress-docker

- Vérifiez que les deux conteneurs tournent : docker ps
- Pour arrêter les conteneurs : docker compose down

## 📁 Comment fonctionne le volume ?

Le volume db_data permet de conserver les données de la base MySQL, même si vous redémarrez ou supprimez les conteneurs.
Cela évite de perdre vos données entre deux utilisations du projet.

## 👨🏽‍💻 Auteur

- **KOUASSI KOUAME JEAN-ELIE**
- Étudiant en Réseaux et Génie Logiciel à Pigier Côte d'Ivoire
- Passionné par **l’automatisation, les systèmes embarqués et la robotique**

## 📎 Liens utiles

- Documentation officielle Docker (https://docs.docker.com/)
- Docker Compose - WordPress Example (https://hub.docker.com/_/wordpress)
- MySQL Docker Hub (https://hub.docker.com/_/mysql)
