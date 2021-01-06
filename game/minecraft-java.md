# Minecraft: JAVA

## Informations

Par défaut, l'ensemble de nos serveurs minecraft sont pré-configurés sur la dernière version de Minecraft avec l'API de PaperSpigot. Donc, par défaut, ton serveur pourra accepter des plugins et fonctionnera sur la dernière version.

## Changer de version

Premièrement, tu peux choisir ta version parmi notre liste disponible dans la page **Plugins** du Panel.

Dans l'onglet version, il s'affiche ce qu'il suit:

<img src="https://just-heberg.fr/img/panel/5.png">

Installe la version que tu souhaite en cliquant sur le bouton vert à droit de la version.

:::warning Lis-bien la description!
Par exemple, je souhaite installer la version Spigot 1.14.4, la description précise "Mettre "spigot-1.14.4.jar" dans paramètres de démarrage.", alors je procèdes comme ce qu'il suit:
:::

Dans paramètres de démarrage:

<img src="https://just-heberg.fr/img/panel/7.png">

Spécifie ce que la description te demandes de faire et remplis ça dans la case ci-dessus, ensuite, clique sur confirmer les changements et redémarre ton serveur.

## Configurer son serveur

Pour configurer son serveur, il est nécessaire d'ouvrir le fichier **server.properties** présent dans la racine de votre serveur, tu peux modifier le fichier directement dans le menu **Gestion des Fichiers**:

Remplace évidemment le texte en vert par **true** pour activé ou **false** pour désactivé, ou par un chiffre si précisé.

``` properties
spawn-protection: C'est le rayon de blocs protégés, du spawn par défaut de votre map.
allow-nether: Autorise le nether sur votre serveur.
gamemode: Le mode de jeu par défaut de votre serveur. 0=Survie, 1=Créatif
difficulty: Le niveau de difficulté général de votre serveur. 1=Facile, 2=Normal, 3=Difficile
spawn-monsters: Décidez si les monstres (hostiles) spawn sur votre serveur.
pvp: Décidez si les joueurs peuvent se combattre entre eux.
hardcore: Décidez si le mode hardcore est activé sur votre serveur (pas de regénération de coeurs hors potions)
enable-command-block: Décidez si les command block sont activés sur votre serveur.
max-players: Le nombre de joueurs maximum sur votre serveur.
allow-flight: Décidez si les joueurs peuvent voler, même en étant en Gamemode 0
spawn-animals: Décidez si les animaux peuvent spawn ou non sur votre serveur.
generate-structures: Décidez si les structures peuvent être générés sur votre map (Temples, Villages PNJ)
online-mode: Décidez si votre serveur communique avec ceux de Mojang (Désactiver pour autoriser les cracks)
motd: Spécifiez le petit message affiché dans la liste des serveurs.
```

:::tip Comment ajouter un icône ?
Dans la racine de ton serveur, upload ton image en .png, elle doit avoir une résolution de 64x64 et devra s'appeler server-icon.png, redémarre ton serveur ensuite et l'icône devrait apparaitre
:::

:::tip Comment mettre des plugins ?
Recherche sur Google le nom du plugin que tu souhaite, ou un site en regroupant quelques-un et télécharge-le. Vérifie bien si le plugin est compatible avec la version de ton serveur. Ensuite, upload le fichier .jar que tu viens de télécharger dans le dossier plugins de ton serveur.
:::

## Optimiser mon serveur

Minecraft est encore un jeu en développement et son manque d'optimisation fait souffrir beaucoup de serveurs et de joueurs.

:::danger Attention aux versions entre 1.13 inclus et 1.14.4
Ces versions ont des problèmes au niveau du chargement des chunks, ce qui monte considérablement le TPS de ton serveur! Change rapidement dans une version ultérieure type 1.12.2 ou simplement la dernière version.
:::

:::warning Vérifie ta map
Certaines vieilles maps qui ont traversés plusieurs versions du jeu peuvent avoir des chunks corrompus, ce qui rend le travail incalculable.
:::

:::tip Utilise Spigot
Craftbukkit est une version complètement obscelète pour créer des serveurs, préfère Spigot ou encore mieux, PaperMC/PaperSpigot
:::

:::tip Pré-génère ta map!
Pour le serveurs openworld (Survival, etc), pré-générer ta map est le plus important pour éliminer le lag. La génération des chunks et l'une des charges les plus lourdes.
:::

Pour pré-générer ta map, utilise le plugin gratuit "WorldBorder"

Va dans le spawn de ta map, et prend les coordonés X et Z.

**/worldborder X Z** pour placer le centre du monde

**/worldborder set ?** et remplace le "?" par le nombre de blocs ou tu veux placer ta limite

**/wb fill** pour charger l'ensemble des chunks présent dans la limite, cela risque de prendre beaucoup de temps et fera lagger ton serveur, c'est un mal pour un bien!

**Configuration de bukkit.yml**

**spawn-limits**

Défaut: monsters:70, animals:15, water-animals:15, ambient:15

Optimisé: monsters:55, animals:12, water-animals:12, ambient:3

Impact: Modéré

Les chiffres indiques les "mobs par joueur", un chiffre plus bas résulte un taux de spawn beaucoup plus bas. Prenez en compte que ce changement sera visible et fera une réduction significative du taux de spawn des mobs.


**chunk-gc**

Défaut: period-in-ticks:600, load-threshold:0

Optimisé: period-in-ticks:400, load-threshold:300

Impact: Modéré-Mineur

