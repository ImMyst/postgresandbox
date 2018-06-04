# Challenges

Vous serez évalués sur la réalisation de ces challenges, qui doivent être disponible sur un repository github (un par équipe).

Votre code sera organisé de la façon suivant :

* Un dossier `/scripts` sera présent dans votre projet.
* Les resources supplémentaires (ex : fichiers SQL ou fichier de config), seront dans des sous-dossiers (ex : `/scripts/sql` ou `/scripts/config`).

## 1 - Script d'installation de PostgreSQL

Faire un script `setup_postgres` d'installation de PostgreSQL.

Il faut qu'à partir d'un système sans PostgreSQL on puisse lancer le script qui installera PostgreSQL complètement, sans aucune saisie utilisateur. À la fin le script afficha la version de `psql` pour valider l'installation.

* Plus d'infos sur [l'installation de PostgreSQL](/doc/setup.md)

## 2 - Créer l'utilisateur admin

Faire un script `create_admin_user`, qui à l'aide l'utilisateur postgres (`sudo -u postgres psql`) crééra un utilisateur **admin** avec le mot de passe **admin42**, qui est super admin.

Ce script doit aussi créer une base de données **admin** dont il est **owner** (c'est un droit spécial à donner pendant la création de la base de données).

Après l'exécution du script, on doit ensuite pouvoir se connecter à psql en tapant directement : `psql --username=admin --password`. Une modification du fichier `pg_hba.conf` est nécessaire pour permettre la connection.

Pour éviter de devoir saisir le mot de passe à chaque fois, on créera un fichier `.pgpass` dans le `home` de l'utilisateur unix en cours.

Les fichiers `pg_hba.conf` et `.pgpass` peuvent être crééer à la main (et pas obligatoirement dans le script), mais doivent être copiés dans le dossier `/scripts/config`.

* Plus d'infos sur [sur la configuration de PostgreSQL](/doc/configuration.md)
* Plus d'infos sur [la connexion en local](/doc/local_connection.md)
* Plus d'infos sur [l'utilisation de psql non interactif](/doc/psql.md)
* Plus d'infos sur [la syntaxe de CREATE ROLE](https://www.postgresql.org/docs/10/static/sql-createrole.html)
* Plus d'infos sur [la syntaxe de CREATE DATABASE](https://www.postgresql.org/docs/10/static/sql-createdatabase.html)

## 3 - Modifier la configuration de postgresql

Créer un script `set_configuration` qui va mettre à jour la `timezone` de PostgreSQL avec la timezone française et affiche la bonne heure à la fin du script. Il utilisera le nouvel utilisateur **admin**. Vous y mettrez tout changements futurs à la configuration de PostgreSQL.

* Plus d'infos sur [sur la configuration de PostgreSQL](/doc/configuration.md)
* Plus d'infos sur [la syntaxe de ALTER SYSTEM](https://www.postgresql.org/docs/10/static/sql-altersystem.html)

## 4 - Créer les tables du jeu de données "séries"

Analyser le contenu des différents fichiers CSV fournis (notament les headers des fichiers) et créer les tables qui correspondent dans une base de donnée `shows`. Les noms des tables et des colonnes **doivent être en anglais** et **en_minuscule_avec_des_underscore**. Vous devrez utiliser des types de données pertinents pour les différents champs et utiliser des clés étrangères pour les tables de jointure.

Le script devra s'appeler  `create_show_database` et créera toutes tables. Je vous conseille d'utiliser la syntaxe `psql -f un_fichier_sql.sql` avec un ou plusiers fichiers SQL que vous ajouterez dans `/scripts/sql`.

À la fin du script, les tables `show`, `episode`, `user` et deux tables de jointures (`episode_watch` et `episode_rating`) doivent être dans la base de données `shows`.

* Tutoriel sur [les types de données](http://www.postgresqltutorial.com/postgresql-data-types/)
* Tutoriel sur [la syntaxe CREATE TABLE](http://www.postgresqltutorial.com/postgresql-create-table/)
