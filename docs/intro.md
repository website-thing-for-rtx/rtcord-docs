---
sidebar_position: 1
---

# Intro
Thanks for choosing this open-source alternative to Discord! It's recommended you read this page fully to understand how to set it up for your needs.

## Getting Started

Get started by **cloning the GitHub repo**.

### What you'll need

- [Node.js](https://nodejs.org/en/download/) version 20.0 or above:
  - When installing Node.js, you are recommended to check all checkboxes related to dependencies.

:::warning

RtCord is known to have some issues with Node 18, we have not yet managed to fix this issue.

:::

## Configuring .env
You might have seen a ``.env.dummy`` file in your cloned repo, you might have also looked inside this file. This part is onna explain what values need to be for what.

- ``PORT`` - The default is **7777**, you may change that if you want it to be hosted on a different port.
- ``SESSION_SECRET`` - The default is **secret**, it is the encryption key for the session cookie, it is **highly recommended** to change this value.
- ``WEBHOOK``/``WEBHOOK2``: Discord webhooks, if you want more info check [here](/).
- ``MODE`` - The default is **server**, this can only be **dev** or **server**.

## Installing depedencies
Installing the depedencies is very easy:

```bash
npm i
```

## Start your server

Run the RtCord server:

```bash
node .
```

The `node .` starts the [Express](https://expressjs.com) server, ready for you to view at http://localhost:7777/.