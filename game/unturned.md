# Unturned
## Configurer mon serveur
Il n'y a besoin que d'un seul fichier!

Sur la page **Gestion des Fichiers** va vers le chemin **/home/container/Servers/Default/Server** et édites le fichier **Commands.dat**

**chatrate** (Temps en seconde que le joueur doit attendre avant de renvoyer un message dans le chat) ex: chatrate 5

**cycle** (Temps en seconde du cycle jour/nuit) ex: cycle 3600

**decay** (Le temps qu'un joueur peux rester hors-ligne en secondes avant que ses structures peuvent être retiré par n'ymporte qui, par défaut c'est 7 Jours) ex: decay 604800

**gold** (Permet d'autoriser le serveur qu'au membres gold)

**map** (Le nom de la map) ex: map pei

**maxplayers** (Le nombre maximum que le serveur peux accueillir) ex: maxplayers 4

**mode** (Choisis le mode de difficulté du serveur Easy/Normal/Hard) ex: mode Normal

**owner** (Choisis le propriétaire du serveur, à renseigner avec le STEAMID64) ex: owner 76561198146366026

**admin** (Ajoute les administrateurs à votre serveur, à renseigner avec le STEAMID64) ex admin 76561198146366026

**password** (Met un mot de passe pour se connecter au serveur) ex: password patate

**perspective** (Choisis le mode de perspective du serveur First/Third/Vehicle/Both) ex perspective Both

**pve** (Désactive le PvP sur votre serveur)

**pvp** (Force le PvP sur votre serveur)

**welcome** (Choisis le message de bienvenue du serveur) ex: welcome Bonjour et bienvenue sur notre serveur!

**name** (Définis le nom de votre serveur) ex:name LeServPvP

**cheats enabled** (Active les cheats lorsque cette ligne est ajoutée)

## Ajouter des addons du Workshop

Sur la page **Gestion des Fichiers** va vers le chemin **/home/container/Servers/Default** et édites le fichier **WorkshopDownloadConfig.json**

Le fichier se présente ainsi:
``` json
"File_UDs": [],
```

Il te suffit d'inscrire l'ID des addons, ou des collections que tu souhaites ajouter à ton serveur, les joueurs qui rejoindrons les téléchargerons automatiquement, l'ID d'un addon se trouve a la fin de son URL: **?id=000000**

Il faut que tu ajoutes les IDs comme ceci:

``` json
"File_IDs": [000000,1234567,1234567,7654321],
```

Enregistre, redémarre ton serveur, c'est carré!

## Ajouter une icône, un nom, une description

Même chose que ci-dessus, sur la page **Gestion des Fichiers** va vers le chemin **/home/container/Servers/Default** et édites le fichier **Config.json**

Dans le fichier, diriges toi vers la catégorie **Browser**

``` json
"Icon": "https://votre.url.vers.une.image.en.png",
"Desc_Hint": "Salut!",
"Desc_Full": "Salut et bienvenue sur notre serveur, vous trouverez ça, et puis ça, et encore ça...",
"Desc_Server_List": "C'est une description qui apparaitera sur la liste des serveurs",
```

:::warning Attention!
L'icône de l'image en .png doit être en 500x500!
:::

:::tip Comment mettre mon image dans un lien ?
L'icône doit forcément être en HTTP(s), tu dois héberger ton icône dans un hébergeur d'images du type [imgur.com](https://imgur.com/), une fois ça fait fais clique droit, et copie l'URL de ton image!
:::