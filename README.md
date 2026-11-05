# Universal Addon Hub

One place to manage music add-on links and their expiry reminders.

## Render Free deployment

This repository is configured for a **free Render web service** in Singapore.

The free service has an ephemeral filesystem. Data saved by the app can disappear when Render restarts, sleeps, or redeploys it. Therefore this free deployment is suitable for a preview/test only until a durable free data store is connected. Do not rely on it as the only copy of important add-on links or expiry records.

## Deploy

1. Connect this repository to Render.
2. Choose Arnav's workspace and Singapore.
3. Confirm the service plan says **Free** and there is no disk or paid database.
4. Set the required secrets in Render's private environment form. Never put bot tokens, access codes, session secrets, or encryption keys in GitHub.
5. After deployment, check `/healthz`.

Build command reconstructs the bundled application source from `bundle/*.b64` and installs dependencies. Start command is `npm start`.

## Important

- This repository is currently **public**. Do not commit private user data or secrets.
- Render Free web services can sleep after 15 minutes of inactivity and may take about a minute to wake.
- The Telegram bot needs its own bot token and owner ID before notifications can be active.
- Package inspection and link management do not prove every Mornye, BitChord, Eclipse, or LastWave provider can play. Each provider must be tested in the target app.
- The app's local data folder is ephemeral on Render Free. A durable external database/store must be connected before treating expiry reminders as dependable.

## Local run

Use Node.js 22 or later.

```sh
npm install
npm start
```
