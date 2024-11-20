
# Atelier Symfony : Rédaction du README

Ce projet a pour objectif de créer une application Symfony pour la gestion d'un annuaire. Ce guide détaille les étapes nécessaires pour déployer et configurer le projet.

# Installation des dépendances PHP
composer install

# Installation des dépendances Node.js
npm install # ou yarn install

# Installation des assets publics
symfony console assets:install

# Nettoyage et régénération du cache
symfony console cache:clear



## Configuration de la base de données
Utilisation de MySQL
Modifiez le fichier .env.local pour définir les informations de connexion à votre base de données MySQL :

env

DATABASE_URL="mysql://db_user:db_password@127.0.0.1:3306/gestion-conges"
Vérifiez si MySQL est installé sur votre machine (Windows) :

bash
Copier le code
mysql --version
Créez la base de données avec la commande suivante :

bash
Copier le code
symfony console doctrine:database:create
Vérifiez que la base de données est bien créée et qu'il n'y a pas d'erreurs.


## Vérification

1. Initialisez la base de données si nécessaire :

bash
 symfony console doctrine:database:create
symfony console doctrine:migrations:generate
 symfony console doctrine:migrations:migrate
 
Validez le schéma de la base de données avec la commande suivante :

symfony console doctrine:schema:validate


Si vous souhaitez repartir sur une base propre, supprimez-la avant de la recréer :

Supprimez la base :
bash

symfony console doctrine:database:drop --force

2. Validez le schéma de la base de données pour vérifier qu'il est conforme :

   bash
    symfony console doctrine:schema:validate
   
