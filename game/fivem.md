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

Change évidemment:
**mysqluser** Pour l'Utilisateur MySQL de ta base de donnée
**password** Pour le mot de passe de ta base de donnée
**database** Pour le nom de ta base de donnée