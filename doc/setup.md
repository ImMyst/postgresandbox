< [À propos de PostgreSQL](/doc/about.md) | [Configuration du serveur](/doc/configuration.md) >

# Installer PostgreSQL

Pour installer PostgreSQL sur n'importe quelle plateforme : [https://www.postgresql.org/download/](https://www.postgresql.org/download/).

## Installation sous Debian / Ubuntu

Il faut d'abord ajouter le dépot apt de PostgreSQL :

```bash
sudo vi /etc/apt/sources.list.d/pgdg.list
```

Ajouter la ligne :

```
deb http://apt.postgresql.org/pub/repos/apt/ stretch-pgdg main
```

Et fermer vim (`:wq`).

Ajoutez ensuite la clé pour accéder au dépot apt et installez PostgreSQL 10 :

```bash
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get install postgresql-10
```

Pour vérifier que PostgreSQL a bien été installé, tapez la commande `psql -V`, qui devrait afficher :

```bash
psql (PostgreSQL) 10.4 (Debian 10.4-2.pgdg90+1)
```

## Ça marche pas 😱

Si on essaye de se connecter à PostgreSQL, les accès sont très limités, par exemple en tapant `psql` vous risquez d'avoir l'erreur suivante :

```bash
psql: FATAL:  role "vagrant" does not exist
```

De même vous ne pouvez pas vous connecter au serveur à distance (avec pgAdmin par exemple), la raison est simple : à l'installation PostgreSQL n'est accessible qu'en local en utilisant l'utilisateur système `postgres` qui a été créé à l'installation. Cet utilisateur n'a pas de mot de passe on ne peut donc pas l'utiliser pour se connecter à distance. C'est un peu plus contraignant que **MySQL** qui propose un accès root sans mot de passe, mais ça force à penser d'abord à la sécurisation de la base de donnée.
