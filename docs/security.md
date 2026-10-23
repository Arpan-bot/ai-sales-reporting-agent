# Security Checklist Before Publishing on GitHub

- [ ] Rotate the Make webhook URL that appeared in screenshots or conversations; replace it in Botpress and disable the old endpoint.
- [ ] Do not upload a Make blueprint until you have checked its **entire text** for webhook URLs, keys, tokens, headers, connection IDs, and personal information.
- [ ] Remove email addresses, account avatars/names, recipient data, and private links from screenshots.
- [ ] Avoid screenshots of Botpress HTTP Request tools when the URL is visible.
- [ ] Never upload Google OAuth tokens, credentials, or cookies.
- [ ] Publish only the fictional sales dataset, not work or client data.
- [ ] Use Gmail **Create Draft Email**, not Send Email, while demonstrating this project.
- [ ] Review all files before clicking Commit changes on a **public** repository.

If you accidentally publish a secret, revoke or rotate it immediately with the service provider. Deleting it from a later commit is not enough to guarantee it disappears from Git history.