Cela dé-charge les chunks d'une valeur plus rapide que Minecraft Vanilla.

**ticks-per.monster-spawns**

Défaut: 1

Optimisé: 2

Impact: Modéré

Cela fait en sorte que (en ticks) le serveur va essayer de faire spawn des mobs à une location dite "légale". En doublant ce paramètres, on double le temps entre chaque vérification, ce qui peux aider.

*Note: Modifiez seulement entre 3 et 5 si vous avez une sévère baisse de TPS.*

**Configuration de spigot.yml**

**save-user-cache-on-stop-only**

Défaut: false

Optimisé: true

Impact: Situationnel

Cela active l'option que les données de vos joueurs ne seront sauvegardés uniquement en cas de redémarrage, ou d'arrêt de votre serveur.

**mob-spawn-range**

Défaut: 8

Optimisé: 6

Impact:n Mineur

Cela définit le rayon maximal à laquelle les mobs peuvent spawner (en chunks) depuis un joueur. Essayez de régler cet option en fonction de votre "view-distance".

**merge-radius**

Défaut: item:2.5, exp:3.0

Optimisé: item:4.0, exp:6.0

Impact: Moyen-Elevé

Cela modifie la distance à laquelle les objets drop et les boules d'XP se fusionnent entre eux.

**nerf-spawner-mobs**

Défaut: false

Optimisé: true

Impact: Moyen-Elevé

Quand activé, les mobs spawnés par les mob-spawners n'ont pas d'IA (ils ne bougerons pas, n'attaquerons pas), il s'activerons uniquement en cas d'approche.

**item-despawn-rate**

Défaut: 6000 (cinq minutes)

Optimisé: plus bas ?

Impact: Mineur-Moyen

L'intervalle (en ticks) que le serveur doit attendre avant de faire despawn les items parterre.

**arrow-despawn-rate**

Défaut: 1200

Optimisé: 300

Impact: Mineur

Pareil pour l'item-despawn-rate. Mais seulement sur les flèches

**Configuration de paper.yml** *(Uniquement lors de l'utilisation de PaperMC/PaperSpigot)*

**max-auto-save-chunks-per-tick**

Défaut: 24

Optimisé: 6 (ou >6 si vous voulez)

Impact: Elevé

L'intervalle ou les chunks vont se faire sauvegarder. Très important en 1.14 tellement cette version est mal optimisé au niveau des chunks.

**optimise-explosions**

Défaut: false

Optimisé: true

Impact: Mineur

Paper appliquera un algorithme plus performant pour gérer les explosions.

**mob-spawner-tick-rate**

Défaut: 1

Optimisé: 2

Impact: Mineur

Le délai en ticks avant qu'un mob-spawner essayera de faire spawn ses mobs.

**disable-chest-cat-detection**

Défaut: false

Optimisé: true

Impact: Mineur

Par défaut, les chats/ocelots, portent des coffres, une sorte d'inventaire, mais cette mécanique n'est plus utilisé.

**fire-physics-event-for-redstone**

Défaut: true

Optimisé: false

Impact: Mineur

Cela stoppe les constructions resdstone active par l'activation d'un "BlockPhysicsEvent". Les nouveaux builds désactivent cet option automatiquement car certains plugins peuvent mal fonctionner (super rare)

**max-entity-collisions**

Défaut: 8

Optimisé: 2

Impact: Mineur

Les entités vont moins entrer en collision et moins consommer en ressources.

**grass-spread-tick-rate**

Défaut: 1

Optimisé: entre 2 et 4

Impact: Moyen

Le temps ( en ticks ) avant que le serveur n'essayera de propager l'herbe dans les chunks chargés.

**hopper.disable-more-event**

Défaut: false

Optimisé: true

Impact: Elevé (Situationnel)

Cela va significativement réduire les lag des hoopers en anticipant "InventoryMoveItemEvent" qui est appelé sur CHAQUE slots dans le hooper. Peux être incompatible avec certains plugins.

**non-player-arrow-despawn-rate**

Défaut: -1

Optimisé: 60 (3 secondes)

Impact: Mineur

Avec ses propriétés, les flèches qui ne peuvent pas être récupéré par le joueur, sera despawn presque immédiatement.

**creative-arrow-despawn-rate**

Défaut: -1

Optimisé: 60

Impact: Mineur

Pareil que la propriété au dessus, sauf que l'on peux récupérer les flèches lancées par un joueur en créatif.

**keep-spawn-loaded**

Défaut: false (true sur les builds récent)

Optimisé: true

Impact: Moyen (Situationnel)

Cela garde votre spawn chargé même si aucun joueur n'est à l'intérieur, cela peux prévenir d'un léger freeze lorsqu'un joueur ce téléporte au spawn.

**prevent-moving-into-unloaded-chunks**

Défaut: false

Optimisé: true

Impact: Moyen-Elevé

Préviens le serveur quand un joueur va entrer dans un chunk déchargé.

**use-faster-eigencraft-redstone**

Défaut: false

Optimisé: true

Impact: Elevé

Ce paramètres élimine les updates de redstone redondantes.

**anti-xray.enabled**

Défaut: false

Optimisé: true, engine-mode: 2

Impact: N/A

Cela optimise le système d'anti-xray.

**Configuration du server.properties**

**view-distance**

Défaut: 10

Optimisé: 4-8

Impact: Très Elevé

Empêche un joueur de charger beaucoup trop de chunks, attention un paramètres bas réduira votre visibilité dans la map. La distance de chargement sera bas.