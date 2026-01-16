---

sidebar_position: 1

---

# Intro

Merci d'avoir choisi cette alternative open-source à Discord ! Il est recommandé de lire cette page en entier pour comprendre comment le configurer selon vos besoins.

## Mise en route

Commencez par **cloner le dépôt GitHub**.

### Ce dont vous aurez besoin

- [Node.js](https://nodejs.org/en/download/) version 20.0 ou supérieure :
  - Lors de l'installation de Node.js, il est recommandé de cocher toutes les cases relatives aux dépendances.

:::warning

RtCord est connu pour avoir des problèmes avec Node 18, nous n'avons pas encore réussi à corriger ce problème.

:::

## Configuration du .env

Vous avez peut-être vu un fichier `.env.dummy` dans votre dépôt cloné, et vous avez peut-être aussi regardé à l'intérieur de ce fichier. Cette partie va expliquer à quoi correspondent les valeurs.

- `PORT` - Par défaut **7777**, vous pouvez le modifier si vous souhaitez l'héberger sur un port différent.
- `SESSION_SECRET` - Par défaut **secret**, c'est la clé de chiffrement pour le cookie de session, il est **fortement recommandé** de changer cette valeur.
- `WEBHOOK`/`WEBHOOK2` : Webhooks Discord, pour plus d'infos, regardez [ici](/).
- `MODE` - Par défaut **server**, cela ne peut être que **dev** ou **server**.

## Installation des dépendances

L'installation des dépendances est très facile :

```bash
npm i

```

## Démarrer votre serveur

Lancez le serveur RtCord :

```bash
node .

```

Le `node .` lance le serveur [Express](https://expressjs.com), prêt à être consulté sur http://localhost:7777/.