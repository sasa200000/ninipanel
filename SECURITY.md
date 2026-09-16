# Security Policy — NiniPanel

## Supported Versions

| Version | Supported |
| ------- | --------- |
| 5.x     | ✅        |

## Reporting a Vulnerability

**Do not open a public issue.** Report privately:

- GitHub: Security tab → Report a vulnerability (private vulnerability reporting)
- Telegram: @sedef3345

We aim to respond within 72 hours.

## Built-in Protections

- Admin password hashed in Cloudflare KV, session cookies `HttpOnly` + `Secure`
- Login brute-force shield: 5 wrong attempts → 15-minute IP block (HTTP 429)
- Security headers on every page (`nosniff`, `DENY` framing, no referrer)
- No secrets in code: passwords, UUIDs and tokens live only in KV / env vars
- Per-user credentials with expiry, traffic quota and connection limits

## Operator Checklist

1. Enable 2FA on your GitHub account (Settings → Password and authentication)
2. Never commit `.env`, `data/` or tokens — secret scanning + push protection stay ON
3. Branch `main` is protected: no force-push, no deletion
4. Roll Cloudflare API tokens and panel passwords periodically
5. Use `PANEL_PASSWORD` env var on server deploys, never the default password
