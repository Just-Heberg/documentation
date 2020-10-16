# Informations

Notre système NodeJS fonctionne à l'aide d'un docker sous alpine, qui lance une instance de nodejs. C'est à toi d'installer ton propre bot, le conteneur démarrera sur **index.js**

En théorie, lorsque tu développera ton bot ou ton script, la structure des fichiers est **strictement** la même de Windows à Linux, tu peux directement tout uploader sur le serveur.

## Connexion à MySQL

Il est possible de connecter ton bot avec une base de donnée, il est important de te procurer des modules nécessaires.

Dans l'hôte, met l'adresse fournie par le panel lors de la création de ta base de donnée, dans l'onglet **Hôte MySQL**.

:::warning Attention
Ne cofonds pas l'hôte et le port, le panel te montrera par exemple 192.168.1.34:3306, garde uniquement les chiffres avant les "**:**" si tu souhaites uniquement mettre l'adresse-ip.
:::

Exemple d'une configuration:
``` js
host: 192.168.1.34
port: 3306
user: u209_DjaudNS625
password: ********
database: u209_Madatabase
```

## Pourquoi "Démarrage" à l'infini ?

Si ton bot ou ton script affiche "Démarrage" à l'infini dans son statut, c'est qu'il faut que tu dises au panel quand ton script à fini de s'initialiser!

A la toute fin de ton code, généralement dans **l'index.js**, il faut faire apparaitre le mot clé **Started** dans la console!

``` js
console.log(`Started`)
```