< [Index](/README.md) | [Installer PostgreSQL](/doc/setup.md) >

# À propos de PostgreSQL

PostgreSQL est un SGBD (système de gestion de base de données) relationnelle.

Le principal atout de PostgreSQL est d'être **open source** tout en pouvant rivaliser avec les grosses bases de données propriétaires (Oracle, Microsoft SQL Server, IBM DB2 etc.).

## Historique

* 1974 : création d'[Ingres](https://fr.wikipedia.org/wiki/Ingres_(base_de_donn%C3%A9es)) par [Michael Stonebraker](https://fr.wikipedia.org/wiki/Michael_Stonebraker)
* 1985 : réécriture d'Ingres à partir de zéro, changement de nom pour **Postgres** (post-ingress).
* 1995 : ajout des fonctionnalités SQL, changement de nom pour **Postgres95**.
* 1996 : changement de nom pour **PostgreSQL**
* 1997 : première version formelle : **PostgreSQL 6**
* 2017, octobre : **PostgreSQL 10**, version utilisée pour ce cours
* 2018, mai : première beta **PostgreSQL 11**

[Histoire sur la page Wikipédia de PostgreSQL](https://fr.wikipedia.org/wiki/PostgreSQL#Histoire)

## Points forts

PostgreSQL est orientée **applicatif**, elle ne se contente pas de stocker des données mais peut être une application à part entière. Pour écrire du code applicatif on dispose d'un vaste choix de langages (PL/pgSQL, JavaScript, python, perl etc.).

PostgreSQL est **extensible**. Tout dans PostgresSQL peut être personalisé avec vos propres types de données, opérateurs etc.

PostgreSQL est facilement **connectable** à n'importe quelle téchnologie : PHP (pdo_pgsql), Java JDBC, Python, Node, .Net, Excel (!) etc.

PostgreSQL peut même dépasser le modèle relationnel et propose aussi quelques fonctionnalités **NoSQL** : des graphes avec `ltree` (comme Neo4j), du clé/valeur avec `hstore` (comme Redis) et du document store avec `JSONB` (comme mongodb).

## Pourquoi pas ?

Si PostgreSQL est si bien que ça, pourquoi n'est-elle pas plus utilisée ?

**MySQL** est souvent utilisée dans les projets parce que généralement associé aux technologies web (le couple PHP/MySQL est très standard). **MySQL** est également un peu plus simple à mettre en place et le grand nombre de fonctionalités avancées de PostgreSQL peut décourager. **Ça ne veut pas dire qu'on ne devrait pas utiliser PostgreSQL à la place de MySQL, même dans les projets simples.**

On préfera aussi une base de données légères comme **sqlite** quand il s'agit d'embarquer une base de donnée dans une application (typiquement les applications mobiles).
