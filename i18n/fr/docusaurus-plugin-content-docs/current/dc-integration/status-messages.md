---
sidebar_position: 1
---

# Messages de statut

L’un des webhooks les plus importants est le **webhook de statut**.

## Mise en place
Cette partie nécessite évidemment un webhook Discord, donc crée-en un et mets-le dans le fichier `.env` avec la clé `WEBHOOK`.

:::danger

Ne mets **pas** ton webhook Discord dans `.env.dummy`.  
Ce fichier n’est **pas ignoré par Git**, ce qui veut dire que si tu pushes tes changements, **n’importe qui pourra voir et utiliser ton webhook Discord**.

:::

## Modification du code
Ça peut sembler flippant, mais t’inquiète, on doit changer **une seule ligne**.  
Ouvre le fichier `index.js` et descends jusqu’à `if (mode == "server")`.  
Juste après, tu devrais voir un `await sendDiscordWebhook(...)`.

Pour changer le rôle ping (celui dans `content`), tu dois récupérer **le nom complet du rôle**, pas juste `@status ping`.  
Ça doit ressembler à quelque chose comme `<@&1455969806132973744>`.  
Une fois que tu l’as, on peut continuer :

```js title="src/index.js"
if (mode == "server")
  await sendDiscordWebhook({
        content: 'remplace par le nom complet du rôle',
          embeds: [
            {
              title: 'power on',
              description: 'rtcord est allumé',
              color: 0x00ff00,
              timestamp: new Date().toISOString(),
            },
          ],
        }, false);
```

Pour l’instant, on a seulement modifié la partie **démarrage**,
mais il y en a aussi une pour **l’arrêt**.

Descends jusqu’à ``process.on('SIGINT', async () => {})``,
puis modifie le code exactement de la même manière qu’avant.