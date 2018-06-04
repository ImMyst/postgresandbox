# Challenges

## 1 - Script de setup de PostgreSQL

Faire un script de setup de PostgreSQL. À partir d'un système vide (Debian), doit installer PostgreSQL complétement, sans interaction et affiche la version de psql à la fin du script.

## 2 - Créer l'utilisateur admin

Faire un script `create_admin_user`, qui se lance avec l'utilisateur postgres (sudo -u postgres psql), qui créé un utilisateur "admin" avec le mot de passe "admin42", qui est super admin.

Créer une base de donnée "admin", dont il est "owner".

Il faut pouvoir se connecter à psql avec la commande `psql --username=admin --password`.
