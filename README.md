
# Atelier Symfony : Rédaction du README

Ce projet a pour objectif de créer une application Symfony pour la gestion d'un annuaire. Ce guide détaille les étapes nécessaires pour déployer et configurer le projet.

---

Étapes pour charger /node_modules
1. Installation des dépendances Node.js
Assurez-vous que node et npm ou yarn sont installés sur votre machine.

Installez les dépendances définies dans package.json :

bash
Copier le code
npm install
ou, si vous utilisez Yarn :

bash
Copier le code
yarn install
Cela générera automatiquement le dossier /node_modules dans votre projet.



## Installation des dépendances

Assurez-vous que toutes les dépendances nécessaires sont installées :

```bash
composer install



## Configuration de la base de données
Utilisation de MySQL
Modifiez le fichier .env.local pour définir les informations de connexion à votre base de données MySQL :

env
Copier le code
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

1. Générez une migration pour créer la table `personne` dans la base de données :

    ```bash
    symfony console make:migration
    symfony console doctrine:migrations:migrate
    ```

2. Validez le schéma de la base de données pour vérifier qu'il est conforme :

    ```bash
    symfony console doctrine:schema:validate
    ```
