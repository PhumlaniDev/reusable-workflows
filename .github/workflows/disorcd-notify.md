# Discord Notification Workflow

This workflow sends a notification to a Discord channel using a webhook. It is designed to be used as a reusable workflow from other GitHub Actions workflows.

## Triggers

- As a reusable workflow (`workflow_call`)

## Inputs

- `status` (string, required): Status of the workflow or event.
- `title` (string, required): Title for the Discord embed.
- `description` (string, required): Description for the Discord embed.
- `color` (string, optional): Embed color (default: `7506394` for blue).

## Secrets Required

- `DISCORD_WEBHOOK`: The Discord webhook URL.

## Jobs

- **send-notification**:
  - Sends a Discord embed message with the provided title, description, and color.

---
