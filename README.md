# Universal Addon Hub

One place to manage music add-on links and their expiry reminders.

## Deploy on Render

1. Open the Render Blueprint link:
   https://dashboard.render.com/blueprint/new?repo=https://github.com/heobeep/universal-addon-hub
2. Choose **Arnav's workspace**.
3. Review the service and permanent-storage price shown by Render before applying.
4. Fill the required values in Render's private environment-variable form. Do not put bot tokens or encryption keys in GitHub.
5. Apply the Blueprint. Render will build the source bundle in this repository and start the app.

The service uses a permanent disk at `/var/data` so saved add-on links, settings and bot state survive restarts.

## Important

- This repository is currently **public**.
- Never commit `.env`, bot tokens, access codes, session secrets or encryption keys.
- The deployment must be checked at `/healthz` after Render finishes building.
- The Hub's package checks and link-management features do not by themselves mean every Mornye, BitChord, Eclipse or LastWave provider is already playable through every app. Provider compatibility must be tested against the actual app and add-on.

## Local run

Use Node.js 22 or later.

```sh
npm install
npm start
```

See `START-HERE.md` for the simple project walkthrough.
