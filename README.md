# Universal Addon Hub

Private control panel and universal music add-on gateway.

This repository contains the Universal Addon Hub v1.0.5 source bundle and Render deployment setup.

## Deploy on Render

This app needs a persistent disk because it stores its SQLite database and managed add-on data.

1. Open the Render Blueprint link for this repository.
2. Review the service and persistent-disk cost.
3. Add the required environment variables from `.env.example`:
   - `PUBLIC_BASE_URL` and `MINI_APP_URL`: the final Render HTTPS URL
   - `TELEGRAM_BOT_TOKEN`: token from BotFather
   - `TELEGRAM_OWNER_IDS`: your numeric Telegram user ID
   - `DATA_ENCRYPTION_KEY`: 64 hex characters
   - `PUBLIC_URL_SECRET`: independent secret of at least 32 characters
4. Apply the Blueprint.

Do not commit real bot tokens or encryption keys. Keep them in Render's Environment settings.

## Source

The complete, tested v1.0.5 project is included in `hub-source.zip`. Render extracts it before installing dependencies and starting the app.

Health check: `/healthz`
