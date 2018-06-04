< [Connexion en local](/doc/local_connection.md)

# psql

[Documentaton de psql](https://docs.postgresql.fr/10/app-psql.html)

psql est l'application en ligne de commande pour faire des requêtes à PostgreSQL. C'est un outil extrêmement puissant.

## Le mode interactif

Quand on tape juste `psql --username=nomuser` on entre en mode interractif. Chaque commande est entrée indépendament, on peut utiliser des commandes spécifiques à psql avec un `\` (par exemple `\q` pour quitter psql), ou écrire directement des commandes SQL, se terminant par un `;` pour être exécutées.

### Commandes psql utiles

* `\q` : quitter psql
* `\?` : obtenir de l'aide sur les commandes psql
* `\h` : obtenir de l'aide sur des opérations SQL
* `\d` : lister des métadonnées, par exemple : `\dt` pour lister les tables
* `\errverbose` : afficher la dernière erreur avec des détails

## Le mode non-interactif

On peut également lancer `psql` unitairement avec des commandes :

```bash
psql -c 'SELECT * FROM foo' -c 'SELECT * FROM bar'
```

Ou avec un fichier qui pourra contenir des commandes psql ou SQL :

```bash
psql -f fichier.sql
```
