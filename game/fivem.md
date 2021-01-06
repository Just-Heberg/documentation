# FiveM

## Configuration de base

Pour commencer, tu dois te rendre dans les paramètres de démarrage pour y remplir les cases suivantes:

<img src=https://just-heberg.fr/img/panel/8.png>

:::tip License FiveM
La lisence permet d'authentifier ton serveur auprès des services de FiveM, utile pour que ton serveur apparaise bien dans la liste officielle.
:::

:::tip Le Jeton d'Authentification
Le Jeton permet de communiquer comme la license, mais cette fois avec les services de Steam.
:::

:::tip Le nom du serveur
C'est le nom qui s'affichera dans la liste des serveurs
:::

:::warning Les Slots
Attention, la clé Patreon n'est pas incluse avec nos services, cependant nous ne définissons aucune limite des slots du côté serveur, si tu possèdes la clé Patreon de FiveM, tu peux l'utiliser avec nos serveurs pour lever la limite des 32 Slots.
:::

:::danger Ton serveur ne démarre pas ?
Veille à bien renseigner les informations ci-dessus! Sinon ton serveur refusera de démarrer et te montrera des crashs...
:::

## Connexion à la base de donnée

Elle te sera obligatoire pour pouvoir stocker les donnés de tes joueurs, rends-toi directement dans la section "Bases de données", crée cette dernière, cela devrait s'afficher comme ce qu'il suit:

<img src=https://just-heberg.fr/img/panel/9.png>

Pour pouvoir la relier avec ton serveur FiveM, il faudra créer un fichier *[libs]* dans le dossier resources à la racine du système de fichiers.

Cela doit ressembler à ça:
<img src=https://just-heberg.fr/img/panel/10.png>

:::warning Attention
Il peut arriver que ce dossier se crée tout seul, dans ses cas là ouvres-le simplement.
:::

Ensuite, ouvre le nouveau dossier *[libs]* que tu viens de créer, tu va devoir télécharger deux plugins.

[esplugin_mysql](https://github.com/kanersps/esplugin_mysql/archive/master.zip)
puis,
[mysql-async](https://github.com/brouznouf/fivem-mysql-async/archive/master.zip)

Il fois télécharger, extrais ces archives dans le dossier *[libs]*, cela doit ressembler à ça:

<img src=https://just-heberg.fr/img/panel/11.png>

Une fois installé, dans la racine de ton serveur, ouvre le fichier **server.cfg** et ajoute ses deux lignes de code:

```
set mysql_connection_string "server=192.168.1.67;uid=mysqluser;password=password;database=fivem"

start mysql-async
start esplugin_mysql
```

Il faut bien évidemment changer les variables ci-dessus par:  
**mysqluser**: l'Utilisateur MySQL  
**password**: Le mot de passe MySQL  
**fivem**: Le nom de la base de donnée

## Gestion de la base avec phpMyAdmin

Pour gérer ta base de donnée (Créer des tables, gérer, modifier) il faut se connecter à une interface d'administration permettant de gérer cette dernière.  

Connectes-toi au phpMyAdmin de Just-Heberg [en cliquant ici](https://mysql.just-heberg.fr/), sélectionne ensuite le **Serveur 5**, c'est le seul serveur qui héberge nos serveurs FiveM donc il est bien nécessaire de sélectionner celui-ci.  

Ensuite, met l'identifiant et le mot de passe de ta base de donnée, tout ceci est trouveable dans la section **Base de données** depuis le panel, on a vu ça dans l'article ci-desssus.  

**C'est fait!** Tu es maintenant connecté et tu peux désormais administrer ta base de donnée comme un pro.

## Réinitialiser mon serveur

Si tu souhaite recommencer ton serveur de zéro, en partant sur de bonnes bases, **éteins ton serveur au préalable**, il suffit ensuite d'accéder à la page "Gestion des Fichiers", sélectionne **tout**, clique ensuite sur le bouton "Action de masse" et sélectionne "Supprimer".

Une fois fait, dans le menu à gauche dans la catégorie "Configuration", clique sur le bouton "Mettre à jour" et confirmes.

Voilà! Ton serveur va s'installer et il sera tout neuf!

:::warning Sauvegarde!
Il est recommandé de sauvegarder ton serveur avant de réinitialiser ce dernier, toutes tes données sont définitivement suppimés après cette procédure. 
:::

## Problèmes connus

```
/entrypoint.sh: line 12: /home/container/alpine/opt/cfx-server/ld-musl-x86_64.so.1: Permission denied
```

Erreur assez courante, c'est lorsque le logiciel (FXServer) n'est pas mis à jour. Il suffit sur le panel, dans le menu de gauche dans la partie "Configuration" de cliquer sur le bouton "Mettre à jour", ton serveur va ensuite réinstaller les fichiers d'FXServer.

:::warning Sauvegardez votre serveur!
Cette action peux remplacer des fichiers par défaut que vous avez sûrement du déjà modifié, comme les fichiers de configuration, veillez bien à effectuer une sauvegarde de votre serveur avant de le mettre à jour.
:::