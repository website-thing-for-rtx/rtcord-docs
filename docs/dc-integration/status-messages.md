---
sidebar_position: 1
---

# Status Messages

One of the most important of webhooks is the **status webhook**.

## Setting up
This section will obviously require a Discord webhook, so create it and put it in .env at key ``WEBHOOK``

:::danger

Do not put your Discord webhook in .env.dummy, this file is not ignored by Git, which means if you push your changes, anyone will be able to see and use your Discord webhook.

:::

## Modifying the code
This may sound scary, but don't worry, we only need to change **one line**, open the ``index.js`` file, and scroll to ``if (mode == "server")``, right after you should see an ``await sendDiscordWEbhook(...)``
To change the ping role (the one in ``'content'``), you will need to get your whole role name (not just @status ping), it should look soemthing like ``<@&1455969806132973744>``, once you got that, we can continue:

```js title="src/index.js"
if (mode == "server")
  await sendDiscordWebhook({
        content: 'replace with the whole role name', 
          embeds: [
            {
              title: 'power on',
              description: 'rtcord is on',
              color: 0x00ff00,
              timestamp: new Date().toISOString(),
            },
          ],
        }, false);
```

For now we only modified the startup part, but there also one for shutdown, scroll down to ``process.on('SIGINT', async () => {})``, then change the code the same way we did before.