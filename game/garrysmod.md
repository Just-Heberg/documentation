# Garry's Mod

## Configuration de base

Diriges-toi dans les fichiers de ton serveur dans le répertoire **garrysmod/cfg** et édites le fichier **server.cfg**, à ce fichiers nous rajouterons les lignes suivantes:

``` cfg
hostname "Nom de votre serveur"
sv_password "mot de passe"
sv_loadingurl "https://chargement.org/"
sv_allowupload 0/1
sbox_maxprops 150
```

Les lignes les plus importantes sont pré-écrites dans le fichier, libre à toi de les modifier!

:::tip Pas de mot de passe ?
Si tu ne souhaites pas de mot de passe pour te connecter à ton serveur, supprime simplement la ligne correspondante!
:::

:::tip sbox_maxprops 150
Le dernier chiffre comme son nom l'indique, définit nativement la limite maximale de props que le serveur encaissera.
:::

:::warning allowupload ?
Il est recommandé de mettre 0, cette ligne permet d'autoriser les clients (joueurs) à uploader des informations sur ton serveur, comme les sprays par exemple, c'est recommandé de désactiver pour des raisons de sécurité!
:::

## Changer le nom du gamemode

Lorsque tu développera ton serveur, tu aimerais faire un PrisonRP ou un SCP-RP, bref, un autre mode de jeu mais basé sur DarkRP mais dans une autre catégorie.

Le procédé est simple à suivre, diriges-toi vers ton gamemode **garrysmod/gamemodes/darkrp/** dans la racine de ton gamemode, édites le fichier **darkrp.txt** et édites la catégorie **Title**, remplace DarkRP par le nom du mode de jeu que tu souhaites.

## Télécharger la collection lors de la connexion

Diriges-toi vers le dossier **garrysmod/lua/autorun/server** et créer le fichier **workshop.lua**, va ensuite jeter un coup d'oeil sur ta collection steam, et à la fin de l'URL de cette dernière, tu trouvera les chiffres suivant par exemple: **id?=8484986**, copie cette suite de chiffre et ajoute dans le fichier **workshop.lua**:

``` lua
resource.AddWorkshop("8484986")
```

Remplace évidemment **8484986** par la suite de chiffre de ta collection, tu peux rajouter plusieurs lignes comme celle-ci pour ajouter d'autres collection, ça marche aussi avec un addon!

## Libérer de l'espace disque

Qu'est-ce que c'est frustrant de ne pas pouvoir démarrer son serveur quand il manque de l'espace disque... on te propose une solution pour ça!

Va dans les fichiers de ton serveur, à la racine, supprime les fichiers s'appellant **core**, puis supprime le dossier **steam_cache**

Va ensuite dans le dossier **garrysmod** et supprime le dossier **cache**

Démarre maintenant ton serveur, ne t'inquiètes pas il retéléchargera l'ensemble des addons, et te voilà avec plus d'espace disponible!

## Optimiser mon serveur

Il est recommandé d'ajouter quelques addons à ta collection, cela te permettera d'optimiser ton serveur et de le rendre un peu plus fluide et moins gourmand en ressources.

[Optimiseur de réseau pour sièges](https://steamcommunity.com/sharedfiles/filedetails/?id=622814666&) Ce script te servira à optimiser automatiquement tout les "sièges" de ton serveur, que ce soit un véhicule ou une simple chaise, très utile pour les serveurs DarkRP contenant beaucoup de véhicules

[Widgets Disabler](https://steamcommunity.com/sharedfiles/filedetails/?id=793317003) Ce script désactive certaines choses intuiles (vraiment)

[Bucket's Optimisation V2](https://steamcommunity.com/sharedfiles/filedetails/?id=1620875048) Cet addon servira non seulement à optimiser le client (Les FPS de tes joueurs), mais aussi ton serveur!

## Protéger mon serveur des hackers

:::danger Les leaks!
C'est primordial avant de continuer ce tutoriel, évite vraiment les leaks car ils contiennent des backdoors (portes ouvertes) que les hackers peuvent utiliser pour pénétrer dans ton serveur!
:::

Modifie ton **server.cfg** qui ce situe dans le dossier **garrysmod/cfg** et ajoute ces lignes:

``` cfg
sv_allowupload 0
sv_allowdownload 0
sv_allowcslua 0
```

Ensuite, édites le fichiers **settings.lua** qui se situe dans le dossier **addons/darkrpmodification/lua/darkrp_config** et remplace la ligne suivante:

``` lua
GM.Config.disallowClientsideScripts = true
```

Il est également recommandé d'ajouter [SNTE](https://steamcommunity.com/sharedfiles/filedetails/?id=1308262997) à ta collection!

Pour limiter la casse, il n'est pas déconseillé d'acheter un anti-cheat sur gmodstore.

:::warning Les addons du Workshop
Certains addons du workshop peuvent contenir des backdoors (oui oui), vérifie souvent les commentaires des addons sur le steam workshop des addons que tu ajoutes à la collection de ton serveur!
:::