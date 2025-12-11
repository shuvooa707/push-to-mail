# Send Email on Push via GitHub Actions

This repository contains a GitHub Actions workflow that automatically sends an email every time a commit is pushed to the `main` branch.

## What It Does

- Triggers on `push` events to the `main` branch
- Sends an email using SMTP via `dawidd6/action-send-mail`
- Supports multiple recipients (To, CC, BCC)
- Accepts attachments
- Converts Markdown to HTML if enabled
- Uses Mailtrap SMTP credentials for testing

## Workflow Location

`.github/workflows/send-email.yml`

## Workflow Overview

The workflow sends an email with:

- Custom subject and body
- Multiple recipients
- Optional attachments
- Reply-To and In-Reply-To headers
- Adjustable priority

## Requirements

You need:

- A functional SMTP server (Mailtrap, Gmail, SendGrid, etc.)
- Valid SMTP username and password
- GitHub Actions enabled on the repo

## Setup

1. Update SMTP credentials with your real values.
2. Replace the email addresses with actual recipients.
3. Commit the workflow file.
4. Push to the `main` branch.
5. The email will be sent automatically.

## Security

Use GitHub Secrets for credentials:

```yaml
username: ${{ secrets.SMTP_USERNAME }}
password: ${{ secrets.SMTP_PASSWORD }}
